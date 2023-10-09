# 怎么添加用户到组？

<https://www.cnblogs.com/mouseleo/p/11867107.html>

linux 中将用户添加到组的 4 个方法

可以使用以下四种方法实现。

-   [usermod](usermod_wYv4ze9jkQ9Deh26CSEsEt.md "usermod")：修改系统帐户文件，以反映在命令行中指定的更改。
-   [gpasswd](gpasswd_kaUM8YJzuTDJCUE4avE4kP.md "gpasswd")：用于管理 /etc/group 和 /etc/gshadow。每个组都可以有管理员、成员和密码。
-   [Shell](Shell_a6sHQMa1GWsp5hVT2uYLkM.md "Shell")：可以让管理员自动执行所需的任务。
-   手动方式：我们可以通过编辑 /etc/group 文件手动将用户添加到任何组中。
