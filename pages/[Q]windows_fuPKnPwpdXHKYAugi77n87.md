# \[Q]windows

-   怎么定时睡眠；关机

    定时关机 [\[win\]shutdown](\[win]shutdown_dDEM1GNW83Up4t3VaNpgQ1.md "\[win]shutdown")&#x20;

    定时睡眠 [\[win\]?powercfg](\[win]-powercfg_4qiY2eG9m38kiX4Uw7hcLA.md "\[win]?powercfg")
-   [RDP协议(远程桌面协议)](RDP协议\(远程桌面协议\)_7qd3wai8Zc11Lpyo9SPCLt.md "RDP协议(远程桌面协议)")相关问题
    -   在windows下查看某个运行程序（或进程）的命令行参数

        使用下面的命令：

        ```powershell
        wmic process get caption,commandline /value
        ```
        如果想查询某一个进程的命令行参数，使用下列方式：

        ```powershell
        wmic process where caption=” Boxsafe.exe ” get caption,commandline /value
        ```
        这样就可以得到进程的可执行文件位置等信息
    -   出现身份验证错误。 要求的函数不受支持, 远程计算机：192.168.0.101 这可能是由于CredSSP加密数据库修正。

        [https://blog.csdn.net/lbq15735104044/article/details/106121675/](https://blog.csdn.net/lbq15735104044/article/details/106121675/ "https://blog.csdn.net/lbq15735104044/article/details/106121675/")
    -   [这可能是由于 CredSSP 加密数据库修正](http://www.codingwhy.com/view/9093.html "这可能是由于 CredSSP 加密数据库修正")

        [http://www.codingwhy.com/view/9093.html](http://www.codingwhy.com/view/9093.html "http://www.codingwhy.com/view/9093.html")

        ![](../image/Snipaste_2021-09-08_23-26-52_MAMx88TSaP.png)
-   win10系统，文件管理器中部分图片不显示缩略图
    -   始终显示图标，从不显示缩略图的选项已经关闭的情况下
    ***
    -   操作：剪切无法显示缩略图的问题，到其他地方然后剪切回来，就会自动生成缩略图
    -   把电脑文件选项中的“始终显示图标，从不显示缩略图的选项”勾去掉，如果还是有部分不显示，可以试下，把图标剪切到别的盘，然后再复制回来，就会正常显示了
    -   清理系统缓存
    -   重启explorer.exe

-   windows定时任务：at和[schtasks](schtasks_kfkzwbqaCiJSTqhXh5V6Zu.md "schtasks")。schtasks被推荐用来替换at，并且at在win10操作系统中已经不再支持。要使用命令行创建计划任务，必须保证计划任务已经在运行。

[开机启动提示"error operating system"](<开机启动提示-error operating system-_jws7CuKaY3cHS2o4AKQDfE.md> "开机启动提示\"error operating system\"")

[windows蓝屏](windows蓝屏_u8Qfoe1befi5Tpf5yHGLYt.md "windows蓝屏")

[windows密码策略位置](windows密码策略位置_2rGNu2YRfmj7h9hStXgy7v.md "windows密码策略位置")

[pageguard.exe 系统错误](<pageguard.exe 系统错误_5uzVXSTPXsuzVsSu3jbJEa.md> "pageguard.exe 系统错误")

[windows日志事件类型的描述](windows日志事件类型的描述_8jngRhqie3cHVGat5tuZGM.md "windows日志事件类型的描述")

[\[Win\]设置环境变量](\[Win]设置环境变量_mjxoV2CbLMZrtaADcQLJWv.md "\[Win]设置环境变量")

[cmd和DOS的差别](cmd和DOS的差别_qd2nhhg51bEcfq5mYmtkPA.md "cmd和DOS的差别")

-   windows 怎么查看接口索引

    arp -a

    route PRINT -4&#x20;
-   \[IE]由于无法验证发行者,所以WINDOWS已阻止该软件

    [from](https://answers.microsoft.com/zh-hans/ie/forum/ie9-windows_7/由于无法验/a20a004b-b745-41e4-a3a9-6c76f65aaae1 "from")
    -   请在收到“无法验证发行者”提示后，点击“未知发布者”，然后你可以得到一个数字签名详细信息，点击查看证书，然后点击安装证书，下一步，选择将所有的证书放入下列存储，点击浏览，选择受信任的根证书颁发机构，点击确定。点击下一步，完成，是。导入成功后点击确定，确定。即可。
    -   **打开IE-工具-选项-安全-internet-自定义级别-下载未签名的ACTIVEX控件-设为启动。**

        待装上之后，再改回来就行！
