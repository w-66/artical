# \[Q\&E]Git

-   \[Q]'git reset' 和 'git checkout'  回退文件的区别 (`git reset`,`git checkout`)

    `git reset` 和 `git checkout` 都可以用于撤销或回退某个文件的修改，但是它们的使用方式和作用范围略有不同。

    `git reset` 用于将某个分支的 HEAD 指针回退到指定的提交，同时撤销暂存区和工作区的修改。如果想要回退单个文件，可以使用 `git reset HEAD <file>` 命令。该命令会将暂存区的该文件恢复到最后一次提交的状态，但不会改变工作区的文件内容。

    `git checkout` 则是用于将某个文件恢复到指定的提交或分支的状态。如果要将单个文件恢复到最后一次提交的状态，可以使用 `git checkout HEAD <file>` 命令。该命令会将工作区的该文件恢复到最后一次提交的状态，但不会改变暂存区的文件内容。

    需要注意的是，使用 `git reset` 命令可能会改变仓库的提交历史记录，因此在回退到之前的提交时需要谨慎操作。而 `git checkout` 命令则不会改变提交历史记录。
-   \[E]fatal: The current branch master has no upstream branch. To push the current branch and set the remote as upstream, use `--set-upstrea`

    这个错误通常是因为你当前所在的分支没有与远程分支建立关联关系。在Git中，每个本地分支都可以和一个远程分支建立关联，可以使用`git push`和`git pull`等命令同步本地和远程分支的代码。在执行`git push`命令时，Git需要知道要将当前分支的代码推送到哪个远程分支，如果当前分支没有与远程分支建立关联，就会提示这个错误信息。

    解决方法可以通过`git push --set-upstream origin master`命令将当前分支与远程分支建立关联，其中`origin`表示远程仓库的名称，`master`表示要关联的分支名称。这样就可以在以后执行`git push`时直接将代码推送到远程分支。
-   \[Q]切换分支，保留当前更改; 提交之后复制提交的更改到新的分支 \[`git checkout``-b`
    -   可以使用 `git checkout -b <new-branch-name>` 命令创建并切换到一个新分支，然后再提交修改。这样就会将修改提交到新分支上，而不会影响当前分支。具体操作如下：
        ```python
        git checkout -b <new-branch-name>   # 创建并切换到新分支
        git add .                           # 添加修改
        git commit -m "commit message"      # 提交修改

        ```
    -   你可以先在当前分支上进行一次提交，然后切换到新分支上，将当前分支上的提交(cherry-pick)到新分支上。

        具体步骤如下：
        1.  在当前分支上进行一次提交，将当前修改的代码保存。
        2.  切换到新分支上：`git checkout -b new-branch`
        3.  将当前分支上的提交(cherry-pick)到新分支上：

            python
        -   `git cherry-pick <commit-hash>`&#x20;

            `<commit-hash>` 是当前分支上的提交的哈希值，可以通过 `git log` 命令查看。
        -   如果需要，可以回到原来的分支上继续开发。
        -   `git checkout original-branch`&#x20;
        -   将新分支推送到远程仓库：

            javascript
        `git push origin new-branch`&#x20;

        这样就完成了将当前分支的修改提交到新分支上的操作。

[\[Q\]git 修改commit信息](<\[Q]git 修改commit信息_tK4oYsE7EHfEUZ3WdzQ8ZX.md> "\[Q]git 修改commit信息")
