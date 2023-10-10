# \[Py]标识符和保留字|关键词

`NotImplemented`

`NotImplemented`

#### Python标识符

有一些单词被我赋予了特定的意义，这些单词你在给你的任何对象起名字的时候都不能用

-   在python里，标识符有字母、数字、下划线组成。
-   在python中，所有标识符可以包括英文、数字以及下划线（\_），但不能以数字开头。
-   python中的标识符是区分大小写的。
-   不能用保留字

以下划线开头的标识符是有特殊意义的。以单下划线开头（\_foo）的代表不能直接访问的类属性，需通过类提供的接口进行访问，不能用"from xxx import \*"而导入；

以双下划线开头的（**foo）代表类的私有成员；以双下划线开头和结尾的（foo**）代表python里特殊方法专用的标识，如\_\_init（）代表类的构造函数。



#### Python**保留字**

下面的列表显示了在Python中的保留字。这些保留字不能用作常数或变数，或任何其他标识符名称。

`break`

[continue](https://docs.python.org/zh-cn/3.9/reference/simple_stmts.html#continue "continue")&#x20;

[\[Py\]yield](\[Py]yield_4a33mF1MdtNUSmYENBRJMb.md "\[Py]yield")

所有Python的关键字只包含小写字母。

| 关键字列表        |         |                                                                  |
| ------------ | ------- | ---------------------------------------------------------------- |
| and          | exec    | not                                                              |
| assert       | finally | or                                                               |
| break        | for     | pass                                                             |
| class        | from    | print                                                            |
| continue     | global  | raise                                                            |
| def          | if      | return                                                           |
| del          | import  | `[Py]try`                                                        |
| elif         | in      | while                                                            |
| else         | is      | [\[Py\]with](\[Py]with_mRCptztLCNdeHM1z8FMay2.md "\[Py]with")    |
| `[Py]except` | lambda  | [\[Py\]yield](\[Py]yield_4a33mF1MdtNUSmYENBRJMb.md "\[Py]yield") |

-   查看保留字

    ![](../image/image_HXsXq9v04-.png)

    None

