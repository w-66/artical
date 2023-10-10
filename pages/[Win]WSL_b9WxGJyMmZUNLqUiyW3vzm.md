# \[Win]WSL

[https://learn.microsoft.com/zh-cn/windows/wsl/](https://learn.microsoft.com/zh-cn/windows/wsl/ "https://learn.microsoft.com/zh-cn/windows/wsl/")

-   帮助
    ```纯文本
    用法: wsl.exe [Argument] [Options...] [CommandLine]

    运行 Linux 二进制文件的参数:

        如果未提供命令行，wsl.exe 将启动默认 shell。

        --exec, -e <CommandLine>
            在不使用默认 Linux Shell 的情况下执行指定的命令。

        --
            按原样传递其余命令行。

    选项:
        --cd <Directory>
            将指定目录设置为当前工作目录。
            如果使用了 ~，则将使用 Linux 用户的主页路径。如果路径
            以 / 字符开头，将被解释为绝对 Linux 路径。
            否则，该值一定是绝对 Windows 路径。

        --distribution, -d <Distro>
            运行指定分发。

        --user, -u <UserName>
            以指定用户身份运行。

    管理适用于 Linux 的 Windows 子系统的参数:

        --help
            显示用法信息。

        --install [选项]
            安装额外的适用于 Linux 的 Windows 子系统分发。
             要获得有效分发列表，请使用“wsl --list --online”。

            选项:
                --distribution, -d [参数]
                    按名称下载并安装分发。

                    参数:
                        有效分发名称(不区分大小写)。

                    示例:
                        wsl --install -d Ubuntu
                        wsl --install --distribution Debian
        --set-default-version <Version>
            更改新分发的默认安装版本。

          --shutdown
             立即终止所有运行的分发及 WSL 2
            轻型工具虚拟机。

             --status
               显示适用于 Linux 的 Windows 子系统的状态。

        --update [选项]
            如果未指定任何选项，则 WSL 2 内核将更新
            到最新版本。

                 选项:
             --rollback
                    还原到 WSL 2 内核的先前版本。

    用于管理适用于 Linux 的 Windows 子系统中的分发的参数:

        --export <Distro> <FileName>
             将分发导出到 tar 文件。
            对于标准输出，文件名可以是 –。

        --import <Distro> <InstallLocation> <FileName> [Options]
                将指定的 tar 文件作为新分发导入。
              对于标准输入，文件名可以是 –。

            选项:
                --version <Version>
                    指定要用于新分发的版本。

        --list, -l [Options]
            列出分发。

            选项:
                --all
                    列出所有分发，包括
            当前正在安装或卸载的分发。

                --running
                    仅列出当前正在运行的分发。

                --quiet, -q
                    仅显示分发名称。

                --verbose, -v
                    显示所有分发的详细信息。

                --online, -o
                    显示使用“wsl --install”进行安装的可用分发列表。

        --set-default, -s <分发>
            将分发设置为默认值。

        --set-version <分发> <版本>
            更改指定分发的版本。

        --terminate, -t <分发>
            终止指定的分发。

        --unregister <分发>
            注销分发并删除根文件系统。

    ```





-   `wsl`
    1.  `wsl --install`[安装](https://learn.microsoft.com/zh-cn/windows/wsl/basic-commands#install "安装")
    2.  `wsl --install --distribution <Distribution Name>`[安装特定的 Linux 发行版](https://learn.microsoft.com/zh-cn/windows/wsl/basic-commands#install-a-specific-linux-distribution "安装特定的 Linux 发行版")
    3.  `wsl --list --online`[列出可用的 Linux 发行版](https://learn.microsoft.com/zh-cn/windows/wsl/basic-commands#list-available-linux-distributions "列出可用的 Linux 发行版")
    4.  `wsl -l -v`,`wsl --list --verbose`[列出已安装的 Linux 发行版](https://learn.microsoft.com/zh-cn/windows/wsl/basic-commands#list-installed-linux-distributions "列出已安装的 Linux 发行版")
    5.  `wsl --set-version <distribution name> <versionNumber>`[将 WSL 版本设置为 1 或 2](https://learn.microsoft.com/zh-cn/windows/wsl/basic-commands#set-wsl-version-to-1-or-2 "将 WSL 版本设置为 1 或 2")
    6.  `wsl --set-default-version <Version>`[设置默认 WSL 版本](https://learn.microsoft.com/zh-cn/windows/wsl/basic-commands#set-default-wsl-version "设置默认 WSL 版本")
    7.  `wsl --set-default <Distribution Name>`[设置默认 Linux 发行版](https://learn.microsoft.com/zh-cn/windows/wsl/basic-commands#set-default-linux-distribution "设置默认 Linux 发行版")

1.  [将目录更改为主页](https://learn.microsoft.com/zh-cn/windows/wsl/basic-commands#change-directory-to-home "将目录更改为主页")
2.  [通过 PowerShell 或 CMD 运行特定的 Linux 发行版](https://learn.microsoft.com/zh-cn/windows/wsl/basic-commands#run-a-specific-linux-distribution-from-powershell-or-cmd "通过 PowerShell 或 CMD 运行特定的 Linux 发行版")
3.  [更新 WSL](https://learn.microsoft.com/zh-cn/windows/wsl/basic-commands#update-wsl "更新 WSL")
4.  [检查 WSL 状态](https://learn.microsoft.com/zh-cn/windows/wsl/basic-commands#check-wsl-status "检查 WSL 状态")
5.  [Help 命令](https://learn.microsoft.com/zh-cn/windows/wsl/basic-commands#help-command "Help 命令")
6.  [以特定用户的身份运行](https://learn.microsoft.com/zh-cn/windows/wsl/basic-commands#run-as-a-specific-user "以特定用户的身份运行")
7.  [更改发行版的默认用户](https://learn.microsoft.com/zh-cn/windows/wsl/basic-commands#change-the-default-user-for-a-distribution "更改发行版的默认用户")
8.  [关闭](https://learn.microsoft.com/zh-cn/windows/wsl/basic-commands#shutdown "关闭")
9.  [Terminate](https://learn.microsoft.com/zh-cn/windows/wsl/basic-commands#terminate "Terminate")
10. [将发行版导出到 TAR 文件](https://learn.microsoft.com/zh-cn/windows/wsl/basic-commands#export-a-distribution-to-a-tar-file "将发行版导出到 TAR 文件")
11. [导入新发行版](https://learn.microsoft.com/zh-cn/windows/wsl/basic-commands#import-a-new-distribution "导入新发行版")
12. [注销或卸载 Linux 发行版](https://learn.microsoft.com/zh-cn/windows/wsl/basic-commands#unregister-or-uninstall-a-linux-distribution "注销或卸载 Linux 发行版")
13. [装载磁盘或设备](https://learn.microsoft.com/zh-cn/windows/wsl/basic-commands#mount-a-disk-or-device "装载磁盘或设备")
14. [已弃用的 WSL 命令](https://learn.microsoft.com/zh-cn/windows/wsl/basic-commands#deprecated-wsl-commands "已弃用的 WSL 命令")



-   `wsl`
    1.  `wsl --install`
        1.  `-d`
    2.  `wsl --install --distribution <Distribution Name>`
    3.  `wsl --list --online`
    4.  `wsl --list --verbose`
        1.  `wsl -l -v`
    5.  `wsl --set-version <distribution name> <versionNumber>`
    6.  `wsl --set-default-version <Version>`
    7.  `wsl --set-default <Distribution Name>`



安装Ubuntu \[`-d`]
