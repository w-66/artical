# \[Task]MySQL\&SQL

| 标签   | 已完成                     |
| ---- | ----------------------- |
| Date | 2022/06/22 → 2022/09/13 |
| 类型   | 技术,后端                   |

\[[MySQL](MySQL_pPMN84zaKJANNFTyjDjZiX.md "MySQL")[SQL](SQL_69pQjm3Twb3qB6d1CQdg1u.md "SQL")]



-   [ ] 使用参数化查询插入数据? \[ₛₗ参数化查询插入]
    -   original
        ```bash
        """
        实操

        将ipfs add生成的文本导入到MySQL中
        """ 
        import MySQLdb
        # import codecs
        import json
        import unicodedata
        import re
        import os

        # 打开原始文件以读取内容
        original_text_path = 'F:\Code\Python\demo_basics_01\demo_module_mysqlclient\push_nas_music.txt'
        secondary_text_path = 'F:\Code\Python\demo_basics_01\demo_module_mysqlclient\ipfs_music_cid.txt'
        # secondary_text_path = 'F:\\Code\Python\\demo_basics_01\\demo_module_mysqlclient\\text.txt'

        #############################提取格式化数据
        def format_data():
            with open(original_text_path, 'r', encoding='utf-8') as file:
                lines = file.readlines()

            # 创建一个空列表来存储提取的信息
            ipfs_info = []

            # 遍历文件的每一行
            for line in lines:
                # 使用正则表达式匹配CID和音乐名称
                import re
                match = re.search(r'added\s+(\S+)\s+nas_music/([^\n]+)', line)
                if match:
                    cid = match.group(1)
                    music_name = match.group(2)
                    ipfs_info.append(f"{cid}\t{music_name}")

            # 将提取的信息写入新文件
            with open(secondary_text_path, 'w', encoding='utf-8') as output_file:
                for info in ipfs_info:
                    output_file.write(info + '\n')


        #######################将格式化数据导入MySQL
        # 填写数据库连接信息
        host = "qwertyui.vip"  # 主机名
        user = "ipfs"  # 数据库用户名
        password = "asdf;lkjdlmmipfs"  # 数据库密码
        db_name = "ipfs"  # 数据库名称
        port = 50001

        # 使用codecs模块解码Unicode转义序列
        def contain_unicode(text):
            def replace_unicode(match):
                unicode_str = match.group(0)
                try:
                    decoded_str = bytes(unicode_str, 'utf-8').decode('unicode_escape')
                    return decoded_str
                except UnicodeDecodeError:
                    return unicode_str

            # 使用正则表达式查找所有Unicode转义字符
            unicode_pattern = r'\\u[0-9a-fA-F]{4}'
            decoded_text = re.sub(unicode_pattern, replace_unicode, text)
            # decoded_text = re.sub(r'\'', "\\'", decoded_text)
            # print(decoded_text)
            return decoded_text

        # 从ipfs add中取出的数据进行录入
        def import_ipfs():
            # 读取提取的IPFS音乐信息文件
            with open(secondary_text_path, 'r', encoding='utf-8') as file:
                lines = file.readlines()
            try:
                # 连接数据库
                connection = MySQLdb.connect(host=host, user=user, password=password, db=db_name, port=port)

                # 创建游标对象
                cursor = connection.cursor()

                # 循环遍历示例数据并插入到数据库中
                for item in lines:
                    cid, filename = item.strip().split('\t') # 分隔数据
                    filename = contain_unicode(filename)
                    if re.search(r'\.[A-Za-z0-9]{1,12}$', filename): # 判断字符串是否带有格式后缀，且不超过12个字符 345345
                        # 有尾缀格式的条目为文件
                        if "/" in filename:
                            # 带路径的文件
                            filename_parts = filename.split("/")
                            path = "/".join(filename_parts[:-1])
                            filename = filename_parts[-1]
                            filename, format = os.path.splitext(filename)  # 分离文件名与格式
                            format = format.strip('.')                     # 去除格式的点
                        else:
                            # 不带路径的文件
                            path = ""
                            filename, format = os.path.splitext(filename)
                            format = format.strip('.')
                            
                        # 联合查询判断是否存在于数据库
                        print(cid, filename, format) # QmS81vLHMPedLY16Ym4LQPKYqL3gGzx7rh9NP4R6rzSqa1 鹰王-It"s Your Birthday jpg
                        # isExist = cursor.execute(f"SELECT 1 FROM ipfs_music WHERE cid='{cid}' AND filename='{filename}'  AND format='{format}'")
                        # 使用参数化查询插入数据 // 可以避免'"两个符号的语法冲突
                        query = "SELECT 1 FROM ipfs_music WHERE cid=%s AND filename=%s AND format=%s"
                        isExist = cursor.execute(query, (cid, filename, format))
                        
                        # 
                        if isExist == 0:
                            # 插入文件记录
                            cursor.execute(
                                "INSERT INTO ipfs.ipfs_music (cid, filename, type, path, format) VALUES (%s, %s, 'file', %s, %s)",
                                (cid, filename, path, format)
                            )
                        else:
                            print(f'已经存在--{filename}.{format}')
                    else:
                        # 没有尾缀的为文件夹名
                        # 插入文件夹记录
                        cursor.execute(
                            "INSERT INTO ipfs.ipfs_music (cid, filename, type, path) VALUES (%s, '', 'path', %s)",
                            (cid, filename)
                        )

                # 提交更改
                connection.commit()
                print("数据已成功录入到数据库。")

            except Exception as e:
                print(f"发生错误：{e}")
            finally:
                # 关闭游标和连接
                cursor.close()
                connection.close()

        if __name__ == '__main__':
            import_ipfs()


        ```

***

```ybsz

title MySQL高级篇 per block:hVuyh2P5AP24xMyHQiRbeS red
title MySQL初级篇 per block:86Aa2aoEC4qBffXnsxN9XJ green
title MySQL初级篇课后练习 per block:e3vBugTrAc5S3C5ouwQ93E red

```

20220622-20220902

20220912-20220913



```ybsz
title 距2022/6/22学习MySQL开始时间已过 day count:2022/6/22 red
```

-   [ ] 扩展-双主双从模式
    -   [ ] 读写分离(mycat<数据库中间件>)
    ![](../image/image_5VDGn5dLgy.png)



🔳🔳🔳🔳🔳🔳🔳🔳🔳⬜️ 90%

