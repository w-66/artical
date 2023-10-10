# \[Q\&E]Linux

-   \[Q\&E]Rocky Linux 9等系统无法使用RSA密钥登录? \[[Rocky](Rocky_pA8ifA6zQQFr1xi2QJS9wR.md "Rocky"),[RedHat](RedHat_crCdH98G7vyTRhiAnHbNM6.md "RedHat")RHEL8,]


    -   [https://www.bestyii.com/topic/280](https://www.bestyii.com/topic/280 "https://www.bestyii.com/topic/280")

        CentOS Stream 9 Rocky Linux 9等操作系统，在某些ssh客户端或程序中不能正常链接。

        通过监控服务器`tail -f /var/log/secure`,得到一下错误提示
        ```text
        userauth_pubkey: key type ssh-rsa not in PubkeyAcceptedAlgorithms [preauth]
        ```
        问题原因

        CentOS Stream 9 / Rocky Linux 9系列系统在OS内部的crypto-policies策略默认为DEFAULT，在该策略模式下openssh-server禁用了ssh-rsa（rsa/SHA1）签名算法。

        由于FinalShell、nuoshell等部分SSH客户端软件默认仅支持使用ssh-rsa（rsa/SHA1）签名算法，不能兼容使用rsa-sha2-256（rsa/SHA256）或者rsa-sha2-512（rsa/SHA512），所以无法登录。

        您可以通过`update-crypto-policies --show`命令查看当前系统的策略。

        如果不想换成更安全的登录方式，则可以简单粗暴的打开ssh-rsa算法支持.

        运行以下命令，切换策略为LEGACY。
        ```text
        update-crypto-policies --set LEGACY
        update-crypto-policies --show
        ```
        ⚠️ 重要提示: LEGACY策略模式可能存在未知安全隐患，请您谨慎操作。
    -   my
        -   \[root\@VM-16-5-rockylinux \~]# tail -f /var/log/secure
            ```react&#x20;jsx

            Sep  3 20:40:11 localhost sudo[24641]: pam_unix(sudo:session): session closed for user root
            Sep  3 20:40:15 localhost sshd[24639]:  userauth_pubkey: key type ssh-rsa not in PubkeyAcceptedAlgorithms [preauth] 
            Sep  3 20:40:17 localhost sshd[24639]: error: Received disconnect from 222.247.150.10 port 28228:13: The user canceled authentication.  [preauth]
            Sep  3 20:40:17 localhost sshd[24639]: Disconnected from authenticating user root 222.247.150.10 port 28228 [preauth]
            Sep  3 20:42:57 localhost sshd[24644]: Received signal 15; terminating.
            Sep  3 20:42:57 localhost sshd[25306]: Server listening on 0.0.0.0 port 19980.
            Sep  3 20:42:57 localhost sshd[25306]: Server listening on :: port 19980.
            Sep  3 20:43:06 localhost sshd[25353]: Accepted publickey for root from 222.247.150.10 port 24634 ssh2: RSA SHA256:qqgrdr+d/o0kkfPC8aps5bXQ/sOkPkqL36mJUNUWFUc
            Sep  3 20:43:06 localhost sshd[25353]: pam_unix(sshd:session): session opened for user root(uid=0) by (uid=0)
            Sep  3 20:43:06 localhost sshd[25353]: pam_lastlog(sshd:session): corruption detected in /var/log/btmp
            ```
    -   官方文档：
        -   [https://www.redhat.com/en/blog/how-customize-crypto-policies-rhel-82](https://www.redhat.com/en/blog/how-customize-crypto-policies-rhel-82 "https://www.redhat.com/en/blog/how-customize-crypto-policies-rhel-82")
        -   [https://access.redhat.com/articles/3642912](https://access.redhat.com/articles/3642912 "https://access.redhat.com/articles/3642912")

