# \[Shell]命令替换：将命令的输出结果赋值给变量

<http://c.biancheng.net/view/1164.html>

(# 着重号=反引号) (# shell中运行命令)

***

` `` `

`$()`

***

shell 中有两种方式可以完成命令替换，一种是反引号\`\`，一种是`$()`，使用方法如下：

Shell 命令替换是指 将命令的输出结果赋值给某个变量。比如，在某个目录中输入 ls 命令可查看当前目录中所有的文件，但如何将输出内容存入某个变量中呢？这就需要使用命令替换了，这也是 Shell 编程中使用非常频繁的功能。

```纯文本
variable=`commands`
variable=$(commands)
```

\[对比]变量声明符号对比： \`\`|`$()`

&#x20;` `` `反引号：阅读代码相对不好；`$()`支持嵌套

`$()`反引号： ` `` `在多种Shell中使用，`$()`仅在bash shell中有效

-   示例：计算脚本运行所消耗的时间  \[`%s`]
    ```纯文本
    #!/bin/bash

    begin_time=`date +%s`    #开始时间，使用``替换
    sleep 20s                #休眠20秒
    finish_time=$(date +%s)  #结束时间，使用$()替换
    run_time=$((finish_time - begin_time))  #时间差

    echo "begin time: $begin_time"
    echo "finish time: $finish_time"
    echo "run time: ${run_time}s"
    ```
    ```纯文本
    运行脚本，20 秒后可以看到输出结果：
    begin time: 1555639864
    finish time: 1555639884
    run time: 20s
    ```
    第 6 行代码中的`(( ))`是 Shell 数学计算命令。和 [C++](http://c.biancheng.net/cplus/ "C++")、[C#](http://c.biancheng.net/csharp/ "C#")、[Java](http://c.biancheng.net/java/ "Java") 等编程语言不同，在 Shell 中进行数据计算不那么方便，必须使用专门的数学计算命令，`(( ))`就是其中之一。更多细节我们将会在《[Shell数学计算](http://c.biancheng.net/view/1169.html "Shell数学计算")》一节中详细讲解。
-   示例：输出时间 \[` `` `,`$()`,[\[Linux\]date](\[Linux]date_qiVWra7JVUe1qYbHvoZCqn.md "\[Linux]date")`%S``%d``%H``%M`]
    ```python
     time1=`date '+%S %d'`
     time2=$(date +%H:%M:%S)
     echo "$time1"
     echo "$time2"
    ```
    ```python
    ]# ./text.sh   
    50 10
    02:49:50
    ```
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



# 示例

-   示例：在shell中变量赋值，查询MySQL进程号(只要进程号) \[\`\``$()`]
    ```纯文本
    mysqlPid=`ps aux | grep [m]ysql | awk '{print $2}'`
    echo ${mysqlPid}

    ```
    ```纯文本
    mysqlPid=$(ps aux | grep [m]ysql | awk '{print $2}')
    echo ${mysqlPid}
    ```
-   示例2：\[对比]变量声明符号对比： \`\`|`$()`：下面的例子演示了使用计算 ls 命令列出的第一个文件的行数，这里使用了两层嵌套。
    ```纯文本
    [c.biancheng.net]$ Fir_File_Lines=$(wc -l $(ls | sed -n '1p'))
    [c.biancheng.net]$ echo "$Fir_File_Lines"
    36 anaconda-ks.cfg
    ```
-   示例1：date 命令用来获得当前的系统时间，使用命令替换可以将它的结果赋值给一个变量。
    ```纯文本
    sec=`date +%S`  # 当前秒数赋予给sec
    minute=$(date +%M)  # 当前分钟赋予给minute
    ```
    ```纯文本
    echo $minute      
    46

    echo $sec
    40

    ```

