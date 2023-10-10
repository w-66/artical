# \[Win]设置环境变量

设置用户环境变量，可以立即生效，但是设置系统环境变量，必须要重启电脑才行

[win系统环境变量](win系统环境变量_bvQP4vZ5rRgWcFxLxJsncS.md "win系统环境变量")

# 命令行设置

[\[win\]set](\[win]set_nhAx2RJgRxjbkZkavKgYAY.md "\[win]set")和 [\[win\]setx](\[win]setx_hN3bmCPzaq5MFsuSkE4ktF.md "\[win]setx")都可以用来设置环境变量，但是它们也有所不同：`set`  ：在当前终端立即生效，但只在当前终端中生效（临时有效）；`setx`：在当前终端不会生效，但在新打开的终端都会生效（永久有效）

另外，在使用 [\[win\]setx](\[win]setx_hN3bmCPzaq5MFsuSkE4ktF.md "\[win]setx") 命令时需要特别注意：`string` 中是不允许带有空格的，若值中有空格，请使用双引号括起来 ；给变量赋值的时候，采用的是覆盖的方式【重要】





-   示例：添加nmap的全局系统变量 \[[\[win\]setx](\[win]setx_hN3bmCPzaq5MFsuSkE4ktF.md "\[win]setx")`/M`,`%PATH%`]
    ```text
    setx /m path "%path%;F:\Program Files (x86)\nmap-7.92"
    ```
    ```纯文本
    setx /m path %path%;"F:\Program Files (x86)\nmap-7.92"

    ```
    ![](../image/image_FOsPVM6V5x.png)

# GUI设置



-   示例：图形化 gui操作设置系统环境变量

    在我的电脑-属性-高级-环境变量-系统变量

    ![](../image/image_6S9XLmF2DC.png)

    ![](../image/image_svndNLZc4d.png)
    > 上面是设置用户变量，下面是系统变量（对任意用户都有效），建议选择在系统变量中进行修改
    点击 `PATH`，新建，加上程序路径

    ![](../image/image_zWhpL8WYcI.png)

    添加程序路径

    ![](../image/image_kjX5kZYTmo.png)
