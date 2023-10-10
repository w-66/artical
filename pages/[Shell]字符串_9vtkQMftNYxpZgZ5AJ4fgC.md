# \[Shell]字符串

-   \[Shell]获取字符串长度 \[#]
    ```bash
    ${#string_name}
    ```
    示例
    ```bash
    #!/bin/bash

    str="123abc"
    echo ${#str}
    ```
    6
-   \[Shell]字符串拼接（连接、合并）\[""]
    ```bash
    #!/bin/bash

    name="谢谢你"
    url="因为有你"

    str1=$name$url  #中间不能有空格
    str2="$name $url"  #如果被双引号包围，那么中间可以有空格
    str3=$name": "$url  #中间可以出现别的字符串
    str4="$name: $url"  #这样写也可以
    str5="${name}丫: ${url}！"  #这个时候需要给变量名加上大括号

    echo $str1
    echo $str2
    echo $str3
    echo $str4
    echo $str5
    ```
    输出
    ```bash
    ./2test.sh   
    谢谢你因为有你
    谢谢你 因为有你
    谢谢你: 因为有你
    谢谢你: 因为有你
    谢谢你丫: 因为有你！
    ```
-   \[Shell]字符串截取 \[:]

    这种方式需要两个参数：除了指定起始位置，还需要截取长度，才能最终确定要截取的字符串。
    #### 从字符串左边开始计数
    ```bash
    ${string: start :length}
    ```
    其中，string 是要截取的字符串，start 是起始位置（从左边开始，从 0 开始计数），length 是要截取的长度（省略的话表示直到字符串的末尾）。
    -   示例1：从字符串左边开始计数
        ```bash
        ubuntu@VM-16-5-ubuntu:~$ user="Administrator"
        ubuntu@VM-16-5-ubuntu:~$ echo ${user:0:5}  # 截取0位之后到第5位的字符串
        Admin

        ubuntu@VM-16-5-ubuntu:~$ echo ${user:5}  #截取第五位之后的字符串
        istrator

        ```
    #### 从右边开始计数
    ```bash
    ${string:  0- start :length}
    ```
    -   示例2：从右边开始计数
        ```bash
        ubuntu@VM-16-5-ubuntu:~$   user="Administrator"
        ubuntu@VM-16-5-ubuntu:~$ echo ${user:0-13:13}  # 从右往左数第13位到从右往左数第13位
        Administrator

        ubuntu@VM-16-5-ubuntu:~$ echo ${user:0-13:12}  # 从右往左数第13位到从右往左数第12位
        Administrato 

        ubuntu@VM-16-5-ubuntu:~$ echo ${user:0-13:5}   # 从右往左数第13位到从右往左数第5位
        Admin

        ```
    > 这里需要强调两点
    >
    > -   从左边开始计数时，起始数字是 0（这符合程序员思维）；从右边开始计数时，起始数字是 1（这符合常人思维）。计数方向不同，起始数字也不同。
    > -   不管从哪边开始计数，截取方向都是从左到右。
    #### 从指定字符（子字符串）开始截取
    这种截取方式无法指定字符串长度，只能从指定字符（子字符串）截取到字符串末尾。Shell 可以截取指定字符（子字符串）右边的所有字符，也可以截取左边的所有字符。
    #### 使用 # 号截取右边字符
    使用`#`号可以截取第一次匹配的指定字符（或者子字符串）右边的所有字符，具体格式如下：
    ```bash
    ${string#*chars}
    ```
    从 string 字符串最后一次出现 \*chars 的位置开始，截取 \*chars 右边的所有字符。
    ```bash
    ${string##*chars}
    ```
    string 表示要截取的字符，chars 是指定的字符（或者子字符串），`*`是通配符的一种，表示任意长度的字符串。`*chars`连起来使用的意思是：忽略左边的所有字符，直到遇见 chars（chars 不会被截取）。
    -   示例3：使用 # 号截取右边字符
        ```bash
        ubuntu@VM-16-5-ubuntu:~$   user="Administrator"
        ubuntu@VM-16-5-ubuntu:~$ echo ${user#*Admin}  # 从匹配第一个Admin 这个字符串 之后开始截取后面所有字符串
        istrato

        ubuntu@VM-16-5-ubuntu:~$ echo ${user#*n}  
        istrator

        ubuntu@VM-16-5-ubuntu:~$ echo ${user#*i}
        nistrator

        ubuntu@VM-16-5-ubuntu:~$ echo ${user#Admin}  # 如果不加*星号，则表示只有完全匹配了Admin整个字符串之后才开始从之后截取字符串，*星号就如同正则的通配符
        istrator

        ubuntu@VM-16-5-ubuntu:~$ echo ${user#*i}   
        nistrator
        ubuntu@VM-16-5-ubuntu:~$ echo ${user##*i}  # Admini strator  匹配最后一次出现的i字符串开始截取之后的字符串
        strator
        ```
    #### 使用 % 截取左边字符
    使用`%`号可以截取指定字符（或者子字符串）左边的所有字符，具体格式如下：
    ```bash
    ${string%chars*}
    ```
    从 string 字符串最后一次出现 \*chars 的位置开始，截取 \*chars 左边的所有字符
    ```bash
    ${string%%*chars}
    ```
    -   示例4：使用 % 截取左边字符
        ```bash
        ubuntu@VM-16-5-ubuntu:~$   user="Administrator"
        ubuntu@VM-16-5-ubuntu:~$ echo ${user%istrator*}
        Admin

        ubuntu@VM-16-5-ubuntu:~$ echo ${user%tra}  # 此处没有匹配到所以全部显示了
        Administrator

        ubuntu@VM-16-5-ubuntu:~$ echo ${user%tra*}
        Adminis

        ```
-   Shell转义字符<参考[正则 符号\[reg.\]](<正则 符号\[reg.]_bUBxxrx8vz57vaLdMYwgYN.md> "正则 符号\[reg.]")>

    \n

    表示新行

    \r

    表示回车

    \t

    表示水平的制表符

    \v

    表示垂直的制表符

    \b

    表示后退符

    \a

    表示“警告”（蜂鸣或是闪动）

    \0xx

    翻译成ASCII码为八进制\_0xx\_所表示的字符

***

#### echo输出转义字符

`-e`

`-e` 启用转义字符，`\n`表示换行，`\t`表示tab，`\c`来强制 echo 命令不换行

enable interpretation of backslash escapes

```text
colorEcho(){
    echo -e "\033[${1}${@:2}\033[0m" 1>& 2
}

```
