# \[Q]Git

-   \[Q]git在之前提交过，后面想要忽略的文件怎么处理? \[`git rm``--cached`,git的**忽略文件**(`.gitignore`),`git commit`]

    如果您之前已经将某些文件提交到Git版本控制中，但后来希望忽略这些文件，可以按照以下步骤进行处理：
    1.  首先，将这些文件从Git跟踪中移除，但保留在本地文件系统中。可以使用以下命令执行此操作：
    ```bash
    git rm --cached <文件路径>
    ```
    将 `<文件路径>` 替换为要移除的文件路径。这将从Git的索引中删除文件，但保留在本地文件系统中。
    1.  接下来，将这些文件添加到 `.gitignore` 文件中。`.gitignore` 是一个用于指定要忽略的文件和目录的配置文件。可以使用文本编辑器打开 `.gitignore` 文件，将要忽略的文件路径添加到其中。每个文件路径占据一行。
    2.  保存并关闭 `.gitignore` 文件。
    3.  提交 `.gitignore` 文件到Git版本控制中：
    ```bash
    git add .gitignore
    git commit -m "Add .gitignore file"
    ```
    现在，Git将忽略这些文件的任何更改，它们将不再显示为未跟踪的文件。

    请注意，忽略文件的添加和移除操作可能会对之前的提交历史产生影响。如果这些文件已经提交并推送到远程仓库，那么对于其他开发者来说，他们仍然可以访问和看到这些文件的历史记录。因此，对于已经被提交并推送的敏感文件，可能需要进行其他的处理措施，例如使用 `git filter-branch` 进行历史重写，以彻底删除这些文件的历史记录。但是，历史重写操作需要谨慎使用，并且可能会影响其他开发者的工作，请在执行之前仔细考虑和备份。
-   \[Q]git 的.gitignore 不生效的原因可能有什么?
    ```python
    以下是 .gitignore 文件不生效的一些常见原因：

        文件已经被暂存（staged）：如果你已经把文件加入了暂存区，它不再受 .gitignore 的影响，因此必须删除它。

        .gitignore 文件的名称拼写错误：检查 .gitignore 文件的名称是否为 .gitignore，不是其他的。

        .gitignore 文件位置不对：.gitignore 文件必须位于存储库根目录中，不能在子目录中。

        空行或注释：在 .gitignore 文件中，空行或注释并不会对忽略规则产生影响。请确保每一行都是一个有效的规则。

        规则语法不正确：检查每一个规则是否有语法错误，例如不存在的路径名称或错误的通配符。

        路径是相对路径：.gitignore 中的路径必须是相对于存储库根目录的绝对路径。

        存储库已经跟踪该文件：如果文件已经被加入到存储库，则不会被 .gitignore 忽略。您需要删除该文件并确保它不再被暂存，然后重新提交 .gitignore 文件。
    ```
-   \[Q]git 怎么修改commit信息?

    [\[Q\]git 修改commit信息](<\[Q]git 修改commit信息_tK4oYsE7EHfEUZ3WdzQ8ZX.md> "\[Q]git 修改commit信息")
-   &#x20;fatal: [unsafe](unsafe_tcLp4P8b5WzViiEnPLWcGA.md "unsafe") [repository](repository_91JBNa7hbaUQ2WQFqyL3zd.md "repository") <在Raidrive中rime同步文件夹中执行git 状态查询>
    ```纯文本
    $ git status
    fatal: unsafe repository ('//RaiDrive-qusay/qian/Backup/rime_sync/Android_rime_runing' is owned by someone else)
    To add an exception for this directory, call:

            git config --global --add safe.directory '%(prefix)///RaiDrive-qusay/qian/Backup/rime_sync/Android_rime_runing'

    ```
