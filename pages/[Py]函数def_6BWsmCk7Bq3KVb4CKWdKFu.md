# \[Py]函数def

`def`

`yield`

***

#### 函数的说明文档

-   示例：函数的说明文档
    ```python
    def demo_def_doc(parameter1, parameter2):
        '''
        自定义函数中的函数文档说明演示
        :param parameter1: 形参1的说明
        :param parameter2: 形参2的说明
        :return: 返回值的说明
        '''
        print(parameter1 + parameter2)

    demo_def_doc(1, 1)
    ```
    ![](../image/image_cUuWYFBiY3.png)

## 函数的参数定义

#### 形参定义默认值

-   示例：
    ```python
    def rename_text(a=0, b=0):
        return a+b

    if __name__ == '__main__':
        print(rename_text(b=13))
    ```

#### 可变参数|位置传参`*`|关键词传参`**`

`*`表示元组,`**`表示字典。 字典参数放在元组参数后面,且放在参数列表最后

-   示例：可变参数|位置传参`*`|关键词传参`**` \[]
    ```python
    def demo(num, *nums, **person):
     
        # nums是一个元组; person是一个字典
        print(num)      # 1
        print(nums)     # (2, 3, 4, 5)
        print(person)   # {'name': '小明', 'age': 18}
     

    demo(1, 2, 3, 4, 5, name="小明", age=18)
    ```



## 函数嵌套

作用：1、内部的嵌套函数可以作为值传递



## 笔记v0

-   示例：我们可以创建一个任意范围内[斐波那契数列（Fibonacci）](斐波那契数列（Fibonacci）_kdZmo6bwNsJPvj5s2xUAmw.md "斐波那契数列（Fibonacci）")的函数
    ```python
    def fib(n):    # write Fibonacci series up to n
        """Print a Fibonacci series up to n."""
        a, b = 0, 1
        while a < n:
            print(a, end=' ')
            a, b = b, a+b

    # Now call the function we just defined:
    fib(2000)
    ```
    -   write Fibonacci series up to n

        写斐波那契数列直到n
    -   Now call the function we just defined:

        现在调用我们刚刚定义的函数：
    运行输出
    ```python
    fib(2000)
    0 1 1 2 3 5 8 13 21 34 55 89 144 233 377 610 987 1597
    ```
-   思维导图 C参考

    ![](../image/image_RIHNd4_Yu8.png)

关键字`def`引入一个函数*定义*。他必须后跟函数名称和带括号的心事参数列表，构成函数体的语句从下一行开始，并且必须缩进。

> 函数体的第一个语句可以（可选的）是字符串文字；这个字符串文字是函数的文档字符串或 docstring（[文档字符串](https://www.wolai.com/wq1314/frAN9kSKDKrxf3bQAuU1k3#qEopw6WpEGmy2uFbZq1Bpv "文档字符串")） 。有些工具使用文档字符串自动生成在线或印刷文档，或者让用户以交互式的形式浏览代码；在你编写的代码中包含文档字符串是一种很好的做法，所以要养成习惯。



~~循环的最后加一个~~~~`print()`~~~~是因为给最后完成打印之后一个换行~~

函数的** 执行 **会引入一个用于函数局部变量的新符号表。 更确切地说，**函数中所有的变量赋值都将存储在局部符号表中；**而变量引用会首先在**局部符号表**中查找，然后是**外层函数的局部符号表**，再然后是**全局符号表**，最后是**内置名称的符号表**。因此，全局变量和外层函数的变量不能在函数内部直接赋值（除非是在 `global`<全局> 语句中定义的全局变量，或者是在 `nonlocal`<非本地> 语句中定义的外层函数的变量），尽管它们可以被引用。

函数在调用时，实际参数（）会被引入被调用的本地符号表中；因此，实参是通过 **按值调用 **传递的（*其中****值****始终是对象****引用****而不是对象的值）*，*实际上，通过对象引用调用 会是一个更好的表述，因为如果传递的是可变对象，则调用者将看到被调用者对其做出的任何更改（插入到列表中的元素）。***当一个函数调用另外一个函数时，将会为该调用创建一个新的本地符号表。**

函数定义会将函数名称与函数对象在当前符号表中进行关联。解释器会将该名称所指向的对象识别为用户自定义函数。 其他名称也可指向同一个函数对象并可被用来访问访函数:

```python
>>> fib
<function fib at 10042ed0>
>>> f = fib
>>> f(100)
0 1 1 2 3 5 8 13 21 34 55 89
```

-   实践实例
    ```python
    def fib2(n):  # return Fibonacci series up to n
        """Return a list containing the Fibonacci series up to n."""
        result = []
        a, b = 0, 1
        while a < n:
            result.append(a)    # see below
            a, b = b, a+b
        return result

    print(fib2)
    f = fib2
    print(f(11))
     
    ```
    ```python
    <function fib2 at 0x02B17100>
    [0, 1, 1, 2, 3, 5, 8]
    ```
-   示例：写一个返回斐波那契数列的列表（而不是把它打印出来）的函数
    ```python
    def fib2(n):  # return Fibonacci series up to n
        """Return a list containing the Fibonacci series up to n."""
        result = []
        a, b = 0, 1
        while a < n:
            result.append(a)    # see below
            a, b = b, a+b
        return result

    f100 = fib2(100)    # call it
    f100                # write the result
    ```
    ```python
    [0, 1, 1, 2, 3, 5, 8, 13, 21, 34, 55, 89]
    ```
