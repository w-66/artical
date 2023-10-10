# \[Py]浮点float

-   整数部份和小数部份组成
-   浮点数存储不精确性
    -   使用浮点数进行计算时，可能会出现小数位不确定的情况

代码:查看浮点数计算结果

```python
n1, n2= 1.1, 2.2
n3 = n1 * n2
print(n3, type(n3))
>>>2.4200000000000004 <class 'float'>
...
n1, n2= 1.1, 2.2
n3 = n1 + n2
print(n3, type(n3))
 >>>3.3000000000000003 <class 'float'>
```

解决计算不精确的情况 (*不精确的情况不常见*)：

导入模块 [\[Py\]decimal](\[Py]decimal_hP3Zt2Mxa2LdFKKiD3ke8j.md "\[Py]decimal")

```python
from decimal import Decimal
print(Decimal('1.1') + Decimal('2.2'))
>>> 3.3

```

