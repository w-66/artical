# \[Web]react Task

| 标签  |            |
| --- | ---------- |
| END | 2022/11/29 |



*   尚硅谷Reactv16.8教程（2022加更，B站超火react教程）(2429m)(40h) \[[\[Web\]React](\[Web]React_h3XfA4SNWf9ohgsZECjLr3.md "\[Web]React")]

    *   [x] [1 001\_尚硅谷react教程\_react简介\_Duration-27Min](https://www.bilibili.com/video/BV1wy4y1D7JT/?p=1 "1 001_尚硅谷react教程_react简介_Duration-27Min")

    *   [x] [2 002\_尚硅谷react教程\_hello\_react案例\_Duration-25Min](https://www.bilibili.com/video/BV1wy4y1D7JT/?p=2 "2 002_尚硅谷react教程_hello_react案例_Duration-25Min")|示例：入门第一例,引入react，并显示在页面

        *   旧版本依赖包

            [react.development.js](../file/react.development_xgU1tvUKYY.js)

            [react-dom.development.js](../file/react-dom.development_45RiD3XZD7.js)

            [babel.min.js](../file/babel.min_9lDe0ZSuTv.js)

            [prop-types.js](../file/prop-types_xJSH5lIMPl.js)

    *   [x] [3 003\_尚硅谷react教程\_虚拟DOM的两种创建方式\_Duration-12Min](https://www.bilibili.com/video/BV1wy4y1D7JT/?p=3 "3 003_尚硅谷react教程_虚拟DOM的两种创建方式_Duration-12Min")|示例：入门第一例,引入react，并显示在页面|`()`

        *   \[笔记]003虚拟DOM创建方式

            *   示例：入门第一例,引入react，并显示在页面

                *   示例：1/2按顺序引入react 组件 \[[\[HTML\]type](\[HTML]type_8dPVbusmjqyEZkzawtPbbT.md "\[HTML]type")`text/javascript`] [¶](https://www.bilibili.com/video/BV1wy4y1D7JT?t=742.1\&p=2 "¶")

                    *   旧版本依赖包

                        [react.development.js](../file/react.development_xgU1tvUKYY.js)

                        [react-dom.development.js](../file/react-dom.development_45RiD3XZD7.js)

                        [babel.min.js](../file/babel.min_9lDe0ZSuTv.js)

                        [prop-types.js](../file/prop-types_xJSH5lIMPl.js)

                    ```javascript
                    <!DOCTYPE html>
                    <html lang="en">
                    <head>
                        <meta charset="UTF-8">
                        <title>react learn 01</title>
                    </head>
                    <body>
                        <div id="text"></div>

                        <!-- react 核心库 -->
                        <script type="text/javascript" src="/static/js/react.development.js"></script>     
                        <!-- 用于react 操作DOM  -->
                        <script type="text/javascript" src="/static/js/react-dom.development.js"></script> 
                        <!-- 将jsx转换为js -->
                        <script type="text/javascript" src="/static/js/babel.min.js"></script>
                    </body>
                    </html>
                    ```

                *   示例：2/2创建**虚拟DOM**，渲染虚拟DOM到页面 \[[\[HTML\]type](\[HTML]type_8dPVbusmjqyEZkzawtPbbT.md "\[HTML]type")`text/babel`,[\[React\]虚拟DOM](\[React]虚拟DOM_Snd6fanVfJeXQdXpbDqd8.md "\[React]虚拟DOM")]

                    ```javascript
                    <!DOCTYPE html>
                    <html lang="en">
                    <head>
                        <meta charset="UTF-8">
                        <title>react learn 01</title>
                    </head>
                    <body>
                         <!-- 创建一个容器 -->
                        <div id="text"></div>

                        <!-- react 核心库 -->
                        <script type="text/javascript" src="/static/js/react.development.js"></script>     
                        <!-- 用于react 操作DOM  -->
                        <script type="text/javascript" src="/static/js/react-dom.development.js"></script> 
                        <!-- 将jsx转换为js -->
                        <script type="text/javascript" src="/static/js/babel.min.js"></script>
                        <script type="text/babel">  //这里必须写text/babel
                                // 创建虚拟DOM
                                const VDOM = <h1>hello react</h1>  //这里不用写引号，因为不是字符串
                                // 渲染虚拟DOM到页面
                                ReactDOM.render(VDOM,document.getElementById('text'))  // 将VDOM虚拟dom的内容传递到id为text的标签中
                        </script>  
                    </body>
                    </html>
                    ```

                    *   方式1：创建虚拟DOM使用[\[React\]JSX](\[React]JSX_s6YqU4tzdiXR9faUSdiKqB.md "\[React]JSX")

                        *   v1

                            ```javascript
                            <!DOCTYPE html>
                            <html lang="en">
                            <head>
                                <meta charset="UTF-8">
                                <title>react learn 02</title>
                            </head>
                            <body>
                                <!-- 创建一个容器 -->
                                <div id="text"></div>

                                <!-- react 核心库 -->
                                <script type="text/javascript" src="/static/js/react.development.js"></script>     
                                <!-- 用于react 操作DOM  -->
                                <script type="text/javascript" src="/static/js/react-dom.development.js"></script> 
                                <!-- 将jsx转换为js -->
                                <script type="text/javascript" src="/static/js/babel.min.js"></script>
                                <script type="text/babel">  //这里必须写text/babel
                                        // 创建虚拟DOM
                                        const VDOM = <h1 id="title">hello react</h1>  //这里不用写引号，因为不是字符串
                                        // 渲染虚拟DOM到页面
                                        ReactDOM.render(VDOM,document.getElementById('text'))
                                </script>  
                            </body>
                            </html>
                            ```

                        *   v1：`()`创建虚拟DOM时，可换行写HTML \[]

                            ```javascript
                            <!DOCTYPE html>
                            <html lang="en">
                            <head>
                                <meta charset="UTF-8">
                                <title>react learn 02</title>
                            </head>
                            <body>
                                <!-- 创建一个容器 -->
                                <div id="text"></div>

                                <!-- react 核心库 -->
                                <script type="text/javascript" src="/static/js/react.development.js"></script>     
                                <!-- 用于react 操作DOM  -->
                                <script type="text/javascript" src="/static/js/react-dom.development.js"></script> 
                                <!-- 将jsx转换为js -->
                                <script type="text/javascript" src="/static/js/babel.min.js"></script>
                                <script type="text/babel">  //这里必须写text/babel
                                        // 创建虚拟DOM
                                        const VDOM = (  //这里不用写引号，因为不是字符串
                                                <h1 id="title">
                                                    <span>hello react</span>
                                                </h1>
                                        )
                                        // 渲染虚拟DOM到页面
                                        ReactDOM.render(VDOM,document.getElementById('text'))
                                </script>  
                            </body>
                            </html>
                            ```

                    *   方式2：创建虚拟DOM使用[JavaScript](JavaScript_w7M7UmgSNLmfSHDWMLjuEi.md "JavaScript")(不推荐，不方便多层标签嵌套)[¶](https://www.bilibili.com/video/BV1wy4y1D7JT?t=387.1\&p=3 "¶")

                        ![](../image/image_Wl2XmKa3FS.png)

                        ![](../image/image_eDk3VO2WMY.png)

                    *   效果

                        ![](../image/image_Arozc83Pen.png)

                        *   \[E]报错`babel.min.js:24 You are using the in-browser Babel transformer. Be sure to precompile your scripts for production `&#x20;

                            前期暂时这样

                            ![](../image/image_f0XK89AeXz.png)

                            [¶](https://www.bilibili.com/video/BV1wy4y1D7JT?t=1244.0\&p=2 "¶")



    *   [x] [4 004\_尚硅谷react教程\_虚拟DOM与真实DOM\_Duration-6Min](https://www.bilibili.com/video/BV1wy4y1D7JT/?p=4 "4 004_尚硅谷react教程_虚拟DOM与真实DOM_Duration-6Min")|[\[React\]虚拟DOM](\[React]虚拟DOM_Snd6fanVfJeXQdXpbDqd8.md "\[React]虚拟DOM")

        *   \[笔记][虚拟DOM与真实DOM](https://www.bilibili.com/video/BV1wy4y1D7JT/?p=4 "虚拟DOM与真实DOM")

            ![](../image/image_ab1WFO8TIX.png)

    *   [x] [5 005\_尚硅谷react教程\_jsx语法规则\_Duration-26Min](https://www.bilibili.com/video/BV1wy4y1D7JT/?p=5 "5 005_尚硅谷react教程_jsx语法规则_Duration-26Min")|JSX语法规则

        *   \[笔记]jsx语法规则

            ![](../image/image_CuP-PmaSv6.png)

            *

                > 示例知识点：Django模板语法 \[`{% verbatim %}`]

                *   v1：JavaScript中变量传参

                    ```javascript
                    <!DOCTYPE html>
                    <html lang="en">
                    <head>
                        <meta charset="UTF-8">
                        <title>react JSX语法规则</title>
                    </head>
                    <body>
                        <h2>JSX语法规则</h2>
                        <div id="text"></div>

                        <!-- react 核心库 -->
                        <script type="text/javascript" src="/static/js/react.development.js"></script>     
                        <!-- 用于react 操作DOM  -->
                        <script type="text/javascript" src="/static/js/react-dom.development.js"></script> 
                        <!-- 将jsx转换为js -->
                        <script type="text/javascript" src="/static/js/babel.min.js"></script>
                        <script type="text/babel">  
                                const myID = "TITLE"
                                const myData = "hello JSX"
                                const VDOM = (
                                    <h3 id={myID}>
                                        <span>{myData.toLowerCase()}</span>
                                    </h3> 
                                ) 
                                ReactDOM.render(VDOM,document.getElementById('text'))
                        </script>  
                    </body>
                    </html>
                    ```

                    ![](../image/image_1v4mAizIn-.png)

                *   v2：外部添加样式，虚拟DOM中设置样式(内联样式) \[`style`]

                    示例知识点：内联样式，要用`style=({key:value}}`的形式去写。&#x20;

                    ```javascript
                    <!DOCTYPE html>
                    <html lang="en">
                    <head>
                        <meta charset="UTF-8">
                        <title>react JSX语法规则</title>
                        <style>
                            .title{
                                width: 200px;
                                background-color: darkgray;
                            }
                        </style>
                    </head>

                    <body>
                        <h2>JSX语法规则</h2>
                        <div id="text"></div>

                        <!-- react 核心库 -->
                        <script type="text/javascript" src="/static/js/react.development.js"></script>     
                        <!-- 用于react 操作DOM  -->
                        <script type="text/javascript" src="/static/js/react-dom.development.js"></script> 
                        <!-- 将jsx转换为js -->
                        <script type="text/javascript" src="/static/js/babel.min.js">// </script>

                        <script type="text/babel">  
                            const myID = "TITLE"
                            const myData = "hello JSX"
                            const VDOM = (
                                <h3 className="title" id={myID}>
                                    {% verbatim %}      
                                    <span style={{color:'white', fontSize:'30px'}}>{myData.toLowerCase()}</span>
                                    {% endverbatim %}
                                </h3> 
                            ) 
                            ReactDOM.render(VDOM,document.getElementById('text'))
                        </script>  
                    </body>
                    </html>
                    ```

                    ![](../image/image_5I6mEyJ5KI.png)

                *   v3：其他语法：示例知识点：只有一个根标签 ,标签必须闭合 ,标签首字母&#x20;

                    ```javascript
                    <!DOCTYPE html>
                    <html lang="en">
                    <head>
                        <meta charset="UTF-8">
                        <title>react JSX语法规则</title>
                        <style>
                            .title{
                                width: 200px;
                                background-color: darkgray;
                            }
                        </style>
                    </head>

                    <body>
                        <h2>JSX语法规则</h2>
                        <div id="text"></div>

                        <!-- react 核心库 -->
                        <script type="text/javascript" src="/static/js/react.development.js"></script>     
                        <!-- 用于react 操作DOM  -->
                        <script type="text/javascript" src="/static/js/react-dom.development.js"></script> 
                        <!-- 将jsx转换为js -->
                        <script type="text/javascript" src="/static/js/babel.min.js">// </script>

                        <script type="text/babel">  
                            const myID = "TITLE"
                            const myData = "hello JSX"
                            const VDOM = (
                                <div>
                                    <h3 className="title" id={myID}>
                                        {% verbatim %}      
                                        <span style={{color:'white', fontSize:'30px'}}>{myData.toLowerCase()}</span>
                                        {% endverbatim %}
                                    </h3>
                                    <h3>
                                        <p>标签必须闭合(如input)</p>
                                        <input type="text"/>
                                        <p>只能存在一个跟标签(目前)</p>
                                    </h3>
                                </div>
                                
                            ) 
                            ReactDOM.render(VDOM,document.getElementById('text'))
                        </script>  
                    </body>
                    </html>
                    ```

    *   [x] [6 006\_尚硅谷react教程\_jsx小练习\_Duration-22Min](https://www.bilibili.com/video/BV1wy4y1D7JT/?p=6 "6 006_尚硅谷react教程_jsx小练习_Duration-22Min")

        *   \[笔记]JSX小练习

            ![](../image/image_HHtAYqiYrs.png)

            *   示例： JSX小练习：动态的展示如下列表 \[[\[React\]虚拟DOM](\[React]虚拟DOM_Snd6fanVfJeXQdXpbDqd8.md "\[React]虚拟DOM"),箭头函数,`map`]

                ![](../image/image_aG4lvY1EJs.png)

                ![](../image/image_YyEX2Xifl3.png)



    *   [x] [7 007\_尚硅谷react教程\_组件与模块\_Duration-8Min](https://www.bilibili.com/video/BV1wy4y1D7JT/?p=7 "7 007_尚硅谷react教程_组件与模块_Duration-8Min")|[\[React\]组件与模块](\[React]组件与模块_tc8jMTUd6Mm5ypAX4XU8bv.md "\[React]组件与模块")

        *   \[笔记]组件与模块介绍

            ![](../image/image_WH-Cts-lRj.png)

    *   [x] [8 008\_尚硅谷react教程\_开发者工具的安装\_Duration-6Min](https://www.bilibili.com/video/BV1wy4y1D7JT/?p=8 "8 008_尚硅谷react教程_开发者工具的安装_Duration-6Min")|[React Developer Tools](<React Developer Tools_kCZQ3ZEZBaRSzsX64FefUy.md> "React Developer Tools")

    *   [x] [9 009\_尚硅谷react教程\_函数式组件\_Duration-17Min](https://www.bilibili.com/video/BV1wy4y1D7JT/?p=9 "9 009_尚硅谷react教程_函数式组件_Duration-17Min")|React面向\[React]组件编程|函数式组件|babel默认开启严格模式 \[严格模式]

        *   \[笔记]函数式组件

            ![](../image/image_m9K353ao5H.png)

    *   [x] [10 010\_尚硅谷react教程\_复习类相关知识\_Duration-27Min](https://www.bilibili.com/video/BV1wy4y1D7JT/?p=10 "10 010_尚硅谷react教程_复习类相关知识_Duration-27Min")|\[JS]继承:`extends`,`super()`[¶](https://www.bilibili.com/video/BV1wy4y1D7JT?t=1039.6\&p=10 "¶"),重写从父类继承来的方法[¶](https://www.bilibili.com/video/BV1wy4y1D7JT?t=1333.7\&p=10 "¶")|

        *   \[笔记][复习类相关知识](https://www.bilibili.com/video/BV1wy4y1D7JT/?p=10 "复习类相关知识")

            ![](../image/image_J3aUpBxyty.png)

            *   示例：\[React:函数式组件] \[Django:Django 模板文件,\[Dj]模板继承]

                > 写好了Django的路由与视图

                ***

                *   示例：1/2 Django模板文件`react_import_tmplate.html`，按顺序引入React的JavaScript文件 \[[📄 react.development.js](../file/react.development_vcfjn9Nnhd.js "📄 react.development.js"),[📄 react-dom.development.js](../file/react-dom.development_iqGpi5Tb9y.js "📄 react-dom.development.js"),[📄 babel.min.js](../file/babel.min_erx37WqQVK.js "📄 babel.min.js")]

                    ```javascript
                    <!DOCTYPE html>
                    <html lang="en">
                    <head>
                        <meta charset="UTF-8">
                        <title>{% block title %}{% endblock %}</title>
                    </head>
                    <body>
                        <h2>{% block h2 %}{% endblock %}</h2>

                        <!-- react 核心库 -->
                        <script type="text/javascript" src="/static/js/react.development.js"></script>     
                        <!-- 用于react 操作DOM  -->
                        <script type="text/javascript" src="/static/js/react-dom.development.js"></script> 
                        <!-- 将jsx转换为js -->
                        <script type="text/javascript" src="/static/js/babel.min.js"></script>
                        {% block content %}{% endblock %}
                        
                    </body>
                    </html>
                    ```

                *   示例：2/2Django模板继承`learn_react_05.html`

                    ```javascript
                    {% extends 'react_import_tmplate.html' %}

                    {% block title %}函数式组件{% endblock %}
                    {% block h2 %}函数式组件{% endblock %}

                    {% block content %}

                    {% endblock %}
                    ```

                *   示例：函数式组件(简单的组件定义) \[`.render()`]

                    *   示例中，组件Dmoe的调用可以写成以下三种方式，效果相同 \[标签形式]

                        1.  `<Demo/>`

                        2.  `<Demo></Demo>`

                        3.  `Demo()`

                            1.  这种写法在[React Developer Tools](<React Developer Tools_kCZQ3ZEZBaRSzsX64FefUy.md> "React Developer Tools")无法显示，因为这样是函数调用，上面两个是以React帮你调用的[¶](https://www.bilibili.com/video/BV1wy4y1D7JT?t=748.1\&p=9 "¶")

                    *   React JSX知识点：若大写字母开头，react就去染对应的组件，若组件没有定义，则报错。

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

                    ![](../image/image_jDqpHCyz4t.png)

                *   \[笔记]函数式组件

                    ![](../image/image_m9K353ao5H.png)

    *   [x] [11 011\_尚硅谷react教程\_类式组件\_Duration-17Min](https://www.bilibili.com/video/BV1wy4y1D7JT/?p=11 "11 011_尚硅谷react教程_类式组件_Duration-17Min")|类式组件

        *   \[笔记]类式组件

            *   示例：构建第个类式组件 \[类式组件`React.Component``.render()`]

                *   示例：1/2 Django模板文件`react_import_tmplate.html`，按顺序引入React的JavaScript文件 \[[📄 react.development.js](../file/react.development_zKXlz9Pj9B.js "📄 react.development.js"),[📄 react-dom.development.js](../file/react-dom.development_LosYVjwbEU.js "📄 react-dom.development.js"),[📄 babel.min.js](../file/babel.min_rwbP4Fjsy1.js "📄 babel.min.js")]

                    ```javascript
                    <!DOCTYPE html>
                    <html lang="en">
                    <head>
                        <meta charset="UTF-8">
                        <title>{% block title %}{% endblock %}</title>
                    </head>
                    <body>
                        <h2>{% block h2 %}{% endblock %}</h2>

                        <!-- react 核心库 -->
                        <script type="text/javascript" src="/static/js/react.development.js"></script>     
                        <!-- 用于react 操作DOM  -->
                        <script type="text/javascript" src="/static/js/react-dom.development.js"></script> 
                        <!-- 将jsx转换为js -->
                        <script type="text/javascript" src="/static/js/babel.min.js"></script>
                        {% block content %}{% endblock %}
                        
                    </body>
                    </html>
                    ```

                ```javascript
                {% extends 'react_import_tmplate.html' %}

                {% block title %}类式组件{% endblock %}
                {% block h2 %}类式组件{% endblock %}

                {% block content %}
                <!-- // 创建容器 -->
                <div id="text"></div>

                <script type="text/babel">
                    class MyComponent extends React.Component {
                        render(){
                            return  <h3>我是类定义的组件(适用于[复杂组件]的定义)</h3>
                        }
                    }
                    ReactDOM.render(<MyComponent/>, document.getElementById('text'))
                </script>
                {% endblock %}
                ```

                ![](../image/image_kVIJshWeTE.png)

    *   [x] [12 012\_尚硅谷react教程\_对state的理解\_Duration-6Min](https://www.bilibili.com/video/BV1wy4y1D7JT/?p=12 "12 012_尚硅谷react教程_对state的理解_Duration-6Min")|组件实例的三大核心属性state简介

    *   [x] [13 013\_尚硅谷react教程\_初始化state\_Duration-13Min](https://www.bilibili.com/video/BV1wy4y1D7JT/?p=13 "13 013_尚硅谷react教程_初始化state_Duration-13Min")

        *   \[笔记]初始化state

            *   示例： \[React:state,`.render()`] \[JS:`constructor`,`extends`,`super()`,`this`]

                *   v1：设置状态属性

                    ```javascript
                    {% extends 'react_import_tmplate.html' %}

                    {% block title %}类式组件属性state{% endblock %}
                    {% block h2 %}类式组件属性:state{% endblock %}

                    {% block content %}
                        <!-- 创建容器 -->
                        <div id="text"></div>
                        <script type="text/babel">
                            class Weather extends React.Component{
                                constructor(props){
                                    super(props)
                                    this.state = {isHot:true}
                                }
                                render(){
                                    return <h3>今天天气很炎热！</h3>
                                }
                            }
                            ReactDOM.render(<Weather/>, document.getElementById('text'))
                        </script>

                    {% endblock %}
                    ```

                *   v2：调用状态属性 \[`条件表达式?表达式1:表达式2;`]

                    *   v1

                        ```javascript
                        {% extends 'react_import_tmplate.html' %}

                        {% block title %}类式组件属性state{% endblock %}
                        {% block h2 %}类式组件属性:state{% endblock %}

                        {% block content %}
                            <!-- 创建容器 -->
                            <div id="text"></div>
                            <script type="text/babel">
                                class Weather extends React.Component{
                                    constructor(props){
                                        super(props)
                                        this.state = {isHot:false}
                                    }
                                    render(){
                                        return <h3>今天天气很{this.state.isHot ? '炎热' : '凉快'}！</h3>
                                    }
                                }
                                ReactDOM.render(<Weather/>, document.getElementById('text'))
                            </script>
                        {% endblock %}
                        ```

                    *   v2：将值变成变量，方便调用

                        ```javascript
                        {% extends 'react_import_tmplate.html' %}

                        {% block title %}类式组件属性state{% endblock %}
                        {% block h2 %}类式组件属性:state{% endblock %}

                        {% block content %}
                            <!-- 创建容器 -->
                            <div id="text"></div>
                            <script type="text/babel">
                                class Weather extends React.Component{
                                    constructor(props){
                                        super(props)
                                        this.state = {isHot:false}
                                    }
                                    render(){
                                        const {isHot} = this.state
                                        return <h3>今天天气很{isHot ? '炎热' : '凉快'}！</h3>
                                    }
                                }
                                ReactDOM.render(<Weather/>, document.getElementById('text'))
                            </script>
                        {% endblock %}
                        ```

    *   [x] [14 014\_尚硅谷react教程\_react中的事件绑定\_Duration-12Min](https://www.bilibili.com/video/BV1wy4y1D7JT/?p=14 "14 014_尚硅谷react教程_react中的事件绑定_Duration-12Min")|\[JS]事件绑定|React事件绑定

        *   \[笔记]React中的事件绑定

            *   示例：1/2 JavaScript原生事件绑定：点击按钮弹窗展示\[JS]事件绑定 \[`.getElementById()`,`.addEventListener()`,`onclick`,`alert()`,[\[HTML\]onclick](\[HTML]onclick_wn5BFu5pYwqozVbCKe1xC7.md "\[HTML]onclick")]

                ```javascript
                <!DOCTYPE html>
                <html lang="en">
                <head>
                    <meta charset="UTF-8">
                    <title>Document</title>
                </head>
                <body>
                    <button id="a1">按钮1</button>
                    <button id="a2">按钮2</button>
                    <button onclick="demo()">按钮3</button>
                    <script>
                        const va1 = document.getElementById('a1')
                        va1.addEventListener('click', ()=>{
                            alert('按钮1被点击')
                        })
                        const va2 = document.getElementById('a2')
                        va2.onclick = ()=>{
                            alert('按钮2被点击')
                        }
                        function demo(){
                            alert('按钮3被点击')
                        }
                    </script>
                </body>
                </html>
                ```



            *   示例：2/2 React事件绑定

                *   可以在React中使用原生JS但是不推荐

                    ![](../image/image_uyTciibc1l.png)





                *   示例：React事件绑定，推荐方式&#x20;

                    ```javascript
                    {% extends 'react_import_tmplate.html' %}

                    {% block title %}类式组件属性state{% endblock %}
                    {% block h2 %}类式组件属性:state{% endblock %}

                    {% block content %}
                        <!-- 创建容器 -->
                        <div id="text"></div>
                        <script type="text/babel">
                            class Weather extends React.Component{
                                constructor(props){
                                    super(props)
                                    this.state = {isHot:false}
                                }
                                render(){
                                    console.log(this)
                                    // 读取状态
                                    const {isHot} = this.state
                                    console.log(isHot)
                                    return <h3 onClick={demo}>今天天气很{isHot ? '炎热' : '凉快'}！</h3>
                                }
                            }
                            ReactDOM.render(<Weather/>, document.getElementById('text'))
                            function demo(){
                                alert('被点击')
                            }
                        </script>
                    {% endblock %}
                    ```



    *   [x] [15 015\_尚硅谷react教程\_类中方法中的this\_Duration-23Min](https://www.bilibili.com/video/BV1wy4y1D7JT/?p=15 "15 015_尚硅谷react教程_类中方法中的this_Duration-23Min")|`this`?|

    *   [x] [16 016\_尚硅谷react教程\_解决类中this指向问题\_Duration-8Min](https://www.bilibili.com/video/BV1wy4y1D7JT/?p=16 "16 016_尚硅谷react教程_解决类中this指向问题_Duration-8Min")|`this`,`.bind()`,`.hsetState()`

        *   \[笔记]解决类中的this指向问题

            *   &#x20;示例： \[`this`,`.bind()`]

                ![](../image/image_1jEVKAPPVk.png)

    *   [x] [17 017\_尚硅谷react教程\_setState的使用\_Duration-19Min](https://www.bilibili.com/video/BV1wy4y1D7JT/?p=17 "17 017_尚硅谷react教程_setState的使用_Duration-19Min")

        *   \[笔记]：setState的使用

            ![](../image/image_TChGN2DfXp.png)

            *   示例：v1点击替换文字 \[`.hsetState()`]

                ![](../image/image_-gIVnyzXg9.png)

                ![](../image/image_cH1OOBHPTa.png)

                ```javascript
                {% extends 'react_import_tmplate.html' %}

                {% block title %}setState{% endblock %}
                {% block h2 %}setState{% endblock %}

                {% block content %}
                    <!-- 创建容器 -->
                    <div id="text"></div>
                    <script type="text/babel">
                        class Weather extends React.Component{
                            constructor(props){
                                super(props)
                                this.state = {isHot:false, fen:'有风'}
                                // 解决changWeather()指向问题
                                this.changW = this.changWeather.bind(this)
                            }
                            render(){
                                // console.log(this)
                                // 读取状态
                                const {isHot,fen} = this.state
                                // console.log(isHot)
                                return <h3 onClick={this.changW}>今天天气很{isHot ? '炎热' : '凉快'},{fen}！</h3>
                            }
                            changWeather(){
                                const isHot = this.state.isHot
                                this.setState({isHot:!isHot}) 
                                // console.log(isHot)
                            }
                        }
                        ReactDOM.render(<Weather/>, document.getElementById('text'))
                        function demo(){
                            alert('被点击')
                        }
                    </script>
                {% endblock %}
                ```



    *   [x] [18 018\_尚硅谷react教程\_state的简写方式\_Duration-18Min](https://www.bilibili.com/video/BV1wy4y1D7JT/?p=18 "18 018_尚硅谷react教程_state的简写方式_Duration-18Min")|类式组件

        *   \[笔记]：state的简写方式

            *   示例：v1点击替换文字 \[`.hsetState()`]

                ![](../image/image_-gIVnyzXg9.png)

                ![](../image/image_cH1OOBHPTa.png)

                ```javascript
                {% extends 'react_import_tmplate.html' %}

                {% block title %}setState{% endblock %}
                {% block h2 %}setState{% endblock %}

                {% block content %}
                    <!-- 创建容器 -->
                    <div id="text"></div>
                    <script type="text/babel">
                        class Weather extends React.Component{
                            constructor(props){
                                super(props)
                                this.state = {isHot:false, fen:'有风'}
                                // 解决changWeather()指向问题
                                this.changW = this.changWeather.bind(this)
                            }
                            render(){
                                // console.log(this)
                                // 读取状态
                                const {isHot,fen} = this.state
                                // console.log(isHot)
                                return <h3 onClick={this.changW}>今天天气很{isHot ? '炎热' : '凉快'},{fen}！</h3>
                            }
                            changWeather(){
                                const isHot = this.state.isHot
                                this.setState({isHot:!isHot}) 
                                // console.log(isHot)
                            }
                        }
                        ReactDOM.render(<Weather/>, document.getElementById('text'))
                        function demo(){
                            alert('被点击')
                        }
                    </script>
                {% endblock %}
                ```



            *   示例：v2 精简 \[类式组件]

                ```javascript
                <script type="text/babel">
                    class Weather extends React.Component{
                    
                        state = {isHost:false, fen:'有风'}

                        render(){
                            const {isHot,fen} = this.state
                            return <h3 onClick={this.changWeather}>今天天气很{isHot ? '炎热' : '凉快'},{fen}！</h3>
                        }

                        changWeather = ()=>{
                            const isHot = this.state.isHot
                            this.setState({isHot:!isHot}) 
                        }
                    }
                    ReactDOM.render(<Weather/>, document.getElementById('text'))
                </script>
                    
                ```

    *   [x] [19 019\_尚硅谷react教程\_总结state\_Duration-4Min](https://www.bilibili.com/video/BV1wy4y1D7JT/?p=19 "19 019_尚硅谷react教程_总结state_Duration-4Min")|state

        *   \[笔记]总结state

            ![](../image/image_FAJHYaw2-N.png)

    *   [x] [20 020\_尚硅谷react教程\_props的基本使用\_Duration-10Min](https://www.bilibili.com/video/BV1wy4y1D7JT/?p=20 "20 020_尚硅谷react教程_props的基本使用_Duration-10Min")|props

        *   \[笔记]props的基本使用

            *   示例：props的基本使用 \[props] \[解构赋值]

                ![](../image/image_zhwr2rnlEE.png)

                ![](../image/image_EdHljfi8KG.png)

                *   v1

                    ```javascript
                    {% extends 'react_import_tmplate.html' %}

                    {% block title %}组件实例的三大核心属性：props{% endblock %}
                    {% block h2 %}组件实例的三大核心属性：props{% endblock %}

                    {% block content %}
                        <!-- 创建容器 -->
                        <div id="text"></div>
                        <div id="text1"></div>

                        <script type="text/babel"> 
                            class Person extends React.Component{
                                render(){
                                    return (
                                        <ul>
                                            <li>{this.props.name}</li>
                                            <li>{this.props.age}</li>
                                            <li>{this.props.weight}</li>
                                        </ul>
                                    )
                                }
                            }
                            ReactDOM.render(<Person name='momo' age='21' weight='50kg'/>, document.getElementById('text'))
                            ReactDOM.render(<Person name='kaka' age='19' weight='50kg'/>, document.getElementById('text1'))
                        </script>


                    {% endblock %}
                    ```

                *   v2  修改一点：使用解构赋值

                    ```javascript
                    {% extends 'react_import_tmplate.html' %}

                    {% block title %}组件实例的三大核心属性：props{% endblock %}
                    {% block h2 %}组件实例的三大核心属性：props{% endblock %}

                    {% block content %}
                        <!-- 创建容器 -->
                        <div id="text"></div>
                        <div id="text1"></div>

                        <script type="text/babel"> 
                            class Person extends React.Component{
                                render(){
                                    const {name, age, weight} = this.props  // 解构赋值
                                    return (
                                        <ul>
                                            <li>{this.props.name}</li>
                                            <li>{this.props.age}</li>
                                            <li>{this.props.weight}</li>
                                        </ul>
                                    )
                                }
                            }
                            ReactDOM.render(<Person name='momo' age='21' weight='50kg'/>, document.getElementById('text'))
                            ReactDOM.render(<Person name='kaka' age='19' weight='50kg'/>, document.getElementById('text1'))
                        </script>


                    {% endblock %}
                    ```

    *   [x] [21 021\_尚硅谷react教程\_批量传递props\_Duration-17Min](https://www.bilibili.com/video/BV1wy4y1D7JT/?p=21 "21 021_尚硅谷react教程_批量传递props_Duration-17Min")|props

        *   \[笔记]

            *   示例：v3v2  修改一点：使用解构赋值改进：props批量传递

                ```javascript
                {% extends 'react_import_tmplate.html' %}

                {% block title %}组件实例的三大核心属性：props{% endblock %}
                {% block h2 %}组件实例的三大核心属性：props{% endblock %}

                {% block content %}
                    <!-- 创建容器 -->
                    <div id="text"></div>
                    <div id="text1"></div>
                    <div id="text2"></div>

                    <script type="text/babel"> 
                        class Person extends React.Component{
                            render(){
                                const {name, age, weight} = this.props  // 解构赋值
                                return (
                                    <ul>
                                        <li>{name}</li>
                                        <li>{age}</li>
                                        <li>{weight}</li>
                                    </ul>
                                )
                            }
                        }
                        const p = {name:'momo',age:'20',weight:'50kg'}
                        const p1 = {name:'kaka',age:'29',weight:'50kg'}
                        ReactDOM.render(<Person {...p}/>, document.getElementById('text'))
                        ReactDOM.render(<Person {...p1}/>, document.getElementById('text1'))

                    </script>


                {% endblock %}
                ```



    *   [x] [22 022\_尚硅谷react教程\_对props进行限制\_Duration-23Min](https://www.bilibili.com/video/BV1wy4y1D7JT/?p=22 "22 022_尚硅谷react教程_对props进行限制_Duration-23Min")|props|**`PropTypes`**`.number`,`.func`,`.string`,`.isRequired`,**`defaultProps`**

        *   \[笔记]对props进行限制：

            *   示例：想让age在页面中加1但是实际age不变，以及名字只能是字符串且非空; 否则将报错。年龄为空，默认为18 \[**`PropTypes`**`.string`,`.isRequired`,**`defaultProps`**]

                *   v1：数据类型是字符串，显示错误

                    ```javascript
                    {% extends 'react_import_tmplate.html' %}

                    {% block title %}组件实例的三大核心属性：props{% endblock %}
                    {% block h2 %}组件实例的三大核心属性：props{% endblock %}

                    {% block content %}
                        <!-- 创建容器 -->
                        <div id="text"></div>
                        <div id="text1"></div>
                        <div id="text2"></div>

                        <script type="text/babel"> 
                            class Person extends React.Component{
                                render(){
                                    const {name, age, weight} = this.props  // 解构赋值
                                    return (
                                        <ul>
                                            <li>{name}</li>
                                            <li>{age+1}</li>
                                            <li>{weight}</li>
                                        </ul>
                                    )
                                }
                            }
                            const p = {name:'momo',age:'20',weight:'50kg'}
                            const p1 = {name:'kaka',age:'29',weight:'50kg'}
                            ReactDOM.render(<Person {...p}/>, document.getElementById('text'))
                            ReactDOM.render(<Person {...p1}/>, document.getElementById('text1'))
                            const p2 = {name:'jojo',age:4,weight:'50kg'}
                            ReactDOM.render(<Person {...p2}/>, document.getElementById('text2'))
                        </script>


                    {% endblock %}
                    ```

                    ![](../image/image_3vSgJnxG7S.png)

                *   v2：解决办法：age在页面中加1但是实际age不变

                    ![](../image/image_F6enlQDuRA.png)

                    ```javascript
                    {% extends 'react_import_tmplate.html' %}

                    {% block title %}组件实例的三大核心属性：props{% endblock %}
                    {% block h2 %}组件实例的三大核心属性：props{% endblock %}

                    {% block content %}
                        <!-- 创建容器 -->
                        <div id="text"></div>
                        <div id="text1"></div>
                        <div id="text2"></div>

                        <script type="text/babel"> 
                            class Person extends React.Component{
                                render(){
                                    const {name, age, weight} = this.props  // 解构赋值
                                    return (
                                        <ul>
                                            <li>{name}</li>
                                            <li>{age+1}</li>
                                            <li>{weight}</li>
                                        </ul>
                                    )
                                }
                            }
                            const p = {name:'momo',age:20,weight:'50kg'}
                            ReactDOM.render(<Person {...p}/>, document.getElementById('text'))

                            ReactDOM.render(<Person name='kaka' age={29} weight='50kg'/>, document.getElementById('text1'))
                            
                            const p2 = {name:'jojo',age:4,weight:'50kg'}
                            ReactDOM.render(<Person {...p2}/>, document.getElementById('text2'))
                        </script>


                    {% endblock %}
                    ```

                *   v3：需要增加新的js文件 用于限制组件标签属性限制，模板文件：react\_import\_tmplate.html \[[📄 prop-types.js](../file/prop-types_-YaUsGZ1Bf.js "📄 prop-types.js")][¶](https://www.bilibili.com/video/BV1wy4y1D7JT?t=837.9\&p=22 "¶")

                    ```javascript
                    <!DOCTYPE html>
                    <html lang="en">
                    <head>
                        <meta charset="UTF-8">
                        <title>{% block title %}{% endblock %}</title>
                    </head>
                    <body>
                        <h2>{% block h2 %}{% endblock %}</h2>

                        <!-- react 核心库 -->
                        <script type="text/javascript" src="/static/js/react.development.js"></script>     
                        <!-- 用于react 操作DOM  -->
                        <script type="text/javascript" src="/static/js/react-dom.development.js"></script> 
                        <!-- 将jsx转换为js -->
                        <script type="text/javascript" src="/static/js/babel.min.js"></script>
                        <!-- 引入prop-types.js，用于限制组件标签属性限制 -->
                        <script type="text/javascript" src="/static/js/prop-types.js"></script>
                        {% block content %}{% endblock %}
                    </body>
                    </html>
                    ```



                *   v4：限制传输的数据类型 名字只能是字符串且非空

                    *   正常代码&#x20;

                        ```javascript
                        {% extends 'react_import_tmplate.html' %}

                        {% block title %}组件实例的三大核心属性：props{% endblock %}
                        {% block h2 %}组件实例的三大核心属性：props{% endblock %}

                        {% block content %}
                            <!-- 创建容器 -->
                            <div id="text"></div>
                            <div id="text1"></div>
                            <div id="text2"></div>

                            <script type="text/babel"> 
                                class Person extends React.Component{
                                    render(){
                                        const {name, age, weight} = this.props  // 解构赋值
                                        return (
                                            <ul>
                                                <li>{name}</li>
                                                <li>{age+1}</li>
                                                <li>{weight}</li>
                                            </ul>
                                        )
                                    }
                                }
                                Person.propTypes = {
                                    name:PropTypes.string  // 限制为，name只能是字符串类型，否则将报错
                                }
                                const p = {name:'tom',age:20,weight:'50kg'}
                                ReactDOM.render(<Person {...p}/>, document.getElementById('text'))

                                ReactDOM.render(<Person name='kaka' age={29} weight='50kg'/>, document.getElementById('text1'))
                                
                                const p2 = {name:'jojo',age:4,weight:'50kg'}
                                ReactDOM.render(<Person {...p2}/>, document.getElementById('text2'))
                            </script>


                        {% endblock %}
                        ```

                    *   \[E]错误代码 指定为字符串，传入数字的报错

                        *   错误代码

                            ```javascript
                            {% extends 'react_import_tmplate.html' %}

                            {% block title %}组件实例的三大核心属性：props{% endblock %}
                            {% block h2 %}组件实例的三大核心属性：props{% endblock %}

                            {% block content %}
                                <!-- 创建容器 -->
                                <div id="text"></div>
                                <div id="text1"></div>
                                <div id="text2"></div>

                                <script type="text/babel"> 
                                    class Person extends React.Component{
                                        render(){
                                            const {name, age, weight} = this.props  // 解构赋值
                                            return (
                                                <ul>
                                                    <li>{name}</li>
                                                    <li>{age+1}</li>
                                                    <li>{weight}</li>
                                                </ul>
                                            )
                                        }
                                    }
                                    Person.propTypes = {
                                        name:PropTypes.string  // 限制为，name只能是字符串类型，否则将报错
                                    }
                                    const p = {name:111,age:20,weight:'50kg'}
                                    ReactDOM.render(<Person {...p}/>, document.getElementById('text'))

                                    ReactDOM.render(<Person name='kaka' age={29} weight='50kg'/>, document.getElementById('text1'))
                                    
                                    const p2 = {name:'jojo',age:4,weight:'50kg'}
                                    ReactDOM.render(<Person {...p2}/>, document.getElementById('text2'))
                                </script>


                            {% endblock %}
                            ```

                        ```javascript
                        react.development.js:2726 Warning: Failed prop type: Invalid prop `name` of type `number` supplied to `Person`, expected `string`.
                            in Person
                        ```

                        ![](../image/image_AytkD88krZ.png)

                    *   \[E]错误代码 指定属性非空，传入空

                        *   误code

                            ```javascript
                            {% extends 'react_import_tmplate.html' %}

                            {% block title %}组件实例的三大核心属性：props{% endblock %}
                            {% block h2 %}组件实例的三大核心属性：props{% endblock %}

                            {% block content %}
                                <!-- 创建容器 -->
                                <div id="text"></div>
                                <div id="text1"></div>
                                <div id="text2"></div>

                                <script type="text/babel"> 
                                    class Person extends React.Component{
                                        render(){
                                            const {name, age, weight} = this.props  // 解构赋值
                                            return (
                                                <ul>
                                                    <li>{name}</li>
                                                    <li>{age+1}</li>
                                                    <li>{weight}</li>
                                                </ul>
                                            )
                                        }
                                    }
                                    Person.propTypes = {
                                        name:PropTypes.string.isRequired,  // 限制为，name只能是字符串类型，否则将报错
                                    }
                                    const p = {name:'tom',age:20,weight:'50kg'}
                                    ReactDOM.render(<Person {...p}/>, document.getElementById('text'))

                                    ReactDOM.render(<Person age={29} weight='50kg'/>, document.getElementById('text1'))
                                    
                                    const p2 = {name:'jojo',age:4,weight:'50kg'}
                                    ReactDOM.render(<Person {...p2}/>, document.getElementById('text2'))
                                </script>


                            {% endblock %}
                            ```

                        ```javascript
                        react.development.js:2726 Warning: Failed prop type: The prop `name` is marked as required in `Person`, but its value is `undefined`.
                            in Person
                        ```

                        ![](../image/image_q8ns9aBD4u.png)

                *   v5：年龄为空，默认为18

                    ![](../image/image_1UTik3gtak.png)

                    ```javascript
                    {% extends 'react_import_tmplate.html' %}

                    {% block title %}组件实例的三大核心属性：props{% endblock %}
                    {% block h2 %}组件实例的三大核心属性：props{% endblock %}

                    {% block content %}
                        <!-- 创建容器 -->
                        <div id="text"></div>
                        <div id="text1"></div>
                        <div id="text2"></div>

                        <script type="text/babel"> 
                            class Person extends React.Component{
                                render(){
                                    const {name, age, weight} = this.props  // 解构赋值
                                    return (
                                        <ul>
                                            <li>{name}</li>
                                            <li>{age+1}</li>
                                            <li>{weight}</li>
                                        </ul>
                                    )
                                }
                            }
                            Person.propTypes = {
                                name:PropTypes.string.isRequired,  // 限制为，name只能是字符串类型，否则将报错
                            }
                            Person.defaultProps = {
                                age:18,
                            }
                            const p = {name:'tom',age:20,weight:'50kg'}
                            ReactDOM.render(<Person {...p}/>, document.getElementById('text'))

                            ReactDOM.render(<Person name='kaka' age={29} weight='50kg'/>, document.getElementById('text1'))
                            
                            const p2 = {name:'jojo', weight:'50kg'}
                            ReactDOM.render(<Person {...p2}/>, document.getElementById('text2'))
                        </script>


                    {% endblock %}
                    ```

    *   [ ] [23 023\_尚硅谷react教程\_props的简写方式\_Duration-8Min](https://www.bilibili.com/video/BV1wy4y1D7JT/?p=23 "23 023_尚硅谷react教程_props的简写方式_Duration-8Min")|props属性|参数只读[¶](https://www.bilibili.com/video/BV1wy4y1D7JT?t=63.5\&p=23 "¶")||静态方法|state[¶](https://www.bilibili.com/video/BV1wy4y1D7JT?t=517.1\&p=23 "¶")

        *   \[笔记]props简写方式

            ```javascript
            {% extends 'react_import_tmplate.html' %}

            {% block title %}组件实例的三大核心属性：props{% endblock %}
            {% block h2 %}组件实例的三大核心属性：props{% endblock %}

            {% block content %}
                <!-- 创建容器 -->
                <div id="text"></div>
                <div id="text1"></div>
                <div id="text2"></div>

                <script type="text/babel"> 
                    class Person extends React.Component{
                        static propTypes = {                   // 类的静态属性
                            name:PropTypes.string.isRequired,  // 限制为，name只能是字符串类型，否则将报错
                        }
                        static defaultProps = {
                            age:18,                            // 限制为，年龄为空，默认18
                        }
                        render(){
                            const {name, age, weight} = this.props  // 解构赋值
                            return (
                                <ul>
                                    <li>{name}</li>
                                    <li>{age+1}</li>
                                    <li>{weight}</li>
                                </ul>
                            )
                        }
                    }

                    const p = {name:'tom',age:20,weight:'50kg'}
                    ReactDOM.render(<Person {...p}/>, document.getElementById('text'))

                    ReactDOM.render(<Person name='kaka' age={29} weight='50kg'/>, document.getElementById('text1'))
                    
                    const p2 = {name:'jojo', weight:'50kg'}
                    ReactDOM.render(<Person {...p2}/>, document.getElementById('text2'))
                </script>


            {% endblock %}
            ```

    *   [ ] [24 024\_尚硅谷ract教程\_类式组件中的构造器与props\_Duration-10Min](https://www.bilibili.com/video/BV1wy4y1D7JT/?p=24 "24 024_尚硅谷ract教程_类式组件中的构造器与props_Duration-10Min")|`constructor`,构造方法中的props|几乎用不到

        *   \[笔记][类式组件中的构造器与props](https://www.bilibili.com/video/BV1wy4y1D7JT/?p=24 "类式组件中的构造器与props")

            结论：构造方法中的props能省则省

            *   截图

                ![](../image/image_OvpDpd-Gxx.png)

    *   [ ] [25 025\_尚硅谷react教程\_函数式组件使用props\_Duration-8Min](https://www.bilibili.com/video/BV1wy4y1D7JT/?p=25 "25 025_尚硅谷react教程_函数式组件使用props_Duration-8Min")函数式组件props

        *   \[笔记]

            *   示例：函数式组件传输props属性中的值 \[`.render()`,props,`...`]

                ![](../image/image_9jEDnkh2DM.png)

                ```javascript
                {% extends 'react_import_tmplate.html' %}

                {% block title %}函数式组件的props{% endblock %}
                {% block h2 %}函数式组件的props{% endblock %}

                {% block content %}
                    <!-- 创建容器 -->
                    <div id="text"></div>

                    <script type="text/babel">
                        function Person(props){
                            const {name,age,weight} = props
                            return(
                                <div>
                                    <ul>
                                        <li>{name}</li>
                                        <li>{age}</li>
                                        <li>{weight}</li>
                                    </ul>
                                </div>
                            )
                        }
                        const p = {name:'tom',age:20,weight:'50kg'}
                        ReactDOM.render(<Person {...p}/>, document.getElementById('text'))
                    </script>
                {% endblock %}
                ```



    *   [ ] [26 026\_尚硅谷react教程\_总结props\_Duration-4Min](https://www.bilibili.com/video/BV1wy4y1D7JT/?p=26 "26 026_尚硅谷react教程_总结props_Duration-4Min")

    *   [ ] [27 027\_尚硅谷react教程\_字符串形式的ref\_Duration-15Min](https://www.bilibili.com/video/BV1wy4y1D7JT/?p=27 "27 027_尚硅谷react教程_字符串形式的ref_Duration-15Min")

    *   [ ] [28 028\_尚硅谷react教程\_回调形式的ref\_Duration-14Min](https://www.bilibili.com/video/BV1wy4y1D7JT/?p=28 "28 028_尚硅谷react教程_回调形式的ref_Duration-14Min")

    *   [ ] [29 029\_尚硅谷react教程\_回调ref中调用次数的问题\_Duration-18Min](https://www.bilibili.com/video/BV1wy4y1D7JT/?p=29 "29 029_尚硅谷react教程_回调ref中调用次数的问题_Duration-18Min")

    *   [ ] [30 030\_尚硅谷react教程\_createRef的使用\_Duration-8Min](https://www.bilibili.com/video/BV1wy4y1D7JT/?p=30 "30 030_尚硅谷react教程_createRef的使用_Duration-8Min")

    *   [ ] [31 031\_尚硅谷react教程\_总结ref\_Duration-3Min](https://www.bilibili.com/video/BV1wy4y1D7JT/?p=31 "31 031_尚硅谷react教程_总结ref_Duration-3Min")

    *   [ ] [32 032\_尚硅谷react教程\_react中的事件处理\_Duration-8Min](https://www.bilibili.com/video/BV1wy4y1D7JT/?p=32 "32 032_尚硅谷react教程_react中的事件处理_Duration-8Min")

    *   [ ] [33 033\_尚硅谷react教程\_非受控组件\_Duration-13Min](https://www.bilibili.com/video/BV1wy4y1D7JT/?p=33 "33 033_尚硅谷react教程_非受控组件_Duration-13Min")

    *   [ ] [34 034\_尚硅谷react教程\_受控组件\_Duration-10Min](https://www.bilibili.com/video/BV1wy4y1D7JT/?p=34 "34 034_尚硅谷react教程_受控组件_Duration-10Min")

    *   [ ] [35 035\_尚硅谷react教程\_高阶函数\_函数柯里化\_Duration-26Min](https://www.bilibili.com/video/BV1wy4y1D7JT/?p=35 "35 035_尚硅谷react教程_高阶函数_函数柯里化_Duration-26Min")

    *   [ ] [36 036\_尚硅谷react教程\_不用柯里化的写法\_Duration-6Min](https://www.bilibili.com/video/BV1wy4y1D7JT/?p=36 "36 036_尚硅谷react教程_不用柯里化的写法_Duration-6Min")

    *   [ ] [37 037\_尚硅谷react教程\_引出生命周期\_Duration-39Min](https://www.bilibili.com/video/BV1wy4y1D7JT/?p=37 "37 037_尚硅谷react教程_引出生命周期_Duration-39Min")

    *   [ ] [38 038\_尚硅谷react教程\_生命周期(旧)\_组件挂载流程\_Duration-14Min](https://www.bilibili.com/video/BV1wy4y1D7JT/?p=38 "38 038_尚硅谷react教程_生命周期(旧)_组件挂载流程_Duration-14Min")

    *   [ ] [39 039\_尚硅谷react教程\_生命周期(旧)\_setState流程\_Duration-13Min](https://www.bilibili.com/video/BV1wy4y1D7JT/?p=39 "39 039_尚硅谷react教程_生命周期(旧)_setState流程_Duration-13Min")

    *   [ ] [40 040\_尚硅谷react教程\_生命周期(旧)\_forceUpdate流程\_Duration-5Min](https://www.bilibili.com/video/BV1wy4y1D7JT/?p=40 "40 040_尚硅谷react教程_生命周期(旧)_forceUpdate流程_Duration-5Min")

    *   [ ] [41 041\_尚硅谷react教程\_生命周期(旧)\_父组件render流程\_Duration-14Min](https://www.bilibili.com/video/BV1wy4y1D7JT/?p=41 "41 041_尚硅谷react教程_生命周期(旧)_父组件render流程_Duration-14Min")

    *   [ ] [42 042\_尚硅谷react教程\_总结生命周期(旧)\_Duration-9Min](https://www.bilibili.com/video/BV1wy4y1D7JT/?p=42 "42 042_尚硅谷react教程_总结生命周期(旧)_Duration-9Min")

    *   [ ] [43 043\_尚硅谷react教程\_对比新旧生命周期\_Duration-31Min](https://www.bilibili.com/video/BV1wy4y1D7JT/?p=43 "43 043_尚硅谷react教程_对比新旧生命周期_Duration-31Min")

    *   [ ] [44 044\_尚硅谷react教程\_getDerivedStateFromProps\_Duration-16Min](https://www.bilibili.com/video/BV1wy4y1D7JT/?p=44 "44 044_尚硅谷react教程_getDerivedStateFromProps_Duration-16Min")

    *   [ ] [45 045\_尚硅谷react教程\_getSnapshotBeforeUpdate\_Duration-16Min](https://www.bilibili.com/video/BV1wy4y1D7JT/?p=45 "45 045_尚硅谷react教程_getSnapshotBeforeUpdate_Duration-16Min")

    *   [ ] [46 046\_尚硅谷react教程\_getSnapshotBeforeUpdate举例\_Duration-19Min](https://www.bilibili.com/video/BV1wy4y1D7JT/?p=46 "46 046_尚硅谷react教程_getSnapshotBeforeUpdate举例_Duration-19Min")

    *   [ ] [47 047\_尚硅谷react教程\_总结生命周期(新)\_Duration-4Min](https://www.bilibili.com/video/BV1wy4y1D7JT/?p=47 "47 047_尚硅谷react教程_总结生命周期(新)_Duration-4Min")

    *   [ ] [48 048\_尚硅谷react教程\_DOM的diffing算法\_Duration-45Min](https://www.bilibili.com/video/BV1wy4y1D7JT/?p=48 "48 048_尚硅谷react教程_DOM的diffing算法_Duration-45Min")

    *   [ ] [49 049\_尚硅谷react教程\_初始化react脚手架\_Duration-23Min](https://www.bilibili.com/video/BV1wy4y1D7JT/?p=49 "49 049_尚硅谷react教程_初始化react脚手架_Duration-23Min")

    *   [ ] [50 050\_尚硅谷react教程\_脚手架文件介绍\_public\_Duration-30Min](https://www.bilibili.com/video/BV1wy4y1D7JT/?p=50 "50 050_尚硅谷react教程_脚手架文件介绍_public_Duration-30Min")

    *   [ ] [51 051\_尚硅谷react教程\_脚手架文件介绍\_src\_Duration-18Min](https://www.bilibili.com/video/BV1wy4y1D7JT/?p=51 "51 051_尚硅谷react教程_脚手架文件介绍_src_Duration-18Min")

    *   [ ] [52 052\_尚硅谷react教程\_一个简单的Hello组件\_Duration-38Min](https://www.bilibili.com/video/BV1wy4y1D7JT/?p=52 "52 052_尚硅谷react教程_一个简单的Hello组件_Duration-38Min")

    *   [ ] [53 053\_尚硅谷react教程\_样式的模块化\_Duration-5Min](https://www.bilibili.com/video/BV1wy4y1D7JT/?p=53 "53 053_尚硅谷react教程_样式的模块化_Duration-5Min")

    *   [ ] [54 054\_尚硅谷react教程\_vscode中react插件的安装\_Duration-6Min](https://www.bilibili.com/video/BV1wy4y1D7JT/?p=54 "54 054_尚硅谷react教程_vscode中react插件的安装_Duration-6Min")

    *   [ ] [55 055\_尚硅谷\_react教程\_组件化编码流程\_Duration-13Min](https://www.bilibili.com/video/BV1wy4y1D7JT/?p=55 "55 055_尚硅谷_react教程_组件化编码流程_Duration-13Min")

    *   [ ] [56 056\_尚硅谷\_react教程\_TodoList案例\_静态组件\_Duration-24Min](https://www.bilibili.com/video/BV1wy4y1D7JT/?p=56 "56 056_尚硅谷_react教程_TodoList案例_静态组件_Duration-24Min")

    *   [ ] [57 057\_尚硅谷\_react教程\_TodoList案例\_动态初始化列表\_Duration-20Min](https://www.bilibili.com/video/BV1wy4y1D7JT/?p=57 "57 057_尚硅谷_react教程_TodoList案例_动态初始化列表_Duration-20Min")

    *   [ ] [58 058\_尚硅谷\_react教程\_TodoList案例\_添加todo\_Duration-24Min](https://www.bilibili.com/video/BV1wy4y1D7JT/?p=58 "58 058_尚硅谷_react教程_TodoList案例_添加todo_Duration-24Min")

    *   [ ] [59 059\_尚硅谷\_react教程\_TodoList案例\_鼠标移入效果\_Duration-8Min](https://www.bilibili.com/video/BV1wy4y1D7JT/?p=59 "59 059_尚硅谷_react教程_TodoList案例_鼠标移入效果_Duration-8Min")

    *   [ ] [60 060\_尚硅谷\_react教程\_TodoList案例\_添加一个todo\_Duration-15Min](https://www.bilibili.com/video/BV1wy4y1D7JT/?p=60 "60 060_尚硅谷_react教程_TodoList案例_添加一个todo_Duration-15Min")

    *   [ ] [61 061\_尚硅谷\_react教程\_TodoList案例\_对props进行限制\_Duration-5Min](https://www.bilibili.com/video/BV1wy4y1D7JT/?p=61 "61 061_尚硅谷_react教程_TodoList案例_对props进行限制_Duration-5Min")

    *   [ ] [62 062\_尚硅谷\_react教程\_TodoList案例\_删除一个todo\_Duration-12Min](https://www.bilibili.com/video/BV1wy4y1D7JT/?p=62 "62 062_尚硅谷_react教程_TodoList案例_删除一个todo_Duration-12Min")

    *   [ ] [63 063\_尚硅谷\_react教程\_TodoList案例\_实现底部功能\_Duration-25Min](https://www.bilibili.com/video/BV1wy4y1D7JT/?p=63 "63 063_尚硅谷_react教程_TodoList案例_实现底部功能_Duration-25Min")

    *   [ ] [64 064\_尚硅谷\_react教程\_TodoList案例\_总结TodoList案例\_Duration-5Min](https://www.bilibili.com/video/BV1wy4y1D7JT/?p=64 "64 064_尚硅谷_react教程_TodoList案例_总结TodoList案例_Duration-5Min")

    *   [ ] [65 065\_尚硅谷\_react教程\_脚手架配置代理\_方法1\_Duration-27Min](https://www.bilibili.com/video/BV1wy4y1D7JT/?p=65 "65 065_尚硅谷_react教程_脚手架配置代理_方法1_Duration-27Min")

    *   [ ] [66 066\_尚硅谷\_react教程\_脚手架配置代理\_方法2\_Duration-26Min](https://www.bilibili.com/video/BV1wy4y1D7JT/?p=66 "66 066_尚硅谷_react教程_脚手架配置代理_方法2_Duration-26Min")

    *   [ ] [67 067\_尚硅谷\_react教程\_github搜索案例\_静态组件\_Duration-19Min](https://www.bilibili.com/video/BV1wy4y1D7JT/?p=67 "67 067_尚硅谷_react教程_github搜索案例_静态组件_Duration-19Min")

    *   [ ] [68 068\_尚硅谷\_react教程\_github搜索案例\_axios发送请求\_Duration-26Min](https://www.bilibili.com/video/BV1wy4y1D7JT/?p=68 "68 068_尚硅谷_react教程_github搜索案例_axios发送请求_Duration-26Min")

    *   [ ] [69 069\_尚硅谷\_react教程\_github搜索案例\_展示数据\_Duration-12Min](https://www.bilibili.com/video/BV1wy4y1D7JT/?p=69 "69 069_尚硅谷_react教程_github搜索案例_展示数据_Duration-12Min")

    *   [ ] [70 070\_尚硅谷\_react教程\_github搜索案例\_完成案例\_Duration-20Min](https://www.bilibili.com/video/BV1wy4y1D7JT/?p=70 "70 070_尚硅谷_react教程_github搜索案例_完成案例_Duration-20Min")

    *   [ ] [71 071\_尚硅谷\_react教程\_消息订阅与发布技\_pubsub\_Duration-28Min](https://www.bilibili.com/video/BV1wy4y1D7JT/?p=71 "71 071_尚硅谷_react教程_消息订阅与发布技_pubsub_Duration-28Min")

    *   [ ] [72 072\_尚硅谷\_react教程\_fetch发送请求\_Duration-47Min](https://www.bilibili.com/video/BV1wy4y1D7JT/?p=72 "72 072_尚硅谷_react教程_fetch发送请求_Duration-47Min")

    *   [ ] [73 073\_尚硅谷\_react教程\_总结github搜索案例\_Duration-3Min](https://www.bilibili.com/video/BV1wy4y1D7JT/?p=73 "73 073_尚硅谷_react教程_总结github搜索案例_Duration-3Min")

    *   [ ] [74 074\_尚硅谷\_react教程\_对SPA应用的理解\_Duration-13Min](https://www.bilibili.com/video/BV1wy4y1D7JT/?p=74 "74 074_尚硅谷_react教程_对SPA应用的理解_Duration-13Min")

    *   [ ] [75 075\_尚硅谷\_react教程\_对路由的理解\_Duration-11Min](https://www.bilibili.com/video/BV1wy4y1D7JT/?p=75 "75 075_尚硅谷_react教程_对路由的理解_Duration-11Min")

    *   [ ] [76 076\_尚硅谷\_react教程\_前端路由原理\_Duration-23Min](https://www.bilibili.com/video/BV1wy4y1D7JT/?p=76 "76 076_尚硅谷_react教程_前端路由原理_Duration-23Min")

    *   [ ] [77 077\_尚硅谷\_react教程\_路由的基本使用\_Duration-44Min](https://www.bilibili.com/video/BV1wy4y1D7JT/?p=77 "77 077_尚硅谷_react教程_路由的基本使用_Duration-44Min")

    *   [ ] [78 078\_尚硅谷\_react教程\_路由组件与一般组件\_Duration-20Min](https://www.bilibili.com/video/BV1wy4y1D7JT/?p=78 "78 078_尚硅谷_react教程_路由组件与一般组件_Duration-20Min")

    *   [ ] [79 079\_尚硅谷\_react教程\_NavLink的使用\_Duration-6Min](https://www.bilibili.com/video/BV1wy4y1D7JT/?p=79 "79 079_尚硅谷_react教程_NavLink的使用_Duration-6Min")

    *   [ ] [80 080\_尚硅谷\_react教程\_封装NavLink组件\_Duration-19Min](https://www.bilibili.com/video/BV1wy4y1D7JT/?p=80 "80 080_尚硅谷_react教程_封装NavLink组件_Duration-19Min")

    *   [ ] [81 081\_尚硅谷\_react教程\_Switch的使用\_Duration-8Min](https://www.bilibili.com/video/BV1wy4y1D7JT/?p=81 "81 081_尚硅谷_react教程_Switch的使用_Duration-8Min")

    *   [ ] [82 082\_尚硅谷\_react教程\_解决样式丢失问题\_Duration-25Min](https://www.bilibili.com/video/BV1wy4y1D7JT/?p=82 "82 082_尚硅谷_react教程_解决样式丢失问题_Duration-25Min")

    *   [ ] [83 083\_尚硅谷\_react教程\_路由的模糊匹配与严格匹配\_Duration-11Min](https://www.bilibili.com/video/BV1wy4y1D7JT/?p=83 "83 083_尚硅谷_react教程_路由的模糊匹配与严格匹配_Duration-11Min")

    *   [ ] [84 084\_尚硅谷\_react教程\_Redirect的使用\_Duration-7Min](https://www.bilibili.com/video/BV1wy4y1D7JT/?p=84 "84 084_尚硅谷_react教程_Redirect的使用_Duration-7Min")

    *   [ ] [85 085\_尚硅谷\_react教程\_嵌套路由\_Duration-28Min](https://www.bilibili.com/video/BV1wy4y1D7JT/?p=85 "85 085_尚硅谷_react教程_嵌套路由_Duration-28Min")

    *   [ ] [86 086\_尚硅谷\_react教程\_向路由组件传递params参数\_Duration-28Min](https://www.bilibili.com/video/BV1wy4y1D7JT/?p=86 "86 086_尚硅谷_react教程_向路由组件传递params参数_Duration-28Min")

    *   [ ] [87 087\_尚硅谷\_react教程\_向路由组件传递search参数\_Duration-16Min](https://www.bilibili.com/video/BV1wy4y1D7JT/?p=87 "87 087_尚硅谷_react教程_向路由组件传递search参数_Duration-16Min")

    *   [ ] [88 088\_尚硅谷\_react教程\_向路由组件传递state参数\_Duration-18Min](https://www.bilibili.com/video/BV1wy4y1D7JT/?p=88 "88 088_尚硅谷_react教程_向路由组件传递state参数_Duration-18Min")

    *   [ ] [89 089\_尚硅谷\_react教程\_总结路由参数\_Duration-2Min](https://www.bilibili.com/video/BV1wy4y1D7JT/?p=89 "89 089_尚硅谷_react教程_总结路由参数_Duration-2Min")

    *   [ ] [90 090\_尚硅谷\_react教程\_push与repalce\_Duration-7Min](https://www.bilibili.com/video/BV1wy4y1D7JT/?p=90 "90 090_尚硅谷_react教程_push与repalce_Duration-7Min")

    *   [ ] [91 091\_尚硅谷\_react教程\_编程式路由导航\_Duration-24Min](https://www.bilibili.com/video/BV1wy4y1D7JT/?p=91 "91 091_尚硅谷_react教程_编程式路由导航_Duration-24Min")

    *   [ ] [92 092\_尚硅谷\_react教程\_withRouter的使用\_Duration-11Min](https://www.bilibili.com/video/BV1wy4y1D7JT/?p=92 "92 092_尚硅谷_react教程_withRouter的使用_Duration-11Min")

    *   [ ] [93 093\_尚硅谷\_react教程\_BrowserRouter与HashRouter\_Duration-7Min](https://www.bilibili.com/video/BV1wy4y1D7JT/?p=93 "93 093_尚硅谷_react教程_BrowserRouter与HashRouter_Duration-7Min")

    *   [ ] [94 094\_尚硅谷\_react教程\_antd的基本使用\_Duration-31Min](https://www.bilibili.com/video/BV1wy4y1D7JT/?p=94 "94 094_尚硅谷_react教程_antd的基本使用_Duration-31Min")

    *   [ ] [95 095\_尚硅谷\_react教程\_antd样式的按需引入\_Duration-22Min](https://www.bilibili.com/video/BV1wy4y1D7JT/?p=95 "95 095_尚硅谷_react教程_antd样式的按需引入_Duration-22Min")

    *   [ ] [96 096\_尚硅谷\_react教程\_antd自定义主题\_Duration-16Min](https://www.bilibili.com/video/BV1wy4y1D7JT/?p=96 "96 096_尚硅谷_react教程_antd自定义主题_Duration-16Min")

    *   [ ] [97 097\_尚硅谷\_react教程\_redux简介\_Duration-16Min](https://www.bilibili.com/video/BV1wy4y1D7JT/?p=97 "97 097_尚硅谷_react教程_redux简介_Duration-16Min")

    *   [ ] [98 098\_尚硅谷\_react教程\_redux工作流程\_Duration-36Min](https://www.bilibili.com/video/BV1wy4y1D7JT/?p=98 "98 098_尚硅谷_react教程_redux工作流程_Duration-36Min")

    *   [ ] [99 099\_尚硅谷\_react教程\_求和案例\_纯react版\_Duration-19Min](https://www.bilibili.com/video/BV1wy4y1D7JT/?p=99 "99 099_尚硅谷_react教程_求和案例_纯react版_Duration-19Min")

    *   [ ] [100 100\_尚硅谷\_react教程\_求和案例\_redux精简版\_Duration-53Min](https://www.bilibili.com/video/BV1wy4y1D7JT/?p=100 "100 100_尚硅谷_react教程_求和案例_redux精简版_Duration-53Min")

    *   [ ] [101 101\_尚硅谷\_react教程\_求和案例\_redux完整版\_Duration-20Min](https://www.bilibili.com/video/BV1wy4y1D7JT/?p=101 "101 101_尚硅谷_react教程_求和案例_redux完整版_Duration-20Min")

    *   [ ] [102 102\_尚硅谷\_react教程\_求和案例\_异步action版\_Duration-35Min](https://www.bilibili.com/video/BV1wy4y1D7JT/?p=102 "102 102_尚硅谷_react教程_求和案例_异步action版_Duration-35Min")

    *   [ ] [103 103\_尚硅谷\_react教程\_对react-redux的理解\_Duration-8Min](https://www.bilibili.com/video/BV1wy4y1D7JT/?p=103 "103 103_尚硅谷_react教程_对react-redux的理解_Duration-8Min")

    *   [ ] [104 104\_尚硅谷\_react教程\_连接容器组件与UI组件\_Duration-22Min](https://www.bilibili.com/video/BV1wy4y1D7JT/?p=104 "104 104_尚硅谷_react教程_连接容器组件与UI组件_Duration-22Min")

    *   [ ] [105 105\_尚硅谷\_react教程\_react-redux基本使用\_Duration-46Min](https://www.bilibili.com/video/BV1wy4y1D7JT/?p=105 "105 105_尚硅谷_react教程_react-redux基本使用_Duration-46Min")

    *   [ ] [106 106\_尚硅谷\_react教程\_优化1\_简写mapDispatch\_Duration-20Min](https://www.bilibili.com/video/BV1wy4y1D7JT/?p=106 "106 106_尚硅谷_react教程_优化1_简写mapDispatch_Duration-20Min")

    *   [ ] [107 107\_尚硅谷\_react教程\_优化2\_Provider组件的使用\_Duration-13Min](https://www.bilibili.com/video/BV1wy4y1D7JT/?p=107 "107 107_尚硅谷_react教程_优化2_Provider组件的使用_Duration-13Min")

    *   [ ] [108 108\_尚硅谷\_react教程\_优化3\_整合UI组件与容器组件\_Duration-27Min](https://www.bilibili.com/video/BV1wy4y1D7JT/?p=108 "108 108_尚硅谷_react教程_优化3_整合UI组件与容器组件_Duration-27Min")

    *   [ ] [109 109\_尚硅谷\_react教程\_数据共享\_编写Person组件\_Duration-14Min](https://www.bilibili.com/video/BV1wy4y1D7JT/?p=109 "109 109_尚硅谷_react教程_数据共享_编写Person组件_Duration-14Min")

    *   [ ] [110 110\_尚硅谷\_react教程\_数据共享\_编写Person组件的reducer\_Duration-13Min](https://www.bilibili.com/video/BV1wy4y1D7JT/?p=110 "110 110_尚硅谷_react教程_数据共享_编写Person组件的reducer_Duration-13Min")

    *   [ ] [111 111\_尚硅谷\_react教程\_数据共享\_完成数据共享\_Duration-33Min](https://www.bilibili.com/video/BV1wy4y1D7JT/?p=111 "111 111_尚硅谷_react教程_数据共享_完成数据共享_Duration-33Min")

    *   [ ] [112 112\_尚硅谷\_react教程\_纯函数\_Duration-18Min](https://www.bilibili.com/video/BV1wy4y1D7JT/?p=112 "112 112_尚硅谷_react教程_纯函数_Duration-18Min")

    *   [ ] [113 113\_尚硅谷\_react教程\_redux开发者工具\_Duration-14Min](https://www.bilibili.com/video/BV1wy4y1D7JT/?p=113 "113 113_尚硅谷_react教程_redux开发者工具_Duration-14Min")

    *   [ ] [114 114\_尚硅谷\_react教程\_最终版\_Duration-23Min](https://www.bilibili.com/video/BV1wy4y1D7JT/?p=114 "114 114_尚硅谷_react教程_最终版_Duration-23Min")

    *   [ ] [115 115\_尚硅谷\_react教程\_项目打包运行\_Duration-7Min](https://www.bilibili.com/video/BV1wy4y1D7JT/?p=115 "115 115_尚硅谷_react教程_项目打包运行_Duration-7Min")

    *   [ ] [116 116\_尚硅谷\_react教程\_扩展1\_setState\_Duration-26Min](https://www.bilibili.com/video/BV1wy4y1D7JT/?p=116 "116 116_尚硅谷_react教程_扩展1_setState_Duration-26Min")

    *   [ ] [117 117\_尚硅谷\_react教程\_扩展2\_lazyLoad\_Duration-20Min](https://www.bilibili.com/video/BV1wy4y1D7JT/?p=117 "117 117_尚硅谷_react教程_扩展2_lazyLoad_Duration-20Min")

    *   [ ] [118 118\_尚硅谷\_react教程\_扩展3\_stateHook\_Duration-18Min](https://www.bilibili.com/video/BV1wy4y1D7JT/?p=118 "118 118_尚硅谷_react教程_扩展3_stateHook_Duration-18Min")

    *   [ ] [119 119\_尚硅谷\_react教程\_扩展4\_EffectHook\_Duration-21Min](https://www.bilibili.com/video/BV1wy4y1D7JT/?p=119 "119 119_尚硅谷_react教程_扩展4_EffectHook_Duration-21Min")

    *   [ ] [120 120\_尚硅谷\_react教程\_扩展5\_RefHook\_Duration-4Min](https://www.bilibili.com/video/BV1wy4y1D7JT/?p=120 "120 120_尚硅谷_react教程_扩展5_RefHook_Duration-4Min")

    *   [ ] [121 121\_尚硅谷\_react教程\_扩展6\_Fragment\_Duration-6Min](https://www.bilibili.com/video/BV1wy4y1D7JT/?p=121 "121 121_尚硅谷_react教程_扩展6_Fragment_Duration-6Min")

    *   [ ] [122 122\_尚硅谷\_react教程\_扩展7\_Context\_Duration-26Min](https://www.bilibili.com/video/BV1wy4y1D7JT/?p=122 "122 122_尚硅谷_react教程_扩展7_Context_Duration-26Min")

    *   [ ] [123 123\_尚硅谷\_react教程\_扩展8\_PureComponent\_Duration-44Min](https://www.bilibili.com/video/BV1wy4y1D7JT/?p=123 "123 123_尚硅谷_react教程_扩展8_PureComponent_Duration-44Min")

    *   [ ] [124 124\_尚硅谷\_react教程\_扩展9\_renderProps\_Duration-25Min](https://www.bilibili.com/video/BV1wy4y1D7JT/?p=124 "124 124_尚硅谷_react教程_扩展9_renderProps_Duration-25Min")

    *   [ ] [125 125\_尚硅谷\_react教程\_扩展10\_ErrorBoundary\_Duration-31Min](https://www.bilibili.com/video/BV1wy4y1D7JT/?p=125 "125 125_尚硅谷_react教程_扩展10_ErrorBoundary_Duration-31Min")

    *   [ ] [126 126\_尚硅谷\_react教程\_组件间通信方式总结\_Duration-6Min](https://www.bilibili.com/video/BV1wy4y1D7JT/?p=126 "126 126_尚硅谷_react教程_组件间通信方式总结_Duration-6Min")

    *   [ ] [127 127\_尚硅谷\_ReactRouter6教程\_课程说明\_Duration-4Min](https://www.bilibili.com/video/BV1wy4y1D7JT/?p=127 "127 127_尚硅谷_ReactRouter6教程_课程说明_Duration-4Min")

    *   [ ] [128 128\_尚硅谷\_ReactRouter6教程\_一级路由\_Duration-14Min](https://www.bilibili.com/video/BV1wy4y1D7JT/?p=128 "128 128_尚硅谷_ReactRouter6教程_一级路由_Duration-14Min")

    *   [ ] [129 129\_尚硅谷\_ReactRouter6教程\_重定向\_Duration-10Min](https://www.bilibili.com/video/BV1wy4y1D7JT/?p=129 "129 129_尚硅谷_ReactRouter6教程_重定向_Duration-10Min")

    *   [ ] [130 130\_尚硅谷\_ReactRouter6教程\_NavLink高亮\_Duration-6Min](https://www.bilibili.com/video/BV1wy4y1D7JT/?p=130 "130 130_尚硅谷_ReactRouter6教程_NavLink高亮_Duration-6Min")

    *   [ ] [131 131\_尚硅谷\_ReactRouter6教程\_useRoutes路由表\_Duration-6Min](https://www.bilibili.com/video/BV1wy4y1D7JT/?p=131 "131 131_尚硅谷_ReactRouter6教程_useRoutes路由表_Duration-6Min")

    *   [ ] [132 132\_尚硅谷\_ReactRouter6教程\_嵌套路由\_Duration-12Min](https://www.bilibili.com/video/BV1wy4y1D7JT/?p=132 "132 132_尚硅谷_ReactRouter6教程_嵌套路由_Duration-12Min")

    *   [ ] [133 133\_尚硅谷\_ReactRouter6教程\_路由的params参数\_Duration-12Min](https://www.bilibili.com/video/BV1wy4y1D7JT/?p=133 "133 133_尚硅谷_ReactRouter6教程_路由的params参数_Duration-12Min")

    *   [ ] [134 134\_尚硅谷\_ReactRouter6教程\_路由的search参数\_Duration-9Min](https://www.bilibili.com/video/BV1wy4y1D7JT/?p=134 "134 134_尚硅谷_ReactRouter6教程_路由的search参数_Duration-9Min")

    *   [ ] [135 135\_尚硅谷\_ReactRouter6教程\_路由的state参数\_Duration-4Min](https://www.bilibili.com/video/BV1wy4y1D7JT/?p=135 "135 135_尚硅谷_ReactRouter6教程_路由的state参数_Duration-4Min")

    *   [ ] [136 136\_尚硅谷\_ReactRouter6教程\_编程式路由导航\_Duration-12Min](https://www.bilibili.com/video/BV1wy4y1D7JT/?p=136 "136 136_尚硅谷_ReactRouter6教程_编程式路由导航_Duration-12Min")

    *   [ ] [137 137\_尚硅谷\_ReactRouter6教程\_useInRouterContext\_Duration-3Min](https://www.bilibili.com/video/BV1wy4y1D7JT/?p=137 "137 137_尚硅谷_ReactRouter6教程_useInRouterContext_Duration-3Min")

    *   [ ] [138 138\_尚硅谷\_ReactRouter6教程\_useNavigationType\_Duration-2Min](https://www.bilibili.com/video/BV1wy4y1D7JT/?p=138 "138 138_尚硅谷_ReactRouter6教程_useNavigationType_Duration-2Min")

    *   [ ] [139 139\_尚硅谷\_ReactRouter6教程\_useOutlet\_Duration-1Min](https://www.bilibili.com/video/BV1wy4y1D7JT/?p=139 "139 139_尚硅谷_ReactRouter6教程_useOutlet_Duration-1Min")

    *   [ ] [140 140\_尚硅谷\_ReactRouter6教程\_useOutletuseResolvedPath\_Duration-1Min](https://www.bilibili.com/video/BV1wy4y1D7JT/?p=140 "140 140_尚硅谷_ReactRouter6教程_useOutletuseResolvedPath_Duration-1Min")

    *   [ ] [141 141\_尚硅谷\_ReactRouter6教程\_总结\_Duration-6Min](https://www.bilibili.com/video/BV1wy4y1D7JT/?p=141 "141 141_尚硅谷_ReactRouter6教程_总结_Duration-6Min")
