# \[英语]华为SSH翻译

SSH登录时提醒消息

```纯文本
[[NW_HW_SW_05L3_3]stelnet 172.16.254.22
Please input the username:huawei
Trying 172.16.254.22 ...
Press CTRL+K to abort
Connected to 172.16.254.22 ...
Warning: The negotiated encryption, digest or key exchange algorithm is insecure. Using a security algorithm (AES256-CTR,SHA2-256,diffie-hellman-group-exchange-sha256) is recommended.
Enter password:
Enter password:

Info: The max number of VTY users is 10, and the number
      of current VTY users on line is 1.
      The current login time is 2020-12-23 02:17:45+00:00.
Info: Lastest accessed IP: 172.16.254.23  Time: 2020-12-23 02:17:42  Failed: 1

Info: Smart-upgrade is currently disabled. Enable Smart-upgrade to get recommended version information. SSH登录时提醒消息
```

-   \[纯文本 代码块]Warning: The  [encryption](encryption_pb9m7Myz6P7jzv2k7pq2V2.md "encryption"), [digest](digest_d5fJb2XrrVmgNByubUa24y.md "digest") or key exchange algorithm is [insecure](insecure_uhCs27Ne43HDoKUbjDwRhP.md "insecure"). Using a security algorithm (AES256-CTR,SHA2-256,diffie-hellman-group-exchange-sha256) is recommended.

    警告：加密，摘要，或者密钥交换算法是不安全的。推荐使用安全的算法。
-   \[纯文本 代码块]Info: Smart-upgrade is currently disabled. Enable Smart-upgrade to get recommended version information.

    提示：当前的智能升级是禁用的，开启智能升级获得推荐的版本信息。

