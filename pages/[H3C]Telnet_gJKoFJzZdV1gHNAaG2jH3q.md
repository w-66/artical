# \[H3C]Telnet

1.  开启Telnet服务：`telnet server enable`
2.  配置 Telnet 用户登录的用户界面采用 scheme 方式：
    ```纯文本
    [Device] line vty 0 63 
    [Device-line-vty0-63] authentication-mode scheme 
    [Device-line-vty0-63] quit
    ```
3.  配置 HWTACACS 方案 hwtac
    ```纯文本
    [Device] hwtacacs scheme hwtac
    ```
4.  配置主认证、授权和计费服务器的 IP 地址为 10.1.1.1，认证、授权和计费的端口号为 49（HWTACACS 服务器的认证、授权和计费端口为 TCP 端口 49）。
    ```纯文本
    [Device-hwtacacs-hwtac] primary authentication 10.1.1.1 49 
    [Device-hwtacacs-hwtac] primary authorization 10.1.1.1 49 
    [Device-hwtacacs-hwtac] primary accounting 10.1.1.1 49
    ```
5.  配置与认证、授权和计费服务器交互报文时的共享密钥均为明文 expert
    ```纯文本
    [Device-hwtacacs-hwtac] key authentication simple expert 
    [Device-hwtacacs-hwtac] key authorization simple expert 
    [Device-hwtacacs-hwtac] key accounting simple expert 
    [Device-hwtacacs-hwtac] quit
    ```
6.  配置与认证、授权和计费服务器交互报文时的共享密钥均为明文 expert。
    ```纯文本
    [Device-hwtacacs-hwtac] key authentication simple expert
    [Device-hwtacacs-hwtac] key authorization simple expert
    [Device-hwtacacs-hwtac] key accounting simple expert
    [Device-hwtacacs-hwtac] quit
    ```
7.  &#x20;配置 ISP 域的 AAA 方案，为 login 用户配置 AAA 认证方法为 HWTACACS 认证、授权和计费。
    ```纯文本
    [Device] domain bbb 
    [Device-isp-bbb] authentication login hwtacacs-scheme hwtac 
    [Device-isp-bbb] authorization login hwtacacs-scheme hwtac 
    [Device-isp-bbb] accounting login hwtacacs-scheme hwtac 
    [Device-isp-bbb] quit
    ```
