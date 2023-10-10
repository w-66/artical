# \[win]md

创建文件夹

```纯文本
MKDIR [drive:]path
MD [drive:]path

如果命令扩展被启用，MKDIR 会如下改变:

如果需要，MKDIR 会在路径中创建中级目录。例如: 假设 \a 不
存在，那么:

    mkdir \a\b\c\d

与:

    mkdir \a
    chdir \a
    mkdir b
    chdir b
    mkdir c
    chdir c
    mkdir d

相同。如果扩展被停用，则需要键入 mkdir \a\b\c\d。
```

# 示例

## 示例

1.创建单个文件夹 &#x20;
格式：MD \[路径\\]目录

例1 &#x20;
md d:\abc &#x20;
在D盘下建立一个名为abc的文件夹。

例2 &#x20;
md abc &#x20;
这里为缺省路径，则在当前目录下创建一个名为abc的文件夹。

例3 &#x20;
md "d:\my game" &#x20;
在D盘下建立一个名为my game的文件夹。 &#x20;
对于新建的文件夹名称中包含有空格或是特殊符号的，一定要用双引号” “把文件夹名括起来。

例4 &#x20;
md "C:\Documents and Settings\456^ 789" &#x20;
在C:\Documents and Settings下建立一个名为456^ 789的文件夹，由于路径中有空格，所以我们用双引号" "把路径 &#x20;
和文件夹名一起括起来了。



2.同时创建多个目录 &#x20;
格式:md \[路径\\]目录1 \[路径\\]目录2 \[路径\\]目录3……

例5 &#x20;
md abc D:\gmae\123 abcd &#x20;
在当前目录下建立abc和abcd两个文件,同时D:\gmae下也建立一个文件夹123。



3.创建多级目录 &#x20;
格式:md \[路径\\]目录1\目录2\目录3\…

假如我们要在D盘下建立文件夹abc,然后在abc中建新文件夹abcd,接着再在abcd中建文件夹abcde,有没有一个命令可以 &#x20;
一次性搞定的呢？答案肯定的！

例6 &#x20;
md d:\abc\abcd\abcde &#x20;
就这么一个命令就搞定了，不信？你当然可以测试一下罗，呵呵\~

思考：

在例4中如果命令不用双引号括起来，即md C:\Documents and Settings\456^ 789  这样会发生什么情况呢？这个 &#x20;
就让大家动手去测试一下了，哈哈！！
