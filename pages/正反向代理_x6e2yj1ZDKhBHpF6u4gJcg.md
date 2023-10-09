# 正反向代理



## 正向[代理](代理_d58n13YGAFW8nnjQ1fK5xG.md "代理")

正向[代理](代理_d58n13YGAFW8nnjQ1fK5xG.md "代理")通过代理服务器，来访问代理服务器网络上的资源，需要客户端，常见应用场景：[VPN](VPN_6KZv2B653cfUweYLiGvkNA.md "VPN")

例子：用国外的VPS搭建一个VPN服务器，我用手机下载SSR，来建立VPN访问外网。

![](../image/image_AyCJvzStJ6.png)

## 反向[代理](代理_d58n13YGAFW8nnjQ1fK5xG.md "代理")

反向[代理](代理_d58n13YGAFW8nnjQ1fK5xG.md "代理")通过代理服务来访问目标服务，反向代理服务器位于用户与目标服务器之间，但是对于用户而言，反向代理服务器就相当于目标服务器，即用户直接访问反向代理服务器就可以获得目标服务器的资源。常见应用场景：[FRP](FRP_epv7VpqmHMPL4d2HbpCsok.md "FRP"),[Nginx](Nginx_vbXbeAuigD9K1FjudRK771.md "Nginx")([🖼️ 图片](../image/image_Z8LQTg8qzs.png "🖼️ 图片"))

例子：比如访问Google网站，谷歌在国内搭建了一个反向代理服务器，网址是123.com，我们就可以使用123.com来访问Google的网站。

-   负载均衡(e.g.[Nginx](Nginx_vbXbeAuigD9K1FjudRK771.md "Nginx"))



区别

正向代理，用户需要在客服端设置

反向代理，用户不需要设置



# 示例

-   示例1：概念解释反向[代理](代理_d58n13YGAFW8nnjQ1fK5xG.md "代理")

    [https://www.bilibili.com/video/BV1PQ4y167f1?p=1\&t=1471.8](https://www.bilibili.com/video/BV1PQ4y167f1?p=1\&t=1471.8 "https://www.bilibili.com/video/BV1PQ4y167f1?p=1\&t=1471.8")

&#x20;
