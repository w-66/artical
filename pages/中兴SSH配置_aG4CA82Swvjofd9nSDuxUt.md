# 中兴SSH配置

在 R7103 版本上进行配置和验证

***

![](../image/image_ukrAs5iAl_.png)

配置实现：

-   使用 RADIUS 服务器对登录 Device 的 SSH 用户进行认证和授权，登录用户名为 hello\@bbb，密码为 aabbcc；
-   Device 向 RADIUS 服务器发送的用户名带域名，服务器根据用户名携带的域名来区分提供给用户的服务。
-   用户通过认证后可执行系统所有功能和资源的相关 display 命令。
-   为了实现通过 RADIUS 来进行认证和授权，需要在 Device 上配置 RADIUS 方案并指定相应的主/从认证和授权服务器，并将其应用于 SSH 用户所属的 ISP 域。
-   为了在 Device 和主/从 RADIUS 服务器之间安全地传输用户密码，并且能在 Device 上验证主/从 RADIUS 服务器响应报文未被篡改，在 Device 和主/从 RADIUS 服务器上都要设置交互报文时所使用的共享密钥。

***

# SSH服务器配置

1.  生成DSA或RSA密钥
    ```纯文本
    public-key local create { dsa | rsa }

    ```
2.  使能SSH服务器功能
    ```纯文本
    ssh server enable

    ```
3.  配置SSH客户端登录时的用户界面
    ```纯文本
    user-interface vty number [ ending-number ]
     authentication-mode scheme
     # 缺省情况下，用户界面认证为password方式
     protocol inbound { all | ssh }
     # 缺省情况下，系统支持所有的协议，即支持Telnet、PAD和SSH
     
    ```
    > 如果在该用户界面上配置支持的协议是SSH，为确保配置成功，请务必配置登录用户界面的认证方式为authentication-mode scheme（采用AAA认证）。
4.  创建本地用户client001，并设置用户访问的命令级别为3。
    ```纯文本
    [Router] local-user client001
    [Router-luser-client001] password simple aabbcc
    [Router-luser-client001] service-type ssh
    [Router-luser-client001] authorization-attribute level 3
    [Router-luser-client001] quit
    ```
5.  &#x20;配置客户端的公钥
    > 本配置适用于采用publickey认证的SSH用户，采用password认证的SSH用户，不必进行本配置。    >
    -   注意

        SSH用户采用publickey认证方式时，需要在服务器端配置客户端的DSA或RSA主机公钥，并在客户端为该SSH用户指定与主机公钥对应的DSA或RSA主机私钥，以便当客户端登录服务器端时，对客户端进行验证。

        可以通过手工配置和从公钥文件中导入两种方式来配置客户端的公钥：

        l 手工配置客户端的公钥时，可以采用手工输入或拷贝粘贴的方式将客户端的公钥配置到服务器本地。这种方式要求手工输入或拷贝粘贴的主机公钥必须是未经转换的DER（Distinguished Encoding Rules，特异编码规则）公钥编码格式。

        l 从公钥文件中导入客户端的公钥时，系统会自动将客户端的公钥转换为PKCS（Public Key Cryptography Standards，公共密钥加密标准）编码形式，并实现客户端公钥的配置。这种方式需要客户端事先将公钥文件通过FTP/TFTP以二进制（binary）方式上传到服务器上。

        l 建议选用从公钥文件导入的方式配置客户端公钥。

        l SSH服务器上最多可以配置20个客户端的公钥。
6.  配置SSH用户并指定服务类型和认证方式

    通过本配置，可以在创建SSH用户的同时，指定SSH用户的服务类型和认证方式

    ![](https://picture-bed1.oss-cn-beijing.aliyuncs.com/markdown-picture-bed/配置SSH用户并指定服务类型和认证方式.png)
    -   注意

        对于AAA用户，即使没有创建对应的SSH用户，只要能够通过AAA认证，且设置的服务类型为SSH，则该用户仍然可以通过password认证方式，使用Stelnet或SFTP登录服务器。