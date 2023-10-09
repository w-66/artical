# 正则表达式示例

-   表达式的分组使用()来标记. 表达式的分组可以被引用为 \0, \1, \2, \3, 等等. \0 表示被匹配的所有字符串. \1 表示被匹配的第一个分组, \2 表示第二个分组

[正则 符号\[reg.\]](<正则 符号\[reg.]_bUBxxrx8vz57vaLdMYwgYN.md> "正则 符号\[reg.]")

***

## 匹配替换

-   示例：将下列文本替换成键值对 \[使用组替换]
    -   1、匹配：`(.*)\t(.*)` 替换：`'$1':'$2',`
        ```python
        from  en
        to  zh
        query  hell
        transtype  realtime
        simple_means_flag  3
        sign  921462.715847
        token  571a154a0227d35f306df93d41e5a536
        domain  common
        ```
        匹配：`(.*)\t(.*)` 替换：`'$1':'$2',`
        ```python
        'from':'en',
        'to':'zh',
        'query':'hell',
        'transtype':'realtime',
        'simple_means_flag':'3',
        'sign':'921462.715847',
        'token':'571a154a0227d35f306df93d41e5a536',
        'domain':'common',
        ```
    -   2、匹配： `(.*): (.*)`  替换：`'$1':'$2',`
        ```python
        Accept: */*
        Accept-Encoding: gzip, deflate, br
        Accept-Language: en,zh-CN;q=0.9,zh;q=0.8
        Acs-Token: 1663398172478_1663426765607_3dRSjIJvEsSE0MO2ZVp76I51LomX1H7n+pZZEh4X1VdB07sWzr0Yh7p0inUdPtSSnY7E1hXHA+DF2o8cU4ErdcOyP4PyOEBDwWa90rm6RtSTwuA03TfS8XsZF2vsyoSU0KlX3h2ekhSBs5/dJKJ/T0ts6eAZ8D0xBx5uk2fsMoBhKajIKRSliNvDtu/mTDeUeTMYuo6HQlNpBzq++967H815W0ojfyac6OOhi5CjAPx8achNCwtE7iEu+/Wt4H/AIWb/zshf0qMItiSpQnBqd55DCI7pREFP6doWUif1vQ0SjAmL4gZkab4dnrsgzN9N
        Connection: keep-alive
        Content-Length: 135
        Content-Type: application/x-www-form-urlencoded; charset=UTF-8
        Cookie: BIDUPSID=3C3E6FDD18CB46529167CA66530D7B6C; PSTM=1663403293; BAIDUID=3C3E6FDD18CB46520044B426016749B3:FG=1; BDORZ=B490B5EBF6F3CD402E515D22BCDA1598; ZFY=IHVvcq9ZfdKchpJgvCuP8yNKWdaatSy:AIIuuBgtMRcc:C; BAIDUID_BFESS=3C3E6FDD18CB46520044B426016749B3:FG=1; APPGUIDE_10_0_2=1; REALTIME_TRANS_SWITCH=1; FANYI_WORD_SWITCH=1; HISTORY_SWITCH=1; SOUND_PREFER_SWITCH=1; SOUND_SPD_SWITCH=1; Hm_lvt_64ecd82404c51e03dc91cb9e8c025574=1663422810; Hm_lpvt_64ecd82404c51e03dc91cb9e8c025574=1663426755; ab_sr=1.0.1_YzJmNWMzZDBkY2Q3ZGI5MGM5YTc1NDIwNjQwMmE4NTVhMTc2ZGUwM2Y1OTZmNTMzYjY3OTg5Yjk3ZWIxYjJjZDYyZmJiYjBmMWIwZGY3YWU4Y2I5ZjRiOWY5ZTBjYzNjMGE0YjQxYjI2NjZhY2JiMzRhYTY0YWU5NTBkZTZkM2Q2OGNlYWM4OTEzOTVhOWYwODg1NzFlMzYxZmQwYTZmZg==
        Host: fanyi.baidu.com
        Origin: https://fanyi.baidu.com
        Referer: https://fanyi.baidu.com/
        Sec-Fetch-Dest: empty
        Sec-Fetch-Mode: cors
        Sec-Fetch-Site: same-origin
        User-Agent: Mozilla/5.0 (Windows NT 10.0; Win64; x64) AppleWebKit/537.36 (KHTML, like Gecko) Chrome/102.0.0.0 Safari/537.36
        X-Requested-With: XMLHttpRequest
        sec-ch-ua: " Not A;Brand";v="99", "Chromium";v="102", "Google Chrome";v="102"
        sec-ch-ua-mobile: ?0
        sec-ch-ua-platform: "Windows"
        ```
        匹配： `(.*): (.*)`  替换：`'$1':'$2',`
        ```python
        'Accept':'*/*',
        'Accept-Encoding':'gzip, deflate, br',
        'Accept-Language':'en,zh-CN;q=0.9,zh;q=0.8',
        'Acs-Token':'1663398172478_1663426765607_3dRSjIJvEsSE0MO2ZVp76I51LomX1H7n+pZZEh4X1VdB07sWzr0Yh7p0inUdPtSSnY7E1hXHA+DF2o8cU4ErdcOyP4PyOEBDwWa90rm6RtSTwuA03TfS8XsZF2vsyoSU0KlX3h2ekhSBs5/dJKJ/T0ts6eAZ8D0xBx5uk2fsMoBhKajIKRSliNvDtu/mTDeUeTMYuo6HQlNpBzq++967H815W0ojfyac6OOhi5CjAPx8achNCwtE7iEu+/Wt4H/AIWb/zshf0qMItiSpQnBqd55DCI7pREFP6doWUif1vQ0SjAmL4gZkab4dnrsgzN9N',
        'Connection':'keep-alive',
        'Content-Length':'135',
        'Content-Type':'application/x-www-form-urlencoded; charset=UTF-8',
        'Cookie':'BIDUPSID=3C3E6FDD18CB46529167CA66530D7B6C; PSTM=1663403293; BAIDUID=3C3E6FDD18CB46520044B426016749B3:FG=1; BDORZ=B490B5EBF6F3CD402E515D22BCDA1598; ZFY=IHVvcq9ZfdKchpJgvCuP8yNKWdaatSy:AIIuuBgtMRcc:C; BAIDUID_BFESS=3C3E6FDD18CB46520044B426016749B3:FG=1; APPGUIDE_10_0_2=1; REALTIME_TRANS_SWITCH=1; FANYI_WORD_SWITCH=1; HISTORY_SWITCH=1; SOUND_PREFER_SWITCH=1; SOUND_SPD_SWITCH=1; Hm_lvt_64ecd82404c51e03dc91cb9e8c025574=1663422810; Hm_lpvt_64ecd82404c51e03dc91cb9e8c025574=1663426755; ab_sr=1.0.1_YzJmNWMzZDBkY2Q3ZGI5MGM5YTc1NDIwNjQwMmE4NTVhMTc2ZGUwM2Y1OTZmNTMzYjY3OTg5Yjk3ZWIxYjJjZDYyZmJiYjBmMWIwZGY3YWU4Y2I5ZjRiOWY5ZTBjYzNjMGE0YjQxYjI2NjZhY2JiMzRhYTY0YWU5NTBkZTZkM2Q2OGNlYWM4OTEzOTVhOWYwODg1NzFlMzYxZmQwYTZmZg==',
        'Host':'fanyi.baidu.com',
        'Origin':'https://fanyi.baidu.com',
        'Referer':'https://fanyi.baidu.com/',
        'Sec-Fetch-Dest':'empty',
        'Sec-Fetch-Mode':'cors',
        'Sec-Fetch-Site':'same-origin',
        'User-Agent':'Mozilla/5.0 (Windows NT 10.0; Win64; x64) AppleWebKit/537.36 (KHTML, like Gecko) Chrome/102.0.0.0 Safari/537.36',
        'X-Requested-With':'XMLHttpRequest',
        'sec-ch-ua':'" Not A;Brand";v="99", "Chromium";v="102", "Google Chrome";v="102"',
        'sec-ch-ua-mobile':'?0',
        'sec-ch-ua-platform':'"Windows"',
        ```

