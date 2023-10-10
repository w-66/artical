# \[Shell]流程控制

[\[Shell\]for|for int](<\[Shell]for-for int_5ravx7fNNP9USjCRra6MEi.md> "\[Shell]for|for int")

<https://www.jb51.net/article/221909.htm>

[\[shell\]if](\[shell]if_dsbF677qnnV83JaPjzEn1K.md "\[shell]if")

-   \[Shell]while
    ```纯文本
    while循环用于不知道循环次数的场景，注意有退出条件
    while [ 条件 ];do
      statement
      .....
    done

    ```



-   1.文件/文件夹(目录)判断

    `[-e]`

    `[ -e FILE ] `如果 指定的文件或目录存在时返回为真。
    ```powershell
    [ -a FILE ] 如果 FILE 存在则为真。文件是否存在 
    [ -d DIR  ] 如果 FILE 存在且是一个目录则为真。
    [ -e FILE ] 如果 指定的文件或目录存在时返回为真。
    [ -f FILE ] 如果 FILE 存在且是一个普通文件则为真。测试是否普通文件
    [ -r FILE ] 如果 FILE 存在且是可读的则为真。
    [ -w FILE ] 如果 FILE存在且是可写的则为真。
    [ -x FILE ] 如果 FILE 存在且是可执行的则为真。
    [ -h FILE ] 测试是否符号链接文件

    [ -b FILE ] 如果 FILE 存在且是一个块特殊文件则为真。测试是否块设备文件
    [ -c FILE ] 如果 FILE 存在且是一个字特殊文件则为真。测试是否字符设备文件
    [ -g FILE ] 如果 FILE 存在且已经设置了SGID则为真。
    [ -k FILE ] 如果 FILE 存在且已经设置了粘制位则为真。
    [ -p FILE ] 如果 FILE 存在且是一个名字管道(F如果O)则为真。
    [ -s FILE ] 如果 FILE 存在且大小不为0则为真。
    [ -t FD   ] 如果文件描述符 FD 打开且指向一个终端则为真。
    [ -u FILE ] 如果 FILE 存在且设置了SUID (set user ID)则为真。
    [ -O FILE ] 如果 FILE 存在且属有效用户ID则为真。
    [ -G FILE ] 如果 FILE 存在且属有效用户组则为真。
    [ -L FILE ] 如果 FILE 存在且是一个符号连接则为真。测试是否是符号链接文件
    [ -N FILE ] 如果 FILE 存在 and has been mod如果ied since it was last read则为真。
    [ -S FILE ] 如果 FILE 存在且是一个套接字则为真。
    [ FILE1 -nt FILE2 ] 如果 FILE1 has been changed more recently than FILE2, or 如果 FILE1 exists and FILE2 does not则为真。
    [ FILE1 -ot FILE2 ] 如果 FILE1 比 FILE2 要老, 或者 FILE2 存在且 FILE1 不存在则为真。
    [ FILE1 -ef FILE2 ] 如果 FILE1 和 FILE2 指向相同的设备和节点号则为真。
    ```
-   字符串判断

    `[ -z STRING ]`

    如果STRING的长度为零则为真 ，即判断是否为空，空即是真；检测字符是否为空，空则真，不空则假    如: \[ -z "" ]为真空则为真


    `[ -n STRING ]`

    如果STRING的长度非零则为真 ，即判断是否为非空，非空即是真；检测字符是否不空，不空则真，不空则假


    `[ STRING1 ]`

    &#x20;如果字符串不为空则返回为真,与`[ -n STRING ]`类似

    `[ STRING1 == STRING2 ]`&#x20;

    如果两个字符串相同则返回为真


    `[ STRING1 != STRING2 ] `

    如果字符串不相同则返回为真


    `[ STRING1 < STRING2 ]`&#x20;

    如果 “STRING1”字典排序在“STRING2”前面则返回为真。

    `[ STRING1 > STRING2 ]`&#x20;

    如果 “STRING1”字典排序在“STRING2”后面则返回为真。

    `[[  ]]`

    字符相比较大小用\[\[  ]]，比的是第一个字母（a-zA-Z）都是大写或者都是小写比较ascii值越大则越大，有大写又有小写则A>a B>b   但是A不大于b的情况
    > 「P.S」`$?`
    ```纯文本
    [root@slave02 ~]# [[ "A" < "B" ]]
    [root@slave02 ~]# echo $?
    0
    [root@slave02 ~]# [[ "a" < "b" ]]
    [root@slave02 ~]# echo $?
    0
      
    ```
-   数值判断

`[INT1 -eq INT2]`INT1和INT2两数相等返回为真 ,= （equal）


`[INT1 -ne INT2]`INT1和INT2两数不等返回为真 ,<>（unequal）


`[INT1 -gt INT2]`INT1大于INT2返回为真 ,>（greater than）


`[INT1 -ge INT2]`INT1大于等于INT2返回为真,>=


`[INT1 -lt INT2]`INT1小于INT2返回为真 ,<（less than）


`[INT1 -le INT2]`INT1小于等于INT2返回为真,<=

`[INT1 -eq INT2]`

