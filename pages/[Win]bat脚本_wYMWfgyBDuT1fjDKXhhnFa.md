# \[Win]bat脚本

## windows command

#### windows command

| command                                                                                                       |
| ------------------------------------------------------------------------------------------------------------- |
| [\[win\]set](\[win]set_nhAx2RJgRxjbkZkavKgYAY.md "\[win]set")                                                 |
| [\[win\]setx](\[win]setx_hN3bmCPzaq5MFsuSkE4ktF.md "\[win]setx")                                              |
| [\[win\]?powercfg](\[win]-powercfg_4qiY2eG9m38kiX4Uw7hcLA.md "\[win]?powercfg")                               |
| [\[win\]echo](\[win]echo_X4RNB6GgMsuQUbHanFjkt.md "\[win]echo")                                               |
| [\[win\]move](\[win]move_7DA7qzsgE7frzH2E12MTBy.md "\[win]move")                                              |
| [\[win\]ren](\[win]ren_8aZqR6WpJXYvWueToahRuX.md "\[win]ren")                                                 |
| [pause(暂停)](pause\(暂停\)_t8jL3LEmVzhCSqGWM4qdSv.md "pause(暂停)")                                                |
| [\[win\]format](\[win]format_9EDArM4EBHvxv4zut3RGBS.md "\[win]format")                                        |
| [\[win\]rmdir](\[win]rmdir_mZ5kLCK4g2gWw5Z8pHMh41.md "\[win]rmdir")                                           |
| [\[Win\]wmic](\[Win]wmic_xvZtWf1oJZ6uk8mkNyHddu.md "\[Win]wmic")                                              |
| [\[Win\]rem](\[Win]rem_naV53PLvkMdwBX8ALp9nsc.md "\[Win]rem")                                                 |
| [\[Win\]set-executionpolicy](\[Win]set-executionpolicy_f8ns1rZM8Qrd2oNet8LKFo.md "\[Win]set-executionpolicy") |
| [\[Win\]mkdir](\[Win]mkdir_n68HJ1B2aii5hVXw4DFWne.md "\[Win]mkdir")                                           |
| [\[Win\]md](\[Win]md_4XZRtvbjSVqysTbhM2FHbn.md "\[Win]md")                                                    |

windows command

taskkaill结束一个或多个任务或进程。

del 文件删除命令&#x20;

> 帮助如同Linux中`-help` 使用 `/?`

