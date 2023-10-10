# \[En]CRT

[CRT破解软件提示](CRT破解软件提示_3f6EnNAZVSTuyLjXmPub95.md "CRT破解软件提示")

![](../image/image_N1cynRRQOk.png)



# 选项栏

-   CRT创建密钥对过程(翻译)

    Tools → Create Public Key

    Key [generation](generation_d5sCKbwRiCkfY134aU52w3.md "generation") [wizard](wizard_muT5PMcC9QaT5a8dEScU3t.md "wizard")
    1.  &#x20;介绍

        ![](../image/image_ZzEyStxVHU.png)
        -   The Key Generation Wizard helps you create a public-[private](private_jgp8HASe2gh6NaFrRJsnnS.md "private") key [pair](pair_h6M6MgUVm6gvVBUgiFy6ui.md "pair") used for [authentication](authentication_j9KWdDPiAcGnCYJitBzwAw.md "authentication"). [separate](separate_qSpyR4MPy5y8w1z7atrrcX.md "separate") files will be created for your public and private keys.

            密钥创建向导帮助你创建用于验证公私钥对，将为你公钥和私钥创建单独的文件。
        -   To begin using your key， you wil need to copy the pubic key file to a drectory on the SSH host after the wizard is finished.See Help or contact your SSH server administrator for more information

            要开始使用您的密钥，您需要在向导完成后将公钥文件复制到 SSH 主机上的目录中。有关详细信息，请参阅帮助或联系您的 SSH 服务器管理员
    2.  &#x20; 加密类型设置

        ![](../image/image_xaLr5MLXLM.png)
        -   select the type of public key to generate

            选择公钥创建的类型：[Ed25519](Ed25519_hnu6e1jizJsNdSixCczdFJ.md "Ed25519")、[RSA](RSA_98Z6nqn4tcZcGK3Qw9cxUM.md "RSA")、[ECDSA](ECDSA_thGnLjChGuaNFa4DyLrYDL.md "ECDSA")、[DSA](DSA_xrxq2AxEh6fr7dzNXYJzGr.md "DSA")
    3.  &#x20;密码口令设置

        ![](../image/image__5cpXtErni.png)
        -   enter a [passphrase](passphrase_dd5d8RGn7v3UeSkCwJPeoS.md "passphrase") [which](which_2Z8rHRsSCfSMVCCXNHhHpc.md "which") protected your encrypted [private](private_jgp8HASe2gh6NaFrRJsnnS.md "private")key. the passphrase is [optional](optional_gWhENUvCauc2n93AZG5n67.md "optional")，but if it is not used， the private key will not be encrypted (not recommended)

            ~~输入密码保护你的加密私钥~~\输入保护您的加密私钥的密码。，这个密码是可选的，但是如果你不使用它，私钥将不会被加密(不推荐)
        -   3Cr4dlmm))&
        ***
        -   enter a [comment](comment_b3Y9cQswCq8TzEyKKQn7fK.md "comment") that will be displayed when are asked for your passphrase. it will be stored with your key.

            在输入密码时，显示的注释，这个将被存储在密钥中
        ***
    4.  加密强度设置
    5.  加密中

        ![](../image/image_CM52WEcte8.png)
    6.  选择目录和私钥文件名

        ![](../image/image_NQq5H5f0_f.png)

        choose a directory and filename for the private key.
        -   Standard public key and VanDyke Key Formant
            -   公钥内容格式
                ```纯文本
                ---- BEGIN SSH2 PUBLIC KEY ----
                Subject: w
                Comment: ""
                ModBitSize: 2048
                AAAAB3NzaC1yc2EAAAADAQABAAABAQCugV5+3BkdelAsh2uFfu2nwffrM1QXUhKr
                y+tpQanJTBs2x4sVADv7cSzQYF5zuJuqmY0N2SqhuwIPgU+hN+iPUcyJ/+wGnOlO
                /dxNhIokcZSusLjmeT9uahPGrL+9miKFWTvjJXmwrZA3GURQWwDnPvdsxQvwZ21w
                zDifENamT4uYCL/zs86tXaygHK7zYHc36MR/rMM7SjaSj6cfNw3yO0R8mTkCu8Zc
                jwDoxLK/TgJLxFvcp5bRMdunb5qSV1OA5yfH6m2XuRRdReNuMVFyda8UwyT8ShOM
                wngUi7Hq+pP43JRQ4xgyhUePMYfp/9EgyhXUz70MDoJ1l5tj90zr
                ---- END SSH2 PUBLIC KEY ----

                ```
        -   **OpenSSH Key format(new)**
            -   公钥内容格式
                ```纯文本
                ssh-rsa AAAAB3NzaC1yc2EAAAADAQABAAABAQCwP8DqKeFZXHvMgmVO5uSLw+6gbWlArxkPrU7ebNJ0DnltuJ9tGzu4S0M79RnU0tLdRTDXEyy1zviw0Avj/Uuz6tuuPJqYUuopzLbHOPOBpWBAbUOQU1B7U5CZuG90Rhd3z/ayTwmYao7v3rW5XqMQ6Tz18EOO9hhuq+vAFuAfa86r3OzoTFM7jyffye180ozfyn9R2HswkOmS7NJ4P4L3cQrwzDPyHZHGGflDsoQsF4lJ6BwY3t9cm7Dyx3kqOMTjG6WWMoUYljfVYKtmy9l6O9kacTpA83763UHowydzqE3GlACnlKJ6cYJzfBrJewt6Ar2pZeiaa0aoqQ1uwVLD qweasd
                ```
        -   OpenSSH Key format(legacy)
            -   公钥格式
                ```纯文本
                ssh-rsa AAAAB3NzaC1yc2EAAAADAQABAAABAQDKPTNAil2r0XfI+8xEq8TwFtdqk1/rqkBYouiDHtzu20xsn+ihdZ+Mi+/wv+Kp5xGNpk+1bW5vC9nnebZ03pY3Km4H6tCcSwrP+87kXYbR89ZI6PXvhDOnNNu1nh4jP/nFiWAxccajuDCJRtbl3JqbgrsWJUgQh+LbRIVuXyKMUHYjyipIZmYInN+jvAwJoiPmLZnEod4lvmT8KSy3CKXXNFCVEhKWdPWwla/hU0QsoSjFdbS4ulOszKg0ywDN472LMkJ2VD6HIrB0aWHVTyVmjv+5tfkApsTQows1t9krMzNQLmFjNKDz9Q9RD6CSUC5Rycg2wdJExZXmG2kpNBpL qweasd
                ```
        ***
        private key filename

        after exiting the wizard ，upload the public key file to the appropriate folder on your SSH server. see help or referto your SSH server documentation for more information.
    7.  &#x20;

        ![](../image/image_Ip98LBRLrZ.png)

        Would you like to use this key as your global publickey?
        您想将此密钥用作您的全局公钥吗？







