# \[Shell]函数

<http://c.biancheng.net/view/1009.html>

-   快照

    Shell 函数的本质是一段可以重复使用的脚本代码，这段代码被提前编写好了，放在了指定的位置，使用时直接调取即可。

    Shell 中的函数和[C++](http://c.biancheng.net/cplus/ "C++")、[Java](http://c.biancheng.net/java/ "Java")、[Python](http://c.biancheng.net/python/ "Python")、[C#](http://c.biancheng.net/csharp/ "C#") 等其它编程语言中的函数类似，只是在语法细节有所差别。

    Shell 函数定义的语法格式如下：

    function name() { &#x20;

    statements &#x20;

    \\\[return value\\] &#x20;

    }

    对各个部分的说明：
    -   `function`是 Shell 中的关键字，专门用来定义函数；
    -   `name`是函数名；
    -   `statements`是函数要执行的代码，也就是一组语句；
    -   `return value`表示函数的返回值，其中 return 是 Shell 关键字，专门用在函数中返回一个值；这一部分可以写也可以不写。
    由`{ }`包围的部分称为函数体，调用一个函数，实际上就是执行函数体中的代码。
    ## 函数定义的简化写法
    如果你嫌麻烦，函数定义时也可以不写 function 关键字：

    name() { &#x20;

    statements &#x20;

    \\\[return value\\] &#x20;

    }

    如果写了 function 关键字，也可以省略函数名后面的小括号：

    function name { &#x20;

    statements &#x20;

    \\\[return value\\] &#x20;

    }

    我建议使用标准的写法，这样能够做到“见名知意”，一看就懂。
    ## 函数调用
    调用 Shell 函数时可以给它传递参数，也可以不传递。如果不传递参数，直接给出函数名字即可：

    name

    如果传递参数，那么多个参数之间以空格分隔：

    name param1 param2 param3

    不管是哪种形式，函数名字后面都不需要带括号。

    和其它编程语言不同的是，Shell 函数在定义时不能指明参数，但是在调用时却可以传递参数，并且给它传递什么参数它就接收什么参数。

    Shell 也不限制定义和调用的顺序，你可以将定义放在调用的前面，也可以反过来，将定义放在调用的后面。
    ## 实例演示
    1\) 定义一个函数，输出 Shell 教程的地址：
    ```text
    function url(){    echo "http://c.biancheng.net/shell/"}url
    ```
    运行结果： &#x20;

    [http://c.biancheng.net/shell/](http://c.biancheng.net/shell/ "http://c.biancheng.net/shell/")

    你可以将调用放在定义的前面，也就是写成下面的形式：
    ```text
    urlfunction url(){    echo "http://c.biancheng.net/shell/"}
    ```
    2\) 定义一个函数，计算所有参数的和：
    ```text
    function getsum(){    local sum=0    for n in $@    do         ((sum+=n))    done    return $sum}getsum 10 20 55 15  echo $?
    ```
    运行结果： &#x20;

    100

    `$@`表示函数的所有参数，`$?`表示函数的退出状态（返回值）。关于如何获取函数的参数，我们将在《[Shell函数参数](http://c.biancheng.net/view/2860.html "Shell函数参数")》一节中详细讲解。

    此处我们借助 return 关键字将所有数字的和返回，并使用`$?`得到这个值，这种处理方案在其它编程语言中没有任何问题，但是在 Shell 中是非常错误的，Shell 函数的返回值和其它编程语言大有不同，我们将在《[Shell函数返回值](http://c.biancheng.net/view/vip_3239.html "Shell函数返回值")》中展开讨论。
