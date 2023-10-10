# \[Shell]for|for int

<http://c.biancheng.net/view/2804.html>

```纯文本
for(( 初始化语句; 判断条件; 自增或自减 ))
do
    statements
done [Shell]for语法
```

for循环

```纯文本
第一种：
for  ((expr1;expr2;expr3))      # expr1：初始值条件  
                #expr2：循环的范围进行退出  
                #expr3：变量的值使用
{
​  循环体
}
for ((expr1;expr2;expr3));do            
​  循环体
done
第二种：
for  变量  in 列表; do
​  循环体
done

```



