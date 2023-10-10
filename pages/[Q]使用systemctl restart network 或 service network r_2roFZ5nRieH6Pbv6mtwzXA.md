# \[Q]使用systemctl restart network 或 service network restart 命令重启网卡失败。Failed to restart network.service: Unit network.service not found.

原因其实也很简单，命令用错了，造成了找不到相应的网卡服务。

**解决：**

1、可以尝试使用以下命令：

`service network-manager restart`

2、如果是 Kali Linux（Debian），则需要用以下命令：

`service networking restart`

3、如果是Centos 8，使用：重载网络配置：`nmcli c reload`

