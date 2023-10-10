# \[win]attrib

设置文件属性：[\[win\]attrib](\[win]attrib_eBAHQJZnqvACbqPAYc1i4i.md "\[win]attrib")

命令全称：[attribute](attribute_idsnk6wkJeVdNsdCfga8Mi.md "attribute")

***

```纯文本
显示或更改文件属性。

ATTRIB [+R | -R] [+A | -A] [+S | -S] [+H | -H] [+O | -O] [+I | -I] [+X | -X] [+P | -P] [+U | -U]
       [drive:][path][filename] [/S [/D]] [/L]

  +   设置属性。
  -   清除属性。
  R   只读文件属性。
  A   存档文件属性。
  S   系统文件属性。
  H   隐藏文件属性。
  O   脱机属性。
  I   无内容索引文件属性。
  X   无清理文件属性。
  V   完整性属性。
  P   固定属性。
  U   非固定属性。
  [drive:][path][filename]
      指定属性要处理的文件。
  /S  处理当前文件夹及其所有子文件夹中的匹配文件。
  /D  也处理文件夹。
  /L  处理符号链接和
      符号链接目标的属性
```

# 示例

1。查看文件的文件属性 &#x20;


格式：ATTRIB \[drive:]\[path]\[filename]

例1, &#x20;
attrib d:\ pagefile.sys &#x20;
查看d:\ pagefile.sys文件的属性。

2。修改文件的属性。 &#x20;


格式:attrib ?属性

例1， &#x20;
attrib –h d:\ pagefile.sys &#x20;
消除d:\ pagefile.sys的“隐藏”属性。

例2, &#x20;
attrib +s h d:\ pagefile.sys &#x20;
给d:\ pagefile.sys设置“系统”和“隐藏”属性。

3。批量文件处理

例1, &#x20;


attrib h d:\123\\\*.bat /s &#x20;
通过/s参数可批量将d:\123及其子目录下的所有bat文件设置为“隐藏”属性.

例2, &#x20;


attrib h d:\123 /s /d &#x20;
将d:\123及其下所有同名为123的子目录设置为“隐藏”属性.参数/d必须在批量设置文件属性的同时，对指定目录及 &#x20;
其下所有子目录进行文件属性操作。参数/d可以理解为“directory”(目录),也就是说/d 必需和/s一起使用。

思考：

`attrib h d:\123 /s /d`和`attrib h d:\123\*.* /s /d`有什么区别呢？ &#x20;


前者只有d:\123以及它同名的子目录设为了“隐藏”，而其它文件及子目录都没有设置“隐藏”。 &#x20;


后者则将d:\123下的所有文件及子目录设置了“隐藏”属性，但d:\123目录没有设置“隐藏”属性。
