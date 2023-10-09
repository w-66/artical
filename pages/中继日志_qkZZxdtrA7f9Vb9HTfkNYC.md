# 中继日志

## 概述

在[MySQL主从复制](MySQL主从复制_ppdss6EqC8ycGWwYxt9xRa.md "MySQL主从复制")时，主服务器进行增删改时，会将修改了数据通过[二进制日志|binlog](二进制日志-binlog_ejCUGaodeJVCeLkhRYzCyE.md "二进制日志|binlog")发送到从服务器，存储在中继日志中，从服务器通过中继日志来进行与主服务器的同步

-   其他

    ![](../image/image_vhra0Xvg0K.png)

## 开启中继日志

`relay-log`：中继日志开关; 值为日志名称

## relay log文件

命名规则

1.  `从服务器名-relay-bin.序号`：relay log数据文件
2.  `从服务器名-relay-bin.index`：relay log 的索引

-   `从服务器名-relay-bin.序号`
-   `从服务器名-relay-bin.index`

