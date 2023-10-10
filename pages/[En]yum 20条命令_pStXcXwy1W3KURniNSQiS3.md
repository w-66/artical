# \[En]yum 20条命令

<https://www.tecmint.com/20-linux-yum-yellowdog-updater-modified-commands-for-package-mangement/>

### What is [\[Linux\]yum](\[Linux]yum_pi49fkNE5XMHfkjDFGLxL6.md "\[Linux]yum")?

-   **YUM** (**Yellowdog Updater Modified**) is an open source command-line as well as graphical based package management tool for **RPM** (**RedHat Package Manager**) based Linux systems.&#x20;

    一个开源命令行以及基于图形的包管理工具，适用于基于 [\[Linux\]rpm](\[Linux]rpm_pwYduzKzqrFTui1zc5wpLu.md "\[Linux]rpm")（RedHat 包管理器）的 Linux 系统。
-   It allows users and system administrator to easily install, update, remove or search software packages on a systems.&#x20;

    它允许用户和系统管理员轻松地在系统上安装、更新、删除或搜索软件包。
-   It was developed and released by **Seth Vidal** under **GPL** (**General Public License**) as an open source, means anyone can allowed to download and access the code to [fix](fix_3ujXR6R12knKiEz8Hz7zdW.md "fix") bugs and develop customized packages.

    它由 Seth Vidal 在 GPL（通用公共许可证）下作为开源开发和发布，这意味着任何人都可以下载和访问代码以修复错误和开发定制包。
-   &#x20;**YUM** uses [numerous](numerous_kQ9BR3ZFHu1CACEL9TL89.md "numerous")  repositorys to install packages automatically by resolving [their](their_gud1bd5sUmVJEpmLHoNGgo.md "their") dependencies [issues](issues_xi5TckpRwJ44SKyjyf1pRW.md "issues").

    YUM 使用许多第三方存储库通过解决它们的依赖关系问题来自动安装包。

| -y  | 安装时取消确认 |
| --- | ------- |

#### 1. Install a Package with [\[Linux\]yum](\[Linux]yum_pi49fkNE5XMHfkjDFGLxL6.md "\[Linux]yum")

```纯文本
yum install [ package name ]
```

To install a package called [Firefox 14](https://www.tecmint.com/install-firefox-14-in-rhel-centos-fedora/ "Firefox 14"), just run the [above](above_rb7VsfG8sa28SGzMxfRd8D.md "above") command it will [automatically](automatically_ejK5nqQjr8y1hEFg1c3Ejo.md "automatically") find and install all required [dependencies](dependencies_mzfcuHXt1SJJjTtPNKbFXn.md "dependencies") for Firefox.

-   yum安装[iperf](iperf_41cVccAvXZr432XGSKdHGf.md "iperf")示例
    ```纯文本
    # yum install iperf
    Loaded plugins: fastestmirror, langpacks
    Determining fastest mirrors
    epel                                                                                                                                                       | 4.7 kB  00:00:00     
    extras                                                                                                                                                     | 2.9 kB  00:00:00     
    os                                                                                                                                                         | 3.6 kB  00:00:00     
    updates                                                                                                                                                    | 2.9 kB  00:00:00     
    Resolving Dependencies
    --> Running transaction check
    ---> Package iperf.x86_64 0:2.0.13-1.el7 will be installed
    --> Finished Dependency Resolution

    Dependencies Resolved

    ==================================================================================================================================================================================
     Package                                  Arch                                      Version                                         Repository                               Size
    ==================================================================================================================================================================================
    Installing:
     iperf                                    x86_64                                    2.0.13-1.el7                                    epel                                     86 k

    Transaction Summary
    ==================================================================================================================================================================================
    Install  1 Package

    Total download size: 86 k
    Installed size: 185 k
    Is this ok [y/d/N]: y
    Downloading packages:
    iperf-2.0.13-1.el7.x86_64.rpm                                                                                                                              |  86 kB  00:00:00     
    Running transaction check
    Running transaction test
    Transaction test succeeded
    Running transaction
      Installing : iperf-2.0.13-1.el7.x86_64                                                                                                                                      1/1 
      Verifying  : iperf-2.0.13-1.el7.x86_64                                                                                                                                      1/1 

    Installed:
      iperf.x86_64 0:2.0.13-1.el7                                                                                                                                                     

    Complete!
    ```
-   The [above](above_rb7VsfG8sa28SGzMxfRd8D.md "above") command will [ask](ask_sc5qyD4dfusp3sBLynCWWf.md "ask") [confirmation](confirmation_6zgLuZUW4C1rpWARcFPcCd.md "confirmation") before installing any package on your system. If you want to install packages automatically [without](without_8NRa57UnajknxNKetnhT5g.md "without") asking any confirmation, use option **`-y`** as shown in below example.

    在您的系统上安装任何软件包之前，上述命令将要求确认。如果您想在不要求任何确认的情况下自动安装软件包，请使用选项 -y，如下例所示。
    ```纯文本
    # yum -y install firefox
    ```


#### 2. Removing a Package with YUM

```纯文本
yum remove [ package name ]
```

-   To remove a package completely with [their](their_gud1bd5sUmVJEpmLHoNGgo.md "their") all dependencies, just run the following command as shown above.

    完整的移除一个包，和他们所有的依赖，只需要下面这个命令，如下所示
-   移除iperf示例
    ```纯文本
    # yum remove iperf
    Loaded plugins: fastestmirror, langpacks
    Resolving Dependencies
    --> Running transaction check
    ---> Package iperf.x86_64 0:2.0.13-1.el7 will be erased
    --> Finished Dependency Resolution

    Dependencies Resolved

    ==================================================================================================================================================================
     Package                             Arch                                 Version                                       Repository                           Size
    ==================================================================================================================================================================
    Removing:
     iperf                               x86_64                               2.0.13-1.el7                                  @epel                               185 k

    Transaction Summary
    ==================================================================================================================================================================
    Remove  1 Package

    Installed size: 185 k
    Is this ok [y/N]: y
    Downloading packages:
    Running transaction check
    Running transaction test
    Transaction test succeeded
    Running transaction
      Erasing    : iperf-2.0.13-1.el7.x86_64                                                                                                                      1/1 
      Verifying  : iperf-2.0.13-1.el7.x86_64                                                                                                                      1/1 

    Removed:
      iperf.x86_64 0:2.0.13-1.el7                                                                                                                                     

    Complete!
    ```
-   Same way the above command will ask confirmation before removing a package. To disable confirmation prompt just add option **`-y`** as shown in below.

    以同样的方式，上述命令将在删除包之前要求确认。要禁用确认提示，只需添加选项 -y，如下所示。

#### 3. Updating a Package using YUM

```纯文本
yum update [ package name ]
```

Let's [say](say_cL6gwQ6y9kyBwi6Gzgvumd.md "say") you have outdated version of MySQL package and you want to update it to the latest [stable](stable_jdZUaRa6465UHXYviVtoXR.md "stable") version. Just run the following command it will automatically resolves all dependencies issues and install them.

#### 4. List a Package using YUM

```纯文本
yum list [package name]
```

Use the list [function](function_7B8eEeXpJxqCYQuxsdUSuw.md "function") to search for the specific package with name. For example to search for a package called openssh, use the command.

To make your search more accurate, define package name with their version, in case you know. For example to search for a specific version **openssh-4.3p2** of the package, use the command.

***

yum list openssh
