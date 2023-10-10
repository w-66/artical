# \[H3C]报文捕获/抓包

目前支持两种报文捕获类型：本地报文捕获和远程报文捕获。

#### 1. 本地报文捕获(`packet-capture loca`)

本地报文捕获功能可以将捕获的报文自动上传到FTP服务器、存储在设备存储介质中或者在登录设备的终端上显示报文信息，用户可以选择其中一种类型来进行报文捕获。

示例：

```纯文本
<H3C-msr2600> packet-capture local interface GigabitEthernet 0/1 autostop filesize  100 write flash:/g0-1.cap
```

#### 2. 远程报文捕获

远程报文捕获是指设备开启远程报文捕获服务功能后，用户必须通过PC上的第三方报文捕获软件Wireshark客户端与捕获报文的设备建立连接，远端报文捕获设备将报文数据发送给Wireshark，供Wireshark显示。



