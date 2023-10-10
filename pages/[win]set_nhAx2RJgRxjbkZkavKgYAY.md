# \[win]set



<https://docs.microsoft.com/zh-cn/windows-server/administration/windows-commands/set_1>

-   set 临时设置环境变量
-

***

-   在输入路径时，带有空格的目录需要加上引号

作用：显示、设置或删除 cmd.exe 环境变量。&#x20;

/p

格式：

SET \[variable=\[string]]

variable 指定环境变量名。

string 指定要指派给变量的一系列字符串。

要求： SET 命令不允许变量名含有等号。





***

示例：

-   示例：用户互交，记录用户输入 \[/p]
    ```powershell
    set /p "user_input=提交的信息(默认:text)"
    echo 你输入了:  %user_input%
    ```
-   示例1.1：增加临时的环境变量，在原有的变量后直接加上想要添加的变量路径(mysql)
    ```纯文本
    C:\Users\qusay>set Path=C:\Windows\system32;C:\Windows;C:\Windows\System32\Wbem;C:\Windows\System32\WindowsPowerShell\v1.0\;C:\Windows\System32\OpenSSH\;C:\Users\qusay\AppData\Local\Microsoft\WindowsApps;F:\aid software\Nmap;F:\aid software\MySQL\Install\MySQL Server 8.0\bin

    C:\Users\qusay>set path
    Path=C:\Windows\system32;C:\Windows;C:\Windows\System32\Wbem;C:\Windows\System32\WindowsPowerShell\v1.0\;C:\Windows\System32\OpenSSH\;C:\Users\qusay\AppData\Local\Microsoft\WindowsApps;F:\aid software\Nmap;F:\aid software\MySQL\Install\MySQL Server 8.0\bin

    ```
-   示例1.2：追加临时的环境变量
    ```纯文本
    C:\Users\qusay>set path=%path%;F:\aid software\MySQL\Install\MySQL Server 8.0\bin

    C:\Users\qusay>set path
    Path=C:\Windows\system32;C:\Windows;C:\Windows\System32\Wbem;C:\Windows\System32\WindowsPowerShell\v1.0\;C:\Windows\System32\OpenSSH\;C:\Users\qusay\AppData\Local\Microsoft\WindowsApps;F:\aid software\Nmap;;F:\aid software\MySQL\Install\MySQL Server 8.0\bin

    ```

示例：

```python
F:\Program Files (x86)\mysql-shell-8.0.31-windows-x86-64bit\mysql-shell-8.0.31-windows-x86-64bit\bin
```

设置的环境变量为临时变量，如：

```javascript
set PATH=%PATH%;D:\Program Files\

```

```javascript
set PATH=%PATH%;"F:\soft nmap\nmap-7.92"
```

> 设置完，输入nmap没生效，重启也没有生效？

使用[\[win\]setx](\[win]setx_hN3bmCPzaq5MFsuSkE4ktF.md "\[win]setx")设置为永久环境变量,适用于bat中：

-   示例：添加nmap的全局系统变量 \[[\[win\]setx](\[win]setx_hN3bmCPzaq5MFsuSkE4ktF.md "\[win]setx")`/M`,`%PATH%`]
    ```text
    setx /m path "%path%;F:\Program Files (x86)\nmap-7.92"
    ```
    ```纯文本
    setx /m path %path%;"F:\Program Files (x86)\nmap-7.92"

    ```
    ![](../image/image_FOsPVM6V5x.png)
