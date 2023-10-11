# 二进制日志|binlog

-   又称：变更日志(update log)

binlog它记录了数据库所有执行的[DDL](DDL_cYGPR1a56ggmvXhqW7f69P.md "DDL") 和[DML](DML_fDW16vu8c5yqvaNpoMXRXU.md "DML") 等数据库更新事件的语句，但是不包含没有修改任何数据的语句（如数据查询语句`SELECT`、`SHOW`等）。

[二进制日志|binlog](二进制日志-binlog_ejCUGaodeJVCeLkhRYzCyE.md "二进制日志|binlog")主要应用场景：用于数据恢复、用于数据复制

-   用于数据恢复

    因为 Binlog 详细记录了所有修改数据的 SQL，当某一时刻的数据误操作而导致出问题，或者数据库宕机数据丢失，那么可以根据 Binlog 来回放历史数据。
-   用于数据复制

    想要做多机备份的业务，可以去监听当前写库的 Binlog 日志，同步写库的所有更改。

可以说MySQL数据库的数据备份、主备、主主、 主从都离不开binlog， 需要依靠binlog来同步数据，保证数据一致性。



![](../image/image_XSpfzmBFG3.png)

版本之间的区别：MySQL5.7 GA默认是关闭的; MySQL8.0默认是开启的 \[﻿`log_bin`]

***

-   `binlog.000001
    binlog.000002
    binlog.000003
    binlog.000004
    binlog.000005
    binlog.000006
    binlog.000007
    binlog.000008
    binlog.000009
    binlog.000010`在每次重启MySQL服务时，将创建新的binlog文件&#x20;

***

## binlog相关变量

