# \[En]Linux

-   Please select the geographic area in which you live. Subsequent configuration questions will narrow this down by presenting a list of cities, representing the time zones in which they are located.
    ```纯文本
    Please select the geographic area in which you live. Subsequent configuration questions will narrow this down by presenting a list of cities, representing the time zones in which they are located.

      1. Africa  2. America  3. Antarctica  4. Australia  5. Arctic  6. Asia  7. Atlantic  8. Europe  9. Indian  10. Pacific  11. SystemV  12. US  13. Etc
    ```
-   upgrade kernel and roofs by install package

    通过安装软件包升级内核和屋顶
-   the local ip format input is error

    本地ip格式输出错误
-   Linux安装firefox提示

    ![](https://picture-bed1.oss-cn-beijing.aliyuncs.com/markdown-picture-bed/Linux安装firefox提示.png)
-   \[user\@locathost network-scripts]\$ systemctl restart network &#x20;

    job for network service failed because the control process exited with error code. See "systemctl status networkservice" and "ournalctl-xe" for details

    ![](../image/image_I300O00MWP.png)
-   执行yum list sshd的提示
    -   \[root\@VM-16-5-centos \~]# yum list sshd
        Loaded plugins: fastestmirror, langpacks
        Loading mirror speeds from cached hostfile
        Error: No matching Packages to list
        \[根 @ VM-16-5-centos \~]# yum list sshd
        加载的插件: fastestmirror，langpacks
        从缓存的主机文件加载镜像速度
        错误: 没有要列出的匹配包


-   SSH的配置文件**Kylin**  cat /etc/ssh/sshd\_config

    \~Package generated configuration file

    \~See the sshd\_config(5) [manpage](manpage_4vB16BfHM15pvrwrwDw6Sw.md "manpage") for details

    \~What ports, IPs and protocols we listen for

    `Port 23456`

    \~Use these options to [restrict](restrict_hrnSwpqVYXET9J7zLVw87d.md "restrict") which interfaces/protocols sshd will [bind](bind_5qjNDDa4SFb4d7juPfYcFy.md "bind") to

    \~ListenAddress ::

    \~ListenAddress 0.0.0.0   //ListenAdderss 0.0.0.0

    `Protocol 2`   //使用SSH V2协议

    \~HostKeys for protocol version 2

    HostKey /etc/ssh/ssh\_host\_rsa\_key

    HostKey /etc/ssh/ssh\_host\_dsa\_key

    HostKey /etc/ssh/ssh\_host\_ecdsa\_key

    HostKey /etc/ssh/ssh\_host\_ed25519\_key

    \~[privilege](privilege_sKvLTXfPXzL3b9wCuoSSWa.md "privilege") [separation](separation_dCYSNhjFakpoPfhWYbCbqe.md "separation") is turned on for security

    UsePrivilegeSeparation yes

    \~ Lifetime and size of [ephemeral](ephemeral_3QdQG53H2WJGqyr9vfq9Eo.md "ephemeral") version 1 server key

    KeyRegenerationInterval 3600

    ServerKeyBits 1024

    \~ Logging

    SyslogFacility AUTH

    LogLevel INFO

    \~ Authentication:

    Login[grace](grace_xwjuhRD3mTvNPSNt96QUuH.md "grace")Time 120   //登录宽限期

    PermitRootLogin yes   //允许root用户登录

    [strict](strict_h7otAsu4Wp9MKX8Ad6Q1UC.md "strict")Modes yes

    严格模式

    RSAAuthentication yes

    PubkeyAuthentication yes

    \~AuthorizedKeysFile  %h/.ssh/authorized\_keys   //公钥存储路径

    \~ Don't read the user's \~/.rhosts and \~/.shosts files

    IgnoreRhosts yes

    \~ For this to work you will also need host keys in /etc/ssh\_known\_hosts

    RhostsRSAAuthentication no

    \~ similar for protocol version 2

    HostbasedAuthentication no

    \~ Uncomment if you don't trust \~/.ssh/known\_hosts for RhostsRSAAuthentication

    \~IgnoreUserKnownHosts yes

    \~ To enable empty passwords, change to yes (NOT RECOMMENDED)

    PermitEmptyPasswords no   //禁止空密码登录

    \~ Change to yes to enable challenge-response passwords (beware issues with

    \~ some PAM modules and threads)

    ChallengeResponseAuthentication no

    \~ Change to no to disable tunnelled clear text passwords

    \~PasswordAuthentication yes

    \~ Kerberos options

    \~KerberosAuthentication no

    \~KerberosGetAFSToken no

    \~KerberosOrLocalPasswd yes

    \~KerberosTicketCleanup yes

    \~ GSSAPI options

    \~GSSAPIAuthentication no

    \~GSSAPICleanupCredentials yes

    X11Forwarding yes

    X11DisplayOffset 10

    PrintMotd no

    PrintLastLog yes

    TCPKeepAlive yes

    \~UseLogin no

    \~MaxStartups 10:30:60

    \~Banner /etc/issue.net

    \~ Allow client to pass locale environment variables

    AcceptEnv LANG LC\_\*

    Subsystem sftp /usr/lib/openssh/sftp-server

    \~ Set this to 'yes' to enable PAM authentication, account processing,

    \~ and session processing. If this is enabled, PAM authentication will

    \~ be allowed through the ChallengeResponseAuthentication and

    \~ PasswordAuthentication.  Depending on your PAM configuration,

    \~ PAM authentication via ChallengeResponseAuthentication may bypass

    \~ the setting of "PermitRootLogin without-password".

    \~ If you just want the PAM account and session checks to run without

    \~ PAM authentication, then enable this but set PasswordAuthentication

    \~ and ChallengeResponseAuthentication to 'no'.

    UsePAM yes
-   GRUB 界面下方提示：use the ↑ and  ↓ keys to select [which](which_2Z8rHRsSCfSMVCCXNHhHpc.md "which") entry ishighlighted. [press](press_7eSu3brcvoHAYfoY1Wgx26.md "press") enter to boot the selected OS， `e` to edit the commands [before](before_8FSULDe8iXkkYBHCNiYUnp.md "before") booting， `a` to [modify](modify_sExr8U5Zttvq7GuXvdoGHw.md "modify") the kernel arguments before booting ，or `c` for a command-line.&#x20;

    ![](../image/image_17KTNynZLM.png)

***

[\[En\]kali](\[En]kali_kNthaQAPjpzR9p84JMck5L.md "\[En]kali")





# man/help文档

[\[En\]man sources.list](<\[En]man sources.list_3yzpCyntwrNKUJYJ93mp3p.md> "\[En]man sources.list")

[\[En\]apt](\[En]apt_nG29cfTcMmpGoiuDCZoNdA.md "\[En]apt")

[man unzip](<man unzip_9mB6hT38rw5V2wcwkfxwFs.md> "man unzip")

[man grep](<man grep_cTZcZdWeuC8Ba7r6oAsZZR.md> "man grep")



[\[En\]man rm](<\[En]man rm_SVLLDNaQVGygwn66JgZwk.md> "\[En]man rm")
