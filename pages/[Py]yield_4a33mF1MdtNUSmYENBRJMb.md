# \[Py]yield

[yield](yield_mKzZZDL9nLVgXJD5mhvEgf.md "yield") [statement](statement_bZ15UVeZneU7NZBV1S1gWU.md "statement")

***

参考1：[https://www.bilibili.com/video/BV1kT4y1u72i?t=248.3](https://www.bilibili.com/video/BV1kT4y1u72i?t=248.3 "https://www.bilibili.com/video/BV1kT4y1u72i?t=248.3") \[示例：一个斐波那契数列的生成 \[[\[Py\]yield](\[Py]yield_4a33mF1MdtNUSmYENBRJMb.md "\[Py]yield"),`_`]]



##



-   示例：一个斐波那契数列的生成 \[[\[Py\]yield](\[Py]yield_4a33mF1MdtNUSmYENBRJMb.md "\[Py]yield"),`_`]

    修改前

    ![](../image/image_Vgsc5BhHIV.png)

    修改后

    ![](../image/image_cP9Ezvoyrx.png)

    每当计算出一个值(也就是a)，就立即将实参传出(返回)
-   示例：[\[Py\]yield](\[Py]yield_4a33mF1MdtNUSmYENBRJMb.md "\[Py]yield")
    ```python
    $ vim test.py

    ```
    ```python
    #! /usr/bin/env python3
    # -*- coding:utf-8 -*-

    import time

    def consumer():
        r = ""
        while True:
            n = yield r
            if not n:
                return
            print("consumer %s"%n)
            r = "200 OK"

    def producer(c):
        c.__next__()
        n = 0
        while n < 3:
            n = n + 1
            print("producer %s"%n)
            r = c.send(n)
            print("producer return %s\n"%r)
        c.close()

    if __name__ == "__main__":
        c = consumer()
        producer(c)

    ```
    ```python
    $ python3 test.py
    producer 1
    consumer 1
    producer return 200 OK

    producer 2
    consumer 2
    producer return 200 OK

    producer 3
    consumer 3
    producer return 200 OK

    ```
    代码分析：首先调用`c.__next__()`启动生成器，一旦生产出东西，则通过`c.send(n)`切换到消费者`consumer`来执行，消费者`consumer`通过`yield`获取到消息后处理，然后通过`yield`将结果传回。生产者`producer`获取到消费者`consumer`处理的结果后继续生产下一条消息。整个过程无锁，由一个线程执行，生产者和消费者协作完成任务，所以称之为协程。

    Python通过`yield`提供了对协程的基本支持，但并不完全。而第三方的Gevent为Python提供了比较完善的协程支持，Gevent是第三方库，可通过Greenlet实现协程。另外，Python中由于GIL的存在导致多线程一直不是很好用，相比之下，协程的优势就更加突出了。

