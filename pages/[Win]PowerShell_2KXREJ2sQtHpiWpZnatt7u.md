# \[Win]PowerShell

ps1|脚本

ps1脚本

-   示例：添加环境变量 \[ps1|脚本,win]
    -   示例：添加环境变量到用户环境变量 \[ps1|脚本]

        [install-add\_user.ps1](../file/install-add_user_AMv1l8nYxB.ps1 "install-add_user.ps1")

        ![](../image/image_szJJL9YWyo.png)
        ```powershell
        # 提示用户输入要添加的路径
        $NewPath = Read-Host "请输入要添加的路径"

        # 获取当前用户的环境变量
        $UserEnv = [System.Environment]::GetEnvironmentVariable("PATH", "User")

        # 检查路径是否已存在于环境变量中
        if ($UserEnv -like "*$NewPath*") {
            Write-Host "路径已存在于PATH环境变量中，无需添加。"
        } else {
            # 显示将要添加的路径，并要求用户确认
            Write-Host "将要添加的路径: $NewPath"
            $confirmation = Read-Host "确认要添加此路径吗？ (Y/N)"

            if ($confirmation -eq "Y" -or $confirmation -eq "y") {
                # 将新路径添加到环境变量
                [System.Environment]::SetEnvironmentVariable("PATH", "$UserEnv;$NewPath", "User")
                Write-Host "路径已成功添加到PATH环境变量。"
            } else {
                Write-Host "未进行更改。"
            }
        }
        pause
        ```
    -   示例：添加环境变量到系统环境变量 \[ps1|脚本]

        [install-add\_system.ps1](../file/install-add_system_4I494LuywA.ps1 "install-add_system.ps1")
        ```powershell

        # 检查是否以管理员权限运行
        $IsAdmin = ([System.Security.Principal.WindowsPrincipal] [System.Security.Principal.WindowsIdentity]::GetCurrent()).IsInRole([System.Security.Principal.WindowsBuiltInRole] "Administrator")

        if ($IsAdmin) {
            # 提示用户输入要添加的路径
            $NewPath = Read-Host "请输入要添加到系统级别的路径"

            # 获取系统级别的环境变量
            $SystemEnv = [System.Environment]::GetEnvironmentVariable("PATH", "Machine")

            # 检查路径是否已存在于环境变量中
            if ($SystemEnv -like "*$NewPath*") {
                Write-Host "路径已存在于系统级别的PATH环境变量中，无需添加。"
            } else {
                # 显示将要添加的路径，并要求用户确认
                Write-Host "将要添加到系统级别的路径: $NewPath"
                $confirmation = Read-Host "确认要添加此路径吗？ (Y/N)"

                if ($confirmation -eq "Y" -or $confirmation -eq "y") {
                    # 将新路径添加到系统级别的环境变量
                    [System.Environment]::SetEnvironmentVariable("PATH", "$SystemEnv;$NewPath", "Machine")
                    Write-Host "路径已成功添加到系统级别的PATH环境变量。"
                } else {
                    Write-Host "未进行更改。"
                }
            }
        } 
        else {
            Write-Host "请以管理员权限运行此脚本。"
        }
        pause 

        ```