***

## 匹配

-   示例：匹配一行有两个相同的单词 \[`^``()``\w``\s``*`(星号)`$`]
    ```react&#x20;jsx
    ^(\w+)\s+\1\s*$
    ```
    取\$1进行替换成一个
-   示例：匹配替换：字段解释
    ```sql
    匹配
    \n\r\n
    替换为
    \t
    ```
    ```sql
    Aborted_clients

    指出由于某种原因客户程序不能正常关闭连接而导致失败的连接的数量。如果客户不在退出之前调整mysql_close()函数，wait_timeout或interactive_timeout的限制已经被超出，或者是客户端程序在传输的过程中被关闭，则这种情况会发生。
    Aborted_connects

    指出试图连接到MYSQL的失败的次数。这种情况在客户尝试用错误的密码进行连接时，没有权限进行连接时，为获得连接的数据包所花费的时间超过了connect_timeout限制的秒数，或数据包中没有包含正确的信息时，都会发生。
    Bytes_received

    从客户处已经接收到的字节数。
    ```
    替换后
    ```sql
    Aborted_clients
      指出由于某种原因客户程序不能正常关闭连接而导致失败的连接的数量。如果客户不在退出之前调整mysql_close()函数，wait_timeout或interactive_timeout的限制已经被超出，或者是客户端程序在传输的过程中被关闭，则这种情况会发生。
    Aborted_connects
      指出试图连接到MYSQL的失败的次数。这种情况在客户尝试用错误的密码进行连接时，没有权限进行连接时，为获得连接的数据包所花费的时间超过了connect_timeout限制的秒数，或数据包中没有包含正确的信息时，都会发生。
    Bytes_received
      从客户处已经接收到的字节数。
    ```

