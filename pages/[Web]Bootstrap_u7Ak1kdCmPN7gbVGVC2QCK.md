# \[Web]Bootstrap

bootstrap的所有组件都是依赖[\[Web\]jquery](\[Web]jquery_dhtvXFZ9amdPiDEiXxq2sK.md "\[Web]jquery")

***

官方页面：

所有版本：[https://www.getbootstrap.cn/docs/versions/](https://www.getbootstrap.cn/docs/versions/ "https://www.getbootstrap.cn/docs/versions/")

[https://getbootstrap.com/](https://getbootstrap.com/ "https://getbootstrap.com/")

&#x20;[https://v5.bootcss.com/docs/getting-started/introduction/](https://v5.bootcss.com/docs/getting-started/introduction/ "https://v5.bootcss.com/docs/getting-started/introduction/")

官方指导(En)：[https://getbootstrap.com/docs/5.2/getting-started/introduction/](https://getbootstrap.com/docs/5.2/getting-started/introduction/ "https://getbootstrap.com/docs/5.2/getting-started/introduction/")

官方指导(Ch)：[https://getbootstrap.net/docs/getting-started/introduction/](https://getbootstrap.net/docs/getting-started/introduction/ "https://getbootstrap.net/docs/getting-started/introduction/")

中文文档：[https://www.bootstrap.cn/doc/book/2.html](https://www.bootstrap.cn/doc/book/2.html "https://www.bootstrap.cn/doc/book/2.html")

***

Bootstrap 是一个用于快速开发 Web 应用程序和网站的前端框架。Bootstrap 是基于 HTML、CSS、JAVASCRIPT 的。

1.  Bootstrap 是 Twitter 所设计的一个 UI 库，以 css 样式为主，也提供了一些组件的功能需要配合 js 来进行使用 &#x20;
2.  使用简单，文档清晰，学习成本低 &#x20;
3.  提供的组件相对较少 &#x20;
4.  可以只使用框架中的 css 样式，可嵌入性较高 &#x20;
5.  UI 的风格符合目前大众的普遍审美 &#x20;
6.  适合使用在对游览器兼容性有要求的项目中

***

## Bootstrap插件

[Bootstrap-datepicker](Bootstrap-datepicker_aMuJ9MVcAfTbvMyLXJQQMP.md "Bootstrap-datepicker"),[flatpickr](flatpickr_rroE3Fski5qhbXeLe317st.md "flatpickr")时间选择插件

[Bootstrap-datepicker](Bootstrap-datepicker_aMuJ9MVcAfTbvMyLXJQQMP.md "Bootstrap-datepicker")

[popper插件](popper插件_aJT4noiQ5wDbDvsJaPta4o.md "popper插件")下拉菜单(定位菜单)



开始使用Bootstrap包,[Bootstrap布局](Bootstrap布局_5BneyEXRzEVza99jTRKSsc.md "Bootstrap布局"),[Bootstrap页面内容](Bootstrap页面内容_kjm8vgpMvoyo9r5WfLZtjv.md "Bootstrap页面内容")

***

## Bootstrap包中的文件

1.  CSS

    bootstrap.min.css

<!---->

1.  JS

    bootstrap.min.js

    bootstrap.bundle.js

    包含了[popper插件](popper插件_aJT4noiQ5wDbDvsJaPta4o.md "popper插件")



## 开始使用Bootstrap包

> JS引入要放在body底部

-   方式1：下载CSS和JS文件，将其引入[¶](https://getbootstrap.com/docs/5.2/getting-started/download/#compiled-css-and-js "¶") \[bootstrap.min.css,bootstrap.min.js]
    ```html
    <!DOCTYPE html>
    <html lang="en">
    <head>
        <meta charset="UTF-8">
        <meta http-equiv="X-UA-Compatible" content="IE=edge">
        <meta name="viewport" content="width=device-width, initial-scale=1.0">
        <link rel="icon" href="/static/img/favicon.ico">
        <!-- 每秒 自动刷新 -->
        <!-- <meta http-equiv="refresh" content="2">   -->
         <link rel="styelsheet" href="/static/bootstrap/css/bootstrap.min.css"> 
        <title>Learn Bootstrap 01</title>
    </head>
    <body>
        <h2>Learn Bootstrap 01</h2>
         <script src="/static/bootstrap/js/bootstrap.bundle.min.js"></script> 
    </body>
    </html>
    ```
-   方式2：直接引入 ，CDN [¶](https://getbootstrap.com/docs/5.2/getting-started/download/#cdn-via-jsdelivr "¶")
    ```html
    <link href="https://cdn.jsdelivr.net/npm/bootstrap@5.2.3/dist/css/bootstrap.min.css" rel="stylesheet" integrity="sha384-rbsA2VBKQhggwzxH7pPCaAqO46MgnOM80zW1RWuH61DGLwZJEdK2Kadq2F9CUG65" crossorigin="anonymous">
    <script src="https://cdn.jsdelivr.net/npm/bootstrap@5.2.3/dist/js/bootstrap.bundle.min.js" integrity="sha384-kenU1KFdBIe4zVF0s0G1M5b4hcpxyD9F7jL+jjXkk+Q2h455rYXK/7HAuoJl+0I4" crossorigin="anonymous"></script>

    ```

***

-   示例：验证吗输入单元; 验证码图片基于父标签上下居中 \[`.d-flex``.justify-content-center``.align-items-center`,`.img-fluid`]
    ```python
    <div class="container p-0">
      <div class="row">
        <div class="col-7">
          <div class="form-floating">
            <input type="text" class="form-control" id="auth_code" placeholder="auth code">
            <label for="floatingPassword">auth code</label>
          </div>
        </div>
        <div class="col-5 d-flex justify-content-center align-items-center">
          <img class="img-fluid" src="/auth/code/" alt="">
        </div>
      </div>
    </div>

    ```



***



## Grid options[¶](https://v5.bootcss.com/docs/5.3/layout/grid/#grid-options "¶")

Bootstrap包含的响应式屏幕尺寸大小：sm(<576)md(<768)lg(<992)xl(<1200)xxl(<1400)

xs(<576)

-   Extra small (xs)

sm(<576)

-   Small (sm)

md(<768)

-   Medium (md)

lg(<992)

-   Large (lg)

xl(<1200)

-   Extra large (xl)

xxl(<1400)

-   Extra extra large (xxl)



|                       | xs  <576px                                                          | sm  576px  | md  768px  | lg  ≥992px | xl  ≥1200px | xxl  ≥1400px |
| --------------------- | ------------------------------------------------------------------- | ---------- | ---------- | ---------- | ----------- | ------------ |
| Container `max-width` | None (auto)                                                         | 540px      | 720px      | 960px      | 1140px      | 1320px       |
| Class prefix          | `.col-`                                                             | `.col-sm-` | `.col-md-` | `.col-lg-` | `.col-xl-`  | `.col-xxl-`  |
| # of columns          | 12                                                                  |            |            |            |             |              |
| Gutter width          | 1.5rem (.75rem on left and right)                                   |            |            |            |             |              |
| Custom gutters        | [Yes](https://v5.bootcss.com/docs/layout/gutters/ "Yes")            |            |            |            |             |              |
| Nestable              | [Yes](https://v5.bootcss.com/docs/5.3/layout/grid/#nesting "Yes")   |            |            |            |             |              |
| Column ordering       | [Yes](https://v5.bootcss.com/docs/layout/columns/#reordering "Yes") |            |            |            |             |              |



***

[Bootstrap盒模型](Bootstrap盒模型_4f4PzGF2AHZF7tGdxJ19it.md "Bootstrap盒模型")

[Bootstrap布局](Bootstrap布局_5BneyEXRzEVza99jTRKSsc.md "Bootstrap布局")

[Bootstrap宽高](Bootstrap宽高_x96PTgnGbe1McJ5QPr2Zdj.md "Bootstrap宽高")

[Bootstrap组件](Bootstrap组件_9BdqjLg44EkMD8D4x3oiPp.md "Bootstrap组件")

[Bootstrap位置](Bootstrap位置_uKTVioWwr5Sfmbx5Vqruic.md "Bootstrap位置")

[Bootstrap圆角](Bootstrap圆角_aMbHBckxL5wCA46iTVqZsE.md "Bootstrap圆角")

[Bootstrap表单](Bootstrap表单_odEqcPW7EXeTauB8H9Myja.md "Bootstrap表单")

[Bootstrap图片](Bootstrap图片_4ofPmz3P4WoBgiXgC2as2b.md "Bootstrap图片")

[Bootstrap文本](Bootstrap文本_uXfB1eVffM3LkL7fX5AhpN.md "Bootstrap文本")

[Bootstrap列表组](Bootstrap列表组_4xKyYeyHqsJEQYeTY4TwF.md "Bootstrap列表组")

[Bootstrap Display](<Bootstrap Display_jSthvSws3Uj1XufSYypzrR.md> "Bootstrap Display")

[Bootstrap颜色](Bootstrap颜色_6MwJbg8kAFxym92GvUqHJc.md "Bootstrap颜色")

[Bootstrap页面内容](Bootstrap页面内容_kjm8vgpMvoyo9r5WfLZtjv.md "Bootstrap页面内容")

[Bootstrap面包屑](Bootstrap面包屑_6YujzCcpMEBYRhX1QbTfbj.md "Bootstrap面包屑")

[弹性盒子](弹性盒子_8f6NANACX8h3MN1Ro2p51z.md "弹性盒子")

[Bootstrap间距](Bootstrap间距_hZLqjoyLYGZsWJxQLNseoK.md "Bootstrap间距")

[ Bootstrap SCSS](<Bootstrap SCSS_hFa2zhc26nkfguo59pSMox.md> " Bootstrap SCSS")

***

[Bootstrap示例](Bootstrap示例_vx4t8uNKPpzUwHAgJte1Ec.md "Bootstrap示例")

### Bootstrap 自带的class



1.  `.container`[¶](https://v5.bootcss.com/docs/5.3/layout/containers/#how-they-work "¶")类用于创建固定宽度的响应式页面; which sets a `max-width` at each responsive breakpoint
2.  `.container-fluid`which is width: 100% at all breakpoints; 浮动，不居中



当`.container`容器大于或等于992且小于1400时，它的宽度是936+ padding12\*2 = 960

|                    | Extra small&#xA;<576px | Small&#xA;≥576px | Medium&#xA;≥768px | Large&#xA;≥992px | X-Large&#xA;≥1200px | XX-Large&#xA;≥1400px |
| ------------------ | ---------------------- | ---------------- | ----------------- | ---------------- | ------------------- | -------------------- |
| `.container`       | 100%                   | 540px            | 720px             | 960px            | 1140px              | 1320px               |
| `.container-sm`    | 100%                   | 540px            | 720px             | 960px            | 1140px              | 1320px               |
| `.container-md`    | 100%                   | 100%             | 720px             | 960px            | 1140px              | 1320px               |
| `.container-lg`    | 100%                   | 100%             | 100%              | 960px            | 1140px              | 1320px               |
| `.container-xl`    | 100%                   | 100%             | 100%              | 100%             | 1140px              | 1320px               |
| `.container-xxl`   | 100%                   | 100%             | 100%              | 100%             | 100%                | 1320px               |
| `.container-fluid` | 100%                   | 100%             | 100%              | 100%             | 100%                | 100%                 |



***

1.  `.row`行

***

1.  `.col-`针对所有设备
2.  `.col-sm-`
3.  `.col-md-`
4.  `.col-lg-`
5.  `.col-xl-`
6.  `.col-xxl-`

***

-   `.offset-*-*`列偏移设置，第一个星号可以设置sm,md,lg,xl，第二个星号为偏移量

***

-   `.order-*`列排序，星号为`first`>`[1-5]`>`last`，小优先

***













`.display-*`星号为`[1-4]`，显示更大

***

`.lead`段落显示突出

`.small`元素显示父元素的80%大小，效果同[\[HTML\]\<small>](\[HTML]-small-_pqEYQBumTAR2f5cfb6nGgf.md "\[HTML]<small>")

***

1.  `.text-start`居左
2.  `.text-center`居中
3.  `.text-end`居右
4.  `.text-*-center`星号表示sm,md,lg,xl，根据屏幕大小响应式对象文本

    `.text-md-center`屏幕宽度大于或等于768px时，居中对齐
5.  `.text-lowercase`转换成小写
6.  `.text-uppercase`转换成大写
7.  `.text-capitalize`每个单词的首字母大写
8.  `.text-truncate`超出屏幕宽度的文本以`...`省略|代替
9.  `.text-wrap`超出盒子自动换行
10. `.text-nowrap`阻止文本换行，超出则溢出盒子
11. `.fs-*`星号为\[1-6]，设置文本大小

***











***

1.  `.fst-italic`设置斜体
2.  `.fst-normal`取消斜体











***

`.text-reset`重置文本或链接的颜色，以便它从其父级继承颜色

***

`.bg-*`背景颜色























***

1.  `.list-unstyled`去除列表符号
2.  `.list-inline`改成水平列表
3.  `.list-inline-item`水平列表中的条目`<li>`
4.  `.list-group`创建列表组
5.  `.list-group-item`创建列表组项目
6.  `.active`列表项目元素为活动
7.  `.disable`列表项目元素为禁用
8.  `.list-group-item-action`鼠标悬停显示灰色背景
9.  `.list-group-flush`添加到`.list-group`元素上，移除外边框与圆角
10. `.list-group-horizontal`添加到`.list-group`元素上，将列表水平显示(并排不堆叠)
11. `.list-group-numbered`添加到`.list-group`元素上，列表显示列表序号(通过CSS显示的数字)
12. `.badge`在`.list-group-item`元素中(包含)，添加徽章

列表项目背景颜色[¶](https://www.bootstrap.cn/doc/read/143.html#contextual-classes "¶")

1.  `.list-group-item-access`列表项目背景颜色













`.badge`徽章[¶](https://www.bootstrap.cn/doc/read/134.html#background-colors "¶")(默认背景颜色`.bg-light`)





1.  `.container`
2.  `.container-fluid`
3.  `.container-sm`
4.  `.container-md`
5.  `.container-lg`
6.  `.container-xl`

***

-   `.row`

***

1.  `.col-`
2.  `.col-sm-`
3.  `.col-md-`
4.  `.col-lg-`
5.  `.col-xl-`
6.  `.col-xxl-`

***

-   `.offset-*-*`

***

-   `.order-*`

***

-   `.h1`
-   `.h2`
-   `.h3`
-   `.h4`
-   `.h5`
-   `.h6`
-   `.display-*`

***

-   `.lead`
-   `.small`

***

1.  `.text-start`
2.  `.text-center`
3.  `.text-end`
4.  `.text-*-center`
    -   `.text-md-center`
5.  `.text-lowercase`
6.  `.text-uppercase`
7.  `.text-capitalize`
8.  `.text-truncate`
9.  `.text-wrap`
10. `.text-nowrap`
11. `.fs-*`

***

-   `.fw-bolder(bolder)`
-   `.fw-bold(700)`
-   `.fw-normal(400)`
-   `.fw-light(300)`
-   `.fw-lighter(lighter)`

***

1.  `.fst-italic`
2.  `.fst-normal`



-   `.lh-1(1rem)`
-   `.lh-sm(1.25rem)`
-   `.lh-base(1.5rem)`
-   `.lh-lg(2rem)`

***

1.  `.text-reset`

***



***

-   `.bg-*`

1.  `.bg-primary`
2.  `.bg-secondary`
3.  `.bg-success`
4.  `.bg-danger`
5.  `.bg-warning`
6.  `.bg-info`
7.  `.bg-light`
8.  `.bg-dark`
9.  `.bg-white`
10. `.bg-transparent`

***

1.  `.list-unstyled`
2.  `.list-inline`
3.  `.list-inline-item`
4.  `.list-group`
5.  `.list-group-item`
6.  `.active`
7.  `.disable`
8.  `.list-group-item-action`
9.  `.list-group-flush`
10. `.list-group-horizontal`
11. `.list-group-numbered`



1.  `.list-group-item-access`
2.  `.list-group-item-primary`
3.  `list-group-item-danger`
4.  `list-group-item-warning`
5.  `list-group-item-info`
6.  `list-group-item-light`
7.  `list-group-item-dark`



1.  `.badge`
2.  `.bg-light`

***

1.  `.table`Bootstrap表格

<!---->

1.  `.table`

***

#### [Bootstrap面包屑](Bootstrap面包屑_6YujzCcpMEBYRhX1QbTfbj.md "Bootstrap面包屑")

`breadcrumb`面包屑外层元素

`breadcrumb-item`面包屑内层项目



`breadcrumb`

`breadcrumb-item`





####



#### [Bootstrap宽高](Bootstrap宽高_x96PTgnGbe1McJ5QPr2Zdj.md "Bootstrap宽高")

















***

## 详解

-   详解`.container`
    1.  `.container`[¶](https://v5.bootcss.com/docs/5.3/layout/containers/#how-they-work "¶")类用于创建固定宽度的响应式页面; which sets a `max-width` at each responsive breakpoint
    ![](../image/image_F_6enOfwfl.png)
-   详解`.container-sm``.container-md``.container-lg``.container-xl`&#x20;

    ![](../image/image_MlDMXfGgMR.png)
-   详解`.col-``.col-sm-``.col-md-``.col-lg-``.col-xl-``.col-xxl-`
    -   \[笔记]

        ![](../image/image_LkRovhoRcH.png)

        ![](../image/image_b2CxHzpNX8.png)

        ![](../image/image_4M3PfDeyz5.png)



***

-   \[对比]`.container`|`.container-fluid`


    -   示例：\[`.container`,`.container-fluid`]
        -   HTML code&#x20;
            ```html
                <!DOCTYPE html>
                <html lang="en">
                <head>
                    <meta charset="UTF-8">
                    <link rel="icon" href="/static/img/favicon.ico">
                    <!-- 每秒 自动刷新 -->
                    <!-- <meta http-equiv="refresh" content="2">   -->
                    <link rel="stylesheet" href="/static/bootstrap/css/bootstrap.min.css">
                    <title>Learn Bootstrap 01</title>
                </head>
                <body>
                    <h2>Learn Bootstrap 01</h2>
                    
                    <div class="container">这是container类</div>
                    <div class="container-fluid">这是container-fluid类</div>
                    <script src="/static/bootstrap/js/bootstrap.bundle.min.js"></script>
                </body>
                </html>
            ```
        ![](../image/2022-22-11-1848_7PPFfM48pj.gif)
    ![](../image/image_fBv8nE-OKn.png)

***



## 示例



## 碎片

`d-grid`

将元素的显示方式设置为网格布局。

`gap-[1-6]`

元素之间的间隔

-   示例：`d-grid``gap-[1-6]`

    ![](../image/image_1FjndZreF2.png)
    ```react&#x20;jsx
          <div className="row ">
            <div className='d-flex flex-row bd-highlight mb-3'>
              <select class="form-select" aria-label="Default select">
                  <option selected>选择</option>
                  <option value="1">1</option>
                  <option value="2">2</option>
                  <option value="3">3</option>
              </select>
              <div className="d-grid gap-2">
                <button type="button" name="" id="" className="btn btn-primary">Button</button>
                <button type="button" name="" id="" className="btn btn-primary">Button</button>
                <button type="button" name="" id="" className="btn btn-primary">Button</button>
              </div>
            </div>
          </div>
    ```

`nav`

`nav`导航基类

[\[E\&Q\]Bootstrap](\[E\&Q]Bootstrap_hgwhF7tNbz6kwt2FMSte21.md "\[E\&Q]Bootstrap")