-   [二进制日志|binlog](二进制日志-binlog_ejCUGaodeJVCeLkhRYzCyE.md "二进制日志|binlog")相关变量`[mysqld]`
    -   `log_bin`：[二进制日志|binlog](二进制日志-binlog_ejCUGaodeJVCeLkhRYzCyE.md "二进制日志|binlog")开关
        -   版本之间的区别：MySQL5.7 GA默认是关闭的; MySQL8.0默认是开启的 \[﻿`log_bin`]
    -   `log_bin_basename`：[二进制日志|binlog](二进制日志-binlog_ejCUGaodeJVCeLkhRYzCyE.md "二进制日志|binlog")存储路径 <示例：`binlog.000001
        binlog.000002
        binlog.000003
        binlog.000004
        binlog.000005
        binlog.000006
        binlog.000007
        binlog.000008
        binlog.000009
        binlog.000010`>
        -   `binlog.000001
            binlog.000002
            binlog.000003
            binlog.000004
            binlog.000005
            binlog.000006
            binlog.000007
            binlog.000008
            binlog.000009
            binlog.000010`在每次重启MySQL服务时，将创建新的binlog文件&#x20;
    -   `log_bin_index`：[二进制日志|binlog](二进制日志-binlog_ejCUGaodeJVCeLkhRYzCyE.md "二进制日志|binlog")的索引 <示例：`binlog.index`>
    -   `sql_log_bin`：变更记录到[二进制日志|binlog](二进制日志-binlog_ejCUGaodeJVCeLkhRYzCyE.md "二进制日志|binlog")
    -   `log_bin_trust_function_creators`是否允许创建存MySQL存储函数<0> 全局系统变量
        -   0
        -   1
        -   默认关闭的原因是在主从复制数据不一致
        -   原因： [空降](https://www.bilibili.com/video/BV1iq4y1u7vj?p=131\&spm_id_from=pageDriver\&vd_source=d87be07aa170c6f76058fa2663ca0da0\&t=398.9 "空降")
            -   报错原因值=0表示不信任函数，不deterministic ;不能创建存储函数

                ![](../image/image_CMMZ46VyYS.png)

                错误代码：1418This function has none of DETERMINISTIC， NO SQL， or READS SQL DATA in its declaration and binary logging is enabled(you\*might\*want to use the less safe log bin trust unction creators variable)
    -   `binlog_expire_logs_auto_purge`：[二进制日志|binlog](二进制日志-binlog_ejCUGaodeJVCeLkhRYzCyE.md "二进制日志|binlog")存储的时间自动清除开关，MySQL8.0新增
    -   `binlog_expire_logs_seconds`：[二进制日志|binlog](二进制日志-binlog_ejCUGaodeJVCeLkhRYzCyE.md "二进制日志|binlog")存储的过期时间，MySQL8.0新增 <示例：`binlog.000001
        binlog.000002
        binlog.000003
        binlog.000004
        binlog.000005
        binlog.000006
        binlog.000007
        binlog.000008
        binlog.000009
        binlog.000010`>
    -   `max_binlog_size`：[二进制日志|binlog](二进制日志-binlog_ejCUGaodeJVCeLkhRYzCyE.md "二进制日志|binlog")单文件存储的最大值(1073741824KB=1G) <示例：`binlog.000001
        binlog.000002
        binlog.000003
        binlog.000004
        binlog.000005
        binlog.000006
        binlog.000007
        binlog.000008
        binlog.000009
        binlog.000010`>
        > 并不严格，如果在即将超过了最大值，而记录的事务还没有完成，将超过最大存储上限，完成事务。
    -   `binlog_format`：[二进制日志|binlog](二进制日志-binlog_ejCUGaodeJVCeLkhRYzCyE.md "二进制日志|binlog")内容格式设置

        MySQL 从 MySQL5.1.8 开始提供 Mixed 模式，MySQL5.7.7之前的版本默认是Statement 模式，之后默认使用Row模式， 但是在 8.0 以上版本已经默认使用 Mixed 模式了。
        -   `row`
            -   基于行的复制(row-based replication-RBR)
            MySQL 5.1 版本开始支持Row模式的 Binlog，它与 Statement 模式的区别在于它不保存具体的 SQL 语句，而是记录具体被修改的信息。

            比如一条 update 语句更新10条数据，如果是 Statement 模式那就保存一条 SQL 就够，但是 Row 模式会保存每一行分别更新了什么，有10条数据。

            Row 模式的优缺点就很明显了。保存每一个更改的详细信息必然会带来存储空间的快速膨胀，换来的是事件操作的详细记录。所以要求越高代价越高。
        -   `statement`
            -   基于 SQL 语句的复制(statement-based replication-SBR)
            保存每一条修改数据的SQL。

            该模式只保存一条普通的SQL语句，不涉及到执行的上下文信息。

            因为每台 MySQL 数据库的本地环境可能不一样，那么对于依赖到本地环境的函数或者上下文处理的逻辑 SQL 去处理的时候可能同样的语句在不同的机器上执行出来的效果不一致。所以\[Q]若在创建存储函数中报错“ you might want to use the less safe log\_bin\_trust\_function\_creators variable ”，有两种处理方法：[^注释1] <1/2添加函数特性; 2/2关闭`log_bin_trust_function_creators`>

            比如像 `sleep()`函数，`LAST_INSERT_ID()`函数，等等，这些都跟特定时间的本地环境有关，在主从服务器上值是不同的。
        -   `mixed`
            -   混合模式复制(mixed-based replication-MBR)
            Mixed 模式即以上两种模式的综合体。既然上面两种模式分别走了极简和一丝不苟的极端，那是否可以区分使用场景的情况下将这两种模式综合起来呢？

            在 Mixed 模式中，一般的更新语句使用 `statement`模式来保存 Binlog，但是遇到一些函数操作，可能会影响数据准确性的操作则使用 `row`模式来保存。这种方式需要根据每一条具体的 SQL 语句来区分选择哪种模式。

            MySQL 从 MySQL5.1.8 开始提供 Mixed 模式，MySQL5.7.7之前的版本默认是Statement 模式，之后默认使用Row模式， 但是在 8.0 以上版本已经默认使用 Mixed 模式了。
    -   `binlog_expire_logs_seconds`：设置binlog过期时间(秒)
    -   `expire_logs_days`：设置binlog过期时间(天)

        Binlog 过期删除不是服务定时执行，是需要借助事件触发才执行，事件包括：
        -   服务器重启
        -   服务器被更新
        -   日志达到了最大日志长度 `max_binlog_size`
        -   日志被刷新

## binlog查询文件信息与内容

-   示例：查看有哪些[二进制日志|binlog](二进制日志-binlog_ejCUGaodeJVCeLkhRYzCyE.md "二进制日志|binlog") 文件 \[`SHOW BINARY LOGS;`] <`binlog.000001
    binlog.000002
    binlog.000003
    binlog.000004
    binlog.000005
    binlog.000006
    binlog.000007
    binlog.000008
    binlog.000009
    binlog.000010`>

    MySQL8.0
    ```sql
    mysql> show binary logs;
    +---------------+-----------+-----------+
    | Log_name      | File_size | Encrypted |
    +---------------+-----------+-----------+
    | binlog.000012 |       157 | No        |
    | binlog.000013 |       486 | No        |
    | binlog.000014 |       157 | No        |
    | binlog.000015 |       180 | No        |
    | binlog.000016 |       157 | No        |
    +---------------+-----------+-----------+
    5 rows in set (0.04 sec)
    ```
    MySQL5.7
    ```sql
    mysql> show binary logs;
    +-------------------+-----------+
    | Log_name          | File_size |
    +-------------------+-----------+
    | binlogFile.000001 |       154 |
    +-------------------+-----------+
    1 row in set (0.00 sec)
    ```
-   示例：查询[二进制日志|binlog](二进制日志-binlog_ejCUGaodeJVCeLkhRYzCyE.md "二进制日志|binlog") 信息 \[`log_bin``log_bin_basename``log_bin_index``log_bin_trust_function_creators``sql_log_bin`]
    ```sql
    mysql> show variables like '%log_bin%';
    +---------------------------------+-------+
    | Variable_name                   | Value |
    +---------------------------------+-------+
    | log_bin                         | OFF   |
    | log_bin_basename                |       |
    | log_bin_index                   |       |
    | log_bin_trust_function_creators | OFF   |
    | log_bin_use_v1_row_events       | OFF   |
    | sql_log_bin                     | ON    |
    +---------------------------------+-------+
    6 rows in set (0.00 sec)
    ```
-   示例：MySQL5.7 GA开启[二进制日志|binlog](二进制日志-binlog_ejCUGaodeJVCeLkhRYzCyE.md "二进制日志|binlog")  \[`[mysqld]``log_bin``log_bin_basename``log_bin_trust_function_creators`]

    示例：开启binlog方式1/2

    `log_bin`：[二进制日志|binlog](二进制日志-binlog_ejCUGaodeJVCeLkhRYzCyE.md "二进制日志|binlog")开关

    `log_bin_basename`：[二进制日志|binlog](二进制日志-binlog_ejCUGaodeJVCeLkhRYzCyE.md "二进制日志|binlog")存储路径 <示例：`binlog.000001
    binlog.000002
    binlog.000003
    binlog.000004
    binlog.000005
    binlog.000006
    binlog.000007
    binlog.000008
    binlog.000009
    binlog.000010`>

    `log_bin_index`：[二进制日志|binlog](二进制日志-binlog_ejCUGaodeJVCeLkhRYzCyE.md "二进制日志|binlog")的索引 <示例：`binlog.index`>
    ```sql
    [mysqld]
    log_bin=ON  
    log_bin_basename=/var/lib/mysql/binlogFile
    log_bin_index=/var/lib/mysql/binlogFile.index
    ```
    示例：开启binlog方式2/2 \[`log-bin`]
    ```sql
    [mysqld]
    log-bin=/var/lib/mysql/binlogFile
    ```
    log-bin参数的作用和log\_bin、log\_bin\_basename、log\_bin\_index的作用是相同的，mysql会根据这个配置自动设置log\_bin为on状态，并自动设置文件名与索引文件的名称
    -   在MySQL5.7之前以上配置ok了，之后还需要配置，随机指定一个不能和其他集群中机器重名的字符串，如果只有一台机器，那就可以随便指定了
        ```sql
        [mysqld]
        server-id=123456
        ```
    -   检查配置
        ```sql
        mysql> show variables like '%log%bin%'; 
        +----------------------------------+---------------------------------+
        | Variable_name                    | Value                           |
        +----------------------------------+---------------------------------+
        | log_bin                          | ON                              |
        | log_bin_basename                 | /var/lib/mysql/binlogFile       |
        | log_bin_index                    | /var/lib/mysql/binlogFile.index |
        | log_bin_trust_function_creators  | OFF                             |
        | log_bin_use_v1_row_events        | OFF                             |
        | log_statements_unsafe_for_binlog | ON                              |
        | sql_log_bin                      | ON                              |
        +----------------------------------+---------------------------------+
        7 rows in set (0.00 sec)
        ```
        ![](../image/image_rZow3rdiPU.png)
-   示例：查询[二进制日志|binlog](二进制日志-binlog_ejCUGaodeJVCeLkhRYzCyE.md "二进制日志|binlog")文件内容
    -   查询binlog内容方式1/2：使用[mysqlbinlog](mysqlbinlog_jfYK2i7M6WTFhke88PmyRv.md "mysqlbinlog")工具查看

        语法：查询binlog内容：`mysqlbinlog -v [binlog PATH]`
    -   查询binlog内容方式2/2：`SHOW BINLOG EVENTS;` <[空降](https://www.bilibili.com/video/BV1iq4y1u7vj?p=189\&spm_id_from=pageDriver\&vd_source=d87be07aa170c6f76058fa2663ca0da0\&t=1438.3 "空降")>

        ![](../image/image_ySidBs0KpR.png)

        ![](../image/image_7Ag1HXJedm.png)

        ![](../image/image_PbF7wQi8of.png)

        ![](../image/image_OFKmss4ftW.png)

## binlog的格式

-   `binlog_format`：[二进制日志|binlog](二进制日志-binlog_ejCUGaodeJVCeLkhRYzCyE.md "二进制日志|binlog")内容格式设置

    MySQL 从 MySQL5.1.8 开始提供 Mixed 模式，MySQL5.7.7之前的版本默认是Statement 模式，之后默认使用Row模式， 但是在 8.0 以上版本已经默认使用 Mixed 模式了。
    -   `row`
        -   基于行的复制(row-based replication-RBR)
        MySQL 5.1 版本开始支持Row模式的 Binlog，它与 Statement 模式的区别在于它不保存具体的 SQL 语句，而是记录具体被修改的信息。

        比如一条 update 语句更新10条数据，如果是 Statement 模式那就保存一条 SQL 就够，但是 Row 模式会保存每一行分别更新了什么，有10条数据。

        Row 模式的优缺点就很明显了。保存每一个更改的详细信息必然会带来存储空间的快速膨胀，换来的是事件操作的详细记录。所以要求越高代价越高。
    -   `statement`
        -   基于 SQL 语句的复制(statement-based replication-SBR)
        保存每一条修改数据的SQL。

        该模式只保存一条普通的SQL语句，不涉及到执行的上下文信息。

        因为每台 MySQL 数据库的本地环境可能不一样，那么对于依赖到本地环境的函数或者上下文处理的逻辑 SQL 去处理的时候可能同样的语句在不同的机器上执行出来的效果不一致。所以\[Q]若在创建存储函数中报错“ you might want to use the less safe log\_bin\_trust\_function\_creators variable ”，有两种处理方法：[^注释1] <1/2添加函数特性; 2/2关闭`log_bin_trust_function_creators`>

        比如像 `sleep()`函数，`LAST_INSERT_ID()`函数，等等，这些都跟特定时间的本地环境有关，在主从服务器上值是不同的。
    -   `mixed`
        -   混合模式复制(mixed-based replication-MBR)
        Mixed 模式即以上两种模式的综合体。既然上面两种模式分别走了极简和一丝不苟的极端，那是否可以区分使用场景的情况下将这两种模式综合起来呢？

        在 Mixed 模式中，一般的更新语句使用 `statement`模式来保存 Binlog，但是遇到一些函数操作，可能会影响数据准确性的操作则使用 `row`模式来保存。这种方式需要根据每一条具体的 SQL 语句来区分选择哪种模式。

        MySQL 从 MySQL5.1.8 开始提供 Mixed 模式，MySQL5.7.7之前的版本默认是Statement 模式，之后默认使用Row模式， 但是在 8.0 以上版本已经默认使用 Mixed 模式了。
-   示例：查询binlog的格式 \[`binlog_format`]
    ```sql
    mysql> show variables like "%binlog_format%";
    +---------------+-------+
    | Variable_name | Value |
    +---------------+-------+
    | binlog_format | ROW   |
    +---------------+-------+
    1 row in set (0.00 sec)
    ```

## 使用日志恢复数据

语法：恢复数据：`mysqlbinlog [OPTION] [binglog PATH] | [msyql LOGIN]`

-   示例：使用日志恢复数据方式1/2：以时间：

    ₛₗ1、查询时间，找到需要恢复的时间范围语法：查询binlog内容：`mysqlbinlog -v [binlog PATH]`

    ₛₗ2、使用[mysqlbinlog](mysqlbinlog_jfYK2i7M6WTFhke88PmyRv.md "mysqlbinlog")进行恢复 \[`--start-position=``--stop-position=``--database`]

    ![](../image/image_ZGsbr1WxbI.png)
-   示例：使用日志恢复数据方式2/2：以pos ：

    ₛₗ1、查询pos，找到需要恢复的范围：`SHOW BINLOG EVENTS;`

    ₛₗ2、使用[mysqlbinlog](mysqlbinlog_jfYK2i7M6WTFhke88PmyRv.md "mysqlbinlog")进行恢复 \[`--start-position=``--stop-position=``--database`]

    ![](../image/image_h-k5bZlx-4.png)

## 删除binlog

MySQL的二进制文件可以配置自动删除，同时MySQL也提供了安全的手动删除二进制文件的方法。`PURGE MASTER LOGS [TO|BEFORE]` 只删除指定部分的二进制日志文件，`RESET MASTER` 删除所有的二进制日志文件。

`PURGE MASTER LOGS [TO|BEFORE]`

`RESET MASTER`



`PURGE MASTER LOGS [TO|BEFORE]`：删除指定日志文件;删除to之前的文件;before：删除之前日期的文件

`RESET MASTER`：删除所有的二进制日志文件

示例：查看有哪些[二进制日志|binlog](二进制日志-binlog_ejCUGaodeJVCeLkhRYzCyE.md "二进制日志|binlog") 文件 \[`SHOW BINARY LOGS;`] <`binlog.000001
binlog.000002
binlog.000003
binlog.000004
binlog.000005
binlog.000006
binlog.000007
binlog.000008
binlog.000009
binlog.000010`>

-   示例：查询日志创建时间：`mysqlbinlog  --no-defaults "/var/lib/mysql/binlog.000016"` \[`--no-defaults`]

    \`\`\`&#x20;
-   语法：删除binlog \[`PURGE MASTER LOGS [TO|BEFORE]`]
    ```sql
     PURGE {MASTER | BINARY} LOGS TO ‘指定日志文件名’
     PURGE {MASTER | BINARY} LOGS BEFORE ‘指定日期’
    ```
-   示例：删除创建时间比binlog.000005早的所有日志 \[`PURGE MASTER LOGS [TO|BEFORE]`]
    ```sql
    PURGE MASTER LOGS TO "binlog.000005";
    ```
-   示例：删除指定日期之前的binlog日志：删除20220829之前的日志 \[`PURGE MASTER LOGS [TO|BEFORE]`]
    ```sql
      PURGE MASTER LOG before "20220829";
    ```
-   示例：删除所有binlog \[`RESET MASTER`]
    ```sql
    RESET MASTER
    ```

## binlog文件的写入机制

## 碎片

`FLUSH LOGS`：刷新日志;生成新的binlog





[^注释1]: [https://www.bilibili.com/video/BV1iq4y1u7vj?p=80\&t=623.3](https://www.bilibili.com/video/BV1iq4y1u7vj?p=80\&t=623.3 "https://www.bilibili.com/video/BV1iq4y1u7vj?p=80\&t=623.3")
