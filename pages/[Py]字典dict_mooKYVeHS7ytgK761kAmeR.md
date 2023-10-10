# \[Py]字典dict

[https://docs.python.org/zh-cn/3/library/stdtypes.html#mapping-types-dict](https://docs.python.org/zh-cn/3/library/stdtypes.html#mapping-types-dict "https://docs.python.org/zh-cn/3/library/stdtypes.html#mapping-types-dict")

字典的键 *几乎* 可以是任何值。 非 [hashable](https://docs.python.org/zh-cn/3/glossary.html#term-hashable "hashable") 的值，即包含列表、字典或其他可变类型的值（此类对象基于值而非对象标识进行比较）不可用作键。 数字类型用作键时遵循数字比较的一般规则：如果两个数值相等 (例如 `1` 和 `1.0`) 则两者可以被用来索引同一字典条目。 （但是请注意，由于计算机对于浮点数存储的只是近似值，因此将其用作字典键是不明智的。）

***

`.dict()`

#### 字典方法

`.items()`以列表返回可遍历的(键, 值) 元组数组

`.get()`以key查key对应的值

`.keys()`取key的值

`.value()`取value的值

`.update()`更新|新增键值



***

`.len()`字典长度

`.items()`

`.get()`

`.keys()`

`.value()`

`.update()`



***

***

## 示例

-   示例：新增键值 \[`.update()`]
    ```react&#x20;jsx
    ####### 嵌套字典
    dict = {}

    # 添加键值
    dict[1] = {'a':'apple'}
    print(dict)
    # 继续添加键值
    dict[1].update({'b':'big'})
    print(dict)

    >>>
    {1: {'a': 'apple'}}
    {1: {'a': 'apple', 'b': 'big'}}

    ```
-   示例：判断多个键值是否在字典中 \[`all()`]
    ```html
    my_dict = {'key1': 'value1', 'key2': 'value2', 'key3': 'value3'}

    keys_to_check = ['key1', 'key2', 'key3']

    all_present = all(key in my_dict for key in keys_to_check)

    if all_present:
        print("所有键值都在字典中")
    else:
        print("至少有一个键值不在字典中")

    ```
    在上述示例中，我们定义了一个名为`my_dict`的字典，并创建了一个包含要检查的键值的列表`keys_to_check`。然后，使用列表推导式遍历`keys_to_check`中的每个键，并检查它是否存在于`my_dict`字典中。

    通过`all()`函数对生成的布尔值迭代器进行判断，如果所有键值都存在于字典中，则`all()`函数返回`True`，否则返回`False`。根据返回结果，我们可以输出相应的提示信息。

    需要注意的是，`all()`函数会短路计算，一旦遇到一个键值不在字典中，就会立即返回`False`，不再继续判断后面的键值。
-   示例：两个字典的合并 <[空降](https://www.bilibili.com/video/BV1kT4y1u72i?t=555.4 "空降")>

    \*表示解包(Unpacking)

    ![](../image/image___LC4RIb7t.png)

    等同于

    ![](../image/image_0hbKmVyGSL.png)
-   示例：Python 字典(`.dict()`)的添加、删除、修改、更新、查询数据的操作 \[`.get()`]
    ```python
    # 创建空字典
    dict = {}

    # 添加
    #----------添加 key1到10 value值为空的字典
    for num in range(1, 10):
        dict[f'{num}']=[]
    print('添加 key1到10 value值为空的字典\n', dict)

    # 删除
    #----------删除key是1的键值对
    del dict['1']
    print('删除key是1的键值对\n', dict)

    # 修改|更新值
    dict['3']='你好' 
    print(dict)

    # 查询键值对
    print(dict['3'])
    print(dict.get('3'))

    ```
-   示例：字典的循环取值 \[`.keys()`,`.value()`,`.items()`]
    ```python
    # 创建空字典
    dict = {}
    #----------添加 key1到10 value值为空的字典 字典生成器
    for num in range(1, 10):
        dict[f'{num}']=num+1
    print(dict)

    #----------取key
    for item in dict.keys():
        print(item)


    #----------取key的value值
    for item in dict.values():
        print(item)

    #----------取key与value的值
    for k,v in dict.items():
        print(f'{k} = {v}')
    ```





## 碎片

`all()`
