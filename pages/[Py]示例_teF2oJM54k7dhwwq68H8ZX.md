# \[Py]示例

-   示例：`.endswith()``os.walk()``isfile()`


-   示例：文件内容去重，每行只有一组字符串 \[\[Py]`set()`]
    ```react&#x20;jsx
    # 打开文件并读取内容
    with open('F:\\network.dict - 副本.yaml', 'r', encoding='utf-8') as file:
        content = file.readlines()

    # 去除每行内容中的换行符
    content = [line.strip() for line in content]

    # 使用set进行去重
    unique_content = list(set(content))
    print(type(unique_content))

    # 将去重后的内容写入新文件
    with open('F:\\network.dict - 副本.yaml', 'w', encoding='utf-8') as file:
        file.write('\n'.join(unique_content))

    ```
-   示例：嵌套循环之乘法表 \[[\[Py\]for
    ](\[Py]for_3XDGtKp2ikTvoRVv9WyCsn.md "\[Py]for
    "),[\[Py\]print()](\[Py]print\(\)_jmn3dLitMHH6aZT6urV6L2.md "\[Py]print()")`end=`]
    ```python
    # a = 1
    # for one in range(1, 10):
    #     a += 1
    #     for tow in range(1,a):
    #         result = one * tow
    #         print(tow,'x' ,one,'=', result,end='\t')
    #     print()


    #
    # for one in range(1, 10):
    #     for tow in range(1,10):
    #         if one >= tow:
    #             result = one * tow
    #             print(tow,'x' ,one,'=', result,end='\t')
    #     print()

    # 教程中的实例

    for one in range(1, 10):
        for tow in range(1,one+1):
            print(tow,'x' ,one,'=', one * tow,end='\t')
        print()
    ```
-   示例：百位下的水仙花数 \[[\[Py\]for
    ](\[Py]for_3XDGtKp2ikTvoRVv9WyCsn.md "\[Py]for
    ")[\[Py\]if](\[Py]if_xtdeURaUuaCm63oszdcx14.md "\[Py]if"),[ \[Py\]range()](\[Py]range\(\)_pLPCNuvhFLF4TPKKD3xTaJ.md " \[Py]range()")]

    输出100到999之间的[水仙花数](水仙花数_bW8jDESuecxeYphAccCEvd.md "水仙花数")（水仙花数是指一个 3 位数，它的每个位上的数字的 3次幂之和等于它本身（例如：1^3 + 5^3+ 3^3 = 153）。）
    ```python
    # 分离各个位数
    # for hua  in range(999, 9999):
    #     qian = hua//1000 % 10
    #     bai = hua//100 % 10
    #     shi = hua // 10 % 10
    #     ge = hua % 10
    #     print(qian,bai,shi,ge)


    for hua  in range(99, 1000):
        bai = hua//100 % 10
        shi = hua // 10 % 10
        ge = hua % 10
        if hua == (bai**3 + shi**3 + ge**3):
            print(hua)

    ```
    -   输出结果
        ```python
        153
        370
        371
        407
        ```

