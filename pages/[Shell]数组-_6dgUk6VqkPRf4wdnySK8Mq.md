# \[Shell]数组\*

[http://c.biancheng.net/view/810.html](http://c.biancheng.net/view/810.html "http://c.biancheng.net/view/810.html")



和其他编程语言一样，Shell 也支持数组。数组（Array）是若干数据的集合，其中的每一份数据都称为元素（Element）。

Shell 并且没有限制数组的大小，理论上可以存放无限量的数据。和 [C++](http://c.biancheng.net/cplus/ "C++")、[Java](http://c.biancheng.net/java/ "Java")、[C#](http://c.biancheng.net/csharp/ "C#") 等类似，Shell 数组元素的下标也是从 0 开始计数。

获取数组中的元素要使用中括号`[]`，下标可以是一个整数，也可以是一个结果为整数的表达式；当然，下标必须大于等于 0。

遗憾的是，常用的 Bash Shell 只支持一维数组，不支持多维数组。

#### Shell 数组的定义`()`

在 Shell 中，用括号`( )`来表示数组，数组元素之间用空格来分隔。由此，定义数组的一般形式为：

array\_name=(ele1  ele2  ele3 ... elen)

注意，赋值号`=`两边不能有空格，必须紧挨着数组名和数组元素。

-   示例：下面是一个定义数组的实例：
    ```bash
    nums=(29 100 13 8 91 44)
    ```
-   示例：Shell 是弱类型的，它并不要求所有数组元素的类型必须相同，例如：
    ```bash
    arr=(20 56 "http://c.biancheng.net/shell/")
    ```
    第三个元素就是一个“异类”，前面两个元素都是整数，而第三个元素是字符串。
-   示例：Shell 数组的长度不是固定的，定义之后还可以增加元素。例如，对于上面的 nums 数组，它的长度是 6，使用下面的代码会在最后增加一个元素，使其长度扩展到 7：
    ```bash
    nums[6]=88
    ```
-   示例：此外，你也无需逐个元素地给数组赋值，下面的代码就是只给特定元素赋值：
    ```bash
    ages=([3]=24 [5]=19 [10]=12)
    ```
    以上代码就只给第 3、5、10 个元素赋值，所以数组长度是 3。

#### 获取数组元素`[]`

-   获取数组元素的值，一般使用下面的格式：`${array_name[index]}`

    其中，array\_name 是数组名，index 是下标。例如：
    ```bash
    n=${nums[2]}
    ```
    表示获取 nums 数组的第二个元素，然后赋值给变量 n。再如：
    ```bash
    echo ${nums[3]}
    ```
    表示输出 nums 数组的第 3 个元素。
-   使用@或\*可以获取数组中的所有元素，例如：
    ```bash
    ${nums[*]}
    ${nums[@]}
    ```
    两者都可以得到 nums 数组的所有元素。

<!---->

-   示例：数组的完整演示
    ```bash
    #!/bin/bash

    nums=(29 100 13 8 91 44)
    echo ${nums[@]}  # 输出所有数组元素
    nums[10]=66      # 给第10个元素赋值（此时会增加数组长度）
    echo ${nums[*]}  # 输出所有数组元素
    echo ${nums[4]}  # 输出第4个元素
    ```
    运行结果： &#x20;

    29 100 13 8 91 44 &#x20;

    29 100 13 8 91 44 66 &#x20;

    91

#### Shell获取数组长度\[@|\*,#]

所谓数组长度，就是数组元素的个数。

利用`@`或`*`，可以将数组扩展成列表，然后使用`#`来获取数组元素的个数，格式如下：

`${#array_name[@]}  `

`${#array_name[*]}`

其中 array\_name 表示数组名。两种形式是等价的，选择其一即可。

如果某个元素是字符串，还可以通过指定下标的方式获得该元素的长度，如下所示：

\${#arr\[2]}

获取 arr 数组的第 2 个元素（假设它是字符串）的长度。

#### Shell数组拼接，Shell数组合并

[http://c.biancheng.net/view/818.html](http://c.biancheng.net/view/818.html "http://c.biancheng.net/view/818.html")

所谓 Shell 数组拼接（数组合并），就是将两个数组连接成一个数组。

拼接数组的思路是：先利用`@`或`*`，将数组扩展成列表

-   示例：其中，array1 和 array2 是需要拼接的数组，array\_new 是拼接后形成的新数组。

    下面是完整的演示代码：
    ```bash
    #!/bin/bash

    array1=(23 56)
    array2=(99 "http://c.biancheng.net/shell/")
    array_new=(${array1[@]} ${array2[*]})

    echo ${array_new[@]}  #也可以写作 ${array_new[*]}
    ```
    运行结果： &#x20;

    23 56 99 [http://c.biancheng.net/shell/](http://c.biancheng.net/shell/ "http://c.biancheng.net/shell/")

#### Shell删除数组元素（也可以删除整个数组）

在 Shell 中，使用 **unset **关键字来删除数组元素，具体格式如下：

```纯文本
unset array_name[index]
```

其中，array\_name 表示数组名，index 表示数组下标。

如果不写下标，而是写成下面的形式：

unset array\_name

那么就是删除整个数组，所有元素都会消失。

示例：下面我们通过具体的代码来演示：

```bash
#!/bin/bash

arr=(23 56 99 "http://c.biancheng.net/shell/")
unset arr[1]
echo ${arr[@]}

unset arr
echo ${arr[*]}
```

运行结果：

23 99 [http://c.biancheng.net/shell/](http://c.biancheng.net/shell/ "http://c.biancheng.net/shell/") &#x20;

注意最后的空行，它表示什么也没输出，因为数组被删除了，所以输出为空。

# Shell关联数组（下标是字符串的数组）

