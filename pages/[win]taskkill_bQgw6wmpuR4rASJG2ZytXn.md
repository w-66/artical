# \[win]taskkill

停止程序；终止程序；停止应用

taskkaill结束一个或多个任务或进程。



示例：关闭进程

```纯文本
@echo off
taskkill /f /im frpc.exe
taskkill /f /im explorer.exe

```

<https://docs.microsoft.com/zh-cn/windows-server/administration/windows-commands/taskkill>

```bash
taskkill [/s <computer> [/u [<domain>\]<username> [/p [<password>]]]] {[/fi <filter>] [...] [/pid <processID> | /im <imagename>]} [/f] [/t]
```

| 参数                      | 说明                                                                                                                     |
| ----------------------- | ---------------------------------------------------------------------------------------------------------------------- |
| /s `<computer>`         | 指定远程计算机的名称或 IP 地址 (不使用反) 。 默认为本地计算机。                                                                                   |
| /u `<domain><username>` | 使用 由 或 指定的用户的帐户权限运行 `<username>` 命令 `<domain><username>` 。 只有在 **还指定了 /s** 时， **才能指定 /u** 参数。 默认值是当前登录到发出命令的计算机的用户的权限。 |
| /p `<password>`         | 指定在 **/u** 参数中指定的用户帐户的密码。                                                                                              |
| /fi `<filter>`          | 应用筛选器以选择一组任务。 可以使用多个筛选器或使用通配符 () `*` 指定所有任务或映像名称。 本文的"筛选器名称、运算符和值 **"部分列出了** 有效筛选器。                                    |
| /pid `<processID>`      | 指定要终止的进程的进程 ID。                                                                                                        |
| /im `<imagename>`       | 指定要终止的进程的映像名称。 使用通配符 `*` () 指定所有图像名称。                                                                                  |
| /f                      | 指定强制结束进程。 对于远程进程，将忽略此参数;所有远程进程都强制结束。                                                                                   |
| /t                      | 结束指定的进程及其启动的任何子进程。                                                                                                     |

| 筛选器名称       | 有效运算符             | 有效 (值)                                                           |
| ----------- | ----------------- | ---------------------------------------------------------------- |
| 状态          | eq、ne             | `RUNNING \| NOT RESPONDING \| UNKNOWN`                           |
| IMAGENAME   | eq、ne             | 映像名称                                                             |
| PID         | eq、ne、gt、lt、ge、le | PID 值                                                            |
| SESSION     | eq、ne、gt、lt、ge、le | 会话号                                                              |
| CPUtime     | eq、ne、gt、lt、ge、le | *HH：MM：SS* 格式的 CPU 时间，其中 *MM* 和 *SS* 介于 0 到 59 之间 *，HH* 是任何无符号数字 |
| MEMUSAGE    | eq、ne、gt、lt、ge、le | 内存使用量 （以 KB 为单位）                                                 |
| USERNAME    | eq、ne             | 任何有效的用户名 (`<user>` 或 `<domain\user>`)                            |
| 服务          | eq、ne             | 服务名称                                                             |
| WINDOWTITLE | eq、ne             | 窗口标题                                                             |
| 模块          | eq、ne             | DLL 名称                                                           |
