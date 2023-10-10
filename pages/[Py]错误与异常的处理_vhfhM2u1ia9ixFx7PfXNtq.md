# \[Py]错误与异常的处理

<https://www.runoob.com/python3/python3-errors-execptions.html>









[\[Py\]with](\[Py]with_mRCptztLCNdeHM1z8FMay2.md "\[Py]with")

-   `[Py]try`
-   `[Py]except`
-   \[Py]`finally`

## 预定义的清理行为

## 内置异常

[https://docs.python.org/zh-cn/3/library/exceptions.html#bltin-exceptions](https://docs.python.org/zh-cn/3/library/exceptions.html#bltin-exceptions "https://docs.python.org/zh-cn/3/library/exceptions.html#bltin-exceptions")



## 示例

-   示例：读取一个不存在的文件，将报错，自定义错误提示 \[`[Py]try``[Py]except`] <[空降](https://www.bilibili.com/video/BV1Db4y1m7Ho?p=50\&spm_id_from=pageDriver\&vd_source=d87be07aa170c6f76058fa2663ca0da0 "空降")>

    正常情况
    ```python
    fp = fp = open('F:/Code/Python/test_file/4.txt', 'r')
    fp.close
    ```
    ```python
    Traceback (most recent call last):
      File "f:\Code\Python\Python\test\str.py", line 55, in <module>    fp = fp = open('F:/Code/Python/test_file/4.txt', 'r')       
     FileNotFoundError : [Errno 2] No such file or directory: 'F:/Code/Python/test_file/4.txt'
    ```
    错误提示类型提示：FileNotFoundError
    ***
    自定义错误提示
    ```python
    try:
        fp = fp = open('F:/Code/Python/test_file/4.txt', 'r')
        fp.close
    except FileNotFoundError:
        print("自定义错误提示：巴拉巴拉")
    ```
    ```python
    自定义错误提示：巴拉巴拉
    ```
