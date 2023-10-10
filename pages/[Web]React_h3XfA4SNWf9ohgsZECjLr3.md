# \[Web]React

参考教程：入门：[https://zh-hans.reactjs.org/tutorial/tutorial.html#overview](https://zh-hans.reactjs.org/tutorial/tutorial.html#overview "https://zh-hans.reactjs.org/tutorial/tutorial.html#overview")

-   React V16
-   React V17
-   [React V18](<React V18_64UAsrzANTizHt5B9zgsU3.md> "React V18")

***

-   前置概念或技术
    -   [\[Web\]DOM](\[Web]DOM_hA1J7qvXNRdJxg7CoGu7X.md "\[Web]DOM")

[\[React\]开源项目](\[React]开源项目_apqz1VeWLAsP1nxTeR4BeH.md "\[React]开源项目")

***

### React 是什么？

React 是一个声明式，高效且灵活的用于构建用户界面的 [JavaScript](JavaScript_w7M7UmgSNLmfSHDWMLjuEi.md "JavaScript")库。使用 React 可以将一些简短、独立的代码片段组合成复杂的 UI 界面，这些代码片段被称作“组件(Component )”。

1.  React框架采用的是[MVC](MVC_6Grg764tEBKQ4c24UR9uM6.md "MVC")体系；Vue框架采用的是[MVVM](MVVM_qUkvMWRoX5WbrFezDf1Nmi.md "MVVM")体系； MVC: model数据层 ，view视图层 controller控制层;  MVVM: model数据层 view视图层 viewModel数据/视图监听层。[🖼️ 图片](../image/image_1hFaVDo9i-.png "🖼️ 图片")
2.  项目中的命名方式

[Ract语法符号](Ract语法符号_sW5YdeNE7XPs6LsQq96fsA.md "Ract语法符号")



## 概念

[\[React\]create-react-app(脚手架)](\[React]create-react-app\(脚手架\)_iKRevG9qrfgg38wTCrMLDx.md "\[React]create-react-app(脚手架)")

[\[React\]虚拟DOM](\[React]虚拟DOM_Snd6fanVfJeXQdXpbDqd8.md "\[React]虚拟DOM")

[\[React\]JSX](\[React]JSX_s6YqU4tzdiXR9faUSdiKqB.md "\[React]JSX")

[\[React\]Hooks](\[React]Hooks_cdoA4yVU3YpyLmGC6GsSfF.md "\[React]Hooks")

[\[React\]组件与属性](\[React]组件与属性_tc8jMTUd6Mm5ypAX4XU8bv.md "\[React]组件与属性")

[\[React\]组件优化](\[React]组件优化_g7r7iofq8ju6UQsmkXop5c.md "\[React]组件优化")

-   组件的通信方式

[\[React\]生命周期](\[React]生命周期_daGsiUspap6JwY68rVudND.md "\[React]生命周期")

[\[React\]Synthetic 合成事件](<\[React]Synthetic 合成事件_db71uLQJ5RVbif35zuNMME.md> "\[React]Synthetic 合成事件")

[React V18](<React V18_64UAsrzANTizHt5B9zgsU3.md> "React V18")

[\[React\]路由](\[React]路由_4SqHXtAt3fngpVE1s8JSet.md "\[React]路由")

[\[JS库\]redux](\[JS库]redux_wYUdBtUF4wPMD74fXKn7zd.md "\[JS库]redux")

-   [\[Web\]React](\[Web]React_h3XfA4SNWf9ohgsZECjLr3.md "\[Web]React")的JS插件库
-   **\[React]开发注意点**
    -   `import`导入sass样式时，使用模块化导入，实现对于同类名的不同模块实现互不影响
        -   示例：正常模块命名，与正常类命名
            ```python
            .header{
                color: red;
            }   
            ```
            ![](../image/image_-nAPDbYVg3.png)

            ![](../image/image_D13NUjH41o.png)
        -   示例：index或其他模块命名，与带`-`的类命名

            ![](../image/image_6G7aN99YIa.png)
            ```python
            .header-1{
                color: red;
                font-size: 3em;
            }   
            ```
            ```python
            import styles1 from  './i.module.scss' 
            //
            export default function Header() {
              return (
                <div className={styles1 ['header-1'] }>
                  Header
                </div>
              )
            }
            ```

***



-   [\[React\]虚拟DOM](\[React]虚拟DOM_Snd6fanVfJeXQdXpbDqd8.md "\[React]虚拟DOM")本质是Object(一般对象)，较"轻"
    -   \[笔记][虚拟DOM与真实DOM](https://www.bilibili.com/video/BV1wy4y1D7JT/?p=4 "虚拟DOM与真实DOM")

        ![](../image/image_ymkT7DQTSX.png)
-   [\[React\]JSX](\[React]JSX_s6YqU4tzdiXR9faUSdiKqB.md "\[React]JSX")全称JavaScript XML



#### 概念碎片

[\[React\]插槽机制](\[React]插槽机制_uuaHRdrQYxNTMe2KLps9ws.md "\[React]插槽机制")

-   babel
    -   [📄 prop-types.js](../file/prop-types_plHg6flfI6.js "📄 prop-types.js")
    -   babel默认开启严格模式 \[严格模式]
-   组件(Component )
    -   我们通过使用组件来告诉 React 我们希望在屏幕上看到什么。当数据发生改变时，React 会高效地更新并重新渲染我们的组件。
    -   **组件类**
-   方法
    -   `ReactDOM`
        -   `ReactDOM.render()`

            `ReactDOM.render()`方法，渲染到页面 \[[\[React\]虚拟DOM](\[React]虚拟DOM_Snd6fanVfJeXQdXpbDqd8.md "\[React]虚拟DOM")]
            -   &#x20;示例：`ReactDOM.render()`写法
                ```javascript
                        const p = {name:'tom',age:20,weight:'50kg'}
                        ReactDOM.render(<Person {...p}/>, document.getElementById('text'))

                        ReactDOM.render(<Person name='kaka' age={29} weight='50kg'/>, document.getElementById('text1'))
                        
                        const p2 = {name:'jojo', weight:'50kg'}
                        ReactDOM.render(<Person {...p2}/>, document.getElementById('text2'))
                ```
    -   `ReactDOM.unmountComponentAtNote()`
    -   react
        -   `React`
            -   `React.forwardRef()`
                -   `React.forwardRef()`实现ref的转发
            -   `React.createElement()`
                -   `React.createElement()`创建虚拟DOM对象 \[[\[React\]虚拟DOM](\[React]虚拟DOM_Snd6fanVfJeXQdXpbDqd8.md "\[React]虚拟DOM")]
            -   React.Children
                -   React.Children.count()
                    -   React.Children.count()计算子节点数量 \[标签体参数]
                -   React.Children.toArray()
                    -   React.Children.toArray()将标签体中的内容解析成数组
                -   React.Children.map()
                -   React.Children.forEach()
                -   React.Children.only()
            -   `React.createContext()`
                -   `Provider`
                    -   `Provider`祖组件(跨级组件)传给后代组件是类式组件时使用
                -   `Consumer`
                    -   `Consumer`祖组件(跨级组件)传给后代组件是函数式组件时使用
            -   `React.StrictMode`
                -   详解 AI

                    `<React.StrictMode>` 是 React 提供的一个特殊组件，它可以帮助开发者在应用程序中发现潜在问题。当你将应用程序或特定组件包裹在 `<React.StrictMode>` 中时，React 在开发模式下执行额外的检查和警告。

                    `<React.StrictMode>` 的目的是突出显示并警告可能导致应用程序出现错误或性能问题的潜在问题。它可以帮助你捕捉并解决某些类型的错误，这些错误可能在没有使用 `<React.StrictMode>` 的情况下被忽略。

                    以下是 `<React.StrictMode>` 执行的一些检查：
                    1.  发现使用过时 API：`<React.StrictMode>` 会在你使用已弃用或即将弃用的 React API 时发出警告。
                    2.  检测不安全的生命周期方法：它会警告你使用不安全的生命周期方法，并提供更安全的替代方法建议。
                    3.  警告使用已弃用功能：如果你在 React 中使用任何已弃用的功能，`<React.StrictMode>` 会发出警告。
                    4.  检测状态的突变：它帮助你识别直接突变自身状态的组件，这可能会导致错误，并且使数据流程更难理解。
                    5.  发现潜在的不必要的重新渲染：`<React.StrictMode>` 会警告你组件中潜在的不必要重新渲染的来源。
                    需要注意的是，`<React.StrictMode>` 仅用于开发环境。它可以帮助你捕捉和修复问题，但在应用程序的生产构建中不提供任何性能优化。

                    要使用 `<React.StrictMode>`，你可以将其包裹在应用程序的根组件中，通常在主要的 `index.js` 或 `App.js` 文件中：
                    ```react&#x20;jsx
                    import React from 'react';
                    import ReactDOM from 'react-dom';

                    ReactDOM.render(
                      <React.StrictMode>
                        <App />
                      </React.StrictMode>,
                      document.getElementById('root')
                    );
                    ```
                    通过将应用程序包裹在 `<React.StrictMode>` 中，你可以利用 React 的额外检查和警告来提高开发过程中 React 应用程序的质量和性能。
        -   `Component`
            -   \[[🖼️ 图片](../image/image_XHGQAATNnS.png "🖼️ 图片")]
        -   `PureComponent`
            -   `PureComponent`重写了`shouldComponentUpdate()` \[[🖼️ 图片](../image/image_Ro0O_adTJa.png "🖼️ 图片")]
                -   在shouldCompoentUpdate()中进行了一次浅比较，如果旧的数据与更新的数据内存地址相同则返回false，不进行更新
        -   `Fragment`
            -   去掉render时需要包一层div，减少div嵌套
        -   &#x20;startTransition
    ***
    1.  `render()`挂载(渲染)组件到真正的DOM中 \[[\[Web\]DOM](\[Web]DOM_hA1J7qvXNRdJxg7CoGu7X.md "\[Web]DOM")]
        -   组件中`render()`的写法:标签形式,函数形式
        1.  标签形式

            因标签必须闭合 所以有两种写法：单标签写法;双标签写法

            单标签写法

            双标签写法
        2.  函数形式
        -   &#x20;示例：
            -   示例中，组件Dmoe的调用可以写成以下三种方式，效果相同 \[标签形式]
                1.  `<Demo/>`
                2.  `<Demo></Demo>`
                3.  `Demo()`
                    1.  这种写法在[React Developer Tools](<React Developer Tools_kCZQ3ZEZBaRSzsX64FefUy.md> "React Developer Tools")无法显示，因为这样是函数调用，上面两个是以React帮你调用的[¶](https://www.bilibili.com/video/BV1wy4y1D7JT?t=748.1\&p=9 "¶")
            -   示例：函数式组件(简单的组件定义) \[`ReactDOM.render()`]
                -   示例中，组件Dmoe的调用可以写成以下三种方式，效果相同 \[标签形式]
                    1.  `<Demo/>`
                    2.  `<Demo></Demo>`
                    3.  `Demo()`
                        1.  这种写法在[React Developer Tools](<React Developer Tools_kCZQ3ZEZBaRSzsX64FefUy.md> "React Developer Tools")无法显示，因为这样是函数调用，上面两个是以React帮你调用的[¶](https://www.bilibili.com/video/BV1wy4y1D7JT?t=748.1\&p=9 "¶")
                -   React JSX知识点：若大写字母开头，react就去染对应的组件，若组件没有定义，则报错。
                ```javascript
                {% extends 'react_import_tmplate.html' %}

                {% block title %}函数式组件{% endblock %}
                {% block h2 %}函数式组件{% endblock %}

                {% block content %}
                 <!-- // 创建容器 -->
                <div id="text"></div>
                <script type="text/babel">
                    
                    // 创建函数式组件
                    function Demo(){
                        return <h3>我是函数定义的组件适用于简单组件的定义</h3>
                    }
                    // 渲染组件到页面
                    ReactDOM.render(<Demo/>, document.getElementById('text'))
                </script> 
                {% endblock %}
                ```
                ![](../image/image_k96GxtRG2h.png)
    2.  `forceUpdate()`
    ***

##



[\[React\]示例](\[React]示例_6YPAdACbxr3sgF5Mi7FVdp.md "\[React]示例")



## 碎片

[Webpack](Webpack_6tozYheuLN7uJtWbcWkoXJ.md "Webpack")

[\[E\&Q\]React](\[E\&Q]React_fApXwhgpS2hkdLRrNgHD77.md "\[E\&Q]React")

-   \[React]key

    ai

    在React中，`key`是用于在渲染列表或循环生成的元素时，为每个元素分配一个唯一标识的属性。`key`属性通常在`map()`函数中用于生成动态的子组件列表。

    `key`的作用是帮助React在更新DOM时识别元素的唯一性，从而优化性能。当列表中的元素发生变化时，React会使用`key`来确定哪些元素需要被添加、更新或删除，从而避免不必要的DOM操作，提高性能。

    使用`key`的好处包括：
    1.  提高性能：使用`key`可以帮助React在更新DOM时快速识别哪些元素需要更新，从而减少不必要的DOM操作，提高性能。
    2.  保持稳定的DOM结构：使用`key`可以确保React在渲染列表时，保持稳定的DOM结构，防止出现意外的UI变化。
    3.  解决警告：使用`key`可以解决React警告中关于缺少`key`的警告信息。
    需要注意的是，`key`应该是唯一且稳定的，最好使用不会发生变化的属性值作为`key`，如ID、索引等。避免使用随机生成的值作为`key`，因为这样可能导致不稳定的DOM结构和性能问题。同时，`key`只在兄弟节点之间需要是唯一的，不需要在全局范围内唯一。
-   高级函数
    -   [🖼️ 图片](../image/image_j4I95zOydM.png "🖼️ 图片")

        ![](../image/image_6cF8k6FNyR.png)
    -   函数柯里化

        函数柯里化是一种将多参数函数转换为一系列接受单一参数的函数的技术。

        [🖼️ 图片](../image/image_aR-T6nEfF8.png "🖼️ 图片")
-   工具插件

    [React Developer Tools](<React Developer Tools_kCZQ3ZEZBaRSzsX64FefUy.md> "React Developer Tools")

