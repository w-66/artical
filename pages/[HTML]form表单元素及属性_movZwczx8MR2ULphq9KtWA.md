# \[HTML]form表单元素及属性

<https://developer.mozilla.org/zh-CN/docs/Web/HTML/Element/form>

HTML \<form> 元素表示文档中的一个区域，此区域包含交互控件，用于向 Web 服务器提交信息。

## 属性

1.  `action`表单信息提交地址，信息提交成功会跳转去该地址
2.  `method`提交方式
    -   get (默认）
    -   post
3.  `target`信息提交成功打开页面的方式

    `_blank`

    `_self`

> 想要了解这个差别需要学习JS的前后端数据交互的内容，除了通过form，在JS中我们还可以通过其他方式对表单数据进行提交。

input表单元素 `<input type="" value="" />`

\- 单标签

\- 用于收集用户信息，根据不同的type值，可以让input表单元素具备不一样的功能

type类型

1.  text单行文本输入框 `input type="text" value="单行文本内的默认文字"/>`

    另：`placeholder `属性提供可描述输入字段预期的提示信息，该提示会在输入字段为空时显示，并会在字段获得焦点时消失。
2.  submit提交 `<input type="submit" value="提交按钮上的文字设置"`

***

## 示例

![](../image/image_NPy5MF9dHD.png)

![](../image/image_jzmoRAnc9d.png)

![action：提交到对应的js，以及定义提交类型：post或者get](../image/Snipaste_2021-10-21_15-02-23_ZaIGm_tZW3.png "action：提交到对应的js，以及定义提交类型：post或者get")



![](../image/image_40bwiRhY8S.png)

