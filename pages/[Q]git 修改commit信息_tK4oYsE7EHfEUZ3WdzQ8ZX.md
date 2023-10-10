# \[Q]git 修改commit信息

<https://blog.csdn.net/Muscleape/article/details/105637401>



修改commit信息主要有这几种情况


1.  修改刚commit，还没有push的commit信息
2.  刚刚push，要修改最近一个push的commit信息，使用git commit --amend；

3.  修改历史push的commit信息，使用git rebase -i HEAD\~n【其中的n为记录数】，配合2中的命令

> **其中1、2两种情况的修改方式是一样的，但是git log的记录是不同的**







-   示例：情况1：修改刚commit，还没有push的commit信息 \[`git commit``--amend`]

    **注意：此方法只是针对刚commit的信息，历史的信息需要用下面其他的方法**

    这时候git status的信息显示如下：

    ![image.png](https://imgconvert.csdnimg.cn/aHR0cHM6Ly91cGxvYWQtaW1hZ2VzLmppYW5zaHUuaW8vdXBsb2FkX2ltYWdlcy8yOTE4MjUyLWFkMDhkZDFmYjE1MmM3YjUucG5n?x-oss-process=image/format,png "image.png")

    git log 记录显示为（指向最近的这次commit）：

    ![image.png](https://imgconvert.csdnimg.cn/aHR0cHM6Ly91cGxvYWQtaW1hZ2VzLmppYW5zaHUuaW8vdXBsb2FkX2ltYWdlcy8yOTE4MjUyLTQxNWM4ZDliZDIxN2I5ZWIucG5n?x-oss-process=image/format,png "image.png")

    执行一下 git commit --amend&#x20;

    ![image.png](https://imgconvert.csdnimg.cn/aHR0cHM6Ly91cGxvYWQtaW1hZ2VzLmppYW5zaHUuaW8vdXBsb2FkX2ltYWdlcy8yOTE4MjUyLWE3N2IzMWJjMmQ5ZWVmNzcucG5n?x-oss-process=image/format,png "image.png")

    出现编辑界面（vim）

    ![image.png](https://imgconvert.csdnimg.cn/aHR0cHM6Ly91cGxvYWQtaW1hZ2VzLmppYW5zaHUuaW8vdXBsb2FkX2ltYWdlcy8yOTE4MjUyLWI2YWVjYjgyYWMxNDIxZjIucG5n?x-oss-process=image/format,png "image.png")

    编辑后保存并退出（“七”改成了“7”）

    ![image.png](https://imgconvert.csdnimg.cn/aHR0cHM6Ly91cGxvYWQtaW1hZ2VzLmppYW5zaHUuaW8vdXBsb2FkX2ltYWdlcy8yOTE4MjUyLWNhMGFlM2IxOWVmZjE4ZjQucG5n?x-oss-process=image/format,png "image.png")

    再次查看git log，commit信息修改完成，继续push就可以了
-   \[Q]git commit --amend 修改完之后，原本的提交记录可以删除吗? \[`git commit``--amend`]

    如果你已经将修改后的提交记录推送到远程仓库，并且其他人也已经从该远程仓库获取了这个提交记录，那么删除这个提交记录可能会破坏协作，并且导致仓库历史记录不一致。

    如果你只是在本地修改并提交了一个错误的提交记录，那么可以使用`git reset`命令来撤销这个提交记录。如果你想要完全删除这个提交记录，可以使用`git reset --hard HEAD^`命令，其中的`^`表示撤销上一个提交记录。

    但是需要注意的是，`git reset --hard`命令会删除所有未提交的修改，包括在工作区和暂存区中的修改。因此，在执行这个命令之前，请确保你已经保存了所有的修改。
