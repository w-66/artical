# \[Shell]变量

[Linux系统中的变量](Linux系统中的变量_eqQdAVGQKfyhXNHDGdSy6S.md "Linux系统中的变量")

***

-   \[Shell]定义变量
    1.  Shell 支持以下三种定义变量的方式 \['',"",无包含状态]
        ```纯文本
        variable=value
        variable='value'  
        variable="value"
        ```
        variable 是变量名，value 是赋给变量的值

        **\[注意]**赋值号=的周围不能有空格
    2.  Shell 变量的命名规范和大部分编程语言都一样
        -   变量名由数字、字母、下划线组成；
        -   必须以字母或者下划线开头；
        -   不能使用 Shell 里的关键字（通过 help 命令可以查看保留关键字）。
-   \[Shell]使用变量

    使用定义过的变量，只要在变量名前面加美元符号`$`即可 \[''""`${}`]
    ```纯文本
    author="ee"
    echo $author
    echo ${author}  「推荐给所有变量加上花括号{ }，这是个良好的编程习惯。」
    ```
    示例：变量名外面的花括号`{}`是可选的，加不加都行，加花括号是为了帮助解释器识别变量的边界，比如下面这种情况：
    ```纯文本
    skill="Java"
    echo "I am good at ${skill}Script"
    ```

-   \[Shell]修改变量的值
    ```纯文本
    url="123"
    echo ${url}
    url="345"
    echo ${url}
    ```
-   \[Shell]\[对比]单引号''和双引号""及 无包含状态 的对比
    -   单引号包含的字符串，只是字符串
    -   双引号包含的字符串，可以输出变量值
    以单引号''包围变量的值时
    -   单引号里面是什么就输出什么，即使内容中有变量和命令（命令需要反引起来）也会把它们原样输出。这种方式比较适合定义显示纯字符串的情况，即不希望解析变量、命令等的场景。
    -   字符串中不能出现单引号，即使对单引号进行转义也不行。
    以双引号""包围变量的值时
    -   输出时会先解析里面的变量和命令，而不是把双引号中的变量名和命令原样输出。这种方式比较适合字符串中附带有变量和命令并且想将其解析后再输出的变量定义。
    -   字符串中可以出现双引号，只要它被转义了就行。
    > 「P.S」其他没有特别要求的字符串等最好都加上双引号，定义变量时加双引号是最常见的使用场景。
    无包含状态
    -   不被引号包围的字符串中出现变量时也会被解析，这一点和双引号`" "`包围的字符串一样。
    -   字符串中不能出现空格，否则空格后边的字符串会作为其他变量或者命令解析。

    <!---->

    -   示例：单引号与双引号 包含字符串 对输出结果的影响
        ```bash
        $ ll
        total 8
        drwxrwxr-x 2 ubuntu ubuntu 4096 May 14 23:16 ./
        drwxrwxr-x 4 ubuntu ubuntu 4096 May 14 23:15 ../
        -rw-rw-r-- 1 ubuntu ubuntu    0 May 14 23:16 file1
        -rw-rw-r-- 1 ubuntu ubuntu    0 May 14 23:16 file2

         $ lsl=$(ls -l) 

        $ echo $lsl
        total 0 -rw-rw-r-- 1 ubuntu ubuntu 0 May 14 23:16 file1 -rw-rw-r-- 1 ubuntu ubuntu 0 May 14 23:16 file2

         $ echo '$lsl'
         $lsl 
         
         $ echo "$lsl"
         total 0
        -rw-rw-r-- 1 ubuntu ubuntu 0 May 14 23:16 file1
        -rw-rw-r-- 1 ubuntu ubuntu 0 May 14 23:16 file2
        ```
        所以，为了防止出现格式混乱的情况，我建议在输出变量时加上双引号。&#x20;
        1.  \[问题2]echo 单引号只输出字符串，双引号是执行其中的命令 \['',""]
            ```纯文本
            $touch test.txt

            $ echo 'echo $$' >> test.txt 
            $ cat test.txt 
            echo $$

            $ echo "echo $$" >> test.txt   
            $ cat test.txt               
            echo $$
            echo 238335
            ```
-   \[Shell]将命令的结果赋值给变量 \[\`\`]
    > 详情[\[Shell\]命令替换：将命令的输出结果赋值给变量](\[Shell]命令替换：将命令的输出结果赋值给变量_wBnu8AVwxZuiDX5SzSGzuB.md "\[Shell]命令替换：将命令的输出结果赋值给变量")
    Shell 也支持将命令的执行结果赋值给变量，常见的有以下两种方式：\[\`\` ,`$()`]
    ```纯文本
    variable=`command`
    variable=$(command)  「推荐」
    ```
    第一种方式把命令用反引号\`\`（位于 Esc 键的下方）包围起来，反引号和单引号非常相似，容易产生混淆，所以不推荐使用这种方式；第二种方式把命令用\$()包围起来，区分更加明显，所以推荐使用这种方式。
    -   示例1：使用 cat 命令将 log.txt 的内容读取出来，并赋值给一个变量，然后使用 echo 命令输出 \[=`$``$()`]
        ```纯文本
        # cat log.txt 
        log1
        log2
        log3
        log4

        # log=$(cat log.txt)
        # echo $log
        log1 log2 log3 log4

        ```
        复制后的log变量 不会随着文件log.txt变化，除非重新赋值

-   \[Shell]只读变量readonly

    使用 **readonly** 命令可以将变量定义为只读变量，只读变量的值不能被改变。
    ```纯文本
    #!/bin/bash

    myUrl="hello"
    readonly myUrl
    myUrl="123"
    ```
    运行
    ```纯文本
    $ ./test.sh 
    ./test.sh: line 5: myUrl: readonly variable
    ubuntu@VM-16-5-ubuntu:~/myProgram$ 
    ```
-   \[Shell]删除变量**unset**&#x20;

    使用 **unset** 命令可以删除变量，unset 命令不能删除只读变量
    #### 示例
    -   示例1
        ```纯文本
        #!/bin/sh

        myUrl="http://c.biancheng.net/shell/"
         unset myUrl 
        echo $myUrl
        ```

