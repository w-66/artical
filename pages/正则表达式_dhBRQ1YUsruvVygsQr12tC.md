# 正则表达式

学习途径

<https://regexlearn.com/zh-cn?utm_source=appinn.com>

<https://regex101.com/>

<https://deerchao.cn/tutorials/regex/regex.htm>

<https://chinese.freecodecamp.org/learn/javascript-algorithms-and-data-structures/regular-expressions/>

<https://jex.im/regulex/#!flags=&re=^(a|b)*%3F%24>

<https://any86.github.io/any-rule/>

[正则 符号\[reg.\]](<正则 符号\[reg.]_bUBxxrx8vz57vaLdMYwgYN.md> "正则 符号\[reg.]")

***

# 正则常用符号

`^` 匹配输入字符串的开始位置。如果设置了 RegExp 对象的 Multiline 属性，^ 也匹配 '\n' 或 '\r' 之后的位置

`\b` 匹配一个单词边界，也就是指单词和空格间的位置。例如， 'er\b' 可以匹配"never" 中的 'er'，但不能匹配 "verb" 中的 'er'

`\n` 匹配一个换行符。等价于 \x0a 和 \cJ。



***

[正则表达式示例](正则表达式示例_gTxervFPUKgYwUJ3ggqaxM.md "正则表达式示例")



-   待看

    ![](../image/image_p37_rYlCWv.png)



[\[Q\]正则](\[Q]正则_2HmZjxsbxsvDg5fWHEs8fv.md "\[Q]正则")

-   [正则表达式(括号)、\[中括号\]、{大括号}的区别](https://www.cnblogs.com/hjbky/p/9512022.html "正则表达式(括号)、\[中括号]、{大括号}的区别")

    正则表达式的() \[] {}有不同的意思。

    () 是为了提取匹配的字符串。表达式中有几个()就有几个相应的匹配字符串。

    (\s\*)表示连续空格的字符串。

    \[]是定义匹配的字符范围。比如 \[a-zA-Z0-9] 表示相应位置的字符要匹配英文字符和数字。\[\s\*]表示空格或者*号。
    *
    *{}一般用来表示匹配的长度，比如 \s{3} 表示匹配三个空格，\s{1,3}表示匹配一到三个空格。
    *
    *(0-9) 匹配 '0-9′ 本身。 \[0-9]* 匹配数字（注意后面有 \*，可以为空）\[0-9]+ 匹配数字（注意后面有 +，不可以为空）{1-9} 写法错误。

    \[0-9]{0,9} 表示长度为 0 到 9 的数字字符串。



# 碎片

[匹配空格](匹配空格_vGSHEmnpHUDe1QqUi5WjNx.md "匹配空格")
