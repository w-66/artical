# \[Py]字符串操作

### Python字符串运算符

字符串内容前的字母含义

`r`,`R`表示无转义的字符串，内容为纯字符串，避免转义。



`f`表示字符串内容中可以以`{}`插入变量



`r`

`R`

`f`

-   示例：`r`
    ```python
    print(r'\n\n\n/n123')

    >>>
    \n\n\n/n123
    ```
    ***
    不带r
    ```python
    print('\n\n\n/n123')
    >>>


    /n123
    ```

| 操作符    | 描述                                                                                                      | 实例                                   |
| ------ | ------------------------------------------------------------------------------------------------------- | ------------------------------------ |
| +      | 字符串连接                                                                                                   | >>>a + b 'HelloPython'               |
| \*     | 重复输出字符串                                                                                                 | >>>a \* 2 'HelloHello'               |
| \[ ]   | 通过索引获取字符串中字符                                                                                            | >>>a\[1] 'e'                         |
| \[ : ] | 截取字符串中的一部分                                                                                              | >>>a\[1:4] 'ell'                     |
| in     | 成员运算符 - 如果字符串中包含给定的字符返回 True                                                                            | >>>"H" in a True                     |
| not in | 成员运算符 - 如果字符串中不包含给定的字符返回 True                                                                           | >>>"M" not in a True                 |
| r/R    | 原始字符串 - 原始字符串：所有的字符串都是直接按照字面的意思来使用，没有转义特殊或不能打印的字符。 原始字符串除在字符串的第一个引号前加上字母"r"（可以大小写）以外，与普通字符串有着几乎完全相同的语法。 | >>>print r'\n' \n >>> print R'\n' \n |
| %      | 格式字符串                                                                                                   |                                      |

#### Python 字符串格式化符号

`%c`

`%s`

***

print ("我叫 %s 今年 %d 岁!" % ('小明', 10))



`%c`格式化字符及其ASCII码

`%s`格式化字符串


`%i`转换为带符号的十进制整数


`%d`格式化整数


`%u`格式化无符号整型


`%o`格式化无符号八进制数


`%x`格式化无符号十六进制数


`%X`格式化无符号十六进制数（大写）


`%f`格式化浮点数字，可指定小数点后的精度


`%e`用科学计数法格式化浮点数


`%E`作用同`%e`，用科学计数法格式化浮点数


`%g` `%f`和`%e`的简写

`%G` `%F` 和 `%E` 的简写

`%p`用十六进制数格式化变量的地址


`%r`使用 repr() 函数将表达式转换为字符串

### Python字符串方法

1.  `.replace`方法把字符串中的 old（旧字符串） 替换成 new(新字符串)，如果指定第三个参数max，则替换不超过 max 次。`str.replace(old, new[, max])`
2.  `.split()`指定分隔符，分隔字符串



1.  `.len()`返回字符串长度
2.  `.capitalize()`返回首字母大写的输入
3.  `.title()`每个单词的首字母大写
4.  `.upper()`所有字母大写
5.  `.lower()`字母小写
6.  `.find()`查找字符串所在位置(下标)
7.  `.index()`与`.find()`类似
8.  `.startswith()`判断字符串是否以指定的字符串开头
9.  `.endswith()`判断字符串是否以指定的字符串结尾
10. `.center()`对指定字符串两侧填充指定字符
    -   `print(str1.center(50, 'h'))`
11. `.rjust()`对指定字符串左侧填充指定字符
    -   `print(str1.rjust(40, 'o'))`
    -   示例
        ```python
        print('str'.rjust(20))      # 默认空格
        print('str'.rjust(20, '*')) # 指定左边插入*

        >>>
        *****************str
                         str

        ```
12. `.isdigit()`判断是否由数字组成
13. `.isalpha()`判断是否由数字组成
14. `.isalnum()`判断是否由数字,字母组成，它返回一个布尔值，如果字符串只包含数字字符，则返回 `True`，否则返回 `False`。
15. `.strip()`删除两侧的空格
16. `.join`Concatenate any number of strings. <ʷ[number](number_rt27iGESV6RxJa1DUxNKD4.md "number")n.数量;>

    The string whose method is called is inserted in between each given string. The result is returned as a new string.

    Example: `'.'.join(['ab', 'pq', 'rs'])` >>> `ab.pq.rs`



