# \[Q]Linux

-   \[Q]写一个 bash 脚本以统计一个文本文件 `words.txt` 中每个单词出现的频率。

    [https://www.wolai.com/q-66/aLUvZBsx7gBk991hpKuMNe](https://www.wolai.com/q-66/aLUvZBsx7gBk991hpKuMNe "https://www.wolai.com/q-66/aLUvZBsx7gBk991hpKuMNe")
    ```纯文本
    cat words.txt | tr -s ' ' '\n' | sort | uniq -c | sort -r | awk '{ print $2, $1 }'

    ```
-   \[Q]两台服务器怎么传输文件? > [\[Linux\]scp](\[Linux]scp_eXWWRhDG6NpchTJPYNg7My.md "\[Linux]scp")|[\[Linux\]SSH](\[Linux]SSH_tWaZxVzRSuRNUygc9QuK8j.md "\[Linux]SSH")
    -   示例：导出Docker镜像文件并发送到对方根目录下
        ```sql
        docker save 09b84bf0192e  | ssh root@45.135.135.139 'cat - > /docker-ttrss.tar'
        ```
-   \[Q]WARNING: apt does not have a stable CLI interface. Use with caution in scripts.

    [\[Linux\]apt](\[Linux]apt_e1MS7RWUoFMHZ4WMqMgw9C.md "\[Linux]apt")在脚本中使用会有此提示，因为它的输出并非总能被其它命令行工具解析，比如它会有个进度条，而这个进度条会影响其它命令行工具解析它的输出
-   \[Q]Linux 如何快速删除大文件或大量文件?
    -   示例：删除大量文件：利用rsync对需要删除的文件夹同步一个空文件夹 \[[\[Linux\]rsync](\[Linux]rsync_hQ1ryBuZt21t9LRhB2X4SM.md "\[Linux]rsync")`--delete-before``-d`]

        1）首先建立一个空白文件夹。
        ```bash
        mkdir /tmp/empty

        ```
        2）之后使用以下语句即可快速的删除文件。
        ```javascript
        rsync --delete-before -d /tmp/empty/ /the/folder/you/want/delete/
        ```
        > 注意文件夹后的 `/`
-   Linux中如何查询文本内容&#x20;
    1.  示例：一个文件时，查询文件中的8080字符，直接`grep -n '8080' 文件1 文件2`
    2.  示例：多个文件时，`ls | xargs grep -n`&#x20;

        示例：在c1.yaml与c2.yaml文件中查找you关键字 \[[\[Linux\]xargs](\[Linux]xargs_42Lcsh2tndwoUsJ8TNf84C.md "\[Linux]xargs")[\[Linux\]grep](\[Linux]grep_s1VmEZHkPA58qZQ5Q1mqqh.md "\[Linux]grep")[\[Linux\]管道 '|'](<\[Linux]管道 '-'_e24YHSbxN4tUe62DpRo8Tq.md> "\[Linux]管道 '|'")]
        ```sql
        ls | xargs  grep -n 'you' c1.yaml c2.yaml
        ```
-   \[Q]`WARNING: apt does not have a stable CLI interface. Use with caution in scripts.`<[参考](https://github.com/woodongwong/notes/issues/9 "参考")>

    如果在脚本中使用apt命令，有可能会得到"`WARNING: apt does not have a stable CLI interface. Use with caution in scripts.`" 提示。请使用apt-get、apt-cache等命令进行替换。apt命令不适合在脚本中运行，因为apt命令是为用户（人）而设计的，它会有颜色的显示、进度条显示等一些友好的交互界面。而在脚本中，对于这些“特性”是不稳定（不支持或者是输出错乱等）的
-   \[Q]qusay is not in the sudoers file.  This incident will be reported.  \[[/etc/sudoers](-etc-sudoers_rvwofo5Jd4yyD8odBwWEev.md "/etc/sudoers")]

    qusay 不在 sudoers 文档中。此事件将被报告。
    ```纯文本
    [qusay@localhost ~]$ sudo vi /etc/sysconfig/network-scripts/ifcfg-ens33
    [sudo] password for qusay: 
    qusay is not in the sudoers file.  This incident will be reported.
    ```
    原因：qusay用户不在sudoers的权限内，无法调用root权限

    解决方案：加上权限

    `qusay ALL = (ALL) ALL`
-   \[Q]重定向nmcli的手册到txt文本出错

    `man nmcli > man_cntest.txt`
    ```纯文本
    [root@VM-16-5-centos ~]# man nmcli > man_cntest.txt  
    <standard input>:1368: warning [p 11, 4.3i, div `3tbd2,2', 0.3i]: can't break line
    ```


    解决方法：`MANWIDTH=160 man nmcli>man_nmcli.txt `

    原因：<[参考](https://www.coder.work/article/6225463 "参考"),[参考](https://stackoverflow.com/questions/34621046/why-is-this-cant-break-line-warning-from-grep-of-gcc-man-page "参考")>通常 `man`格式化内容以匹配终端的宽度。您将它的输出重定向到一个没有“屏幕宽度”的管道，因此它使用 80 个字符的默认宽度进行格式化。某些手册页的表格宽度超过 80 个字符，因此您会收到“无法换行”的警告。
-   Linux CenOS6 在VMware虚拟机中使用桥接模式 网络问题 \[[/etc/sysconfig/network-scripts](-etc-sysconfig-network-scripts_cRHvRjPPivW46N713d6Wng.md "/etc/sysconfig/network-scripts")]

    [参考](https://developer.aliyun.com/article/33285 "参考")

    [参考](https://blog.csdn.net/Wsxyi/article/details/113063222 "参考")
    -   问题描述

        重启网络服务提示 service network restart
        ```纯文本
        BRINGING UP INTERFACE ETH0 ：device eth0 dose not seem tobe present  搜索关键字
        ```
        ![](../image/image_XFBwsAYj-W.png)

        /etc/sysconfig/network-scripts路径中只有eth0的网卡配置文件

        ifconfig命令只有eth1的端口

    -   错误原因，是因为linux网卡绑定了原mac地址导致
    -   解决方案
        1.  修改eth0配置文件名为eth1，内容修改成eth1的实际参数(修改前注意备份文件)
            ```纯文本
            [root@localhost network-scripts]# cat ifcfg-eth1
             DEVICE=eth1 
            TYPE=Ethernet
            UUID=d99f87d3-9bc1-4661-b72e-91a2d7608a65
            ONBOOT=yes
            NM_CONTROLLED=yes
            BOOTPROTO=static
            DEFROUTE=yes
            IPV4_FAILURE_FATAL=yes
            IPV6INIT=no
            NAME="System eth0"
            #HWADDR=00:0C:29:20:DD:20
            PEERDNS=yes
            PEERROUTES=yes
             IPADDR=10.80.242.5
            NETMASK=255.255.255.0
            GATEWAY=10.80.242.1
            DNS1=114.114.114.114
            ```
        2.  在/etc/udev/rules.d删除或注释注释掉eth0的条目信息
            ```纯文本
            [root@localhost network-scripts]# cd /etc/udev/rules.d/
            [root@localhost rules.d]# ll
            总用量 20
            -rw-r--r--. 1 root root 316 10月 15 2014 60-raw.rules
            -rw-r--r--. 1 root root 789 6月  21 15:15 70-persistent-cd.rules
            -rw-r--r--  1 root root 420 6月  25 14:02 70-persistent-net.rules
            -rw-r--r--  1 root root 585 6月  25 13:47 70-persistent-net.rules.bk
            -rw-r--r--. 1 root root  54 12月  8 2011 99-fuse.rules
            [root@localhost rules.d]# cat 70-persistent-net.rules
            # This file was automatically generated by the /lib/udev/write_net_rules
            # program, run by the persistent-net-generator.rules rules file.
            #
            # You can modify it, as long as you keep each rule on a single
            # line, and change only the value of the NAME= key.

            # PCI device 0x8086:0x100f (e1000)
            SUBSYSTEM=="net", ACTION=="add", DRIVERS=="?*", ATTR{address}=="00:0c:29:20:dd:20", ATTR{type}=="1", KERNEL=="eth*", NAME="eth1"
            [root@localhost rules.d]# 
            ```
        3.  重启服务器
-   Linux下删除乱码或特殊字符文件

    Linux下删除乱码或特殊字符文件：由于编码原因，在linux[服务器](https://cloud.tencent.com/product/cvm?from=10680 "服务器")上上传、创建中文文件或目录时，会产生乱码，如果想删除它，用rm命令是删除不了的，这种情况下，用find命令可以删除乱码的文件或目录。

    ![](../image/image_3oV2tet1Yr.png)

    找到文件的[inode](inode_2sv8mpeDA8muCpeu27dgze.md "inode")，然后使用find删除

    ![](../image/image_O5nMZLxl8a.png)



    ![](../image/image_NuFdBhfWRR.png)

[\[对比\]网络工具netplan|ifupdown](\[对比]网络工具netplan-ifupdown_26MnQnektkpAsXW7Ls9F3.md "\[对比]网络工具netplan|ifupdown")

-   查询Linux系统版本

    [查询Linux发行版本|内核版本](查询Linux发行版本-内核版本_c2pHx5X2RqLbz8AZsc4yno.md "查询Linux发行版本|内核版本")

[\[Q\]使用systemctl restart network 或 service network restart 命令重启网卡失败。Failed to restart network.service: Unit network.service not found.](<\[Q]使用systemctl restart network 或 service network r_2roFZ5nRieH6Pbv6mtwzXA.md> "\[Q]使用systemctl restart network 或 service network restart 命令重启网卡失败。Failed to restart network.service: Unit network.service not found.")

[Linux怎么查看文件系统类型?](Linux怎么查看文件系统类型-_5e8mZsx5xu9rKaKNk5wch7.md "Linux怎么查看文件系统类型?")

[Linux中查看端口占用情况](Linux中查看端口占用情况_daxcFrp4LcyqvHdYc1jNxu.md "Linux中查看端口占用情况")

-   问题描述修改了网卡配置[/etc/sysconfig/network-scripts](-etc-sysconfig-network-scripts_cRHvRjPPivW46N713d6Wng.md "/etc/sysconfig/network-scripts")中的eth1，导致断网

    ![](../image/image_YegfFnJL3P.png)

    使用`service network restart`或者使用ifdown，ifup时重启网络服务，卡在了eth0

    提示：`determining ip information for eth0`

    编辑`ifcfg-eth0`，将`BOOTPROTO`从`dhcp`改成`static`

    重启网卡`ifdown eth0`、`ifup eth0`



[bash编程：sudo echo输入信息到/etc/apt/sources.list报错Permission denied](<bash编程：sudo echo输入信息到-etc-apt-sources.list报错Permis_22fdQejJ3VpQRZz64N7Ze5.md> "bash编程：sudo echo输入信息到/etc/apt/sources.list报错Permission denied")

-   \[Q]Linux怎么修改主机名

    [参考](<https://cloud.tencent.com/developer/article/1725903#:~:text=Linux修改主机名命令 1、如果只需要临时更改主机名，可以使用hostname命令。 sudo hostname \<new- hostname,\> # 例如： sudo hostname myDebian> "参考")
    -   **方式一：临时修改****`hostname <new-hostname>`**

        如果只需要临时更改主机名，可以使用hostname命令。
        ```纯文本
        sudo hostname <new-hostname>
        # 例如：
        sudo hostname myDebian
        ```
        这条命令不会更改[/etc/hostname](-etc-hostname_rguPC6eQs1FyuNp3JUk6sD.md "/etc/hostname")文件中的静态主机名（static hostname），它更改的只是临时主机名（transient hostname）。所以重启计算机后会回到旧的主机名。
    -   **方式二：永久修改主机名**

        使用vim手动修改[/etc/hostname](-etc-hostname_rguPC6eQs1FyuNp3JUk6sD.md "/etc/hostname")文件
        ```纯文本
        sudo vim /etc/hostname
        ```
        `hostnamectl set-hostname`
    > 扩展：查看当前的主机名[hostnamectl](hostnamectl_uhZsS5TZkkfDbbrqgZHLgZ.md "hostnamectl")

[Linux查看进程运行的完整路径方法](Linux查看进程运行的完整路径方法_hX7UeaepVJLToSK879bHxm.md "Linux查看进程运行的完整路径方法")

[Linux相关问题搜索记录](Linux相关问题搜索记录_87gGNaWTN96h6EP69nGGVd.md "Linux相关问题搜索记录")

[Linux重置密码](Linux重置密码_6cuTzadz2dJy7yT1d2rPcW.md "Linux重置密码")

[Linux系统解决权限设置成777仍然无权限访问的问题](Linux系统解决权限设置成777仍然无权限访问的问题_76pYSHnUPnsy9uJyPtxMCg.md "Linux系统解决权限设置成777仍然无权限访问的问题")

[Linux怎么升级软件](Linux怎么升级软件_9HAjrPGv4cngh2qVEYR2uE.md "Linux怎么升级软件")

[麒麟无法进入桌面在密码输入正确的情况下](麒麟无法进入桌面在密码输入正确的情况下_r8FxeToiyfJpHTRMkCfSUz.md "麒麟无法进入桌面在密码输入正确的情况下")

[Linux给文件追加多行内容](Linux给文件追加多行内容_osNMqRuNKqeF1RpgYHGEFe.md "Linux给文件追加多行内容")

-   2021-12-01 1.51麒麟服务器未知原因进入到了紧急模式

    ![](../image/image_8D10X5xnof.png)

    ![](../image/image_IrxPSQOA-J.png)

    ![](../image/image_5NIZsga-h_.png)

    You are in emergency mode.After logging in，type "[journalctl](journalctl_4rPHa5dNMaCKYT32TmHLkE.md "journalctl") -xb" to view system logs "systemctl reboot" to reboot ，"systemctl default " or "exit" to boot into default mode.

    参考文档：[华](https://support.huaweicloud.com/trouble-ecs/ecs_trouble_0310.html "华")[为弹性云服务器 ECS](https://support.huaweicloud.com/ecs/index.html "为弹性云服务器 ECS")
    1.  (emergency mode)查询失败日志

        ![](../image/image_9joSlUPHcN.png)
        -   失败条目1：`localhost.localdomain kernel ：acpi pnp0a03:00:_osc failed (ae_not_found)；disabling aspm`
        -   失败条目2：`seLinux policy load failed continuing` 。禁用[SELinux](SELinux_o2uDvqWRHVRXwPFGFbpoAa.md "SELinux")，之后Linux日志没有了此错误 。
        -   [\[Linux\]mount](\[Linux]mount_2VgJLKTwauc9gXn3QZnEgG.md "\[Linux]mount")` -a`提示`/data`未知的挂载类型 `default`：查看[/etc/fstab](-etc-fstab_mMfaW5ELNVQ8Nyj8nsBnyw.md "/etc/fstab")，找到`/data`那一行，先注释掉看看，重启就能正常进系统了。
            -   进入系统后，查看的失败日志

                ![](../image/image_1AGko2GRzK.png)
        -   \[英语翻译]
            -   if  you wish to  chec the consistency of  an XFS filesystem or repair a damaged filesystem,see xfs\_repair(8)

                如果您希望检查XFS文件系统的一致性或修复损坏的文件系统，请参阅XFS repair(8)

-   普通用户使用`sudo`，报错：\[sudo] password for jack: jack is not in the sudoers file.  This [incident](incident_9c19uTYVyryG2KkEh8owKT.md "incident") will be reported.

    解决方法就是在[/etc/sudoers](-etc-sudoers_rvwofo5Jd4yyD8odBwWEev.md "/etc/sudoers")文件里给该用户添加权限
-   xjkp\@xjkp-220E-M:\~\$ docker&#x20;
    Traceback (most recent call last):
    File "`/usr/lib/command-not-found`", line 27, in \<module>
    from CommandNotFound.util import crash\_guard
    ModuleNotFoundError: No module named 'CommandNotFound

    [参考文章](https://blog.csdn.net/weixin_42024384/article/details/107300262 "参考文章")[→考文章](https://discuss.python.org/t/modulenotfounderror-no-module-named-commandnotfound/3384 "→考文章")：文件`/usr/lib/command-not-found`主要问题可能是你安装了新版的python（python3.7）或者别的版本，然后在/usr/bin下将名为python3的软链接指向了新版本的python。因为Python版本不同，Python的模块有些许的不同,中的python与系统中安装的版本不一致导致的。

    before
    ```纯文本
    sudo vim /usr/lib/command-not-found 

    #!/usr/bin/ python3 
    ...
    ```
    after
    ```纯文本
    #!/usr/bin/ python3.5 
    ...
    ```
    未知名词：[crash](crash_sVn9QCVEqUCjKYTGRhpbwT.md "crash")\_[guard](guard_huX7Uc8r7oVtAKuKRef8ut.md "guard")

***

