# \[华为]SFTP Server

[SFTP](SFTP_5U9g9MfnuWoPrx2dzyrs2r.md "SFTP")协议

***

# \[HDX]V200R007\_AR通过SFTP进行文件操作示例

如[图1](http://localhost:7890/pages/AZI0519H/17/AZI0519H/17/resources/dc/dc_cfg_file_0021.html?ft=99\&fe=1\&id=dc_cfg_file_0021\&keyword=+\(sftp\)+\(infotype:"instruction"+OR+infotype:all\)\&noteId=#dc_cfg_file_0021__fig_dc_cfg_file_002101 "图1")所示，终端PC1与设备来连接，10.136.23.4是设备的管理网口IP地址。用户希望在终端与设备之间进行安全的文件传输操作。将设备配置为SSH服务器，提供SFTP服务，服务器通过对客户端的认证和双向的数据加密，实现用户对安全文件传输操作的要求。配置安全策略，保证只有PC1才能访问SSH服务器。

**图1** 配置通过SFTP进行文件操作组网图

![](http://localhost:7890/pages/AZI0519H/17/AZI0519H/17/resources/dc/images/fig_dc_cfg_file_002101ar.png)

#### 配置思路

采用如下的思路配置用户通过SFTP进行文件操作：

1.  在SSH服务器端生成本地密钥对及使能SFTP服务器功能，实现在服务器端和客户端进行安全地数据交互。
2.  配置SSH服务器端的VTY用户界面。
3.  配置SSH用户，包括认证方式以及用户名和密码等。
4.  配置SSH服务器的访问权限，实现对SSH用户的限制。
5.  从终端通过第三方软件OpenSSH实现访问SSH服务器。

#### 操作步骤

1.  在服务器端生成本地密钥对，并使能SFTP服务器功能。
    ```纯文本
    <Huawei> system-view
    [Huawei] sysname SSH Server
     [SSH Server] sftp server enable
    [SSH Server] rsa local-key-pair create 

    The key name will be: Host
    RSA keys defined for Host already exist.
    Confirm to replace them? (y/n)[n]:y
    The range of public key size is (512 ~ 2048).
    NOTES: If the key modulus is less than 2048,
           It will introduce potential security risks.
    Input the bits in the modulus[default = 2048]:2048
    Generating keys...
    ......................................................................................+++
    ....+++
    .......................................++++++++
    ..............++++++++
    ```
2.  在服务器端配置VTY用户界面。
    ```纯文本
    [SSH Server]  user-interface vty 0 14 
    [SSH Server-ui-vty0-14]  authentication-mode aaa 
    [SSH Server-ui-vty0-14]  protocol inbound ssh 
    [SSH Server-ui-vty0-14]  quit
    ```
3.  配置SSH用户，包括认证方式以及用户名和密码等。
    ```纯文本
    [SSH Server]  aaa 
    [SSH Server-aaa]  local-user client001 password irreversible-cipher Huawei@123 
    [SSH Server-aaa]  local-user client001 privilege level 15 
    [SSH Server-aaa]  local-user client001 service-type ssh 
    [SSH Server-aaa]  quit  [SSH Server]  ssh user client001 authentication-type password
    ```
4.  配置SSH服务器的访问权限。
    ```纯文本
    [SSH Server]  acl 2001 
    [SSH Server-acl-basic-2001]  rule permit source 10.136.23.10 32 
    [SSH Server-acl-basic-2001]  rule deny source 10.136.23.20 32 
    [SSH Server-acl-basic-2001]  quit 
    [SSH Server]  user-interface vty 0 14 
    [SSH Server-ui-vty0-14]  acl 2001 inbound 
    [SSH Server-ui-vty0-14]  quit
    ```
5.  从终端通过OpenSSH软件实现访问SFTP服务器。

    只有在用户终端安装了OpenSSH软件后，Windows命令行提示符才能识别OpenSSH相关命令。

# \[HDX]V200R007\_AR通过SFTP访问其他设备文件示例



