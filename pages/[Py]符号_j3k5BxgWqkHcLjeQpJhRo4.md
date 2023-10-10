# \[Py]符号





1.  `'''`Python多行注释、多行赋值
2.  `_`单下划线

    ([Python中下划线的含义](https://www.runoob.com/w3cnote/python-5-underline.html "Python中下划线的含义"))
    -   单下划线 `_`

        按照习惯，有时候单个独立下划线是用作一个名字，来表示某个变量是临时的或无关紧要的。
        -   示例：在下面的循环中，我们不需要访问正在运行的索引，我们可以使用"\_"来表示它只是一个临时值 \[`_`]
            ```javascript
            >>> for _ in range(32):
            ...    print('Hello, World.')
            ```
3.  `__`私有类属性;

位置传参`*`

关键词传参`**`

`*`表示元组,`**`表示字典。 字典参数放在元组参数后面,且放在参数列表最后

`'''`

`_`

`__`

`*`

`**`



|=





-   示例：`**`的应用

    在Python中，`**` 是幂运算符，用于计算一个数的某个幂次方。它可以用在不同的上下文中，下面是一些常见的用法：
    1.  **计算幂次方：**
        ```python
        result = 2 ** 3  # 计算 2 的 3 次方，结果为 8
        ```
    2.  **计算平方根或立方根：**
        ```python
        square_root = 16 ** 0.5  # 计算 16 的平方根，结果为 4.0
        cube_root = 8 ** (1/3)   # 计算 8 的立方根，结果为 2.0
        ```
    3.  **用于函数参数传递：**

        `**` 还可以用于函数参数传递，将一个字典中的键值对作为关键字参数传递给函数。
        ```python
        def print_info(name, age):
            print(f"Name: {name}, Age: {age}")

        info_dict = {'name': 'Alice', 'age': 30}
        print_info(**info_dict)  # 传递字典中的键值对作为关键字参数
        ```
        这将输出：`Name: Alice, Age: 30`。
    4.  **定义函数参数时的可变关键字参数：**

        `**` 也可以用于函数定义中，表示可变的关键字参数，这使得函数能够接受任意数量的关键字参数，并将它们作为字典处理。
        ```python
        def process_data(**kwargs):
            for key, value in kwargs.items():
                print(f"{key}: {value}")

        process_data(name='Alice', age=30, city='New York')
        ```
        这将输出：
        ```bash
        name: Alice
        age: 30
        city: New York
        ```
    总之，`**` 在Python中用于幂运算、传递函数参数、处理关键字参数等不同的上下文中。其用途非常灵活，根据不同的需求可以有不同的应用方式。
