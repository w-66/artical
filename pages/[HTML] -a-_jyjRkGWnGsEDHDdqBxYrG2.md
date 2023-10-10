# \[HTML] \<a>

<https://developer.mozilla.org/zh-CN/docs/Web/HTML/Element/a>

-   定义超链接，用它可以从一个页面链接到另一个页面`href`、`target`
-   锚点
-   maitto&#x20;

    示例5：邮箱链接

***

# 属性

**必选属性**

[\[HTML\]href](\[HTML]href_sTJsivDvW2btMpgzfHZdZH.md "\[HTML]href")：`href="URL"`

包含超链接指向的 URL 或 URL 片段

为空时相等于刷新：`<a href="">为空是刷新</a>`

> 可以使用 `href="#top"` 或者 `href="#"` 链接返回到页面顶部。



**可选属性**

[\[HTML\]target](\[HTML]target_jszELQu9F1uPSKNmGGMfqq.md "\[HTML]target")：\[`_blank `|`_parent`|`_self `|`_top`|[\[HTML\]name](\[HTML]name_vLe2jpz3e1FTZKGUfvhwsN.md "\[HTML]name")]

`_blank `

*新标签页*


`_parent`

`_self `

*默认属性*；本页面打开

`_top`

[\[HTML\]name](\[HTML]name_vLe2jpz3e1FTZKGUfvhwsN.md "\[HTML]name")

规定在何处打开链接文档。<链接跳转的模式>

