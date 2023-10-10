# \[Shell]read

-   read 命令从键盘读取用户输入的内容并赋值给变量
-   read 是 [Shell 内置命令](http://c.biancheng.net/view/1136.html "Shell 内置命令")，用来从标准输入中读取数据并赋值给变量。如果没有进行重定向，默认就是从键盘读取用户输入的数据；如果进行了重定向，那么可以从文件中读取数据。



```bash
read [-options] [variables]
```



`-p`

[prompt](prompt_meNSS7nJ1phhTDxDY78GAB.md "prompt")  output the string PROMPT without a trailing newline before attempting to read

在输入时，给用户的显示提示信息

&#x20;`-s`

do not echo input coming from a terminal
不回显来自终端的输入

`-n`

`-n 1`表示只读取一个字符。运行脚本后，只要用户输入一个字符，立即读取结束，不用等待用户按下回车键。

nchars  return after reading NCHARS characters rather than waiting for a newline, but honor a delimiter if fewer than

`-t`

指定超时时间

timeout  time out and return failure if a complete line of input is not read within TIMEOUT seconds.  The value of the TMOUT variable is the default timeout.  TIMEOUT may be a fractional number.  If TIMEOUT is 0, read returns immediately, without trying to read any data, returning success only if input is available on the specified file descriptor.  The exit status is greater than 128 if the timeout is exceeded

-   `read --help`
    ```text
    read: read [-ers] [-a array] [-d delim] [-i text] [-n nchars] [-N nchars] [-p prompt] [-t timeout] [-u fd] [name ...]
        Read a line from the standard input and split it into fields.
        
        Reads a single line from the standard input, or from file descriptor FD
        if the -u option is supplied.  The line is split into fields as with word
        splitting, and the first word is assigned to the first NAME, the second
        word to the second NAME, and so on, with any leftover words assigned to
        the last NAME.  Only the characters found in $IFS are recognized as word
        delimiters.
        
        If no NAMEs are supplied, the line read is stored in the REPLY variable.
        
        Options:
          -a array  assign the words read to sequential indices of the array
            variable ARRAY, starting at zero
          -d delim  continue until the first character of DELIM is read, rather
            than newline
          -e  use Readline to obtain the line
          -i text  use TEXT as the initial text for Readline
          -n nchars  return after reading NCHARS characters rather than waiting
            for a newline, but honor a delimiter if fewer than
            NCHARS characters are read before the delimiter
          -N nchars  return only after reading exactly NCHARS characters, unless
            EOF is encountered or read times out, ignoring any
            delimiter
          -p prompt  output the string PROMPT without a trailing newline before
            attempting to read
          -r  do not allow backslashes to escape any characters
          -s  do not echo input coming from a terminal
          -t timeout  time out and return failure if a complete line of
            input is not read within TIMEOUT seconds.  The value of the
            TMOUT variable is the default timeout.  TIMEOUT may be a
            fractional number.  If TIMEOUT is 0, read returns
            immediately, without trying to read any data, returning
            success only if input is available on the specified
            file descriptor.  The exit status is greater than 128
            if the timeout is exceeded
          -u fd  read from file descriptor FD instead of the standard input
        
        Exit Status:
        The return code is zero, unless end-of-file is encountered, read times out
        (in which case it's greater than 128), a variable assignment error occurs,
        or an invalid file descriptor is supplied as the argument to -u.

    ```





# 示例

-   示例3：在指定时间内输入密码\[`-t` `-s``-p`]
    ```bash
    #!/bin/bash

    if
        read -t 20 -sp "Enter password in 20 seconds(once) > " pass1 && printf "\n" &&  #第一次输入密码
        read -t 20 -sp "Enter password in 20 seconds(again)> " pass2 && printf "\n" &&  #第二次输入密码
        [ $pass1 == $pass2 ]  #判断两次输入的密码是否相等
    then
        echo "Valid password"
    else
        echo "Invalid password"
    fi
    ```
-   示例2：使用 read 命令给多个变量赋值 \[`-p`]
    ```bash
    #!/bin/bash

    read -p "Enter some information > [name url age]: " name url age
    echo "网站名字：$name"
    echo "网址：$url"
    echo "年龄：$age"
    ```
    运行输出
    ```bash
    ubuntu@VM-16-5-ubuntu:~/myProgram$ ./t.sh   
    Enter some information > [name url age]: jeck www.123.com 100
    网站名字：jeck
    网址：www.123.com
    年龄：100
    ```

-   示例1：read 命令从键盘读取用户输入的内容并赋值给变量

    test.sh的内容
    ```纯文本
      #!/bin/bash
      
      echo "age?" 
      read age
      echo "your age is  $age"
    ```
    输出
    ```纯文本
    $ ./test.txt 
    age?
    18   「此处是手动输入，并回车」
    your age is  18
    ```
