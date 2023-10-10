# \[Py]内置|预置函数

\[[official](https://docs.python.org/zh-cn/3/library/functions.html?highlight=id#id "official")]

[https://docs.python.org/zh-cn/3.9/library/functions.html](https://docs.python.org/zh-cn/3.9/library/functions.html "https://docs.python.org/zh-cn/3.9/library/functions.html")

不需要导入既可使用的函数，称为内置函数 <[OfficialDoc](https://docs.python.org/zh-cn/3.9/library/functions.html "OfficialDoc")>

[\[Py\]print()](\[Py]print\(\)_jmn3dLitMHH6aZT6urV6L2.md "\[Py]print()")打印

[\[Py\]open()](\[Py]open\(\)_ghtpmRBeZJdWUQ7qZ446Lr.md "\[Py]open()")打开文件

[\[Py\]type()](\[Py]type\(\)_5gEedTYkBh5er4jEarpyCM.md "\[Py]type()")输出类型

[\[Py\]sorted()](\[Py]sorted\(\)_rvtcB64n8EH2st4KdMqs5a.md "\[Py]sorted()")排序

`getattr()`获取对象属性 <同`__getattribute__()`>

`setattr()`设置对象属性

`delattr()`删除对象属性

`hasattr()`判断对象属性



[\[Py\]repr()](\[Py]repr\(\)_vbUG3hGrGndBNzeEUeG83X.md "\[Py]repr()")

[\[Py\]print()](\[Py]print\(\)_jmn3dLitMHH6aZT6urV6L2.md "\[Py]print()")

[\[Py\]open()](\[Py]open\(\)_ghtpmRBeZJdWUQ7qZ446Lr.md "\[Py]open()")

[\[Py\]type()](\[Py]type\(\)_5gEedTYkBh5er4jEarpyCM.md "\[Py]type()")

[\[Py\]id()](\[Py]id\(\)_hVWEiiERxXNgggB4Jb6iao.md "\[Py]id()")

[\[Py\]sum](\[Py]sum_32tt6UBjdhGExrScDiozkX.md "\[Py]sum")

[\[Py\]input()](\[Py]input\(\)_xmC3GN1MeoC5ZQDAxtPj7m.md "\[Py]input()")

[ \[Py\]range()](\[Py]range\(\)_pLPCNuvhFLF4TPKKD3xTaJ.md " \[Py]range()")

[\[Py\]input()](\[Py]input\(\)_t1vcEhaCTYvhQLuTzjHZjq.md "\[Py]input()")

[\[Py\]enumerate()](\[Py]enumerate\(\)_5ngjCbmBeqAhM3JtKsY9fP.md "\[Py]enumerate()")

[\[Py\]reversed()](\[Py]reversed\(\)_gWMPmjyvJHE7gXXcgp4mjW.md "\[Py]reversed()")

[\[Py\]sorted()](\[Py]sorted\(\)_rvtcB64n8EH2st4KdMqs5a.md "\[Py]sorted()")

[\[Py\]dir()](\[Py]dir\(\)_tGHi2hVKTb6ZSDLGBFMfqY.md "\[Py]dir()")

[\[Py\]id()](\[Py]id\(\)_ritCXjANmDxTjFxU8kih9A.md "\[Py]id()")

[\[Py\]datetime](\[Py]datetime_sYLqvAKMJVh3mwXXVq4z3o.md "\[Py]datetime")

-   `getattr()`
-   `setattr()`
-   `delattr()`
-   `hasattr()`

### 字符串的方法[¶](https://docs.python.org/zh-cn/3.9/library/stdtypes.html?highlight=isdecimal#string-methods "¶")

`str.isdecimal()`判断字符串是否为数字; 如果字符串中的所有字符都是十进制字符且该字符串至少有一个字符，则返回 `True` ， 否则返回 `False` 。十进制字符指那些可以用来组成10进制数字的字符，例如 U+0660 ，即阿拉伯字母数字0 。 严格地讲，十进制字符是 Unicode 通用类别 "Nd" 中的一个字符。

`str.isdecimal()`

