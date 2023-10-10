# \[参考文章]OSPF邻居状态机停留原因解析

***

<https://blog.csdn.net/qq_40467699/article/details/108644219>

***

> 不细分网络类型来讲OSPF共有8种状态机，分别是： &#x20;
> Down、Attempt、Init、2-way、Exstart、Exchange、Loading、Full
> 下面分别是每个状态机的解释：
> Down：邻居会话的初始阶段，表明没有在邻居失效时间间隔内收到来自邻居路由器的Hello数据包。
> Attempt：该状态仅发生在OSPF NBMA（非广播多路访问）网络类型中，表明对端在邻居失效时间间隔（dead interval）超时前仍然没有回复Hello报文。此时路由器依然每发送轮询Hello报文的时间间隔（poll interval 默认120s）向对端发送Hello报文。
> Init：收到Hello报文后状态为Init（Hello报文邻居字段中不携带自己Router id）。
> 2-way：收到的Hello报文中邻居字段包含有自己的Router ID，则状态为2-way；如果不需要形成邻接关系则邻居状态机就停留在此状态，否则进入Exstart状态。
> Exstart：开始协商主从关系，并确定DD的序列号，此时状态为Exstart。
> Exchange：主从关系协商完毕后开始交换DD报文，此时状态为Exchange。
> Loading：DD报文交换完成即Exchange done，此时状态为Loading。
> Full：LSR重传列表为空，此时状态为Full。

***

## 为什么OSPF设计状态机？

> 由于OSPF建立邻居关系机制复杂，设计OSPF不同状态机的细分后，不同状态机建立邻居、邻接关系对应阶段也不同，不同状态下有不同现象。而在现网中如果OSPF出现故障，可以实现快速故障定位。

***本篇文章主要研究 OSPF邻居状态机停留情况及原因，下面案例可供参考，本次实验使用华为eNsp模拟器完成。***

\_\_\_

#### 一、Down状态与Attempt状态

Down状态为路由器未运行OSPF协议所处的状态，在此不多做赘述