1.  匹配的字符，添加其他字符包裹，如括号等

    [参考](https://blog.csdn.net/zoukangdlut/article/details/53072583 "参考")

    表达式的分组使用()来标记. 表达式的分组可以被引用为 \0, \1, \2, \3, 等等. \0 表示被匹配的所有字符串. \1 表示被匹配的第一个分组, \2 表示第二个分组

    所有Ubuntu的版本号以 `` ` `` 包裹

    匹配：`Ubuntu.*[）0-9S]`

    替换：`` `$0` ``
    -   原文
        ```纯文本
        版本号  代号  发布时间
        Ubuntu 4.10（初始发布版本）
          Warty Warthog  2004-10-20
        Ubuntu 5.04
          Hoary Hedgehog  2005-04-08
        Ubuntu 5.10
          Breezy Badger  2005-10-13
        Ubuntu 6.06 LTS
          Dapper Drake  2006-06-01
        Ubuntu 6.10
          Edgy Eft  2006-10-26
        Ubuntu 7.04
          Feisty Fawn  2007-04-19
        Ubuntu 7.10
          Gutsy Gibbon  2007-10-18
        Ubuntu 8.04 LTS
          Hardy Heron  2008-04-24
        Ubuntu 8.10
          Intrepid Ibex  2008-10-30
        Ubuntu 9.04
          Jaunty Jackalope  2009-04-23
        Ubuntu 9.10
          Karmic Koala  2009-10-29
        Ubuntu 10.04 LTS
          Lucid Lynx  2010-04-29
        Ubuntu 10.10
          Maverick Meerkat  2010-10-10
        Ubuntu 11.04（Unity成为默认桌面环境）
          Natty Narwhal  2011-04-28
        Ubuntu 11.10
          Oneiric Ocelot  2011-10-13
        Ubuntu 12.04 LTS
          Precise Pangolin  2012-04-26
        Ubuntu 12.10
          Quantal Quetzal  2012-10-18
        Ubuntu 13.04
          Raring Ringtail  2013-04-25
        Ubuntu 13.10
          Saucy Salamander  2013-10-17
        Ubuntu 14.04 LTS
          Trusty Tahr  2014-04-18
        Ubuntu 14.10
          Utopic Unicorn  2014-10-23
        Ubuntu 15.04
          Vivid Vervet  2015-04-22
        Ubuntu 15.10
          Wily Werewolf  2015-10-23
        Ubuntu 16.04 LTS
          Xenial Xerus  2016-04-21
        Ubuntu 16.10
          Yakkety Yak  2016-10-20
        Ubuntu 17.04
          Zesty Zapus  2017-04-13
        Ubuntu 17.10（GNOME成为默认桌面环境）
          Artful Aardvark  2017-10-21
        Ubuntu 18.04 LTS
          Bionic Beaver  2018-04-26
        Ubuntu 18.10
          Cosmic Cuttlefish  2018-10-18
        Ubuntu 19.04
          Disco Dingo  2019-4-19
        Ubuntu 19.10
          Eoan Ermine  2019-10-17
        Ubuntu 20.04 LTS
          Focal Fossa  2020-04-23
        Ubuntu 20.10
          Groovy Gorilla  2020-10-22
        Ubuntu 21.04
          Hirsute Hippo  2021-04-22
        ```
    -   替换后
        ```纯文本
        版本号  代号  发布时间
        `Ubuntu 4.10（初始发布版本）`
          Warty Warthog  2004-10-20
        `Ubuntu 5.04`
          Hoary Hedgehog  2005-04-08
        `Ubuntu 5.10`
          Breezy Badger  2005-10-13
        `Ubuntu 6.06 LTS`
          Dapper Drake  2006-06-01
        `Ubuntu 6.10`
          Edgy Eft  2006-10-26
        `Ubuntu 7.04`
          Feisty Fawn  2007-04-19
        `Ubuntu 7.10`
          Gutsy Gibbon  2007-10-18
        `Ubuntu 8.04 LTS`
          Hardy Heron  2008-04-24
        `Ubuntu 8.10`
          Intrepid Ibex  2008-10-30
        `Ubuntu 9.04`
          Jaunty Jackalope  2009-04-23
        `Ubuntu 9.10`
          Karmic Koala  2009-10-29
        `Ubuntu 10.04 LTS`
          Lucid Lynx  2010-04-29
        `Ubuntu 10.10`
          Maverick Meerkat  2010-10-10
        `Ubuntu 11.04（Unity成为默认桌面环境）`
          Natty Narwhal  2011-04-28
        `Ubuntu 11.10`
          Oneiric Ocelot  2011-10-13
        `Ubuntu 12.04 LTS`
          Precise Pangolin  2012-04-26
        `Ubuntu 12.10`
          Quantal Quetzal  2012-10-18
        `Ubuntu 13.04`
          Raring Ringtail  2013-04-25
        `Ubuntu 13.10`
          Saucy Salamander  2013-10-17
        `Ubuntu 14.04 LTS`
          Trusty Tahr  2014-04-18
        `Ubuntu 14.10`
          Utopic Unicorn  2014-10-23
        `Ubuntu 15.04`
          Vivid Vervet  2015-04-22
        `Ubuntu 15.10`
          Wily Werewolf  2015-10-23
        `Ubuntu 16.04 LTS`
          Xenial Xerus  2016-04-21
        `Ubuntu 16.10`
          Yakkety Yak  2016-10-20
        `Ubuntu 17.04`
          Zesty Zapus  2017-04-13
        `Ubuntu 17.10（GNOME成为默认桌面环境）`
          Artful Aardvark  2017-10-21
        `Ubuntu 18.04 LTS`
          Bionic Beaver  2018-04-26
        `Ubuntu 18.10`
          Cosmic Cuttlefish  2018-10-18
        `Ubuntu 19.04`
          Disco Dingo  2019-4-19
        `Ubuntu 19.10`
          Eoan Ermine  2019-10-17
        `Ubuntu 20.04 LTS`
          Focal Fossa  2020-04-23
        `Ubuntu 20.10`
          Groovy Gorilla  2020-10-22
        `Ubuntu 21.04`
          Hirsute Hippo  2021-04-22
        ```
2.  在行首加字符
    -   示例：行首是字母开头的，在之前添加制表符(tab)

        匹配：`^([a-Z].+)$`

        替换：`\t$1`
        -   原文档
            ```纯文本
            版本号  代号  发布时间
            4.10（初始发布版本）
            Warty Warthog  2004-10-20
            5.04
            Hoary Hedgehog  2005-04-08
            5.10
            Breezy Badger  2005-10-13
            6.06 LTS
            Dapper Drake  2006-06-01
            6.10
            Edgy Eft  2006-10-26
            7.04
            Feisty Fawn  2007-04-19
            7.10
            Gutsy Gibbon  2007-10-18
            8.04 LTS
            Hardy Heron  2008-04-24
            8.10
            Intrepid Ibex  2008-10-30
            9.04
            Jaunty Jackalope  2009-04-23
            9.10
            Karmic Koala  2009-10-29
            10.04 LTS
            Lucid Lynx  2010-04-29
            10.10
            Maverick Meerkat  2010-10-10
            11.04（Unity成为默认桌面环境）
            Natty Narwhal  2011-04-28
            11.10
            Oneiric Ocelot  2011-10-13
            12.04 LTS
            Precise Pangolin  2012-04-26
            12.10
            Quantal Quetzal  2012-10-18
            13.04
            Raring Ringtail  2013-04-25
            13.10
            Saucy Salamander  2013-10-17
            14.04 LTS
            Trusty Tahr  2014-04-18
            14.10
            Utopic Unicorn  2014-10-23
            15.04
            Vivid Vervet  2015-04-22
            15.10
            Wily Werewolf  2015-10-23
            16.04 LTS
            Xenial Xerus  2016-04-21
            16.10
            Yakkety Yak  2016-10-20
            17.04
            Zesty Zapus  2017-04-13
            17.10（GNOME成为默认桌面环境）
            Artful Aardvark  2017-10-21
            18.04 LTS
            Bionic Beaver  2018-04-26
            18.10
            Cosmic Cuttlefish  2018-10-18
            19.04
            Disco Dingo  2019-4-19
            19.10
            Eoan Ermine  2019-10-17
            20.04 LTS
            Focal Fossa  2020-04-23
            20.10
            Groovy Gorilla  2020-10-22
            21.04
            Hirsute Hippo  2021-04-22
            ```
    -   示例：行首是数字开头的，在之前添加字符：`Ubuntu `

        匹配：`^([0-9].+)$`

        替换：`Ubuntu $1`
3.  匹配IP地址
    ```python
    ((1[0-9][0-9]\.)|(2[0-4][0-9]\.)|(25[0-5]\.)|([1-9][0-9]\.)|([0-9]\.)){3}((1[0-9][0-9])|(2[0-4][0-9])|(25[0-5])|([1-9][0-9])|([0-9]))
    ```
4.  匹配[MAC](MAC_iq5Wbam7PFQwvTV1zWCWNe.md "MAC")地址：
    ```python
    ((([a-f0-9]{2}:){5})|(([a-f0-9]{2}-){5}))[a-f0-9]{2}
    ```
    -   参考 <[https://blog.csdn.net/momDIY/article/details/79679921](https://blog.csdn.net/momDIY/article/details/79679921 "https://blog.csdn.net/momDIY/article/details/79679921")>

        因为考虑到MAC地址一般有两种格式，使用`-`连接或是`:`连接，于是我稍作改动，改动结果如下
        -   **`/((([a-f0-9]{2}:){5})|(([a-f0-9]{2}-){5}))[a-f0-9]{2}/gi`**
        以上正则表达式就是最终版的MAC地址验证表达式，如果不清楚具体原理可以接着往下看。
        ### 拆解分析
        #### 1. `[a-f0-9]`
        匹配a到f或0到9中的任意一位字符。
        > 匹配的结果例如`2`或`d`。
        #### 2. `[a-f0-9]{2}`
        匹配连续两位的括号中任意字符。
        > 匹配的结果例如`d2`或`ac`。
        #### 3. `[a-f0-9]{2}:`
        连续两位的括号中任意字符再拼接一个`:`(冒号)。
        > 匹配的结果例如`b2:`或`23:`
        #### 4. `([a-f0-9]{2}:)|([a-f0-9]{2}-)`
        在第三步的基础上可以将冒号替换为横杠。
        > 匹配的结果例如`f3:`或`79-`
        #### 5. `(([a-f0-9]{2}:)|([a-f0-9]{2}-)){5}`
        将第四步的结果重复5次。
        > 匹配的结果例如`00-01-6C-06-A6-`或`00:01:6C:06:A6:`
        #### 6. `(([a-f0-9]{2}:)|([a-f0-9]{2}-)){5}[a-f0-9]{2}`
        在第五步的结果上再拼接两个`[A-F0-9]`范围内的两个字符
        > 匹配的结果例如`00-01-6C-06-A6-29`或`00:01:6C:06:A6:29`
        #### 7. 设置大小写不敏感与全局匹配
        在正则最后加上`/ig`。

        完整的正则表达式也就是：
        #### `/(([a-f0-9]{2}:)|([a-f0-9]{2}-)){5}[a-f0-9]{2}/gi`
        #### 8.解决`AA:BB-CC:DD:EE-FF`这类符号混用也能通过验证的问题
        根据评论区`smsra`大佬的提醒，第7步的正则无法剔除`AA:BB-CC:DD:EE-FF`这类·-·与‘:’混用的脏数据，因此稍作改动，将重复匹配5次这一操作分别作用于`([a-f0-9]{2}:)`与`([a-f0-9]{2}-)`。最终正则如下：
        ```bash
        /((([a-f0-9]{2}:){5})|(([a-f0-9]{2}-){5}))[a-f0-9]{2}/gi
        ```
        ## END
5.  示例：删除(去除)文件中的中文(行内匹配)
    -   示例：([\[Linux\]sed](\[Linux]sed_k3UmJRASAQ3DbU8cr1Gabt.md "\[Linux]sed"))删除文件中所有中文：`LANG=C sed -rn "s/[\x81-\xFE]+//g" regexp.txt `
    -   示例1(实)：去除文件regexp.txt中的中文，使用[\[Linux\]sed](\[Linux]sed_k3UmJRASAQ3DbU8cr1Gabt.md "\[Linux]sed")、[正则表达式](正则表达式_dhBRQ1YUsruvVygsQr12tC.md "正则表达式")：`sed -rn "s#(^/.*)(：.*$)#\1#gp" regexp.txt`
        -   文件内容
            ```纯文本
            ubuntu@VM-16-5-ubuntu:~/myProgram$ cat regexp.txt 
            常用日志目录代表的意思
            /var/log/messages：常规日志消息
            /var/log/boot：系统启动日志
            /var/log/debug：调试日志消息
            /var/log/auth.log：用户登录和身份验证日志
            /var/log/daemon.log：运行squid，ntpd等其他日志消息到这个文件
            /var/log/dmesg：Linux内核环缓存日志
            /var/log/dpkg.log：所有二进制包日志都包括程序包安装和其他信息
            /var/log/faillog：用户登录日志文件失败
            /var/log/kern.log：内核日志文件
            /var/log/lpr.log：打印机日志文件
            /var/log/mail.：所有邮件服务器消息日志文件
            /var/log/mysql.：MySQL服务器日志文件
            /var/log/user.log：所有用户级日志
            /var/log/xorg.0.log：X.org日志文件
            /var/log/apache2/：Apache Web服务器日志文件目录
            /var/log/lighttpd/：Lighttpd Web服务器日志文件目录
            /var/log/fsck/*：fsck命令日志
            /var/log/apport.log：应用程序崩溃报告/日志文件
            /var/log/syslog：系统日志
            /var/log/ufw：ufw防火墙日志
            /var/log/gufw：gufw防火墙日志
            ```
        -   初始方案
            ```纯文本
            ubuntu@VM-16-5-ubuntu:~/myProgram$ LANG=C sed -rn "s#(^/.*：)(.*$)#\1#gp" regexp.txt  用反向应用筛选
            /var/log/messages：
            /var/log/boot：
            /var/log/debug：
            /var/log/auth.log：
            /var/log/daemon.log：
            /var/log/dmesg：
            /var/log/dpkg.log：
            /var/log/faillog：
            /var/log/kern.log：
            /var/log/lpr.log：
            /var/log/mail.：
            /var/log/mysql.：
            /var/log/user.log：
            /var/log/xorg.0.log：
            /var/log/apache2/：
            /var/log/lighttpd/：
            /var/log/fsck/*：
            /var/log/apport.log：
            /var/log/syslog：
            /var/log/ufw：
            /var/log/gufw：
            ```
            ```纯文本
            ubuntu@VM-16-5-ubuntu:~/myProgram$ sed -rn "s#(^/.*：)(.*$)#\1#gp" regexp.txt  | sed 's#：##'       # 用管道去除冒号
            /var/log/messages
            /var/log/boot
            /var/log/debug
            /var/log/auth.log
            /var/log/daemon.log
            /var/log/dmesg
            /var/log/dpkg.log
            /var/log/faillog
            /var/log/kern.log
            /var/log/lpr.log
            /var/log/mail.
            /var/log/mysql.
            /var/log/user.log
            /var/log/xorg.0.log
            /var/log/apache2/
            /var/log/lighttpd/
            /var/log/fsck/*
            /var/log/apport.log
            /var/log/syslog
            /var/log/ufw
            /var/log/gufw
            ```
        -   优化方案
            ```纯文本
            ubuntu@VM-16-5-ubuntu:~/myProgram$ sed -rn "s#(^/.*)(：.*$)#\1#gp" regexp.txt     
            /var/log/messages
            /var/log/boot
            /var/log/debug
            /var/log/auth.log
            /var/log/daemon.log
            /var/log/dmesg
            /var/log/dpkg.log
            /var/log/faillog
            /var/log/kern.log
            /var/log/lpr.log
            /var/log/mail.
            /var/log/mysql.
            /var/log/user.log
            /var/log/xorg.0.log
            /var/log/apache2/
            /var/log/lighttpd/
            /var/log/fsck/*
            /var/log/apport.log
            /var/log/syslog
            /var/log/ufw
            /var/log/gufw
            ```
6.  反向匹配`(?<=pattern)`：匹配中间的空格
    ```纯文本
    (?<=(\t\w*))\-(?=(\w*\t))

    (?<=\t\w*)\-(?=\w*\t)

    ```
    1.  示例：匹配空格：匹配数字字母中的的空行：`(?<=[\w]) (?=[\w])` \[`\w``(?<=pattern)`]
    2.  示例：匹配空格：数字字母与井号之间的空格 `(?<=\w\b) (?=#)` \[`\w``(?<=pattern)`]
    3.  示例：匹配空格：匹配汉字中间的空格 `(?<=[\u4e00-\u9fa5]) (?=[\u4e00-\u9fa5])`  \[`\w``(?<=pattern)`]
    4.  示例：匹配空格：在小写字母与`>`符号与大写字母之间的公合，匹配两个以上的空格`(?<=[a-z>]) {2,}(?=[A-Z])`  \[`{n,}`]

        应用场景：在Linux帮助文档中
    5.  示例：匹配中间的课程名称
        -   样本
            ```sql
            "part":"02-安装部署-VMware中安装CentOS7.4"
            "part":"03-安装部署-让虚拟机可以联网"
            "part":"04-安装部署-使用XShell给虚拟机配置静态ip"
            "part":"05-安装部署-虚拟机不能上网简单排错"
            "part":"06-安装部署-Nginx四个发行版本简单介绍"
            "part":"07-安装部署-Nginx在CentOS7中编译安装成系统服务"
            "part":"08-基本使用-Nginx的目录结构 在线编辑默认页"
            "part":"09-基本使用-Nginx多进程模型和基本请求流程"
            "part":"10-基本使用-Nginx.conf 最小配置解析"
            "part":"11-基本使用-虚拟主机实战介绍"
            "part":"12-基本使用-浏览器、Nginx与http协议"
            "part":"13-基本使用-虚拟主机原理"
            "part":"14-基本使用-使用host文件解析域名"
            "part":"15-基本使用-公网域名配置与泛域名解析实战"
            "part":"16-基本使用-Nginx虚拟主机域名配置"
            "part":"17-基本使用-servername的多种匹配方式"
            "part":"18-基本使用-基于域名的几种互联网企业需求解析"
            "part":"19-基本使用-反向代理与负载均衡实战介绍"
            "part":"20-基本使用-Nginx隧道式模型 网关、代理与反向代理"
            "part":"21-基本使用-Nginx反向代理在企业中的应用场景"
            "part":"22-基本使用-什么是负载均衡"
            "part":"23-基本使用-反向代理到外网与内网主机的配置"
            "part":"24-基本使用-负载均衡基本配置"
            "part":"25-基本使用-负载均策略之权重、down、backup"
            "part":"26-基本使用-负载均策略之ip_hash、fair、leastconn与无状态回话解决方案"
            "part":"27-基本使用-动静分离的原理与使用场景"
            "part":"28-基本使用-动静分离配置"
            "part":"29-基本使用-使用正则配置动静分离"
            "part":"30-基本使用-URLRewrite 伪静态配置"
            "part":"31-基本使用-网关的概念、伪静态同时负载均衡"
            "part":"32-基本使用-防盗链与http的referer"
            "part":"33-基本使用-防盗链基本配置与none"
            "part":"34-基本使用-使用curl测试防盗链"
            "part":"35-基本使用-企业实战-盗链资源返回页面或提示图片"
            "part":"36-基本使用-高可用场景及解决方案"
            "part":"37-基本使用-最快速度搞定keepalived"
            "part":"38-基本使用-不安全的Http协议"
            "part":"39-基本使用-非对称加密算法原理"
            "part":"40-基本使用-同样不安全的非对称加密算法"
            "part":"41-基本使用-ca机构参与保证互联网安全"
            "part":"42-基本使用-自签名介绍"
            "part":"43-线上实战-购买域名流程"
            "part":"44-线上实战-购买vps流程"
            "part":"45-线上实战-在控制台修改vps密码"
            "part":"46-线上实战-安装LNMP环境防火墙配置"
            "part":"47-线上实战-修改Nginx默认页"
            "part":"48-线上实战-解析域名到主机"
            "part":"49-线上实战-在线申请证书"
            "part":"50-线上实战-把刚申请的证书配置到Nginx上"
            "part":"51-线上实战-安装Discuz与协议自动跳转"
            "part":"052-Nginx高级篇介绍"
            "part":"053-通过扩容提升整体吞吐量"
            "part":"054-服务器硬件扩容及存储选型"
            "part":"055-集群中使用Nginx保持会话的特点"
            "part":"056-iphash维持会话特点及配置"
            "part":"057-在nginx中通过URI维持会话"
            "part":"058-在nginx中使用java的cookie负载均衡"
            "part":"059-使用第三方模块平滑升级"
            "part":"060-sticky上游静态服务器会话保持"
            "part":"061-观察baidu的keepalive"
            "part":"062-什么时候使用keepalive"
            "part":"063-在nginx 中关闭keepalive"
            "part":"064-使用charles工具抓包连接状态"
            "part":"065-nginx对客户端keepalive配置详解"
            "part":"066-nginx对上游服务器使用keepalive配置详解"
            "part":"067-Nginx反向代理开关keepalive性能压测对比"
            "part":"068-Tomcat直连与反向代理性能压测对比"
            "part":"069-http报文结构"
            "part":"070-反向代理内存与文件缓冲区核心流程"
            "part":"071-Nginx对客户端的缓冲和限制"
            "part":"072-使用反向代理后无法获取客户端ip地址"
            "part":"073-使用X-Forwarded-For获取真实ip以及思考"
            "part":"074-一些默认有用的header"
            "part":"075-有哪些网站使用了gzip压缩"
            "part":"076-Gzip动态压缩及缺点"
            "part":"077-gzip_static_module与http_gunzip_module"
            "part":"078-gzip_static_module配置说明"
            "part":"079-gunzip_module配置使用"
            "part":"080-Brotli比gzip更好的压缩格式模块化安装"
            "part":"081-Brotli配置"
            "part":"082-淘宝网案例 进一步压缩客户端的请求数"
            "part":"083-Tengine concat模块安装在开源版本Nginx上"
            "part":"084-模拟淘宝网合并请求效果"
            "part":"085-高并发系统资源静态化方案"
            "part":"086-Nginx SSI 服务器端文件合并"
            "part":"087-Nginx SSI服务器端配置选项"
            "part":"088-Nginx SSI模板命令"
            "part":"089-资源静态同步方案介绍"
            "part":"090-使用rsync手动同步源文件"
            "part":"091-增加安全认证及免密登录"
            "part":"092-近时推送方案"
            "part":"093-实时推送源服务器配置"
            "part":"094-rsync的readonly"
            "part":"095-使用inotify监控目录文件变化"
            "part":"096-rsync inotify 自动化脚本"
            "part":"097-什么是多级缓存"
            "part":"098-京东web端浏览器缓存使用情况"
            "part":"099-浏览器的强制缓存与协商缓存"
            "part":"100-Nginx etag lasmodify配置"
            "part":"101-配合使用etag lasmodify cache-control expires"
            "part":"102-浏览器缓存额外需要注意的事项和应用场景"
            "part":"103-cdn实现原理及场景"
            "part":"104-在云服务器安装GEOIP依赖"
            "part":"105-Nginx下GEOIP模块安装"
            "part":"106-线上获取用户归属地实例配置与智能dns对比"
            "part":"107-使用Nginx作为跳板机正向代理服务器配置"
            "part":"108-反向代理缓存proxy_cache配置"
            "part":"109-缓存清理插件编译安装"
            "part":"110-cache_key 与缓存清理"
            "part":"111-nginx的断点续传"
            "part":"112-proxy_cache配置详解"
            "part":"113-nginx内存缓存介绍"
            "part":"114-nginx外置缓存介绍"
            "part":"115-应用缓存与多级缓存整体结构"
            "part":"116-使用strace追踪内核对sendfile缓存调优"
            "part":"117-errorpage使用"
            "part":"118-匿名location和return"
            "part":"119-Nginx+Memcached完整解决方案"
            "part":"120-开源版Nginx中使用redis2-nginx-module连接redis"
            "part":"121-使用Stream模块为mysql集群透明代理"
            "part":"122-QPS限制模块及使用jemeter压测"
            "part":"123-QPS限制中漏桶算法实现及压测"
            "part":"124-limit_req burst与漏桶算法中bucket概念对比"
            "part":"125-什么是令牌桶算法"
            "part":"126-传输带宽限制"
            "part":"127-客户端并发数限制"
            "part":"128-互联网公司日志的使用场景"
            "part":"129-日志内存缓冲区"
            "part":"130-日志压缩解压缩与json格式输出"
            "part":"131-error日志与日志分割"
            "part":"132-upstream被动式重试机制"
            "part":"133-主动健康检查使用tengine模块"
            "part":"134-Lua luajit nginx openresty关系及开发工具介绍"
            "part":"135-lua基础语法"
            "part":"136-Openresty安装及测试lua代码"
            "part":"137-获取系统变量及参数"
            "part":"138-lua自定义函数、lrucache、shared_dict"
            "part":"139-Openresty连接redis"
            "part":"140-Openresty连接mysql"
            "part":"141-在Openresty中使用模板引擎"
            "part":"142-redis+mysql+模板引擎示例"

            ```
        -   正则匹配：`(?<="part":").*(?=")`
        -   匹配的内容
            ```sql
            02-安装部署-VMware中安装CentOS7.4
            03-安装部署-让虚拟机可以联网
            04-安装部署-使用XShell给虚拟机配置静态ip
            05-安装部署-虚拟机不能上网简单排错
            06-安装部署-Nginx四个发行版本简单介绍
            07-安装部署-Nginx在CentOS7中编译安装成系统服务
            08-基本使用-Nginx的目录结构 在线编辑默认页
            09-基本使用-Nginx多进程模型和基本请求流程
            10-基本使用-Nginx.conf 最小配置解析
            11-基本使用-虚拟主机实战介绍
            12-基本使用-浏览器、Nginx与http协议
            13-基本使用-虚拟主机原理
            14-基本使用-使用host文件解析域名
            15-基本使用-公网域名配置与泛域名解析实战
            16-基本使用-Nginx虚拟主机域名配置
            17-基本使用-servername的多种匹配方式
            18-基本使用-基于域名的几种互联网企业需求解析
            19-基本使用-反向代理与负载均衡实战介绍
            20-基本使用-Nginx隧道式模型 网关、代理与反向代理
            21-基本使用-Nginx反向代理在企业中的应用场景
            22-基本使用-什么是负载均衡
            23-基本使用-反向代理到外网与内网主机的配置
            24-基本使用-负载均衡基本配置
            25-基本使用-负载均策略之权重、down、backup
            26-基本使用-负载均策略之ip_hash、fair、leastconn与无状态回话解决方案
            27-基本使用-动静分离的原理与使用场景
            28-基本使用-动静分离配置
            29-基本使用-使用正则配置动静分离
            30-基本使用-URLRewrite 伪静态配置
            31-基本使用-网关的概念、伪静态同时负载均衡
            32-基本使用-防盗链与http的referer
            33-基本使用-防盗链基本配置与none
            34-基本使用-使用curl测试防盗链
            35-基本使用-企业实战-盗链资源返回页面或提示图片
            36-基本使用-高可用场景及解决方案
            37-基本使用-最快速度搞定keepalived
            38-基本使用-不安全的Http协议
            39-基本使用-非对称加密算法原理
            40-基本使用-同样不安全的非对称加密算法
            41-基本使用-ca机构参与保证互联网安全
            42-基本使用-自签名介绍
            43-线上实战-购买域名流程
            44-线上实战-购买vps流程
            45-线上实战-在控制台修改vps密码
            46-线上实战-安装LNMP环境防火墙配置
            47-线上实战-修改Nginx默认页
            48-线上实战-解析域名到主机
            49-线上实战-在线申请证书
            50-线上实战-把刚申请的证书配置到Nginx上
            51-线上实战-安装Discuz与协议自动跳转
            052-Nginx高级篇介绍
            053-通过扩容提升整体吞吐量
            054-服务器硬件扩容及存储选型
            055-集群中使用Nginx保持会话的特点
            056-iphash维持会话特点及配置
            057-在nginx中通过URI维持会话
            058-在nginx中使用java的cookie负载均衡
            059-使用第三方模块平滑升级
            060-sticky上游静态服务器会话保持
            061-观察baidu的keepalive
            062-什么时候使用keepalive
            063-在nginx 中关闭keepalive
            064-使用charles工具抓包连接状态
            065-nginx对客户端keepalive配置详解
            066-nginx对上游服务器使用keepalive配置详解
            067-Nginx反向代理开关keepalive性能压测对比
            068-Tomcat直连与反向代理性能压测对比
            069-http报文结构
            070-反向代理内存与文件缓冲区核心流程
            071-Nginx对客户端的缓冲和限制
            072-使用反向代理后无法获取客户端ip地址
            073-使用X-Forwarded-For获取真实ip以及思考
            074-一些默认有用的header
            075-有哪些网站使用了gzip压缩
            076-Gzip动态压缩及缺点
            077-gzip_static_module与http_gunzip_module
            078-gzip_static_module配置说明
            079-gunzip_module配置使用
            080-Brotli比gzip更好的压缩格式模块化安装
            081-Brotli配置
            082-淘宝网案例 进一步压缩客户端的请求数
            083-Tengine concat模块安装在开源版本Nginx上
            084-模拟淘宝网合并请求效果
            085-高并发系统资源静态化方案
            086-Nginx SSI 服务器端文件合并
            087-Nginx SSI服务器端配置选项
            088-Nginx SSI模板命令
            089-资源静态同步方案介绍
            090-使用rsync手动同步源文件
            091-增加安全认证及免密登录
            092-近时推送方案
            093-实时推送源服务器配置
            094-rsync的readonly
            095-使用inotify监控目录文件变化
            096-rsync inotify 自动化脚本
            097-什么是多级缓存
            098-京东web端浏览器缓存使用情况
            099-浏览器的强制缓存与协商缓存
            100-Nginx etag lasmodify配置
            101-配合使用etag lasmodify cache-control expires
            102-浏览器缓存额外需要注意的事项和应用场景
            103-cdn实现原理及场景
            104-在云服务器安装GEOIP依赖
            105-Nginx下GEOIP模块安装
            106-线上获取用户归属地实例配置与智能dns对比
            107-使用Nginx作为跳板机正向代理服务器配置
            108-反向代理缓存proxy_cache配置
            109-缓存清理插件编译安装
            110-cache_key 与缓存清理
            111-nginx的断点续传
            112-proxy_cache配置详解
            113-nginx内存缓存介绍
            114-nginx外置缓存介绍
            115-应用缓存与多级缓存整体结构
            116-使用strace追踪内核对sendfile缓存调优
            117-errorpage使用
            118-匿名location和return
            119-Nginx+Memcached完整解决方案
            120-开源版Nginx中使用redis2-nginx-module连接redis
            121-使用Stream模块为mysql集群透明代理
            122-QPS限制模块及使用jemeter压测
            123-QPS限制中漏桶算法实现及压测
            124-limit_req burst与漏桶算法中bucket概念对比
            125-什么是令牌桶算法
            126-传输带宽限制
            127-客户端并发数限制
            128-互联网公司日志的使用场景
            129-日志内存缓冲区
            130-日志压缩解压缩与json格式输出
            131-error日志与日志分割
            132-upstream被动式重试机制
            133-主动健康检查使用tengine模块
            134-Lua luajit nginx openresty关系及开发工具介绍
            135-lua基础语法
            136-Openresty安装及测试lua代码
            137-获取系统变量及参数
            138-lua自定义函数、lrucache、shared_dict
            139-Openresty连接redis
            140-Openresty连接mysql
            141-在Openresty中使用模板引擎
            142-redis+mysql+模板引擎示例

            ```
    6.  示例：匹配b站链接中的视频ID(bvid)：`(?<=/)[\w]{12}(?=.)` \[`\w``(?<=pattern)``{n}`]
7.  匹所有中文|汉字&#x20;
    1.  示例：匹配汉字文字： `[\u4e00-\u9fa5]`
    2.  示例：匹配非汉字字符： `[^\u4e00-\u9fa5]` \[`[^]`]
    3.  示例：匹配双字节字符（汉字、中文标点符号等）： `[^\x00-\xff]`
    4.
8.  示例：[\[NAS\]qBittorrent](\[NAS]qBittorrent_p3CgynHAHUzgDXr8ooGxfL.md "\[NAS]qBittorrent")中[RSS](RSS_6ihfkq7gRcvk9AhneAw1sk.md "RSS")订阅自动下载正则匹配标题
    `\d{3}`数字匹配三次

    [test.txt](../file/test_bCd91y7r2P.txt "test.txt")
    -   眷思量下载
        ```html
        \[Gm-Team\]\[国漫\]\[眷思量\]\[The Island of Siliang\]\[2021\]\[\d\d\]\[AVC\]\[GB\]\[1080P\]
        ```
        ![](../image/image_NyXPToNvqZ.png)
    -   斗罗大陆
        ```html
        ^.*\[GM-Team\].*\[斗罗大陆\].*\[\d{3}\].*\]$
        ```
        ![](../image/image_AD_oQQJYX2.png)
9.  示例：[去除所有括号以及括号中的内容](https://blog.csdn.net/Searchin_R/article/details/90769235 "去除所有括号以及括号中的内容")
    ```javascript
    \\<.*?>
    ```
    [^符号的用法](^符号的用法_gk4dUSGm4AkoprnHHvHNcK.md "^符号的用法")：下方`^`为取反用法
    ```javascript
    \([^\)]*?\)
    ```
10. 示例：只匹配所有的单括号(如中括号)
    ```javascript
    \[|\]
    ```
11. 示例：[secureCRT自动记录日志配置](secureCRT自动记录日志配置_dyXeFLMrx2GZ9DdGedagbj.md "secureCRT自动记录日志配置")中的log内容去除时间；正则
    ```纯文本
    \[\d\d\:\d\d\:\d\d\]
    ```

