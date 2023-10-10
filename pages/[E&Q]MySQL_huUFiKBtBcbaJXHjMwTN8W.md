# \[E\&Q]MySQL

-   \[E]\(admin.E040) ModelAdmin must define "search\_fields"

    参考：示例：`ModelAdmin.autocomplete_fields`

    注意点：
    ```javascript
    class LifelogAdmin(admin.ModelAdmin):
    ...
        autocomplete_fields = ['tags']             # use select2 to select user   

    class TagAdmin(admin.ModelAdmin):
         search_fields = ['tag']    # 搜索 


    ...
     admin.site.register(Tag,TagAdmin)
    ```
-   \[E]`ERROR 2002 (HY000): Can't connect to local MySQL server through socket '/var/run/mysqld/mysqld.sock' (2)`

    主要参考：[https://blog.csdn.net/weixin\_45777669/article/details/115671283](https://blog.csdn.net/weixin_45777669/article/details/115671283 "https://blog.csdn.net/weixin_45777669/article/details/115671283")

    排查：服务启动了; 端口正常; 配置文件

    查看mysql.sock文件位置，与配置文件中不同，修改到正确的路径，注释原有配置
    ```python
    find / -name '*.sock'

    /var/lib/mysql/mysql.sock

    ```
    ```python
    [client]
    #socket=/var/run/mysqld/mysqld.sock
    socket=/var/lib/mysql/mysql.sock
    [mysqld]
    #socket=/var/run/mysqld/mysqld.sock
    socket=/var/lib/mysql/mysql.sock

    ```

-   MySQL 函数 向字符串后面添加字符串|MYSQL 在某字段的后面追加字符串
    ```javascript
    SELECT songer,song,tag FROM person.favormusic WHERE songer = '测试';

    UPDATE person.favormusic SET tag = CONCAT(tag,'钢琴2,') WHERE songer = '测试' 
    ```
    ![](../image/image_nBswRkeV2H.png)
-   \[Q][MySQL 数据库怎样把一个表的数据插入到另一个表](https://blog.51cto.com/yangfei520/381568 "MySQL 数据库怎样把一个表的数据插入到另一个表")

    web开发中，我们经常需要将一个表的数据插入到另外一个表，有时还需要指定导入字段，设置只需要导入目标表中不存在的记录，虽然这些都可以在程序中拆分成简单sql来实现，但是用一个sql的话，会节省大量代码。下面我以mysql数据库为例分情况一一说明：

    两张表：insertTest和insertTest2，前者中有测试数据

    create table insertTest(id int(4),name varchar(12)); &#x20;
    insert into insertTest values(100,'liudehua'); &#x20;
    insert into insertTest values(101,'zhourunfa'); &#x20;
    insert into insertTest values(102,'zhouhuajian');

    **1.如果2张表的字段一致，并且希望插入全部数据，可以用这种方法：**

    *INSERT INTO 目标表 SELECT \* FROM 来源表;*

    insert into insertTest select \* from insertTest2;

    **2.如果只希望导入指定字段，可以用这种方法：**

    *INSERT INTO 目标表 (字段1, 字段2, ...) SELECT 字段1, 字段2, ... FROM 来源表;*

    注意字段的顺序必须一致。

    insert into insertTest2(id) select id from insertTest2;

    **3.如果您需要只导入目标表中不存在的记录，可以使用这种方法：**

    *INSERT INTO 目标表*  

    *(字段1, 字段2, ...)*  

    *SELECT 字段1, 字段2, ...*  

    *FROM 来源表*  

    *WHERE not exists (select \* from 目标表*  

    *where 目标表.比较字段 = 来源表.比较字段);* 

    1>.插入多条记录：

    insert into insertTest2(id,name)select id,namefrom insertTestwhere not exists (select \* from insertTest2where [insertTest2.id=insertTest.id](http://insertTest2.id=insertTest.id "insertTest2.id=insertTest.id"));

    2>.插入一条记录：

    insert into insertTest    (id, name)    SELECT 100, 'liudehua'    FROM dual    WHERE not exists (select \* from insertTest    where [insertTest.id](http://insertTest.id "insertTest.id") = 100);

    使用 dual 作表名，select 语句后面直接跟上要插入的字段的值。
-   SQL 错误 \[3167] \[HY000]: The 'INFORMATION\_SCHEMA.GLOBAL\_STATUS' [feature](feature_85wkx2ibSQF9Kd63DhDz54.md "feature") is disabled; see the documentation for 'show\_compatibility\_56'
    ```sql
    SELECT * FROM information_schema.GLOBAL_STATUS gs ;
    ```
-   Attribute img was changed but it hasn't associated unique key

    ![](../image/image_q3tZRczwKr.png)
-   [operand](operand_hxVEXvrwRLWRjQqQvmrRZ6.md "operand") [should](should_dySSEXsenxvhsmhy5E6Rv1.md "should") [contain](contain_tP2gCVr6m6J4Z6jyKRdzim.md "contain") 1 [column](column_fppTGpGASrAEBfRjPrgyU8.md "column")(s)


-   错误ERROR1046(3D000): No database selected

    ![](../image/image_ezcBbwIBUZ.png)

    ![](../image/image_wfcRxZI-6m.png)
-   &#x20;ERROR: Can't initialize batch\_readline - may be the input source is a directory or a block device&#x20;

    原因：路径打错了
    ```纯文本
    [root@VM-16-5-centos ~]# mysql -u root -p sgk_phpinfo<./sgdb/phpinfo.me
    Enter password: 
    ERROR: Can't initialize batch_readline - may be the input source is a directory or a block device.
    ```
-   \[Q][MySQL](MySQL_pPMN84zaKJANNFTyjDjZiX.md "MySQL") 与 [SQL](SQL_69pQjm3Twb3qB6d1CQdg1u.md "SQL") 什么关系

    MySQL所使用的 SQL语言是用于访问 数据库 的最常用标准化语言。

    MySQL是数据库软件，使用SQL语言来查询数据库SQL是一种用于操作数据库的语言MySQL是市场上第一个可用的开源数据库之一SQL用于访问，更新和操作数据库中的数据MySQL是一种RDBMS，它允许保持数据库中存在的数据SQL是结构化查询语言MySQL是一个使用MYSQL存储，检索，修改和管理数据库的RDBMSSQL是一种查询语言，而MYSQL是数据库软件