# 碎片

SSH登录验证(authentication)

-   publicKey
-   keyboard interactive
-   GSSAPI
-   Password
-   \[Q]SFTP登录设备报警

    ![](../image/image_GJiwhiQxMq.png)
    ```纯文本
    i SecureFX version 8.3.3.1646 (Official Release - May 3, 2018) 
    i Attempting to connect to 10.43.233.254 
    i Session window 00001 established for session 省水利厅\A水利厅设备\省厅网络设备\(S)3260-10.43.233.254
    i SSH2Core version 8.3.0.1646
    i Connecting to 10.43.233.254:22 ...
    i Changing state from STATE_NOT_CONNECTED to STATE_EXPECT_KEX_INIT
    i Using protocol SSH2
    i RECV : Remote Identifier = 'SSH-1.99-DOPRA-1.5'
    i CAP  : Remote can re-key
    i CAP  : Remote sends language in password change requests
    i CAP  : Remote sends algorithm name in PK_OK packets
    i CAP  : Remote sends algorithm name in public key packets
    i CAP  : Remote sends algorithm name in signatures
    i CAP  : Remote sends error text in open failure packets
    i CAP  : Remote sends name in service accept packets
    i CAP  : Remote includes port number in x11 open packets
    i CAP  : Remote uses 160 bit keys for SHA1 MAC
    i CAP  : Remote supports new diffie-hellman group exchange messages
    i CAP  : Remote correctly handles unknown SFTP extensions
    i CAP  : Remote correctly encodes OID for gssapi
    i CAP  : Remote correctly uses connected addresses in forwarded-tcpip requests
    i CAP  : Remote can do SFTP version 4
    i CAP  : Remote uses SHA1 hash in RSA signatures for x.509v3
    i CAP  : Remote x.509v3 uses ASN.1 encoding for DSA signatures
    i CAP  : Remote correctly handles zlib@openssh.com
    i SSPI : Requesting full delegation
    i SSPI : [Kerberos] SPN : host@10.43.233.254
    i SSPI : [Kerberos] InitializeSecurityContext() failed.
    i SSPI : [Kerberos] The specified target is unknown or unreachable
    i SSPI : [Kerberos] Disabling gss mechanism
    i GSS  : Requesting full delegation
    i GSS  : [Kerberos] SPN : host@10.43.233.254
    i GSS  : [Kerberos] InitializeSecurityContext() failed.
    i GSS  : [Kerberos] Could not load library 'gssapi64.dll': The specified module could not be found.
    i GSS  : [Kerberos] Disabling gss mechanism
    i GSS  : [Kerberos] Disabling gss mechanism
    i The following key exchange method has been filtered from the key exchange method list because it is not supported: gss-group1-sha1-toWM5Slw5Ew8Mqkay+al2g==
    i SSPI : Requesting full delegation
    i SSPI : [Kerberos (Group Exchange)] SPN : host@10.43.233.254
    i SSPI : [Kerberos (Group Exchange)] InitializeSecurityContext() failed.
    i SSPI : [Kerberos (Group Exchange)] The specified target is unknown or unreachable
    i SSPI : [Kerberos (Group Exchange)] Disabling gss mechanism
    i GSS  : Requesting full delegation
    i GSS  : [Kerberos (Group Exchange)] SPN : host@10.43.233.254
    i GSS  : [Kerberos (Group Exchange)] InitializeSecurityContext() failed.
    i GSS  : [Kerberos (Group Exchange)] Could not load library 'gssapi64.dll': The specified module could not be found.
    i GSS  : [Kerberos (Group Exchange)] Disabling gss mechanism
    i GSS  : [Kerberos (Group Exchange)] Disabling gss mechanism
    i The following key exchange method has been filtered from the key exchange method list because it is not supported: gss-gex-sha1-toWM5Slw5Ew8Mqkay+al2g==
    i SEND : KEXINIT
    i RECV : Read kexinit
    i Available Remote Kex Methods = diffie-hellman-group1-sha1,diffie-hellman-group-exchange-sha1
    i Selected Kex Method = diffie-hellman-group-exchange-sha1
    i Available Remote Host Key Algos = ssh-rsa
    i Selected Host Key Algo = ssh-rsa
    i Available Remote Send Ciphers = aes128-cbc,blowfish-cbc,3des-cbc,des-cbc
    i Selected Send Cipher = aes128-cbc
    i Available Remote Recv Ciphers = aes128-cbc,blowfish-cbc,3des-cbc,des-cbc
    i Selected Recv Cipher = aes128-cbc
    i Available Remote Send Macs = hmac-sha1,hmac-sha1-96,hmac-md5,hmac-md5-96
    i Selected Send Mac = hmac-sha1
    i Available Remote Recv Macs = hmac-sha1,hmac-sha1-96,hmac-md5,hmac-md5-96
    i Selected Recv Mac = hmac-sha1
    i Available Remote Compressors = none
    i Selected Compressor = none
    i Available Remote Decompressors = none
    i Selected Decompressor = none
    i Changing state from STATE_EXPECT_KEX_INIT to STATE_KEY_EXCHANGE
    i SEND : KEXDH_GEX_REQUEST
    i RECV : KEXDH_GEX_GROUP
    i RECV : DH Prime is 2048 bits
    i SEND : KEXDH_INIT
    i RECV : KEXDH_REPLY
    i Changing state from STATE_KEY_EXCHANGE to STATE_READY_FOR_NEW_KEYS
    i RECV: Remote Hostkey (SHA-2 hash hex): d9:0f:4d:d0:d0:3c:83:fb:db:6f:71:f5:72:13:e0:4f:71:8c:cf:f9:d2:b7:ee:ff:0a:56:6d:5e:1c:b0:1d:03
    i RECV: Remote Hostkey (SHA-2 hash base64): 2Q9N0NA8g/vbb3H1chPgT3GMz/nSt+7/ClZtXhywHQM
    i RECV: Remote Hostkey (SHA-1 hash): e3:60:0b:ca:48:ae:9a:de:24:59:7e:16:3c:0d:ff:cd:0b:82:24:51
    i RECV: Remote Hostkey (MD5 hash): 75:32:15:55:6c:97:83:d5:0c:4a:ee:c9:85:18:d2:22
    i SEND : NEWKEYS
    i Changing state from STATE_READY_FOR_NEW_KEYS to STATE_EXPECT_NEWKEYS
    i RECV : NEWKEYS
    i Changing state from STATE_EXPECT_NEWKEYS to STATE_CONNECTION
    i SEND: SERVICE_REQUEST[ssh-userauth]
    i RECV: SERVICE_ACCEPT[ssh-userauth] -- OK
    i SENT : USERAUTH_REQUEST [none]
    i Authenticating as user huawei
    i RECV : USERAUTH_FAILURE, continuations [password]
    i SENT : USERAUTH_REQUEST [password]
    i RECV : AUTH_SUCCESS
    i RECV : Server Sftp Version: 3
    i SEND : fs-multiple-roots-supported request[On]
    i SEND : vendor-id request
    i Changing state from STATE_CONNECTION to STATE_CLOSING
    i RECV: Disconnect packet (reason: 2: A protocol error occurred. The connection is closed by SSH Server//Current FSM is SSH_Main_Disconnect )
    i Changing state from STATE_CLOSING to STATE_CLOSED
    i Connected for 1 seconds, 1717 bytes sent, 1495 bytes received
    i A protocol error occurred.//The connection is closed by SSH Server//Current FSM is SSH_Main_Disconnect
    i Channel Closed.

    ```