1.  `.replace`
2.  `.split()`



1.  `.len()`
2.  `.capitalize()`
3.  `.title()`
4.  `.upper()`
5.  `.lower()`
6.  `.find()`
7.  `.index()`
8.  `.startswith()`
9.  `.endswith()`
10. `.center()`
11. `.rjust()`
12. `.isdigit()`
13. `.isalpha()`
14. `.isalnum()`
15. `.strip()`
16. `.join`





### \[Py]python字符串中插入变量的三种方法|格式化字符串&#x20;

-   字符串中插入变量1/4：在字符串前后使用`+`连接
-   字符串中插入变量2/4：Python 字符串格式化符号
    -   示例：Python 字符串格式化符号 \[`%s`]
        ```python
        message = '我的银行卡密码:'
        age = 23
        print("我今年%s岁，%s123121"  %(age,message))
        ```
        ![](../image/image_3O-s2kcu0E.png)
-   字符串中插入变量3/4：格式化

    print语句中加入`f`就可以起到和`format`函数类似的作用。

    PEP 498（即Python Enhancement Proposals， Python增强提案或Python改进建议书），引入了一种新的字符串字面量:f-字符串，或格式化字符串字面量。格式化字符串字面值以’f’作为前缀，类似于str.format()所接受的格式字符串。它们包含用花括号括起来的替换字段。
    -   示例：字符串中插入变量3/3：格式化：print语句中加入`f`就可以起到和`format`函数类似的作用。
        ```python
        message = '我的银行卡密码:'
        age = 23
        print(f'我今年{age},{message}123')
        ```
        ![](../image/image_VXjShSoSjB.png)
    ***
-   4/4：formt方法 (不推荐)

    ![](../image/image_dHD_m2LMfH.png)

***

在Python中，你可以使用字符串格式化技术将变量插入文本（字符串）中。有几种常见的方法可以实现这一点，以下是其中的一些方法：

1.  使用f-string（格式化字符串字面值） - 适用于Python 3.6及更高版本：
    ```python
    name = "小明"
    age = 30

    # 使用f-string将变量插入文本
    message = f"我的名字是{name}，今年{age}岁了。"
    print(message)
    ```
2.  使用`.format()` 方法：
    ```python
    name = "小明"
    age = 30

    # 使用format方法将变量插入文本
    message = "我的名字是{}，今年{}岁了。".format(name, age)
    print(message)
    ```
3.  使用`%`格式化（旧方法，仍然支持，但不建议在新代码中使用）：
    ```python
    name = "小明"
    age = 30

    # 使用%格式化将变量插入文本
    message = "我的名字是%s，今年%d岁了。" % (name, age)
    print(message)
    ```

所有这些方法都可以实现相同的效果，即将变量的值插入到文本中。然而，f-string（第一种方法）被认为是最可读性和现代化的字符串格式化方式。













## 碎片

字符串有多种形式，`('')、("")`单引号和双引号都可以的得到同样的结果。反斜杠‘`\`’用来转义

```python
>>> 'spam eggs'  # single quotes
'spam eggs'

>>> "\"Yes,\" they said."
'"Yes," they said.'

>>> '"Isn\'t," they said.'
'"Isn\'t," they said.' 
```

-   使用单引号或者双引号时的输出结果：
    -   if 单引号输出双引号：
        ```python
        >>> "1"
        '1'
        ```
    -   if 双引号输出单引号：
        ```python
        >>> "1"
        '1'
        ```
    -   if 引号内出现了其它符号：
        ```python
        >>> "1'"
        "1'"
        ```
        ```python
        >>> '1"'
        '1"'
        ```




    如果你不希望前置“`\`”的字符转义成特殊符号，可以使用*原始字符串*方式，在引号前添加`r`既可。

    例如下方的`\n`是特殊符号的换行符，需要消除对影响

```python
>>> print("\one\note")
\one
ote

>>> print(r"\one\note")
\one\note

