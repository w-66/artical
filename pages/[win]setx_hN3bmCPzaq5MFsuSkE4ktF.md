# \[win]setx



setx此命令提供了唯一直接、永久地设置系统环境值的命令行或编程方式。

-   添加的必须是路径(绝对路径)

`/M`

设置系统环境变量; 指定应该在系统 (HKEY\_LOCAL\_MACHINE) 环境中设置此变量。在HKEY\_CURRENT\_USER 环境下，默认将设置此变量。

### 注意

> ❗修改前注意备份

> ❗环境变量的值，是路径，不是具体程序

> ❗setx设置环境变量后，将在新打开的终端中生效，当前终端不会立即生效。 &#x20;

***

注意1.

在某些情况下会出现“setx 无效语法 默认选项不能超过’2’次”的错误，据信是因为原先的环境变量中存在空格导致的，可使用双引号进行避免。 &#x20;

注意3. &#x20;


setx在设置变量的长度超过1024，会截取多出的字符。 &#x20;


注意4. &#x20;


setx还可以操作远程计算机，具体参数设置百度一下setx用法。 &#x20;


注意5. &#x20;


setx在设置某一变量的值，如果已经存在该变量会覆盖之前的值。所以正确方式是：要保存值=获取当前该变量的值+新值。 &#x20;
例如：set oldValue=获取当前变量值 &#x20;
          setx path %oldValue%;%newValue%





# 示例

> 📌添加的必须是路径(绝对路径)

-   help
    ```纯文本
    描述:
        在用户或系统环境创建或修改环境变量。能基于参数、注册表项或文件输入设置变量。
    参数列表:
        /S     system          指定要连接到的远程系统。
        /U     [domain\]user   指定应该在哪个用户上下文执行命令。
        /P     [password]      指定给定用户上下文的密码。如果省略则提示输入。
        var                    指定要设置的环境变量。
        value                  指定分配给环境变量的值。
        /K     regpath         指定变量是基于注册表项的信息而设置的。路径的格式应该是 hive\key\...\value。例如HKEY_LOCAL_MACHINE\System\CurrentControlSet\Control\TimeZoneInformation\StandardName。
        /F     file            指定要使用的文本文件的文件名。
        /A     x,y             指定绝对文件坐标(线 X，项目 Y)作为在此文件里搜索的参数。
        /R     x,y string      指定有关“字符串”作为搜索参数的相对文件坐标。
        /M                     指定应该在系统 (HKEY_LOCAL_MACHINE) 环境中设置此变量。在 HKEY_CURRENT_USER 环境下，默认将设置此变量。
        /X                     用 x，y 坐标显示文件内容。
        /D     delimiters      指定其他限定符，如 "," 或 "\"。内置分隔符是空格、制表符、回车和换行符。所有ASCII 字符都可作为限定符。限定符的最大数量，包括内置分隔符，是 15。
        /?                     显示此帮助消息。
    ```

***

-   示例：查看全局系统变量(cli)
    ```bash
    echo %path%
    F:\Code\Python\django_venv\Scripts;C:\Users\wq\AppData\Local\Programs\Python\Python39\Scripts\;C:\Users\wq\AppData\Local\Programs\Python\Python39\;C:\Users\wq\AppData\Local\Microsoft\WindowsApps;C:\Users\wq\AppData\Local\Programs\EmEditor;F:\aid sofware\Nmap;F:\aid sofware\Microsoft VS Code\bin;f:\Program Files\JetBrains\PyCharm 2022.2.2\bin;f:\Program Files\JetBrains\PyCharm Community Edition 2022.2.2\bin
    ```
-   示例：添加当前用户的环境变量，不加/m便是  \[[\[win\]setx](\[win]setx_hN3bmCPzaq5MFsuSkE4ktF.md "\[win]setx"),`%PATH%`]
    ```python
    两种写法
    setx path "%path%;F:\Program Files (x86)\nmap-7.92"
    setx path %path%;"F:\Program Files (x86)\nmap-7.92"

    ```
-   示例：添加nmap的全局系统变量 \[[\[win\]setx](\[win]setx_hN3bmCPzaq5MFsuSkE4ktF.md "\[win]setx")`/M`,`%PATH%`]
    ```text
    setx /m path "%path%;F:\Program Files (x86)\nmap-7.92"
    ```
    ```纯文本
    setx /m path %path%;"F:\Program Files (x86)\nmap-7.92"

    ```
    ![](../image/image_FOsPVM6V5x.png)



-   示例：添加mysqlsh程序到环境变量path中<3>
    ```python
    setx /m path "%path%;F:\Program Files (x86)\mysql-shell-8.0.31-windows-x86-64bit\mysql-shell-8.0.31-windows-x86-64bit\bin"
    ```

