# \[win]?powercfg



#### 1、定时关机

# 注：/s 关机， /t 后面接时间，单位是秒&#x20;

shutdown /s /t 3600  #一个小时后关机

shutdown -a #取消定时关机

注："shutdown /h"是立即进入休眠的命令，但/h参数不能与/t连用，故不能用shutdown实现定时休眠的功能。/h可与/f连用，/f 表示强制关闭正在运行的应用程序而不事先警告用户。

#### 2、定时休眠

以管理员身份运行[cmd](https://so.csdn.net/so/search?q=cmd\&spm=1001.2101.3001.7020 "cmd")或者powershell

powercfg -h on

schtasks /create /tn my-standby /tr "rundll32.exe powrprof.dll,SetSuspendState" /sc once /st 23:30

schtasks /delete /tn my-standby # 取消定时任务

#### 3、定时睡眠（定时待机）：

以管理员身份运行cmd或者powershell

powercfg -h off

schtasks /create /tn my-standby /tr "rundll32.exe powrprof.dll,SetSuspendState" /sc once /st 23:30

注：查看休眠是否开启：powercfg /a

在"powercfg -h on"状态下，以管理员身份运行"rundll32.exe powrprof.dll,SetSuspendState 0,1,0"不会进入睡眠，而是休眠