`[INT1 -ne INT2]`

`[INT1 -gt INT2]`

`[INT1 -ge INT2]`

`[INT1 -lt INT2]`

`[INT1 -le INT2]`

-   4.逻辑判断
    ```bash
    [ ! EXPR ] 逻辑非，如果 EXPR 是false则返回为真。
    [ EXPR1 -a EXPR2 ] 逻辑与，如果 EXPR1 and EXPR2 全真则返回为真。
    [ EXPR1 -o EXPR2 ] 逻辑或，如果 EXPR1 或者 EXPR2 为真则返回为真。
    [ ] || [ ] 用OR来合并两个条件
    [ ] && [ ] 用AND来合并两个条件
    ```





#### 示例

-   示例1：写一个脚本，输入三个数字进行相应的加减乘除
    ```纯文本
    [root@slave02 ~]# cat script01.sh 
    #!/bin/bash
    a=$1
    b=$2
    c=$3
    num1=$[$a+$b+$c]
    num2=$[$a-$b-$c]
    num3=$[$a*$b*$c]
    echo "$a + $b + $c" = $num1
    echo "$a - $b - $c" = $num2
    echo "$a * $b * $c" = $num3
    awk "BEGIN{printf \"$a/$b/$c=%.2f\n\",$a/$b/$c}"
    [root@slave02 ~]# source script01.sh 100 10 9
    100 + 10 + 9 = 119
    100 - 10 - 9 = 81
    100 * 10 * 9 = 9000
    100/10/9=1.11

    ```
-   示例2：猜数字游戏
    ```纯文本
    [root@master ~]# cat test03.sh 
    #!/bin/bash
    nums=99
    read -p "please enter a number: " num
    if [ $num -gt $nums ];then
            echo "数字大了"
    elif [ $num -lt $nums ];then
            echo "数字小了"
    else
            echo "猜对"
    fi        
    [root@master ~]# . test03.sh 
    please enter a number: 10
    数字小了
    [root@master ~]# . test03.sh
    please enter a number: 100
    数字大了
    [root@master ~]# . test03.sh
    please enter a number: 99
    猜对

    ```
-   示例3：写一个脚本，让nginx服务设置开机自启
    ```纯文本
    #$0是nginx本身 $1是变量对应着下面的start|stop|restart|status
    [root@192 init.d]# pwd
    /etc/init.d
    [root@192 init.d]# cat nginx 
    #!/bin/bash
    case $1 in
            'start')
              /usr/local/nginx/sbin/nginx
              ;;
            'stop')
              /usr/local/nginx/sbin/nginx -s stop
              ;;
            'restart')
            /usr/local/nginx/sbin/nginx -s stop
            /usr/local/nginx/sbin/nginx
              ;;
            'status')
              num=$(ps -ef |grep -v 'grep'|grep -c nginx:)
              if [ $num -eq 0 ];then
                     echo "nginx is stoped" 
              else
                     echo "nginx is running"
              fi
              ;;
            *)
                  echo "Usage: service $0 start|stop|restart|status"
              ;;          
    esac
        #当判断有nginx进程数量则认为开启服务，否则认为服务开启失败

    ```
-   示例4：利用for循环，创建user序号1-100的用户
    ```纯文本
    #创建用户user1-100
    [root@master ~]# cat test05.sh 
    #!/bin/bash
    for (( i=1;i<=100;i++));do
            useradd user$i
            id user$i &>/dev/null
            if [ $? -eq 0 ];then  #只要判断用户成功，$?才会显示0，显示0则代表执行下一条命令，否则显示user以及存在
                    echo "success"
            else  
                echo "user is exis"    
            fi
    done

    ```
-   示例：利用while循环，计算1+2…100的值 \[\[Shell]while`[INT1 -le INT2]`]
    ```python
    #!/bin/bash
    s=0          # 初始值0
    i=1          # 判断的数值，最终到100停止
    while [ $i -le 100 ];do
    s=$[$s+$i]       
    i=$[$i+1]            #自增加数
    done
    echo $s
    ```
    ```纯文本
    [root@slave02 ~]# source which.sh 
    5050

    ```
-   示例：while循环：一直循环 ; 指定循环次数 \[\[Shell]while,[\[Linux\]sleep](\[Linux]sleep_cEe4RXNmBreD9R4iQjGYDi.md "\[Linux]sleep"),`$()`]&#x20;

    一直循环&#x20;
    ```python
    #!/bin/bash
    while :    #冒号表述死循环 同while (true)
    do
        ls /etc
        sleep 5
    done
    ```
    循环指定次数
    ```python
    #!/bin/bash
    n=0
    while (($n<10))
    do
        ls /etc
         n=$((n+1))
        sleep 5
    done
    ```
