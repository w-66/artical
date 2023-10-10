# \[win-bat]start

`/B`

`/B`后台启动; 启动应用程序，但不创建新窗口。

```纯文本
启动一个单独的窗口以运行指定的程序或命令。

START ["title"] [/D path] [/I] [/MIN] [/MAX] [/SEPARATE | /SHARED]
      [/LOW | /NORMAL | /HIGH | /REALTIME | /ABOVENORMAL | /BELOWNORMAL]
      [/NODE <NUMA node>] [/AFFINITY <hex affinity mask>] [/WAIT] [/B]
      [command/program] [parameters]

    "title"     在窗口标题栏中显示的标题。
    path        启动目录。
    /B          后台启动; 启动应用程序，但不创建新窗口。
                应用程序已忽略 ^C 处理。除非应用程序
                启用 ^C 处理，否则 ^Break 是唯一可以中断
                该应用程序的方式。
    I           新的环境将是传递
                给 cmd.exe 的原始环境，而不是当前环境。
    MIN         以最小化方式启动窗口。
    MAX         以最大化方式启动窗口。
    SEPARATE    在单独的内存空间中启动 16 位 Windows 程序。
    SHARED      在共享内存空间中启动 16 位 Windows 程序。
    LOW         在 IDLE 优先级类中启动应用程序。
    NORMAL      在 NORMAL 优先级类中启动应用程序。
    HIGH        在 HIGH 优先级类中启动应用程序。
    REALTIME    在 REALTIME 优先级类中启动应用程序。
    ABOVENORMAL 在 ABOVENORMAL 优先级类中启动应用程序。
    BELOWNORMAL 在 BELOWNORMAL 优先级类中启动应用程序。
    NODE        将首选非一致性内存结构(NUMA)节点指定为
                十进制整数。
    AFFINITY    将处理器关联掩码指定为十六进制数字。
```





# 示例

-   示例：同时执行两个程序
    ```纯文本
    start frpc.exe -c frpc.ini
    start mstsc.exe

    ```



```纯文本
start http://www.baidu.com
```

用NOTEPAD（记事本）打开 桌面上的1.txt。

```纯文本
start "" "%windir%\system32\NOTEPAD.EXE" "%userprofile%\桌面\1.txt"
```

这里start后面要加""才能启动文件abc.doc，否则不能启动。

```纯文本
start "" "%userprofile%\桌面\abc.doc"
```

如果start 后没有 " " 则表示把title省略了，此时文件名若有""的话start就会把它看作是标题，从而变成了省略文件名，就默认开启cmd了。所以在start后加上""就能防止这种意外的情况。

用记事本最小化打开桌面的abc.txt。

```纯文本
start /min "" "%windir%\system32\NOTEPAD.EXE" "%userprofile%\桌面\abc.txt"
```
