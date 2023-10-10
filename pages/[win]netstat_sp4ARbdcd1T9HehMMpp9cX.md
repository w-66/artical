# \[win]netstat

端口使用查询

<https://www.pianshen.com/article/6951451997/>

## 示例

1.  查看所有的端口占用情况命令

    `netstat -ano`
2.  查看指定端口的占用情况

    `netstat -aon|findstr "3692"`
3.  查看PID对应的进程命令

    `tasklist|findstr "3692"`
4.  结束该进程

    `taskkill /f /t /im nvcontainer.exe`

以端口号查询对应程序

```powershell
netstat -ano | find "8081"
  TCP    10.8.1.110:5801        101.32.245.47:8081     ESTABLISHED     12400
```

12400即PID (进程ID)

## 语法

```纯文本
netstat [-a] [-e] [-n] [-o] [-p Protocol] [-r] [-s] [Interval] 

```

-   `-a` 显示所有活动的 TCP 连接以及计算机侦听的 TCP 和 UDP 端口。&#x20;
-   `-n` 显示活动的 TCP 连接，不过，只以数字形式表现地址和端口号，却不尝试确定名称。&#x20;
-   `-o` 显示活动的 TCP 连接并包括每个连接的进程 ID (PID)?Windows 任务管理器中的“进程”选项卡上找到基于 PID 的应用程序。任务管理器中查看－－选择列－－PID选项选中，即可查看当前进程的PID，可根据此PID删掉占用端口的进程。该参数可以与 -a、-n 和 -p 结合使用。&#x20;
-   `-e` 显示以太网统计信息，如发送和接收的字节数、数据包数。该参数可以与 -s 结合使用。&#x20;
-   `-p `*`Protocol`* 显示 Protocol 所指定的协议的连接。在这种情况下，Protocol 可以是 tcp、udp、tcpv6 或 udpv6。如果该参数与 -s 一起使用按协议显示统计信息，则 Protocol 可以是 tcp、udp、icmp、ip、tcpv6、udpv6、icmpv6 或 ipv6。&#x20;
-   `-s` 按协议显示统计信息。默认情况下，显示 TCP、UDP、ICMP 和 IP 协议的统计信息。如果安装了 Windows XP 的 IPv6 协议，就会显示有关 IPv6 上的 TCP、IPv6 上的 UDP、ICMPv6 和 IPv6 协议的统计信息?梢允褂?-p 参数指定协议集。&#x20;
-   `-r` 显示 IP 路由表的内容。该参数与 route print 命令等价。&#x20;
-   `-Interval` 每隔 Interval 秒重新显示一次选定的信息。按 CTRL C 停止重新显示统计信息。如果省略该参数，netstat 将只打印一次选定的信息。
    > 与该命令一起使用的参数必须以连字符 (-) 而不是以短斜线 (/) 作为前缀。&#x20;

> 在用eclipse配合wtp开发jsp时，总是提示tomcat的8005、8080、8009端口被占用无法启动。一个非常好用的dos命令netstat。它可以有一些参数，如-a是显示所用所有连接和监听端口，-n是以数字显示地址和端口号，-o是显示每个连接的进程ID。在命令提示符中输入netstat -ano，列出所有的网络连接情况，发现占据这三个端口的进程ID是848。到任务管理器里去找，在“选择列”中列出PID，发现原来是javaw在占用这三个端口。结束进程后，tomcat便能正常启动了，jsp文件也能正常查看了。在命令提示符中输入netstat -help还能查看各个参数的功能。

## 在cmd下常用的形式为netstat -相关参数

-   LISTEN：侦听来自远方的TCP端口的连接请求&#x20;
-   SYN-SENT：再发送连接请求后等待匹配的连接请求&#x20;
-   SYN-RECEIVED：再收到和发送一个连接请求后等待对方对连接请求的确认&#x20;
-   ESTABLISHED：代表一个打开的连接&#x20;
-   FIN-WAIT-1：等待远程TCP连接中断请求，或先前的连接中断请求的确认&#x20;
-   FIN-WAIT-2：从远程TCP等待连接中断请求&#x20;
-   CLOSE-WAIT：等待从本地用户发来的连接中断请求&#x20;
-   CLOSING：等待远程TCP对连接中断的确认&#x20;
-   LAST-ACK：等待原来的发向远程TCP的连接中断请求的确认&#x20;
-   TIME-WAIT：等待足够的时间以确保远程TCP接收到连接中断请求的确认&#x20;
-   CLOSED：没有任何连接状
