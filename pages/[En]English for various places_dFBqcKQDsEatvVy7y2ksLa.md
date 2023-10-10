# \[En]English for various places

English for [various](various_33AFVAkTGcxxu1K2rx82GD.md "various") places各种地方的英语

***

[\[En\]PythonCharm](\[En]PythonCharm_t43WRubWEaAvnJTzDNMKYp.md "\[En]PythonCharm")

[vim提示](vim提示_sB47AgDwTKPu683qy1QUrD.md "vim提示")

[WebStorm](WebStorm_d3hy9J6N12JNqBxv87uVn6.md "WebStorm")

[NetDrive3](NetDrive3_oSqEWUXNJrhPwabtr2etMU.md "NetDrive3")

[\[En\]VS code](<\[En]VS code_u36F9CxNPtBiyuXx4C6JyZ.md> "\[En]VS code")

[Sandboxie-Plus](Sandboxie-Plus_9ZV1bnKve6ZU1Xrq97JRoy.md "Sandboxie-Plus")

[IDM翻译](IDM翻译_9ReA3S9EkkB9ZdDkY1k9fJ.md "IDM翻译")

[qimgv翻译](qimgv翻译_9HMeK9ofB8sgwMrgS6eGdw.md "qimgv翻译")



-   \[En]Git(1%)
    # 安装时
    ![](../image/image_JfvZJn3rAR.png)

    ![](../image/image_D4mr0WP_jv.png)

    ![](../image/image_MdSsvX0bVN.png)

    ![](../image/image_7KVSRPaPgU.png)

    ![](../image/image_fp_7CnQ3a_.png)

    ![](../image/image_sRp8yfR1DE.png)

    ![](../image/image_ia8IjcYVay.png)

    ![](../image/image_0wVHa8zwW_.png)

    ![](../image/image_Y0bUbElKW6.png)
    # 命令输出时
    `git status`
    -   On [branch](branch_xiyzwHmMUgEmdqeXgrPAMT.md "branch") master
        nothing to commit, working tree clean
    -   Changes to be committed
        ```纯文本
        wq@DESKTOP-P7DQ7AA MINGW64 /e/tem (master)
        $ git status
        On branch master

        No commits yet

        Changes to be committed:
          (use "git rm --cached <file>..." to unstage)
                new file:   doc1/text_1.txt

        ```
    -   nothing to commit, working tree clean
        ```纯文本
        wq@DESKTOP-P7DQ7AA MINGW64 /e/tem (master)
        $ git status
        On branch master
        nothing to commit, working tree clean

        ```
    -   insertions、[deletion](deletion_gJFzpv57iF6FnW3fCSQop1.md "deletion")
        ```纯文本
        wq@DESKTOP-P7DQ7AA MINGW64 /e/tem (v2)
        $ git commit -m v2
        [v2 8add9e7] v2
         1 file changed, 2 insertions(+), 1 deletion(-)

        ```
    ***
    Git出现的新单词：[merge](merge_5sduKaNVuqfNgUyb5Sy7Cy.md "merge")、[rebase](rebase_8WDa5dnqcY7fE9vpoy2CXn.md "rebase")、[reset](reset_7MrquJxJuhyuUsQsqtPW6j.md "reset")、[revert](revert_9U33wF5FavwRtAZvZA6fg2.md "revert")、insertions


-   \[En]Nginx官方配置文档

[\[En\]CRT](\[En]CRT_pPE5GB25YLgvEEjMksc11F.md "\[En]CRT")

[\[En\]Elastic](\[En]Elastic_fB9YgM11bHqSmiZWQXAuav.md "\[En]Elastic")

[\[En\]Kibana](\[En]Kibana_cxCoaF95rugzKRCcALYNSK.md "\[En]Kibana")

[\[En\]pytho](\[En]pytho_hksgL7fYKFjVkqqXCSo7Lu.md "\[En]pytho")

[\[En\]Linux](\[En]Linux_uydYnM3wcHE3rKLJVyyNpp.md "\[En]Linux")

[\[En\]windows](\[En]windows_diUQ2KvQKubERWufJ35dUk.md "\[En]windows")

[\[En\]NAS英语翻译](\[En]NAS英语翻译_iQYrGsweUjmcw8VUyKJ58h.md "\[En]NAS英语翻译")

# Network Devices

[华为设备相关](华为设备相关_vC8EGJCx7HP9MCDJEKT4sN.md "华为设备相关")

[H3C](H3C_4oA5NKQHStJxKnC8A2F4L7.md "H3C")

[inspur浪潮](inspur浪潮_izrSC9Va9RP4RFBo498cC7.md "inspur浪潮")

# other

-   system boot warning

    ![](../image/5c90212e483f599212062d71ee551a5_5pmrBjwrU0.jpg)



[\[En\]Logstash](\[En]Logstash_rbz3LUggokF9zsQSgYeFss.md "\[En]Logstash")

# \[Q]MySQL

-   \[Q]MySQL5.7中日志时间戳与系统时间不匹配。原因：因为`log_timestamps`默认是UTC

    查询方法
    ```python
    SHOW variables like'log_time%';
    SELECT @@global.log_timestamps;
    ```
    ```python
    +---------------------+-------------------+
    |Variable_name        |           Value   |
    +---------------------+-------------------+
    |log_timestamps       |           UTC     |
    +---------------------+-------------------+
    ```
    解决方案：不重启MySQL服务的修改方案：修改值为SYSTEM

    1、临时修改
    ```python
    SET GLOBAL log_timestamps=SYSTEM;
    ```
    2、永久修改
    ```python
    [mysqld]
    log_timestamps = SYSTEM
    ```
-   \[En]'ENCODE' is deprecated and will be removed in a future release. Please use AES\_ENCRYPT instead


-   \[Error]相同的UUID将会报错

    ![](../image/image_taMg1eJZMx.png)
-   \[Error]注意：在从机执行show slave status\G时报错：

    Last\_IO\_Error: error connecting to master 'slave1\@192.168.1.150:3306' - retry-time: 60 retries: 1
    message: Authentication plugin 'caching\_sha2\_password' reported error: Authentication requiressecure connection.





# 碎片

-   error: mysql-community-client\_8.0.29-1ubuntu21.10\_amd64.deb: not an rpm package (or package manifest):
-   configure there settings to [ensure](ensure_AKCQtifwX4npH7TCkLpEp.md "ensure") [option](option_WdhQG4FrJd8p7SZsFioTC.md "option") disk [performance](performance_eYn42F8r3D2n4ZPVG2RrSR.md "performance") and [health](health_fSEdt3RUT1CnsaDoA2ryDf.md "health")

    配置那里的设置以确保选项磁盘性能和运行状况

    ![](../image/image_Gyn8NzsVoM.png)
-   \[W]debconf: [delaying](delaying_ve4o8oBhNYJdmzewHd3e72.md "delaying") package configuration, [since](since_qu9cpjucCeKSwWCi2pxZ9k.md "since") apt-utils is not installed



