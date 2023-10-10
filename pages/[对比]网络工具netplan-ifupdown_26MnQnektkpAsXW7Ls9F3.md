# \[对比]网络工具netplan|ifupdown

<https://www.modb.pro/db/218221>

从Ubuntu 18.04.2版本开始，系统的网络配置改成了新的 [\[Linux\]netplan](\[Linux]netplan_pxdMViQsgFYwWDLeiJ2JBw.md "\[Linux]netplan") 方式，弃用了之前使用的 [\[Linux\]ifupdown](\[Linux]ifupdown_bX2UndZ3mF6SNbEKNqdy63.md "\[Linux]ifupdown")方式。所以网络配置文件和配置方式和之前不同，本文主要介绍新的配置方式如何使用及与之前的区别。

镜像下载、域名解析、时间同步请点击 [阿里巴巴开源镜像站](https://developer.aliyun.com/mirror "阿里巴巴开源镜像站")

从Ubuntu 18.04.2版本开始，系统的网络配置改成了新的 [netplan.io](http://netplan.io "netplan.io") 方式，弃用了之前使用的 ifupdown 方式。所以网络配置文件和配置方式和之前不同，本文介绍新的配置方式如何使用及与之前的区别。

```text
注：ifupdown 就是用这个脚本 /etc/init.d/networking、systemctl start networking.service 启动网络服务的方式。
```

## 一、新旧版本对比

-   Ubuntu 18.04的DNS解析设置改成了 systemd-resolved，不是在原先的配置文件 /etc/resolv.conf 设置了。
-   Ubuntu 18.04默认情况下不再安装ifupdown，因此命令ifup和ifdown也不可用。可以使用ip命令来实现类似的功能，ip link set device up 和 ip link set device down。
-   之前Ubuntu16.04版本里的网卡配置文件 /etc/network/interfaces  不起作用了，改成了netplan方式。
-   如果新的 netplan 目前不能满足用户的网络使用需求，ifupdown 软件包仍然可以在Ubuntu 中使用和支持。 &#x20;

    ifupdown安装命令：apt install ifupdown  &#x20;

## 二、netplan 是什么？

netplan官网说它是一个在Linux系统中简单方便配置网络的程序，使用YAML格式的文件进行配置。YAML是什么？传送门 [YAML 入门教程 | 菜鸟教程](https://www.runoob.com/w3cnote/yaml-intro.html "YAML 入门教程 | 菜鸟教程") &#x20;

## 三、netplan 的工作方式

netplan 从配置文件 `/etc/netplan/*.yaml` 读取网络配置，启动后 netplan 在 `/run` 目录中生成特定网卡名称后缀的配置文件，然后将网卡设备的控制权移交给特定的网络守护程序。netplan 目前支持以下两种服务：**NetworkManagerSystemd-networkd**

![1.jpeg](https://img-blog.csdnimg.cn/img_convert/b1955e8f0cc3263e28c41f406d142743.png "1.jpeg")

ubuntu18.04系统里查看网卡用netplan配置的信息

```text
root@ubuntu18:~# networkctl status eth0● 2: eth0       Link File: /lib/systemd/network/99-default.link    Network File: /run/systemd/network/10-netplan-eth0.network            Type: ether           State: routable (configuring)            Path: pci-0000:00:05.0          Driver: virtio_net          Vendor: Red Hat, Inc.           Model: Virtio network device      HW Address: 00:16:3e:2c:b5:e7 (Xensource, Inc.)         Address: 172.17.161.4         Gateway: 172.17.175.253             DNS: 100.100.2.136                  100.100.2.138
```

## 四、如何使用 netplan

配置文件：`/etc/netplan/*.yaml`命令：`netplan apply`每个网卡都需要在 `/etc/netplan` 目录中设置配置文件，在配置中指定网卡ip信息，使用DHCP或者静态ip方式。`/etc/netplan/` 目录下的配置文件，扩展名为`.yaml`（例如 /etc/netplan/config.yaml），然后运行 `netplan apply` 此命令分析配置信息并将其应用生效。配置文件示例：

```text
#网卡eth0使用dhcp方式配置ip网络，配置如下。yaml配置是用空格作为缩进对齐，不能使用tab键。network:  version: 2  renderer: networkd  ethernets:    eth0:      dhcp4: yes      dhcp6: no#网卡eth0使用静态ip方式，用关键字addresses指定ip地址和子网掩码（支持ipv4和ivp6），gateway4指定网关ip，nameservers 指定DNS。network:  version: 2  renderer: networkd  ethernets:    eth0:      addresses:        - 10.10.10.2/24      gateway4: 10.10.10.1      nameservers:          search: [mydomain, otherdomain]          addresses: [10.10.10.1, 1.1.1.1]
```

配置文件里的关键字说明：**renderer：**指定后端网络服务，支持networkd（Systemd-networkd） 和 NetworkManager两种，默认是networkd。**ethernets：**指定是以太网配置，其他的还包括 wifis 或者 bridges**eth0：**以太网网卡名称**dhcp4：**开启使用ipv4的DHCP，默认是关闭。**dhcp6：**开启使用ipv6的DHCP，默认是关闭。**addresses：**对应网卡配置的静态ip地址，是ip/掩码的格式，支持ipv6地址，例如 addresses: \[192.168.14.2/24, "2001:1::1/64"]**gateway4, gateway6：**指定IPv4/6默认网关，使用静态ip配置时使用。例如IPv4: gateway4: 172.16.0.1 例如IPv6: gateway6: "2001:4::1"**nameservers：**设置DNS服务器和搜索域。有两个受支持的字段：addresses:是DNS地址列表，search:是搜索域列表,没有特殊需要可以不配置search这项。更多配置项可以参考netplan.io文档 [Netplan | Backend-agnostic network configuration in YAML](https://netplan.io/reference "Netplan | Backend-agnostic network configuration in YAML") &#x20;

### 参考资料：

[BionicBeaver/ReleaseNotes - Ubuntu Wiki](https://wiki.ubuntu.com/BionicBeaver/ReleaseNotes "BionicBeaver/ReleaseNotes - Ubuntu Wiki")[Netplan | Backend-agnostic network configuration in YAML](https://netplan.io/ "Netplan | Backend-agnostic network configuration in YAML")

本文转自：[Ubuntu 18.04 网络配置介绍-阿里云开发者社区](https://developer.aliyun.com/article/744737?spm=a2c6h.12873581.0.0.34342784WeLlsz\&groupCode=mirror "Ubuntu 18.04 网络配置介绍-阿里云开发者社区")
