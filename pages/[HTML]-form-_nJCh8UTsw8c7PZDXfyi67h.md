# \[HTML]\<form>

内部可包含[\[HTML\]\<input/>](\[HTML]-input--_EKoUZbzZBwJoGKiBhYRL1.md "\[HTML]<input/>")、[\[\[HTML\]\<textarea>](\[\[HTML]-textarea-_dnuxxSuPSH7SLCkykdBwJ7.md "\[\[HTML]<textarea>")、[\[HTML\]\<select>](\[HTML]-select-_sZ8xaPhPcU7kTRTvvQ6F2e.md "\[HTML]<select>")、[\[HTML\]\<fieldset>](\[HTML]-fieldset-_nkLNTjW6ge9QDYC4x8Ea9N.md "\[HTML]<fieldset>")，为用户定义需要使用的表单项

# 属性

#### 必选属性

[\[HTML\]action](\[HTML]action_mc7GK3s2qUjwG6wDNu41gK.md "\[HTML]action")**：传输信息；为空表示传输到本页**；输入数据将被传输到的地方，例：php页面

[\[HTML\]method](\[HTML]method_3p4FMe5EQKGoxJkKri56Kv.md "\[HTML]method")**：数据传输的方式；\[****`get`****|****`post`****]所有跟用户相关的都使用****`post`****方式**

`get`会显示到地址栏中；明文传输速度快；最多支持65535字节

`post`加密传输，更安全，不会显示到地址栏中，传输信息量大

#### 可选属性

**\[HTML]****`id`**：使用**表单分离技术**([HTML5](HTML5_hCmUUjZGPX9YJ9Qe4DK6tj.md "HTML5")新增)，关联form之外的`input`表单

[\[HTML\]novalidate](\[HTML]novalidate_t88B7HX9DZVu5s2ZfHG5C8.md "\[HTML]novalidate")：可使整个表单失去浏览器自带的**验证**效果

\[HTML]onsubmit当表单提交时触发该事件，通常用于处理表单的提交行为

# 示例

-   示例1：创建表单[\[HTML\]\<form>](\[HTML]-form-_nJCh8UTsw8c7PZDXfyi67h.md "\[HTML]<form>")、[\[HTML\]\<input/>](\[HTML]-input--_EKoUZbzZBwJoGKiBhYRL1.md "\[HTML]<input/>")

    ![](../image/image_kqvW7FRgYa.png)

    ![](../image/image_UDXZKl6699.png)

