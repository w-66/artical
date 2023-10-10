# \[win]echo



显示消息，或者启用或关闭命令回显。

ECHO \[ON | OFF]

ECHO \[message]

若要显示当前回显设置，请键入不带参数的 ECHO。

***

# 示例

`echo [{ on|off}]`打开回显或关闭本批处理的所有回显功能

-   演示
    ```纯文本
    @echo off
    echo 显示文字1
    echo 显示文字2
    pause
    ```
    ![](../image/image_tnHGaEhh9u.png)

`echo.`：输出一个空行，相当于回车

-   演示
    ```纯文本
    @echo off
    echo 显示文字1
    echo.
    echo 显示文字2
    pause
    ```
    ![](../image/image_eBwCd9SoEz.png)

`echo 回复|命令表达式`：答复命令中的提问；

在一些命令中如[\[win\]rd](\[win]rd_6TbPtDRASj8Q2B4V5XeP2y.md "\[win]rd")删除一个非空文件夹时，会让你回复`(Y/N)`，这个时候使用此方式自动回复

-   演示
    > [\[win\]rd](\[win]rd_6TbPtDRASj8Q2B4V5XeP2y.md "\[win]rd")在删除不是**空文件夹**的时候才需要回复
    直接删除需要手动回复`(Y/N)`

    ![](../image/image_v0uP-FTWLA.png)
    ***
    加入自动回复，将直接删除而无需回复
    ```纯文本
    @echo off
    echo y|rd /s E:\临时\新建文件夹
    pause
    ```
    ![](../image/image_LIlqUOaWcC.png)

`echo  %cd% `打印当前路径相当于[\[Linux\]pwd](\[Linux]pwd_qqNc2c3E2uJa1NgBf53Z9z.md "\[Linux]pwd")
