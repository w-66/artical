# \[Shell]变量作用域

Shell 变量的作用域（Scope），就是 Shell 变量的有效范围（可以使用的范围）。

Shell 变量的作用域可以分为三种：

-   有的变量只能在函数内部使用，这叫做局部变量（local variable）；
-   有的变量可以在当前 Shell 进程中使用，这叫做全局变量（global variable）；
-   而有的变量还可以在子进程中使用，这叫做环境变量（environment variable）。

### Shell 局部变量

-   Shell 也支持自定义函数，在 Shell 函数中定义的变量默认也是全局变量，它和在函数外部定义变量拥有一样的效果。例：
    ```纯文本
    #!/bin/bash

    #定义函数
    function func(){
        a=99
    }

    #调用函数
    func

    #输出函数内部的变量
    echo $a
    ```
    输出结果： &#x20;
    99
-   想变量的作用域仅限于函数内部，可以在定义时加上`local`命令，此时该变量就成了局部变量。例：
    ```纯文本
    #!/bin/bash

    #定义函数
    function func(){
        local a=99
    }

    #调用函数
    func

    #输出函数内部的变量
    echo $a
    ```
    输出结果为空，表明变量 a 在函数外部无效，是一个局部变量。

### Shell 全局变量

所谓全局变量，就是指变量在当前的整个 Shell 进程中都有效。每个 Shell 进程都有自己的作用域，彼此之间互不影响。在 Shell 中定义的变量，默认就是全局变量。

也就是说除了用[\[Linux\]source](\[Linux]source_pFBn7mw1cpdTX2aJvKkcMz.md "\[Linux]source")所执行的脚本实在本Shell进程中执行，进程号不变。其他Shell脚本运行都会以新进程执行。相同的变量不会干扰。<[运行 Shell 脚本的方法](<运行 Shell 脚本的方法_kroR8bMe5ZWEwUnypkCYt6.md> "运行 Shell 脚本的方法")>

#### Shell 环境变量

全局变量只在当前 Shell 进程中有效，对其它 Shell 进程和子进程都无效。如果使用[\[Linux\]export](\[Linux]export_qrhz1KzP2GsvgMbQ9fbYs4.md "\[Linux]export")命令将全局变量导出，那么它就在所有的子进程中也有效了，这称为“环境变量”。

环境变量被创建时所处的 Shell 进程称为父进程，如果在父进程中再创建一个新的进程来执行 Shell 命令，那么这个新的进程被称作 Shell 子进程。当 Shell 子进程产生时，它会继承父进程的环境变量为自己所用，所以说环境变量可从父进程传给子进程。不难理解，环境变量还可以传递给孙进程。

注意，两个没有父子关系的 Shell 进程是不能传递环境变量的，并且环境变量只能向下传递而不能向上传递，即“传子不传父”。

示例1中可以发现，默认情况下，a 在 Shell 子进程中是无效的；使用 [\[Linux\]export](\[Linux]export_qrhz1KzP2GsvgMbQ9fbYs4.md "\[Linux]export")将 a 导出为环境变量后，在子进程中就可以使用了。

环境变量也是临时的，如果需要持久的，无父子关系的变量，需要在shell配置文件中配置。(Shell配置文件（配置脚本）的加载)

#### 示例

-   示例1：Shell 环境变量
    ```纯文本
    [c.biancheng.net]$ a=22       #定义一个全局变量
    [c.biancheng.net]$ echo $a    #在当前Shell中输出a，成功
    22
    [c.biancheng.net]$ bash       #进入Shell子进程
    [c.biancheng.net]$ echo $a    #在子进程中输出a，失败

    [c.biancheng.net]$ exit       #退出Shell子进程，返回上一级Shell
    exit
    [c.biancheng.net]$ export a   #将a导出为环境变量
    [c.biancheng.net]$ bash       #重新进入Shell子进程
    [c.biancheng.net]$ echo $a    #在子进程中再次输出a，成功
    22
    [c.biancheng.net]$ exit       #退出Shell子进程
    exit
    [c.biancheng.net]$ exit       #退出父进程，结束整个Shell会话
    ```

