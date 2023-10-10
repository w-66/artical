# \[Shell]exit

| 分类   |                  |
| ---- | ---------------- |
| 简介   |                  |
| 标签   | 内置               |
| 创建时间 | 2022/06/24 10:42 |

[http://c.biancheng.net/view/1145.html](http://c.biancheng.net/view/1145.html "http://c.biancheng.net/view/1145.html")

<http://c.biancheng.net/view/1145.html>

-   快照

    exit 是一个 [Shell 内置命令](http://c.biancheng.net/view/1136.html "Shell 内置命令")，用来退出当前 Shell 进程，并返回一个退出状态；使用`$?`可以接收这个退出状态，这一点已在《[Shell \$?](http://c.biancheng.net/view/808.html "Shell \$?")》中进行了讲解。

    exit 命令可以接受一个整数值作为参数，代表退出状态。如果不指定，默认状态值是 0。

    一般情况下，退出状态为 0 表示成功，退出状态为非 0 表示执行失败（出错）了。

    exit 退出状态只能是一个介于 0\~255 之间的整数，其中只有 0 表示成功，其它值都表示失败。

    Shell 进程执行出错时，可以根据退出状态来判断具体出现了什么错误，比如打开一个文件时，我们可以指定 1 表示文件不存在，2 表示文件没有读取权限，3 表示文件类型不对。

    编写下面的脚本，并命名为 [test.sh](http://test.sh "test.sh")：
    ```text
    echo "befor exit"exit 8echo "after exit"
    ```
    运行该脚本：

    \\\[mozhiyan\@localhost \~\\]\$ bash ./test.sh &#x20;

    befor exit

    可以看到，`"after exit"`并没有输出，这说明遇到 exit 命令后，[test.sh](http://test.sh "test.sh") 执行就结束了。
    > 注意，exit 表示退出当前 Shell 进程，我们必须在新进程中运行 [test.sh](http://test.sh "test.sh")，否则当前 Shell 会话（终端窗口）会被关闭，我们就无法看到输出结果了。
    我们可以紧接着使用`$?`来获取 [test.sh](http://test.sh "test.sh") 的退出状态：

    \\\[mozhiyan\@localhost \~\\]\$ echo \$? &#x20;

    8