-   详细
    | 属性                                                                                  | 值                                                                                                | 描述                                                                                                                                                                                                                                                                                                   |
    | ----------------------------------------------------------------------------------- | ------------------------------------------------------------------------------------------------ | ---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
    | [href](https://www.w3school.com.cn/tags/att_a_href.asp "href")                      | *URL*                                                                                            | 规定链接指向的页面的 URL。&#xA;&#xA;邮箱链接：`<a href="mailto:2961116754@qq.com">发送邮箱</a>`&#xA;电话链接：`<a href="tel:+491570156">+49 157 0156</a>`&#xA;ping： `<a href="`[https://qwertyui.vip](https://qwertyui.vip "https://qwertyui.vip")`" ping="https://qwertyui.vip">click me</a>`                                |
    | [target](https://www.w3school.com.cn/tags/att_a_target.asp "target")                | \_blank *新标签页*&#xA;\_parent&#xA;\_self *默认属性*&#xA;\_top&#xA;*framename*                          | 规定在何处打开链接文档。<链接跳转的模式>&#xA;示例：\<a target="\_blank" `href="`[https://www.wolai.com/wq1314/6vhxeND2UhzHBSMpAKpih1?theme=light](https://www.wolai.com/wq1314/6vhxeND2UhzHBSMpAKpih1?theme=light "https://www.wolai.com/wq1314/6vhxeND2UhzHBSMpAKpih1?theme=light")`">入网手册</a>`\</span>\</span>&#xA;&#xA; |
    | id                                                                                  | 必须以字母 A-Z 或 a-z 开头&#xA;其后的字符：字母(A-Za-z)、数字(0-9)、连字符("-")、下划线("\_")、冒号(":") 以及点号(".")&#xA;值对大小写敏感 | id 属性规定 HTML 元素的唯一的 id。&#xA;id 属性可用作链接锚（link anchor），通过 JavaScript（HTML DOM）或通过 CSS 为带有指定 id 的元素改变或添加样式。&#xA;&#xA;示例：锚点实例：跳转到当前页面的顶部`<a id>`、`<a href>`、`<p>`                                                                                                                                        |
    | [download](https://www.w3school.com.cn/tags/att_a_download.asp "download")`<HTML5>` | *filename*                                                                                       | 规定被下载的超链接目标。                                                                                                                                                                                                                                                                                         |
    | [hreflang](https://www.w3school.com.cn/tags/att_a_hreflang.asp "hreflang")          | *language\_code*                                                                                 | 规定被链接文档的语言。                                                                                                                                                                                                                                                                                          |
    | [media](https://www.w3school.com.cn/tags/att_a_media.asp "media")&#xA;`<HTML5>`     | *media\_query*                                                                                   | 规定被链接文档是为何种媒介/设备优化的。                                                                                                                                                                                                                                                                                 |
    | [type](https://www.w3school.com.cn/tags/att_a_type.asp "type")&#xA;`<HTML5>`        | *MIME type*                                                                                      | 规定被链接文档的的[ MIME 类型](<MIME 类型_9mMp4eqvLX8Q7uT9TPqvGt.md> " MIME 类型")。                                                                                                                                                                                                                                 |
    | [rel](https://www.w3school.com.cn/tags/att_a_rel.asp "rel")                         | *text*                                                                                           | 规定当前文档与被链接文档之间的关系。                                                                                                                                                                                                                                                                                   |
    | [rev](https://www.w3school.com.cn/tags/att_a_rev.asp "rev")                         | *text*                                                                                           | HTML5 中不支持。规定被链接文档与当前文档之间的关系。                                                                                                                                                                                                                                                                        |
    | [charset](https://www.w3school.com.cn/tags/att_a_charset.asp "charset")             | *char\_encoding*                                                                                 | HTML5 中不支持。规定被链接文档的字符集。                                                                                                                                                                                                                                                                              |
    | [coords](https://www.w3school.com.cn/tags/att_a_coords.asp "coords")                | *coordinates*                                                                                    | HTML5 中不支持。规定链接的坐标。                                                                                                                                                                                                                                                                                  |
    | [shape](https://www.w3school.com.cn/tags/att_a_shape.asp "shape")                   | default&#xA;rect&#xA;circle&#xA;poly                                                             | HTML5 中不支持。规定链接的形状。                                                                                                                                                                                                                                                                                  |
    | [name](https://www.w3school.com.cn/tags/att_a_name.asp "name")                      | *section\_name*                                                                                  | HTML5 中不支持。规定锚的名称。                                                                                                                                                                                                                                                                                   |
-   \[HTML]rel

    \[E]`Line 94:38:  Using target="_blank" without rel="noreferrer" (which implies rel="noopener") is a security risk in older browsers: see https://mathiasbynens.github.io/rel-noopener/#recommendations `

    `rel="noreferrer"`&#x20;

    `rel="noopener"`
    -   \[对比]

        `rel="noreferrer"` 和 `rel="noopener"` 是两个可以用于 `<a>` 标签的属性，用于解决在使用 `target="_blank"` 打开链接时的安全问题。它们的主要区别在于如何处理 `window.opener` 属性。
        -   `rel="noreferrer"`：使用这个属性时，浏览器会阻止新页面访问原始页面的信息，包括 `window.opener` 属性。这意味着新页面无法获取对原始页面的引用或访问其对象和方法。使用 `rel="noreferrer"` 可以提供更好的安全性，但可能会导致一些功能受限，比如无法在新页面中使用 `window.opener` 进行通信。
        -   `rel="noopener"`：这个属性的作用是在新页面中禁止访问打开它的页面，即原始页面。新页面不会继承任何来自原始页面的信息，并且无法通过 `window.opener` 访问原始页面。使用 `rel="noopener"` 也提供了一定的安全性，同时保留了一些与原始页面之间的通信功能。
        综上所述，如果你只关注安全性，并且不需要在新页面中使用 `window.opener` 进行通信，那么可以使用 `rel="noreferrer"`。如果你希望保留一些与原始页面之间的通信功能，并且不希望新页面能够访问原始页面的信息，那么可以使用 `rel="noopener"`。在某些情况下，也可以同时使用两者，即 `rel="noreferrer noopener"`。
    在旧的浏览器中，当链接使用 `target="_blank"` 打开一个新的窗口或标签页时，原始页面的窗口对象可以通过 `window.opener` 属性访问到新页面。这可能导致安全漏洞，使新页面可以访问原始页面的对象和方法，甚至可能进行恶意操作。

    为了解决这个安全问题，建议使用 `rel="noreferrer"` 或 `rel="noopener"` 属性中的至少一个来阻止新页面访问原始页面的对象。
    ```react&#x20;jsx
    <a href="https://example.com" target="_blank" rel="noreferrer">Link</a>

    ```

# 示例

-   示例1：`_blank `
    ```html
    <a target="_blank" href="https://www.wolai.com/wq1314/6vhxeND2UhzHBSMpAKpih1?theme=light">入网手册</a>
    ```
-   实例：跳转到其他页面&#x20;
    -   page2
        ```纯文本
        <p id=" page2_anchor1 ">page1到转至此，锚点设置</p>
        ```
    -   page1
        ```纯文本
        <p><a href=" page2.html#page2_anchor1 ">进入page2的锚点&lt;1page2_anchor1&gt;</a></p> 
        ```
-   锚点实例：跳转到当前页面的顶部`<a id>`、`<a href>`、`<p>`
    -   示例1：回到顶部

        ![](../image/image_WcQtRBoDTx.png)
        ```纯文本
        <a id="tu1" href="test_My.html"><img src="images/1.jpg" alt="头图" height="400"></a>
        ...
        <p><a href="#tu1">回到顶部</a></p>
        ```
    -   示例2：点击链接回到指定标题

        ![](../image/image_GTFSPYEyvZ.png)

        ![](../image/image_ImcJU4iMrE.png)
        ## [属性](https://developer.mozilla.org/zh-CN/docs/Web/HTML/Element/code#属性 "属性")
-   示例5：邮箱链接

    ![](../image/image_yUYBV6wj1e.png)
    ```html
    <a href="mailto:99@qq.com">发送邮箱</a>
    ```
    发送并抄送邮箱：
    ```纯文本
    <a href="mailto:66@qq.com?cc=99@qq.com">发送邮箱</a> 
    ```
    发送邮件并抄送邮件并密送，并加邮箱主题

    ![](../image/image_G3ySQr-HYr.png)


-   示例2：电话链接：`<a href="tel:+491570156">+49 157 0156</a>`
-   示例3：ping： `<a href="`[https://qwertyui.vip](https://qwertyui.vip "https://qwertyui.vip")`" ping="https://qwertyui.vip">click me</a>`
-   示例4访问本地路径
    -   (绝对路径)加协议只能是绝对路径

        ![](../image/image_IAChAPPW0M.png)
    -   (相对路径)

        ![](../image/image_yj99SIyYtd.png)
-   示例5

    ![](../image/image_t7ODAEx4CG.png)



