# \[shell]if

bash shell会按顺序执行if语句，如果command执行后且它的返回状态是**`0`**(零表示真)，则会执行符合该条件执行的语句，否则后面的命令不执行，跳到下一条命令。 &#x20;

当有多个嵌套时，只有第一个返回0退出状态的命令会导致符合该条件执行的语句部分被执行,如果所有的语句的执行状态都不为0，则执行else中语句。 &#x20;


返回状态：最后一个命令的退出状态，或者当没有条件是真的话为0。

-   注意
    ```bash
    、[ ]表示条件测试。注意这里的空格很重要。要注意在'['后面和']'前面都必须要有空格
    、在shell中，then和fi是分开的语句。如果要在同一行里面输入，则需要用分号将他们隔开。
    、注意if判断中对于变量的处理，需要加引号，以免一些不必要的错误。没有加双引号会在一些含空格等的字符串变量判断的时候产生错误。比如[ -n "$var" ]如果var为空会出错
    、判断是不支持浮点值的
    、如果只单独使用>或者<号，系统会认为是输出或者输入重定向，虽然结果显示正确，但是其实是错误的，因此要对这些符号进行转意
    、在默认中，运行if语句中的命令所产生的错误信息仍然出现在脚本的输出结果中
    、使用-z或者-n来检查长度的时候，没有定义的变量也为0
    、空变量和没有初始化的变量可能会对shell脚本测试产生灾难性的影响，因此在不确定变量的内容的时候，在测试号前使用-n或者-z测试一下
    、? 变量包含了之前执行命令的退出状态（最近完成的前台进程）（可以用于检测退出状态）
    ```



相关：[\[Shell\]数学|逻辑计算](\[Shell]数学-逻辑计算_kHX6nR7Mjn6RbrQtq9Wgbq.md "\[Shell]数学|逻辑计算")



一、if的基本语法:

```powershell
if [ command ];then
   符合该条件执行的语句
elif [ command ];then
   符合该条件执行的语句
else
   符合该条件执行的语句 
fi 
```

```纯文本
多分支：
if [ 条件 ];then
  statement1
​  .....
elif  [ 条件2 ];then
​  statement2
​  ....
else
​  statement3
​  ....
fi

```

-   1.文件/文件夹(目录)判断

    `[-e]`

    `[ -e FILE ] `如果 指定的文件或目录存在时返回为真。
    ```powershell
    [ -a FILE ] 如果 FILE 存在则为真。文件是否存在 
    [ -d DIR  ] 如果 FILE 存在且是一个目录则为真。
    [ -e FILE ] 如果 指定的文件或目录存在时返回为真。
    [ -f FILE ] 如果 FILE 存在且是一个普通文件则为真。测试是否普通文件
    [ -r FILE ] 如果 FILE 存在且是可读的则为真。
    [ -w FILE ] 如果 FILE存在且是可写的则为真。
    [ -x FILE ] 如果 FILE 存在且是可执行的则为真。
    [ -h FILE ] 测试是否符号链接文件

    [ -b FILE ] 如果 FILE 存在且是一个块特殊文件则为真。测试是否块设备文件
    [ -c FILE ] 如果 FILE 存在且是一个字特殊文件则为真。测试是否字符设备文件
    [ -g FILE ] 如果 FILE 存在且已经设置了SGID则为真。
    [ -k FILE ] 如果 FILE 存在且已经设置了粘制位则为真。
    [ -p FILE ] 如果 FILE 存在且是一个名字管道(F如果O)则为真。
    [ -s FILE ] 如果 FILE 存在且大小不为0则为真。
    [ -t FD   ] 如果文件描述符 FD 打开且指向一个终端则为真。
    [ -u FILE ] 如果 FILE 存在且设置了SUID (set user ID)则为真。
    [ -O FILE ] 如果 FILE 存在且属有效用户ID则为真。
    [ -G FILE ] 如果 FILE 存在且属有效用户组则为真。
    [ -L FILE ] 如果 FILE 存在且是一个符号连接则为真。测试是否是符号链接文件
    [ -N FILE ] 如果 FILE 存在 and has been mod如果ied since it was last read则为真。
    [ -S FILE ] 如果 FILE 存在且是一个套接字则为真。
    [ FILE1 -nt FILE2 ] 如果 FILE1 has been changed more recently than FILE2, or 如果 FILE1 exists and FILE2 does not则为真。
    [ FILE1 -ot FILE2 ] 如果 FILE1 比 FILE2 要老, 或者 FILE2 存在且 FILE1 不存在则为真。
    [ FILE1 -ef FILE2 ] 如果 FILE1 和 FILE2 指向相同的设备和节点号则为真。
    ```
-   字符串判断

    `[ -z STRING ]`

    如果STRING的长度为零则为真 ，即判断是否为空，空即是真；检测字符是否为空，空则真，不空则假    如: \[ -z "" ]为真空则为真


    `[ -n STRING ]`

    如果STRING的长度非零则为真 ，即判断是否为非空，非空即是真；检测字符是否不空，不空则真，不空则假


    `[ STRING1 ]`

    &#x20;如果字符串不为空则返回为真,与`[ -n STRING ]`类似

    `[ STRING1 == STRING2 ]`&#x20;

    如果两个字符串相同则返回为真


    `[ STRING1 != STRING2 ] `

    如果字符串不相同则返回为真


    `[ STRING1 < STRING2 ]`&#x20;

    如果 “STRING1”字典排序在“STRING2”前面则返回为真。

    `[ STRING1 > STRING2 ]`&#x20;

    如果 “STRING1”字典排序在“STRING2”后面则返回为真。

    `[[  ]]`

    字符相比较大小用\[\[  ]]，比的是第一个字母（a-zA-Z）都是大写或者都是小写比较ascii值越大则越大，有大写又有小写则A>a B>b   但是A不大于b的情况
    > 「P.S」`$?`
    ```纯文本
    [root@slave02 ~]# [[ "A" < "B" ]]
    [root@slave02 ~]# echo $?
    0
    [root@slave02 ~]# [[ "a" < "b" ]]
    [root@slave02 ~]# echo $?
    0
      
    ```
-   数值判断
-   4.逻辑判断
    ```bash
    [ ! EXPR ] 逻辑非，如果 EXPR 是false则返回为真。
    [ EXPR1 -a EXPR2 ] 逻辑与，如果 EXPR1 and EXPR2 全真则返回为真。
    [ EXPR1 -o EXPR2 ] 逻辑或，如果 EXPR1 或者 EXPR2 为真则返回为真。
    [ ] || [ ] 用OR来合并两个条件
    [ ] && [ ] 用AND来合并两个条件
    ```

#### 示例

-   示例：Bash 代码块

