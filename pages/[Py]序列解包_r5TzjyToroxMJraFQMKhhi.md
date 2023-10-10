# \[Py]序列解包

Sequence Unpacking

***

参考1：[https://www.bilibili.com/video/BV1kT4y1u72i?t=621.9](https://www.bilibili.com/video/BV1kT4y1u72i?t=621.9 "https://www.bilibili.com/video/BV1kT4y1u72i?t=621.9") \[示例：单独提取姓与名 \[[\[Py\]序列解包](\[Py]序列解包_r5TzjyToroxMJraFQMKhhi.md "\[Py]序列解包")]]

***



## 示例

-   示例：单独提取姓与名 \[[\[Py\]序列解包](\[Py]序列解包_r5TzjyToroxMJraFQMKhhi.md "\[Py]序列解包")]

    ![](../image/image_eg5O5tKTy2.png)

    方案1：

    ![](../image/image_HttZOaqJq7.png)

    方案2：

    ![](../image/image_KhQA1Aitat.png)
-   示例：Python中类似JavaScript中的解构的语法

    在 Python 中，可以使用多种方式进行解构（解构赋值），类似于 JavaScript 中的解构语法。
    1.  元组解构：
    ```python
    # 定义元组
    tuple1 = (1, 2, 3)
    # 元组解构赋值
    a, b, c = tuple1
    print(a)  # 输出: 1
    print(b)  # 输出: 2
    print(c)  # 输出: 3
    ```
    1.  列表解构：
    ```python
    # 定义列表
    list1 = [1, 2, 3]
    # 列表解构赋值
    [a, b, c] = list1
    print(a)  # 输出: 1
    print(b)  # 输出: 2
    print(c)  # 输出: 3
    ```
    1.  字典解构：
    ```python
    # 定义字典
    dict1 = {'name': 'John', 'age': 25}
    # 字典解构赋值
    {name, age} = dict1
    print(name)  # 输出: John
    print(age)   # 输出: 25
    ```
    1.  嵌套结构解构：
    ```python
    # 定义嵌套结构
    nested_tuple = (1, (2, 3), 4)
    # 嵌套结构解构赋值
    a, (b, c), d = nested_tuple
    print(a)  # 输出: 1
    print(b)  # 输出: 2
    print(c)  # 输出: 3
    print(d)  # 输出: 4
    ```
    需要注意的是，在 Python 中，解构赋值的左边变量的个数必须与右边的元素个数相匹配，否则会引发 ValueError 异常。另外，解构赋值也可以在函数参数传递、循环迭代等场景中使用。
