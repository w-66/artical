# \[华为]CSS(堆叠)

# 介绍

#### 定义

集群交换系统CSS（Cluster Switch System），又称为堆叠，是指将多台支持堆叠特性的交换机设备组合在一起，从逻辑上组合成一台整体交换设备，如[图1](http://localhost:7890/pages/DCB1222B/03/DCB1222B/03/resources/dc/dc_fd_css_0002.html#dc_fd_css_0002__fig_dc_fd_css_000201 "图1")所示。

**图1** CSS示意图

![](http://localhost:7890/pages/DCB1222B/03/DCB1222B/03/resources/dc/images/fig_dc_fd_css_000201.png)

#### 目的

随着数据中心数据访问量的逐渐增大以及网络可靠性要求越来越高，单台交换机已经无法满足需求，而通过交换机的堆叠能够实现数据中心大数据量转发和网络高可靠性。

#### 受益

堆叠主要具有以下优点：

-   高可靠性。堆叠系统多台成员设备之间冗余备份；堆叠支持跨设备的链路聚合功能，实现跨设备的链路冗余备份。
-   强大的网络扩展能力。通过增加成员设备，可以轻松的扩展堆叠系统的端口数、带宽和处理能力。
-   简化配置和管理。堆叠形成后，多台物理设备虚拟成为一台设备，用户可以通过任何一台成员设备登录堆叠系统，对堆叠系统所有成员设备进行统一配置和管理。





# CSS(堆叠)命令

[https://support.huawei.com/hedex/hdx.do?docid=EDOC1100211201\&id=AZK09107\_04\_10030\&lang=zh](https://support.huawei.com/hedex/hdx.do?docid=EDOC1100211201\&id=AZK09107_04_10030\&lang=zh "https://support.huawei.com/hedex/hdx.do?docid=EDOC1100211201\&id=AZK09107_04_10030\&lang=zh")

[https://support.huawei.com/hedex/hdx.do?docid=EDOC1100211201\&id=ZH-CN\_TASK\_0177100936\&lang=zh](https://support.huawei.com/hedex/hdx.do?docid=EDOC1100211201\&id=ZH-CN_TASK_0177100936\&lang=zh "https://support.huawei.com/hedex/hdx.do?docid=EDOC1100211201\&id=ZH-CN_TASK_0177100936\&lang=zh")

`stack port enable`

`port member-group`

命令用来向堆叠端口中添加堆叠物理成员端口

#### display

`display stack configuration all`

`display stack topology`

# 示例

-   示例3：两个交换机堆叠

    ![物理连接图](../image/image_5AAUFZqGOF.png "物理连接图")

    配置日志

    [CRT\_session-NW\_楼层HJ1\_172.16.254.3-20220301.log](../file/CRT_session-NW_楼层HJ1_172.16.254.3-20220301_V76l9dO.log "CRT_session-NW_楼层HJ1_172.16.254.3-20220301.log")

    [CRT\_session-NW\_楼层HJ2\_172.16.254.4-20220301.log](../file/CRT_session-NW_楼层HJ2_172.16.254.4-20220301_vej-oSw.log "CRT_session-NW_楼层HJ2_172.16.254.4-20220301.log")
-   示例2(华为文档：配置堆叠示例)

    如[🖼️ 图片](http://127.0.0.1:7890/pages/DCB1222B/03/DCB1222B/03/resources/dc/images/fig_dc_cfg_istack_004101.png "🖼️ 图片")所示，SwitchA、SwitchB、SwitchC和SwitchD四台交换机组成环型堆叠系统。

    由于网络规模的扩大，接入层交换机提供的端口数已经不能满足服务器的接入要求，需要在保护现有投资的基础上扩展端口接入数量，并要求网络易管理、易维护。

    以S5700LI的业务口堆叠为例。
    -   **图1** 配置堆叠组网图

        ![](http://127.0.0.1:7890/pages/DCB1222B/03/DCB1222B/03/resources/dc/images/fig_dc_cfg_istack_004101.png)
    #### 配置思路
    采用如下的思路配置：
    1.  按照[图1](http://127.0.0.1:7890/pages/DCB1222B/03/DCB1222B/03/resources/dc/dc_cfg_istack_0041.html?ft=0\&fe=10\&hib=1.5.10.12.8.1\&id=dc_cfg_istack_0041#dc_cfg_istack_0041__fig_dc_cfg_istack_004101 "图1")所示，使用SFP+堆叠电缆连接各端口。
    2.  为了能够在堆叠的成员设备间转发数据报文，配置堆叠物理成员端口，并加入堆叠端口。注意同一条堆叠链路上的两个堆叠物理成员端口需加入不同堆叠端口。
    #### 操作步骤
    -   1、配置堆叠端口
        1.  配置SwitchA的业务口GigabitEthernet0/0/27～GigabitEthernet0/0/28为堆叠物理成员端口，并加入堆叠端口。`stack port enable`、`port member-group`
            ```纯文本
            <HUAWEI> system-view
            [HUAWEI] sysname SwitchA
            [SwitchA] stack port interface gigabitethernet 0/0/27 enable
            Warning: Enabling stack port may cause configuration loss on the interface, continue?[Y/N]:y
            [SwitchA] stack port interface gigabitethernet 0/0/28 enable
            Warning: Enabling stack port may cause configuration loss on the interface, continue?[Y/N]:y
            [SwitchA] interface stack-port 0/1
            [SwitchA-stack-port0/1] port member-group interface gigabitethernet 0/0/27
            [SwitchA-stack-port0/1] quit
            [SwitchA] interface stack-port 0/2
            [SwitchA-stack-port0/2] port member-group interface gigabitethernet 0/0/28
            [SwitchA-stack-port0/2] quit
            ```
        2.  配置SwitchB的业务口GigabitEthernet0/0/27～GigabitEthernet0/0/28为堆叠物理成员端口，并加入堆叠端口。
            ```纯文本
            <HUAWEI> system-view
            [HUAWEI] sysname SwitchB
            [SwitchB] stack port interface gigabitethernet 0/0/27 enable
            Warning: Enabling stack port may cause configuration loss on the interface, continue?[Y/N]:y
            [SwitchB] stack port interface gigabitethernet 0/0/28 enable
            Warning: Enabling stack port may cause configuration loss on the interface, continue?[Y/N]:y
            [SwitchB] interface stack-port 0/1
            [SwitchB-stack-port0/1] port member-group interface gigabitethernet 0/0/27
            [SwitchB-stack-port0/1] quit
            [SwitchB] interface stack-port 0/2
            [SwitchB-stack-port0/2] port member-group interface gigabitethernet 0/0/28
            [SwitchB-stack-port0/2] quit
            ```
        3.  配置SwitchC的业务口GigabitEthernet0/0/27～GigabitEthernet0/0/28为堆叠物理成员端口，并加入堆叠端口。
        4.  配置SwitchD的业务口GigabitEthernet0/0/27～GigabitEthernet0/0/28为堆叠物理成员端口，并加入堆叠端口。
    -   2、配置堆叠ID和堆叠优先级
        1.  配置SwitchA的堆叠优先级为200。
            ```纯文本
            [SwitchA] stack slot 0 priority 200
            Warning:Please do not frequently modify Priority, it will make the stack split! continue?[Y/N]:y 
            ```
        2.  配置SwitchB的堆叠ID为1。
            ```纯文本
            [SwitchB] stack slot 0 renumber 1
            Warning:Please do not frequently modify slotid, it will make the stack split! co
            ntinue?[Y/N]:y
            Info: Stack configuration has been changed, need reboot to take effect. 
            ```
        3.  配置SwitchC的堆叠ID为2。
        4.  配置SwitchD的堆叠ID为3。
    -   3、重新启动所有交换机
    -   4、验证配置结果
        ```纯文本
        <SwitchA> display stack
        Stack topology type : Ring
        Stack system MAC：0018-82d2-2e85
        MAC switch delay time: 10 min
        Stack reserve vlanid : 4093
        slot#     Role        Mac address      Priority   Device type
        -------------------------------------------------------------
            0     Master      0018-82d2-2e85   200        S5700-28P-LI-AC
            1     Slave       0018-82c6-1f44   100        S5700-28P-LI-AC
            2     Standby     0018-82c6-1f4c   100        S5700-28P-LI-AC
            3     Slave       0018-82b1-6eb8   100        S5700-28P-LI-AC
        ```
-   示例1[^1]
    -   示例1.0

        主设备
        ```纯文本
        ]stack
        -stack]stack member 1
        -stack]stack priority 200
        -stack]stack domain 100
        -stack]stack link-type lineborad-direct


        ```
    -   1、CSS命令

        ![](../image/image_GVFdSaesN8.png)

        ![](../image/image_2a-QYFdbp5.png)

        ![](../image/image_lDJKPbhnf_.png)
    -   2、`display stack configuration all`

        ![](../image/image_3Xx4yZfIaM.png)
    -   3、完成配置之后 使能堆叠(在配置完成之后)先重启主
        ```纯文本
        ]stack
        -stack]stack enable
        ```




[^1]: https\://www\.bilibili.com/video/av757700091?from=search\&seid=3310766606486256677\&spm\_id\_from=333.337.0.0
