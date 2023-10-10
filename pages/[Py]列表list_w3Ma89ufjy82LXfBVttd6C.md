# \[Py]列表list

[https://www.runoob.com/python/python-lists.html](https://www.runoob.com/python/python-lists.html "https://www.runoob.com/python/python-lists.html")

列表是结构化的、非标量类型，它是值的有序序列，每个值都可以通过索引进行标识，定义列表可以将列表的元素放在`[]`中，多个元素用`,`进行分隔，可以使用`for`循环对列表元素进行遍历，也可以使用`[]`或`[:]`运算符取出列表中的一个或多个元素。

`.list()`

`.append()`

`.extend()`

`.remove()`

`.pop()`

`.clear()`

`.sort()`

`reverse`

\=True

*reverse* 为一个布尔值。 如果设为 `True`，则每个列表元素将按反向顺序比较进行排序

列表取值与切片

列表的排序

-   示例：基础列表操作
    ```python
    # 创建空列表
    list = []
    print(type(list))
    # 添加数据
    list.append('Google')  # 使用 append() 添加元素
    print(list)
    # 删除元素
    del list[0]
    print(list)
    ```
-   列表遍历元素
    -   示例：通过循环用下标遍历列表元素 \[[\[Py\]for
        ](\[Py]for_3XDGtKp2ikTvoRVv9WyCsn.md "\[Py]for
        ")]
        ```python
        for index in range(len(list)):
            print(list[index])
        ```
    -   示例：通过for循环遍历列表元素 \[[\[Py\]for
        ](\[Py]for_3XDGtKp2ikTvoRVv9WyCsn.md "\[Py]for
        ")]
        ```python
        for elem in list:
            print(elem)
        ```
    -   示例：通过[\[Py\]enumerate()](\[Py]enumerate\(\)_5ngjCbmBeqAhM3JtKsY9fP.md "\[Py]enumerate()")函数处理列表之后再遍历可以同时获得元素索引和值
        ```python
        seasons = ['Spring', 'Summer', 'Fall', 'Winter']
        list(enumerate(seasons))

        [(0, 'Spring'), (1, 'Summer'), (2, 'Fall'), (3, 'Winter')]

        list(enumerate(seasons, start=1))
        [(1, 'Spring'), (2, 'Summer'), (3, 'Fall'), (4, 'Winter')]
        ```
        等价于
        ```python
        def enumerate(sequence, start=0):
            n = start
            for elem in sequence:
                yield n, elem
                n += 1
        ```
-   列表增删改
    -   示例：添加一个元素到列表末尾 \[`.append()`]
        ```python
        list0 = [1]
        list0.append(200)
        print(list0)

        >>> 
        [1, 200]
        ```
    -   示例：列表取值与切片 ，带冒号返回列表，单值返回数据
        ```python
        list0[1:]  # 从1开始到结束所有元素
        list0[2:4]
        list0[:]   # 切片所有元素
        list0[-1]  # 倒数第一个元素
        list0[-2:] # 倒数第二个元素开始往后算
        list0[-1:-3]
        list0[::-1]  # 列表反序

        ```
    ***
    -   示例：合并两个列表 \[`.extend()`]
        ```python
        list0 = [1]
        list0.extend(['hi', 'how are you'])
        print(list0)
        >>>
        [1, 'hi', 'how are you']

        ```
        等价于
        ```python
        list0 = [1]
        list0 += ['hi', 'how are you']
        print(list0)
        >>>
        [1, 'hi', 'how are you']

        ```
        ***
        ```python
        list0 = [1]
        list2 = [1,3,4,5,6]
        list0 += list2
        print(list0)
        >>>
        [1, 1, 3, 4, 5, 6]

        ```
    -   示例：删除元素 \[`.remove()`,`.pop()`,`.clear()`]

        示例：如果3存在与列表则删除 \[`.remove()`]
        ```python
        list0 = [1,3,4,5,6]
        if 3 in list0:
          list.remove(3)
        print(list0)
        >>>
        [1, 4, 5, 6]

        ```
        示例：通过下标来删除元素 \[`.pop()`]
        ```python
        list0 = [1,3,4,5,6]
        list.pop(1)
        print(list0)
        >>>
        [1, 4, 5, 6]

        ```
        示例：清空列表 \[`.clear()`]
        ```python
        list0.clear()
        ```

    ***
    -   示例：列表的排序 \[[\[Py\]sorted()](\[Py]sorted\(\)_rvtcB64n8EH2st4KdMqs5a.md "\[Py]sorted()")]

        示例：列表按数字大小排序
        ```python
        list0 = [1,22,33,3,4,5,6]
        print(sorted(list0))
        >>>
        [1, 3, 4, 5, 6, 22, 33]

        ```
        示例：列表按字符串长度排序 \[[\[Py\]sorted()](\[Py]sorted\(\)_rvtcB64n8EH2st4KdMqs5a.md "\[Py]sorted()")`key`]
        ```python
        list1 = ['123','12','1','2','wa']
        print(sorted(list1, key=len))
        >>>
        ['1', '2', '12', 'wa', '123']

        ```
-   创建列表
    -   示例：for循环创建列表
        ```python
        f = [x for x in range(1, 10)]
        print(f)
        ```
        ```python
        f = [x + y for x in 'ABCDE' for y in '1234567']
        print(f)
        >>>
        ['A1', 'A2', 'A3', 'A4', 'A5', 'A6', 'A7', 'B1', 'B2', 'B3', 'B4', 'B5', 'B6', 'B7', 'C1', 'C2', 'C3', 'C4', 'C5', 'C6', 'C7', 'D1', 'D2', 'D3', 'D4', 'D5', 'D6', 'D7', 'E1', 'E2', 'E3', 'E4', 'E5', 'E6', 'E7']

        ```
    -   示例：用这种语法创建列表之后元素已经准备就绪所以需要耗费较多的内存空间 \[`.getsizeof()`]
        ```python
        # 请注意下面的代码创建的不是一个列表而是一个生成器对象
        # 通过生成器可以获取到数据但它不占用额外的空间存储数据
        # 每次需要数据的时候就通过内部的运算得到数据(需要花费额外的时间)
        f = [x ** 2 for x in range(1, 1000)]
        print(sys.getsizeof(f))  # 查看对象占用内存的字节数
        print(f)
        ```
    -   示例：通过生成器可以获取到数据但它不占用额外的空间存储数据
        ```python
        f = (x ** 2 for x in range(1, 1000))
        print(sys.getsizeof(f))  # 相比生成式生成器不占用存储数据的空间
        print(f)
        for val in f:
            print(val)
        ```
    -   示例：除了上面提到的生成器语法，Python中还有另外一种定义生成器的方式，就是通过`yield`关键字将一个普通函数改造成生成器函数。下面的代码演示了如何实现一个生成[斐波拉切数列](https://zh.wikipedia.org/wiki/斐波那契数列 "斐波拉切数列")的生成器。所谓斐波拉切数列可以通过下面[递归](https://zh.wikipedia.org/wiki/递归 "递归")的方法来进行定义&#x20;
        ```python
        import sys
        def fib(n):
            a, b = 0, 1
            for _ in range(n):
                a, b = b, a + b
                yield a


        def main():
            for val in fib(20):
                print(val)


        if __name__ == '__main__':
            main()
        ```
-   可以支持索引和切片：
    ```python
    >>> squares = [1, 4, 9, 16, 25]
    >>> squares
    [1, 4, 9, 16, 25]
    ```
-   所有的切片操作都返回一个包含请求元素的新列表。这意味着一下切片操作会返回一个\[Py]浅拷贝：
    ```python
    >>> squares[:]
    [1, 4, 9, 16, 25]
    ```
-   也支持拼接操作：
    ```python
    >>> squares + [36, 49, 64, 81, 100]
    [1, 4, 9, 16, 25, 36, 49, 64, 81, 100]

    >>> squares * 2
    [1, 4, 9, 16, 25, 1, 4, 9, 16, 25]

    >>> squares[1:2] * 2
    [4, 4]

    ```
    与字符串不同，，列表是一个`mutable`类型，所以说列表的内容可以改变。
-   修改列表`squares`的索引0为10000000
    ```python
    >>> squares
    [1, 4, 9, 16, 25]

    >>> squares[0] =  10000000
    >>> squares
    [10000000, 4, 9, 16, 25]
    ```
-   还可以通过`append()`方法添加新元素
    ```python
    > squares.append(1)
    >> squares
    [10000000, 4, 9, 16, 25, 1]
    ```
-   切片也可以赋值
    ```python
    >>> squares
    [1, '1', 1, 1]

    >>> squares[0:2] = [1]
    >>> squares
    [1, 1, 1]
    ```
-   内置函数`len()`作用到列表上（计算列表存在多少数据）：
    ```python
    >>> letters = ['a', 'b', 'c', 'd']
    >>> len(letters)
    4
    ```
-   嵌套列表（列表中包含列表）：
    ```python
    >>> a = ['a', 'b', 'c']
    >>> n = [1, 2, 3]
    >>> x = [a, n]

    >>> x
    [['a', 'b', 'c'], [1, 2, 3]]

    >>> x[0]
    ['a', 'b', 'c']

    >>> x[0][1]
    'b'
    >>> x[1][1]
    2
    ```