```

### &#x20;   字符串字面值可以跨行输入

1.  一种方式是用三重引号："""...""" 或 '''...'''，字符串中的**回车换行会自动包含到字符串中**，如果不想包含，在行尾添加一个 `\` 即可。
    ```python
    print("""\
    Usage: thingy [OPTIONS]
         -h                        Display this usage message
         -H hostname               Hostname to connect to
    """) 
    ```
    输出：
    ```python
    Usage: thingy [OPTIONS]
         -h                        Display this usage message
         -H hostname               Hostname to connect to
    ```

### &#x20;   字符串之间进行连接和重复

1.  “`+`”进行连接字符串，也可以使用“`*`”进行重复：
    ```python
    >>> "1" + "1"
    '11'
    >>> "1" + "1" + '2'
    '112'
    >>> "1" + "1" + '2' * 3
    '11222'

    ```
2.  &#x20;can't concatenate a variable and a string literal



### &#x20;   字符串的索引（下标访问），第一个字符索引是0。

1.  索引变量`word` 是0的字符：
    ```python
    >>> word = 'Python'
    >>> word[0]  # character in position 0
    'P'
    ```
2.  可以使用负数
    ```python
    >>> word[-1]  # last character
    'n'
    >>> word[-2]  # second-last character
    'o'
    >>> word[-6]
    'P'
    ```



### &#x20;   字符串切片

> 索引得到单个字符串，切片得到指定的字符串片段

```python
>>> word[0:2]  # characters from position 0 (included) to 2 (excluded)
'Py' 
```

1.  **切片的开始总是被包括在结果中，而结束不被包括。**
2.  切片的索引有默认值；省略开始索引时默认为0，省略结束索引时默认为到字符串的结束:
    ```python
    >>> word[:2]   # character from the beginning to position 2 (excluded)
    'Py'

    >>> word[4:]   # characters from position 4 (included) to the end
    'on'

    >>> word[-2:]  # characters from the second-last (included) to the end
    'on' 
    ```
    -   理解
        ```python
         +---+---+---+---+---+---+
         | P | y | t | h | o | n |
         +---+---+---+---+---+---+
           0   1   2   3   4   5   6
          -6  -5  -4  -3  -2  -1
        ```
3.  使用过大的索引回产生一个错误
    ```python
    >>> word[42]  # the word only has 6 characters
    Traceback (most recent call last):
      File "<stdin>", line 1, in <module>
    IndexError: string index out of range
    ```
    但是，切片中的越界索引会被自动处理:
    ```python
    >>> word[4:42]
    'on'
    >>> word[42:]
    ''
    ```



4\. Python 中的字符串不能被修改，它们是 `immutable`（不可改变的）的。因此，向字符串的某个索引位置赋值会产生一个错误:

```python
>>> word[0] = 'J'
Traceback (most recent call last):
  File "<stdin>", line 1, in <module>
TypeError: 'str' object does not support item assignment
>>> word[2:] = 'py'
Traceback (most recent call last):
  File "<stdin>", line 1, in <module>
TypeError: 'str' object does not support item assignment
```

-   如果需要一个不同的字符串，应当新建一个:
    ```python
    >
    >> 'J' + word[1:]
    'Jython'
    >> word[:2] + 'py'
    'Pypy'
    ```
-   内建函数 len() 返回一个字符串的长度:
    ```python
    > s = 'supercalifragilisticexpialidocious'
    >> len(s)
    34
    ```

<!---->

-   参见

    [文本序列类型 --- str](https://docs.python.org/zh-cn/3.9/library/stdtypes.html#textseq "文本序列类型 --- str")

    字符串是一种 序列类型 ，因此也支持序列类型的各种操作。

    [字符串的方法](https://docs.python.org/zh-cn/3.9/library/stdtypes.html#string-methods "字符串的方法")

    字符串支持许多变换和查找的方法。

    [格式化字符串字面值](https://docs.python.org/zh-cn/3.9/reference/lexical_analysis.html#f-strings "格式化字符串字面值")

    内嵌表达式的字符串字面值。

    格[式字符串语法](https://docs.python.org/zh-cn/3.9/library/string.html#formatstrings "式字符串语法")

    使用 str.format() 进行字符串格式化。

    [printf 风格的字符串格式化](https://docs.python.org/zh-cn/3.9/library/stdtypes.html#old-string-formatting "printf 风格的字符串格式化")

    这里详述了使用 % 运算符进行字符串格式化。





[\[Py\]转义字符与原字符](\[Py]转义字符与原字符_tb4u2kigwNwUXgQuLxqteX.md "\[Py]转义字符与原字符")
