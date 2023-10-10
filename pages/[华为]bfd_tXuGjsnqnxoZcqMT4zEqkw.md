# \[华为]bfd

# 配置BFD单跳检测

![](../image/q17kgqc4_jC_PCi14tQ.bmp)

#### 操作步骤

1.  执行命令[**system-view**](http://127.0.0.1:7890/pages/31188611/11/31188611/11/resources/dc/system-view.html "system-view")，进入系统视图。
2.  执行命令[**bfd**](http://127.0.0.1:7890/pages/31188611/11/31188611/11/resources/dc/bfd.html "bfd")，使能全局BFD功能并进入BFD视图。

    缺省情况下，全局BFD功能处于未使能状态。
3.  （可选）执行命令[**default-ip-address**](http://127.0.0.1:7890/pages/31188611/11/31188611/11/resources/dc/default-ip-address.html "default-ip-address") *ip-address*，配置BFD缺省组播IP地址。

    缺省情况下，BFD使用组播IP地址224.0.0.184。

    如果BFD检测路径上存在重叠的BFD会话，例如，三层接口通过具有BFD功能的二层交换设备连接，不同BFD会话所在的设备必须配置不同的缺省组播IP地址，以避免BFD报文被错误地转发。
4.  执行命令[**quit**](http://127.0.0.1:7890/pages/31188611/11/31188611/11/resources/dc/quit_all_views.html "quit")，返回系统视图。
5.  根据BFD检测接口类型的不同，选择执行如下步骤之一：
    -   对于有IP地址的三层接口：

        执行命令[**bfd**](http://127.0.0.1:7890/pages/31188611/11/31188611/11/resources/dc/bfd_bind_peer-ip.html "bfd") *session-name* **bind** **peer-ip** *ip-address* \[ **vpn-instance** *vpn-name* ] **interface** *interface-type* *interface-number* \[ **source-ip** *ip-address* ]，创建BFD会话的绑定信息。

        缺省情况下，未创建BFD会话。

        在第一次创建单跳BFD会话时，必须绑定对端IP地址和本端相应接口，且创建后不可修改。如果需要修改，则只能删除后重新创建。
    -   对于二层接口：

        执行命令[**bfd**](http://127.0.0.1:7890/pages/31188611/11/31188611/11/resources/dc/bfd_bind_peer-ip_default-ip.html "bfd") *session-name* **bind peer-ip default-ip** **interface** *interface-type interface-number* \[ **source-ip** *ip-address* ]，创建BFD会话的绑定信息。

        缺省情况下，未创建BFD会话。
6.  执行命令[**discriminator**](http://127.0.0.1:7890/pages/31188611/11/31188611/11/resources/dc/discriminator.html "discriminator") **local** *discr-value*，配置BFD会话的本地标识符。
7.  执行命令[**discriminator**](http://127.0.0.1:7890/pages/31188611/11/31188611/11/resources/dc/discriminator.html "discriminator") **remote** *discr-value*，配置BFD会话的远端标识符。
    > 配置标识符时，本端的本地标识符与对端的远端标识符必须相同，否则BFD会话无法正确建立。并且，本地标识符和远端标识符配置成功后不可修改。
    >
    > 对于使用缺省组播IP地址的BFD会话，本地标识符和远端标识符不能相同。
8.  执行命令commit，提交配置。

# 配置BFD多跳检测

配置BFD多跳检测，实现快速检测和监控网络中的多跳路径。

![](../image/smys5vlv_JHDhH_lIfJ.bmp)

#### 操作步骤

1.  执行命令[**system-view**](http://127.0.0.1:7890/pages/31188611/11/31188611/11/resources/dc/system-view.html "system-view")，进入系统视图。
2.  执行命令[**bfd**](http://127.0.0.1:7890/pages/31188611/11/31188611/11/resources/dc/bfd.html "bfd")，使能全局BFD功能并进入BFD视图。

    缺省情况下，全局BFD功能处于未使能状态。
3.  （可选）执行命令[**multi-hop**](http://127.0.0.1:7890/pages/31188611/11/31188611/11/resources/dc/multi-hop.html "multi-hop") **destination-port**\*\*{ 3784 | 4784 }\*\*，配置多跳BFD会话的目的端口号。

    缺省情况下，使用3784作为多跳BFD会话报文的目的端口号。
4.  执行命令[**quit**](http://127.0.0.1:7890/pages/31188611/11/31188611/11/resources/dc/quit_all_views.html "quit")，返回系统视图。
5.  执行命令[**bfd**](http://127.0.0.1:7890/pages/31188611/11/31188611/11/resources/dc/bfd_bind_peer-ip.html "bfd") *session-name* **bind** **peer-ip** *ip-address* \[ **vpn-instance** *vpn-name* ] \[ **source-ip** *ip-address* ]，创建BFD会话的绑定信息。

    缺省情况下，未创建BFD会话。
    -   注意
        -   在创建多跳BFD会话时，必须绑定对端IP地址。
        -   在创建BFD配置项时，系统只检查IP地址是否符合IP地址格式，不检查其正确性。绑定错误的对端IP地址或源IP地址都将导致BFD会话无法建立。
        -   在创建BFD会话时，**peer-ip**和**source-ip**不能为GRE Tunnel接口的IP地址。
        -   在创建BFD会话时，**peer-ip**的出接口不能为Tunnel接口。
        -   配置BFD多跳会话时，如果peer-ip地址与某LDP-LSP/静态-LSP的32位目的地址相同，则该BFD会话会联动该LSP。即：当BFD会话检测到故障时，会触发LSP进行保护切换。
6.  执行命令[**discriminator**](http://127.0.0.1:7890/pages/31188611/11/31188611/11/resources/dc/discriminator.html "discriminator") **local** *discr-value*，配置BFD会话的本地标识符。
7.  执行命令[**discriminator**](http://127.0.0.1:7890/pages/31188611/11/31188611/11/resources/dc/discriminator.html "discriminator") **remote** *discr-value*，配置BFD会话的远端标识符
8.  执行命令[**commit**](http://127.0.0.1:7890/pages/31188611/11/31188611/11/resources/dc/commit_bfd_session_view.html "commit")，提交配置。

# 配置静态标识符自协商BFD

如果对端设备采用动态BFD，而本端设备既要与之互通，又要能够实现BFD检测静态路由，必须配置静态标识符自协商BFD。该功能主要用于检测采用静态路由实现三层互通的网络中。

对于三层接口，正确配置接口IP地址。

![](../image/86n429hq_b0SpZ0QwQz.bmp)

#### 操作步骤

1.  执行命令[**system-view**](http://127.0.0.1:7890/pages/31188611/11/31188611/11/resources/dc/system-view.html "system-view")，进入系统视图。
2.  执行命令[**bfd**](http://127.0.0.1:7890/pages/31188611/11/31188611/11/resources/dc/bfd.html "bfd")，使能全局BFD功能并进入BFD视图。

    缺省情况下，全局BFD功能处于未使能状态。
3.  执行命令[**quit**](http://127.0.0.1:7890/pages/31188611/11/31188611/11/resources/dc/quit_all_views.html "quit")，返回系统视图。
4.  执行命令[**bfd**](http://127.0.0.1:7890/pages/31188611/11/31188611/11/resources/dc/bfd_bind_peer-ip_source-ip_auto.html "bfd") *session-name* **bind** **peer-ip** *ip-address* \[ **vpn-instance** *vpn-name* ] \[ **interface** *interface-type* *interface-number* ] **source-ip** *ip-address* **auto**，创建静态标识符自协商BFD会话。

    缺省情况下，未创建BFD会话。
    -   说明
        -   必须配置源IP地址。
        -   必须指定明确的对端IP地址，不能使用组播IP地址。
5.  执行命令commit，提交配置。

***

# display

display bfd session all



# 示例

-   示例1

    创建名称为atob的BFD会话，对从本端接口VLANIF100到对端IP地址为10.10.10.2的单跳链路进行检测。
    ```纯文本
    <HUAWEI> system-view
    [HUAWEI] bfd
    [HUAWEI-bfd] quit
    [HUAWEI] bfd atob bind peer-ip 10.10.10.2 interface vlanif 100

    ```
    创建名为atoc的BFD会话，检测到对端IP地址为10.10.20.2的多跳链路。
    ```纯文本
    <HUAWEI> system-view
    [HUAWEI] bfd
    [HUAWEI-bfd] quit
    [HUAWEI] bfd atoc bind peer-ip 10.10.20.2
    ```
-   配置单臂回声功能示例
    #### 组网需求
    如[图1](http://127.0.0.1:7890/pages/31188611/11/31188611/11/resources/dc/dc_cfg_bfd_0034.html#dc_cfg_bfd_0034__fig_dc_bfd_cfg_003401 "图1")所示，SwitchA和SwitchB通过直连链路连通，SwitchA支持BFD功能，SwitchB不支持BFD功能。用户希望实现对链路故障的快速检测。

    ![](../image/t2xg0jm9_6xaMZFta9t.bmp)

[示例：静态路由联动bfd单臂回声](示例：静态路由联动bfd单臂回声_pmGstthnEWjW7uDhxu45sr.md "示例：静态路由联动bfd单臂回声")