-   参考学习

    <https://www.lmdouble.com/category/windows_skill/dosbat>

    [批处理之家](http://www.bathome.net/ "批处理之家")

    [\[bat\]批处理(It's too old)](<\[bat]批处理(It's too old)_rSzAUFFwmNpsD4iMFfeZFc.md> "\[bat]批处理(It's too old)")

***

-   基础认识

    特殊符号 `"`

***



[\[win\]if](\[win]if_d7LoG9Caz8BwAe8CTpaV2S.md "\[win]if")



# bat问题

-   bat/cmd将命令执行的结果赋值给变量

    [https://www.cnblogs.com/zndxall/p/9188300.html](https://www.cnblogs.com/zndxall/p/9188300.html "https://www.cnblogs.com/zndxall/p/9188300.html")
    -   示例：比如我想把git代码的commitid获取以后加到文件夹上来标记文件夹中的包是哪个git 节点构建得到的。git 命令是git rev-parse --short HEAD
        ```纯文本
        for /F %%i in ('git rev-parse --short HEAD') do ( set commitid=%%i)
        echo commitid=%commitid%
        ```
-   怎么循环执行一条命令 \[bat]`goto`

    [https://zhidao.baidu.com/question/1603543665268707707.html#:\~:text=让bat脚本循环执行有以下两种方法： 第一、可以直接加个%0，即执行本身，实现循环。,第二、用goto命令，去到你要重复的开头，如果要限制次数，可以先set 一个值，循环一次减1，条件命令到0退出，实现循环。](<https://zhidao.baidu.com/question/1603543665268707707.html#:~:text=让bat脚本循环执行有以下两种方法： 第一、可以直接加个%0，即执行本身，实现循环。,第二、用goto命令，去到你要重复的开头，如果要限制次数，可以先set 一个值，循环一次减1，条件命令到0退出，实现循环。> "https://zhidao.baidu.com/question/1603543665268707707.html#:~:text=让bat脚本循环执行有以下两种方法： 第一、可以直接加个%0，即执行本身，实现循环。,第二、用goto命令，去到你要重复的开头，如果要限制次数，可以先set 一个值，循环一次减1，条件命令到0退出，实现循环。")
    ```纯文本
    让bat脚本循环执行有以下两种方法：

    第一、可以直接加个%0，即执行本身，实现循环。
    第二、用goto命令，去到你要重复的开头，如果要限制次数，可以先set 一个值，循环一次减1，条件命令到0退出，实现循环。

    若使用goto命令执行循环，有如下代码可供参考：
    @echo off

    set n=0

    :abc

    set /a n+=1

    if %n%==60 exit

    goto abc
    每次执行n+1，当n=60就退出

    进行跳转，之前可以加上判断条件，判断是否跳到开头继续执行
    ```
    set n=0

    :abc
    echo 1


    set /a n+=1

    if %n%==60 exit

    goto abc
-   重启explorer.exe(需要用到[\[win\]taskkill](\[win]taskkill_bQgw6wmpuR4rASJG2ZytXn.md "\[win]taskkill")、[\[win\]start](\[win]start_p9VtKQG4msmYypRoXHdCwD.md "\[win]start"))
    ```javascript
    taskkill /f /IM explorer.exe
    start explorer.exe
    exit
    ```

[bat 提示y/n确认互交实现](<bat 提示y-n确认互交实现_5SSBW2ADjc2U8bcbisNT4r.md> "bat 提示y/n确认互交实现")

[批处理文件中文出现乱码](批处理文件中文出现乱码_xav7AFQpmXH1aWiQDWnJvQ.md "批处理文件中文出现乱码")

# 变量

系统变量

`%errorlevel%`

自定义变量

`set`

`/p`

用户输入

```纯文本
@echo off
set /p  a="num:"
echo %a%

pause
```

-   示例：bat变量设置
    ```纯文本
    set VARNAME=VALUE
    ```
    ```纯文本
    set MY_VAR=Hello, world!
    echo %MY_VAR%
    del %MY_VAR%

    ```

# bat脚本示例

-   示例：查看当前执行路径`%CD%`%\~dp0
    ```纯文本
    echo %CD%
    echo %~dp0
    >>>
    F:\Code\Project
    F:\Code\Project\

    ```
-   示例：配合nmap持续监控 输入的端口号 在服务端是否开放 \[`set``/p`]
    ```纯文本
    @echo off
    set /p port=inpute port : 
    set n=0

    :abc

    nmap -n -p%port% qwertyui.vip | find "%port%"

    set /a n+=1


    if %n%==60 exit

    goto abc

    ```
    ![](../image/image_YM31L0Pybb.png)
-   桌面图标快捷方式 箭头显示或取消 控制

    取消小箭头

    [1.bat](../file/1_LfEI5cz23f.bat "1.bat")
    ```bash
    reg add "HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\Windows\CurrentVersion\Explorer\Shell Icons" /v 29 /d "%systemroot%\system32\imageres.dll,197" /t reg_sz /f

    taskkill /f /im explorer.exe

    attrib -s -r -h "%userprofile%\AppData\Local\iconcache.db"

    del "%userprofile%\AppData\Local\iconcache.db" /f /q

    start explorer

    pause
    ```
    显示小箭头
    ```bash
    reg delete "HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\Windows\CurrentVersion\Explorer\Shell Icons" /v 29 /f

    taskkill /f /im explorer.exe

    attrib -s -r -h "%userprofile%\AppData\Local\iconcache.db"

    del "%userprofile%\AppData\Local\iconcache.db" /f /q

    start explorer

    pause
    ```

[修改IP（批处理）](修改IP（批处理）_fku6nVP1ki1dwKJZ4GTo24.md "修改IP（批处理）")

-   \[win]manage-bde
-   清楚DNS缓存`ipconfig/flushdns `
-   修改[RDP协议(远程桌面协议)](RDP协议\(远程桌面协议\)_7qd3wai8Zc11Lpyo9SPCLt.md "RDP协议(远程桌面协议)")端口脚本
    ```纯文本
    %1 mshta vbscript:CreateObject("Shell.Application").ShellExecute("cmd.exe","/c %~s0 ::","","runas",1)(window.close)&&exit
    cd /d "%~dp0"
    REG ADD "HKEY_LOCAL_MACHINE\System\CurrentControlSet\Control\Terminal Server\WinStations\RDP-Tcp" /v "PortNumber" /t REG_DWORD /d 3000 /f
    REG ADD "HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\Control\Terminal Server\Wds\rdpwd\Tds\tcp" /v "PortNumber" /t REG_DWORD /d 3000 /f

    ```

&#x20;bat脚本 运行scrcpy

-   \[bat]bat脚本加密


    ```bash
    @echo off
    cls
    color 2a
    :start
    cls
    echo *******************************************************************************
    echo * *
    echo * BAT 加 密 最 终 版 *
    echo * *
    echo *******************************************************************************
    echo.
    echo.
    echo BAT加密最终版为"BAT加密工具"的更新版本, 较上一版加密工具而言有诸多优势:
    echo.
    echo ★ 可以一次性成功加密任何批处理文件, 更省事.
    echo.
    echo ★ 可以由您输入任意需要加密的批处理, 加密灵活性更大.
    echo.
    echo ★ 能够自动判断错误输入, 更加人性化.
    echo.
    echo 说明: 在下面输入需要加密的批处理文件, 直接输入批处理文件名为加密当前目录下的BAT,也可以带路径指定任意BAT. 当前目录下生成的encrypt.bat文件即为加密的批处理.
    echo.
    echo 作者:木林森 QQ:573381312 BYE
    echo.
    echo.
    echo.
    set /p file=请输入需要加密的批处理后按回车键(q=退出):
    if "%file%"=="q" goto quit
    echo %file%|findstr /i "\.bat$">nul && goto go
    echo %file%|findstr /i "\.cmd$">nul && goto go
    cls
    echo ==============
    echo 请正确输入!
    echo ==============
    echo.
    echo.
    echo 按任意键重新输入......
    pause>nul
    goto start
    :go
    if not exist "%file%" goto newly
    if exist encrypt.bat copy encrypt.bat encryptbak.bat
    echo %%%%a %%%%a %%%%a %%%%a %%%%a %%%%a %%%%a %%%%a %%%%a %%%%a %%%%a %%%%a %%%%a %%%%a %%%%a %%%%a %%%%a %%%%a %%%%a %%%%a %%%%a %%%%a %%%%a %%%%a %%%%a %%%%a %%%%a %%%%a %%%%a %%%%a %%%%a %%%%a %%%%a %%%%a %%%%a %%%%a %%%%a %%%%a %%%%a %%%%a %%%%a %%%%a %%%%a %%%%a %%%%a %%%%a %%%%a %%%%a %%%%a %%%%a %%%%a %%%%a %%%%a %%%%a %%%%a %%%%a %%%%a %%%%a %%%%a %%%%a %%%%a %%%%a %%%%a %%%%a %%%%a %%%%a %%%%a %%%%a %%%%a %%%%a %%%%a %%%%a %%%%a %%%%a %%%%a %%%%a %%%%a %%%%a %%%%a %%%%a %%%%a %%%%a %%%%a %%%%a %%%%a %%%%a %%%%a %%%%a %%%%a %%%%a %%%%a %%%%a %%%%a %%%%a %%%%a %%%%a %%%%a %%%%a %%%%a %%%%a %%%%a %%%%a %%%%a %%%%a %%%%a %%%%a %%%%a %%%%a %%%%a %%%%a %%%%a %%%%a %%%%a %%%%a %%%%a %%%%a %%%%a %%%%a %%%%a %%%%a %%%%a %%%%a %%%%a %%%%a %%%%a %%%%a %%%%a %%%%a %%%%a >"%tmp%\encrypt.tmp"
    echo cls>>"%tmp%\encrypt.tmp"
    type "%file%">>"%tmp%\encrypt.tmp"
    setlocal enabledelayedexpansion
    for %%i in ("%tmp%\encrypt.tmp") do (
    echo %%~zi >nul 2>nul
    set size=%%~zi
    set num=!size:~-1!
    set /a mod=!num!%%2
    if !mod! equ 0 (goto even) else (goto odd)
    )
    :even
    copy "%tmp%\encrypt.tmp" encrypt.bat
    del "%tmp%\encrypt.tmp"
    cls
    echo ==========================
    echo 恭喜你, 批处理加密成功^^!
    echo ==========================
    echo.
    echo.
    echo 按任意键退出......
    pause>nul
    goto quit
    :odd
    echo. >>"%tmp%\encrypt.tmp"
    copy "%tmp%\encrypt.tmp" encrypt.bat
    del "%tmp%\encrypt.tmp"
    cls
    echo ==========================
    echo 恭喜你, 批处理加密成功^^!
    echo ==========================
    echo.
    echo.
    echo 按任意键退出......
    pause>nul
    goto quit
    :newly
    cls
    echo ================================
    echo 找不到批处理文件, 请重新输入!
    echo ================================
    echo.
    echo.
    echo 按任意键开始......
    pause>nul
    goto start
    :quit
    exit 
    ```
    -   解密bat
        ```bash
        @echo off
        mode con: cols=80 lines=25
        :index
        color 27
        cls
        echo ╭──────────── ──╮
        echo │ │
        echo ╭─────────┤ BAT 解 密 工 具 ├─────────╮
        echo │ │ │ │
        echo │ ╰────────── ────╯ │
        echo │ │
        echo │ │
        echo │ 本工具用来对混淆文本编码类型的加密批处理进行解密! │
        echo │ │
        echo │ 在下面填入需要解密的批处理按回车键即可. │
        echo │ │
        echo │ 建议直接把待解密的批处理文件拖曳至本窗口释放. │
        echo │ │
        echo │ 解密成功后会在本程序目录下生成"new_待解密文件名.文件后缀名" │
        echo │ 格式的文件. │
        echo │ │
        echo │ 注意: 如果本目录下存在"new_待解密文件名.文件后缀名"的文件, │
        echo │ 将会被替换. │
        echo │ │
        echo │ │
        echo ╰─── ─────────────────────────────╯
        echo.
        set route=%cd%
        set ravel=
        set /p ravel= 请输入要解密的批处理:
        set "ravel=%ravel:"=%"
        if /i "%ravel:~-4%"==".bat" if exist "%ravel%" goto go
        if /i "%ravel:~-4%"==".cmd" if exist "%ravel%" goto go
        cls
        echo ╭──────────╮
        echo ╭─────────┤ 文 件 错 误 ├────────╮
        echo │ ╰──────────╯ │
        echo │ │
        echo │ 指定文件不存在或文件不是批处理类型! │
        echo │ │
        echo │ 按任意键重新输入... │
        echo │ │
        echo ╰───────────────── ───────────╯
        echo.
        echo.
        echo 按任意键重新输入...
        pause >nul
        goto index

        :go
        for /f "tokens=*" %%c in ("%ravel%") do (
        cd /d "%%~dpc"
        if exist "%route%\new_%%~nxc" attrib -s -h -r -a "%route%\new_%%~nxc"
        echo author:pengfei@www.cn-dos.net>"%route%\new_%%~nxc"
        for /f "tokens=*" %%i in (%%~nxc) do (
        echo %%i>>"%route%\new_%%~nxc"
        )
        )
        cls
        echo ╭──────────╮
        echo ╭─────────┤ 解 密 成 功 ├────────╮
        echo │ ╰──────────╯ │
        echo │ │
        echo │ 恭喜, 批处理解密成功! │
        echo │ │
        echo ╰──────────────────── ────────╯
        echo.
        echo.
        echo 按任意键退出...
        pause >nul
        exit 
        ```

-   \[bat]编码格式转换(默认从`ANSI(GB2312)` 转 `UTF-8`，否则需要修改一下)

    使用：直接将要转换的文件拖至bat文件

    [参考](https://blog.csdn.net/weixin_43673589/article/details/109774579 "参考")
    ```powershell
    ::注释
    ::code1=ANSI(GB2312)
    ::code2=Big5
    ::code3=Shift_JIS
    ::code4=EUC-KR
    ::code5=UTF-8
    ::code6=Unicode

    @echo off & setlocal enabledelayedexpansion
    ::设置文件转换前编码类型，请参考上面编码序号，序号5即指code5也就是UTF-8编码
    set aaa=1

    ::设置文件转换后编码类型，请参考上面编码序号，序号1即指code1也就是ANSI(GB2312)编码
    set bbb=5

    ::设置要转换的文件名
    set file=%~nx1
    set wfiles=%file%

    ::开始转换
    echo !aaa!|findstr /be "[1-6]" >nul ||goto :eof
    echo !bbb!|findstr /be "[1-6]" >nul ||goto :eof
    if "!aaa!" == "!bbb!" goto :eof
    echo>MakeBOM.vbs Set objFSO = CreateObject("Scripting.FileSystemObject")
    echo>> MakeBOM.vbs Set objFile = objFSO.CreateTextFile("Unicode.BOM",,true)
    cscript //Nologo MakeBOM.vbs
    set codepth=编码转换后
    md %codepth%\tmp
    :loop
    set vvv=!aaa!
    if "!aaa!" == "6" set vvv=!bbb!
    for /f "tokens=%vvv%" %%a in ("936 950 932 949 65001") do (reg add "HKCU\Console\%%SystemRoot%%_System32_cmd.exe" /v CodePage /t REG_DWORD /d %%a /f >nul)
    if not "!aaa!" == "6" (
    if not "!bbb!" == "6" (
    start /wait /min cmd /u /c "for %%a in (%%wfiles%%) do copy Unicode.BOM tmpfile.tmp&type "%%~fa" >> tmpfile.tmp&move /y tmpfile.tmp %codepth%\tmp\"%%~nxa""
    set aaa=6
    set wfiles=%codepth%\tmp\*
    goto loop
    )
    )
    if "!bbb!" == "6" (
    start /wait /min cmd /u /c "for %%a in (%%wfiles%%) do copy Unicode.BOM tmpfile.tmp&type "%%~fa" >> tmpfile.tmp&move /y tmpfile.tmp %codepth%\"%%~nxa""
    ) else (start /wait /min cmd /c "for %%a in (%%wfiles%%) do type "%%~fa" > %codepth%\"%%~nxa"")
    reg delete "HKCU\Console\%%SystemRoot%%_System32_cmd.exe" /v CodePage /f >nul
    del MakeBOM.vbs
    del Unicode.BOM
    move /y "%codepth%\%file%" "%file%"
    rd /s /q "%codepth%"
    pause
    ```
-   \[bat]示例：持续|循环 测试端口脚本 基于nmap
    ```sql
    @echo off

    set n=0

    :abc

    nmap -n -p443 baidu.com | find "443"

    set /a n+=1


    if %n%==60 exit

    goto abc

    ```





# 碎片

-   \[bat]`goto`

    判断输入的是Y或者N去直接跳转到指定一行执行。`输入Y之后直接跳转到prgrm所在的那一行一直yes从而跳过了echo no那一段。`
    ```纯文本
    @echo off

    :start
    cls
    echo.
    echo 本批处理文件由jueyi5857制作
    echo.
    set /p c=是否继续执行？（Y/N）
    if "%c%"=="Y" goto prgrm
    if "%c%"=="N" goto end
    goto start

    :end
    echo no
    pause

    :prgrm
    echo yes
    pause

    exit

    ```



[以管理员权限运行](以管理员权限运行_vvugEqhS9rT3JSoT1X2LSi.md "以管理员权限运行")

-   无需要确认的命令怎么执行确认

    示例：格式化分区，直接确认
    ```bash
     echo y|format d: /q
    ```
    其中`y`就是自动选择为yes确认
-   开启自启
    1.  在文件资源管理器中

        `C:\ProgramData\Microsoft\Windows\Start Menu\Programs\StartUp`

        添加快捷方式或者是程序既可
    2.  注册表

        `计算机\HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\Windows\CurrentVersion\Run`
-   关闭显示；关闭回显(命令将不会显示出来)：`@echo off `

bat后台运行：在bat文件命令前加入一下代码(需要了解<在需要管理员权限时可能不会提示确认权限的对话框)

```纯文本
@echo off 　　
if "%1" == "h" goto begin 
  mshta vbscript:createobject("wscript.shell").run("%~nx0 h",0)(window.close)&&exit 
:begin 
```





## 待看示例

-   流量监控软件NetSpeedMonitor

    ![](../image/image_V2YvlJkEZN.png)
    ```html
    @echo off
    goto check_Permissions

    :check_Permissions

    NET SESSION >nul 2>&1
    IF %ERRORLEVEL% NEQ 0 (
        ECHO 请以管理员身份运行!
        PAUSE >nul
        exit /B 1
    )

    cd /d %~dp0
    regsvr32 nsm.dll
    start nsmc.exe
    ```