-   [x] P199 <空降>
-   [x] P198 <[空降](https://www.bilibili.com/video/BV1iq4y1u7vj?p=198\&spm_id_from=pageDriver\&vd_source=d87be07aa170c6f76058fa2663ca0da0 "空降")>数据库迁移
-   [x] P197 <空降>物理备份实现
-   [x] P196 <[空降](https://www.bilibili.com/video/BV1iq4y1u7vj?p=196\&spm_id_from=pageDriver\&vd_source=d87be07aa170c6f76058fa2663ca0da0 "空降")>逻辑备份实现
-   [x] P195 <[空降](https://www.bilibili.com/video/BV1iq4y1u7vj?p=195\&spm_id_from=pageDriver\&vd_source=d87be07aa170c6f76058fa2663ca0da0 "空降")>[DB的备份与恢复](DB的备份与恢复_xe9Kw7bfnE4ZkzQXPM6ffL.md "DB的备份与恢复") 备份文件的内容解读<[空降](https://www.bilibili.com/video/BV1iq4y1u7vj?p=195\&spm_id_from=pageDriver\&vd_source=d87be07aa170c6f76058fa2663ca0da0\&t=814.2 "空降")>
-   [x] P194 <[空降](https://www.bilibili.com/video/BV1iq4y1u7vj?p=194\&spm_id_from=pageDriver\&vd_source=d87be07aa170c6f76058fa2663ca0da0 "空降")>数据同步一致性问题 如何解决一致性问题<[空降](https://www.bilibili.com/video/BV1iq4y1u7vj?p=194\&spm_id_from=pageDriver\&vd_source=d87be07aa170c6f76058fa2663ca0da0\&t=194.1 "空降")>
-   [x] P193 <[空降](https://www.bilibili.com/video/BV1iq4y1u7vj?p=193\&spm_id_from=pageDriver\&vd_source=d87be07aa170c6f76058fa2663ca0da0 "空降")>binlog的格式
-   [x] P192-一主一从架构搭建与主从同步的实现|一主一从架构搭建<[空降](https://www.bilibili.com/video/BV1iq4y1u7vj?p=192\&spm_id_from=pageDriver\&vd_source=d87be07aa170c6f76058fa2663ca0da0\&t=784.8 "空降")>
-   [x] P191-[中继日志](中继日志_qkZZxdtrA7f9Vb9HTfkNYC.md "中继日志")、[MySQL主从复制](MySQL主从复制_ppdss6EqC8ycGWwYxt9xRa.md "MySQL主从复制")步骤与原理剖析 <[空降](https://www.bilibili.com/video/BV1iq4y1u7vj?p=191\&spm_id_from=pageDriver\&vd_source=d87be07aa170c6f76058fa2663ca0da0\&t=3.7 "空降")>
-   [x] P190-binlog的删除、binlog的写入机制与两阶段提交<[空降](https://www.bilibili.com/video/BV1iq4y1u7vj?p=190\&spm_id_from=pageDriver\&vd_source=d87be07aa170c6f76058fa2663ca0da0 "空降")> |使用日志恢复数据删除binlog|&#x20;
    -   [ ] [空降](https://www.bilibili.com/video/BV1iq4y1u7vj?p=190\&spm_id_from=pageDriver\&vd_source=d87be07aa170c6f76058fa2663ca0da0\&t=599.9 "空降")binlog文件的写入机制<[空降](https://www.bilibili.com/video/BV1iq4y1u7vj?p=190\&spm_id_from=pageDriver\&vd_source=d87be07aa170c6f76058fa2663ca0da0\&t=599.9 "空降")>\*
-   [x] P189-binlog日志的参数设置与实现数据恢复演示 binlog的格式<[空降](https://www.bilibili.com/video/BV1iq4y1u7vj?p=189\&spm_id_from=pageDriver\&vd_source=d87be07aa170c6f76058fa2663ca0da0\&t=1524.6 "空降")>|使用日志恢复数据<[空降](https://www.bilibili.com/video/BV1iq4y1u7vj?p=189\&spm_id_from=pageDriver\&vd_source=d87be07aa170c6f76058fa2663ca0da0\&t=1627.0 "空降")>
-   [x] P188-通用查询日志、错误日志<[空降](https://www.bilibili.com/video/BV1iq4y1u7vj?p=188\&spm_id_from=pageDriver\&vd_source=d87be07aa170c6f76058fa2663ca0da0 "空降")>通用查询日志错误日志
-   [x] P187-六大日志文件的概述<[空降](https://www.bilibili.com/video/BV1iq4y1u7vj?p=187\&vd_source=d87be07aa170c6f76058fa2663ca0da0 "空降")>|日志类型
-   P169-186 锁&#x20;
-   [ ] P186-MVCC在可重复读下解决幻读的流程
-   [ ] P185-MVCC在读已提交和可重复读隔离级别下的操作流程
-   [ ] P184 复习<[空降](https://www.bilibili.com/video/BV1iq4y1u7vj?p=184\&spm_id_from=pageDriver\&vd_source=d87be07aa170c6f76058fa2663ca0da0 "空降")>MVCC实现原理之ReadView<[空降](https://www.bilibili.com/video/BV1iq4y1u7vj?p=184\&spm_id_from=pageDriver\&vd_source=d87be07aa170c6f76058fa2663ca0da0\&t=845.8 "空降")>
-   [ ] P183-[MVCC机制](MVCC机制_5TREWmSUs2e75ePg7nC7aM.md "MVCC机制")<[空降](https://www.bilibili.com/video/BV1iq4y1u7vj?p=183\&spm_id_from=pageDriver\&vd_source=d87be07aa170c6f76058fa2663ca0da0 "空降")>
-   [x] P182-锁的内存结构<[空降](https://www.bilibili.com/video/BV1iq4y1u7vj?p=182\&spm_id_from=pageDriver\&vd_source=d87be07aa170c6f76058fa2663ca0da0 "空降")>;  锁的监控<[空降](https://www.bilibili.com/video/BV1iq4y1u7vj?p=182\&spm_id_from=pageDriver\&vd_source=d87be07aa170c6f76058fa2663ca0da0\&t=947.8 "空降")>？
-   [x] P181-全局锁与死锁的理解<[空降](https://www.bilibili.com/video/BV1iq4y1u7vj?p=181\&spm_id_from=pageDriver\&vd_source=d87be07aa170c6f76058fa2663ca0da0 "空降")> | [全局锁](全局锁_96YnXXNeVH54NYD5xuQmSq.md "全局锁") | [死锁(Deadlock)](死锁\(Deadlock\)_amBFE2vxvBXoMYFnyDgESf.md "死锁(Deadlock)")<[空降](https://www.bilibili.com/video/BV1iq4y1u7vj?p=181\&spm_id_from=pageDriver\&vd_source=d87be07aa170c6f76058fa2663ca0da0\&t=227.7 "空降")>
-   [ ] P180-加锁方式：[隐式锁](隐式锁_cqq9gVW9UWLzUYNmEhLGmb.md "隐式锁")、[显示锁](显示锁_f6QNS2PnGYy5h6YbpFNdNz.md "显示锁")？<[空降](https://www.bilibili.com/video/BV1iq4y1u7vj?p=180\&spm_id_from=pageDriver\&vd_source=d87be07aa170c6f76058fa2663ca0da0 "空降")>

    [https://www.bilibili.com/video/BV1iq4y1u7vj?p=180\&spm\_id\_from=pageDriver\&vd\_source=d87be07aa170c6f76058fa2663ca0da0\&t=690.6](https://www.bilibili.com/video/BV1iq4y1u7vj?p=180\&spm_id_from=pageDriver\&vd_source=d87be07aa170c6f76058fa2663ca0da0\&t=690.6 "https://www.bilibili.com/video/BV1iq4y1u7vj?p=180\&spm_id_from=pageDriver\&vd_source=d87be07aa170c6f76058fa2663ca0da0\&t=690.6")
-   [x] P179 <[空降](https://www.bilibili.com/video/BV1iq4y1u7vj?p=179\&spm_id_from=pageDriver\&vd_source=d87be07aa170c6f76058fa2663ca0da0 "空降")>[页级锁](页级锁_bCfV43Gvb5aCdwwksx99gW.md "页级锁") | 从对待锁的态度划分[悲观锁](悲观锁_nyJujMES3zSpyEcrJpWWgv.md "悲观锁")、[乐观锁](乐观锁_9ViHME74Wz7h8RpWT9pwEN.md "乐观锁")<[空降](https://www.bilibili.com/video/BV1iq4y1u7vj?p=179\&spm_id_from=pageDriver\&vd_source=d87be07aa170c6f76058fa2663ca0da0\&t=201.0 "空降")> | <[空降](https://www.bilibili.com/video/BV1iq4y1u7vj?p=179\&spm_id_from=pageDriver\&vd_source=d87be07aa170c6f76058fa2663ca0da0\&t=390.5 "空降")> | <[空降](https://www.bilibili.com/video/BV1iq4y1u7vj?p=179\&spm_id_from=pageDriver\&vd_source=d87be07aa170c6f76058fa2663ca0da0\&t=655.8 "空降")>| 、两种锁的适用场景

    [https://www.bilibili.com/video/BV1iq4y1u7vj?p=179\&spm\_id\_from=pageDriver\&vd\_source=d87be07aa170c6f76058fa2663ca0da0\&t=945.2](https://www.bilibili.com/video/BV1iq4y1u7vj?p=179\&spm_id_from=pageDriver\&vd_source=d87be07aa170c6f76058fa2663ca0da0\&t=945.2 "https://www.bilibili.com/video/BV1iq4y1u7vj?p=179\&spm_id_from=pageDriver\&vd_source=d87be07aa170c6f76058fa2663ca0da0\&t=945.2")
-   [x] P178 <[空降](https://www.bilibili.com/video/BV1iq4y1u7vj?p=178\&spm_id_from=pageDriver\&vd_source=d87be07aa170c6f76058fa2663ca0da0 "空降")>临键锁(Next-Key Locks)<[空降](https://www.bilibili.com/video/BV1iq4y1u7vj?p=178\&spm_id_from=pageDriver\&vd_source=d87be07aa170c6f76058fa2663ca0da0\&t=79.2 "空降")> | 插入意向锁(Insert Intention Locks)
-   [x] P177 <[空降](https://www.bilibili.com/video/BV1iq4y1u7vj?p=177\&spm_id_from=pageDriver\&vd_source=d87be07aa170c6f76058fa2663ca0da0 "空降")> [行级锁](行级锁_nMK3XogpBVKKEKoGgBXnev.md "行级锁")|记录锁(Record Locks) |间隙锁(Gap Locks)<[空降](https://www.bilibili.com/video/BV1iq4y1u7vj?p=177\&spm_id_from=pageDriver\&vd_source=d87be07aa170c6f76058fa2663ca0da0\&t=505.0 "空降")>
-   [x] P176 <[空降](https://www.bilibili.com/video/BV1iq4y1u7vj?p=176\&spm_id_from=pageDriver\&vd_source=d87be07aa170c6f76058fa2663ca0da0 "空降")> 表级别自增锁(AUTO-INC锁);表级锁元数据锁<[空降](https://www.bilibili.com/video/BV1iq4y1u7vj?p=176\&spm_id_from=pageDriver\&vd_source=d87be07aa170c6f76058fa2663ca0da0\&t=508.5 "空降")>
-   [x] P175 锁之S锁、X锁、意向锁 <[空降](https://www.bilibili.com/video/BV1iq4y1u7vj?p=175\&spm_id_from=pageDriver\&vd_source=d87be07aa170c6f76058fa2663ca0da0 "空降")> | 从数据操作的粒度划分：[表级锁](表级锁_eoAdhZjeSwxAg2SwXi6AZz.md "表级锁")、[页级锁](页级锁_bCfV43Gvb5aCdwwksx99gW.md "页级锁")、[行级锁](行级锁_nMK3XogpBVKKEKoGgBXnev.md "行级锁") | 表级别的意向锁<[空降](https://www.bilibili.com/video/BV1iq4y1u7vj?p=175\&spm_id_from=pageDriver\&vd_source=d87be07aa170c6f76058fa2663ca0da0\&t=1220.0 "空降")>
-   [x] P174 数据操作类型的角度理解S锁与X锁 <[空降](https://www.bilibili.com/video/BV1iq4y1u7vj?p=174\&spm_id_from=pageDriver\&vd_source=d87be07aa170c6f76058fa2663ca0da0 "空降")> 锁的分类与解析> 从数据操作的类型划分：读锁|共享锁、写锁|排它锁
-   [x] P173 锁的概述\_读写的并发问题<[空降](https://www.bilibili.com/video/BV1iq4y1u7vj?p=173\&spm_id_from=pageDriver\&vd_source=d87be07aa170c6f76058fa2663ca0da0 "空降") >[MySQL锁](MySQL锁_djf5GQA6U4fUvmrGVEGZPo.md "MySQL锁") ;读-读操作;写-写操作;读-写或写-读情况;并发问题的解决方案
-   P169-172 [事务日志](事务日志_7kTqyN3jnAr1Fik6HVRT9c.md "事务日志")
-   [x] P172 Undo日志的概述与写入过程 <[空降](https://www.bilibili.com/video/BV1iq4y1u7vj?p=172\&spm_id_from=pageDriver\&vd_source=d87be07aa170c6f76058fa2663ca0da0\&t=3.3 "空降")> undo log
    -   undo log的作用：回滚数据、[MVCC机制](MVCC机制_5TREWmSUs2e75ePg7nC7aM.md "MVCC机制")
    -   undo log的存储结构
    -   undo log的类型：`insert undo log`、`update undo log`
    -   undo log的生命周期\* <[空降](https://www.bilibili.com/video/BV1iq4y1u7vj?p=172\&spm_id_from=pageDriver\&vd_source=d87be07aa170c6f76058fa2663ca0da0\&t=1199.4 "空降")>
-   [x] P171 写入Redo Log Buffer和Redo Log File的写入策略 <[空降](https://www.bilibili.com/video/BV1iq4y1u7vj?p=171\&spm_id_from=pageDriver\&vd_source=d87be07aa170c6f76058fa2663ca0da0 "空降")> | 写入`redo log buffer`的过程[^注释1];日志文件组<[空降](https://www.bilibili.com/video/BV1iq4y1u7vj?p=171\&spm_id_from=pageDriver\&vd_source=d87be07aa170c6f76058fa2663ca0da0\&t=972.1 "空降")>
-   [x] P170 Redo日志的刷盘策略与过程剖析<[空降](https://www.bilibili.com/video/BV1iq4y1u7vj?p=170\&spm_id_from=pageDriver\&vd_source=d87be07aa170c6f76058fa2663ca0da0 "空降")> | redo日志的组成 不同的刷盘策略对时间的影响
-   [x] P169  Redo日志和Undo日志的理解、为什么需要Redo日志  整体介绍与redo log详解 <[空降](https://www.bilibili.com/video/BV1iq4y1u7vj?p=169\&spm_id_from=pageDriver\&vd_source=d87be07aa170c6f76058fa2663ca0da0 "空降")>
-   P161-178 [MySQL事务的概念](MySQL事务的概念_bkGaaG7MZ31wNkg2NFoCt1.md "MySQL事务的概念")
-   [x] P168 演示隔离级别
-   [x] P167 演示隔离级别
-   [x] P166 演示隔离级别
-   [x] P165-MySQL隔离级别的查看和设置 <[空降](https://www.bilibili.com/video/BV1iq4y1u7vj?p=165\&spm_id_from=pageDriver\&vd_source=d87be07aa170c6f76058fa2663ca0da0 "空降")>
-   [x] P164-数据并发问题与4种隔离级别 <[空降](https://www.bilibili.com/video/BV1iq4y1u7vj?p=164\&spm_id_from=pageDriver\&vd_source=d87be07aa170c6f76058fa2663ca0da0 "空降")> \[事务隔离级别] 面试
-   [x] P163-事务的使用举例 <[空降](https://www.bilibili.com/video/BV1iq4y1u7vj?p=163\&spm_id_from=pageDriver\&vd_source=d87be07aa170c6f76058fa2663ca0da0 "空降")>  \[事务的示例]
-   [x] P162-显式事务与隐式事务 <[空降](https://www.bilibili.com/video/BV1iq4y1u7vj?p=162\&spm_id_from=pageDriver\&vd_source=d87be07aa170c6f76058fa2663ca0da0 "空降")>  \[使用事务
-   [x] P161-事务的ACID特性与事务的状态 <[空降](https://www.bilibili.com/video/BV1iq4y1u7vj?p=161\&spm_id_from=pageDriver\&vd_source=d87be07aa170c6f76058fa2663ca0da0 "空降")>

    MySQL事务概念

    事务的特性(ACID) <[空降](https://www.bilibili.com/video/BV1iq4y1u7vj?p=161\&spm_id_from=pageDriver\&vd_source=d87be07aa170c6f76058fa2663ca0da0\&t=794.5 "空降")>
-   P159-160**数据库其他调优策略**
-   [x] P160 数据库结构优化、大表优化 <[空降](https://www.bilibili.com/video/BV1iq4y1u7vj?p=160\&spm_id_from=pageDriver\&vd_source=d87be07aa170c6f76058fa2663ca0da0\&t=28.7 "空降")> [优化数据库结构](优化数据库结构_uMqoL5jRbWrSvoj74YZL4o.md "优化数据库结构")&#x20;
-   [x] P159 数据库调优整体步骤、优化MySQL服务器硬件和参数[优化MySQL服务器](优化MySQL服务器_f8y1nuauRtpKvEYV6QAC8T.md "优化MySQL服务器")
-   P150-158 [数据库的设计规范\*](数据库的设计规范-_4SzPcG2z7CVDFF4rJ1CS2m.md "数据库的设计规范*")
-   [x] P158 PowerDesigner创建概念、物理数据模型 <[空降](https://www.bilibili.com/video/BV1iq4y1u7vj?p=158\&spm_id_from=pageDriver\&vd_source=d87be07aa170c6f76058fa2663ca0da0 "空降")>
-   [x] P157 数据库的设计原则和日常SQL编写规范 <[空降](https://www.bilibili.com/video/BV1iq4y1u7vj?p=157\&spm_id_from=pageDriver\&vd_source=d87be07aa170c6f76058fa2663ca0da0 "空降")>

    数据表的设计原则 <[空降](https://www.bilibili.com/video/BV1iq4y1u7vj?p=157\&spm_id_from=pageDriver\&vd_source=d87be07aa170c6f76058fa2663ca0da0\&t=63.2 "空降")>
-   [x] P156 ER建模与转换数据表的过程 <[空降](https://www.bilibili.com/video/BV1iq4y1u7vj?p=156\&spm_id_from=pageDriver\&vd_source=d87be07aa170c6f76058fa2663ca0da0 "空降")>

    ER模型 <[空降](https://www.bilibili.com/video/BV1iq4y1u7vj?p=156\&spm_id_from=pageDriver\&vd_source=d87be07aa170c6f76058fa2663ca0da0 "空降")>
-   [x] P155 范式的实战案例 <[空降](https://www.bilibili.com/video/BV1iq4y1u7vj?p=155\&spm_id_from=pageDriver\&vd_source=d87be07aa170c6f76058fa2663ca0da0 "空降")>
-   [x] P154 巴斯范式、第四范式、第五范式和域键范式 <[空降](https://www.bilibili.com/video/BV1iq4y1u7vj?p=154\&spm_id_from=pageDriver\&vd_source=d87be07aa170c6f76058fa2663ca0da0 "空降")>

    BCNF(巴斯范式)

    第四范式 <[空降](https://www.bilibili.com/video/BV1iq4y1u7vj?p=154\&spm_id_from=pageDriver\&vd_source=d87be07aa170c6f76058fa2663ca0da0\&t=864.5 "空降")>

    第五范式; 域键范式 <[空降](https://www.bilibili.com/video/BV1iq4y1u7vj?p=154\&spm_id_from=pageDriver\&vd_source=d87be07aa170c6f76058fa2663ca0da0\&t=1037.2 "空降")>
-   [x] P153 反范式化的应用

    反范式化 <[空降](https://www.bilibili.com/video/BV1iq4y1u7vj?p=153\&spm_id_from=pageDriver\&vd_source=d87be07aa170c6f76058fa2663ca0da0 "空降")>
-   [x] P152 第二范式与第三范式 <[空降](https://www.bilibili.com/video/BV1iq4y1u7vj?p=152\&spm_id_from=pageDriver\&vd_source=d87be07aa170c6f76058fa2663ca0da0 "空降")>

    第二范式(2nd NF)

    第三范式(3rd NF) <[空降](https://www.bilibili.com/video/BV1iq4y1u7vj?p=152\&spm_id_from=pageDriver\&vd_source=d87be07aa170c6f76058fa2663ca0da0\&t=957.6 "空降")>
-   [x] P151 范式概述与第一范式

    第一范式(1st NF)
-   [x] P150 淘宝数据库的主键如何设计| 推荐的主键设计;最简单的主键设计：`UUID()`
-   P141-P149 [索引优化与查询优化\*](索引优化与查询优化-_ifSZmgjWtaBwwy5BJoDSPB.md "索引优化与查询优化*")
-   [ ] P149
-   [ ] P148
-   [ ] P147
-   [ ] [P146](https://www.bilibili.com/video/BV1iq4y1u7vj?p=146\&spm_id_from=pageDriver\&vd_source=d87be07aa170c6f76058fa2663ca0da0 "P146")
-   [x] [P145](https://www.bilibili.com/video/BV1iq4y1u7vj?p=145\&spm_id_from=pageDriver\&vd_source=d87be07aa170c6f76058fa2663ca0da0 "P145") [MySQL子查询](MySQL子查询_tTVo6FJmWoSzQA5qNBqRUo.md "MySQL子查询")优化;`ORDER BY`优化

    FileSort排序 <[空降](https://www.bilibili.com/video/BV1iq4y1u7vj?p=145\&spm_id_from=pageDriver\&vd_source=d87be07aa170c6f76058fa2663ca0da0\&t=2299.7 "空降")>\*
-   [ ] P144 `JOIN...ON`语句的底层原理<[空降](https://www.bilibili.com/video/BV1iq4y1u7vj?p=144\&spm_id_from=pageDriver\&vd_source=d87be07aa170c6f76058fa2663ca0da0 "空降") >
-   [x] P143 **外连接**与**内连接**查询优化<[空降](https://www.bilibili.com/video/BV1iq4y1u7vj?p=143\&spm_id_from=pageDriver\&vd_source=d87be07aa170c6f76058fa2663ca0da0 "空降")>

    外连接时驱动表与被驱动表字段需要索引增加效率 <字段类型需要相同> <[空降](https://www.bilibili.com/video/BV1iq4y1u7vj?p=143\&spm_id_from=pageDriver\&vd_source=d87be07aa170c6f76058fa2663ca0da0\&t=362.1 "空降")>&#x20;
-   [x] P142 索引失效案例2<[空降](https://www.bilibili.com/video/BV1iq4y1u7vj?p=142\&spm_id_from=pageDriver\&vd_source=d87be07aa170c6f76058fa2663ca0da0\&t=1.0 "空降")>&#x20;

    范围条件右边的列索引失效<[空降](https://www.bilibili.com/video/BV1iq4y1u7vj?p=142\&spm_id_from=pageDriver\&vd_source=d87be07aa170c6f76058fa2663ca0da0\&t=175.5 "空降")>&#x20;

    不等于(`!=`或者`<>`)索引失效<[空降](https://www.bilibili.com/video/BV1iq4y1u7vj?p=142\&spm_id_from=pageDriver\&vd_source=d87be07aa170c6f76058fa2663ca0da0\&t=414.0 "空降")>&#x20;

    `IS NULL` 可以使用索引，`IS NOT NULL` 无法触发索引<[空降](https://www.bilibili.com/video/BV1iq4y1u7vj?p=142\&spm_id_from=pageDriver\&vd_source=d87be07aa170c6f76058fa2663ca0da0\&t=503.6 "空降")>

    `LIKE`以通配符%开头索引失效，结尾生效<[空降](https://www.bilibili.com/video/BV1iq4y1u7vj?p=142\&spm_id_from=pageDriver\&vd_source=d87be07aa170c6f76058fa2663ca0da0\&t=611.8 "空降")>
-   [x] P141 数据准备；索引失效

    [https://www.bilibili.com/video/BV1iq4y1u7vj?p=141\&vd\_source=d87be07aa170c6f76058fa2663ca0da0\&t=1182.4](https://www.bilibili.com/video/BV1iq4y1u7vj?p=141\&vd_source=d87be07aa170c6f76058fa2663ca0da0\&t=1182.4 "https://www.bilibili.com/video/BV1iq4y1u7vj?p=141\&vd_source=d87be07aa170c6f76058fa2663ca0da0\&t=1182.4")
-   P134-P140[性能分析工具的使用](性能分析工具的使用_fSuvB29WiBoc68LnjySPmm.md "性能分析工具的使用")
-   [x] P140 分析优化器执行计划:trace\&MySQL监控分析视图 sys schema &#x20;
-   [x] P139 `EXPLAIN`四种输出格式** <**[**空降**](https://www.bilibili.com/video/BV1iq4y1u7vj?p=139\&spm_id_from=pageDriver\&vd_source=d87be07aa170c6f76058fa2663ca0da0 "空降")**>**
-   [x] P138 演示`EXPLAIN` <[空降](https://www.bilibili.com/video/BV1iq4y1u7vj?p=136\&spm_id_from=pageDriver\&vd_source=d87be07aa170c6f76058fa2663ca0da0\&t=1208.6 "空降")><空降>&#x20;
    -   [x] [https://www.bilibili.com/video/BV1iq4y1u7vj?p=138\&spm\_id\_from=pageDriver\&vd\_source=d87be07aa170c6f76058fa2663ca0da0\&t=820.9](https://www.bilibili.com/video/BV1iq4y1u7vj?p=138\&spm_id_from=pageDriver\&vd_source=d87be07aa170c6f76058fa2663ca0da0\&t=820.9 "https://www.bilibili.com/video/BV1iq4y1u7vj?p=138\&spm_id_from=pageDriver\&vd_source=d87be07aa170c6f76058fa2663ca0da0\&t=820.9")
-   [x] P137 分析查询语句：`EXPLAIN`：字段解析

    [https://www.bilibili.com/video/BV1iq4y1u7vj?p=137\&spm\_id\_from=pageDriver\&vd\_source=d87be07aa170c6f76058fa2663ca0da0\&t=758.5](https://www.bilibili.com/video/BV1iq4y1u7vj?p=137\&spm_id_from=pageDriver\&vd_source=d87be07aa170c6f76058fa2663ca0da0\&t=758.5 "https://www.bilibili.com/video/BV1iq4y1u7vj?p=137\&spm_id_from=pageDriver\&vd_source=d87be07aa170c6f76058fa2663ca0da0\&t=758.5")
    -   [ ] 练习<[空降](https://www.bilibili.com/video/BV1iq4y1u7vj?p=137\&spm_id_from=pageDriver\&vd_source=d87be07aa170c6f76058fa2663ca0da0\&t=2366.8 "空降")>
-   [x] P136 分析查询语句：`EXPLAIN`
-   [x] P135 定位执行慢的SQL：慢查询日志 <[空降](https://www.bilibili.com/video/BV1iq4y1u7vj?p=135\&spm_id_from=pageDriver\&vd_source=d87be07aa170c6f76058fa2663ca0da0 "空降")>
    -   [x] [https://www.bilibili.com/video/BV1iq4y1u7vj?p=135\&spm\_id\_from=pageDriver\&vd\_source=d87be07aa170c6f76058fa2663ca0da0\&t=409.5](https://www.bilibili.com/video/BV1iq4y1u7vj?p=135\&spm_id_from=pageDriver\&vd_source=d87be07aa170c6f76058fa2663ca0da0\&t=409.5 "https://www.bilibili.com/video/BV1iq4y1u7vj?p=135\&spm_id_from=pageDriver\&vd_source=d87be07aa170c6f76058fa2663ca0da0\&t=409.5")
-   [x] P134 数据库服务器的优化步骤<[空降](https://www.bilibili.com/video/BV1iq4y1u7vj?p=134\&spm_id_from=pageDriver\&vd_source=d87be07aa170c6f76058fa2663ca0da0 "空降")>&#x20;
    -   统计SQL的查询成本:last\_query\_cost <[空降](https://www.bilibili.com/video/BV1iq4y1u7vj?p=134\&spm_id_from=pageDriver\&vd_source=d87be07aa170c6f76058fa2663ca0da0\&t=732.2 "空降")>
-   P129-133[索引的创建删除与设计原则](索引的创建删除与设计原则_kXi1e5hoCMJtmkoXNhz5YY.md "索引的创建删除与设计原则")
-   [x] P133 索引的设计原则>不适合创建索引的情况 <[空降](https://www.bilibili.com/video/BV1iq4y1u7vj?p=133\&spm_id_from=pageDriver\&vd_source=d87be07aa170c6f76058fa2663ca0da0 "空降")>
-   [x] P132 索引的设计原则>限制索引的数目<[空降](https://www.bilibili.com/video/BV1iq4y1u7vj?p=132\&spm_id_from=pageDriver\&vd_source=d87be07aa170c6f76058fa2663ca0da0 "空降")>
-   [x] P131 索引的设计原则 <[空降](https://www.bilibili.com/video/BV1iq4y1u7vj?p=131\&spm_id_from=pageDriver\&vd_source=d87be07aa170c6f76058fa2663ca0da0\&t=23.0 "空降")>
-   [x] P130 通宵看得，注意力不大行...

    MySQL8.0新特性：降序索引,隐藏索引

    删除索引
-   [x] P129 [索引的创建删除与设计原则](索引的创建删除与设计原则_kXi1e5hoCMJtmkoXNhz5YY.md "索引的创建删除与设计原则")

    索引分类，索引的创建与删除

    [https://www.bilibili.com/video/BV1iq4y1u7vj?p=129\&spm\_id\_from=pageDriver\&vd\_source=d87be07aa170c6f76058fa2663ca0da0\&t=1705.9](https://www.bilibili.com/video/BV1iq4y1u7vj?p=129\&spm_id_from=pageDriver\&vd_source=d87be07aa170c6f76058fa2663ca0da0\&t=1705.9 "https://www.bilibili.com/video/BV1iq4y1u7vj?p=129\&spm_id_from=pageDriver\&vd_source=d87be07aa170c6f76058fa2663ca0da0\&t=1705.9")
-   110-128MySQL逻辑架构 与存储引擎
    -   121-124 [MySQL数据页内部结构与行格式详情](MySQL数据页内部结构与行格式详情_hFDNrzBC4oxBhdCJTTUNRo.md "MySQL数据页内部结构与行格式详情")
-   [x] P128 [索引的创建删除与设计原则](索引的创建删除与设计原则_kXi1e5hoCMJtmkoXNhz5YY.md "索引的创建删除与设计原则") <[空降](https://www.bilibili.com/video/BV1iq4y1u7vj?p=128\&spm_id_from=pageDriver\&vd_source=d87be07aa170c6f76058fa2663ca0da0 "空降")>
-   [x] P127区、段、碎片区、表空间结构
-   [x] P126

    `Redundant`详解 <[空降](https://www.bilibili.com/video/BV1iq4y1u7vj?p=126\&spm_id_from=pageDriver\&vd_source=d87be07aa170c6f76058fa2663ca0da0\&t=673.7 "空降")>
-   [x] P125设置行格式与idb文件剖析compact行格式 <[空降](https://www.bilibili.com/video/BV1iq4y1u7vj?p=125\&spm_id_from=pageDriver\&vd_source=d87be07aa170c6f76058fa2663ca0da0 "空降")>

    从**InnoDB数据页**的角度去看B+树如何查询! <[空降](https://www.bilibili.com/video/BV1iq4y1u7vj?p=125\&spm_id_from=pageDriver\&vd_source=d87be07aa170c6f76058fa2663ca0da0 "空降")>

    行格式字段(或记录格式)详解
-   [x] P124 页结构之页目录与页头<[空降](https://www.bilibili.com/video/BV1iq4y1u7vj?p=124\&spm_id_from=pageDriver\&vd_source=d87be07aa170c6f76058fa2663ca0da0 "空降")>
-   [x] P123页结构之最小最大记录\_行格式之记录头信息<[空降](https://www.bilibili.com/video/BV1iq4y1u7vj?p=123\&spm_id_from=pageDriver\&vd_source=d87be07aa170c6f76058fa2663ca0da0 "空降")>
-   [x] P122-(页的内部结构)<[空降](https://www.bilibili.com/video/BV1iq4y1u7vj?p=122\&spm_id_from=pageDriver\&vd_source=d87be07aa170c6f76058fa2663ca0da0 "空降")>
-   [x] P121InnoDB数据存储结构概述<[空降](https://www.bilibili.com/video/BV1iq4y1u7vj?p=121\&spm_id_from=pageDriver\&vd_source=d87be07aa170c6f76058fa2663ca0da0 "空降")>
-   115-120为索引的演变过程，迭代过程 解释[B+树](B+树_bDX7m5wCuiyeoVZTwFCbGr.md "B+树")迭代过程
-   [x] P120Hash索引、AVL树、B树与B+树对比 <[空降](https://www.bilibili.com/video/BV1iq4y1u7vj?p=120\&spm_id_from=pageDriver\&vd_source=d87be07aa170c6f76058fa2663ca0da0 "空降")> <面试>&#x20;
-   [x] P119InnoDB中B+树注意事项MyISAM的索引方案
    -   [ ] \[对比]InnoDB|MyISAM索引区别
-   [x] P118聚簇索引、二级索引与联合索引的概念 按物理实现方式：可分为聚簇索引与非聚簇索引<[空降](https://www.bilibili.com/video/BV1iq4y1u7vj?p=118\&vd_source=d87be07aa170c6f76058fa2663ca0da0 "空降")>
    -   [ ] 听得比较糢糊 70%
-   [x] P117索引的迭代方案 <[空降](https://www.bilibili.com/video/BV1iq4y1u7vj?p=117\&spm_id_from=pageDriver\&vd_source=d87be07aa170c6f76058fa2663ca0da0 "空降")>
-   [x] P116 一个简单地索引设计方案<[空降](https://www.bilibili.com/video/BV1iq4y1u7vj?p=116\&spm_id_from=pageDriver\&vd_source=d87be07aa170c6f76058fa2663ca0da0 "空降")>
-   [x] 115[索引的数据结构](索引的数据结构_nMQimr9uNRBVw83GfDLoWR.md "索引的数据结构")
-   [x] P113[存储引擎](存储引擎_3BumHhg2TQuHhxjPDw2kof.md "存储引擎") <[空降](https://www.bilibili.com/video/BV1iq4y1u7vj?p=113\&spm_id_from=pageDriver\&vd_source=d87be07aa170c6f76058fa2663ca0da0 "空降")>
    -   [x] \[对比][InnoDB](InnoDB_9AbdCV6Ly4n3LfXoMKs849.md "InnoDB")|[MyISAM](MyISAM_qq8DJDUoJfyD9mhogWGFNQ.md "MyISAM")
    -   [x] P114存储引擎介绍 <[空降](https://www.bilibili.com/video/BV1iq4y1u7vj?p=114\&t=1.0 "空降")>
-   [x] P112MySQL逻辑架构>Oracle中的SQL执行流程(了解) <[空降](https://www.bilibili.com/video/BV1iq4y1u7vj?p=112\&spm_id_from=pageDriver\&vd_source=d87be07aa170c6f76058fa2663ca0da0 "空降")>
-   [x] P111MySQL逻辑架构>MySQL8.0、MySQL5.7中SQL执行原理<[空降](https://www.bilibili.com/video/BV1iq4y1u7vj?p=111\&spm_id_from=pageDriver\&vd_source=d87be07aa170c6f76058fa2663ca0da0 "空降")>
-   [x] P110[MySQL逻辑架构](MySQL逻辑架构_9brzyg5amWc13PMAS8DU6n.md "MySQL逻辑架构")
    -   [ ] P110MySQL逻辑架构>SQL执行流程 <[空降](https://www.bilibili.com/video/BV1iq4y1u7vj?p=110\&spm_id_from=pageDriver\&vd_source=d87be07aa170c6f76058fa2663ca0da0 "空降")>  <面试> <糢糊>

        P111MySQL逻辑架构>MySQL8.0、MySQL5.7中SQL执行原理<[空降](https://www.bilibili.com/video/BV1iq4y1u7vj?p=111\&spm_id_from=pageDriver\&vd_source=d87be07aa170c6f76058fa2663ca0da0 "空降")>

        P112MySQL逻辑架构>Oracle中的SQL执行流程(了解) <[空降](https://www.bilibili.com/video/BV1iq4y1u7vj?p=112\&spm_id_from=pageDriver\&vd_source=d87be07aa170c6f76058fa2663ca0da0 "空降")>
-   P105-108 权限管理，用户角色管理
-   [x] P108角色的使用

    [https://www.bilibili.com/video/BV1iq4y1u7vj?p=108\&spm\_id\_from=pageDriver\&vd\_source=d87be07aa170c6f76058fa2663ca0da0](https://www.bilibili.com/video/BV1iq4y1u7vj?p=108\&spm_id_from=pageDriver\&vd_source=d87be07aa170c6f76058fa2663ca0da0 "https://www.bilibili.com/video/BV1iq4y1u7vj?p=108\&spm_id_from=pageDriver\&vd_source=d87be07aa170c6f76058fa2663ca0da0")
-   [x] P107权限管理与访问控制(粗讲)

    (可能需要回看)
-   [x] P106用户管理
-   [x] P105[MySQL用户与权限管理](MySQL用户与权限管理_gQnQcuBHQzU9XK6dDjF58S.md "MySQL用户与权限管理")

    [https://www.bilibili.com/video/BV1iq4y1u7vj?p=105\&t=451.1](https://www.bilibili.com/video/BV1iq4y1u7vj?p=105\&t=451.1 "https://www.bilibili.com/video/BV1iq4y1u7vj?p=105\&t=451.1")

    [https://www.bilibili.com/video/BV1iq4y1u7vj?p=105\&spm\_id\_from=pageDriver\&vd\_source=d87be07aa170c6f76058fa2663ca0da0](https://www.bilibili.com/video/BV1iq4y1u7vj?p=105\&spm_id_from=pageDriver\&vd_source=d87be07aa170c6f76058fa2663ca0da0 "https://www.bilibili.com/video/BV1iq4y1u7vj?p=105\&spm_id_from=pageDriver\&vd_source=d87be07aa170c6f76058fa2663ca0da0")
-   P96-103MySQL的Linux环境搭建
-   [x] P104[MySQL数据库和文件系统的关系](MySQL数据库和文件系统的关系_qMvZLR9SR2tikjpZmbVXSf.md "MySQL数据库和文件系统的关系")
-   [x] P103SQL大小写规范

    [https://www.bilibili.com/video/BV1iq4y1u7vj?p=103\&t=113.4](https://www.bilibili.com/video/BV1iq4y1u7vj?p=103\&t=113.4 "https://www.bilibili.com/video/BV1iq4y1u7vj?p=103\&t=113.4")
-   [x] P102字符集与比较规则

    [https://www.bilibili.com/video/BV1iq4y1u7vj?p=102\&vd\_source=d87be07aa170c6f76058fa2663ca0da0](https://www.bilibili.com/video/BV1iq4y1u7vj?p=102\&vd_source=d87be07aa170c6f76058fa2663ca0da0 "https://www.bilibili.com/video/BV1iq4y1u7vj?p=102\&vd_source=d87be07aa170c6f76058fa2663ca0da0")
-   [x] P101字符集的修改

    [https://www.bilibili.com/video/BV1iq4y1u7vj?p=101\&t=1.4](https://www.bilibili.com/video/BV1iq4y1u7vj?p=101\&t=1.4 "https://www.bilibili.com/video/BV1iq4y1u7vj?p=101\&t=1.4")
-   [x] P100远程连接MySQL
-   [x] P99[MySQL安装与卸载](MySQL安装与卸载_kjQ9fg6MGpYnrJ1KRbdimn.md "MySQL安装与卸载")
    -   [x] CenOS7安装MySQL5.7
    -   [x] CenOS8安装MySQL8.0
    -   [ ] [https://www.bilibili.com/video/BV1iq4y1u7vj?p=99\&t=769.6](https://www.bilibili.com/video/BV1iq4y1u7vj?p=99\&t=769.6 "https://www.bilibili.com/video/BV1iq4y1u7vj?p=99\&t=769.6")
-   [x] P98[MySQL安装与卸载](MySQL安装与卸载_kjQ9fg6MGpYnrJ1KRbdimn.md "MySQL安装与卸载")-卸载

    2022-07-24
-   [x] P97

    [https://www.bilibili.com/video/BV1iq4y1u7vj?p=97\&t=3.3](https://www.bilibili.com/video/BV1iq4y1u7vj?p=97\&t=3.3 "https://www.bilibili.com/video/BV1iq4y1u7vj?p=97\&t=3.3")

    2022-07-24
    -   [x] 准备工作虚拟机及操作系统
    -   [x] 网络问题处理
-   [x] P96

    [https://www.bilibili.com/video/BV1iq4y1u7vj?p=96\&t=4.4](https://www.bilibili.com/video/BV1iq4y1u7vj?p=96\&t=4.4 "https://www.bilibili.com/video/BV1iq4y1u7vj?p=96\&t=4.4")

<!---->

-   **待做练习**

    🔳🔳⬜️⬜️⬜️⬜️⬜️⬜️⬜️⬜️ 16%
    -   [ ] [MySQL触发器](MySQL触发器_tsVYu7xorGRWMgxsSpTEVa.md "MySQL触发器")练习

        [https://www.bilibili.com/video/BV1iq4y1u7vj?p=93\&t=1157.8](https://www.bilibili.com/video/BV1iq4y1u7vj?p=93\&t=1157.8 "https://www.bilibili.com/video/BV1iq4y1u7vj?p=93\&t=1157.8")
    -   [ ] [MySQL 变量&流程控制&游标](<MySQL 变量&流程控制&游标_gNhntmsjGCebXAqKs2UX6Y.md> "MySQL 变量&流程控制&游标")练习

        [https://www.bilibili.com/video/BV1iq4y1u7vj?p=91\&spm\_id\_from=pageDriver\&vd\_source=d87be07aa170c6f76058fa2663ca0da0](https://www.bilibili.com/video/BV1iq4y1u7vj?p=91\&spm_id_from=pageDriver\&vd_source=d87be07aa170c6f76058fa2663ca0da0 "https://www.bilibili.com/video/BV1iq4y1u7vj?p=91\&spm_id_from=pageDriver\&vd_source=d87be07aa170c6f76058fa2663ca0da0")
    -   [ ] [MySQL存储过程与存储函数](MySQL存储过程与存储函数_qppGQm17ZfBkCWyfr2gtMn.md "MySQL存储过程与存储函数")练习

        [https://www.bilibili.com/video/BV1iq4y1u7vj?p=84\&t=1582.7](https://www.bilibili.com/video/BV1iq4y1u7vj?p=84\&t=1582.7 "https://www.bilibili.com/video/BV1iq4y1u7vj?p=84\&t=1582.7")

        [https://www.bilibili.com/video/BV1iq4y1u7vj?p=82\&t=17.1](https://www.bilibili.com/video/BV1iq4y1u7vj?p=82\&t=17.1 "https://www.bilibili.com/video/BV1iq4y1u7vj?p=82\&t=17.1")
    -   [ ] &#x20;视图练习

        [https://www.bilibili.com/video/BV1iq4y1u7vj?p=77\&vd\_source=d87be07aa170c6f76058fa2663ca0da0](https://www.bilibili.com/video/BV1iq4y1u7vj?p=77\&vd_source=d87be07aa170c6f76058fa2663ca0da0 "https://www.bilibili.com/video/BV1iq4y1u7vj?p=77\&vd_source=d87be07aa170c6f76058fa2663ca0da0")
    -   [ ] 约束练习

        [https://www.bilibili.com/video/BV1iq4y1u7vj?p=73\&t=11.0](https://www.bilibili.com/video/BV1iq4y1u7vj?p=73\&t=11.0 "https://www.bilibili.com/video/BV1iq4y1u7vj?p=73\&t=11.0")
    -   [x] 子查询练习
        -   [x] [空降](https://www.bilibili.com/video/BV1iq4y1u7vj?p=47\&t=2.6 "空降")练习1

            [https://www.bilibili.com/video/BV1iq4y1u7vj?p=48\&t=430.1](https://www.bilibili.com/video/BV1iq4y1u7vj?p=48\&t=430.1 "https://www.bilibili.com/video/BV1iq4y1u7vj?p=48\&t=430.1")&#x20;
        -   [x] [空降](https://www.bilibili.com/video/BV1iq4y1u7vj?p=48\&t=0.7 "空降")练习2

🔳🔳🔳🔳🔳🔳🔳🔳🔳🔳 100%

-   [x] [MySQL8.0其他新特性](MySQL8.0其他新特性_bWdTBZBoU24DVN4DAjVNth.md "MySQL8.0其他新特性")
    -   [x] [MySQL8.0窗口函数(新特性)](MySQL8.0窗口函数\(新特性\)_frtiJ7ZqWt58SrsqMnaxox.md "MySQL8.0窗口函数(新特性)")&#x20;

        [https://www.bilibili.com/video/BV1iq4y1u7vj?p=94\&t=2385.1](https://www.bilibili.com/video/BV1iq4y1u7vj?p=94\&t=2385.1 "https://www.bilibili.com/video/BV1iq4y1u7vj?p=94\&t=2385.1")

        [https://www.bilibili.com/video/BV1iq4y1u7vj?p=94\&t=1265.8](https://www.bilibili.com/video/BV1iq4y1u7vj?p=94\&t=1265.8 "https://www.bilibili.com/video/BV1iq4y1u7vj?p=94\&t=1265.8")
    -   [x] [MySQL8.0公用表表达式(新特性)](MySQL8.0公用表表达式\(新特性\)_j43y2j7nKaypyK3MnMXVfC.md "MySQL8.0公用表表达式(新特性)")
    [https://www.bilibili.com/video/BV1iq4y1u7vj?p=94\&spm\_id\_from=pageDriver\&vd\_source=d87be07aa170c6f76058fa2663ca0da0](https://www.bilibili.com/video/BV1iq4y1u7vj?p=94\&spm_id_from=pageDriver\&vd_source=d87be07aa170c6f76058fa2663ca0da0 "https://www.bilibili.com/video/BV1iq4y1u7vj?p=94\&spm_id_from=pageDriver\&vd_source=d87be07aa170c6f76058fa2663ca0da0")
-   [x] [MySQL触发器](MySQL触发器_tsVYu7xorGRWMgxsSpTEVa.md "MySQL触发器")

    [https://www.bilibili.com/video/BV1iq4y1u7vj?p=92\&spm\_id\_from=pageDriver\&vd\_source=d87be07aa170c6f76058fa2663ca0da0](https://www.bilibili.com/video/BV1iq4y1u7vj?p=92\&spm_id_from=pageDriver\&vd_source=d87be07aa170c6f76058fa2663ca0da0 "https://www.bilibili.com/video/BV1iq4y1u7vj?p=92\&spm_id_from=pageDriver\&vd_source=d87be07aa170c6f76058fa2663ca0da0")
-   [x] [MySQL 变量&流程控制&游标](<MySQL 变量&流程控制&游标_gNhntmsjGCebXAqKs2UX6Y.md> "MySQL 变量&流程控制&游标")

    [https://www.bilibili.com/video/BV1iq4y1u7vj?p=86\&t=2.0](https://www.bilibili.com/video/BV1iq4y1u7vj?p=86\&t=2.0 "https://www.bilibili.com/video/BV1iq4y1u7vj?p=86\&t=2.0")
-   [x] [MySQL存储过程与存储函数](MySQL存储过程与存储函数_qppGQm17ZfBkCWyfr2gtMn.md "MySQL存储过程与存储函数")

    [https://www.bilibili.com/video/BV1iq4y1u7vj?p=81\&t=914.0](https://www.bilibili.com/video/BV1iq4y1u7vj?p=81\&t=914.0 "https://www.bilibili.com/video/BV1iq4y1u7vj?p=81\&t=914.0")

    [https://www.bilibili.com/video/BV1iq4y1u7vj?p=80\&t=268.1](https://www.bilibili.com/video/BV1iq4y1u7vj?p=80\&t=268.1 "https://www.bilibili.com/video/BV1iq4y1u7vj?p=80\&t=268.1")

    [https://www.bilibili.com/video/BV1iq4y1u7vj?p=78\&vd\_source=d87be07aa170c6f76058fa2663ca0da0](https://www.bilibili.com/video/BV1iq4y1u7vj?p=78\&vd_source=d87be07aa170c6f76058fa2663ca0da0 "https://www.bilibili.com/video/BV1iq4y1u7vj?p=78\&vd_source=d87be07aa170c6f76058fa2663ca0da0")
-   [x] [MySQL视图(VIEW)](MySQL视图\(VIEW\)_a5fmB1ZArvessdnorPVmnY.md "MySQL视图(VIEW)")

    [https://www.bilibili.com/video/BV1iq4y1u7vj?p=75\&t=1.5](https://www.bilibili.com/video/BV1iq4y1u7vj?p=75\&t=1.5 "https://www.bilibili.com/video/BV1iq4y1u7vj?p=75\&t=1.5")
-   [x] [MySQL约束](MySQL约束_qCpN3odMSsEtbzWnsMoNsV.md "MySQL约束")
    -   [x] 示例：创建表时 加唯一性约束，加表级复合约束，指定约束名`f1_f2_cst`,表示`f1`和`f2`将不能有重复的组合  \[`CREATE TABLE`,表级约束]验证
    -   [x] **`FOREIGN KEY`**

        [https://www.bilibili.com/video/BV1iq4y1u7vj?p=69\&t=1029.9](https://www.bilibili.com/video/BV1iq4y1u7vj?p=69\&t=1029.9 "https://www.bilibili.com/video/BV1iq4y1u7vj?p=69\&t=1029.9")
    [https://www.bilibili.com/video/BV1iq4y1u7vj?p=68\&t=1016.9](https://www.bilibili.com/video/BV1iq4y1u7vj?p=68\&t=1016.9 "https://www.bilibili.com/video/BV1iq4y1u7vj?p=68\&t=1016.9")

    [https://www.bilibili.com/video/BV1iq4y1u7vj?p=66\&spm\_id\_from=pageDriver\&vd\_source=d87be07aa170c6f76058fa2663ca0da0](https://www.bilibili.com/video/BV1iq4y1u7vj?p=66\&spm_id_from=pageDriver\&vd_source=d87be07aa170c6f76058fa2663ca0da0 "https://www.bilibili.com/video/BV1iq4y1u7vj?p=66\&spm_id_from=pageDriver\&vd_source=d87be07aa170c6f76058fa2663ca0da0")
-   [x] [MySQL数据类型](MySQL数据类型_vnVkhcu93hNWvdzSgY9rum.md "MySQL数据类型")

    [https://www.bilibili.com/video/BV1iq4y1u7vj?p=64\&t=1019.4](https://www.bilibili.com/video/BV1iq4y1u7vj?p=64\&t=1019.4 "https://www.bilibili.com/video/BV1iq4y1u7vj?p=64\&t=1019.4")

    [https://www.bilibili.com/video/BV1iq4y1u7vj?p=63\&t=70.6](https://www.bilibili.com/video/BV1iq4y1u7vj?p=63\&t=70.6 "https://www.bilibili.com/video/BV1iq4y1u7vj?p=63\&t=70.6")

    [https://www.bilibili.com/video/BV1iq4y1u7vj?p=61\&t=1447.3](https://www.bilibili.com/video/BV1iq4y1u7vj?p=61\&t=1447.3 "https://www.bilibili.com/video/BV1iq4y1u7vj?p=61\&t=1447.3")

    [https://www.bilibili.com/video/BV1iq4y1u7vj?p=60\&t=1.6](https://www.bilibili.com/video/BV1iq4y1u7vj?p=60\&t=1.6 "https://www.bilibili.com/video/BV1iq4y1u7vj?p=60\&t=1.6")

[https://www.bilibili.com/video/BV1iq4y1u7vj?p=59\&t=2.2](https://www.bilibili.com/video/BV1iq4y1u7vj?p=59\&t=2.2 "https://www.bilibili.com/video/BV1iq4y1u7vj?p=59\&t=2.2")

-   [x] DML

    [https://www.bilibili.com/video/BV1iq4y1u7vj?p=56\&spm\_id\_from=pageDriver\&vd\_source=d87be07aa170c6f76058fa2663ca0da0](https://www.bilibili.com/video/BV1iq4y1u7vj?p=56\&spm_id_from=pageDriver\&vd_source=d87be07aa170c6f76058fa2663ca0da0 "https://www.bilibili.com/video/BV1iq4y1u7vj?p=56\&spm_id_from=pageDriver\&vd_source=d87be07aa170c6f76058fa2663ca0da0")

    [https://www.bilibili.com/video/BV1iq4y1u7vj?p=55\&t=60.6](https://www.bilibili.com/video/BV1iq4y1u7vj?p=55\&t=60.6 "https://www.bilibili.com/video/BV1iq4y1u7vj?p=55\&t=60.6")

    [https://www.bilibili.com/video/BV1iq4y1u7vj?p=52\&t=998.5](https://www.bilibili.com/video/BV1iq4y1u7vj?p=52\&t=998.5 "https://www.bilibili.com/video/BV1iq4y1u7vj?p=52\&t=998.5")
-   [x] 增删改

    [https://www.bilibili.com/video/BV1iq4y1u7vj?p=52\&t=526.6](https://www.bilibili.com/video/BV1iq4y1u7vj?p=52\&t=526.6 "https://www.bilibili.com/video/BV1iq4y1u7vj?p=52\&t=526.6")

    [https://www.bilibili.com/video/BV1iq4y1u7vj?p=51\&t=86.3](https://www.bilibili.com/video/BV1iq4y1u7vj?p=51\&t=86.3 "https://www.bilibili.com/video/BV1iq4y1u7vj?p=51\&t=86.3")

    [https://www.bilibili.com/video/BV1iq4y1u7vj?p=50\&t=1119.2](https://www.bilibili.com/video/BV1iq4y1u7vj?p=50\&t=1119.2 "https://www.bilibili.com/video/BV1iq4y1u7vj?p=50\&t=1119.2")

    [https://www.bilibili.com/video/BV1iq4y1u7vj?p=50\&t=531.0](https://www.bilibili.com/video/BV1iq4y1u7vj?p=50\&t=531.0 "https://www.bilibili.com/video/BV1iq4y1u7vj?p=50\&t=531.0")

    [https://www.bilibili.com/video/BV1iq4y1u7vj?p=49\&t=0.7](https://www.bilibili.com/video/BV1iq4y1u7vj?p=49\&t=0.7 "https://www.bilibili.com/video/BV1iq4y1u7vj?p=49\&t=0.7")
-   [x] 查询

    [MySQL子查询](MySQL子查询_tTVo6FJmWoSzQA5qNBqRUo.md "MySQL子查询")
    -   [x] 子查询练习
        -   [x] [空降](https://www.bilibili.com/video/BV1iq4y1u7vj?p=47\&t=2.6 "空降")练习1

            [https://www.bilibili.com/video/BV1iq4y1u7vj?p=48\&t=430.1](https://www.bilibili.com/video/BV1iq4y1u7vj?p=48\&t=430.1 "https://www.bilibili.com/video/BV1iq4y1u7vj?p=48\&t=430.1")&#x20;
        -   [x] [空降](https://www.bilibili.com/video/BV1iq4y1u7vj?p=48\&t=0.7 "空降")练习2
    [https://www.bilibili.com/video/BV1iq4y1u7vj?p=45\&t=900.0](https://www.bilibili.com/video/BV1iq4y1u7vj?p=45\&t=900.0 "https://www.bilibili.com/video/BV1iq4y1u7vj?p=45\&t=900.0")

    [https://www.bilibili.com/video/BV1iq4y1u7vj?p=43](https://www.bilibili.com/video/BV1iq4y1u7vj?p=43 "https://www.bilibili.com/video/BV1iq4y1u7vj?p=43")
-   [x] 多行函数练习[https://www.bilibili.com/video/BV1iq4y1u7vj?p=42\&spm\_id\_from=pageDriver](https://www.bilibili.com/video/BV1iq4y1u7vj?p=42\&spm_id_from=pageDriver "https://www.bilibili.com/video/BV1iq4y1u7vj?p=42\&spm_id_from=pageDriver")
-   [x] [https://www.bilibili.com/video/BV1iq4y1u7vj?p=41\&t=5.4](https://www.bilibili.com/video/BV1iq4y1u7vj?p=41\&t=5.4 "https://www.bilibili.com/video/BV1iq4y1u7vj?p=41\&t=5.4")
-   [x] [https://www.bilibili.com/video/BV1iq4y1u7vj?p=39\&t=2396.9](https://www.bilibili.com/video/BV1iq4y1u7vj?p=39\&t=2396.9 "https://www.bilibili.com/video/BV1iq4y1u7vj?p=39\&t=2396.9")
-   [x] MySQL单行函数练习[https://www.bilibili.com/video/BV1iq4y1u7vj?p=38\&spm\_id\_from=pageDriver](https://www.bilibili.com/video/BV1iq4y1u7vj?p=38\&spm_id_from=pageDriver "https://www.bilibili.com/video/BV1iq4y1u7vj?p=38\&spm_id_from=pageDriver")
-   [x] [https://www.bilibili.com/video/BV1iq4y1u7vj?p=36\&t=1085.4](https://www.bilibili.com/video/BV1iq4y1u7vj?p=36\&t=1085.4 "https://www.bilibili.com/video/BV1iq4y1u7vj?p=36\&t=1085.4")
-   [x] [https://www.bilibili.com/video/BV1iq4y1u7vj?p=33\&t=1984.0](https://www.bilibili.com/video/BV1iq4y1u7vj?p=33\&t=1984.0 "https://www.bilibili.com/video/BV1iq4y1u7vj?p=33\&t=1984.0")
-   [x] 表多表查询练习：[https://www.bilibili.com/video/BV1iq4y1u7vj?p=31\&t=26.6](https://www.bilibili.com/video/BV1iq4y1u7vj?p=31\&t=26.6 "https://www.bilibili.com/video/BV1iq4y1u7vj?p=31\&t=26.6")
-   [x] [https://www.bilibili.com/video/BV1iq4y1u7vj?p=30\&t=32.0](https://www.bilibili.com/video/BV1iq4y1u7vj?p=30\&t=32.0 "https://www.bilibili.com/video/BV1iq4y1u7vj?p=30\&t=32.0")
-   [x] MySQL的Linux安装

    [https://www.bilibili.com/video/BV1iq4y1u7vj?p=97\&t=208.7](https://www.bilibili.com/video/BV1iq4y1u7vj?p=97\&t=208.7 "https://www.bilibili.com/video/BV1iq4y1u7vj?p=97\&t=208.7")
-   [x] 远程连接

    [https://www.bilibili.com/video/BV1iq4y1u7vj?p=100\&t=448.2](https://www.bilibili.com/video/BV1iq4y1u7vj?p=100\&t=448.2 "https://www.bilibili.com/video/BV1iq4y1u7vj?p=100\&t=448.2")
-   [x] [https://www.bilibili.com/video/BV1iq4y1u7vj?p=29\&t=24.7](https://www.bilibili.com/video/BV1iq4y1u7vj?p=29\&t=24.7 "https://www.bilibili.com/video/BV1iq4y1u7vj?p=29\&t=24.7") \[重看]
-   [x] [https://www.bilibili.com/video/BV1iq4y1u7vj?p=29\&t=170.5](https://www.bilibili.com/video/BV1iq4y1u7vj?p=29\&t=170.5 "https://www.bilibili.com/video/BV1iq4y1u7vj?p=29\&t=170.5")
-   [x] [https://www.bilibili.com/video/BV1iq4y1u7vj?p=25\&t=22.2](https://www.bilibili.com/video/BV1iq4y1u7vj?p=25\&t=22.2 "https://www.bilibili.com/video/BV1iq4y1u7vj?p=25\&t=22.2")
-   [x] [https://www.bilibili.com/video/BV1iq4y1u7vj?p=23\&t=992.0](https://www.bilibili.com/video/BV1iq4y1u7vj?p=23\&t=992.0 "https://www.bilibili.com/video/BV1iq4y1u7vj?p=23\&t=992.0")
-   [x] [https://www.bilibili.com/video/BV1iq4y1u7vj?p=22\&t=528.0](https://www.bilibili.com/video/BV1iq4y1u7vj?p=22\&t=528.0 "https://www.bilibili.com/video/BV1iq4y1u7vj?p=22\&t=528.0")
-   [x] [https://www.bilibili.com/video/BV1iq4y1u7vj?p=22\&t=3.9](https://www.bilibili.com/video/BV1iq4y1u7vj?p=22\&t=3.9 "https://www.bilibili.com/video/BV1iq4y1u7vj?p=22\&t=3.9")
-   [x] [https://www.bilibili.com/video/BV1iq4y1u7vj?p=14\&spm\_id\_from=pageDriver](https://www.bilibili.com/video/BV1iq4y1u7vj?p=14\&spm_id_from=pageDriver "https://www.bilibili.com/video/BV1iq4y1u7vj?p=14\&spm_id_from=pageDriver")
-   [x] [https://www.bilibili.com/video/BV1iq4y1u7vj?p=3\&spm\_id\_from=pageDriver](https://www.bilibili.com/video/BV1iq4y1u7vj?p=3\&spm_id_from=pageDriver "https://www.bilibili.com/video/BV1iq4y1u7vj?p=3\&spm_id_from=pageDriver")





[^注释1]: [https://www.bilibili.com/video/BV1iq4y1u7vj?p=171\&spm\_id\_from=pageDriver\&vd\_source=d87be07aa170c6f76058fa2663ca0da0\&t=201.2](https://www.bilibili.com/video/BV1iq4y1u7vj?p=171\&spm_id_from=pageDriver\&vd_source=d87be07aa170c6f76058fa2663ca0da0\&t=201.2 "https://www.bilibili.com/video/BV1iq4y1u7vj?p=171\&spm_id_from=pageDriver\&vd_source=d87be07aa170c6f76058fa2663ca0da0\&t=201.2")
