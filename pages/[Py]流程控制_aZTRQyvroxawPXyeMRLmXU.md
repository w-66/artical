# \[Py]流程控制

[\[Py\]if](\[Py]if_xtdeURaUuaCm63oszdcx14.md "\[Py]if")

[\[Py\]for
](\[Py]for_3XDGtKp2ikTvoRVv9WyCsn.md "\[Py]for
")

[\[Py\]while](\[Py]while_rh58JgvXSrEiXUqecUpEJQ.md "\[Py]while")

[\[Py\]else](\[Py]else_j83ZP9vnkKQazthe75SC9R.md "\[Py]else")

[\[Py\]pass语句
](\[Py]pass语句_ax1ettZeVxZiXqQQdJChhF.md "\[Py]pass语句
")

[\[Py\]二重循环中的break和continne用于控制本层循环](\[Py]二重循环中的break和continne用于控制本层循环_xsSTEfB9VysvQ2SyMAnjLt.md "\[Py]二重循环中的break和continne用于控制本层循环")

***

1.  \[Py]break、continut、循环中的else

    `break`用于跳出最近的[\[Py\]for
    ](\[Py]for_3XDGtKp2ikTvoRVv9WyCsn.md "\[Py]for
    ")或[\[Py\]while](\[Py]while_rh58JgvXSrEiXUqecUpEJQ.md "\[Py]while")循环。
    -   示例：以下搜索[素数（质数 prime number）](<素数（质数 prime number）_4ToLoWYgcWmLCiAVX8qPLX.md> "素数（质数 prime number）")的循环 \[`break`]
        ```python
        for n in range(2, 10):         # n遍历的范围2到10
            for x in range(2, n):      # x遍历的范围2到n
                if n % x == 0:         # 如果n除x余数等于0，则
                    print(n, 'equals', x, '*', n//x)
                    break              # 打印输出，并跳出循环
            else:
            # 否则（这里else不属于if，而是for）       # loop fell through without finding a factor
                print(n, 'is a prime number')        # 循环失败，找不到因数
        ```
        -   运行输出：
            ```python
            2 is a prime number
            3 is a prime number
            4 equals 2 * 2
            5 is a prime number
            6 equals 2 * 3
            7 is a prime number
            8 equals 2 * 4
            9 equals 3 * 3
            ```
            *题外-*[*孪生素数*](https://www.wolai.com/wq1314/4ToLoWYgcWmLCiAVX8qPLX#sgudVVBRtbHJrbyXzUuQ8Q "孪生素数")


    [continue](https://docs.python.org/zh-cn/3.9/reference/simple_stmts.html#continue "continue") 语句也是借鉴自 C 语言，**表示忽略循环中****`continue`****以下的代码并重新循环下一次迭代：**
    -   示例：[continue](https://docs.python.org/zh-cn/3.9/reference/simple_stmts.html#continue "continue")&#x20;
        ```python
        for num in range(2, 10):
            if num % 2 == 0:
                print("Found an even number", num)
                continue
            print("Found an odd number", num)
        ```
