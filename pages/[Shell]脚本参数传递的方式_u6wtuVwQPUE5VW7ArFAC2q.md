# \[Shell]脚本参数传递的方式

\[关键字] shell；脚本选项参数；传递参数；

***

<https://www.jianshu.com/p/6393259f0a13>



***



1.  `$n` 直接处理

    `$n(n≥1)`

    传递给脚本或函数的参数

    n 是一个数字，表示第几个参数。例如，第一个参数是 \$1，第二个参数是 \$2。

    如果参数个数太多，达到或者超过了 10 个，那么就得用`${n}`的形式来接收了，例如 ${10}、${23}。`{ }`的作用是为了帮助解释器识别参数的边界，这跟使用变量时加`{ }`是一样的效果。
2.  [\[Shell\]getopts](\[Shell]getopts_kRAUYjSmj5pY71pd756gL4.md "\[Shell]getopts")

    getpots是Shell命令行参数解析工具，旨在从Shell Script的命令行当中解析参数。
3.  [\[Shell\]getopt](\[Shell]getopt_j7rVYWd5Tp6b35jmQCtzAE.md "\[Shell]getopt")





小脚本直接处理即可，getopts能处理绝大多数的情况，getopt较复杂、功能也更强大。