-   git 显示中文和解决中文乱码

    <https://zhuanlan.zhihu.com/p/133706032#:~:text=%E6%89%8D%E8%83%BD%E6%AD%A3%E7%A1%AE%E6%98%BE%E7%A4%BA%E4%B8%AD%E6%96%87.%20%E5%9C%A8%20git%20bash%20%E7%9A%84%E7%95%8C%E9%9D%A2%E4%B8%AD%E5%8F%B3%E5%87%BB%E7%A9%BA%E7%99%BD%E5%A4%84%EF%BC%8C%E5%BC%B9%E5%87%BA%E8%8F%9C%E5%8D%95%EF%BC%8C%E9%80%89%E6%8B%A9%20%E9%80%89%E9%A1%B9-%3E%E6%96%87%E6%9C%AC-%3E%E6%9C%AC%E5%9C%B0Locale%20%EF%BC%8C%E8%AE%BE%E7%BD%AE%E4%B8%BA%20zh_CN,bash%E7%BB%88%E7%AB%AF%E6%B2%A1%E6%9C%89%E8%8F%9C%E5%8D%95%E9%80%89%E9%A1%B9%E6%98%BE%E7%A4%BA%EF%BC%8C%E8%BF%98%E5%8F%AF%E4%BB%A5%E9%80%9A%E8%BF%87%E7%9B%B4%E6%8E%A5%E4%BF%AE%E6%94%B9%E9%85%8D%E7%BD%AE%E6%96%87%E4%BB%B6%E7%9A%84%E6%96%B9%E5%BC%8F%E6%9D%A5%E8%A7%A3%E5%86%B3%E4%B8%AD%E6%96%87%E4%B9%B1%E7%A0%81%E9%97%AE%E9%A2%98%E3%80%82%20%E7%BC%96%E8%BE%91%20etcgitconfig%20%E6%96%87%E4%BB%B6%EF%BC%8C%E4%B9%9F%E6%9C%89%E4%BA%9Bwindows%E7%B3%BB%E7%BB%9F%E6%98%AF%E5%AD%98%E6%94%BE%E5%9C%A8%20C%253AUsersAdministrator.gitconfig%20%E8%B7%AF%E5%BE%84%E6%88%96%20%E5%AE%89%E8%A3%85%E7%9B%98%E7%AC%A6%253AGitmingw64etcgitconfig%20%EF%BC%8C%E5%9C%A8%E6%96%87%E4%BB%B6%E6%9C%AB%E5%B0%BE%E5%A2%9E%E5%8A%A0%E4%BB%A5%E4%B8%8B%E5%86%85%E5%AE%B9%EF%BC%9A>

    将git配置文件 `core.quotepath`项设置为`false`。`quotepath`表示引用路径，加上`--global`表示全局配置

    `git bash`终端输入命令：

    git config --global core.quotepath false

`git add .`报错：

not a git repository (or any of the parent directories): .git

原因：未初始化此目录(`git init`)

-   克隆仓库出现问题，密钥问题：本地没有找到私钥。可以使用[\[Linux\]ssh-keygen](\[Linux]ssh-keygen_enUXZizSYHRBTyoaNkcurW.md "\[Linux]ssh-keygen")生成，或者使用已有公私钥。
    1.  默认windows读取`%HOMEPATH%\.ssh`中的公私钥，公钥需要上传到云仓库之中，本地路径中公私钥都需要存在并且相同的名字

        ![](../image/image_kVteFu8MX9.png)
    2.  完成上述条件既可正常

        ![](../image/image_54PDwlyCNh.png)
    ```纯文本
    $ git clone git@github.com:insightglacier/Dictionary-Of-Pentesting.git
    Cloning into 'Dictionary-Of-Pentesting'...
    The authenticity of host 'github.com (20.205.243.166)' can't be established.
    ED25519 key fingerprint is SHA256:+DiY3wvvV6TuJJhbpZisF/zLDA0zPMSvHdkr4UvCOqU.
    This key is not known by any other names
    Are you sure you want to continue connecting (yes/no/[fingerprint])? yes
    Warning: Permanently added 'github.com' (ED25519) to the list of known hosts.
    git@github.com: Permission denied (publickey).
    fatal: Could not read from remote repository.

    Please make sure you have the correct access rights
    and the repository exists.

    ```
    ```纯文本
    $ git clone git@github.com:insightglacier/Dictionary-Of-Pentesting.git
    Cloning into 'Dictionary-Of-Pentesting'...
    git@github.com: Permission denied (publickey).
    fatal: Could not read from remote repository.

    Please make sure you have the correct access rights
    and the repository exists.

    ```
    new word：[authenticity](authenticity_hPs4WJWRABiBWv8GUk4KCc.md "authenticity")(n.真实性)、[establish](establish_qQ9HewxZSo25AknSv2V8cv.md "establish")

    review：[fingerprint](fingerprint_nHgEEtgdxtv7xdJT96gbFr.md "fingerprint")