-   示例6.apache简单的一个编译部署脚本
    ```纯文本
    1.一般项目或者脚本，文件，放在相应的位置里，方便查找
    [root@slave02 tmp]# pwd
    /tmp
    [root@slave02 tmp]# ls
    apache
    [root@slave02 apache]# ls
    install_apache.sh  soft
    [root@slave02 soft]# ls
    apr-1.7.0.tar.bz2   apr-util-1.6.1.tar.bz2    httpd-2.4.48.tar.bz2  httpd.service
    [root@slave02 apache]# cat install_apache.sh #!/bin/bash echo "欢迎使用此脚本" apachedir=/usr/local/apache if [ $UID -ne 0 ];then
            echo "伙计，请使用管理员身份运行"
    fi
    echo "正在安装依赖包..."
    yum -y install epel-release  bzip2 "@Development Tools"  &>/dev/null
    yum -y install openssl-devel pcre-devel expat-devel libtool gcc gcc-c++ make  &>/dev/null
    id apache &>/dev/null
    if [ $? -ne 0 ];then
            useradd -r -M -s /sbin/nologin apache
    fi
    cd /tmp/apache/soft/
    tar -xf apr-1.7.0.tar.bz2
    tar -xf apr-util-1.6.1.tar.bz2
    tar -xf  httpd-2.4.48.tar.bz2
    sed -i '/ $RM "$cfgfile"/d' apr-1.7.0/configure
    echo "正在编译安装apr，请听听歌放松放松......." 
    cd apr-1.7.0/
    [ ! -d /usr/local/apr ]
    if [ $? -eq 0 ];then
            ./configure --prefix=/usr/local/apr && make && make install &>/dev/null
    else
            echo "apr已经安装"
    fi
    cd ../apr-util-1.6.1/
    [ ! -d /usr/local/apr-util ]
    if [ $? -eq 0 ];then
            ./configure --prefix=/usr/local/apr-util --with-apr=/usr/local/apr && make && make install &/dev/null
    else
            echo "apr-util已经安装"
    fi
    cd ../httpd-2.4.48/
    [ ! -d /usr/local/apache/ ]
    if [ $? -eq 0 ];then
    ./configure --prefix=$apachedir \
            --sysconfdir=/etc/httpd24 \
            --enable-so \
            --enable-ssl \
            --enable-cgi \
            --enable-rewrite \
            --with-zlib \
            --with-pcre \
            --with-apr=/usr/local/apr \
            --with-apr-util=/usr/local/apr-util/ \
            --enable-modules=most \
            --enable-mpms-shared=all \
            --with-mpm=prefork
            make && make install &>/dev/null
    else
            echo "httpd已经安装"
    fi
    cd
    #有影响的加判断，没影响的忽略
    echo "export PATH=$apachedir/bin:\$PATH"   > /etc/profile.d/httpd.sh
    ln -s $apachedir/include/ /usr/include/apache &>/dev/null
    grep 'apache/man' /etc/man_db.conf   &>/dev/null

    if [ $? -eq 1 ];then
            sed -i "20aMANDATORY_MANPATH   $apachedir/man" /etc/man_db.conf
    else
            echo "apache is help exists"
    fi

    [ ! -f /usr/lib/systemd/system/httpd.service ]
    if  [ $? -eq 0 ];then
            cp /clq/apache/soft/httpd.service /usr/lib/systemd/system/
    else
            echo "已经存在文件跳过"
    fi
    systemctl daemon-reload
    systemctl enable --now httpd
    num02=$(ps -ef |grep -v 'grep'|grep -c httpd)
    if [ $num02 -eq 0 ];then
            echo "httpd自启失败"
    else
            echo "httpd自启成功"
    fi
    echo "欢迎下次使用"                                 
    [root@slave02 apache]# chmod +x install_apache.sh 
    [root@slave02 apache]# source install_apache.sh 
    [root@slave02 apache]# source install_apache.sh 
    欢迎使用此脚本
    正在安装依赖包...
    正在编译安装apr，请听听歌放松放松.......
    apr以及安装
    apr-util以及安装
    httpd已经安装
    apache is help exists
    已经存在文件跳过
    httpd自启成功
    欢迎下次使用
    [root@slave02 ~]# systemctl status httpd.service 
    ● httpd.service - Start http
       Loaded: loaded (/usr/lib/systemd/system/httpd.service; enabled; vendor preset: disabled)
       Active: active (running) since Sat 2021-09-04 17:45:33 CST; 5h 57min ago
     Main PID: 834761 (httpd)
        Tasks: 7 (limit: 5782)
       Memory: 6.3M
       CGroup: /system.slice/httpd.service
               ├─834761 /usr/local/apache/bin/httpd -k start
               ├─835358 /usr/local/apache/bin/httpd -k start
               ├─835359 /usr/local/apache/bin/httpd -k start
               ├─835360 /usr/local/apache/bin/httpd -k start
               ├─835361 /usr/local/apache/bin/httpd -k start
               ├─835362 /usr/local/apache/bin/httpd -k start
               └─836063 /usr/local/apache/bin/httpd -k start
    [root@slave02 ~]# ss -antl
    State         Recv-Q        Send-Q               Local Address:Port               Peer Address:Port        Process        
    LISTEN        0             128                        0.0.0.0:22                      0.0.0.0:*                          
    LISTEN        0             128                              *:80                            *:*                          
    LISTEN        0             128                           [::]:22                         [::]:*   

    ```