![NBMA网络类型下的状态机](https://img-blog.csdnimg.cn/20200917153317884.png#pic_center "NBMA网络类型下的状态机")

如图所示拓扑，AR1与AR2之间运行OSPF协议，网络类型为**NBMA**，当AR2手工配置peer邻居AR1但AR1没有配置peerAR2时，AR2的OSPF状态机会变为Attempt状态。这表示AR2**已经开始周期性（30s）的发送hello报文，但是还没有收到对方发送的hello报文**。 &#x20;

![状态机](https://img-blog.csdnimg.cn/20200917154148347.png#pic_center "状态机")

![状态机](https://img-blog.csdnimg.cn/20200917154159271.png#pic_center "状态机")

而在等待一个 Dead Interval(120s) 的时间后仍旧没有收到任何hello报文后，设备会发送日志并由Attempt转为Down状态。 &#x20;

![状态机更改](https://img-blog.csdnimg.cn/2020091715460022.png#pic_center "状态机更改")

![邻居信息](https://img-blog.csdnimg.cn/20200917154618293.png#pic_center "邻居信息")

在OSPF NBMA网络类型中，Down状态不同于其他网络类型初始的Down状态，在NBMA网络中的Down状态中，会启用一个**Poll计时器（轮询发送hello报文的间隔）**，每120s发送一次发送hello报文。

#### 二、Init状态

当OSPF收到的Hello报文中邻居字段没有自己的router-id时，会停留在init状态

![广播网络类型](https://img-blog.csdnimg.cn/20200917155520315.png#pic_center "广播网络类型")

如图所示拓扑，AR1与AR2之间运行OSPF协议，网络类型为**广播**。此时在R2上配置ACL策略，在G0/0/0接口**入方向\*\*\*\*拒绝掉OSPF流量**。这样**AR2就无法收到AR1发送的hello报文**，但是**AR1可以收到AR2发送的hello报文**，此时状态机会停留在Init状态。

具体实现方式如下：

![ACL策略](https://img-blog.csdnimg.cn/20200917155936291.png#pic_center "ACL策略")

![查看定义的流量策略](https://img-blog.csdnimg.cn/20200917155956289.png#pic_center "查看定义的流量策略")

定义ACL策略，在AR2设备G0/0/0接口入方向调用，此时设备会发送日志信息，并将状态转为Init

![状态机更改](https://img-blog.csdnimg.cn/20200917160202623.png#pic_center "状态机更改")

![查看状态机](https://img-blog.csdnimg.cn/20200917160211397.png#pic_center "查看状态机")

注：在AR1上做ACL策略也可实现

#### 三、2-Way状态

当收到的Hello报文邻居字段携带自己的Router-id时，则会到达2-Way状态 &#x20;

（其他情况：当设备DR优先级都为0时，同为DR-Other设备时会停留在2-Way状态）

![广播网络类型](https://img-blog.csdnimg.cn/20200917162105441.png?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L3FxXzQwNDY3Njk5,size_16,color_FFFFFF,t_70#pic_center "广播网络类型")

如图所示拓扑，AR1与AR2之间运行OSPF协议，网络类型为**广播**。若**修改AR1与AR2设备接口DR优先级为0**，使其成为**DR-Other设备**，状态机则会停留在2-Way状态。

具体实现方式如下： &#x20;

![修改DR优先级](https://img-blog.csdnimg.cn/2020091716221152.png#pic_center "修改DR优先级")

![状态机更改](https://img-blog.csdnimg.cn/20200917162120786.png#pic_center "状态机更改")

![邻居信息](https://img-blog.csdnimg.cn/20200917162227752.png#pic_center "邻居信息")

#### 四、ExStart状态与ExChange状态

OSPF当开启MTU协商，两端MTU值不一致时会停留在ExStart或ExChange状态，但是又可以细分下列几种情况。 &#x20;

（注：华为设备默认不协商，报文中MTU字段填充为0） &#x20;

> MTU协商规则： &#x20;
> 对方DD报文中MTU字段的值<=接收报文接口的MTU值。 &#x20;
> ①如果协商不通过会导致邻接关系停留在Exstart状态或ExChange状态，无法建立FULL的邻接关系。 &#x20;
> ②如果不协商MTU值，可能会出现接口收到的OSPF报文比MTU大的情况。路由器会丢弃这个报文，导致数据库同步无法完成，邻居状态停留在Exchange或Loading中。

#### （1）从设备的MTU值小于主设备MTU时

![广播网络类型](https://img-blog.csdnimg.cn/20200917162721331.png#pic_center "广播网络类型")

如图所示拓扑，AR1与AR2之间运行OSPF协议，网络类型为**广播**。**AR2设备Router id为2.2.2.2**，**AR1设备Router id为1.1.1.1**，在进行主从选举时AR2会做为主设备。假设AR1、AR2**均开启了MTU协商**且**AR1接口MTU值为1490**，**AR2设备接口MTU值为1500(默认值)**，配置完成后，设备会发送日志信息，状态机均会停留在**ExStart状态**。

具体实现方式如下：

![AR1配置](https://img-blog.csdnimg.cn/20200917164404930.jpg#pic_center "AR1配置")

![AR2配置](https://img-blog.csdnimg.cn/20200917164413289.jpg#pic_center "AR2配置")

上图为AR1与AR2设备接口具体配置，由于默认MTU为1500，AR2设备接口无需再配置MTU值。

![状态机更改](https://img-blog.csdnimg.cn/20200917162730305.png#pic_center "状态机更改")

![在这里插入图片描述](https://img-blog.csdnimg.cn/20200917162741308.png#pic_center "在这里插入图片描述")

#### （2）从设备的MTU大于主设备的MTU时 &#x20;

依旧以上图拓扑为例，AR1、AR2均开启了MTU协商。当**AR1接口MTU值为1490**，**AR2设备接口MTU值为1480时**，配置完成后，设备会发送日志信息，**从设备会停留在ExChange状态**，而**主设备则停留在ExStart状态**。

!状态机更改]\([https://img-blog.csdnimg.cn/20200917165442196.png#pic\_center](https://img-blog.csdnimg.cn/20200917165442196.png#pic_center "https://img-blog.csdnimg.cn/20200917165442196.png#pic_center"))

![AR1邻居信息](https://img-blog.csdnimg.cn/20200917165402293.png#pic_center "AR1邻居信息")

!\[AR2邻居信息

## 总结

以上就是今天要讲的内容，本文主要讲解为什么有OSPF状态机及OSPF状态机停留原因，如有不同观点可以在评论打出，共同讨论，共同学习。

\_\_\_

> 不细分网络类型来讲OSPF共有8种状态机，分别是： &#x20;
> Down、Attempt、Init、2-way、Exstart、Exchange、Loading、Full
>
> 下面分别是每个状态机的解释：
>
> Down：邻居会话的初始阶段，表明没有在邻居失效时间间隔内收到来自邻居路由器的Hello数据包。
>
> Attempt：该状态仅发生在OSPF NBMA（非广播多路访问）网络类型中，表明对端在邻居失效时间间隔（dead interval）超时前仍然没有回复Hello报文。此时路由器依然每发送轮询Hello报文的时间间隔（poll interval 默认120s）向对端发送Hello报文。
>
> Init：收到Hello报文后状态为Init（Hello报文邻居字段中不携带自己Router id）。
>
> 2-way：收到的Hello报文中邻居字段包含有自己的Router ID，则状态为2-way；如果不需要形成邻接关系则邻居状态机就停留在此状态，否则进入Exstart状态。
>
> Exstart：开始协商主从关系，并确定DD的序列号，此时状态为Exstart。
>
> Exchange：主从关系协商完毕后开始交换DD报文，此时状态为Exchange。
>
> Loading：DD报文交换完成即Exchange done，此时状态为Loading。
>
> Full：LSR重传列表为空，此时状态为Full。

\_\_\_

## 为什么OSPF设计状态机？

> 由于OSPF建立邻居关系机制复杂，设计OSPF不同状态机的细分后，不同状态机建立邻居、邻接关系对应阶段也不同，不同状态下有不同现象。而在现网中如果OSPF出现故障，可以实现快速故障定位。

***本篇文章主要研究 OSPF邻居状态机停留情况及原因，下面案例可供参考，本次实验使用华为eNsp模拟器完成。***

\_\_\_

#### 一、Down状态与Attempt状态

Down状态为路由器未运行OSPF协议所处的状态，在此不多做赘述

![NBMA网络类型下的状态机](https://img-blog.csdnimg.cn/20200917153317884.png#pic_center "NBMA网络类型下的状态机")

如图所示拓扑，AR1与AR2之间运行OSPF协议，网络类型为**NBMA**，当AR2手工配置peer邻居AR1但AR1没有配置peerAR2时，AR2的OSPF状态机会变为Attempt状态。这表示AR2**已经开始周期性（30s）的发送hello报文，但是还没有收到对方发送的hello报文**。 &#x20;

![状态机](https://img-blog.csdnimg.cn/20200917154148347.png#pic_center "状态机")

![状态机](https://img-blog.csdnimg.cn/20200917154159271.png#pic_center "状态机")

而在等待一个 Dead Interval(120s) 的时间后仍旧没有收到任何hello报文后，设备会发送日志并由Attempt转为Down状态。 &#x20;

![状态机更改](https://img-blog.csdnimg.cn/2020091715460022.png#pic_center "状态机更改")

![邻居信息](https://img-blog.csdnimg.cn/20200917154618293.png#pic_center "邻居信息")

在OSPF NBMA网络类型中，Down状态不同于其他网络类型初始的Down状态，在NBMA网络中的Down状态中，会启用一个**Poll计时器（轮询发送hello报文的间隔）**，每120s发送一次发送hello报文。

#### 二、Init状态

当OSPF收到的Hello报文中邻居字段没有自己的router-id时，会停留在init状态

![广播网络类型](https://img-blog.csdnimg.cn/20200917155520315.png#pic_center "广播网络类型")

如图所示拓扑，AR1与AR2之间运行OSPF协议，网络类型为**广播**。此时在R2上配置ACL策略，在G0/0/0接口**入方向\*\*\*\*拒绝掉OSPF流量**。这样**AR2就无法收到AR1发送的hello报文**，但是**AR1可以收到AR2发送的hello报文**，此时状态机会停留在Init状态。

具体实现方式如下：

![ACL策略](https://img-blog.csdnimg.cn/20200917155936291.png#pic_center "ACL策略")

![查看定义的流量策略](https://img-blog.csdnimg.cn/20200917155956289.png#pic_center "查看定义的流量策略")

定义ACL策略，在AR2设备G0/0/0接口入方向调用，此时设备会发送日志信息，并将状态转为Init

![状态机更改](https://img-blog.csdnimg.cn/20200917160202623.png#pic_center "状态机更改")

![查看状态机](https://img-blog.csdnimg.cn/20200917160211397.png#pic_center "查看状态机")

注：在AR1上做ACL策略也可实现

#### 三、2-Way状态

当收到的Hello报文邻居字段携带自己的Router-id时，则会到达2-Way状态 &#x20;

（其他情况：当设备DR优先级都为0时，同为DR-Other设备时会停留在2-Way状态）

![广播网络类型](https://img-blog.csdnimg.cn/20200917162105441.png?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L3FxXzQwNDY3Njk5,size_16,color_FFFFFF,t_70#pic_center "广播网络类型")

如图所示拓扑，AR1与AR2之间运行OSPF协议，网络类型为**广播**。若**修改AR1与AR2设备接口DR优先级为0**，使其成为**DR-Other设备**，状态机则会停留在2-Way状态。

具体实现方式如下： &#x20;

![修改DR优先级](https://img-blog.csdnimg.cn/2020091716221152.png#pic_center "修改DR优先级")

![状态机更改](https://img-blog.csdnimg.cn/20200917162120786.png#pic_center "状态机更改")

![邻居信息](https://img-blog.csdnimg.cn/20200917162227752.png#pic_center "邻居信息")

#### 四、ExStart状态与ExChange状态

OSPF当开启MTU协商，两端MTU值不一致时会停留在ExStart或ExChange状态，但是又可以细分下列几种情况。 &#x20;

（注：华为设备默认不协商，报文中MTU字段填充为0） &#x20;

> MTU协商规则： &#x20;
> 对方DD报文中MTU字段的值<=接收报文接口的MTU值。 &#x20;
> ①如果协商不通过会导致邻接关系停留在Exstart状态或ExChange状态，无法建立FULL的邻接关系。 &#x20;
> ②如果不协商MTU值，可能会出现接口收到的OSPF报文比MTU大的情况。路由器会丢弃这个报文，导致数据库同步无法完成，邻居状态停留在Exchange或Loading中。

#### （1）从设备的MTU值小于主设备MTU时

![广播网络类型](https://img-blog.csdnimg.cn/20200917162721331.png#pic_center "广播网络类型")

如图所示拓扑，AR1与AR2之间运行OSPF协议，网络类型为**广播**。**AR2设备Router id为2.2.2.2**，**AR1设备Router id为1.1.1.1**，在进行主从选举时AR2会做为主设备。假设AR1、AR2**均开启了MTU协商**且**AR1接口MTU值为1490**，**AR2设备接口MTU值为1500(默认值)**，配置完成后，设备会发送日志信息，状态机均会停留在**ExStart状态**。

具体实现方式如下：

![AR1配置](https://img-blog.csdnimg.cn/20200917164404930.jpg#pic_center "AR1配置")

![AR2配置](https://img-blog.csdnimg.cn/20200917164413289.jpg#pic_center "AR2配置")

上图为AR1与AR2设备接口具体配置，由于默认MTU为1500，AR2设备接口无需再配置MTU值。

![状态机更改](https://img-blog.csdnimg.cn/20200917162730305.png#pic_center "状态机更改")

![在这里插入图片描述](https://img-blog.csdnimg.cn/20200917162741308.png#pic_center "在这里插入图片描述")

#### （2）从设备的MTU大于主设备的MTU时 &#x20;

依旧以上图拓扑为例，AR1、AR2均开启了MTU协商。当**AR1接口MTU值为1490**，**AR2设备接口MTU值为1480时**，配置完成后，设备会发送日志信息，**从设备会停留在ExChange状态**，而**主设备则停留在ExStart状态**。

!状态机更改]\([https://img-blog.csdnimg.cn/20200917165442196.png#pic\_center](https://img-blog.csdnimg.cn/20200917165442196.png#pic_center "https://img-blog.csdnimg.cn/20200917165442196.png#pic_center"))

![AR1邻居信息](https://img-blog.csdnimg.cn/20200917165402293.png#pic_center "AR1邻居信息")

!\[AR2邻居信息

## 总结

以上就是今天要讲的内容，本文主要讲解为什么有OSPF状态机及OSPF状态机停留原因，如有不同观点可以在评论打出，共同讨论，共同学习。
