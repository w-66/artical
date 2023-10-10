# \[Py]特殊方法|魔法方法

1.  `__subclasses__()`

***

1.  `__new__()`
2.  `__init__()`
3.  `__len__()`
4.  `__str__()`
5.  `__del__()`
6.  `__getattr__()`
7.  `__getattribute__()`
8.  `__setattr__()`

算术运算

1.  `__add__()`

反算术运算

\_\_radd\_\_()



增强赋值运算

\_\_iadd\_\_()



一元运算

其他运算



***

1.  [\[Py\]特殊方法|魔法方法](\[Py]特殊方法-魔法方法_d9gQzVJoyk4xcnF4UXETgu.md "\[Py]特殊方法|魔法方法")和特殊属性
    1.  特殊属性
        1.  `__dict__`：获得类对象或实例对象所绑定的所有属性和方法的字典
            -   一个字典或其他类型的映射对象，用于存储对象的（可写）属性。
        2.  `__class__`类实例所属的类; 对象属于哪个类
        3.  `__bases__`类的父类(元组); 由类对象的基类所组成的元组
        4.  `__baase__`类包含多个父类，输出第一个父类
        5.  `__mor__`类的层次结构; 类的所有父类与父类的父类...
        6.  `__slots__`添加此属性之后，就无法动态添加属性，但也节约了空间(内存); 继承父类的\_\_slots\_\_属性不会在子类中生效
    2.  [\[Py\]特殊方法|魔法方法](\[Py]特殊方法-魔法方法_d9gQzVJoyk4xcnF4UXETgu.md "\[Py]特殊方法|魔法方法")：具有特殊功能的方法[^注释1]; `__xx__`格式
        1.  `__subclasses__()`类包含(被调用)的子类(列表)
        ***
        1.  `__add__()`：两个对象进行加法运算
        2.  `__len__()`：通过重写\_\_len\_\_()，让内置函数len()的参数可以是自定义类型
        3.  `__new__()`：用于创建对象
        4.  `__init__()`初始化对象[^注释2]; 对创建的对象进行初始化; 初始化方法
            -   在创建一个对象时默认被调用
            -   当中的self参数，不需要开发者传递，Python解释器会自动把当前的对象引用传递过去
            -   带参数的`__init__()`
        5.  `__str__()`打印时，会打印从这个方法中return数据
            -   当使用print对象的时候，默认打印对象的内存地址
        6.  `__del__()`当删除对象时，Python解释器会默认调用\_\_del\_\_()方法
            -   调用完对象之后内存默认会删除，所以会调用\_\_del\_\_()方法删除
            -
        7.  `__getattr__()`获取对象的属性。





***

-   示例：实现是将两个对象的a属性合并到一个列表中`__add__()`

    [https://segmentfault.com/a/1190000040286979](https://segmentfault.com/a/1190000040286979 "https://segmentfault.com/a/1190000040286979")
    ```python
    class A:
        def __init__(self,a):
            self.a=a
        def __add__(self,others):
            print('this is a magic method')
            return [self.a,others.a]
        
    >>>a=A(1)
    >>>b=A(3)
    >>>c=a+b#自定义的__add__方法，实现是将两个对象的a属性合并到一个列表中
    this is a magic method#+调用的是__add__方法
    >>>c
    [1, 3]

    >>>a.__add__(b)#等价于直接调用
    this is a magic method
    [1, 3]
    ```

[^注释1]: [https://www.bilibili.com/video/BV14q4y1976H/?p=10\&spm\_id\_from=pageDriver\&vd\_source=d87be07aa170c6f76058fa2663ca0da0](https://www.bilibili.com/video/BV14q4y1976H/?p=10\&spm_id_from=pageDriver\&vd_source=d87be07aa170c6f76058fa2663ca0da0 "https://www.bilibili.com/video/BV14q4y1976H/?p=10\&spm_id_from=pageDriver\&vd_source=d87be07aa170c6f76058fa2663ca0da0")

[^注释2]: [https://www.bilibili.com/video/BV14q4y1976H/?p=10\&spm\_id\_from=pageDriver\&vd\_source=d87be07aa170c6f76058fa2663ca0da0\&t=272.6](https://www.bilibili.com/video/BV14q4y1976H/?p=10\&spm_id_from=pageDriver\&vd_source=d87be07aa170c6f76058fa2663ca0da0\&t=272.6 "https://www.bilibili.com/video/BV14q4y1976H/?p=10\&spm_id_from=pageDriver\&vd_source=d87be07aa170c6f76058fa2663ca0da0\&t=272.6")
