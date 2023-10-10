# \[win]gre(修改注册表命令)

<https://docs.microsoft.com/zh-cn/windows-server/administration/windows-commands/reg>

语法

[reg add](<reg add_fMCGt4XNt7dUV4D5JRozyT.md> "reg add")

reg add   向注册表中添加新的子项或条目。
reg add：修改windows远程桌面端口3389为3000

reg compare   比较指定的注册表子项或条目。


reg copy   将注册表项复制到本地或远程计算机上的指定位置。


reg delete   删除注册表中的一个或一些项。


reg export   将本地计算机的指定子项、项和值复制到文件中，以便传输到其他服务器。


reg import   将包含导出的注册表子项、项和值的文件的内容复制到本地计算机的注册表中。


reg load   将保存的子项和项写入注册表中的不同子项。


reg query   返回位于注册表中指定子项下的子子项和条目的列表。


reg restore   将保存的子项和项写入注册表。


reg save   在指定的文件中保存指定子项、项和注册表值的副本。


reg unload   删除使用 reg load 操作加载的注册表部分。

***

```bash
REG Operation [Parameter List]

  Operation  [ QUERY   | ADD    | DELETE  | COPY    |
               SAVE    | LOAD   | UNLOAD  | RESTORE |
               COMPARE | EXPORT | IMPORT  | FLAGS ]

返回代码: (除了 REG COMPARE)

  0 - 成功
  1 - 失败

要得到有关某个操作的帮助，请键入:

  REG Operation /?

例如:

  REG QUERY /?
  REG ADD /?
  REG DELETE /?
  REG COPY /?
  REG SAVE /?
  REG RESTORE /?
  REG LOAD /?
  REG UNLOAD /?
  REG COMPARE /?
  REG EXPORT /?
  REG IMPORT /?
  REG FLAGS /?
```





