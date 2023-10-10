# \[Shell]符号集合

1.  ''
2.  ""
3.  无包含状态
4.  \=

<!---->

1.  `{}`
2.  `[]`
3.  `()`
4.  `$`



***

`${}`：使用变量﻿ \[`$``{}`]

`$()`：命令结果赋值 \[﻿`$``()`]

`${}`

`$()`

\`\`

着重号；反引号

\#

:

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



@

\*



[\[Shell\]数学|逻辑计算](\[Shell]数学-逻辑计算_kHX6nR7Mjn6RbrQtq9Wgbq.md "\[Shell]数学|逻辑计算")

[Linux系统中的变量](Linux系统中的变量_eqQdAVGQKfyhXNHDGdSy6S.md "Linux系统中的变量")

