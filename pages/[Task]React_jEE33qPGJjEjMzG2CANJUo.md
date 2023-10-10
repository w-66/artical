# \[Task]React

| 标签   |                         |
| ---- | ----------------------- |
| Date | 2022/11/29 → 2023/05/07 |
| 类型   | 前端,技术                   |

-   尚硅谷Reactv16.8教程（2022加更，B站超火react教程）(2429m)(40h) \[[\[Web\]React](\[Web]React_h3XfA4SNWf9ohgsZECjLr3.md "\[Web]React")] <2022-11-29-2023-05-07>
    -   package.json
        ```react&#x20;jsx
        {
          "name": "react_app",
          "version": "0.1.0",
          "private": true,
          "dependencies": {
            "@ant-design/icons": "^5.0.1",
            "@reduxjs/toolkit": "^1.9.5",
            "@testing-library/jest-dom": "^5.16.5",
            "@testing-library/react": "^13.4.0",
            "@testing-library/user-event": "^13.5.0",
            "antd": "^5.4.6",
            "axios": "^1.3.6",
            "big-integer": "^1.6.51",
            "prop-types": "^15.8.1",
            "pubsub-js": "^1.9.4",
            "query-string": "^8.1.0",
            "react": "^18.2.0",
            "react-dom": "^18.2.0",
            "react-redux": "^8.0.5",
            "react-router-dom": "^5.3.4",
            "react-scripts": "5.0.1",
            "react-thunk": "^1.0.0",
            "redux": "^4.2.1",
            "redux-devtools-extension": "^2.13.9",
            "web-vitals": "^2.1.4"
          },
          "scripts": {
            "start": "react-scripts start",
            "build": "react-scripts build",
            "test": "react-scripts test",
            "eject": "react-scripts eject"
          },
          "eslintConfig": {
            "extends": [
              "react-app",
              "react-app/jest"
            ]
          },
          "browserslist": {
            "production": [
              ">0.2%",
              "not dead",
              "not op_mini all"
            ],
            "development": [
              "last 1 chrome version",
              "last 1 firefox version",
              "last 1 safari version"
            ]
          },
          "devDependencies": {
            "@types/react-router-dom": "^5.3.3"
          }
        }

        ```
    🔳🔳🔳🔳🔳🔳🔳🔳🔳🔳 100%
    -   [x] [1 001\_尚硅谷react教程\_react简介\_Duration-27Min](https://www.bilibili.com/video/BV1wy4y1D7JT/?p=1 "1 001_尚硅谷react教程_react简介_Duration-27Min")
    -   [x] [2 002\_尚硅谷react教程\_hello\_react案例\_Duration-25Min](https://www.bilibili.com/video/BV1wy4y1D7JT/?p=2 "2 002_尚硅谷react教程_hello_react案例_Duration-25Min")|示例：入门第一例,引入react，并显示在页面
        -   旧版本依赖包

            [react.development.js](../file/react.development_9_cBwt7MJ9.js "react.development.js")

            [react-dom.development.js](../file/react-dom.development_KGs93ch4yK.js "react-dom.development.js")

            [babel.min.js](../file/babel.min_d0Qb5JbguR.js "babel.min.js")

            [prop-types.js](../file/prop-types_bMAkp1dhH7.js "prop-types.js")
    -   [x] [3 003\_尚硅谷react教程\_虚拟DOM的两种创建方式\_Duration-12Min](https://www.bilibili.com/video/BV1wy4y1D7JT/?p=3 "3 003_尚硅谷react教程_虚拟DOM的两种创建方式_Duration-12Min")|示例：入门第一例,引入react，并显示在页面|`()`·
        -   \[笔记]003虚拟DOM创建方式
            -   示例：入门第一例,引入react，并显示在页面
                -   示例：1/2按顺序引入react 组件 \[[\[HTML\]type](\[HTML]type_8dPVbusmjqyEZkzawtPbbT.md "\[HTML]type")`text/javascript`] [¶](https://www.bilibili.com/video/BV1wy4y1D7JT?t=742.1\&p=2 "¶")
                    -   旧版本依赖包

                        [react.development.js](../file/react.development_9_cBwt7MJ9.js "react.development.js")

                        [react-dom.development.js](../file/react-dom.development_KGs93ch4yK.js "react-dom.development.js")

                        [babel.min.js](../file/babel.min_d0Qb5JbguR.js "babel.min.js")

                        [prop-types.js](../file/prop-types_bMAkp1dhH7.js "prop-types.js")
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
                -   示例：2/2创建**虚拟DOM**，渲染虚拟DOM到页面 \[[\[HTML\]type](\[HTML]type_8dPVbusmjqyEZkzawtPbbT.md "\[HTML]type")`text/babel`,[\[React\]虚拟DOM](\[React]虚拟DOM_Snd6fanVfJeXQdXpbDqd8.md "\[React]虚拟DOM")]
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
                    -   方式1：创建虚拟DOM使用[\[React\]JSX](\[React]JSX_s6YqU4tzdiXR9faUSdiKqB.md "\[React]JSX")
                        -   v1
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
                        -   v1：`()`创建虚拟DOM时，可换行写HTML \[]
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
                    -   方式2：创建虚拟DOM使用[JavaScript](JavaScript_w7M7UmgSNLmfSHDWMLjuEi.md "JavaScript")(不推荐，不方便多层标签嵌套)[¶](https://www.bilibili.com/video/BV1wy4y1D7JT?t=387.1\&p=3 "¶")

                        ![](../image/image_MpGW5ks2FM.png)

                        ![](../image/image_MLtb4_O7zF.png)
                    -   效果

                        ![](../image/image_rP4c9wbJoX.png)
                        -   \[E]报错`babel.min.js:24 You are using the in-browser Babel transformer. Be sure to precompile your scripts for production `&#x20;

                            前期暂时这样

                            ![](../image/image_hqnnG4xn4j.png)

                            [¶](https://www.bilibili.com/video/BV1wy4y1D7JT?t=1244.0\&p=2 "¶")


    -   [x] [4 004\_尚硅谷react教程\_虚拟DOM与真实DOM\_Duration-6Min](https://www.bilibili.com/video/BV1wy4y1D7JT/?p=4 "4 004_尚硅谷react教程_虚拟DOM与真实DOM_Duration-6Min")|[\[React\]虚拟DOM](\[React]虚拟DOM_Snd6fanVfJeXQdXpbDqd8.md "\[React]虚拟DOM")
        -   \[笔记][虚拟DOM与真实DOM](https://www.bilibili.com/video/BV1wy4y1D7JT/?p=4 "虚拟DOM与真实DOM")

            ![](../image/image_ymkT7DQTSX.png)
    -   [x] [5 005\_尚硅谷react教程\_jsx语法规则\_Duration-26Min](https://www.bilibili.com/video/BV1wy4y1D7JT/?p=5 "5 005_尚硅谷react教程_jsx语法规则_Duration-26Min")|JSX语法规则
        -   \[笔记]jsx语法规则

            ![](../image/image_oAucCdLsVP.png)
            -
                > 示例知识点：Django模板语法 \[`{% verbatim %}`]
                -   v1：JavaScript中变量传参
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
                    ![](../image/image_ecP-5b8D0A.png)
                -   v2：外部添加样式，虚拟DOM中设置样式(内联样式) \[`style`]

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
                    ![](../image/image_krQmrJRD6K.png)
                -   v3：其他语法：示例知识点：只有一个根标签,标签必须闭合 ,标签首字母&#x20;
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
    -   [x] [6 006\_尚硅谷react教程\_jsx小练习\_Duration-22Min](https://www.bilibili.com/video/BV1wy4y1D7JT/?p=6 "6 006_尚硅谷react教程_jsx小练习_Duration-22Min")
        -   \[笔记]JSX小练习

            ![](../image/image_-etTaHX7RL.png)
            -   示例： JSX小练习：动态的展示如下列表 \[[\[React\]虚拟DOM](\[React]虚拟DOM_Snd6fanVfJeXQdXpbDqd8.md "\[React]虚拟DOM"),箭头函数,`Array.map()`]

                ![](../image/image_40jPG_bEwQ.png)

                ![](../image/image_GELdFV60vA.png)


    -   [x] [7 007\_尚硅谷react教程\_组件与模块\_Duration-8Min](https://www.bilibili.com/video/BV1wy4y1D7JT/?p=7 "7 007_尚硅谷react教程_组件与模块_Duration-8Min")|[\[React\]组件与属性](\[React]组件与属性_tc8jMTUd6Mm5ypAX4XU8bv.md "\[React]组件与属性")
        -   \[笔记]组件与模块介绍

            ![](../image/image_euBqLl1IM5.png)
    -   [x] [8 008\_尚硅谷react教程\_开发者工具的安装\_Duration-6Min](https://www.bilibili.com/video/BV1wy4y1D7JT/?p=8 "8 008_尚硅谷react教程_开发者工具的安装_Duration-6Min")|[React Developer Tools](<React Developer Tools_kCZQ3ZEZBaRSzsX64FefUy.md> "React Developer Tools")
    -   [x] [9 009\_尚硅谷react教程\_函数式组件\_Duration-17Min](https://www.bilibili.com/video/BV1wy4y1D7JT/?p=9 "9 009_尚硅谷react教程_函数式组件_Duration-17Min")|React面向\[React]组件编程|函数式组件|babel默认开启严格模式 \[严格模式]
        -   \[笔记]函数式组件

            ![](../image/image_DfmsBbeftN.png)
    -   [x] [10 010\_尚硅谷react教程\_复习类相关知识\_Duration-27Min](https://www.bilibili.com/video/BV1wy4y1D7JT/?p=10 "10 010_尚硅谷react教程_复习类相关知识_Duration-27Min")|\[JS]继承:`extends`,`super()`[¶](https://www.bilibili.com/video/BV1wy4y1D7JT?t=1039.6\&p=10 "¶"),重写从父类继承来的方法[¶](https://www.bilibili.com/video/BV1wy4y1D7JT?t=1333.7\&p=10 "¶")|
        -   \[笔记][复习类相关知识](https://www.bilibili.com/video/BV1wy4y1D7JT/?p=10 "复习类相关知识")

            ![](../image/image_vlN5lspocM.png)
            -   示例：\[React:函数式组件] \[Django:Django 模板文件,\[Dj]模板继承]
                > 写好了Django的路由与视图
                ***
                -   示例：1/2 Django模板文件`react_import_tmplate.html`，按顺序引入React的JavaScript文件 \[[📄 react.development.js](../file/react.development_3MDG7vLco8.js "📄 react.development.js"),[📄 react-dom.development.js](../file/react-dom.development_gnUZqaGJ9P.js "📄 react-dom.development.js"),[📄 babel.min.js](../file/babel.min_adaWvS1ZCQ.js "📄 babel.min.js")]
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
                -   示例：2/2Django模板继承`learn_react_05.html`
                    ```javascript
                    {% extends 'react_import_tmplate.html' %}

                    {% block title %}函数式组件{% endblock %}
                    {% block h2 %}函数式组件{% endblock %}

                     {% block content %} 
                     
                     { % endblock %}
                    ```
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
                -   \[笔记]函数式组件

                    ![](../image/image_DfmsBbeftN.png)
    -   [x] [11 011\_尚硅谷react教程\_类式组件\_Duration-17Min](https://www.bilibili.com/video/BV1wy4y1D7JT/?p=11 "11 011_尚硅谷react教程_类式组件_Duration-17Min")|类式组件
        -   \[笔记]类式组件
            -   示例：构建第个类式组件 \[类式组件`React.Component``ReactDOM.render()`]
                -   示例：1/2 Django模板文件`react_import_tmplate.html`，按顺序引入React的JavaScript文件 \[[📄 react.development.js](../file/react.development_j1dFfNF7ix.js "📄 react.development.js"),[📄 react-dom.development.js](../file/react-dom.development_PEneVCa6Hf.js "📄 react-dom.development.js"),[📄 babel.min.js](../file/babel.min_He5qxQitwm.js "📄 babel.min.js")]
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
                ![](../image/image_YFmZBubM59.png)
    -   [x] [12 012\_尚硅谷react教程\_对state的理解\_Duration-6Min](https://www.bilibili.com/video/BV1wy4y1D7JT/?p=12 "12 012_尚硅谷react教程_对state的理解_Duration-6Min")|组件实例的三大核心属性state简介
    -   [x] [13 013\_尚硅谷react教程\_初始化state\_Duration-13Min](https://www.bilibili.com/video/BV1wy4y1D7JT/?p=13 "13 013_尚硅谷react教程_初始化state_Duration-13Min")
        -   \[笔记]初始化state
            -   示例： \[React:state,`ReactDOM.render()`] \[JS:`constructor`,`extends`,`super()`,`this`]
                -   示例：初始化state v1：设置状态属性
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
                -   示例：初始化state v2：调用状态属性 \[`条件表达式?表达式1:表达式2;`]
                    -   v1
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
                    -   v2：将值变成变量，方便调用
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
                -   示例：state的简写方式v2 精简 \[类式组件] \[箭头函数[¶](https://www.bilibili.com/video/BV1wy4y1D7JT?t=831.8\&p=18 "¶")]
                    > 箭头函数没有自己的this，它的this由外层作用域决定，和它调用方式无关
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
    -   [x] [14 014\_尚硅谷react教程\_react中的事件绑定\_Duration-12Min](https://www.bilibili.com/video/BV1wy4y1D7JT/?p=14 "14 014_尚硅谷react教程_react中的事件绑定_Duration-12Min")|\[JS]事件绑定|React事件绑定
        -   \[笔记]React中的事件绑定
            -   示例：1/2 JavaScript原生事件绑定：点击按钮弹窗展示\[JS]事件绑定 \[`.getElementById()`,`.addEventListener()`,`onclick`,`alert()`]
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

            -   示例：2/2 React事件绑定
                -   可以在React中使用原生JS但是不推荐

                    ![](../image/image_7A-pIt6s4P.png)




                -   示例：React事件绑定，推荐方式&#x20;
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
                                    return <h3  onClick={demo} >今天天气很{isHot ? '炎热' : '凉快'}！</h3>
                                }
                            }
                            ReactDOM.render(<Weather/>, document.getElementById('text'))
                             function demo(){
                                alert('被点击') 
                            }
                        </script>
                    {% endblock %}
                    ```

    -   [x] [15 015\_尚硅谷react教程\_类中方法中的this\_Duration-23Min](https://www.bilibili.com/video/BV1wy4y1D7JT/?p=15 "15 015_尚硅谷react教程_类中方法中的this_Duration-23Min")|`this`?|
    -   [x] [16 016\_尚硅谷react教程\_解决类中this指向问题\_Duration-8Min](https://www.bilibili.com/video/BV1wy4y1D7JT/?p=16 "16 016_尚硅谷react教程_解决类中this指向问题_Duration-8Min")|`this`,`.bind()`,`.hsetState()`
        -   \[笔记]解决类中的this指向问题
            -   &#x20;示例： \[`this`,`.bind()`]

                ![](../image/image_XzjXPsFYOb.png)
    -   [x] [17 017\_尚硅谷react教程\_setState的使用\_Duration-19Min](https://www.bilibili.com/video/BV1wy4y1D7JT/?p=17 "17 017_尚硅谷react教程_setState的使用_Duration-19Min")
        -   \[笔记]：setState的使用 \[`setState()`]

            ![](../image/image_BM5K9MzS9j.png)
            -   示例：state的简写方式v1点击替换文字 \[`.hsetState()`]

                ![](../image/image_ulV1UyAUWa.png)

                ![](../image/image_AdlGJ1EjPs.png)
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

    -   [x] [18 018\_尚硅谷react教程\_state的简写方式\_Duration-18Min](https://www.bilibili.com/video/BV1wy4y1D7JT/?p=18 "18 018_尚硅谷react教程_state的简写方式_Duration-18Min")|类式组件
        -   \[笔记]：state的简写方式
            -   示例：state的简写方式v1点击替换文字 \[`.hsetState()`]

                ![](../image/image_ulV1UyAUWa.png)

                ![](../image/image_AdlGJ1EjPs.png)
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

            -   示例：state的简写方式v2 精简 \[类式组件] \[箭头函数[¶](https://www.bilibili.com/video/BV1wy4y1D7JT?t=831.8\&p=18 "¶")]
                > 箭头函数没有自己的this，它的this由外层作用域决定，和它调用方式无关
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
    -   [x] [19 019\_尚硅谷react教程\_总结state\_Duration-4Min](https://www.bilibili.com/video/BV1wy4y1D7JT/?p=19 "19 019_尚硅谷react教程_总结state_Duration-4Min")|state
        -   \[笔记]总结state

            ![](../image/image_VGs7aG0SDw.png)
    -   [x] [20 020\_尚硅谷react教程\_props的基本使用\_Duration-10Min](https://www.bilibili.com/video/BV1wy4y1D7JT/?p=20 "20 020_尚硅谷react教程_props的基本使用_Duration-10Min")|props
        -   \[笔记]props的基本使用
            -   示例：props的基本使用 \[props] \[解构赋值]

                ![](../image/image_73gKEHvqRI.png)

                ![](../image/image_N5Bs0qtcdi.png)
                -   v1：基础的使用
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
                -   v2  修改一点：使用解构赋值
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
                -   示例：v3v2  修改一点：使用解构赋值改进：props批量传递 \[\[JS]展开运算符 \[`...`]:展开对象]
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

    -   [x] [21 021\_尚硅谷react教程\_批量传递props\_Duration-17Min](https://www.bilibili.com/video/BV1wy4y1D7JT/?p=21 "21 021_尚硅谷react教程_批量传递props_Duration-17Min")|props
        -   \[笔记]
            -   示例：v3v2  修改一点：使用解构赋值改进：props批量传递 \[\[JS]展开运算符 \[`...`]:展开对象]
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

    -   [x] [22 022\_尚硅谷react教程\_对props进行限制\_Duration-23Min](https://www.bilibili.com/video/BV1wy4y1D7JT/?p=22 "22 022_尚硅谷react教程_对props进行限制_Duration-23Min")||**`PropTypes`**`PropType.number`,`PropType.func`,`PropType.string`,`.isRequired`,**`defaultProps`**
        -   \[笔记]对props进行限制 \[[\[JS库\]prop-type](\[JS库]prop-type_ji55v62TxKVe1hhx4LE1Tp.md "\[JS库]prop-type")]
            -   示例：对props传递的属性进行限制，想让age在页面中加1但是实际age不变，以及名字只能是字符串且非空; 否则将报错。年龄为空，默认为18 \[props,**`PropTypes`**`PropType.string`,`.isRequired`,**`defaultProps`**]
                -   v1：数据类型是字符串，显示错误
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
                    ![](../image/image_rurqMd3bMp.png)
                -   v2：解决办法：age在页面中加1但是实际age不变

                    ![](../image/image_EIiG16dX4m.png)
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
                -   v3：需要增加新的js文件 用于限制组件标签属性限制，模板文件：react\_import\_tmplate.html \[[📄 prop-types.js](../file/prop-types_MyFtvj9tFQ.js "📄 prop-types.js")][¶](https://www.bilibili.com/video/BV1wy4y1D7JT?t=837.9\&p=22 "¶")
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

                -   v4：限制传输的数据类型 名字只能是字符串且非空
                    -   正常代码&#x20;
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
                    -   \[E]错误代码 指定为字符串，传入数字的报错
                        -   错误代码
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
                                    const p = { name:111 ,age:20,weight:'50kg'}
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
                        ![](../image/image_3VeEnNwSot.png)
                    -   \[E]错误代码 指定属性非空，传入空
                        -   误code
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
                        ![](../image/image_Eg8jbZcHv5.png)
                -   v5：年龄为空，默认为18

                    ![](../image/image_Z9aI8eEIKm.png)
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
                                name:PropTypes.string.isRequired,  // 限制为，name只能是字符串类型且必须传，否则将报错
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
    -   [x] [23 023\_尚硅谷react教程\_props的简写方式\_Duration-8Min](https://www.bilibili.com/video/BV1wy4y1D7JT/?p=23 "23 023_尚硅谷react教程_props的简写方式_Duration-8Min")|
        -   \[笔记]props简写方式：通过静态方法static \[**`PropTypes`****`defaultProps`**,props属性|参数只读，原因被冻结了¶||静态方法`static`|state[¶](https://www.bilibili.com/video/BV1wy4y1D7JT?t=517.1\&p=23 "¶")]
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
                            name:PropTypes.string.isRequired,  // 限制为，name只能是字符串类型且必须传，否则将报错
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
    -   [x] [24 024\_尚硅谷ract教程\_类式组件中的构造器与props\_Duration-10Min](https://www.bilibili.com/video/BV1wy4y1D7JT/?p=24 "24 024_尚硅谷ract教程_类式组件中的构造器与props_Duration-10Min")|`constructor`,构造方法中的props|几乎用不到
        -   \[笔记][类式组件中的构造器与props](https://www.bilibili.com/video/BV1wy4y1D7JT/?p=24 "类式组件中的构造器与props")

            结论：构造方法中的props能省则省
            -   截图

                ![](../image/image_IqS73RtvaI.png)
    -   [x] [25 025\_尚硅谷react教程\_函数式组件使用props\_Duration-8Min](https://www.bilibili.com/video/BV1wy4y1D7JT/?p=25 "25 025_尚硅谷react教程_函数式组件使用props_Duration-8Min")
        -   \[笔记]
            -   示例：函数式组件传输props属性中的值，以及对props属性进行限制 \[`ReactDOM.render()`,,`...`,函数式组件]

                ![](../image/image_dIZGQO4Lyv.png)
                ```javascript
                {% extends 'react_import_tmplate.html' %}

                {% block title %}函数式组件的props{% endblock %}
                {% block h2 %}函数式组件的props{% endblock %}

                {% block content %}
                    <!-- 创建容器 -->
                    <div id="text"></div>

                    <script type="text/babel">
                        function Person( props ){
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
                        ReactDOM.render(<Person  {...p} />, document.getElementById('text'))
                    </script>
                {% endblock %}
                ```
                ![](../image/image_LD9sbrZp_6.png)
    -   [x] [26 026\_尚硅谷react教程\_总结props\_Duration-4Min](https://www.bilibili.com/video/BV1wy4y1D7JT/?p=26 "26 026_尚硅谷react教程_总结props_Duration-4Min")
    -   [x] [27 027\_尚硅谷react教程\_字符串形式的ref\_Duration-15Min](https://www.bilibili.com/video/BV1wy4y1D7JT/?p=27 "27 027_尚硅谷react教程_字符串形式的ref_Duration-15Min")
        -   \[笔记]
            -   示例：方式1/3字符串形式的ref(不推荐) \[refs] \[]

                ![](../image/image_YjflV1NH0i.png)
                ```javascript
                <script type="text/babel">
                    class Demo_refs extends React.Component {
                        showData = ()=>{
                            // console.log(this.refs)           // {input1: input}
                            // console.log(this.refs.input1)    // <input ref="input1" placeholder="点击弹出弹窗警告" />
                            const {input1} =  this.refs        // 解构赋值，从refs中
                            // console.log(input1.value)        // 获取inpute1里面value的值
                            // console.log(input1.placeholder)  // 获取inpute1里面placeholder的值
                            alert(input1.value)              // 点击事件：弹窗中显示左侧输入框的值
                        }
                        showData2 = ()=>{
                            // console.log('失去焦点')
                            const {input2} =  this.refs       // 解构
                            alert(input2.value)             // 弹窗
                        }
                        render() {
                            return (
                                <div>
                                    <div>
                                        <input  ref="input1"  placeholder="点击右边按钮弹窗" />
                                        <button onClick={this.showData}>点击弹出左侧输入框的数据</button>
                                        <input  ref="input2"  onBlur={this.showData2} type="text" placeholder="失去焦点弹出提示" />
                                    </div>                    
                                </div>
                            )
                        }
                    }
                    ReactDOM.render(<Demo_refs/>, document.getElementById('text'))
                </script>
                ```
    -   [x] [28 028\_尚硅谷react教程\_回调形式的ref\_Duration-14Min](https://www.bilibili.com/video/BV1wy4y1D7JT/?p=28 "28 028_尚硅谷react教程_回调形式的ref_Duration-14Min")
        -   \[笔记]
            -   示例：方式2/3回调(箭头函数)参数形式的ref \[refs] \[,箭头函数回调函数]
                ```javascript
                <div id="text2"></div>

                <script type="text/babel">
                    class Demo_refs extends React.Component {
                        showData = ()=>{
                            const  {input3} = this             // 解构赋值，从refs中
                            alert(input3.value)              // 点击事件：弹窗中显示左侧输入框的值
                        }
                        showData2 = ()=>{
                            const  {input4} = this       // 解构
                            alert(input4.value)             // 弹窗
                        }
                        render() {
                            return (
                                <div>
                                    <div>
                                        <input  ref={(a) => {this.input3 = a}}  placeholder="点击右边按钮弹窗" title="把ref当前所处的节点，挂在了实例自身上，并命名为input3;  一句话,把真实dom节点存到了实例属性中了"/> 
                                        <button onClick={this.showData}>点击弹出左侧输入框的数据</button>
                                        <input  ref={b => this.input4 =b}  onBlur={this.showData2} type="text" placeholder="失去焦点弹出提示" title="简写箭头函数" />
                                    </div>
                                </div>
                            )
                        }
                    }
                    ReactDOM.render(<Demo_refs/>, document.getElementById('text2'))
                </script>
                ```
    -   [x] [29 029\_尚硅谷react教程\_回调ref中调用次数的问题\_Duration-18Min](https://www.bilibili.com/video/BV1wy4y1D7JT/?p=29 "29 029_尚硅谷react教程_回调ref中调用次数的问题_Duration-18Min")
        -   \[笔记]
            -   示例：不使用内联方式，回调函数 \[refs,箭头函数回调函数]

                ![](../image/image_e1CJ6ECFR-.png)

                ![](../image/image_PkVZMseOcZ.png)
    -   [x] [30 030\_尚硅谷react教程\_createRef的使用\_Duration-8Min](https://www.bilibili.com/video/BV1wy4y1D7JT/?p=30 "30 030_尚硅谷react教程_createRef的使用_Duration-8Min")
        -   \[笔记]
            -   示例：方式3/3 api参数形式的ref(推荐) \[refs] \[]
                ```javascript
                <div id="text3"></div>

                <script type="text/babel">
                    class Demo_refs3 extends React.Component {
                         myRef1 = React.createRef() 
                         myRef2 = React.createRef() 

                        showData = ()=>{
                            alert( this.myRef1.current.value )          // 点击事件：弹窗中显示左侧输入框的值
                        }
                        showData2 = ()=>{
                           alert( this.myRef2.current.value )
                        }
                        render() {
                            return (
                                <div>
                                    <div>
                                        <input  ref={this.myRef1}  placeholder="点击右边按钮弹窗"/> 
                                        <button onClick={this.showData}>点击弹出左侧输入框的数据</button>
                                        <input  ref={this.myRef2}  onBlur={this.showData2} type="text" placeholder="失去焦点弹出提示"/>
                                    </div>
                                </div>
                            )
                        }
                    }
                    ReactDOM.render(<Demo_refs3/>, document.getElementById('text3'))

                </script>
                ```



    -   [x] [31 031\_尚硅谷react教程\_总结ref\_Duration-3Min](https://www.bilibili.com/video/BV1wy4y1D7JT/?p=31 "31 031_尚硅谷react教程_总结ref_Duration-3Min")
    -   [x] [32 032\_尚硅谷react教程\_react中的事件处理\_Duration-8Min](https://www.bilibili.com/video/BV1wy4y1D7JT/?p=32 "32 032_尚硅谷react教程_react中的事件处理_Duration-8Min")
        -   \[笔记]
            -   示例：发生事件的元素正好是你操作的元素则可以省略ref \[refs]

                ![](../image/image_yniusP4esD.png)

                ![](../image/image_XUpZXycVhK.png)
    -   [x] [33 033\_尚硅谷react教程\_非受控组件\_Duration-13Min](https://www.bilibili.com/video/BV1wy4y1D7JT/?p=33 "33 033_尚硅谷react教程_非受控组件_Duration-13Min")
        -   \[笔记]
            -   示例：定义一个包含表单的组件，输入用户名密码之后，点击登录提示输入信息 \[收集表单数据,非受控组件,refs方式2/3回调(箭头函数)参数形式的ref \[],\[HTML]onsubmit]
                ```javascript
                <div id="demo12"></div>

                <script type="text/babel">
                    class Login extends React.Component{
                        showInput = (event) =>{
                            event.preventDefault()
                            const {username, password} = this
                            alert(`登录用户：${username.value}，登录密码：${password.value}`)
                        }
                        render(){
                            return (
                                <form action="" onSubmit={this.showInput}>
                                    用户<input ref={input1 => this.username = input1} type="text" name='username'/>
                                    密码<input ref={input2 => this.password = input2} type="password" name='password'/>
                                    <button>Login</button>
                                </form>
                            )
                        }
                    }
                    ReactDOM.render(<Login/>, document.getElementById('demo12'))
                </script>

                ```
    -   [x] [34 034\_尚硅谷react教程\_受控组件\_Duration-10Min](https://www.bilibili.com/video/BV1wy4y1D7JT/?p=34 "34 034_尚硅谷react教程_受控组件_Duration-10Min")
        -   \[笔记]
            -   示例：定义一个包含表单的组件，输入用户名密码之后，点击登录提示输入信息，通过state存储用户与密码 \[受控组件,state`setState()`,可以省略refs的设置(推荐),\[HTML]onChange]
                ```javascript
                <!-- 受控组件 -->
                <script type="text/babel">
                    class Login extends React.Component{
                        state = {  // 定义state的初始化状态(默认值)
                            username: '',
                            password: ''
                        }
                        showInput = (event) =>{
                            event.preventDefault()
                            // console.log(this.state)    // {username: '1', password: '2'}
                            const {username, password} = this.state
                            alert(`登录用户：${username}，登录密码：${password}`)

                        }
                         saveUsername = (event) =>{
                            // console.log(event.target.value)  // 通过onChange事件，触发回调函数(这里)，输出输入框中正在输入的值
                            this.setState({username:event.target.value})
                        } 
                        savePassword = (event) =>{
                            this.setState({password:event.target.value})
                        }
                        render(){
                            return (
                                <form action="" onSubmit={this.showInput}>
                                    用户<input  onChange={this.saveUsername}  type="text" name='username'/>
                                    密码<input onChange={this.savePassword} type="password" name='password'/>
                                    <button>Login</button>
                                </form>
                            )
                        }
                    }
                    ReactDOM.render(<Login/>, document.getElementById('demo13'))
                </script>
                ```
                在 React 中，事件处理函数中的 event 参数是一个合成事件对象。它是 React 封装的浏览器原生事件对象的跨浏览器包装器，提供了与原生事件相同的属性和方法。您可以在事件处理函数中使用该对象来访问事件相关信息，如 event.target 表示事件的目标元素，event.preventDefault() 可以阻止默认行为等。
            -   示例：优化上一课的代码：将方法改成一个，统一处理，表单变化 \[高级函数\[JS]高阶函数：函数柯里化[¶](https://www.bilibili.com/video/BV1wy4y1D7JT?t=1419.8\&p=35 "¶")]
    -   [x] [35 035\_尚硅谷react教程\_高阶函数\_函数柯里化\_Duration-26Min](https://www.bilibili.com/video/BV1wy4y1D7JT/?p=35 "35 035_尚硅谷react教程_高阶函数_函数柯里化_Duration-26Min")
        -   \[笔记]
            -   示例：优化上一课的代码：将方法改成一个，统一处理，表单变化 \[高级函数\[JS]高阶函数：函数柯里化[¶](https://www.bilibili.com/video/BV1wy4y1D7JT?t=1419.8\&p=35 "¶")]

                ![](../image/image_6cF8k6FNyR.png)

                ![](../image/image_82TPKmJcow.png)
                ```javascript
                <!-- 受控组件 示例优化 -->
                <script type="text/babel">
                    class Login3 extends React.Component {
                        state = {  // 定义state的初始化状态(默认值)
                            username: '',
                            password: ''
                        }
                        showInput = (event) => {
                            event.preventDefault()
                            // console.log(this.state)    // {username: '1', password: '2'}
                            const { username, password } = this.state
                            alert(`登录用户：${username}，登录密码：${password}`)

                        }
                         saveFormData = (dataType) =>{    // 高阶函数：函数柯里化
                            // console.log(dataType)    // 输出类型
                             return ()=>{ 
                                // console.log(dataType,event.target.value)     // 获取输出的类型与输入框的值 username 123 password 1
                                 this.setState({[dataType]:event.target.value})   // 设置state的值，输入什么类型的表单，就state就存储什么类型的值
                             } 
                         } 
                        render() {
                            return (
                                <form action="" onSubmit={this.showInput}>
                                    用户<input  onChange={this.saveFormData('username')}  type="text" name='username' />
                                    密码<input  onChange={this.saveFormData('password')}  type="password" name='password' />
                                    <button>Login</button>
                                </form>
                            )
                        }
                    }
                    ReactDOM.render(<Login3 />, document.getElementById('demo14'))
                </script>
                ```
                ![](../image/image_6L0Y7V-HaU.png)
    -   [x] [36 036\_尚硅谷react教程\_不用柯里化的写法\_Duration-6Min](https://www.bilibili.com/video/BV1wy4y1D7JT/?p=36 "36 036_尚硅谷react教程_不用柯里化的写法_Duration-6Min")
        -   \[笔记]

            ![](../image/image_PlPMu2yTsg.png)
    -   [x] [37 037\_尚硅谷react教程\_引出生命周期\_Duration-39Min](https://www.bilibili.com/video/BV1wy4y1D7JT/?p=37 "37 037_尚硅谷react教程_引出生命周期_Duration-39Min")
        -   \[笔记]
            -   旧版本生命周期流程图(v16)

                ![](../image/image_FgEUlQW-5U.png)

                ![](../image/react生命周期\(旧\)_99TBCI8wXa.png)
            -   示例：[¶](https://www.bilibili.com/video/BV1wy4y1D7JT?t=2091.4\&p=37 "¶")标签透明度自动递减，直到透明，然后出现，循环，点击按钮卸载组件 \[[\[React\]生命周期](\[React]生命周期_daGsiUspap6JwY68rVudND.md "\[React]生命周期"),`componentDidMount()``componentWillUnmount()`,state,`{%verbatim%}`,`setInterval()``clearInterval()`]

                ![](../image/2023-23-15-2023_N4eXQ0Qf6T.gif)
                ```javascript
                <div id="demo1"></div>

                <script type="text/babel">
                    class Life extends React.Component{
                        state = {opacity:1}
                        price = ()=>{
                            // clearInterval(this.timer)  // 卸载组件之前需要先清除定时器，因为不然会报错，无法更新已经卸载的组件
                            ReactDOM.unmountComponentAtNode(document.getElementById('demo1')) // 点击卸载组件
                        }
                        // 组件挂在完毕之后调用一次
                         componentDidMount() {
                            this.timer = setInterval(() => {
                                // 获取原状态
                                let {opacity} = this.state
                                opacity -= 0.1  // 每次减一
                                // 判断如果opacity小于等于0，则设置opacity为1(重置)
                                if(opacity <= 0) opacity = 1
                                // 设置实际的透明度(状态中)
                                console.log(opacity)
                                this.setState({opacity:opacity})
                            }, 200);
                        }
                         componentWillUnmount() {
                            clearInterval(this.timer)  // 卸载组件之前需要先清除定时器，因为不然会报错，无法更新已经卸载的组件
                        }

                        render(){
                            return(
                                <div>
                                    <div style={{opacity:this.state.opacity}}>my life!</div>
                                    <button onClick={this.price}>一键发财，代价是什么?</button>
                                </div>
                            )
                        }
                    }
                    ReactDOM.render(<Life/>, document.getElementById('demo1'))
                </script>
                ```

    -   [x] [38 038\_尚硅谷react教程\_生命周期(旧)\_组件挂载流程\_Duration-14Min](https://www.bilibili.com/video/BV1wy4y1D7JT/?p=38 "38 038_尚硅谷react教程_生命周期(旧)_组件挂载流程_Duration-14Min")
        -   \[笔记]

            ![](../image/image_51Ri0Xyuvl.png)


            -   示例： 声明周期了解 \[`componentWillMount()``componentDidMount()``componentWillUnmount()`,`shouldComponentUpdate()``componentWillUpdate()``componentDidUpdate()`,`forceUpdate()`]

                ![](../image/image_EpUI0WerWq.png)
                -   第一部分

                    ![](../image/image_6rUo2wDDpO.png)
                -   第二部分，setState()，shouldComponentUpdate()，componentWillUpdate()，componentDidUpdate()



                    ![](../image/image_V620VxEtxg.png)

                    ![](../image/image_y9WbAMME0S.png)
                -   第三部分，forceUpdate()，componentWillUpdate()，componentDidUpdate()[¶](https://www.bilibili.com/video/BV1wy4y1D7JT?t=146.4\&p=40 "¶")

                    ![](../image/image_foGd0yND0q.png)
    -   [x] [39 039\_尚硅谷react教程\_生命周期(旧)\_setState流程\_Duration-13Min](https://www.bilibili.com/video/BV1wy4y1D7JT/?p=39 "39 039_尚硅谷react教程_生命周期(旧)_setState流程_Duration-13Min")
        -   \[笔记]
            -   示例： 声明周期了解 \[`componentWillMount()``componentDidMount()``componentWillUnmount()`,`shouldComponentUpdate()``componentWillUpdate()``componentDidUpdate()`,`forceUpdate()`]

                ![](../image/image_EpUI0WerWq.png)
                -   第一部分

                    ![](../image/image_6rUo2wDDpO.png)
                -   第二部分，setState()，shouldComponentUpdate()，componentWillUpdate()，componentDidUpdate()



                    ![](../image/image_V620VxEtxg.png)

                    ![](../image/image_y9WbAMME0S.png)
                -   第三部分，forceUpdate()，componentWillUpdate()，componentDidUpdate()[¶](https://www.bilibili.com/video/BV1wy4y1D7JT?t=146.4\&p=40 "¶")

                    ![](../image/image_foGd0yND0q.png)

    -   [x] [40 040\_尚硅谷react教程\_生命周期(旧)\_forceUpdate流程\_Duration-5Min](https://www.bilibili.com/video/BV1wy4y1D7JT/?p=40 "40 040_尚硅谷react教程_生命周期(旧)_forceUpdate流程_Duration-5Min")
        -   \[笔记]
            -   示例： 声明周期了解 \[`componentWillMount()``componentDidMount()``componentWillUnmount()`,`shouldComponentUpdate()``componentWillUpdate()``componentDidUpdate()`,`forceUpdate()`]

                ![](../image/image_EpUI0WerWq.png)
                -   第一部分

                    ![](../image/image_6rUo2wDDpO.png)
                -   第二部分，setState()，shouldComponentUpdate()，componentWillUpdate()，componentDidUpdate()



                    ![](../image/image_V620VxEtxg.png)

                    ![](../image/image_y9WbAMME0S.png)
                -   第三部分，forceUpdate()，componentWillUpdate()，componentDidUpdate()[¶](https://www.bilibili.com/video/BV1wy4y1D7JT?t=146.4\&p=40 "¶")

                    ![](../image/image_foGd0yND0q.png)
    -   [x] [41 041\_尚硅谷react教程\_生命周期(旧)\_父组件render流程\_Duration-14Min](https://www.bilibili.com/video/BV1wy4y1D7JT/?p=41 "41 041_尚硅谷react教程_生命周期(旧)_父组件render流程_Duration-14Min")&#x20;
        -   \[笔记]
            -   示例：父组件：A组件是B组件的父组件 ，\[`componentWillReceiveProps()`[¶](https://www.bilibili.com/video/BV1wy4y1D7JT?t=367.4\&p=41 "¶")]

                ![](../image/image_YlEvUuPoac.png)

                ![](../image/image_5KDoGhXNoJ.png)
    -   [x] [42 042\_尚硅谷react教程\_总结生命周期(旧)\_Duration-9Min](https://www.bilibili.com/video/BV1wy4y1D7JT/?p=42 "42 042_尚硅谷react教程_总结生命周期(旧)_Duration-9Min")
        -   \[笔记]
            -   新版本生命周期流程图(v17)

                ![](../image/image_CJIyU3jvnv.png)

                ![](../image/react生命周期\(新\)_BN7shXupxS.png)
            ![](../image/image_0Io5FSB1GY.png)


    -   [x] [43 043\_尚硅谷react教程\_对比新旧生命周期\_Duration-31Min](https://www.bilibili.com/video/BV1wy4y1D7JT/?p=43 "43 043_尚硅谷react教程_对比新旧生命周期_Duration-31Min")
    -   [x] [44 044\_尚硅谷react教程\_getDerivedStateFromProps\_Duration-16Min](https://www.bilibili.com/video/BV1wy4y1D7JT/?p=44 "44 044_尚硅谷react教程_getDerivedStateFromProps_Duration-16Min")
        -   \[笔记]
            -   示例：在`getDerivedStateFromProps()`中，state的值以props为主。 \[stateprops]
                ```javascript
                <div id="demo2"></div>
                <script type="text/babel">
                    // 定义组件

                    class AutoSum extends React.Component{
                        // 构造器
                        constructor(props){
                            super(props)
                            console.log('constructor')
                             this.state = {count:0} 
                        }
                        // 初始化状态
                        // 定义加一函数
                        plusOne = ()=>{
                            const {count} = this.state 
                            console.log(count)
                            // count += 1 // state 不能直接修改 值
                            this.setState({count:count+1})
                        }
                        //  
                         static getDerivedStateFromProps(props, state){
                            console.log('getDerivedStateFromProps',props,state)
                            return props
                        } 
                        // 挂载完成
                        componentDidMount(){
                            console.log('componentDidMount')
                        }
                        // 渲染(挂载)
                        render(){
                            const {count} = this.state
                            console.log('render')
                            return(
                                <div>
                                    <p>当前求和：{count}</p>
                                    <button onClick={this.plusOne}>+1</button>
                                </div>
                            )
                        }
                    }
                    // 渲染组件到页面
                    ReactDOM.render(<AutoSum  count='100' />, document.getElementById('demo2'))
                </script>
                ```

    -   [x] [45 045\_尚硅谷react教程\_getSnapshotBeforeUpdate\_Duration-16Min](https://www.bilibili.com/video/BV1wy4y1D7JT/?p=45 "45 045_尚硅谷react教程_getSnapshotBeforeUpdate_Duration-16Min")
        -   \[笔记]
            -   示例：[¶](https://www.bilibili.com/video/BV1wy4y1D7JT?t=922.1\&p=45 "¶")`getSnapshotBeforeUpdate()``componentDidUpdate()`
                ```javascript
                <div id="demo3"></div>

                <script type="text/babel">
                    // 定义组件
                    class AutoSum2 extends React.Component {
                        // 构造器
                        constructor(props) {
                            super(props)
                            console.log('2-constructor')
                            this.state = { count2: 0 }
                        }
                        // 初始化状态
                        // 定义加一函数
                        plusOne = () => {
                            const { count2 } = this.state
                            console.log(count2)
                            // count += 1 // state 不能直接修改 值
                            this.setState({ count2: count2 + 1 })
                        }
                        static getDerivedStateFromProps(props, state) {
                            console.log('2-getDerivedStateFromProps', props, state)
                            return null
                        }
                        // 挂载完成
                        componentDidMount() {
                            console.log('2-componentDidMount')
                        }
                        // 获取更新之前 的快照值
                        getSnapshotBeforeUpdate(){
                            console.log('2-getSnapshotBeforeUpdate')
                            // return null
                            return 123222
                        }
                        // 组件更新完成，可传入两个参数，更新之前的state 与 props 属性的值
                        // componentDidUpdate(a, b, c) {
                        //     console.log('2-componentDidUpdate', a, b, c)
                        // }
                        // // 命名语义化变量参数
                        // # 这里的第三个参数接收来自getSnapshotBeforeUpdate返回的值
                        componentDidUpdate(preState, preProps, prevSnapshot) {
                            console.log('2-componentDidUpdate', preState, preProps, prevSnapshot)
                        }
                        // 渲染(挂载)
                        render() {
                            const { count2 } = this.state
                            console.log('render')
                            return (
                                <div>
                                    <p>当前求和：{count2}</p>
                                    <button onClick={this.plusOne}>+1</button>
                                </div>
                            )
                        }
                    }
                    // 渲染组件到页面
                    ReactDOM.render(<AutoSum2 count='100'/>, document.getElementById('demo3'))

                </script>
                ```
    -   [x] [46 046\_尚硅谷react教程\_getSnapshotBeforeUpdate举例\_Duration-19Min](https://www.bilibili.com/video/BV1wy4y1D7JT/?p=46 "46 046_尚硅谷react教程_getSnapshotBeforeUpdate举例_Duration-19Min")
        -   \[笔记]
            -   示例：新闻条目持续更新，但是当前的滚动条位置不随着更新发生变化\[`getSnapshotBeforeUpdate()``shouldComponentUpdate()`,staterefs`setState()`，`Array.map()`,`componentDidUpdate()`,`.dir()``Element.scrollTop`﻿]
                -   复习dir()，scrollTop 控制滚动

                    ![](../image/image_uDTexEbEwN.png)

                    ![](../image/image_38xbtZ0Jyg.png)

                    ![](../image/image_AEuWUXiWMy.png)
                ![](<../image/2023-23-16-2139 (1)_Py-QXdG1QC.gif>)
                ```react&#x20;jsx
                <div id="demo1"></div>

                <script type="text/babel">
                    class List extends React.Component{
                         state = {newsArray:[]} 
                        componentDidMount(){
                            setInterval(() => {
                                // 获取原状态
                                 const {newsArray} = this.state 
                                // 模拟一条新闻
                                const news = '新闻' + (newsArray.length+1)
                                // 更新状态
                                 this.setState({newsArray:[news,...newsArray]}) 
                                // console.log(newsArray)
                            }, 1000);
                        }
                        getSnapshotBeforeUpdate(){
                            // 返回当前滚动条的整体高度
                             return this.refs.list.scrollHeight 
                        }
                        // componentDidUpdate(preState,perProps,perSnapshot){
                        //     console.log(preState,perProps,perSnapshot)
                        // }
                         componentDidUpdate(preState,perProps,perSnapshot){ 
                            // perSnapshot 为更新前的滚动条整体高度，通过getSnapshotBeforeUpdate取值
                            // this.refs.list.scrollHeight 为更新后的滚动条整体高度
                            // this.refs.list.scrollTop 为更新之后，计算 当前的滚动位置
                             this.refs.list.scrollTop += this.refs.list.scrollHeight - perSnapshot 
                        }
                        render(){
                            return(
                                <div>
                                    {/* 注释
                                    <div className="list list-group m-2">
                                        <a href="#" className="news list-group-item list-group-item-action ">新闻2</a>
                                        <a href="#" className="news list-group-item list-group-item-action ">新闻1</a>
                                    </div>
                                    */}
                                    <div  ref='list'  className="list list-group m-2">
                                        {
                                             this.state.newsArray .map((n, index)=>{  // n是状态中的数组中的每个单独的值 index是遍历之后的唯一值
                                                return <div key={index} className="news list-group-item list-group-item-action">{n}</div>
                                            })
                                        }
                                    </div>
                                </div>
                            )
                        }
                    }
                    ReactDOM.render(<List/>, document.getElementById('demo1'))
                </script>
                ```
                -   \[E]Warning: Each child in a list should have a unique "key" prop. ; 关于其中的map中的index参数，如果不写将报此警告 \[`Array.map()`]
                    ```react&#x20;jsx
                    <div id="demo1"></div>

                    <script type="text/babel">
                        class List extends React.Component{
                             state = {newsArray:[]} 
                            componentDidMount(){
                                setInterval(() => {
                                    // 获取原状态
                                     const {newsArray} = this.state 
                                    // 模拟一条新闻
                                    const news = '新闻' + (newsArray.length+1)
                                    // 更新状态
                                     this.setState({newsArray:[news,...newsArray]}) 
                                    // console.log(newsArray)
                                }, 1000);
                            }
                            getSnapshotBeforeUpdate(){
                                // 返回当前滚动条的整体高度
                                 return this.refs.list.scrollHeight 
                            }
                            // componentDidUpdate(preState,perProps,perSnapshot){
                            //     console.log(preState,perProps,perSnapshot)
                            // }
                             componentDidUpdate(preState,perProps,perSnapshot){ 
                                // perSnapshot 为更新前的滚动条整体高度，通过getSnapshotBeforeUpdate取值
                                // this.refs.list.scrollHeight 为更新后的滚动条整体高度
                                // this.refs.list.scrollTop 为更新之后，计算 当前的滚动位置
                                 this.refs.list.scrollTop += this.refs.list.scrollHeight - perSnapshot 
                            }
                            render(){
                                return(
                                    <div>
                                        {/* 注释
                                        <div className="list list-group m-2">
                                            <a href="#" className="news list-group-item list-group-item-action ">新闻2</a>
                                            <a href="#" className="news list-group-item list-group-item-action ">新闻1</a>
                                        </div>
                                        */}
                                        <div  ref='list'  className="list list-group m-2">
                                            {
                                                 this.state.newsArray .map((n, index)=>{  // n是状态中的数组中的每个单独的值 index是遍历之后的唯一值
                                                    return <div key={index} className="news list-group-item list-group-item-action">{n}</div>
                                                })
                                            }
                                        </div>
                                    </div>
                                )
                            }
                        }
                        ReactDOM.render(<List/>, document.getElementById('demo1'))
                    </script>
                    ```
                    在 React 中，每个组件渲染出来的多个子元素都需要有一个 `key` 属性来区分彼此。这个 `key` 属性不需要是唯一的，但它应该在这个组件的同级子元素之间是唯一的。当我们使用 `map()` 方法渲染一个列表时，我们需要在遍历的子元素中添加 `key` 属性。`key` 属性可以是数组中每个元素的唯一标识，例如它们的 ID 或索引。在这种情况下，`index` 是 `map()` 方法中回调函数的第二个参数，它是当前遍历的元素在数组中的索引值。因此，在 `map()` 方法中，我们通常会将 `key` 属性设置为 `index` 值，以确保每个子元素都有一个唯一的标识符。

                    index 的值从哪里来的?
                    -   `index`：当前元素在数组中的索引

                        在 `map` 方法中，`index` 参数表示当前遍历到的元素在原数组中的索引位置。React 在使用 `map` 方法渲染列表时，通常需要为每个子组件设置一个 `key` 属性，这个属性的值通常设置为对应元素在数组中的索引值，这样 React 就能正确地比较新旧元素，实现高效的更新。因此，`index` 值就是数组中元素的索引位置。
    -   [x] [47 047\_尚硅谷react教程\_总结生命周期(新)\_Duration-4Min](https://www.bilibili.com/video/BV1wy4y1D7JT/?p=47 "47 047_尚硅谷react教程_总结生命周期(新)_Duration-4Min")
        -   \[笔记]

            ![](../image/image_CJIyU3jvnv.png)
    -   [x] [48 048\_尚硅谷react教程\_DOM的diffing算法\_Duration-45Min](https://www.bilibili.com/video/BV1wy4y1D7JT/?p=48 "48 048_尚硅谷react教程_DOM的diffing算法_Duration-45Min")
        -   \[笔记]
            -   \[笔记]✧关于`Array.map()`不推荐使用index作为\[React]key的原因[¶](https://www.bilibili.com/video/BV1wy4y1D7JT?t=1572.5\&p=48 "¶")

                ![](../image/image_7c5VTMSs8B.png)

                ![](../image/image_MB-xThVMY4.png)
            -   示例： \[[Diffing算法](Diffing算法_9pKGYJeH3uP4JfqyBVMBCA.md "Diffing算法")\[React]key,[\[JS\]Date()](\[JS]Date\(\)_aviHL1B2ZveadTcdRofEMR.md "\[JS]Date()")`.toTimeString()`]

                ![](../image/image_MB-xThVMY4.png)


    -   [x] [49 049\_尚硅谷react教程\_初始化react脚手架\_Duration-23Min](https://www.bilibili.com/video/BV1wy4y1D7JT/?p=49 "49 049_尚硅谷react教程_初始化react脚手架_Duration-23Min") \[[Webpack](Webpack_6tozYheuLN7uJtWbcWkoXJ.md "Webpack")
        -   示例：安装[\[React\]create-react-app(脚手架)](\[React]create-react-app\(脚手架\)_iKRevG9qrfgg38wTCrMLDx.md "\[React]create-react-app(脚手架)") \[[npm](npm_6L2ASmevicELg4gRE57X4j.md "npm")`npm start`,Linux]
            -   Linux(Ubuntu)安装npm
                -   apt-get update & apt-get install -y npm
                -   下载并执行 NodeSource 安装脚本：`curl -sL https://deb.nodesource.com/setup_14.x | sudo -E bash -`
                    -   之后就可以下载14版本的node
                        ```react&#x20;jsx
                        apt install nodejs
                        ```
            -   安装create-react-app
                ```react&#x20;jsx
                root@59f6c9bea13b:/www# npm install -g create-react-app
                npm WARN deprecated tar@2.2.2: This version of tar is no longer supported, and will not receive security updates. Please upgrade asap.
                /usr/local/bin/create-react-app -> /usr/local/lib/node_modules/create-react-app/index.js
                npm WARN notsup Unsupported engine for create-react-app@5.0.1: wanted: {"node":">=14"} (current: {"node":"10.19.0","npm":"6.14.4"})
                npm WARN notsup Not compatible with your version of node/npm: create-react-app@5.0.1
                npm WARN notsup Unsupported engine for fs-extra@10.1.0: wanted: {"node":">=12"} (current: {"node":"10.19.0","npm":"6.14.4"})
                npm WARN notsup Not compatible with your version of node/npm: fs-extra@10.1.0

                + create-react-app@5.0.1
                added 67 packages from 27 contributors in 19.649s
                ```
            -   创建项目 `create-react-app react_app`
                ```react&#x20;jsx
                root@59f6c9bea13b:/www# create-react-app react_app

                Creating a new React app in /www/react_app.

                Installing packages. This might take a couple of minutes.
                Installing react, react-dom, and react-scripts with cra-template...


                > core-js@3.30.1 postinstall /www/react_app/node_modules/core-js
                > node -e "try{require('./postinstall')}catch(e){}"


                > core-js-pure@3.30.1 postinstall /www/react_app/node_modules/core-js-pure
                > node -e "try{require('./postinstall')}catch(e){}"

                + cra-template@1.2.0
                + react-scripts@5.0.1
                + react@18.2.0
                + react-dom@18.2.0
                added 1434 packages from 627 contributors in 809.752s

                234 packages are looking for funding
                  run `npm fund` for details


                Initialized a git repository.

                Installing template dependencies using npm...
                npm WARN @apideck/better-ajv-errors@0.3.6 requires a peer of ajv@>=8 but none is installed. You must install peer dependencies yourself.
                npm WARN fork-ts-checker-webpack-plugin@6.5.3 requires a peer of typescript@>= 2.7 but none is installed. You must install peer dependencies yourself.
                npm WARN tsutils@3.21.0 requires a peer of typescript@>=2.8.0 || >= 3.2.0-dev || >= 3.3.0-dev || >= 3.4.0-dev || >= 3.5.0-dev || >= 3.6.0-dev || >= 3.6.0-beta || >= 3.7.0-dev || >= 3.7.0-beta but none is installed. You must install peer dependencies yourself.
                npm WARN optional SKIPPING OPTIONAL DEPENDENCY: fsevents@2.3.2 (node_modules/fsevents):
                npm WARN notsup SKIPPING OPTIONAL DEPENDENCY: Unsupported platform for fsevents@2.3.2: wanted {"os":"darwin","arch":"any"} (current: {"os":"linux","arch":"x64"})

                + web-vitals@2.1.4
                + @testing-library/jest-dom@5.16.5
                + @testing-library/react@13.4.0
                + @testing-library/user-event@13.5.0
                added 55 packages from 81 contributors in 57.666s

                234 packages are looking for funding
                  run `npm fund` for details

                Removing template package using npm...

                npm WARN @apideck/better-ajv-errors@0.3.6 requires a peer of ajv@>=8 but none is installed. You must install peer dependencies yourself.
                npm WARN fork-ts-checker-webpack-plugin@6.5.3 requires a peer of typescript@>= 2.7 but none is installed. You must install peer dependencies yourself.
                npm WARN tsutils@3.21.0 requires a peer of typescript@>=2.8.0 || >= 3.2.0-dev || >= 3.3.0-dev || >= 3.4.0-dev || >= 3.5.0-dev || >= 3.6.0-dev || >= 3.6.0-beta || >= 3.7.0-dev || >= 3.7.0-beta but none is installed. You must install peer dependencies yourself.
                npm WARN optional SKIPPING OPTIONAL DEPENDENCY: fsevents@2.3.2 (node_modules/fsevents):
                npm WARN notsup SKIPPING OPTIONAL DEPENDENCY: Unsupported platform for fsevents@2.3.2: wanted {"os":"darwin","arch":"any"} (current: {"os":"linux","arch":"x64"})

                removed 1 package and audited 1489 packages in 30.359s

                234 packages are looking for funding
                  run `npm fund` for details

                found 1 high severity vulnerability
                  run `npm audit fix` to fix them, or `npm audit` for details

                Created git commit.

                Success! Created react_app at /www/react_app
                Inside that directory, you can run several commands:

                  npm start
                    Starts the development server.

                  npm run build
                    Bundles the app into static files for production.

                  npm test
                    Starts the test runner.

                  npm run eject
                    Removes this tool and copies build dependencies, configuration files
                    and scripts into the app directory. If you do this, you can’t go back!

                We suggest that you begin by typing:

                  cd react_app
                  npm start

                Happy hacking!
                ```
            -   启动 `npm start`
                ```react&#x20;jsx
                Compiled successfully!

                You can now view react_app in the browser.

                  Local:            http://localhost:3000
                  On Your Network:  http://10.0.3.3:3000

                Note that the development build is not optimized.
                To create a production build, use npm run build.

                webpack compiled successfully

                ```

    -   [x] [50 050\_尚硅谷react教程\_脚手架文件介绍\_public\_Duration-30Min](https://www.bilibili.com/video/BV1wy4y1D7JT/?p=50 "50 050_尚硅谷react教程_脚手架文件介绍_public_Duration-30Min")
        -   \[笔记]创建项目中文件解析[index.html](index.html_oXFx66fQXLz7A9RnU9pr87.md "index.html")

            ![](../image/image_3hlvIZ3ryT.png)

            ![](../image/image_Xc-3gb2d8J.png)

            ![](../image/image_PMoNDvqYoH.png)
    -   [x] [51 051\_尚硅谷react教程\_脚手架文件介绍\_src\_Duration-18Min](https://www.bilibili.com/video/BV1wy4y1D7JT/?p=51 "51 051_尚硅谷react教程_脚手架文件介绍_src_Duration-18Min")
        -   \[笔记]`./src/`[index.js](index.js_6jYd8AoBx9reoEKZN96D5o.md "index.js")[reportWebVitals.js](reportWebVitals.js_6U54hsu8J7S4QuaCdq7QVi.md "reportWebVitals.js"); 执行顺序：>[index.html](index.html_oXFx66fQXLz7A9RnU9pr87.md "index.html")>[App.js](App.js_smsVFfHWYrYu6vAuTn3Ks.md "App.js")[¶](https://www.bilibili.com/video/BV1wy4y1D7JT?t=943.7\&p=51 "¶")


    -   [x] [52 052\_尚硅谷react教程\_一个简单的Hello组件\_Duration-38Min](https://www.bilibili.com/video/BV1wy4y1D7JT/?p=52 "52 052_尚硅谷react教程_一个简单的Hello组件_Duration-38Min") [ES6](ES6_rB5cSLXpPJWFQdqG5dhpnf.md "ES6")>ES6 模块语法
        -   \[笔记]
            -   脚手架中的js代码与组件.js做区分，可以通过两种方式：1、通过首字母大写表示组件来区分 2、通过尾缀改为jsx表示组件来区分&#x20;
    -   [x] [53 053\_尚硅谷react教程\_样式的模块化\_Duration-5Min](https://www.bilibili.com/video/BV1wy4y1D7JT/?p=53 "53 053_尚硅谷react教程_样式的模块化_Duration-5Min")
        -   \[笔记]样式模块化
            -   因为不同组件之间之间import CSS文件会导致相同选择器的相互冲突，所以...
            -   示例：
                -   1、修改组件中的CSS文件为\*.module.css

                    ![](../image/image_c6nPk6ICan.png)
                -   2、导入CSS

                    ![](../image/image_vDepWPYGln.png)
    -   [x] [54 054\_尚硅谷react教程\_vscode中react插件的安装\_Duration-6Min](https://www.bilibili.com/video/BV1wy4y1D7JT/?p=54 "54 054_尚硅谷react教程_vscode中react插件的安装_Duration-6Min")
        -   \[笔记]

            ![](../image/image_77M6jrUO-5.png)
    -   [x] [55 055\_尚硅谷\_react教程\_组件化编码流程\_Duration-13Min](https://www.bilibili.com/video/BV1wy4y1D7JT/?p=55 "55 055_尚硅谷_react教程_组件化编码流程_Duration-13Min")
        -   \[笔记]编码流程(过程)

            ![](../image/image_lXQ74-Bd7s.png)
    -   [x] [56 056\_尚硅谷\_react教程\_TodoList案例\_静态组件\_Duration-24Min](https://www.bilibili.com/video/BV1wy4y1D7JT/?p=56 "56 056_尚硅谷_react教程_TodoList案例_静态组件_Duration-24Min") &#x20;
    -   [x] [57 057\_尚硅谷\_react教程\_TodoList案例\_动态初始化列表\_Duration-20Min](https://www.bilibili.com/video/BV1wy4y1D7JT/?p=57 "57 057_尚硅谷_react教程_TodoList案例_动态初始化列表_Duration-20Min")
        -   \[笔记] \[HTML]defaultChecked[¶](https://www.bilibili.com/video/BV1wy4y1D7JT?t=1105.7\&p=57 "¶")

            ![](../image/image_lnq2W0HFPa.png)
    -   [x] [58 058\_尚硅谷\_react教程\_TodoList案例\_添加todo\_Duration-24Min](https://www.bilibili.com/video/BV1wy4y1D7JT/?p=58 "58 058_尚硅谷_react教程_TodoList案例_添加todo_Duration-24Min")
        -   \[笔记]

            ![](../image/image_U6zBVf7s9p.png)
            -   示例： \[父组件 ←传递参数 ←子组件 [¶](https://www.bilibili.com/video/BV1wy4y1D7JT?t=541.5\&p=58 "¶") ,props,`event`keyCode ,trim()]

                ![](../image/2023-23-20-1903_-bunguCde7.gif)

                ![](../image/image_0ahds6bTfw.png)
                -   示例：src/App.jsx  \[父组件]
                    -   v1：App.jsx： 子组件Header.jsx在输入框中输入的值，将可以传递给父组件App.jsx
                        ```react&#x20;jsx
                        import React, { Component } from 'react'
                        // 我的组件
                        import Header from './component/Header/Header'
                        import List from './component/List/List'
                        import Bottom from './component/Bottom/Bottom'
                        // 我的CSS
                        import './App.css'
                        //
                        export default class App extends Component {
                          // 初始化状态
                          state = {todos:[
                                          {id: '001', name:'吃饭', done:true},
                                          {id: '002', name:'睡觉', done:false},
                                          {id: '003', name:'Codeing', done:false},
                                          {id: '004', name:'学开飞机', done:false},
                                  ]}
                          // 用于添加todo，接收 todo 对象
                           addTodo = (todoObj) => {
                            // 接收来自子组件的数据
                            const {todos} = this.state
                            // console.log(typeof(todos))  // 是个对象object
                            const newTodos = [todoObj, ...todos]

                            this.setState({todos:newTodos})
                          } 

                          render() {
                            const {todos} = this.state
                            return (
                              <div>
                                <div id='totoContainer'>
                                  <Header addTodo={this.addTodo}/>
                                  <List todos={todos}/>
                                  <Bottom />
                                </div>
                              </div>
                            )
                          }
                        }
                        ```
                    -   v2：App.jsx 触摸条目高亮以及，出现删除按钮
                        ```react&#x20;jsx
                        import React, { Component } from 'react'
                        // 我的组件
                        import Header from './component/Header/Header'
                        import List from './component/List/List'
                        import Bottom from './component/Bottom/Bottom'
                        // 我的CSS
                        import './App.css'
                        //
                        export default class App extends Component {
                          // 初始化状态
                          state = {todos:[
                                          {id: '001', name:'吃饭', done:true},
                                          {id: '002', name:'睡觉', done:false},
                                          {id: '003', name:'Codeing', done:false},
                                          {id: '004', name:'学开飞机', done:false},
                                  ]}
                          // 用于添加todo，接收 todo 对象
                          addTodo = (todoObj) => {
                            // 接收来自子组件的数据
                            const {todos} = this.state
                            // console.log(typeof(todos))  // 是个对象object
                            const newTodos = [todoObj, ...todos]

                            this.setState({todos:newTodos})
                          }

                          render() {
                            const {todos} = this.state
                            return (
                              <div>
                                <div id='totoContainer'>
                                  <Header addTodo={this.addTodo}/>
                                  <List todos={todos}/>
                                  <Bottom />
                                </div>
                              </div>
                            )
                          }
                        }

                        ```
                    -   v3：App.jsx孙子组件修改爷爷组件的状态 \[props]
                        ```react&#x20;jsx
                        import React, { Component } from 'react'
                        // 我的组件
                        import Header from './component/Header/Header'
                        import List from './component/List/List'
                        import Bottom from './component/Bottom/Bottom'
                        // 我的CSS
                        import './App.css'
                        //
                        export default class App extends Component {
                          // 初始化状态
                          state = {todos:[
                                          {id: '001', name:'吃饭', done:true},
                                          {id: '002', name:'睡觉', done:false},
                                          {id: '003', name:'Codeing', done:false},
                                          {id: '004', name:'学开飞机', done:false},
                                  ]}
                          // 通过props传递函数，来添加 state 中 todos 的条目
                          addTodo = (todoObj) => {
                            // 接收来自子组件的数据
                            const {todos} = this.state
                            // console.log(typeof(todos))  // 是个对象object
                            const newTodos = [todoObj, ...todos]

                            this.setState({todos:newTodos})
                          }
                           // 通过props传递函数，来修改 state 中 todos 中 done 的值
                          isDone = (id, done)=>{
                            // 获取原状态
                            const {todos} = this.state
                            // 遍历，判断每一条数据的id是否与传入的id相同，如果相同则，修改done的值为传入的done的值，否则不修改
                            // 最后存入newTodos
                            const newTodos = todos.map((i)=>{
                              if (i.id === id) return {...i, done:done}
                              else return i
                            })
                            this.setState({todos:newTodos})
                          } 

                          render() {
                            const {todos} = this.state
                            return (
                              <div>
                                <div id='totoContainer'>
                                  <Header addTodo={this.addTodo}/>
                                  <List todos={todos} isDone={this.isDone}/>
                                  <Bottom />
                                </div>
                              </div>
                            )
                          }
                        }


                        ```
                -   示例：src/component/Header/Header.jsx \[子组件]
                    -   v1：Header.jsx：子组件Header.jsx在输入框中输入的值，将可以传递给父组件App.jsx
                        ```react&#x20;jsx
                        import React, { Component } from 'react'
                        // 导入自定义的雪花ID生成器
                        import SnowFlake from '../../plugin/snowFlake'

                        export default class Header extends Component {

                          handlerKey = (event) => {
                            if (event.keyCode !== 13) return  
                            // 判断输入不能为空  
                             if (event.target.value.trim() === '') {
                              alert('不能为空')
                              return 
                            }
                            // 创建一个todoObj
                            const todoObj = {id:SnowFlake(), name:event.target.value, done:false}
                            // 通过addTodo 发送todoObj数据到父组件
                            this.props.addTodo(todoObj)
                            // 清空输入框
                            event.target.value = '' 
                          }

                          render() {
                            return (
                              <div>
                                <input type="text" onKeyUp={this.handlerKey}/>
                              </div>
                            )
                          }
                        }


                        ```
                -   示例：src/component/List/List.jsx
                    -   v3：List.jsx孙子组件修改爷爷组件的状态
                        ```react&#x20;jsx
                        import React, { Component } from 'react'
                        // my component
                        import Item from '../Item/Item'
                        //
                        export default class List extends Component {

                          render() {
                            const {todos, isDone} = this.props   // 通过App.jsx中定义的props 参数 todos={todos}，传递到了这里，通过解构赋值取出todos
                            return (
                              <div>
                                {
                                  todos.map((todo) => {
                                    return <Item key={todo.id} todo={todo}  isDone={isDone }  />
                                     // isDone 是是通过父类App中的props传过来的，然后将它再传给Item组件实现孙子给爷爷传递数据 
                                  })
                                }
                              </div>
                            )
                          }
                        }
                        ```
                -   示例：src/component/Item/Item.jsx
                    -   v2：Item.jsx触摸条目高亮以及，出现删除按钮
                        ```react&#x20;jsx
                        import React, { Component } from 'react'

                        export default class Item extends Component {
                          //
                          state = {mouse:false}

                          // 
                          handleMouse(flag){
                            return ()=>{
                              this.setState({mouse:flag})
                            }
                          }

                          render() {
                            const {todo} = this.props
                            const ismouse = this.state.mouse
                            return (
                              <div>
                                {
                                  <li style={{backgroundColor:ismouse? '#ddd' : 'white'} } onMouseEnter={this.handleMouse(true)} onMouseLeave={this.handleMouse(false)}>
                                    <label  htmlFor="">
                                      <input type="checkbox" name="" id="" defaultChecked={todo.done}/>
                                      <span>{todo.name} </span>
                                      <span>{todo.id} </span>
                                      <a style={{display:ismouse?'inline':'none'}} href="#" role="button">Del</a>
                                    </label>
                                  </li>
                                }
                              </div>
                            )
                          }
                        }

                        ```
                    -   v3：Item.jsx孙子组件修改爷爷组件的状态
                        ```react&#x20;jsx
                        import React, { Component } from 'react'

                        export default class Item extends Component {
                          // 鼠标移入移出条目状态
                          state = {mouse:false}

                          // 鼠标移入移出条目状态控制
                          handleMouse(flag){
                            return ()=>{
                              this.setState({mouse:flag})
                            }
                          }
                          // todo是否完成
                           handleCheck(id){
                            return (event)=>{
                              console.log(id, event.target.checked)
                              // 从父组件(List)的父组件(App)中传过来的props.isDone参数(函数)
                              this.props.isDone(id, event.target.checked)
                            }
                          } 
                          //
                          render() {
                            const {todo} = this.props
                            const ismouse = this.state.mouse
                            return (
                              <div>
                                {
                                  <li style={{backgroundColor:ismouse? '#ddd' : 'white'} } onMouseEnter={this.handleMouse(true)} onMouseLeave={this.handleMouse(false)}>
                                    <label  htmlFor="">
                                      <input type="checkbox" onChange={this.handleCheck(todo.id)} defaultChecked={todo.done}/>
                                      <span>{todo.name} </span>
                                      <span>{todo.id} </span>
                                      <a style={{display:ismouse?'inline':'none'}} href="#" role="button">Del</a>
                                    </label>
                                  </li>
                                }
                              </div>
                            )
                          }
                        }
                        ```
    -   [x] [59 059\_尚硅谷\_react教程\_TodoList案例\_鼠标移入效果\_Duration-8Min](https://www.bilibili.com/video/BV1wy4y1D7JT/?p=59 "59 059_尚硅谷_react教程_TodoList案例_鼠标移入效果_Duration-8Min")
        -   \[笔记]
            -   示例：`mouseout``mouseenter`\[JS]三元运算符`条件表达式?表达式1:表达式2;`
                -   v2：App.jsx 触摸条目高亮以及，出现删除按钮
                    ```react&#x20;jsx
                    import React, { Component } from 'react'
                    // 我的组件
                    import Header from './component/Header/Header'
                    import List from './component/List/List'
                    import Bottom from './component/Bottom/Bottom'
                    // 我的CSS
                    import './App.css'
                    //
                    export default class App extends Component {
                      // 初始化状态
                      state = {todos:[
                                      {id: '001', name:'吃饭', done:true},
                                      {id: '002', name:'睡觉', done:false},
                                      {id: '003', name:'Codeing', done:false},
                                      {id: '004', name:'学开飞机', done:false},
                              ]}
                      // 用于添加todo，接收 todo 对象
                      addTodo = (todoObj) => {
                        // 接收来自子组件的数据
                        const {todos} = this.state
                        // console.log(typeof(todos))  // 是个对象object
                        const newTodos = [todoObj, ...todos]

                        this.setState({todos:newTodos})
                      }

                      render() {
                        const {todos} = this.state
                        return (
                          <div>
                            <div id='totoContainer'>
                              <Header addTodo={this.addTodo}/>
                              <List todos={todos}/>
                              <Bottom />
                            </div>
                          </div>
                        )
                      }
                    }

                    ```
                -   v2：Item.jsx触摸条目高亮以及，出现删除按钮
                    ```react&#x20;jsx
                    import React, { Component } from 'react'

                    export default class Item extends Component {
                      //
                      state = {mouse:false}

                      // 
                      handleMouse(flag){
                        return ()=>{
                          this.setState({mouse:flag})
                        }
                      }

                      render() {
                        const {todo} = this.props
                        const ismouse = this.state.mouse
                        return (
                          <div>
                            {
                              <li style={{backgroundColor:ismouse? '#ddd' : 'white'} } onMouseEnter={this.handleMouse(true)} onMouseLeave={this.handleMouse(false)}>
                                <label  htmlFor="">
                                  <input type="checkbox" name="" id="" defaultChecked={todo.done}/>
                                  <span>{todo.name} </span>
                                  <span>{todo.id} </span>
                                  <a style={{display:ismouse?'inline':'none'}} href="#" role="button">Del</a>
                                </label>
                              </li>
                            }
                          </div>
                        )
                      }
                    }

                    ```
    -   [x] [60 060\_尚硅谷\_react教程\_TodoList案例\_添加一个todo\_Duration-15Min](https://www.bilibili.com/video/BV1wy4y1D7JT/?p=60 "60 060_尚硅谷_react教程_TodoList案例_添加一个todo_Duration-15Min")
        -   \[笔记]
            -   状态在哪里，操作状态的方法就在哪里
            -   v3：App.jsx孙子组件修改爷爷组件的状态 \[props]
                ```react&#x20;jsx
                import React, { Component } from 'react'
                // 我的组件
                import Header from './component/Header/Header'
                import List from './component/List/List'
                import Bottom from './component/Bottom/Bottom'
                // 我的CSS
                import './App.css'
                //
                export default class App extends Component {
                  // 初始化状态
                  state = {todos:[
                                  {id: '001', name:'吃饭', done:true},
                                  {id: '002', name:'睡觉', done:false},
                                  {id: '003', name:'Codeing', done:false},
                                  {id: '004', name:'学开飞机', done:false},
                          ]}
                  // 通过props传递函数，来添加 state 中 todos 的条目
                  addTodo = (todoObj) => {
                    // 接收来自子组件的数据
                    const {todos} = this.state
                    // console.log(typeof(todos))  // 是个对象object
                    const newTodos = [todoObj, ...todos]

                    this.setState({todos:newTodos})
                  }
                   // 通过props传递函数，来修改 state 中 todos 中 done 的值
                  isDone = (id, done)=>{
                    // 获取原状态
                    const {todos} = this.state
                    // 遍历，判断每一条数据的id是否与传入的id相同，如果相同则，修改done的值为传入的done的值，否则不修改
                    // 最后存入newTodos
                    const newTodos = todos.map((i)=>{
                      if (i.id === id) return {...i, done:done}
                      else return i
                    })
                    this.setState({todos:newTodos})
                  } 

                  render() {
                    const {todos} = this.state
                    return (
                      <div>
                        <div id='totoContainer'>
                          <Header addTodo={this.addTodo}/>
                          <List todos={todos} isDone={this.isDone}/>
                          <Bottom />
                        </div>
                      </div>
                    )
                  }
                }


                ```
            -   v3：List.jsx孙子组件修改爷爷组件的状态
                ```react&#x20;jsx
                import React, { Component } from 'react'
                // my component
                import Item from '../Item/Item'
                //
                export default class List extends Component {

                  render() {
                    const {todos, isDone} = this.props   // 通过App.jsx中定义的props 参数 todos={todos}，传递到了这里，通过解构赋值取出todos
                    return (
                      <div>
                        {
                          todos.map((todo) => {
                            return <Item key={todo.id} todo={todo}  isDone={isDone }  />
                             // isDone 是是通过父类App中的props传过来的，然后将它再传给Item组件实现孙子给爷爷传递数据 
                          })
                        }
                      </div>
                    )
                  }
                }
                ```
            -   v3：Item.jsx孙子组件修改爷爷组件的状态
                ```react&#x20;jsx
                import React, { Component } from 'react'

                export default class Item extends Component {
                  // 鼠标移入移出条目状态
                  state = {mouse:false}

                  // 鼠标移入移出条目状态控制
                  handleMouse(flag){
                    return ()=>{
                      this.setState({mouse:flag})
                    }
                  }
                  // todo是否完成
                   handleCheck(id){
                    return (event)=>{
                      console.log(id, event.target.checked)
                      // 从父组件(List)的父组件(App)中传过来的props.isDone参数(函数)
                      this.props.isDone(id, event.target.checked)
                    }
                  } 
                  //
                  render() {
                    const {todo} = this.props
                    const ismouse = this.state.mouse
                    return (
                      <div>
                        {
                          <li style={{backgroundColor:ismouse? '#ddd' : 'white'} } onMouseEnter={this.handleMouse(true)} onMouseLeave={this.handleMouse(false)}>
                            <label  htmlFor="">
                              <input type="checkbox" onChange={this.handleCheck(todo.id)} defaultChecked={todo.done}/>
                              <span>{todo.name} </span>
                              <span>{todo.id} </span>
                              <a style={{display:ismouse?'inline':'none'}} href="#" role="button">Del</a>
                            </label>
                          </li>
                        }
                      </div>
                    )
                  }
                }
                ```
    -   [x] [61 061\_尚硅谷\_react教程\_TodoList案例\_对props进行限制\_Duration-5Min](https://www.bilibili.com/video/BV1wy4y1D7JT/?p=61 "61 061_尚硅谷_react教程_TodoList案例_对props进行限制_Duration-5Min")
        -   \[笔记]&#x20;
            -   示例：将父组件传递给子组件的props类型进行限制，不符合类型是，将给予警告 \[对props属性进行限制 \[[\[JS库\]prop-type](\[JS库]prop-type_ji55v62TxKVe1hhx4LE1Tp.md "\[JS库]prop-type")]`PropType.func``PropType.array``.isRequired`]
                -   安装[\[JS库\]prop-type](\[JS库]prop-type_ji55v62TxKVe1hhx4LE1Tp.md "\[JS库]prop-type")
                -   对props的类型添加限制
                    -   App
                        ```react&#x20;jsx
                        import React, { Component } from 'react'
                        // 我的组件
                        import Header from './component/Header/Header'
                        import List from './component/List/List'
                        import Bottom from './component/Bottom/Bottom'
                        // 我的CSS
                        import './App.css'
                        //
                        export default class App extends Component {

                          // 初始化状态
                          state = {todos:[
                                          {id: '001', name:'吃饭', done:true},
                                          {id: '002', name:'睡觉', done:false},
                                          {id: '003', name:'Codeing', done:false},
                                          {id: '004', name:'学开飞机', done:false},
                                  ]}
                          // 通过props传递函数，来添加 state 中 todos 的条目
                          addTodo = (todoObj) => {
                            // 接收来自子组件的数据
                            const {todos} = this.state
                            // console.log(typeof(todos))  // 是个对象object
                            const newTodos = [todoObj, ...todos]

                            this.setState({todos:newTodos})
                          }
                          // 通过props传递函数，来修改 state 中 todos 中 done 的值
                          isDone = (id, done)=>{
                            // 获取原状态
                            const {todos} = this.state
                            // 遍历，判断每一条数据的id是否与传入的id相同，如果相同则，修改done的值为传入的done的值，否则不修改
                            // 最后存入newTodos
                            const newTodos = todos.map((i)=>{
                              if (i.id === id) return {...i, done:done}
                              else return i
                            })
                            this.setState({todos:newTodos})
                          }

                          render() {
                            const {todos} = this.state
                            return (
                              <div>
                                <div id='totoContainer'>
                                  <Header  addTodo={this.addTodo} />
                                  <List  todos={todos} isDone={this.isDone} />
                                  <Bottom />
                                </div>
                              </div>
                            )
                          }
                        }
                        ```
                    -   Header
                        ```react&#x20;jsx
                        import React, { Component } from 'react'
                         import PropTypes from 'prop-types' 
                        // 导入自定义的雪花ID生成器
                        import SnowFlake from '../../plugin/snowFlake'


                        export default class Header extends Component {
                           // 限制 props 参数，从父组件传入的必须是一个函数
                          static propTypes = {
                            addTodo:PropTypes.func.isRequired
                          } 
                          handlerKey = (event) => {
                            if (event.keyCode !== 13) return  
                            // 判断输入不能为空  
                            if (event.target.value.trim() === '') {
                              alert('不能为空')
                              return 
                            }
                            // 创建一个todoObj 对象
                            const todoObj = {id:SnowFlake(), name:event.target.value, done:false}
                            // 通过addTodo 发送todoObj数据到父组件
                            this.props.addTodo(todoObj)
                            // 清空输入框
                            event.target.value = ''
                          }

                          render() {
                            return (
                              <div>
                                <input type="text" onKeyUp={this.handlerKey}/>
                              </div>
                            )
                          }
                        }
                        ```
                    -   List
                        ```react&#x20;jsx
                        import React, { Component } from 'react'
                         import PropTypes from 'prop-types'  
                        // my component
                        import Item from '../Item/Item'
                        //
                        export default class List extends Component {
                          // 限制 props 参数，从父组件中传过来的todos必须是一个数组，idDone 必须是一个函数
                           static propTypes =  {
                            todos:PropTypes.array.isRequired,
                            isDone:PropTypes.func.isRequired
                          } 
                          render() {
                            const {todos, isDone} = this.props   // 通过App.jsx中定义的props 参数 todos={todos}，传递到了这里，通过解构赋值取出todos
                            // console.log(typeof(todos), todos)
                            return (
                              <div>
                                {
                                  todos.map((todo) => {
                                    return <Item key={todo.id} todo={todo} isDone={isDone} />
                                    // isDone 是是通过父类App中的props传过来的，然后将它再传给Item组件实现孙子给爷爷传递数据
                                  })
                                }
                              </div>
                            )
                          }
                        }
                        ```
    -   [x] [62 062\_尚硅谷\_react教程\_TodoList案例\_删除一个todo\_Duration-12Min](https://www.bilibili.com/video/BV1wy4y1D7JT/?p=62 "62 062_尚硅谷_react教程_TodoList案例_删除一个todo_Duration-12Min")
        -   \[笔记]
            -   示例：添加删除todo条目的功能，并添加删除确认提示 <注意：在React中confim()需要`windom.confirm()`才能生效> \[`Array.filter()`，`.confirm()`]
                -   App 创建删除函数
                    ```react&#x20;jsx
                    import React, { Component } from 'react'
                    // 我的组件
                    import Header from './component/Header/Header'
                    import List from './component/List/List'
                    import Bottom from './component/Bottom/Bottom'
                    // 我的CSS
                    import './App.css'
                    //
                    export default class App extends Component {

                      // 初始化状态
                      state = {todos:[
                                      {id: '001', name:'吃饭', done:true},
                                      {id: '002', name:'睡觉', done:false},
                                      {id: '003', name:'Codeing', done:false},
                                      {id: '004', name:'学开飞机', done:false},
                              ]}
                      // 通过props传递函数，来添加 state 中 todos 的条目
                      addTodo = (todoObj) => {
                        // 接收来自子组件的数据
                        const {todos} = this.state
                        // console.log(typeof(todos))  // 是个对象object
                        const newTodos = [todoObj, ...todos]

                        this.setState({todos:newTodos})
                      }
                      // 通过props传递函数，来修改 state 中 todos 中 done 的值
                      isDone = (id, done)=>{
                        // 获取原状态
                        const {todos} = this.state
                        // 遍历，判断每一条数据的id是否与传入的id相同，如果相同则，修改done的值为传入的done的值，否则不修改
                        // 最后存入newTodos
                        const newTodos = todos.map((i)=>{
                          if (i.id === id) return {...i, done:done}
                          else return i
                        })
                        this.setState({todos:newTodos})
                      }
                      // 通过props传递函数，来删除 state 中 todos 的 todo
                       delTodo = (id)=>{ 
                        // 获取原状态
                         const {todos} = this.state 
                        // 过滤数组，删除
                        // const newTodos = todos.filter((todo)=> {return todo.id !== id} )
                        // this.setState({todos:newTodos})
                        //// 简写上方的组数过滤
                         const newTodos = todos.filter((todo)=> todo.id !== id )
                        this.setState({todos:newTodos})
                      } 

                      render() {
                        const {todos} = this.state
                        return (
                          <div>
                            <div id='totoContainer'>
                              <Header addTodo={this.addTodo}/>
                              <List todos={todos} isDone={this.isDone}  delTodo={this.delTodo} />
                              <Bottom />
                            </div>
                          </div>
                        )
                      }
                    }
                    ```
                -   List 传递删除函数给Item
                    ```react&#x20;jsx
                    import React, { Component } from 'react'
                    import PropTypes from 'prop-types' 
                    // my component
                    import Item from '../Item/Item'
                    //
                    export default class List extends Component {
                      // 限制 props 参数，从父组件中传过来的todos必须是一个数组，idDone 必须是一个函数
                      static propTypes =  {
                        todos:PropTypes.array.isRequired,
                        isDone:PropTypes.func.isRequired,
                        delTodo:PropTypes.func.isRequired
                      }
                      render() {
                        const {todos, isDone,  delTodo } = this.props   // 通过App.jsx中定义的props 参数 todos={todos}，传递到了这里，通过解构赋值取出todos
                        // console.log(typeof(todos), todos)
                        return (
                          <div>
                            {
                              todos.map((todo) => {
                                return <Item key={todo.id} todo={todo} isDone={isDone}  delTodo={delTodo}  />
                                // isDone 是是通过父类App中的props传过来的，然后将它再传给Item组件实现孙子给爷爷传递数据
                              })
                            }
                          </div>
                        )
                      }
                    }
                    ```
                -   Item 调用删除函数，删除指定的todo条目
                    ```react&#x20;jsx
                    import React, { Component } from 'react'

                    export default class Item extends Component {
                      // 鼠标移入移出条目状态
                      state = {mouse:false}

                      // 鼠标移入移出 的回调
                      handleMouse(flag){
                        return ()=>{
                          this.setState({mouse:flag})
                        }
                      }
                      // todo是否完成; 取消或勾上某个 todo 的回调
                      handleCheck(id){
                        return (event)=>{
                          // console.log(id, event.target.checked)
                          // 从父组件(List)的父组件(App)中传过来的props.isDone参数(函数)
                          this.props.isDone(id, event.target.checked)
                        }
                      }
                      // 删除一条todo 的回调，这里不使用高阶函数的方式
                       handleDelete(id){
                        // console.log(id)  // 获取删除的条目ID
                        // 进行删除确认 判断是否删除
                        if(window.confirm('是否删除')){
                          this.props.delTodo(id)
                        }
                      } 
                      //
                      render() {
                        const {todo} = this.props
                        const ismouse = this.state.mouse
                        return (
                          <div>
                            {
                              <li style={{backgroundColor:ismouse? '#ddd' : 'white'} } onMouseEnter={this.handleMouse(true)} onMouseLeave={this.handleMouse(false)}>
                                <label  htmlFor="">
                                  {/* 复选框 发生改变(onChange)时，调用函数 */}
                                  <input type="checkbox" onChange={this.handleCheck(todo.id)} defaultChecked={todo.done}/>
                                  <span>{todo.name} </span>
                                  <span>{todo.id} </span>
                                  <a style={{display:ismouse?'inline':'none'}}  onClick={()=>this.handleDelete(todo.id)}  href='#123'>
                                    Del
                                  </a>
                                </label>
                              </li>
                            }
                          </div>
                        )
                      }
                    }
                    ```
    -   [x] [63 063\_尚硅谷\_react教程\_TodoList案例\_实现底部功能\_Duration-25Min](https://www.bilibili.com/video/BV1wy4y1D7JT/?p=63 "63 063_尚硅谷_react教程_TodoList案例_实现底部功能_Duration-25Min")
        -   \[笔记]
            -   示例：全选按钮，已完成的todo全部清除按钮 的功能实现 \[props,`Array.reduce()`,`.confirm()`]
                -   App
                    ```react&#x20;jsx
                    import React, { Component } from 'react'
                    // 我的组件
                    import Header from './component/Header/Header'
                    import List from './component/List/List'
                    import Bottom from './component/Bottom/Bottom'
                    // 我的CSS
                    import './App.css'
                    //
                    export default class App extends Component {

                      // 初始化状态
                      state = {todos:[
                                      {id: '001', name:'吃饭', done:true},
                                      {id: '002', name:'睡觉', done:false},
                                      {id: '003', name:'Codeing', done:false},
                                      {id: '004', name:'学开飞机', done:false},
                              ]}
                      // 通过props传递函数，来添加 state 中 todos 的条目
                      addTodo = (todoObj) => {
                        // 接收来自子组件的数据
                        const {todos} = this.state
                        // console.log(typeof(todos))  // 是个对象object
                        const newTodos = [todoObj, ...todos]

                        this.setState({todos:newTodos})
                      }
                      // 通过props传递函数，来修改 state 中 todos 中 done 的值
                      isDone = (id, done)=>{
                        // 获取原状态
                        const {todos} = this.state
                        // 遍历，判断每一条数据的id是否与传入的id相同，如果相同则，修改done的值为传入的done的值，否则不修改
                        // 最后存入newTodos
                        const newTodos = todos.map((i)=>{
                          if (i.id === id) return {...i, done:done}
                          else return i
                        })
                        this.setState({todos:newTodos})
                      }
                      // 通过props传递函数，来删除 state 中 todos 的 todo
                      delTodo = (id)=>{
                        // 获取原状态
                        const {todos} = this.state
                        // 过滤数组，删除
                        // const newTodos = todos.filter((todo)=> {return todo.id !== id} )
                        // this.setState({todos:newTodos})
                        //// 简写上方的组数过滤
                        const newTodos = todos.filter((todo)=> todo.id !== id )
                        this.setState({todos:newTodos})
                      }
                       // 全选按钮
                      checkAll =(done)=>{
                        // 获取原状态
                        const {todos} = this.state
                        // 遍历
                        const newTodos = todos.map((i)=>{
                            return {...i, done}  // return {...i, done: done} 的简写
                        })
                        // 最后存入newTodos
                        this.setState({todos:newTodos})
                      } 
                      // 删除已完成的todo
                       delDoneTodo = ()=>{
                        // 获取原状态
                        const {todos} = this.state
                        // const newTodos = todos.filter((todo)=> todo.done !== true )  // 过滤所有以完成的todo
                        const newTodos = todos.filter((todo)=> !todo.done)  // 上方代码的简写，负负得正所以留下，真假为假，所以过滤掉
                        this.setState({todos:newTodos})
                      } 
                      render() {
                        const {todos} = this.state
                        return (
                          <div>
                            <div id='totoContainer'>
                              <Header addTodo={this.addTodo}/>
                              <List todos={todos} isDone={this.isDone} delTodo={this.delTodo}/>
                              <Bottom todos={todos}  checkAll={this.checkAll}   delDoneTodo={this.delDoneTodo} />
                            </div>
                          </div>
                        )
                      }
                    }
                    ```
                -   Bottom
                    ```react&#x20;jsx
                    import React, { Component } from 'react'

                    export default class Bottom extends Component {
                      // 全选 
                      checkAll = (event)=>{
                        this.props.checkAll(event.target.checked)
                      } 
                      // 删除已完成的todo 
                      delDoneTodo = ()=>{
                        if(window.confirm('确认清除所有已完成的选项吗?')){
                          this.props.delDoneTodo()
                        }
                          
                      } 
                      render() {
                        const {todos} = this.props
                        const doneCount = todos.reduce((count, curTodo)=>{
                          if (curTodo.done){
                            count ++
                          } 
                          return count // 返回已经完成的数目
                        }, 0)
                        // 计算总条目
                        const todosCount = todos.length
                        //
                        return (
                          <div>
                            <label htmlFor="">
                              <input type="checkbox" name="" id="" onChange={this.checkAll} checked={doneCount === todosCount && todosCount!==0 ? true:false} />
                            </label>
                            <span>已完成{doneCount} / 总数{todosCount} </span>
                            <button onClick={this.delDoneTodo}>清除已完成的任务</button>
                          </div>
                        )
                      }
                    }
                    ```
    -   [x] [64 064\_尚硅谷\_react教程\_TodoList案例\_总结TodoList案例\_Duration-5Min](https://www.bilibili.com/video/BV1wy4y1D7JT/?p=64 "64 064_尚硅谷_react教程_TodoList案例_总结TodoList案例_Duration-5Min")
        -   \[笔记]状态提升,父组件 ←传递参数 ←子组件 [¶](https://www.bilibili.com/video/BV1wy4y1D7JT?t=152.5\&p=64 "¶")

            ![](../image/image_pl1e7wxchi.png)
    -   [x] [65 065\_尚硅谷\_react教程\_脚手架配置代理\_方法1\_Duration-27Min](https://www.bilibili.com/video/BV1wy4y1D7JT/?p=65 "65 065_尚硅谷_react教程_脚手架配置代理_方法1_Duration-27Min")
        -   \[笔记]

            [65 065\_尚硅谷\_react教程\_脚手架配置代理\_方法1\_Duration-27Min](https://www.bilibili.com/video/BV1wy4y1D7JT/?p=65 "65 065_尚硅谷_react教程_脚手架配置代理_方法1_Duration-27Min")课程前置知识：[\[JS库\]axios](\[JS库]axios_3KLSyeBhEtnvZAkP4DS4aU.md "\[JS库]axios"),
            -   示例：添加代理(一个) 方式1 \[[./package.json](--package.json_5XzrB1BD9kJ9xyQ72pXvy9.md "./package.json")]

                ![](../image/image_8YGHs2SPVs.png)

                ![](../image/image_ppUgXbsocf.png)

                ![](../image/image_DvM1pUMrRs.png)
                > 代理5000的端口，
                ![](../image/image_C_V7HiUF3h.png)
                > client是3000端口，所有发送也只能是3000端口，再通过代理到5000端口 解决[CORS](CORS_hk5DR43g1YhbKADigy2VLv.md "CORS")，只适用于代理一个server
            ***
    ## 搜索案例
    -   [x] [66 066\_尚硅谷\_react教程\_脚手架配置代理\_方法2\_Duration-26Min](https://www.bilibili.com/video/BV1wy4y1D7JT/?p=66 "66 066_尚硅谷_react教程_脚手架配置代理_方法2_Duration-26Min")
        -   \[笔记]
            -   示例：添加代理(一个) 方式1 \[[./package.json](--package.json_5XzrB1BD9kJ9xyQ72pXvy9.md "./package.json")]

                ![](../image/image_8YGHs2SPVs.png)

                ![](../image/image_ppUgXbsocf.png)

                ![](../image/image_DvM1pUMrRs.png)
                > 代理5000的端口，
                ![](../image/image_C_V7HiUF3h.png)
                > client是3000端口，所有发送也只能是3000端口，再通过代理到5000端口 解决[CORS](CORS_hk5DR43g1YhbKADigy2VLv.md "CORS")，只适用于代理一个server
            -   示例：添加代理(多个) 方式2 \[[setupProxy.js](setupProxy.js_uhNfFMw6QZ2A5BQokWtCtM.md "setupProxy.js")]
                > http-proxy-middleware 1.x 版本后用这个 const { createProxyMiddleware } = require('http-proxy-middleware');
                ![](../image/image_fzEx2DsKE5.png)

                ![](../image/image_rIaK1H5k8A.png)

                ![](../image/image_wLUOUz22vy.png)


                ***
                ![](../image/image_iV8-htHTgt.png)
    -   [x] [67 067\_尚硅谷\_react教程\_github搜索案例\_静态组件\_Duration-19Min](https://www.bilibili.com/video/BV1wy4y1D7JT/?p=67 "67 067_尚硅谷_react教程_github搜索案例_静态组件_Duration-19Min")
    -   [x] [68 068\_尚硅谷\_react教程\_github搜索案例\_axios发送请求\_Duration-26Min](https://www.bilibili.com/video/BV1wy4y1D7JT/?p=68 "68 068_尚硅谷_react教程_github搜索案例_axios发送请求_Duration-26Min")
        -   \[笔记] 连续解构赋值



            ![](../image/image_Wxo_RPOrie.png)
    -   [x] [69 069\_尚硅谷\_react教程\_github搜索案例\_展示数据\_Duration-12Min](https://www.bilibili.com/video/BV1wy4y1D7JT/?p=69 "69 069_尚硅谷_react教程_github搜索案例_展示数据_Duration-12Min")
        -   \[笔记]
    -   [x] [70 070\_尚硅谷\_react教程\_github搜索案例\_完成案例\_Duration-20Min](https://www.bilibili.com/video/BV1wy4y1D7JT/?p=70 "70 070_尚硅谷_react教程_github搜索案例_完成案例_Duration-20Min")
        -   \[笔记]
            -   示例：完整的 {搜索功能} \[[\[JS库\]axios](\[JS库]axios_3KLSyeBhEtnvZAkP4DS4aU.md "\[JS库]axios"),state,propsrefs,\[JS]三元运算符,`then()`,[\[Web\]Bootstrap](\[Web]Bootstrap_u7Ak1kdCmPN7gbVGVC2QCK.md "\[Web]Bootstrap")

                ![](<../image/2023-23-23-2119 (1)_LS7qfK2CGa.gif>)

                ![](../image/image_ujAt4OC1hl.png)
                -   App
                    ```react&#x20;jsx
                    import React, { Component } from 'react'
                    //
                    import Search from './component/Search/Search'
                    import List from './component/TestAxios/List/List'
                    //
                    export default class App extends Component {
                      state = {
                        data:[],          // 存储搜索之后的数据
                        isFirst:true,     // 当前是否为第一次搜索之前的状态
                        isLoading:false,  // 当前是否为加载状态
                        err:''            // 错误信息
                      }
                      // 更新App的状态的函数
                      updateAppState = (stateObj) =>{
                        this.setState(stateObj)
                      }

                      render() {
                        return (
                          <div>
                            <Search updateAppState={this.updateAppState}/>
                            <List stateData={this.state}/>
                          </div>
                        )
                      }
                    }

                    ```
                -   Search
                    ```react&#x20;jsx
                    import React, { Component } from 'react'
                    import axios from 'axios'

                    export default class Search extends Component {
                        keyWord = React.createRef()
                        search = ()=>{
                            // 获取搜索的值
                            const keyword = this.keyWord.current.value
                            console.log(keyword)
                            // 准备进行搜索
                            this.props.updateAppState({isFirst:false, isLoading:true})
                            // 进行网络请求
                            axios.get(`http://qwertyui.vip:22285/demo/drf/movie2/`).then(
                                response =>{
                                    // console.log(response.data)
                                    // 成功接收到了数据 将数据返回给父组件App中传递过来的函数，更新状态
                                    this.props.updateAppState({isLoading:false, data:response.data})
                                },
                                error => {
                                    // 如果请求失败，存储错误信息，更新加载状态
                                    this.props.updateAppState({isLoading:false, err:error.message})
                                    // console.log('错误')
                                    // console.log(error.message)
                                }
                            )
                        }
                        render() {
                            return (
                                <div>
                                    <section className="text-center container">
                                        <div className="row py-lg-5">
                                            <div className="col-lg-6 col-md-8 mx-auto">
                                                <h1 className="fw-light">搜索</h1>
                                                <div className='flex '>
                                                    <div className="mb-3">
                                                        <div className='input-group'>
                                                        <input ref={this.keyWord} type="text"
                                                            className="form-control" name="" id="" aria-describedby="helpId" placeholder="" />
                                                        <button onClick={this.search} type="button" className="btn btn-primary">Search</button>
                                                        </div>
                                                        <small id="helpId" className="form-text text-muted">爱搜啥搜啥，看我出不出</small>

                                                    </div>
                                                </div>
                                            </div>
                                        </div>
                                    </section>
                                </div>
                            )
                        }
                    }

                    ```
                -   List
                    ```react&#x20;jsx
                    import React, { Component } from 'react'

                    export default class List extends Component {
                        render() {
                            const { data, isFirst, isLoading, err } = this.props.stateData
                            // console.log('in List component', typeof(isSearch), isLoading,err)
                            return (
                                <div>
                                    <div className="album py-5 bg-lig">
                                        <div className="container">
                                            <div className="row row-cols-1 row-cols-sm-2 row-cols-md-3 g-3">
                                                {
                                                    // 根据状态做判断，显示对应状态的信息
                                                    isFirst  ? <h2>请搜索巴拉巴拉</h2> :    // 如果是第一次搜索之前，显示的信息
                                                    isLoading ? <h2>加载中........</h2> :   // 如果是正在加载时，显示的信息
                                                    err ? <span>{err}</span> :              // 如果有错误，则显示错误信息，否则，正常展示
                                                    
                                                    data.map((movieObj) => {
                                                        return <div key={movieObj.id}  className="col">
                                                            <div className="card shadow-sm">
                                                                <img src="https://w.wallhaven.cc/full/3l/wallhaven-3lw5g9.jpg" alt="Head diagram" />
                                                                <div className="card-body">
                                                                    <p className='card-text'>{movieObj.name_ch}|{movieObj.name_en}</p>
                                                                    <p className="card-text">{movieObj.movie_synopsis}</p>
                                                                    <div className="d-flex justify-content-between align-items-center">
                                                                        <div className="btn-group">
                                                                            <button type="button" className="btn btn-sm btn-outline-secondary">View</button>
                                                                            <button type="button" className="btn btn-sm btn-outline-secondary">Edit</button>
                                                                        </div>
                                                                        <small className="text-muted">9 mins</small>
                                                                    </div>
                                                                </div>
                                                            </div>
                                                        </div>
                                                    })
                                                }
                                            </div>
                                        </div>
                                    </div>
                                </div>
                            )
                        }
                    }

                    ```
    -   [x] [71 071\_尚硅谷\_react教程\_消息订阅与发布技\_pubsub\_Duration-28Min](https://www.bilibili.com/video/BV1wy4y1D7JT/?p=71 "71 071_尚硅谷_react教程_消息订阅与发布技_pubsub_Duration-28Min")
        -   \[笔记]
            -   示例：[¶](https://www.bilibili.com/video/BV1wy4y1D7JT?t=853.6\&p=71 "¶")兄弟组件之间的通信; 组件通信方式2/4：[\[React\]消息订阅&消息发布](\[React]消息订阅&消息发布_prwmsFoDKTvHDdrrD4DvXQ.md "\[React]消息订阅&消息发布")：[\[JS库\]PubSubJS](\[JS库]PubSubJS_xPdUSX2Zq1GZCEBDd9RK4.md "\[JS库]PubSubJS");  ; [\[JS库\]axios](\[JS库]axios_3KLSyeBhEtnvZAkP4DS4aU.md "\[JS库]axios") \[`.publish()``.subscribe()``.unsubscribe()`]
                1.  将原本在App中的状态信息，移到List组件之中，因为List组件是调用这些信息
                2.  在Search组件中发布信息，用于修改List组件的中的状态信息
                3.  在List组件中订阅来自Search中发布的信息，来更改自身state的状态，从而修改页面信息
                -   App
                    ```react&#x20;jsx
                    import React, { Component } from 'react'

                    //
                    import Search from './component/Search/Search'
                    import List from './component/TestAxios/List/List'
                    //
                    export default class App extends Component {
                      render() {
                        return (
                          <div>
                            <Search updateAppState={this.updateAppState}/>
                            <List stateData={this.state}/>
                          </div>
                        )
                      }
                    }

                    ```
                -   Search
                    ```react&#x20;jsx
                    import React, { Component } from 'react'
                    import axios from 'axios'
                    import PubSub from 'pubsub-js'
                    //
                    export default class Search extends Component {
                        // ref引用
                        keyWord = React.createRef()
                        //    
                        search = ()=>{
                            // 获取搜索的值
                            const keyword = this.keyWord.current.value
                            console.log(keyword)
                            // 准备进行搜索
                            //// this.props.updateAppState({isFirst:false, isLoading:true})
                             PubSub.publish('search',{isFirst:false, isLoading:true}) 
                            // 进行网络请求
                            axios.get(`http://qwertyui.vip:22285/demo/drf/movie/`).then(
                                response =>{
                                    // console.log(response.data)
                                    // 成功接收到了数据 将数据返回给父组件App中传递过来的函数，更新状态
                                    // this.props.updateAppState({isLoading:false, data:response.data})
                                     PubSub.publish('search', {isLoading:false, data:response.data}) 
                                },
                                error => {
                                    // 如果请求失败，存储错误信息，更新加载状态
                                    // this.props.updateAppState({isLoading:false, err:error.message})
                                     PubSub.publish('search', {isLoading:false, err:error.message}) 
                                    // console.log('错误')
                                    console.log(error.message)
                                }
                            )
                        }
                        render() {
                            return (
                                <div>
                                    <section className="text-center container">
                                        <div className="row py-lg-5">
                                            <div className="col-lg-6 col-md-8 mx-auto">
                                                <h1 className="fw-light">搜索</h1>
                                                <div className='flex '>
                                                    <div className="mb-3">
                                                        <div className='input-group'>
                                                        <input ref={this.keyWord} type="text"
                                                            className="form-control" name="" id="" aria-describedby="helpId" placeholder="" />
                                                        <button onClick={this.search} type="button" className="btn btn-primary">Search</button>
                                                        </div>
                                                        <small id="helpId" className="form-text text-muted">爱搜啥搜啥，看我出不出</small>

                                                    </div>
                                                </div>
                                            </div>
                                        </div>
                                    </section>
                                </div>
                            )
                        }
                    }
                    ```
                -   List
                    ```react&#x20;jsx
                    import React, { Component } from 'react'
                    import PubSub from 'pubsub-js'
                    //
                    export default class List extends Component {
                        state = {
                            data:[],          // 存储搜索之后的数据
                            isFirst:true,     // 当前是否为第一次搜索之前的状态
                            isLoading:false,  // 当前是否为加载状态
                            err:''            // 错误信息
                          }
                        // 组件挂载完成时
                         componentDidMount(){
                            // 订阅 来自Search组件的对此部份发布的消息的更新，也就是state的状态更新
                            PubSub.subscribe('search',(_, stateObj)=>{
                                this.setState(stateObj)
                            });
                        } 
                         // 组件即将卸载时
                        componentWillUnmount(){
                            // 在组件将要卸载时，取消订阅
                            PubSub.unsubscribe(this.token)
                        } 
                        render() {
                            const { data, isFirst, isLoading, err } = this.state
                            // console.log('in List component', typeof(isSearch), isLoading,err)
                            return (
                                <div>
                                    <div className="album py-5 bg-lig">
                                        <div className="container">
                                            <div className="row row-cols-1 row-cols-sm-2 row-cols-md-3 g-3">
                                                {
                                                    // 根据状态做判断，显示对应状态的信息
                                                    isFirst  ? <h2>请搜索巴拉巴拉</h2> :    // 如果是第一次搜索之前，显示的信息
                                                    isLoading ? <h2>加载中........</h2> :   // 如果是正在加载时，显示的信息
                                                    err ? <span>{err}</span> :              // 如果有错误，则显示错误信息，否则，正常展示
                                                    
                                                    data.map((movieObj) => {
                                                        return <div key={movieObj.id}  className="col">
                                                            <div className="card shadow-sm">
                                                                <img src="https://w.wallhaven.cc/full/3l/wallhaven-3lw5g9.jpg" alt="Head diagram" />
                                                                <div className="card-body">
                                                                    <p className='card-text'>{movieObj.name_ch}|{movieObj.name_en}</p>
                                                                    <p className="card-text">{movieObj.movie_synopsis}</p>
                                                                    <div className="d-flex justify-content-between align-items-center">
                                                                        <div className="btn-group">
                                                                            <button type="button" className="btn btn-sm btn-outline-secondary">View</button>
                                                                            <button type="button" className="btn btn-sm btn-outline-secondary">Edit</button>
                                                                        </div>
                                                                        <small className="text-muted">9 mins</small>
                                                                    </div>
                                                                </div>
                                                            </div>
                                                        </div>
                                                    })
                                                }
                                            </div>
                                        </div>
                                    </div>
                                </div>
                            )
                        }
                    }
                    ```
    -   [x] [**72 072\_尚硅谷\_react教程\_fetch发送请求\_Duration-47Min**](https://www.bilibili.com/video/BV1wy4y1D7JT/?p=72 "72 072_尚硅谷_react教程_fetch发送请求_Duration-47Min")
        -   \[笔记] [Fetch API](<Fetch API_kKwSXQoRQDfe1FqZtujruo.md> "Fetch API"),`Promise()``then()``catch()`,`await`,`try...catch`
            -   优化过程

                ![](../image/image_wPtqdR40a7.png)

                ![](../image/image_F2sqJPKk7S.png)

                ![](../image/image_vyf_znCJF0.png)
            ![](../image/image_Xku2DZZguG.png)
    -   [x] [73 073\_尚硅谷\_react教程\_总结github搜索案例\_Duration-3Min](https://www.bilibili.com/video/BV1wy4y1D7JT/?p=73 "73 073_尚硅谷_react教程_总结github搜索案例_Duration-3Min")
    ## 路由篇
    -   [x] [74 074\_尚硅谷\_react教程\_对SPA应用的理解\_Duration-13Min](https://www.bilibili.com/video/BV1wy4y1D7JT/?p=74 "74 074_尚硅谷_react教程_对SPA应用的理解_Duration-13Min") [SPA](SPA_dRpTki5ypsK6niwgePfbz9.md "SPA")
    -   [x] [75 075\_尚硅谷\_react教程\_对路由的理解\_Duration-11Min](https://www.bilibili.com/video/BV1wy4y1D7JT/?p=75 "75 075_尚硅谷_react教程_对路由的理解_Duration-11Min") \[[\[React\]路由](\[React]路由_4SqHXtAt3fngpVE1s8JSet.md "\[React]路由")]
    -   [x] [76 076\_尚硅谷\_react教程\_前端路由原理\_Duration-23Min](https://www.bilibili.com/video/BV1wy4y1D7JT/?p=76 "76 076_尚硅谷_react教程_前端路由原理_Duration-23Min") [\[JS\]history](\[JS]history_wknz5W9Lwmeoi1yVtPWX2q.md "\[JS]history")
        -   \[笔记]

            ![](../image/image_YCnsnDtFWJ.png)
    -   [x] [77 077\_尚硅谷\_react教程\_路由的基本使用\_Duration-44Min](https://www.bilibili.com/video/BV1wy4y1D7JT/?p=77 "77 077_尚硅谷_react教程_路由的基本使用_Duration-44Min")
        -   \[笔记]&#x20;
            -   注意点：react-router-dom的所有组件必须被`Router`中的之一包裹
            -   示例1.0：基础使用：无刷跳转home与about页面 \[[\[JS库\]react-route-dom](\[JS库]react-route-dom_jGUgd2TkFiY94rBUA6txun.md "\[JS库]react-route-dom")`@5.3.4`,设置路由链接注册路由✧,\[`BrowserRouter``Link``Route`]
                -   v1

                    ![](../image/image_p-QKorlQPj.png)
                    ```react&#x20;jsx
                    import React, { Component } from 'react'
                    import {BrowserRouter as BRouter, Link} from 'react-router-dom'

                    export default class App extends Component {
                      render() {
                        return (
                          <div>
                            <div className="container">
                              <div className="row">
                                <div className="col-12">
                                  <h2>标题</h2>
                                </div>
                                <div className="col-4">
                                <div className="list-group">
                              {/* // 原生使用a标签跳转页面 */}
                              {/* <a className="list-group-item active" href="./about.html">About</a> */}
                              {/* <a className="list-group-item" href="./home.html">Home</a> */}
                              {/* // 使用 react-router-dom */}
                              <BRouter>
                                <Link className="list-group-item active" to='/about'>About</Link>
                                <Link className="list-group-item" to='/home'>Home</Link>

                              </BRouter>
                            </div>
                                </div>
                                <div className="col-8">内容</div>
                              </div>
                            </div>
                          </div>
                        )
                      }
                    }

                    ```
                -   v2

                    ![](../image/image_qjJnTn-Wwl.png)
                    ```react&#x20;jsx
                    import React, { Component } from 'react'
                    import { BrowserRouter, Link, Route } from 'react-router-dom'
                    //
                    import About from './component/About'
                    import Home from './component/Home'
                    //
                    export default class App extends Component {
                      render() {
                        return (
                          <div>
                             <BrowserRouter> 
                              <div className="container">
                                <div className="row">
                                  <div className="col-12">
                                    <h2>标题</h2>
                                  </div>
                                  <div className="col-4">
                                    <div className="list-group">
                                      {/* // 原生使用a标签跳转页面 */}
                                      {/* <a className="list-group-item active" href="./about.html">About</a> */}
                                      {/* <a className="list-group-item" href="./home.html">Home</a> */}
                                      {/* // 使用 react-router-dom 编写路由链接 设置路由链接 */}
                                       <Link className="list-group-item active"  to='/home' >Home</Link>
                                      <Link className="list-group-item "   to='/about ' >About</Link> 
                                    </div>
                                  </div>
                                  <div className="col-8">
                                     {/* 注册路由 */}
                                    <Route path="/home" component={Home} />
                                    <Route path="/about" component={About} /> 
                                  </div>
                                </div>
                              </div>
                             </BrowserRouter> 
                          </div>
                        )
                      }
                    }


                    ```
    -   [x] [78 078\_尚硅谷\_react教程\_路由组件与一般组件\_Duration-20Min](https://www.bilibili.com/video/BV1wy4y1D7JT/?p=78 "78 078_尚硅谷_react教程_路由组件与一般组件_Duration-20Min")
        -   \[笔记]
            -   示例1.1： \[[\[JS库\]react-route-dom](\[JS库]react-route-dom_jGUgd2TkFiY94rBUA6txun.md "\[JS库]react-route-dom"),一般组件,路由组件]
                -   \[对比]一般组件|路由组件
                    -   一般组件：直接写、路由组件：通过Router
                    -   例如：一般组件：直接写、路由组件：通过Router

                        ![](../image/image_5MTsoW_wO8.png)
                    -   例如：路由组件的会接收三个props&#x20;

                        ![](../image/image_7nHI7knLeF.png)
                -   路由组件，按规范放在pages文件夹中

                    ![](../image/image_tfnr7_teiu.png)
                -   路由组件三大属性
                    -   主要学习

                        ![](../image/image_es7_R60Uh3.png)
                    -   全

                        ![](../image/image_rcsRVss8M0.png)
    -   [x] [79 079\_尚硅谷\_react教程\_NavLink的使用\_Duration-6Min](https://www.bilibili.com/video/BV1wy4y1D7JT/?p=79 "79 079_尚硅谷_react教程_NavLink的使用_Duration-6Min")
        -   \[笔记]
            -   `NavLink`设置路由链接; 可以添加属性`@6.x.x`activeClassName=""->函数回调，当点击对应NavLink时，加载什么类名
    -   [x] [80 080\_尚硅谷\_react教程\_封装NavLink组件\_Duration-19Min](https://www.bilibili.com/video/BV1wy4y1D7JT/?p=80 "80 080_尚硅谷_react教程_封装NavLink组件_Duration-19Min")
        -   \[笔记]
            -   示例：封装NavLink到MyNavLink中，类名参数与标签体参数通过解构实现。 \[[\[JS库\]react-route-dom](\[JS库]react-route-dom_jGUgd2TkFiY94rBUA6txun.md "\[JS库]react-route-dom"),props属性参数标签体参数`children`,解构赋值]
                -   传递在标签体中的参数会放到props中的children属性中

                    ![](../image/image_JLWikeUfrc.png)

                    ![](../image/image_WYbRMV76WO.png)
                ***


                ![](../image/image_2OlSILxKz1.png)
                -   App
                    -   v1
                        ```react&#x20;jsx
                        import React, { Component } from 'react'
                        import { BrowserRouter, Route } from 'react-router-dom'
                        //
                        import About from './pages/About'
                        import Home from './pages/Home'
                        import MyNavLink from './component/MyNavLink/MyNavLink'
                        //
                        export default class App extends Component {
                          render() {
                            return (
                              <div>
                                <BrowserRouter>
                                  <div className="container">
                                    <div className="row">
                                      <div className="col-12">
                                        <h2>标题</h2>
                                      </div>
                                      <div className="col-4">
                                        <div className="list-group">
                                          {/* 原生使用a标签跳转页面 */}
                                          {/* <a className="list-group-item active" href="./about.html">About</a> */}
                                          {/* <a className="list-group-item" href="./home.html">Home</a> */}
                                          {/* 使用 react-router-dom 编写路由链接 */}
                                          {/* 封装NavLink */}
                                           <MyNavLink to="/home">Home</MyNavLink>
                                          <MyNavLink to="/about">About</MyNavLink> 
                                        </div>
                                      </div>
                                      <div className="col-8">
                                        {/* 注册路由 */}
                                        <Route path="/home" component={Home} />  {/* 如果检测路径是/home，则在这部分HTML中调用Home组件*/}
                                        <Route path="/about" component={About} />
                                      </div>
                                    </div>
                                  </div>
                                </BrowserRouter>
                              </div>
                            )
                          }
                        }
                        ```
                    -   v2 后面发现的问题，修复bug
                        -   ✧\[Q]在非Redirect指定的路径，刷新浏览器时，页面会回到redirect路径中? \[`Switch``Redirect`]

                            没像明白...
                            ***
                            -   问题代码
                                ```react&#x20;jsx
                                import React, { Component } from 'react'
                                import { Route, Switch, Redirect} from 'react-router-dom'
                                //
                                import About from './pages/About'
                                import Home from './pages/Home'
                                import MyNavLink from './component/MyNavLink/MyNavLink'
                                //
                                export default class App extends Component {
                                  render() {
                                    return (
                                      <div>
                                        <div className="container">
                                          <div className="row">
                                            <div className="col-12">
                                              <h2>标题</h2>
                                            </div>
                                            <div className="col-4">
                                              <div className="list-group">
                                                {/* 原生使用a标签跳转页面 */}
                                                {/* <a className="list-group-item active" href="./about.html">About</a> */}
                                                {/* <a className="list-group-item" href="./home.html">Home</a> */}
                                                {/* 使用 react-router-dom 编写路由链接 */}
                                                {/* 封装NavLink */}
                                                <MyNavLink to="/home">Home</MyNavLink>
                                                <MyNavLink to="/about">About</MyNavLink>
                                              </div>
                                            </div>
                                            <div className="col-8">
                                              {/* 注册路由 */}   
                                               <Route path="/home" component={Home} />  {/* 如果检测路径是/home，则在这部分HTML中调用Home组件*/}
                                              <Route path="/about" component={About} />
                                              <Redirect to="/about"/> 
                                            </div>
                                          </div>
                                        </div>
                                      </div>
                                    )
                                  }
                                }
                                ```
                            -   修复bug：
                                ```react&#x20;jsx
                                import React, { Component } from 'react'
                                import { Route, Switch, Redirect} from 'react-router-dom'
                                //
                                import About from './pages/About'
                                import Home from './pages/Home'
                                import MyNavLink from './component/MyNavLink/MyNavLink'
                                //
                                export default class App extends Component {
                                  render() {
                                    return (
                                      <div>
                                        <div className="container">
                                          <div className="row">
                                            <div className="col-12">
                                              <h2>标题</h2>
                                            </div>
                                            <div className="col-4">
                                              <div className="list-group">
                                                {/* 原生使用a标签跳转页面 */}
                                                {/* <a className="list-group-item active" href="./about.html">About</a> */}
                                                {/* <a className="list-group-item" href="./home.html">Home</a> */}
                                                {/* 使用 react-router-dom 编写路由链接 */}
                                                {/* 封装NavLink */}
                                                <MyNavLink to="/home">Home</MyNavLink>
                                                <MyNavLink to="/about">About</MyNavLink>
                                              </div>
                                            </div>
                                            <div className="col-8">
                                              {/* 注册路由 */}
                                               <Switch>
                                              <Route path="/home" component={Home} />  {/* 如果检测路径是/home，则在这部分HTML中调用Home组件*/}
                                              <Route path="/about" component={About} />
                                              <Redirect to="/about"/>
                                              </Switch> 
                                            </div>
                                          </div>
                                        </div>
                                      </div>
                                    )
                                  }
                                }
                                ```
                            ***
                            -   反正结论就是redirect需要在switch包裹
                        ```react&#x20;jsx
                        import React, { Component } from 'react'
                        import { Route, Switch, Redirect} from 'react-router-dom'
                        //
                        import About from './pages/About'
                        import Home from './pages/Home'
                        import MyNavLink from './component/MyNavLink/MyNavLink'
                        //
                        export default class App extends Component {
                          render() {
                            return (
                              <div>
                                <div className="container">
                                  <div className="row">
                                    <div className="col-12">
                                      <h2>标题</h2>
                                    </div>
                                    <div className="col-4">
                                      <div className="list-group">
                                        {/* 原生使用a标签跳转页面 */}
                                        {/* <a className="list-group-item active" href="./about.html">About</a> */}
                                        {/* <a className="list-group-item" href="./home.html">Home</a> */}
                                        {/* 使用 react-router-dom 编写路由链接 */}
                                        {/* 封装NavLink */}
                                        <MyNavLink to="/home">Home</MyNavLink>
                                        <MyNavLink to="/about">About</MyNavLink>
                                      </div>
                                    </div>
                                    <div className="col-8">
                                      {/* 注册路由 */}
                                      <Switch>
                                      <Route path="/home" component={Home} />  {/* 如果检测路径是/home，则在这部分HTML中调用Home组件*/}
                                      <Route path="/about" component={About} />
                                      <Redirect to="/about"/>
                                      </Switch>
                                    </div>
                                  </div>
                                </div>
                              </div>
                            )
                          }
                        }

                        ```
                -   MyNavLink
                    ```react&#x20;jsx
                    import React, { Component } from 'react'
                    import { NavLink } from 'react-router-dom'
                    export default class MyNavLink extends Component {
                      render() {
                        // 传递过来的的数据通过解构赋值，NavLink
                        console.log(this.props)
                        // {to: '/home', children: 'Home'}
                        // {to: '/about', children: 'About'}
                        return (
                             <NavLink activeClassName='active' className="list-group-item" {...this.props}/> 
                        )
                      }
                    }
                    ```
    -   [x] [81 081\_尚硅谷\_react教程\_Switch的使用\_Duration-8Min](https://www.bilibili.com/video/BV1wy4y1D7JT/?p=81 "81 081_尚硅谷_react教程_Switch的使用_Duration-8Min")
        -   \[笔记]
            -   默认情况下：两个路由指向同一个链接，会同时输出两个路由指定的组件[¶](https://www.bilibili.com/video/BV1wy4y1D7JT?t=334.5\&p=81 "¶")

                ![](../image/image_I1OK1jPeR8.png)
            -   示例： \[`Switch`]

                ![](../image/image_X9BPQm7VzH.png)
    -   [x] [82 082\_尚硅谷\_react教程\_解决样式丢失问题\_Duration-25Min](https://www.bilibili.com/video/BV1wy4y1D7JT/?p=82 "82 082_尚硅谷_react教程_解决样式丢失问题_Duration-25Min")
        -   \[笔记]

            问题：[解决样式丢失问题](https://www.bilibili.com/video/BV1wy4y1D7JT/?p=82 "解决样式丢失问题")，在设置了嵌套路由，在中刷新页面时

            原因：正常的一级路由，刷新获取CSS正常，与嵌套路由刷新获取的CSS路径，不对

            ![](../image/image_vELoEbCppC.png)
            -   样式丢失解决办法1[¶](https://www.bilibili.com/video/BV1wy4y1D7JT?t=1124.3\&p=82 "¶")：将index.html中的Bootstrap样式的`.`去除，使用绝对路径  <推荐>

                ![](../image/image_IQvpHXtSEd.png)
            -   样式丢失解决办法2[¶](https://www.bilibili.com/video/BV1wy4y1D7JT?t=1228.6\&p=82 "¶")：使用%PUBLIC\_URL%，变量参数 <推荐>

                ![](../image/image_lTV8YrEygw.png)
            -   样式丢失解决办法3[¶](https://www.bilibili.com/video/BV1wy4y1D7JT?t=1344.6\&p=82 "¶")：使用`HashRouter`

                ![](../image/image_kS0yLsOZ8u.png)

                ![](../image/image_VsTFYBQ4pW.png)
    -   [x] [83 083\_尚硅谷\_react教程\_路由的模糊匹配与严格匹配\_Duration-11Min](https://www.bilibili.com/video/BV1wy4y1D7JT/?p=83 "83 083_尚硅谷_react教程_路由的模糊匹配与严格匹配_Duration-11Min")
        -   \[笔记]

            ![](../image/image_V9KYKf2Vec.png)
            -   示例：路由链接是/home/a/b，但是注册路由时是/home就会出发糢糊匹配 \[路由的糢糊匹配(默认)[¶](https://www.bilibili.com/video/BV1wy4y1D7JT?t=288.6\&p=83 "¶"),exact路由的精确匹配,设置路由链接注册路由]
                -   示例：路由的糢糊匹配(默认)

                    ![](../image/image_QlhWZBmT-o.png)
                -   示例：exact路由的精确匹配[¶](https://www.bilibili.com/video/BV1wy4y1D7JT?t=584.1\&p=83 "¶")

                    简写

                    ![](../image/image_jAeeEyxwdC.png)

                    ![](../image/image_hluaqrIsho.png)
    -   [x] [84 084\_尚硅谷\_react教程\_Redirect的使用\_Duration-7Min](https://www.bilibili.com/video/BV1wy4y1D7JT/?p=84 "84 084_尚硅谷_react教程_Redirect的使用_Duration-7Min")
        -   \[笔记]
            -   示例：没匹配到的路由全部走about页面`Redirect`[¶](https://www.bilibili.com/video/BV1wy4y1D7JT?t=368.0\&p=84 "¶")  (`<Redirect to='/about' />`)
                -   code
                    ```react&#x20;jsx
                    import React, { Component } from 'react'
                    import { BrowserRouter, Route, Redirect} from 'react-router-dom'
                    //
                    import About from './pages/About'
                    import Home from './pages/Home'
                    import MyNavLink from './component/MyNavLink/MyNavLink'
                    //
                    export default class App extends Component {
                      render() {
                        return (
                          <div>
                            <BrowserRouter>
                              <div className="container">
                                <div className="row">
                                  <div className="col-12">
                                    <h2>标题</h2>
                                  </div>
                                  <div className="col-4">
                                    <div className="list-group">
                                      {/* 原生使用a标签跳转页面 */}
                                      {/* <a className="list-group-item active" href="./about.html">About</a> */}
                                      {/* <a className="list-group-item" href="./home.html">Home</a> */}
                                      {/* 使用 react-router-dom 编写路由链接 */}
                                      {/* 封装NavLink */}
                                      <MyNavLink to="/home">Home</MyNavLink>
                                      <MyNavLink to="/about">About</MyNavLink>
                                    </div>
                                  </div>
                                  <div className="col-8">
                                    {/* 注册路由 */}
                                    <Route path="/home" component={Home} />  {/* 如果检测路径是/home，则在这部分HTML中调用Home组件*/}
                                    <Route path="/about" component={About} />
                                     <Redirect to='/about' />  
                                  </div>
                                </div>
                              </div>
                            </BrowserRouter>
                          </div>
                        )
                      }
                    }
                    ```
                ![](../image/image_9Fr4_RD3YM.png)
    -   [x] [85 085\_尚硅谷\_react教程\_嵌套路由\_Duration-28Min](https://www.bilibili.com/video/BV1wy4y1D7JT/?p=85 "85 085_尚硅谷_react教程_嵌套路由_Duration-28Min")
        -   \[笔记]
            -   示例1.2：二级路由：Home组件中添加News与Anther路由组件 \[[\[JS库\]react-route-dom](\[JS库]react-route-dom_jGUgd2TkFiY94rBUA6txun.md "\[JS库]react-route-dom"),嵌套路由,`NavLink``Route`exact[🖼️ 图片](../image/image_ewM_0sQ_Un.png "🖼️ 图片")(第三条)[¶](https://www.bilibili.com/video/BV1wy4y1D7JT?t=1533.8\&p=85 "¶"),`Redirect``Switch`,`list-group-horizontal`]

                ![](../image/image_6ZW6CoDmzu.png)

                ![](../image/2023-23-25-1546_uG46Z6m3f8.gif)
                -   `src/pages/Home/index.jsx`
                    ```react&#x20;jsx
                    import React, { Component } from 'react'
                    import { NavLink, Route, Redirect, Switch } from 'react-router-dom'
                    import News from './News/News'
                    import Anther from './Anther/Anther'
                    //
                    // import News from './News/News'
                    // import Anther from './Anther/Anther'

                    export default class index extends Component {
                      render() {
                        return (
                          <div>
                            <div className="list-group list-group-horizontal mb-1">
                              {/* 设置链接 */}
                               <NavLink className="list-group-item" to="/home/news">News</NavLink>
                              <NavLink className="list-group-item" to="/home/anther">Anther</NavLink> 
                            </div>
                            <div className="row">
                              {/* 注册链接 */}
                               <Switch>
                              <Route path='/home/news' component={News} />
                              <Route path='/home/anther' component={Anther}/>
                              <Redirect to="/home/news" />
                              </Switch> 
                            </div>
                          </div>
                        )
                      }
                    }
                    ```
                -   `src/pages/Home/Anther/Anther.jsx`
                    ```react&#x20;jsx
                    import React, { Component } from 'react'

                    export default class Anther extends Component {
                      render() {
                        return (
                            <div>
                            <div className="list-group">
                                <div href="#" className="list-group-item list-group-item-action ">anther</div>
                                <div href="#" className="list-group-item list-group-item-action">Item</div>
                                <div href="#" className="list-group-item list-group-item-action disabled">Disabled item</div>
                            </div>
                          </div>
                        )
                      }
                    }

                    ```
                -   `src/pages/Home/News/News.jsx`
                    ```react&#x20;jsx
                    import React, { Component } from 'react'

                    export default class News extends Component {
                      render() {
                        return (
                          <div>
                            <div className="list-group">
                                <div href="#" className="list-group-item list-group-item-action">news</div>
                                <div href="#" className="list-group-item list-group-item-action">Item</div>
                                <div href="#" className="list-group-item list-group-item-action disabled">Disabled item</div>
                            </div>
                          </div>
                        )
                      }
                    }

                    ```
                -   示例：给active添加单独的样式 \[activeClassName=""]
                    -   Home/index.jsx
                        ```react&#x20;jsx
                        import React, { Component } from 'react'
                        import { NavLink, Route, Redirect, Switch } from 'react-router-dom'
                        import News from './News/News'
                        import Anther from './Anther/Anther'
                        //
                        // import News from './News/News'
                        // import Anther from './Anther/Anther'

                        export default class index extends Component {
                          render() {
                            return (
                              <div>
                                <div className="list-group list-group-horizontal mb-1">
                                  {/* 设置链接 */}
                                  <NavLink className="list-group-item"  activeClassName='activeClassName'  to="/home/news">News</NavLink>
                                  <NavLink className="list-group-item" activeClassName='activeClassName' to="/home/anther">Anther</NavLink>
                                </div>
                                <div className="row">
                                  {/* 注册链接 */}
                                  <Switch>
                                  <Route path='/home/news' component={News} />
                                  <Route path='/home/anther' component={Anther}/>
                                  <Redirect to="/home/news" />
                                  </Switch>
                                </div>
                              </div>
                            )
                          }
                        }
                        ```
                    -   在`public/index.html`
                        ```react&#x20;jsx
                            <style>
                                .activeClassName {
                                    /* 设置 active 背景颜色为黄色 */
                                    background-color: rgba(165, 175, 255, 0.553);
                                }
                            </style>
                        ```
    -   [x] [86 086\_尚硅谷\_react教程\_向路由组件传递params参数\_Duration-28Min](https://www.bilibili.com/video/BV1wy4y1D7JT/?p=86 "86 086_尚硅谷_react教程_向路由组件传递params参数_Duration-28Min")
        -   \[笔记]

            ![](../image/image_YIIDGZJRdO.png)
            -   示例：三级路由：路由组件传参方式1 \[`match.params`,(C)路由组件传参方式1：[¶](https://www.bilibili.com/video/BV1wy4y1D7JT?t=849.8\&p=86 "¶"),,嵌套路由,`Array.find()`,解构赋值\[JS]三元运算符,模板字符串(` `` `[)](https://developer.mozilla.org/zh-CN/docs/Web/JavaScript/Reference/Template_literals ")")]

                ![](../image/image_2N0umAxWzS.png)

                ![](../image/2023-23-25-1812_oj087IGDuf.gif)
                -   `src/pages/Home/News/News.jsx`
                    ```react&#x20;jsx
                    import React, { Component } from 'react'
                    import { Link, Route } from 'react-router-dom'
                    //
                    import Detail from './Detail/Detail'
                    //
                    export default class News extends Component {
                      // 模拟数据
                       state = {
                        newsArray:[
                          {id:"01", title:'朝鲜核问题'},
                          {id:"02", title:'伊朗核问题'},
                          {id:"03", title:'新闻3'},
                          {id:"04", title:'新闻4'},
                        ]
                      } 

                      render() {
                        return (
                          <div>
                            <div className="list-group">
                              {/* 设置路由链接 */}
                              {/* <Link className='list-group-item list-group-item-action' to='/home/news/detail' >新闻1</Link> */}
                               {
                                this.state.newsArray.map((newsObj)=>{
                                  return <Link key={newsObj.id} className='list-group-item list-group-item-action' 
                                     // to={`/home/news/detail/${newsObj.id}/${newsObj.title}`}>   {/* 路由组件传递 一个 params 参数 */} 
                                    to={`/home/news/detail/${newsObj.id}/${newsObj.title}`}>      {/* 路由组件传递 两个params 参数 */}
                                    {newsObj.title}
                                  </Link> 
                                })
                              } 
                            </div>
                            <hr/>
                            <div>
                              {/* 注册路由 */}
                              {/* 接收上面Link传递的 params 参数 */}
                              {/* 接收一个 params 参数 */}
                              {/* <Route path={`/home/news/detail/:id/`} component={Detail}></Route>   */}
                               {/* 接收两个 params 参数 */}
                              <Route path={`/home/news/detail/:id/:title/`} component={Detail}></Route> 
                            </div>
                          </div>
                        )
                      }
                    }


                    ```
                -   `src/pages/Home/News/Detail/Detail.jsx`
                    ```react&#x20;jsx
                    import React, { Component } from 'react'

                    export default class Detail extends Component {
                      // 模拟从DB获取的数据
                      state = {
                        newsDetail:[
                          {id:'01', detail:'核问题是指自1990年代朝鲜民主主义人民共和国...'},
                          {id:'02', detail:'伊朗核问题，简称伊核问题，是伊朗于1950年起开发核工业所引发的国际问题...'},
                          {id:'03', detail:'年轻人...'},
                          {id:'04', detail:'老龄化社会的...'},
                        ]
                      }

                      render() {
                        // console.log('信息来自Detail  ', this.props.match)
                        // console.log('信息来自Detail  ', this.props.match.params.id)
                         const {params:{id, title}} = this.props.match   // 多重解构赋值 
                        // ++++++++++++++调试的数据++++++++++++++++++++++++++++++++++++++++++++++++++++++++++
                        // const {params:{id, title}, url} = this.props.match   // 多重解构赋值
                        // console.log('信息来自Detail\n', '接收的数据为：\n', id, title, '\nurl:', url)
                        //   信息来自Detail
                        //   接收的数据为：
                        //   03 News 3 
                        //   url: /home/news/detail/03/News 3
                        // ++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++
                         const {newsDetail} = this.state 
                        // 根据 id 参数匹配对应的新闻详情数据
                         const currentNewsDetail = newsDetail.find(news => news.id === id); 
                        // currentNewsDetail 为 {id: '02', detail: '新闻详情2'}
                        
                        return (
                          <div>
                            <div className="list-group">
                              <div href="#" className="list-group-item list-group-item-action">
                                 {currentNewsDetail ? <ul>
                                                        <li>新闻ID:{currentNewsDetail.id}</li>
                                                        <li>标题:{title}</li>
                                                        <li>{currentNewsDetail.detail}</li>
                                                      </ul>
                                                    : <div>无</div>
                                } 
                              </div>
                            </div>
                          </div>
                        )
                      }
                    }
                    ```
    -   [x] [87 087\_尚硅谷\_react教程\_向路由组件传递search参数\_Duration-16Min](https://www.bilibili.com/video/BV1wy4y1D7JT/?p=87 "87 087_尚硅谷_react教程_向路由组件传递search参数_Duration-16Min")
        -   \[笔记]

            ![](../image/image_r9IS2YyE1R.png)
            -   示例：(C)路由组件传参方式2：`location.search` \[,[\[JS库\]query-string](\[JS库]query-string_pPtrHSc9DMBMuCam24W7T6.md "\[JS库]query-string").parse()]

                ![](../image/2023-23-25-1812_oj087IGDuf.gif)
                -   `src/pages/Home/News/News.jsx`
                    ```react&#x20;jsx
                    import React, { Component } from 'react'
                    import { Link, Route } from 'react-router-dom'
                    //
                    import Detail from './Detail/Detail'
                    //
                    export default class News extends Component {
                      // 模拟数据
                      state = {
                        newsArray:[
                          {id:"01", title:'朝鲜核问题'},
                          {id:"02", title:'伊朗核问题'},
                          {id:"03", title:'新闻3'},
                          {id:"04", title:'新闻4'},
                        ]
                      }

                      render() {
                        return (
                          <div>
                            <div className="list-group">
                              {/* 设置路由链接 */}
                              {/* <Link className='list-group-item list-group-item-action' to='/home/news/detail' >新闻1</Link> */}
                              {
                                this.state.newsArray.map((newsObj)=>{

                                  // 路由组件通过params传递参数 ++++++++++++++++++++++++++++++++++++++++++
                                  // return <Link key={newsObj.id} className='list-group-item list-group-item-action' 
                                  //   // to={`/home/news/detail/${newsObj.id}/${newsObj.title}`}>   {/* 路由组件传递 一个 params 参数 */}
                                  //   to={`/home/news/detail/${newsObj.id}/${newsObj.title}`}>      {/* 路由组件传递 两个params 参数 */}
                                  //   {newsObj.title}
                                  // </Link> 
                                  // ++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++
                                  // 路由组件通过search传递参数 +++++++++++++++++++++++++++++++++++++++++++
                                      return <Link key={newsObj.id} className='list-group-item list-group-item-action'
                                            to={`/home/news/detail/?id=${newsObj.id}&title=${newsObj.title}`}>
                                      {newsObj.title}
                                     </Link> 
                                })
                              }
                            </div>
                            <hr/>
                            <div>
                              {/* 注册路由 */}
                              {/* 路由组件通过params传递参数 ++++++++++++++++++++++++++++++++++++++++++ */}
                              {/* 接收上面Link传递的 params 参数 */}
                              {/* 接收一个 params 参数 */}
                              {/* <Route path={`/home/news/detail/:id/`} component={Detail}></Route>   */}
                              {/* 接收两个 params 参数 */}
                              {/* <Route path={`/home/news/detail/:id/:title/`} component={Detail}></Route> */}

                              {/* 路由组件通过search传递参数 +++++++++++++++++++++++++++++++++++++++++++ */}
                                   <Route path={`/home/news/detail/`} component={Detail}></Route> 
                            </div>
                          </div>
                        )
                      }
                    }
                    ```
                -   `src/pages/Home/News/Detail/Detail.jsx`
                    ```react&#x20;jsx
                    import React, { Component } from 'react'
                     import qs from 'query-string' 

                    export default class Detail extends Component {
                      // 模拟从DB获取的数据
                      state = {
                        newsDetail:[
                          {id:'01', detail:'核问题是指自1990年代朝鲜民主主义人民共和国...'},
                          {id:'02', detail:'伊朗核问题，简称伊核问题，是伊朗于1950年起开发核工业所引发的国际问题...'},
                          {id:'03', detail:'年轻人...'},
                          {id:'04', detail:'老龄化社会的...'},
                        ]
                      }

                      render() {
                        // 路由组件通过params传递参数 ++++++++++++++++++++++++++++++++++++++++++
                        // // console.log('信息来自Detail  ', this.props.match)
                        // // console.log('信息来自Detail  ', this.props.match.params.id)
                        // const {params:{id, title}} = this.props.match   // 多重解构赋值
                        // // ++++++++++++++调试的数据++++++++++++++++++++++++++++++++++++++++++
                        // // const {params:{id, title}, url} = this.props.match   // 多重解构赋值
                        // // console.log('信息来自Detail\n', '接收的数据为：\n', id, title, '\nurl:', url)
                        // //   信息来自Detail
                        // //   接收的数据为：
                        // //   03 News 3 
                        // //   url: /home/news/detail/03/News 3

                        // 路由组件通过search传递参数 ++++++++++++++++++++++++++++++++++++++++++
                          const {search} = this.props.location  // >>> ?id=02&title=伊朗核问题
                         const {id, title} = qs.parse(search)  // 解构赋值   
                        // 路由组件通过xxxx传递参数 ++++++++++++++++++++++++++++++++++++++++++

                        
                        const {newsDetail} = this.state
                        // 根据 id 参数匹配对应的新闻详情数据
                        const currentNewsDetail = newsDetail.find(news => news.id === id);
                        // currentNewsDetail 为 {id: '02', detail: '新闻详情2'}
                        
                        return (
                          <div>
                            <div className="list-group">
                               <div href="#" className="list-group-item list-group-item-action">
                                {currentNewsDetail ? <ul>
                                                        <li>新闻ID:{currentNewsDetail.id}</li>
                                                        <li>标题:{title}</li>
                                                        <li>{currentNewsDetail.detail}</li>
                                                      </ul>
                                                    : <div>无</div>
                                }
                              </div> 
                            </div>
                          </div>
                        )
                      }
                    }
                    ```


    -   [x] [88 088\_尚硅谷\_react教程\_向路由组件传递state参数\_Duration-18Min](https://www.bilibili.com/video/BV1wy4y1D7JT/?p=88 "88 088_尚硅谷_react教程_向路由组件传递state参数_Duration-18Min")
        -   \[笔记]

            ![](../image/Snipaste_2023-05-07_13-15-59_rzuxaoYvaw.png)
            -   示例：(C)路由组件传参方式3：`location.state` \[`location.pathname`]
                -   `src/pages/Home/News/News.jsx`
                    ```react&#x20;jsx
                    import React, { Component } from 'react'
                    import { Link, Route } from 'react-router-dom'
                    //
                    import Detail from './Detail/Detail'
                    //
                    export default class News extends Component {
                      // 模拟数据
                      state = {
                        newsArray:[
                          {id:"01", title:'朝鲜核问题'},
                          {id:"02", title:'伊朗核问题'},
                          {id:"03", title:'新闻3'},
                          {id:"04", title:'新闻4'},
                        ]
                      }

                      render() {
                        return (
                          <div>
                            <div className="list-group">
                              {/* 设置路由链接 */}
                              {/* <Link className='list-group-item list-group-item-action' to='/home/news/detail' >新闻1</Link> */}
                              {
                                this.state.newsArray.map((newsObj)=>{

                                  // 路由组件通过params传递参数 ++++++++++++++++++++++++++++++++++++++++++
                                  // return <Link key={newsObj.id} className='list-group-item list-group-item-action' 
                                  //   // to={`/home/news/detail/${newsObj.id}/${newsObj.title}`}>   {/* 路由组件传递 一个 params 参数 */}
                                  //   to={`/home/news/detail/${newsObj.id}/${newsObj.title}`}>      {/* 路由组件传递 两个params 参数 */}
                                  //   {newsObj.title}
                                  // </Link> 
                                  // ++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++
                                  // 路由组件通过search传递参数 +++++++++++++++++++++++++++++++++++++++++++
                                  // return <Link key={newsObj.id} className='list-group-item list-group-item-action'
                                  //         to={`/home/news/detail/?id=${newsObj.id}&title=${newsObj.title}`}>
                                  //   {newsObj.title}
                                  // </Link>
                                  // ++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++
                                  // 路由组件通过state传递参数 ++++++++++++++++++++++++++++++++++++++++++++
                                   return <Link key={newsObj.id} className='list-group-item list-group-item-action'
                                          to={{pathname:'/home/news/detail/', state:{id:newsObj.id, title:newsObj.title}}}>
                                    {newsObj.title}
                                  </Link> 
                                })
                              }
                            </div>
                            <hr/>
                            <div>
                              {/* 注册路由 */}
                              {/* 路由组件通过params传递参数 ++++++++++++++++++++++++++++++++++++++++++ */}
                              {/* 接收上面Link传递的 params 参数 */}
                              {/* 接收一个 params 参数 */}
                              {/* <Route path={`/home/news/detail/:id/`} component={Detail}></Route>   */}
                              {/* 接收两个 params 参数 */}
                              {/* <Route path={`/home/news/detail/:id/:title/`} component={Detail}></Route> */}

                              {/* 路由组件通过search传递参数 +++++++++++++++++++++++++++++++++++++++++++ */}
                                  {/* <Route path={`/home/news/detail/`} component={Detail}></Route> */}

                              {/* 路由组件通过state传递参数 +++++++++++++++++++++++++++++++++++++++++++ */}
                               <Route path={`/home/news/detail/`} component={Detail}></Route> 
                            </div>
                          </div>
                        )
                      }
                    }
                    ```
                -   `src/pages/Home/News/Detail/Detail.jsx`
                    ```react&#x20;jsx
                    import React, { Component } from 'react'
                    // import qs from 'query-string'

                    export default class Detail extends Component {
                      // 模拟从DB获取的数据
                      state = {
                        newsDetail:[
                          {id:'01', detail:'核问题是指自1990年代朝鲜民主主义人民共和国...'},
                          {id:'02', detail:'伊朗核问题，简称伊核问题，是伊朗于1950年起开发核工业所引发的国际问题...'},
                          {id:'03', detail:'年轻人...'},
                          {id:'04', detail:'老龄化社会的...'},
                        ]
                      }

                      render() {
                        // 路由组件通过params传递参数 ++++++++++++++++++++++++++++++++++++++++++
                        // // console.log('信息来自Detail  ', this.props.match)
                        // // console.log('信息来自Detail  ', this.props.match.params.id)
                        // const {params:{id, title}} = this.props.match   // 多重解构赋值
                        // // ++++++++++++++调试的数据++++++++++++++++++++++++++++++++++++++++++
                        // // const {params:{id, title}, url} = this.props.match   // 多重解构赋值
                        // // console.log('信息来自Detail\n', '接收的数据为：\n', id, title, '\nurl:', url)
                        // //   信息来自Detail
                        // //   接收的数据为：
                        // //   03 News 3 
                        // //   url: /home/news/detail/03/News 3

                        //  路由组件通过search传递参数 ++++++++++++++++++++++++++++++++++++++++++
                        //  const {search} = this.props.location  // >>> ?id=02&title=伊朗核问题
                        //  const {id, title} = qs.parse(search)  // 解构赋值  

                        // 路由组件通过state传递参数 ++++++++++++++++++++++++++++++++++++++++++
                         const {id, title} = this.props.location.state  // >> {id: '02', title: '伊朗核问题'} 
                        
                        const {newsDetail} = this.state
                        // 根据 id 参数匹配对应的新闻详情数据
                        const currentNewsDetail = newsDetail.find(news => news.id === id);
                        // currentNewsDetail 为 {id: '02', detail: '新闻详情2'}
                        
                        return (
                          <div>
                            <div className="list-group">
                              <div href="#" className="list-group-item list-group-item-action">
                                {currentNewsDetail ? <ul>
                                                        <li>新闻ID:{currentNewsDetail.id}</li>
                                                        <li>标题:{title}</li>
                                                        <li>{currentNewsDetail.detail}</li>
                                                      </ul>
                                                    : <div>无</div>
                                }
                              </div>
                            </div>
                          </div>
                        )
                      }
                    }


                    ```

    -   [x] [89 089\_尚硅谷\_react教程\_总结路由参数\_Duration-2Min](https://www.bilibili.com/video/BV1wy4y1D7JT/?p=89 "89 089_尚硅谷_react教程_总结路由参数_Duration-2Min")
        -   \[笔记]`replace`[¶](https://www.bilibili.com/video/BV1wy4y1D7JT?t=254.0\&p=90 "¶")
            -   示例：整个路由传参的示例代码汇总
                -   src/pages/Home/News/News.jsx
                    ```react&#x20;jsx
                    import React, { Component } from 'react'
                    import { Link, Route } from 'react-router-dom'
                    //
                    import Detail from './Detail/Detail'
                    //
                    export default class News extends Component {
                      // 模拟数据
                      state = {
                        newsArray:[
                          {id:"01", title:'朝鲜核问题'},
                          {id:"02", title:'伊朗核问题'},
                          {id:"03", title:'新闻3'},
                          {id:"04", title:'新闻4'},
                        ]
                      }
                      show = () =>{
                        console.log('123')
                      }
                      render() {
                        return (
                          <div>
                            <div className="list-group ">
                              {/* 设置路由链接 */}
                              {/* <Link className='list-group-item list-group-item-action' to='/home/news/detail' >新闻1</Link> */}
                              {
                                this.state.newsArray.map((newsObj)=>{

                                  // 路由组件通过params传递参数 ++++++++++++++++++++++++++++++++++++++++++
                                  return (
                                    <div key={newsObj.id} className='list-group'>
                                      <div className='  list-group-item d-flex'>
                                        <Link className=' flex-grow-1' 
                                          // to={`/home/news/detail/${newsObj.id}/${newsObj.title}`}>   {/* 路由组件传递 一个 params 参数 */}
                                          to={`/home/news/detail/${newsObj.id}/${newsObj.title}`}>      {/* 路由组件传递 两个params 参数 */}
                                            {newsObj.title}
                                        </Link> 
                                      </div>
                                    </div>
                                    
                                    )
                                  // 路由组件通过search传递参数 +++++++++++++++++++++++++++++++++++++++++++
                                  // return <Link key={newsObj.id} className='list-group-item list-group-item-action'
                                  //         to={`/home/news/detail/?id=${newsObj.id}&title=${newsObj.title}`}>
                                  //   {newsObj.title}
                                  // </Link>
                                  // 路由组件通过state传递参数 ++++++++++++++++++++++++++++++++++++++++++++
                                  // return <Link key={newsObj.id} className='list-group-item list-group-item-action'
                                  //         to={{pathname:'/home/news/detail/', state:{id:newsObj.id, title:newsObj.title}}}>
                                  //   {newsObj.title}
                                  // </Link>
                                })
                              }
                            </div>
                            <hr/>
                            <div>
                              {/* 注册路由 */}
                              {/* 路由组件通过params传递参数 ++++++++++++++++++++++++++++++++++++++++++ */}
                              {/* 接收上面Link传递的 params 参数 */}
                              {/* 接收一个 params 参数 */}
                              <Route path={`/home/news/detail/:id/`} component={Detail}></Route>  
                              {/* 接收两个 params 参数 */}
                              {/* <Route path={`/home/news/detail/:id/:title/`} component={Detail}></Route> */}

                              {/* 路由组件通过search传递参数 +++++++++++++++++++++++++++++++++++++++++++ */}
                                  {/* <Route path={`/home/news/detail/`} component={Detail}></Route> */}

                              {/* 路由组件通过state传递参数 +++++++++++++++++++++++++++++++++++++++++++ */}
                              {/* <Route path={`/home/news/detail/`} component={Detail}></Route> */}
                            </div>
                          </div>
                        )
                      }
                    }


                    ```
                -   src/pages/Home/News/Detail/Detail.jsx
                    ```react&#x20;jsx
                    import React, { Component } from 'react'
                    // import qs from 'query-string'

                    export default class Detail extends Component {
                      // 模拟从DB获取的数据
                      state = {
                        newsDetail:[
                          {id:'01', detail:'核问题是指自1990年代朝鲜民主主义人民共和国...'},
                          {id:'02', detail:'伊朗核问题，简称伊核问题，是伊朗于1950年起开发核工业所引发的国际问题...'},
                          {id:'03', detail:'年轻人...'},
                          {id:'04', detail:'老龄化社会的...'},
                        ]
                      }

                      render() {
                        // 路由组件通过params传递参数 ++++++++++++++++++++++++++++++++++++++++++
                        const {params:{id, title}} = this.props.match   // 多重解构赋值
                        
                        // ++++++++++++++调试的数据++++++++++++++++++++++++++++++++++++++++++
                        // console.log('信息来自Detail  ', this.props.match)
                        // console.log('信息来自Detail  ', this.props.match.params.id)
                        // const {params:{id, title}, url} = this.props.match   // 多重解构赋值
                        // console.log('信息来自Detail\n', '接收的数据为：\n', id, title, '\nurl:', url)
                        //   // 信息来自Detail
                        //   // 接收的数据为：
                        //   // 03 News 3 
                        //   // url: /home/news/detail/03/News 3

                        //  路由组件通过search传递参数 ++++++++++++++++++++++++++++++++++++++++++
                        //  const {search} = this.props.location  // >>> ?id=02&title=伊朗核问题
                        //  const {id, title} = qs.parse(search)  // 解构赋值  

                        // 路由组件通过state传递参数 ++++++++++++++++++++++++++++++++++++++++++
                        // const {id, title} = this.props.location.state  // >> {id: '02', title: '伊朗核问题'}
                        // ---------------------------------
                        // 查找state 匹配的id news
                        const {newsDetail} = this.state
                        // // 根据 id 参数匹配对应的新闻详情数据
                        const currentNewsDetail = newsDetail.find(news => news.id === id);
                        // // currentNewsDetail 为 {id: '02', detail: '新闻详情2'}
                        
                        return (
                          <div>
                            <div className="list-group">
                              <div href="#" className="list-group-item list-group-item-action">
                                {currentNewsDetail ? <ul>
                                                        <li>新闻ID:{currentNewsDetail.id}</li>
                                                        <li>标题:{title}</li>
                                                        <li>{currentNewsDetail.detail}</li>
                                                      </ul>
                                                    : <div>无</div>
                                }
                              </div>
                            </div>
                          </div>
                        )
                      }
                    }

                    ```
    -   [x] [90 090\_尚硅谷\_react教程\_push与repalce\_Duration-7Min](https://www.bilibili.com/video/BV1wy4y1D7JT/?p=90 "90 090_尚硅谷_react教程_push与repalce_Duration-7Min")
    -   [x] [91 091\_尚硅谷\_react教程\_编程式路由导航\_Duration-24Min](https://www.bilibili.com/video/BV1wy4y1D7JT/?p=91 "91 091_尚硅谷_react教程_编程式路由导航_Duration-24Min")
        -   \[笔记]
            -   示例：调整样式以及使用：路由组件通过params传递参数 \[编程式路由导航,`history``replace(path,state)``push(path,state)`[¶](https://www.bilibili.com/video/BV1wy4y1D7JT?t=928.2\&p=91 "¶"),函数柯里化]

                ![](../image/2023-23-28-2112_tnmBk0HXoY.gif)
                -   示例：函数的柯里化
                    ```react&#x20;jsx
                    import React, { Component } from 'react'
                    import { Link, Route } from 'react-router-dom'
                    //
                    import Detail from './Detail/Detail'
                    //
                    export default class News extends Component {
                      // 模拟数据
                      state = {
                        newsArray:[
                          {id:"01", title:'朝鲜核问题'},
                          {id:"02", title:'伊朗核问题'},
                          {id:"03", title:'新闻3'},
                          {id:"04", title:'新闻4'},
                        ]
                      }
                       showReplace = (id, title) =>{
                        return () => {
                          // console.log(`/home/news/detail/${id}/${title}`)
                          this.props.history.replace(`/home/news/detail/${id}/${title}`)
                        }
                      } 
                      render() {
                        return (
                          <div>
                            <div className="list-group ">
                              {/* 设置路由链接 */}
                              {/* <Link className='list-group-item list-group-item-action' to='/home/news/detail' >新闻1</Link> */}
                              {
                                this.state.newsArray.map((newsObj)=>{

                                  // 路由组件通过params传递参数 ++++++++++++++++++++++++++++++++++++++++++
                                  return (
                                    <div key={newsObj.id} className='list-group'>
                                      <div className='  list-group-item d-flex'>
                                        <Link className=' flex-grow-1' 
                                          // to={`/home/news/detail/${newsObj.id}/${newsObj.title}`}>   {/* 路由组件传递 一个 params 参数 */}
                                          to={`/home/news/detail/${newsObj.id}/${newsObj.title}`}>      {/* 路由组件传递 两个params 参数 */}
                                            {newsObj.title}
                                        </Link> 
                                        <div onClick={this.showReplace} className='fw-light lh-sm btn btn-info b-0 '>push(增加记录)</div>
                                        <div  onClick={this.showReplace(newsObj.id, newsObj.title)}  className='fw-light lh-sm btn btn-primary ms-1'>replace(替换记录)</div>
                                      </div>
                                    </div>
                                    
                                    )
                                  // 路由组件通过search传递参数 +++++++++++++++++++++++++++++++++++++++++++
                                  // return <Link key={newsObj.id} className='list-group-item list-group-item-action'
                                  //         to={`/home/news/detail/?id=${newsObj.id}&title=${newsObj.title}`}>
                                  //   {newsObj.title}
                                  // </Link>
                                  // 路由组件通过state传递参数 ++++++++++++++++++++++++++++++++++++++++++++
                                  // return <Link key={newsObj.id} className='list-group-item list-group-item-action'
                                  //         to={{pathname:'/home/news/detail/', state:{id:newsObj.id, title:newsObj.title}}}>
                                  //   {newsObj.title}
                                  // </Link>
                                })
                              }
                            </div>
                            <hr/>
                            <div>
                              {/* 注册路由 */}
                              {/* 路由组件通过params传递参数 ++++++++++++++++++++++++++++++++++++++++++ */}
                              {/* 接收上面Link传递的 params 参数 */}
                              {/* 接收一个 params 参数 */}
                              <Route path={`/home/news/detail/:id/`} component={Detail}></Route>  
                              {/* 接收两个 params 参数 */}
                              {/* <Route path={`/home/news/detail/:id/:title/`} component={Detail}></Route> */}

                              {/* 路由组件通过search传递参数 +++++++++++++++++++++++++++++++++++++++++++ */}
                                  {/* <Route path={`/home/news/detail/`} component={Detail}></Route> */}

                              {/* 路由组件通过state传递参数 +++++++++++++++++++++++++++++++++++++++++++ */}
                              {/* <Route path={`/home/news/detail/`} component={Detail}></Route> */}
                            </div>
                          </div>
                        )
                      }
                    }
                    ```
                -   示例：通过函数式路由，携带params传递参数
                    -   src/pages/Home/News/News.jsx
                        ```react&#x20;jsx
                        import React, { Component } from 'react'
                        import { Link, Route } from 'react-router-dom'
                        //
                        import Detail from './Detail/Detail'
                        //
                        export default class News extends Component {
                          // 模拟数据
                          state = {
                            newsArray:[
                              {id:"01", title:'朝鲜核问题'},
                              {id:"02", title:'伊朗核问题'},
                              {id:"03", title:'新闻3'},
                              {id:"04", title:'新闻4'},
                            ]
                          }
                           showReplace = (id, title) =>{
                            return () => {
                              // params 传参 replace跳转
                              this.props.history.replace(`/home/news/detail/${id}/${title}`)
                              // search 传参 replace跳转
                              // // this.props.history.replace(`/home/news/detail/?id=${id}&title=${title}`)
                              // this.props.history.push(`/home/news/detail/?id=${id}&title=${title}`)
                            }
                          }
                          showPush = (id, title) =>{
                            return () =>{
                              // params 传参 push跳转
                              this.props.history.push(`/home/news/detail/${id}/${title}`)
                              // // search 传参 replace跳转
                              // this.props.history.push(`/home/news/detail/?id=${id}&title=${title}`)
                            }
                          } 
                          render() {
                            return (
                              <div>
                                <div className="list-group ">
                                  {/* 设置路由链接 */}
                                  {/* <Link className='list-group-item list-group-item-action' to='/home/news/detail' >新闻1</Link> */}
                                  {
                                    this.state.newsArray.map((newsObj)=>{

                                      // 路由组件通过params传递参数 ++++++++++++++++++++++++++++++++++++++++++
                                      // return <Link key={newsObj.id} className='list-group-item list-group-item-action' 
                                      //   // to={`/home/news/detail/${newsObj.id}/${newsObj.title}`}>   {/* 路由组件传递 一个 params 参数 */}
                                      //   to={`/home/news/detail/${newsObj.id}/${newsObj.title}`}>      {/* 路由组件传递 两个params 参数 */}
                                      //   {newsObj.title}
                                      // </Link> 
                                      // 路由组件通过search传递参数 +++++++++++++++++++++++++++++++++++++++++++
                                      // return <Link key={newsObj.id} className='list-group-item list-group-item-action'
                                      //         to={`/home/news/detail/?id=${newsObj.id}&title=${newsObj.title}`}>
                                      //   {newsObj.title}
                                      // </Link>
                                      // 路由组件通过state传递参数 ++++++++++++++++++++++++++++++++++++++++++++
                                      // return <Link key={newsObj.id} className='list-group-item list-group-item-action'
                                      //         to={{pathname:'/home/news/detail/', state:{id:newsObj.id, title:newsObj.title}}}>
                                      //   {newsObj.title}
                                      // </Link>
                                      // 编程式路由
                                       return (
                                        <div key={newsObj.id} className='list-group'>
                                          <div className='  list-group-item d-flex'>
                                            <Link className=' flex-grow-1' 
                                              // to={`/home/news/detail/${newsObj.id}/${newsObj.title}`}>   {/* 路由组件传递 一个 params 参数 */}
                                              to={`/home/news/detail/${newsObj.id}/${newsObj.title}`}>      {/* 路由组件传递 两个params 参数 */}
                                                {newsObj.title}
                                            </Link> 
                                            <div onClick={this.showPush(newsObj.id, newsObj.title)}className='fw-light lh-sm btn btn-info b-0 '>push(增加记录)</div>
                                            <div onClick={this.showReplace(newsObj.id, newsObj.title)} className='fw-light lh-sm btn btn-primary ms-1'>replace(替换记录)</div>
                                          </div>
                                        </div>
                                        
                                        ) 
                                    })
                                  }
                                </div>
                                <hr/>
                                <div>
                                  {/* 注册路由 */}
                                  {/* 路由组件通过params传递参数 ++++++++++++++++++++++++++++++++++++++++++ */}
                                  {/* 接收上面Link传递的 params 参数 */}
                                  {/* 接收一个 params 参数 */}
                                  {/* <Route path={`/home/news/detail/:id/`} component={Detail}></Route>   */}
                                  {/* 接收两个 params 参数 */}
                                  <Route path={`/home/news/detail/:id/:title/`} component={Detail}></Route>

                                  {/* 路由组件通过search传递参数 +++++++++++++++++++++++++++++++++++++++++++ */}
                                      {/* <Route path={`/home/news/detail/`} component={Detail}></Route> */}

                                  {/* 路由组件通过state传递参数 +++++++++++++++++++++++++++++++++++++++++++ */}
                                  {/* <Route path={`/home/news/detail/`} component={Detail}></Route> */}
                                </div>
                              </div>
                            )
                          }
                        }
                        ```
                    -   src/pages/Home/News/Detail/Detail.jsx
                        ```react&#x20;jsx
                        import React, { Component } from 'react'
                        // import qs from 'query-string'

                        export default class Detail extends Component {
                          // 模拟从DB获取的数据
                          state = {
                            newsDetail:[
                              {id:'01', detail:'核问题是指自1990年代朝鲜民主主义人民共和国...'},
                              {id:'02', detail:'伊朗核问题，简称伊核问题，是伊朗于1950年起开发核工业所引发的国际问题...'},
                              {id:'03', detail:'年轻人...'},
                              {id:'04', detail:'老龄化社会的...'},
                            ]
                          }

                          render() {
                            // 路由组件通过params传递参数 ++++++++++++++++++++++++++++++++++++++++++
                            const {params:{id, title}} = this.props.match   // 多重解构赋值

                            // ++++++++++++++调试的数据++++++++++++++++++++++++++++++++++++++++++
                            // console.log('信息来自Detail  ', this.props.match)
                            // console.log('信息来自Detail  ', this.props.match.params.id)
                            // const {params:{id, title}, url} = this.props.match   // 多重解构赋值
                            // console.log('信息来自Detail\n', '接收的数据为：\n', id, title, '\nurl:', url)
                            //   // 信息来自Detail
                            //   // 接收的数据为：
                            //   // 03 News 3 
                            //   // url: /home/news/detail/03/News 3

                            //  路由组件通过search传递参数 ++++++++++++++++++++++++++++++++++++++++++
                            //  const {search} = this.props.location  // >>> ?id=02&title=伊朗核问题
                            //  const {id, title} = qs.parse(search)  // 解构赋值  

                            // 路由组件通过state传递参数 ++++++++++++++++++++++++++++++++++++++++++
                            // const {id, title} = this.props.location.state  // >> {id: '02', title: '伊朗核问题'}
                            // ---------------------------------
                            // 获取 从数据库(模拟)传来的数据 
                            const {newsDetail} = this.state
                            // // 根据 id 参数匹配对应的新闻详情数据
                            const currentNewsDetail = newsDetail.find(news => news.id === id);
                            // // currentNewsDetail 为 {id: '02', detail: '新闻详情2'}
                            
                            return (
                              <div>
                                <div className="list-group">
                                  <div href="#" className="list-group-item list-group-item-action">
                                    {currentNewsDetail ? <ul>
                                                            <li>新闻ID:{currentNewsDetail.id}</li>
                                                            <li>标题:{title}</li>
                                                            <li>{currentNewsDetail.detail}</li>
                                                          </ul>
                                                        : <div>无</div>
                                    }
                                  </div>
                                </div>
                              </div>
                            )
                          }
                        }


                        ```
                -   示例：通过函数式路由，携带search传递参数
                    -   src/pages/Home/News/News.jsx
                        ```react&#x20;jsx
                        import React, { Component } from 'react'
                        import { Link, Route } from 'react-router-dom'
                        //
                        import Detail from './Detail/Detail'
                        //
                        export default class News extends Component {
                          // 模拟数据
                          state = {
                            newsArray:[
                              {id:"01", title:'朝鲜核问题'},
                              {id:"02", title:'伊朗核问题'},
                              {id:"03", title:'新闻3'},
                              {id:"04", title:'新闻4'},
                            ]
                          }
                          showReplace = (id, title) =>{
                            return () => {
                              // // params 传参 replace跳转
                              // this.props.history.replace(`/home/news/detail/${id}/${title}`)
                              // search 传参 replace跳转
                               this.props.history.replace(`/home/news/detail/?id=${id}&title=${title}`)
                            }
                          }
                          showPush = (id, title) =>{
                            return () =>{
                              // // params 传参 push跳转
                              // this.props.history.push(`/home/news/detail/${id}/${title}`)
                              // // search 传参 replace跳转
                              this.props.history.push(`/home/news/detail/?id=${id}&title=${title}`)
                              // state 传参 replace跳转
                              // pathname:'/home/news/detail/', state:{id:newsObj.id, title:newsObj.title}
                            }
                          }
                          render() {
                            return (
                              <div>
                                <div className="list-group ">
                                  {/* 设置路由链接 */}
                                  {/* <Link className='list-group-item list-group-item-action' to='/home/news/detail' >新闻1</Link> */}
                                  {
                                    this.state.newsArray.map((newsObj)=>{

                                      // 路由组件通过params传递参数 ++++++++++++++++++++++++++++++++++++++++++
                                      // return <Link key={newsObj.id} className='list-group-item list-group-item-action' 
                                      //   // to={`/home/news/detail/${newsObj.id}/${newsObj.title}`}>   {/* 路由组件传递 一个 params 参数 */}
                                      //   to={`/home/news/detail/${newsObj.id}/${newsObj.title}`}>      {/* 路由组件传递 两个params 参数 */}
                                      //   {newsObj.title}
                                      // </Link> 
                                      // 路由组件通过search传递参数 +++++++++++++++++++++++++++++++++++++++++++
                                      // return <Link key={newsObj.id} className='list-group-item list-group-item-action'
                                      //         to={`/home/news/detail/?id=${newsObj.id}&title=${newsObj.title}`}>
                                      //   {newsObj.title}
                                      // </Link>
                                      // 路由组件通过state传递参数 ++++++++++++++++++++++++++++++++++++++++++++
                                      // return <Link key={newsObj.id} className='list-group-item list-group-item-action'
                                      //         to={{pathname:'/home/news/detail/', state:{id:newsObj.id, title:newsObj.title}}}>
                                      //   {newsObj.title}
                                      // </Link>
                                      // 编程式路由
                                      return (
                                        <div key={newsObj.id} className='list-group'>
                                          <div className='  list-group-item d-flex'>
                                            <Link className=' flex-grow-1' 
                                              to={`/home/news/detail/${newsObj.id}/${newsObj.title}`}>     
                                                {newsObj.title}
                                            </Link> 
                                            <div onClick={this.showPush(newsObj.id, newsObj.title)}className='fw-light lh-sm btn btn-info b-0 '>push(增加记录)</div>
                                            <div onClick={this.showReplace(newsObj.id, newsObj.title)} className='fw-light lh-sm btn btn-primary ms-1'>replace(替换记录)</div>
                                          </div>
                                        </div>
                                        
                                        )
                                    })
                                  }
                                </div>
                                <hr/>
                                <div>
                                  {/* 注册路由 */}
                                  {/* 路由组件通过params传递参数 ++++++++++++++++++++++++++++++++++++++++++ */}
                                  {/* 接收上面Link传递的 params 参数 */}
                                  {/* 接收一个 params 参数 */}
                                  {/* <Route path={`/home/news/detail/:id/`} component={Detail}></Route>   */}
                                  {/* 接收两个 params 参数 */}
                                  {/* <Route path={`/home/news/detail/:id/:title/`} component={Detail}></Route> */}

                                  {/* 路由组件通过search传递参数 +++++++++++++++++++++++++++++++++++++++++++ */}
                                      <Route path={`/home/news/detail/`} component={Detail}></Route>

                                  {/* 路由组件通过state传递参数 +++++++++++++++++++++++++++++++++++++++++++ */}
                                  {/* <Route path={`/home/news/detail/`} component={Detail}></Route> */}
                                </div>
                              </div>
                            )
                          }
                        }

                        ```
                    -   src/pages/Home/News/Detail/Detail.jsx
                        ```react&#x20;jsx
                        import React, { Component } from 'react'
                        import qs from 'query-string'

                        export default class Detail extends Component {
                          // 模拟从DB获取的数据
                          state = {
                            newsDetail:[
                              {id:'01', detail:'核问题是指自1990年代朝鲜民主主义人民共和国...'},
                              {id:'02', detail:'伊朗核问题，简称伊核问题，是伊朗于1950年起开发核工业所引发的国际问题...'},
                              {id:'03', detail:'年轻人...'},
                              {id:'04', detail:'老龄化社会的...'},
                            ]
                          }

                          render() {
                            // 路由组件通过params传递参数 ++++++++++++++++++++++++++++++++++++++++++
                            // const {params:{id, title}} = this.props.match   // 多重解构赋值

                            // ++++++++++++++调试的数据++++++++++++++++++++++++++++++++++++++++++
                            // console.log('信息来自Detail  ', this.props.match)
                            // console.log('信息来自Detail  ', this.props.match.params.id)
                            // const {params:{id, title}, url} = this.props.match   // 多重解构赋值
                            // console.log('信息来自Detail\n', '接收的数据为：\n', id, title, '\nurl:', url)
                            //   // 信息来自Detail
                            //   // 接收的数据为：
                            //   // 03 News 3 
                            //   // url: /home/news/detail/03/News 3

                            //  路由组件通过search传递参数 ++++++++++++++++++++++++++++++++++++++++++
                             const {search} = this.props.location  // >>> ?id=02&title=伊朗核问题
                             const {id, title} = qs.parse(search)  // 解构赋值  

                            // 路由组件通过state传递参数 ++++++++++++++++++++++++++++++++++++++++++
                            // const {id, title} = this.props.location.state  // >> {id: '02', title: '伊朗核问题'}
                            // ---------------------------------
                            // 获取 从数据库(模拟)传来的数据 
                            const {newsDetail} = this.state
                            // // 根据 id 参数匹配对应的新闻详情数据
                            const currentNewsDetail = newsDetail.find(news => news.id === id);
                            // // currentNewsDetail 为 {id: '02', detail: '新闻详情2'}
                            
                            return (
                              <div>
                                <div className="list-group">
                                  <div href="#" className="list-group-item list-group-item-action">
                                    {currentNewsDetail ? <ul>
                                                            <li>新闻ID:{currentNewsDetail.id}</li>
                                                            <li>标题:{title}</li>
                                                            <li>{currentNewsDetail.detail}</li>
                                                          </ul>
                                                        : <div>无</div>
                                    }
                                  </div>
                                </div>
                              </div>
                            )
                          }
                        }


                        ```
                -   示例：通过函数式路由，携带state传递参数[¶](https://www.bilibili.com/video/BV1wy4y1D7JT?t=1005.0\&p=91 "¶")
                    -   src/pages/Home/News/News.jsx
                        ```react&#x20;jsx
                        import React, { Component } from 'react'
                        import { Link, Route } from 'react-router-dom'
                        //
                        import Detail from './Detail/Detail'
                        //
                        export default class News extends Component {
                          // 模拟数据
                          state = {
                            newsArray:[
                              {id:"01", title:'朝鲜核问题'},
                              {id:"02", title:'伊朗核问题'},
                              {id:"03", title:'新闻3'},
                              {id:"04", title:'新闻4'},
                            ]
                          }
                          showReplace = (id, title) =>{
                            return () => {
                              // // params 传参 replace跳转
                              // this.props.history.replace(`/home/news/detail/${id}/${title}`)
                              // // search 传参 replace跳转
                              //  this.props.history.replace(`/home/news/detail/?id=${id}&title=${title}`)
                              // state 传参 replace跳转
                              this.props.history.replace(`/home/news/detail/`, {id:id, title:title})

                            }
                          }
                          showPush = (id, title) =>{
                            return () =>{
                              // // params 传参 push跳转
                              // this.props.history.push(`/home/news/detail/${id}/${title}`)
                              // // search 传参 replace跳转
                              // this.props.history.push(`/home/news/detail/?id=${id}&title=${title}`)
                              // state 传参 replace跳转
                              this.props.history.push(`/home/news/detail/`, {id:id, title:title})
                            }
                          }
                          render() {
                            return (
                              <div>
                                <div className="list-group ">
                                  {/* 设置路由链接 */}
                                  {/* <Link className='list-group-item list-group-item-action' to='/home/news/detail' >新闻1</Link> */}
                                  {
                                    this.state.newsArray.map((newsObj)=>{

                                      // 路由组件通过params传递参数 ++++++++++++++++++++++++++++++++++++++++++
                                      // return <Link key={newsObj.id} className='list-group-item list-group-item-action' 
                                      //   // to={`/home/news/detail/${newsObj.id}/${newsObj.title}`}>   {/* 路由组件传递 一个 params 参数 */}
                                      //   to={`/home/news/detail/${newsObj.id}/${newsObj.title}`}>      {/* 路由组件传递 两个params 参数 */}
                                      //   {newsObj.title}
                                      // </Link> 
                                      // 路由组件通过search传递参数 +++++++++++++++++++++++++++++++++++++++++++
                                      // return <Link key={newsObj.id} className='list-group-item list-group-item-action'
                                      //         to={`/home/news/detail/?id=${newsObj.id}&title=${newsObj.title}`}>
                                      //   {newsObj.title}
                                      // </Link>
                                      // 路由组件通过state传递参数 ++++++++++++++++++++++++++++++++++++++++++++
                                      // return <Link key={newsObj.id} className='list-group-item list-group-item-action'
                                      //         to={{pathname:'/home/news/detail/', state:{id:newsObj.id, title:newsObj.title}}}>
                                      //   {newsObj.title}
                                      // </Link>
                                      // 编程式路由  +++++++++++++++++++++++++++++++++++++++++++++++++++++++++
                                      return (
                                        <div key={newsObj.id} className='list-group'>
                                          <div className='  list-group-item d-flex'>
                                            <Link className=' flex-grow-1' 
                                               to={{pathname:'/home/news/detail/', state:{id:newsObj.id, title:newsObj.title}}}>   
                                                {newsObj.title}
                                            </Link> 
                                            <div onClick={this.showPush(newsObj.id, newsObj.title)}className='fw-light lh-sm btn btn-info b-0 '>push(增加记录)</div>
                                            <div onClick={this.showReplace(newsObj.id, newsObj.title)} className='fw-light lh-sm btn btn-primary ms-1'>replace(替换记录)</div>
                                          </div>
                                        </div>
                                        
                                        )
                                    })
                                  }
                                </div>
                                <hr/>
                                <div>
                                  {/* 注册路由 */}
                                  {/* 路由组件通过params传递参数 ++++++++++++++++++++++++++++++++++++++++++ */}
                                  {/* 接收上面Link传递的 params 参数 */}
                                  {/* 接收一个 params 参数 */}
                                  {/* <Route path={`/home/news/detail/:id/`} component={Detail}></Route>   */}
                                  {/* 接收两个 params 参数 */}
                                  {/* <Route path={`/home/news/detail/:id/:title/`} component={Detail}></Route> */}

                                  {/* 路由组件通过search传递参数 +++++++++++++++++++++++++++++++++++++++++++ */}
                                      {/* <Route path={`/home/news/detail/`} component={Detail}></Route> */}

                                  {/* 路由组件通过state传递参数 +++++++++++++++++++++++++++++++++++++++++++ */}
                                  <Route path={`/home/news/detail/`} component={Detail}></Route>
                                </div>
                              </div>
                            )
                          }
                        }

                        ```
                    -   src/pages/Home/News/Detail/Detail.jsx
                        ```react&#x20;jsx
                        import React, { Component } from 'react'
                        // import qs from 'query-string'

                        export default class Detail extends Component {
                          // 模拟从DB获取的数据
                          state = {
                            newsDetail:[
                              {id:'01', detail:'核问题是指自1990年代朝鲜民主主义人民共和国...'},
                              {id:'02', detail:'伊朗核问题，简称伊核问题，是伊朗于1950年起开发核工业所引发的国际问题...'},
                              {id:'03', detail:'年轻人...'},
                              {id:'04', detail:'老龄化社会的...'},
                            ]
                          }

                          render() {
                            // 路由组件通过params传递参数 ++++++++++++++++++++++++++++++++++++++++++
                            // const {params:{id, title}} = this.props.match   // 多重解构赋值

                            // ++++++++++++++调试的数据++++++++++++++++++++++++++++++++++++++++++
                            // console.log('信息来自Detail  ', this.props.match)
                            // console.log('信息来自Detail  ', this.props.match.params.id)
                            // const {params:{id, title}, url} = this.props.match   // 多重解构赋值
                            // console.log('信息来自Detail\n', '接收的数据为：\n', id, title, '\nurl:', url)
                            //   // 信息来自Detail
                            //   // 接收的数据为：
                            //   // 03 News 3 
                            //   // url: /home/news/detail/03/News 3

                            //  路由组件通过search传递参数 ++++++++++++++++++++++++++++++++++++++++++
                            //  const {search} = this.props.location  // >>> ?id=02&title=伊朗核问题
                            //  const {id, title} = qs.parse(search)  // 解构赋值  

                            // 路由组件通过state传递参数 ++++++++++++++++++++++++++++++++++++++++++
                            const {id, title} = this.props.location.state  // >> {id: '02', title: '伊朗核问题'}
                            // ---------------------------------
                            // 获取 从数据库(模拟)传来的数据 
                            const {newsDetail} = this.state
                            // // 根据 id 参数匹配对应的新闻详情数据
                            const currentNewsDetail = newsDetail.find(news => news.id === id);
                            // // currentNewsDetail 为 {id: '02', detail: '新闻详情2'}
                            
                            return (
                              <div>
                                <div className="list-group">
                                  <div href="#" className="list-group-item list-group-item-action">
                                    {currentNewsDetail ? <ul>
                                                            <li>新闻ID:{currentNewsDetail.id}</li>
                                                            <li>标题:{title}</li>
                                                            <li>{currentNewsDetail.detail}</li>
                                                          </ul>
                                                        : <div>无</div>
                                    }
                                  </div>
                                </div>
                              </div>
                            )
                          }
                        }


                        ```
                -   示例：使用api实现前进后退  \[`goBack()``goForward()`,`go()`]

                    ![](../image/image_cheH56l1Sd.png)
                    -   示例：src/pages/Home/News/News.jsx
                        ```react&#x20;jsx
                        import React, { Component } from 'react'
                        import { Link, Route } from 'react-router-dom'
                        //
                        import Detail from './Detail/Detail'
                        //
                        export default class News extends Component {
                          // 模拟数据
                          state = {
                            newsArray:[
                              {id:"01", title:'朝鲜核问题'},
                              {id:"02", title:'伊朗核问题'},
                              {id:"03", title:'新闻3'},
                              {id:"04", title:'新闻4'},
                            ]
                          }
                           // 浏览器标签页的前进后退
                          // 前进
                          tapsForward = () => {
                            this.props.history.goForward()
                          }
                          // 后退
                          tapsBack = () => {
                            this.props.history.goBack()
                          } 
                           // 后退两步
                          tapsGO = () => {
                            this.props.history.go(-2)
                          } 

                          // 编程式路由
                          showReplace = (id, title) =>{
                            return () => {
                              // // params 传参 replace跳转
                              // this.props.history.replace(`/home/news/detail/${id}/${title}`)
                              // // search 传参 replace跳转
                              //  this.props.history.replace(`/home/news/detail/?id=${id}&title=${title}`)
                              // state 传参 replace跳转
                              this.props.history.replace(`/home/news/detail/`, {id:id, title:title})

                            }
                          }
                          showPush = (id, title) =>{
                            return () =>{
                              // // params 传参 push跳转
                              // this.props.history.push(`/home/news/detail/${id}/${title}`)
                              // // search 传参 replace跳转
                              // this.props.history.push(`/home/news/detail/?id=${id}&title=${title}`)
                              // state 传参 replace跳转
                              this.props.history.push(`/home/news/detail/`, {id:id, title:title})
                            }
                          }
                          render() {
                            return (
                              <div>
                                <div className="list-group ">
                                  {/* 设置路由链接 */}
                                  {/* <Link className='list-group-item list-group-item-action' to='/home/news/detail' >新闻1</Link> */}
                                  {
                                    this.state.newsArray.map((newsObj)=>{

                                      // 路由组件通过params传递参数 ++++++++++++++++++++++++++++++++++++++++++
                                      // return <Link key={newsObj.id} className='list-group-item list-group-item-action' 
                                      //   // to={`/home/news/detail/${newsObj.id}/${newsObj.title}`}>   {/* 路由组件传递 一个 params 参数 */}
                                      //   to={`/home/news/detail/${newsObj.id}/${newsObj.title}`}>      {/* 路由组件传递 两个params 参数 */}
                                      //   {newsObj.title}
                                      // </Link> 
                                      // 路由组件通过search传递参数 +++++++++++++++++++++++++++++++++++++++++++
                                      // return <Link key={newsObj.id} className='list-group-item list-group-item-action'
                                      //         to={`/home/news/detail/?id=${newsObj.id}&title=${newsObj.title}`}>
                                      //   {newsObj.title}
                                      // </Link>
                                      // 路由组件通过state传递参数 ++++++++++++++++++++++++++++++++++++++++++++
                                      // return <Link key={newsObj.id} className='list-group-item list-group-item-action'
                                      //         to={{pathname:'/home/news/detail/', state:{id:newsObj.id, title:newsObj.title}}}>
                                      //   {newsObj.title}
                                      // </Link>
                                      // 编程式路由  +++++++++++++++++++++++++++++++++++++++++++++++++++++++++
                                      return (
                                        <div key={newsObj.id} className='list-group'>
                                          <div className='  list-group-item d-flex'>
                                            <Link className=' flex-grow-1' 
                                               to={{pathname:'/home/news/detail/', state:{id:newsObj.id, title:newsObj.title}}}>   
                                                {newsObj.title}
                                            </Link> 
                                            <div onClick={this.showPush(newsObj.id, newsObj.title)}className='fw-light lh-sm btn btn-info b-0 '>push(增加记录)</div>
                                            <div onClick={this.showReplace(newsObj.id, newsObj.title)} className='fw-light lh-sm btn btn-primary ms-1'>replace(替换记录)</div>
                                          </div>
                                        </div>
                                        
                                        )
                                    })
                                  }
                                  <nav aria-label="Page navigation">
                                    <ul className="pagination mt-1">
                                      <li className="page-item btn border" onClick={this.tapsForward}>前进</li>
                                      <li className="page-item btn border ms-1" onClick={this.tapsBack}>后退</li>
                                      <li className="page-item btn border ms-1" onClick={this.tapsGO}>后退两次</li>
                                    </ul>
                                  </nav>
                                </div>
                                <hr/>
                                <div>
                                  {/* 注册路由 */}
                                  {/* 路由组件通过params传递参数 ++++++++++++++++++++++++++++++++++++++++++ */}
                                  {/* 接收上面Link传递的 params 参数 */}
                                  {/* 接收一个 params 参数 */}
                                  {/* <Route path={`/home/news/detail/:id/`} component={Detail}></Route>   */}
                                  {/* 接收两个 params 参数 */}
                                  {/* <Route path={`/home/news/detail/:id/:title/`} component={Detail}></Route> */}

                                  {/* 路由组件通过search传递参数 +++++++++++++++++++++++++++++++++++++++++++ */}
                                      {/* <Route path={`/home/news/detail/`} component={Detail}></Route> */}

                                  {/* 路由组件通过state传递参数 +++++++++++++++++++++++++++++++++++++++++++ */}
                                  <Route path={`/home/news/detail/`} component={Detail}></Route>
                                </div>
                              </div>
                            )
                          }
                        }
                        ```
            -   示例：等待2s跳转的需求实现，只要在从about页面就过两秒跳转到home页面 \[编程式路由导航,`history``replace(path,state)``push(path,state)`[¶](https://www.bilibili.com/video/BV1wy4y1D7JT?t=928.2\&p=91 "¶")]
                -   src/pages/About/index.jsx
                    ```react&#x20;jsx
                    import React, { Component } from 'react'

                    export default class index extends Component {
                      componentDidMount(){
                        setTimeout(() => {
                          this.props.history.push('/home/')
                        }, 2000);
                      }
                      render() {
                        return (
                          <div>
                            <h3>
                              About content
                            </h3>
                            <strong className='text-danger'>
                              (警告2s之后将跳转到home页面)
                            </strong>
                          </div>
                        )
                      }
                    }

                    ```
    -   [x] [92 092\_尚硅谷\_react教程\_withRouter的使用\_Duration-11Min](https://www.bilibili.com/video/BV1wy4y1D7JT/?p=92 "92 092_尚硅谷_react教程_withRouter的使用_Duration-11Min")
        -   \[笔记]
            -   示例：在一般组件使用路由组件的属性 \[`withRouter()`,一般组件,路由组件]

                ![](../image/image_5658TU0ZFq.png)
                -   src/component/Hander/Header.jsx
                    ```react&#x20;jsx
                    import React, { Component } from 'react'
                     import { withRouter } from 'react-router-dom' 

                    class Header extends Component {
                      // 浏览器标签页的前进后退
                      // 前进
                      tapsForward = () => {
                        this.props.history.goForward()
                      }
                      // 后退
                      tapsBack = () => {
                        this.props.history.goBack()
                      }
                      // 后退两步
                      tapsGO = () => {
                        this.props.history.go(-2)
                      }
                      render() {
                        return (
                        <div>
                            <h2>[React]</h2>
                            <h3>在一般组件使用路由组件的属性</h3>
                            <nav aria-label="Page navigation">
                                <ul className="pagination mt-1">
                                  <li className="page-item btn border" onClick={this.tapsForward}>前进</li>
                                  <li className="page-item btn border ms-1" onClick={this.tapsBack}>后退</li>
                                  <li className="page-item btn border ms-1" onClick={this.tapsGO}>后退两次</li>
                                </ul>
                              </nav>
                        </div>
                        )
                      }
                    }
                     export default withRouter(Header)
                    ```
                -   src/App.jsx
                    ```react&#x20;jsx
                    import React, { Component } from 'react'
                    import { Route, Switch, Redirect} from 'react-router-dom'
                    //
                    import About from './pages/About'
                    import Home from './pages/Home'
                    import MyNavLink from './component/MyNavLink/MyNavLink'
                     import Header from './component/Hander/Header' 
                    //
                    export default class App extends Component {
                      render() {
                        return (
                          <div>
                            <div className="container">
                              <div className="row">
                                <div className="col-12">
                                   <Header /> 
                                </div>
                                <div className="col-4">
                                  <div className="list-group">
                                    {/* 原生使用a标签跳转页面 */}
                                    {/* <a className="list-group-item active" href="./about.html">About</a> */}
                                    {/* <a className="list-group-item" href="./home.html">Home</a> */}
                                    {/* 使用 react-router-dom 编写路由链接 */}
                                    {/* 封装NavLink */}
                                    <MyNavLink to="/home">Home</MyNavLink>
                                    <MyNavLink to="/about">About</MyNavLink>
                                  </div>
                                </div>
                                <div className="col-8">
                                  {/* 注册路由 */}
                                  <Switch>
                                  <Route path="/home" component={Home} />  {/* 如果检测路径是/home，则在这部分HTML中调用Home组件*/}
                                  <Route path="/about" component={About} />
                                  <Redirect to="/about"/>
                                  </Switch>
                                </div>
                              </div>
                            </div>
                          </div>
                        )
                      }
                    }
                    ```
    -   [x] [93 093\_尚硅谷\_react教程\_BrowserRouter与HashRouter\_Duration-7Min](https://www.bilibili.com/video/BV1wy4y1D7JT/?p=93 "93 093_尚硅谷_react教程_BrowserRouter与HashRouter_Duration-7Min")
        -   \[笔记]&#x20;

            \[对比]`BrowserRouter`|`HashRouter` \[`location.state`]

            `location.state`在刷新浏览器时，使用后者Hash的方式路由，将丢失记录[¶](https://www.bilibili.com/video/BV1wy4y1D7JT?t=390.6\&p=93 "¶")，原因:因为它没有使用history这个api

            ![](../image/image_OKaLxFy2NR.png)
    -   路由案例全部代码

        ![](../image/image_btk3AP_ov5.png)
        -
    ***
    -   [x] [94 094\_尚硅谷\_react教程\_antd的基本使用\_Duration-31Min](https://www.bilibili.com/video/BV1wy4y1D7JT/?p=94 "94 094_尚硅谷_react教程_antd的基本使用_Duration-31Min")
        -   示例：[\[JS库\]antd](\[JS库]antd_caQzfSXshntbdsi9UQvwgX.md "\[JS库]antd")[\[JS库\]Element](\[JS库]Element_teaKs9Fg9rARoPhuv4Dj.md "\[JS库]Element")[\[JS库\]vant](\[JS库]vant_t9q2vCqxNrzxBzj6M3Kvap.md "\[JS库]vant")

            ![](../image/image_5izELhmoSS.png)
            ```react&#x20;jsx
            import React, { Component } from 'react'
            // UI库
            import { Button,Progress } from 'antd';
            // 图标库
            import {
                GoogleOutlined,
                SyncOutlined,
              } from '@ant-design/icons';
            //
            import { red } from '@ant-design/colors';
            //
            export default class App extends Component {
              render() {
                return (
                  <div>
                    <h1>UI组件库</h1><hr/>
                    <h2>antd</h2>
                    <div>
                        <h3>按钮</h3>
                        <Button type="primary">Primary Button</Button>
                        <Button type="primary" danger='true'>danger Button</Button>
                    </div>
                    <div>
                        <h3>图标</h3>
                        <p><q>构使用图标组件，你需要安装 @ant-design/icons 图标组件包</q></p>
                        <p>使用图标加按钮的组合如下</p>
                        <Button icon={<GoogleOutlined/>}></Button>
                        <Button icon={<SyncOutlined/>}></Button>
                    </div>
                    <div>
                        <h3>进度条</h3>
                        <Progress percent={90} status="active" strokeColor={red[1]} />
                        
                    </div>
                    <div>
                        <h3>1</h3>
                    </div>

                  </div>
                )
              }
            }

            ```
    -   [x] [95 095\_尚硅谷\_react教程\_antd样式的按需引入\_Duration-22Min](https://www.bilibili.com/video/BV1wy4y1D7JT/?p=95 "95 095_尚硅谷_react教程_antd样式的按需引入_Duration-22Min") 跳过
    -   [x] [96 096\_尚硅谷\_react教程\_antd自定义主题\_Duration-16Min](https://www.bilibili.com/video/BV1wy4y1D7JT/?p=96 "96 096_尚硅谷_react教程_antd自定义主题_Duration-16Min") 跳过
    ***
    ## redux
    -   [x] [97 097\_尚硅谷\_react教程\_redux简介\_Duration-16Min](https://www.bilibili.com/video/BV1wy4y1D7JT/?p=97 "97 097_尚硅谷_react教程_redux简介_Duration-16Min")&#x20;
        -   \[笔记]
            -   \[笔记]：[\[JS库\]redux](\[JS库]redux_wYUdBtUF4wPMD74fXKn7zd.md "\[JS库]redux")

                ![](../image/image_7BiCIZ9Cgh.png)
    -   [x] [98 098\_尚硅谷\_react教程\_redux工作流程\_Duration-36Min](https://www.bilibili.com/video/BV1wy4y1D7JT/?p=98 "98 098_尚硅谷_react教程_redux工作流程_Duration-36Min")
        -   \[笔记] 初步了解redux的概念 \[[\[JS库\]redux](\[JS库]redux_wYUdBtUF4wPMD74fXKn7zd.md "\[JS库]redux")redux工作原理redux三个核心概念`action``reducer``store`]

            ![](../image/image_4a1x4rkLgt.png)

            ![](../image/image_ryH1QvYig0.png)

            ![](../image/image_Tw76SkmY-5.png)
    -   [x] [99 099\_尚硅谷\_react教程\_求和案例\_纯react版\_Duration-19Min](https://www.bilibili.com/video/BV1wy4y1D7JT/?p=99 "99 099_尚硅谷_react教程_求和案例_纯react版_Duration-19Min")
        -   \[笔记]
    -   [x] [100 100\_尚硅谷\_react教程\_求和案例\_redux精简版\_Duration-53Min](https://www.bilibili.com/video/BV1wy4y1D7JT/?p=100 "100 100_尚硅谷_react教程_求和案例_redux精简版_Duration-53Min")
        -   \[笔记]

            ![](../image/image_ubnTxsyWjp.png)
            -   示例：求和案例 \[createStore`store.getState()``store.dispatch()``setTimeout()`,方式3/3 api参数形式的ref(推荐) \[refs]]

                ![](../image/image_al2BwTtvGW.png)

                ![](<../image/2023-23-01-1829 (1)_FuFWBZXdTI.gif>)
                -   src/App.jsx&#x20;
                    ```react&#x20;jsx
                    import React, { Component } from 'react'
                    //
                    import Header from './component/Header/Header'
                    import Calculate from './component/Calculate/Calculate'

                    export default class App extends Component {
                      render() {
                        return (
                          <div className='container'>
                              <Header />
                              <Calculate />
                          </div>
                        )
                      }
                    }
                     
                    ```
                -   src/component/Calculate/Calculate.jsx 一般组件
                    ```react&#x20;jsx
                    import React, { Component } from 'react'
                    // 引用redux中的store
                    import store from '../../redux/store'

                    export default class Calculate extends Component {
                      refSelect = React.createRef()   // ref
                      
                       increment = () => {
                        store.dispatch({type:'increment', data:this.refSelect.current.value*1})
                        console.log('Calculate组件中，在加之后的值', store.getState())
                      }
                      decrement = () => {
                        store.dispatch({type:'decrement', data:this.refSelect.current.value*1})
                        console.log('Calculate组件中，在减之后的值', store.getState())
                      }
                      oddIncrement = () => {
                          if (store.getState() % 2 !== 0) {
                            store.dispatch({type:'increment', data:this.refSelect.current.value*1})
                          }
                        console.log('Calculate组件中，如为奇数则+1', store.getState())
                      }
                      asynIncrement = () => {
                        setTimeout(() => {
                          store.dispatch({type:'increment', data:this.refSelect.current.value*1})
                        }, 500);
                        console.log('Calculate组件中，异步加', store.getState())
                      } 
                      

                      
                      selectValue = (event) => {
                        // console.log(event.target.value)
                        this.setState({selectValue:event.target.value})  // 设置state
                      }
                      render() {
                        return (
                          <div className="row">
                            <div className='d-flex flex-row bd-highlight px-0 '>
                              <select ref={this.refSelect} className="form-select w-25" aria-label="Default select"  onChange={this.selectValue}>
                                  <option value="1">1</option>
                                  <option value="2">2</option>
                                  <option value="3">3</option>
                              </select>

                              <button type="button" name="" id="" onClick={this.increment} className="btn btn-primary ms-1">+</button>
                              <button type="button" name="" id="" onClick={this.decrement} className="btn btn-primary ms-1">-</button>
                              <button type="button" name="" id="" onClick={this.oddIncrement} className="btn btn-primary ms-1">如为奇数则+1</button>
                              <button type="button" name="" id="" onClick={this.asynIncrement} className="btn btn-primary ms-1">异步加</button>
                            </div>
                          </div>
                        )
                      }
                    }
                    ```
                -   src/component/Header/Header.jsx 一般组件
                    ```react&#x20;jsx
                    import React, { Component } from 'react'
                    // 引用redux中的store
                    import store from '../../redux/store'

                    export default class Header extends Component {
                      // componentDidMount(){
                      //   // redux 更新了值，但是不会重新渲染页面，所以需要手动渲染页面...或者另一种方式在index.js中写，就不用在每个组件中写这部分代码了
                      //   store.subscribe(()=>{
                      //     this.setState({})
                      //   })
                      // }
                      
                      render() {
                        return (
                          <div className="row mb-2">
                            当前的值为：{store.getState()}
                          </div>
                        )
                      }
                    }

                    ```
                -   src/index.js  redux 更新了值，但是不会重新渲染页面，所以需要手动渲染页面
                    ```react&#x20;jsx
                    import React from "react";
                    import { createRoot } from "react-dom/client";

                    import App from "./App";
                    import store from "./redux/store";

                    const root  = createRoot(document.getElementById('root'))
                    root.render(<App/>)

                    store.subscribe(()=>{
                        // redux 更新了值，但是不会重新渲染页面，所以需要手动渲染页面...或者另一种方式在index.js中写
                        root.render(<App/>)
                    })
                    ```
                -   src/redux/count\_reducer.js
                    ```react&#x20;jsx

                    const initState = 0  // 初始化值
                    export default function countReducer(preState=initState, action) {
                        // console.log(preState, action.type, action.data)
                        console.log('count_reducer，在运算的之前的值', preState)
                        const {type, data} = action
                        switch (type) {
                            case 'increment':
                                return preState + data
                            case 'decrement':
                                return preState - data
                            default:
                                return preState
                        }
                    }
                    ```
                -   src/redux/store.js
                    ```react&#x20;jsx
                    /*
                        该文件专门用于暴露一个store对象，整个应用只存在一个store对象
                    */

                    // 引入createStore 专门用于创建redux中最核心的store对象
                    import {legacy_createStore as  createStore} from 'redux'
                    // 引入Count组件服务的reducer
                    import countReducer from './count_reducer'
                    // 暴露store
                    export default createStore(countReducer)
                    ```
    -   [x] [101 101\_尚硅谷\_react教程\_求和案例\_redux完整版\_Duration-20Min](https://www.bilibili.com/video/BV1wy4y1D7JT/?p=101 "101 101_尚硅谷_react教程_求和案例_redux完整版_Duration-20Min")
        -   \[笔记]添加action文件，添加常量模块 \[`action`]
    -   [x] [102 102\_尚硅谷\_react教程\_求和案例\_异步action版\_Duration-35Min](https://www.bilibili.com/video/BV1wy4y1D7JT/?p=102 "102 102_尚硅谷_react教程_求和案例_异步action版_Duration-35Min")
        -   \[笔记]

            ![](../image/image_ZO2I0j9zGE.png)
            -   示例：增加异步，在action中 \[`action`分为：同步action，为对象异步action，为函数[¶](https://www.bilibili.com/video/BV1wy4y1D7JT?t=171.1\&p=102 "¶")[¶](https://www.bilibili.com/video/BV1wy4y1D7JT?t=827.9\&p=102 "¶")[\[JS库\]react-thunk](\[JS库]react-thunk_pnKfZG5HF8F9RQRNoK9Yhj.md "\[JS库]react-thunk"),`reducer`]
                -   src/redux/count\_action.js
                    ```react&#x20;jsx
                    // 引入常量
                    import { INCREMENT, DECREMENT } from "./constant"

                    // 专门为Calculate组件生成action对象

                    // function createIncrementAction(data) {
                    //     return {type:'increment', data}
                    // }

                    // 简化
                    // 同步 action
                    export const createIncrementAction = (data) => ({type:INCREMENT, data}) 
                    export const createDecrementAction = (data) => ({type:DECREMENT, data}) 
                    // 异步 action
                     export const createDecrementAsynAction = (data, time) => { 
                        // return () => {
                        //     setTimeout(() => {
                        //         store.dispatch(createIncrementAction(data))
                        //     }, time);
                        // }
                        // 因为会传给store，所以这里可以不用引入store
                        // import store from "./store"
                         return (dispatch) => { 
                             setTimeout(() => {
                                dispatch(createIncrementAction(data))
                            }, time);
                        }
                    } 
                    ```
                -   src/redux/store.js
                    ```react&#x20;jsx
                    /*
                        该文件专门用于暴露一个store对象，整个应用只存在一个store对象
                    */

                    // 引入createStore 专门用于创建redux中最核心的store对象
                     import {legacy_createStore as  createStore, applyMiddleware} from 'redux' 
                    // 引入Count组件服务的reducer
                    import countReducer from './count_reducer'
                    //
                     import thunk from 'redux-thunk' 
                    // 暴露store
                    export default createStore(countReducer,  applyMiddleware(thunk ))
                    ```
    -   [x] [103 103\_尚硅谷\_react教程\_对react-redux的理解\_Duration-8Min](https://www.bilibili.com/video/BV1wy4y1D7JT/?p=103 "103 103_尚硅谷_react教程_对react-redux的理解_Duration-8Min")
        -   \[笔记] [\[JS库\]React-Redux](\[JS库]React-Redux_4YJrdLfLyt7NXy4jbdoYPC.md "\[JS库]React-Redux")



            ![](../image/image_OnVmvWOsbM.png)
    -   [x] [104 104\_尚硅谷\_react教程\_连接容器组件与UI组件\_Duration-22Min](https://www.bilibili.com/video/BV1wy4y1D7JT/?p=104 "104 104_尚硅谷_react教程_连接容器组件与UI组件_Duration-22Min") \[[\[JS库\]React-Redux](\[JS库]React-Redux_4YJrdLfLyt7NXy4jbdoYPC.md "\[JS库]React-Redux")`connect()`;容器组件UI组件]
    -   [x] [105 105\_尚硅谷\_react教程\_react-redux基本使用\_Duration-46Min](https://www.bilibili.com/video/BV1wy4y1D7JT/?p=105 "105 105_尚硅谷_react教程_react-redux基本使用_Duration-46Min")
        -   \[笔记]

            ![](../image/image_eyXWNcm7fo.png)
            -   示例：通过react-redux进行状态管理的基础示例 \[[\[JS库\]React-Redux](\[JS库]React-Redux_4YJrdLfLyt7NXy4jbdoYPC.md "\[JS库]React-Redux")`connect()`[¶](https://www.bilibili.com/video/BV1wy4y1D7JT?t=568.9\&p=105 "¶")[¶](https://www.bilibili.com/video/BV1wy4y1D7JT?t=2660.4\&p=105 "¶"),`store.getState()`,`store.dispatch()`]
                -   src/App.jsx
                    ```react&#x20;jsx
                    import React, { Component } from 'react'
                    //
                    // import Header from './component/Header/Header'
                    // import Calculate from './component/Calculate/Calculate'
                    import Count from './container/Count'
                    // 引入store
                    import store from './redux/store'

                    export default class App extends Component {
                      render() {
                        return (
                          <div className='container'>
                              {/* 给容器组件传递store */}
                              <Count  store={store} />
                          </div>
                        )
                      }
                    }
                    ```
                -   src/container/Count/index.jsx 容器组件将redux的值通过props传递给UI组件
                    ```react&#x20;jsx
                    // 引入UI组件
                    import Count from "../../components/Count";
                    // 引入connect用于连接UI组件与redux
                    import {connect} from 'react-redux'
                    import { createIncrementAction, createDecrementAction,createIncrementAsynAction } from "../../redux/count_action";


                    // 传递给UI组件的状态与方法
                    // 在react-redux已经在传递状态的时候，把state也就是从App中传递过来的store的值放在了state(第一个参数)中
                    //// 从这里传入子组件(UI组件)中的props中，UI组件就只需要从props中调用(来自redux store的参数)既可
                    //// 这步相当于redux api的getState()
                    function mapStateToProps(state) {
                        return {count:state}
                    }
                    function mapDispatchToProps(dispatch) {
                        // return {increment:()=>{console.log('在容器组件中传递参数给UI组件的方法返回值的执行')}}
                        return {
                            increment:(number)=>{dispatch(createIncrementAction(number))},
                            decrement:(number)=>{dispatch(createDecrementAction(number))},
                            incrementAsyn:(number)=>{dispatch(createIncrementAsynAction(number, 500))},
                        }
                    }
                    // 创建并暴露一个Count的容器组件
                    export default connect(mapStateToProps, mapDispatchToProps)(Count)

                    ```
                -   src/components/Count/Header/Header.jsx 读取reudx通过容器组件通过props传递过来的当前求和的值
                    ```react&#x20;jsx
                    import React, { Component } from 'react'
                    // 引用redux中的store
                    // import store from '../../redux/store'

                    export default class Header extends Component {
                      // componentDidMount(){
                      //   // redux 更新了值，但是不会重新渲染页面，所以需要手动渲染页面...或者另一种方式在index.js中写，就不用在每个组件中写这部分代码了
                      //   store.subscribe(()=>{
                      //     this.setState({})
                      //   })
                      // }
                      
                      render() {
                        return (
                          <div className="row mb-2">
                            当前的值为：{this.props.count}
                          </div>
                        )
                      }
                    }

                    ```
                -   src/components/Count/index.jsx  UI组件将收到的props参数继续传递给子组件
                    ```react&#x20;jsx
                    import React, { Component } from 'react'
                    import Calculate from './Calculate/Calculate'
                    import Header from './Header/Header'

                    export default class Count extends Component {
                      render() {
                        // console.log('1在UI组件中1', this.props)
                        // console.log('2在UI组件中，在容器中间中传递过来的方法：', this.props.increment)
                        // console.log('4在UI组件中，在容器组件中传递过来的值(状态)：', this.props.count)

                        return (
                          <div>
                            <Header count={this.props.count} />
                            <Calculate count={this.props}/>
                          </div>
                        )
                      }
                    }

                    ```
                -   src/components/Count/Calculate/Calculate.jsx  UI组件的子组件将收到了方法进行调用既可
                    ```react&#x20;jsx
                    import React, { Component } from 'react'

                    export default class Calculate extends Component {
                      refSelect = React.createRef()   // ref
                      
                      increment = () => {
                        console.log('Calculate',this.props.count.increment)
                        const value = this.refSelect.current.value*1
                        this.props.count.increment(value)
                        console.log('Calculate组件中，在加之后的值', this.props.count.count)
                      }
                      decrement = () => {
                        const value = this.refSelect.current.value*1
                        this.props.count.decrement(value)
                        console.log('Calculate组件中，在减之后的值', this.props.count.count)
                      }
                      oddIncrement = () => {
                        const value = this.refSelect.current.value*1
                        if (this.props.count.count % 2 !== 0) {
                          this.props.count.increment(value)
                        }
                        console.log('Calculate组件中，如为奇数则+1', this.props.count.count)
                      }
                      asynIncrement = () => {
                        const value = this.refSelect.current.value*1
                        this.props.count.incrementAsyn(value)
                        console.log('Calculate组件中，异步加', this.props.count.count)
                      }
                      

                      

                      render() {
                        return (
                          <div className="row">
                            <div className='d-flex flex-row bd-highlight px-0 '>
                              <select ref={this.refSelect} className="form-select w-25" aria-label="Default select" >
                                  <option value="1">1</option>
                                  <option value="2">2</option>
                                  <option value="3">3</option>
                              </select>

                              <button type="button" name="" id="" onClick={this.increment} className="btn btn-primary ms-1">+</button>
                              <button type="button" name="" id="" onClick={this.decrement} className="btn btn-primary ms-1">-</button>
                              <button type="button" name="" id="" onClick={this.oddIncrement} className="btn btn-primary ms-1">如为奇数则+1</button>
                              <button type="button" name="" id="" onClick={this.asynIncrement} className="btn btn-primary ms-1">异步加</button>
                            </div>
                          </div>
                        )
                      }
                    }

                    ```
    -   [x] [106 106\_尚硅谷\_react教程\_优化1\_简写mapDispatch\_Duration-20Min](https://www.bilibili.com/video/BV1wy4y1D7JT/?p=106 "106 106_尚硅谷_react教程_优化1_简写mapDispatch_Duration-20Min")
        -   \[笔记]

            ![](../image/image_3u6bl_v806.png)
            -   示例：优化|简化代码 \[[\[JS库\]React-Redux](\[JS库]React-Redux_4YJrdLfLyt7NXy4jbdoYPC.md "\[JS库]React-Redux")`connect()`，简化`store.dispatch()`]
                -   src/container/Count/index.jsx
                    ```react&#x20;jsx
                    // 引入UI组件
                    import Count from "../../components/Count";
                    // 引入connect用于连接UI组件与redux
                    import {connect} from 'react-redux'
                    import { createIncrementAction, createDecrementAction,createIncrementAsynAction } from "../../redux/count_action";


                    // 传递给UI组件的状态与方法
                    // 在react-redux已经在传递状态的时候，把state也就是从App中传递过来的store的值放在了state(第一个参数)中
                    //// 从这里传入子组件(UI组件)中的props中，UI组件就只需要从props中调用(来自redux store的参数)既可
                    //// 这步相当于redux api的getState()
                    // function mapStateToProps(state) {
                    //     return {count:state}
                    // }
                    // function mapDispatchToProps(dispatch) {
                    //     // return {increment:()=>{console.log('在容器组件中传递参数给UI组件的方法返回值的执行')}}
                    //     return {
                    //         increment:(number)=>{dispatch(createIncrementAction(number))},
                    //         decrement:(number)=>{dispatch(createDecrementAction(number))},
                    //         incrementAsyn:(number)=>{dispatch(createIncrementAsynAction(number, 500))},
                    //     }
                    // }
                    // // 创建并暴露一个Count的容器组件
                    // export default connect(mapStateToProps, mapDispatchToProps)(Count)
                    // ----------------------简写

                    export default connect(
                        state => ({count:state})
                        , 
                        {
                            increment:createIncrementAction,
                            decrement:createDecrementAction,
                            incrementAsyn:createIncrementAsynAction,
                        }
                        )(Count)
                    ```
    -   [x] [107 107\_尚硅谷\_react教程\_优化2\_Provider组件的使用\_Duration-13Min](https://www.bilibili.com/video/BV1wy4y1D7JT/?p=107 "107 107_尚硅谷_react教程_优化2_Provider组件的使用_Duration-13Min") &#x20;
        -   \[笔记]

            ![](../image/image_pBKIgVobhY.png)

            ![](../image/image_U_ME_IrYs1.png)
            -   示例：简化，不在需要手动去检测redux中的store的值发生变化而在写一段代码来重新渲染页面 \[[\[JS库\]React-Redux](\[JS库]React-Redux_4YJrdLfLyt7NXy4jbdoYPC.md "\[JS库]React-Redux")Provider`store`]
                -   src/App.jsx
                    ```react&#x20;jsx
                    import React, { Component } from 'react'
                    //
                    // import Header from './component/Header/Header'
                    // import Calculate from './component/Calculate/Calculate'
                    import Count from './container/Count'
                    // 引入store
                    import store from './redux/store'

                    export default class App extends Component {
                      render() {
                        return (
                          <div className='container'>
                              <Count/>
                          </div>
                        )
                      }
                    }

                    ```
                -   src/index.js
                    -   &#x20;
                        ```react&#x20;jsx
                        import React from "react";
                        import { createRoot } from "react-dom/client";

                        import App from "./App";
                        // import store from "./redux/store";

                        const root  = createRoot(document.getElementById('root'))
                        root.render(<App/>)

                        // store.subscribe(()=>{
                        //     // redux 中的值发生改变，但是不会重新渲染页面，所以需要手动渲染页面...或者另一种方式在index.js中写
                               // 在 react-redux 中就不需要这么写了，已经优化了
                        //     root.render(<App/>)
                        // })
                        ```
                    ```react&#x20;jsx
                    import React from "react";
                    import { createRoot } from "react-dom/client";
                    import { Provider } from "react-redux";
                    //
                    import store from './redux/store'
                    //
                    import App from "./App";

                    const root  = createRoot(document.getElementById('root'))
                    root.render(
                        <Provider store={store}>
                            <App/>
                        </Provider>
                        )


                    ```
            -   示例：优化，UI组件与容器组件合并 \[
                -   src/container/Count/index.jsx
                    ```react&#x20;jsx
                    // 引入UI组件 // 优化 ， 将UI组件合并到一起
                    // import Count from "../../components/Count"; 
                    // 引入connect用于连接UI组件与redux
                    import {connect} from 'react-redux'
                    import { createIncrementAction, createDecrementAction,createIncrementAsynAction } from "../../redux/count_action";


                    // 传递给UI组件的状态与方法
                    // 在react-redux已经在传递状态的时候，把state也就是从App中传递过来的store的值放在了state(第一个参数)中
                    //// 从这里传入子组件(UI组件)中的props中，UI组件就只需要从props中调用(来自redux store的参数)既可
                    //// 这步相当于redux api的getState()
                    // function mapStateToProps(state) {
                    //     return {count:state}
                    // }
                    // function mapDispatchToProps(dispatch) {
                    //     // return {increment:()=>{console.log('在容器组件中传递参数给UI组件的方法返回值的执行')}}
                    //     return {
                    //         increment:(number)=>{dispatch(createIncrementAction(number))},
                    //         decrement:(number)=>{dispatch(createDecrementAction(number))},
                    //         incrementAsyn:(number)=>{dispatch(createIncrementAsynAction(number, 500))},
                    //     }
                    // }
                    // // 创建并暴露一个Count的容器组件
                    // export default connect(mapStateToProps, mapDispatchToProps)(Count)
                    // ----------------------简写
                     import React, { Component } from 'react'
                    import Calculate from "../../components/Count/Calculate/Calculate";
                    import Header from "../../components/Count/Header/Header";

                    // UI 组件
                    class Count extends Component {
                      render() {
                        // console.log('1在UI组件中1', this.props)
                        // console.log('2在UI组件中，在容器中间中传递过来的方法：', this.props.increment)
                        // console.log('4在UI组件中，在容器组件中传递过来的值(状态)：', this.props.count)

                        return (
                          <div>
                            <Header count={this.props.count} />
                            <Calculate count={this.props}/>
                          </div>
                        )
                      }
                    } 

                    // 容器组件

                    export default connect(
                        state => ({count:state})
                        , 
                        {
                            increment:createIncrementAction,
                            decrement:createDecrementAction,
                            incrementAsyn:createIncrementAsynAction,
                        }
                        )(Count)
                    ```
    -   [x] [108 108\_尚硅谷\_react教程\_优化3\_整合UI组件与容器组件\_Duration-27Min](https://www.bilibili.com/video/BV1wy4y1D7JT/?p=108 "108 108_尚硅谷_react教程_优化3_整合UI组件与容器组件_Duration-27Min")
        -   使用[\[JS库\]React-Redux](\[JS库]React-Redux_4YJrdLfLyt7NXy4jbdoYPC.md "\[JS库]React-Redux")完成过程演示[¶](https://www.bilibili.com/video/BV1wy4y1D7JT?t=1013.3\&p=108 "¶")
        -   示例：优化，UI组件与容器组件合并 \[
            -   src/container/Count/index.jsx
                ```react&#x20;jsx
                // 引入UI组件 // 优化 ， 将UI组件合并到一起
                // import Count from "../../components/Count"; 
                // 引入connect用于连接UI组件与redux
                import {connect} from 'react-redux'
                import { createIncrementAction, createDecrementAction,createIncrementAsynAction } from "../../redux/count_action";


                // 传递给UI组件的状态与方法
                // 在react-redux已经在传递状态的时候，把state也就是从App中传递过来的store的值放在了state(第一个参数)中
                //// 从这里传入子组件(UI组件)中的props中，UI组件就只需要从props中调用(来自redux store的参数)既可
                //// 这步相当于redux api的getState()
                // function mapStateToProps(state) {
                //     return {count:state}
                // }
                // function mapDispatchToProps(dispatch) {
                //     // return {increment:()=>{console.log('在容器组件中传递参数给UI组件的方法返回值的执行')}}
                //     return {
                //         increment:(number)=>{dispatch(createIncrementAction(number))},
                //         decrement:(number)=>{dispatch(createDecrementAction(number))},
                //         incrementAsyn:(number)=>{dispatch(createIncrementAsynAction(number, 500))},
                //     }
                // }
                // // 创建并暴露一个Count的容器组件
                // export default connect(mapStateToProps, mapDispatchToProps)(Count)
                // ----------------------简写
                 import React, { Component } from 'react'
                import Calculate from "../../components/Count/Calculate/Calculate";
                import Header from "../../components/Count/Header/Header";

                // UI 组件
                class Count extends Component {
                  render() {
                    // console.log('1在UI组件中1', this.props)
                    // console.log('2在UI组件中，在容器中间中传递过来的方法：', this.props.increment)
                    // console.log('4在UI组件中，在容器组件中传递过来的值(状态)：', this.props.count)

                    return (
                      <div>
                        <Header count={this.props.count} />
                        <Calculate count={this.props}/>
                      </div>
                    )
                  }
                } 

                // 容器组件

                export default connect(
                    state => ({count:state})
                    , 
                    {
                        increment:createIncrementAction,
                        decrement:createDecrementAction,
                        incrementAsyn:createIncrementAsynAction,
                    }
                    )(Count)
                ```
    -   [x] [109 109\_尚硅谷\_react教程\_数据共享\_编写Person组件\_Duration-14Min](https://www.bilibili.com/video/BV1wy4y1D7JT/?p=109 "109 109_尚硅谷_react教程_数据共享_编写Person组件_Duration-14Min")
    -   [x] [110 110\_尚硅谷\_react教程\_数据共享\_编写Person组件的reducer\_Duration-13Min](https://www.bilibili.com/video/BV1wy4y1D7JT/?p=110 "110 110_尚硅谷_react教程_数据共享_编写Person组件的reducer_Duration-13Min")
        -   \[笔记]
            -   示例：组件之间数据共享 ：Person组件的action、reducer点击事件等准备  \[[\[JS库\]React-Redux](\[JS库]React-Redux_4YJrdLfLyt7NXy4jbdoYPC.md "\[JS库]React-Redux")[\[JS库\]redux](\[JS库]redux_wYUdBtUF4wPMD74fXKn7zd.md "\[JS库]redux")方式2/3回调(箭头函数)参数形式的ref \[refs]]
                -   src/redux/actions/person.js
                    ```react&#x20;jsx
                    // 引入常量
                    import { ADD_PERSON } from '../constant'

                    //
                    export const addPersonAction = (personObj) => ({type:ADD_PERSON, data:personObj})

                    ```
                -   src/redux/reducers/person.js
                    ```react&#x20;jsx
                    // reducer 的作用：初始化状态与加工状态

                    // 引入常量
                    import { ADD_PERSON } from "../constant";

                    const initState = [{id:01, name:jek, age:11}] // 初始化值
                    export default function personReducer(preState=initState, action) {
                        const {type, data} = action // 结构action
                        switch (type) {             // 判断动作的类型是什么
                            case ADD_PERSON:
                                return {data, ...preState} 
                            default:
                                return preState;
                        }
                    }
                    ```
                -   src/container/Person/Person.jsx&#x20;
                    ```react&#x20;jsx
                    import React, { Component } from 'react'
                    //
                    import SnowFlake from '../../plugin/snowFlake'

                    export default class Person extends Component {
                      addPerson = () => {
                        const name = this.inputName.value
                        const age  = this.inputAge.value
                        const constObj = {id:SnowFlake(), name, age}
                        console.log(constObj)
                      }
                      render() {
                        return (
                          <div>

                            <div className="container m-0 p-0">
                              <form>
                                <div>
                                  <div className="input-group input-group-sm mb-3">
                                    <span className="input-group-text" id="inputGroup-sizing-sm">人名</span>
                                    <input ref={(a) => {this.inputName = a}} type="text" className="form-control" aria-label="Sizing example input" aria-describedby="inputGroup-sizing-sm" />
                                  </div>
                                  <div className="input-group input-group-sm mb-3">
                                    <span className="input-group-text" id="inputGroup-sizing-sm">年龄</span>
                                    <input ref={(a) => {this.inputAge = a}} type="text" className="form-control" aria-label="Sizing example input" aria-describedby="inputGroup-sizing-sm" />
                                  </div>

                                </div>
                                <div>
                                  <div className="d-grid gap-2">
                                    <button className="btn btn-primary" type="button" onClick={this.addPerson}>添加</button>
                                  </div>
                                </div>
                              </form>
                            </div>
                            <ul className='list-group mt-3'>
                              <li className='list-group-item'>网--23</li>
                              <li className='list-group-item'>周--18</li>
                              <li className='list-group-item'>李--22</li>
                            </ul>
                          </div>
                        )
                      }
                    }

                    ```
    -   [x] [111 111\_尚硅谷\_react教程\_数据共享\_完成数据共享\_Duration-33Min](https://www.bilibili.com/video/BV1wy4y1D7JT/?p=111 "111 111_尚硅谷_react教程_数据共享_完成数据共享_Duration-33Min")
        -   \[笔记]&#x20;

            ![](../image/image_gF1AXGikw-.png)
            -   示例：组件之间数据共享： \[[\[JS库\]React-Redux](\[JS库]React-Redux_4YJrdLfLyt7NXy4jbdoYPC.md "\[JS库]React-Redux")[\[JS库\]redux](\[JS库]redux_wYUdBtUF4wPMD74fXKn7zd.md "\[JS库]redux")`combineReducers`,`store`,props]
                -   src/redux/actions/count.js   添加person的动作
                    ```react&#x20;jsx
                    // 引入常量
                    import { ADD_PERSON } from '../constant'

                    //
                    export const addPersonAction = (personObj) => ({type:ADD_PERSON, data:personObj})

                    ```
                -   src/redux/reducers/person.js   处理添加perosn的动作
                    ```react&#x20;jsx
                    // reducer 的作用：初始化状态与加工状态

                    // 引入常量
                    import { ADD_PERSON } from "../constant";

                     const initState = [] // 初始化值 
                    export default function personReducer(preState=initState, action) {
                        const {type, data} = action   // data为从person中的输入框传递过来的值
                        // console.log('src/redux/reducers/person.js 接收的action中的data与type', data, type)
                        switch (type) {
                            case ADD_PERSON:
                                // console.log('data为从person中的输入框传递过来的值:', data)
                                // console.log(...preState)
                                 return [data, ...preState] 
                            default:
                                return preState;
                        }
                    }
                    ```
                -   src/container/Person/Person.jsx  UI组件与容器组件
                    ```react&#x20;jsx
                    import React, { Component } from 'react'
                    //
                    // 引入connect用于连接UI组件与redux
                    import {connect} from 'react-redux'
                    // 
                    import { addPersonAction } from '../../redux/actions/person'
                    //
                    import SnowFlake from '../../plugin/snowFlake'

                    class Person extends Component {
                      addPerson = () => {
                        const name = this.inputName.value
                        const age  = this.inputAge.value
                        const constObj = {id:SnowFlake(), name, age}
                        // console.log('Person, 输入框中传递过来的值：', constObj)
                        // console.log('Person, this.props', this.props)
                        this.props.addPerson(constObj)  // 调用从容器组件中传递过来的方法用于添加person
                      }
                      render() {
                        return (
                          <div>

                            <div className="container m-0 p-0">
                              <form>
                                <div>
                                  <div className="input-group input-group-sm mb-3">
                                    <span className="input-group-text" id="inputGroup-sizing-sm">人名</span>
                                    <input ref={(a) => {this.inputName = a}} type="text" className="form-control" aria-label="Sizing example input" aria-describedby="inputGroup-sizing-sm" />
                                  </div>
                                  <div className="input-group input-group-sm mb-3">
                                    <span className="input-group-text" id="inputGroup-sizing-sm">年龄</span>
                                    <input ref={(a) => {this.inputAge = a}} type="text" className="form-control" aria-label="Sizing example input" aria-describedby="inputGroup-sizing-sm" />
                                  </div>

                                </div>
                                <div>
                                  <div className="d-grid gap-2">
                                    <button className="btn btn-primary" type="button" onClick={this.addPerson}>添加</button>
                                  </div>
                                </div>
                              </form>
                            </div>
                            <ul className='list-group mt-3'>
                              {
                                this.props.personObj.map((person)=>{
                                  return <li key={person.id} className='list-group-item'>{person.name}--{person.age}</li>
                                })
                              }
                            </ul>
                          </div>
                        )
                      }
                    }

                    // 容器组件
                    export default connect(
                      state => ({personObj:state.personObj})  // 将store中的关于perosn的状态通过props传递给组件
                      ,
                      {
                        addPerson:addPersonAction   // 将添加person的动作(acton)函数通过props转递给UI组件
                      }
                    )(Person)
                    ```
                -   src/redux/store.js&#x20;
                    ```react&#x20;jsx
                    /*
                        该文件专门用于暴露一个store对象，整个应用只存在一个store对象
                    */

                    // 引入createStore 专门用于创建redux中最核心的store对象
                    import {legacy_createStore as  createStore, applyMiddleware, combineReducers} from 'redux'
                    // 引入Count组件服务的reducer
                    import countReducer from './reducers/count.js'
                    //
                    import personReducer from './reducers/person.js'
                    // 用于支持异步action
                    import thunk from 'redux-thunk'
                     // 汇总所有的 reducer 命名为allReducer
                    const allReducer = combineReducers({
                        countValue:countReducer,
                        personObj:personReducer
                    }) 
                    // 暴露store
                    export default createStore(allReducer, applyMiddleware(thunk))
                    ```
                ***
                Count组件的数据与Person组件的数据共享

                ![](../image/2023-23-03-2038__P3ZuhO71C.gif)
                -   src/container/Person/Person.jsx
                    ```react&#x20;jsx
                    import React, { Component } from 'react'
                    //
                    // 引入connect用于连接UI组件与redux
                    import {connect} from 'react-redux'
                    // 
                    import { addPersonAction } from '../../redux/actions/person'
                    //
                    import SnowFlake from '../../plugin/snowFlake'

                    class Person extends Component {
                      addPerson = () => {
                        const name = this.inputName.value
                        const age  = this.inputAge.value
                        const constObj = {id:SnowFlake(), name, age}
                        // console.log('Person, 输入框中传递过来的值：', constObj)
                        // console.log('Person, this.props', this.props)
                        this.props.addPerson(constObj)  // 调用从容器组件中传递过来的方法用于添加person
                      }
                      render() {
                        return (
                          <div>

                            <div className="container m-0 p-0">
                              <form>
                                <div>
                                  <div className="input-group input-group-sm mb-3">
                                    <span className="input-group-text" id="inputGroup-sizing-sm">人名</span>
                                    <input ref={(a) => {this.inputName = a}} type="text" className="form-control" aria-label="Sizing example input" aria-describedby="inputGroup-sizing-sm" />
                                  </div>
                                  <div className="input-group input-group-sm mb-3">
                                    <span className="input-group-text" id="inputGroup-sizing-sm">年龄</span>
                                    <input ref={(a) => {this.inputAge = a}} type="text" className="form-control" aria-label="Sizing example input" aria-describedby="inputGroup-sizing-sm" />
                                  </div>

                                </div>
                                <div>
                                  <div className="d-grid gap-2">
                                    <button className="btn btn-primary" type="button" onClick={this.addPerson}>添加</button>
                                  </div>
                                </div>
                              </form>
                               <div>读取来此Count组件的求和的值：{this.props.countValue}</div> 
                            </div>
                            <ul className='list-group mt-3'>
                              {
                                this.props.personObj.map((person)=>{
                                  return <li key={person.id} className='list-group-item'>{person.name}--{person.age}</li>
                                })
                              }
                            </ul>
                          </div>
                        )
                      }
                    }

                    // 容器组件
                    export default connect(
                      state => ({
                        personObj:state.personObj,
                         countValue:state.countValue   // 获取来自count组件的求和的值 
                      })  // 将store中的关于perosn的状态传递给是组件
                      ,
                      {
                        addPerson:addPersonAction   // 将函数转递给UI组件
                      }
                    )(Person)
                    ```
                -   src/container/Count/index.jsx
                    ```react&#x20;jsx
                    // 引入UI组件 // 优化 ， 将UI组件合并到一起
                    // import Count from "../../components/Count";
                    // 引入connect用于连接UI组件与redux
                    import {connect} from 'react-redux'
                    import { createIncrementAction, createDecrementAction,createIncrementAsynAction } from "../../redux/actions/count";


                    // 传递给UI组件的状态与方法
                    // 在react-redux已经在传递状态的时候，把state也就是从App中传递过来的store的值放在了state(第一个参数)中
                    //// 从这里传入子组件(UI组件)中的props中，UI组件就只需要从props中调用(来自redux store的参数)既可
                    //// 这步相当于redux api的getState()
                    // function mapStateToProps(state) {
                    //     return {count:state}
                    // }
                    // function mapDispatchToProps(dispatch) {
                    //     // return {increment:()=>{console.log('在容器组件中传递参数给UI组件的方法返回值的执行')}}
                    //     return {
                    //         increment:(number)=>{dispatch(createIncrementAction(number))},
                    //         decrement:(number)=>{dispatch(createDecrementAction(number))},
                    //         incrementAsyn:(number)=>{dispatch(createIncrementAsynAction(number, 500))},
                    //     }
                    // }
                    // // 创建并暴露一个Count的容器组件
                    // export default connect(mapStateToProps, mapDispatchToProps)(Count)
                    // ----------------------简写
                    import React, { Component } from 'react'
                    import Calculate from "../../components/Count/Calculate/Calculate";
                    import Header from "../../components/Count/Header/Header";

                    // UI 组件
                    class Count extends Component {
                      render() {
                        // console.log('Count, this.props', this.props)
                        // console.log('2在UI组件中，在容器中间中传递过来的方法：', this.props.increment)
                        // console.log('4在UI组件中，在容器组件中传递过来的值(状态)：', this.props.count)

                        return (
                          <div>
                            <Header count={this.props.count} />
                            <Calculate count={this.props}/>
                             <div>读取来此Person组件的条目总数：{this.props.totalPerson}</div> 
                          </div>
                        )
                      }
                    }

                    // 容器组件
                    // connect(mapStateToProps, mapDispatchToProps)(组件名)
                    export default connect(
                        state => ({
                          count:state.countValue,
                           totalPerson:state.personObj.length 
                        })
                        , 
                        {
                            increment:createIncrementAction,
                            decrement:createDecrementAction,
                            incrementAsyn:createIncrementAsynAction,
                        }
                        )(Count)
                    ```
                -   src/redux/store.js&#x20;
                    ```react&#x20;jsx
                    /*
                        该文件专门用于暴露一个store对象，整个应用只存在一个store对象
                    */

                    // 引入createStore 专门用于创建redux中最核心的store对象
                    import {legacy_createStore as  createStore, applyMiddleware, combineReducers} from 'redux'
                    // 引入Count组件服务的reducer
                    import countReducer from './reducers/count.js'
                    //
                    import personReducer from './reducers/person.js'
                    // 用于支持异步action
                    import thunk from 'redux-thunk'
                     // 汇总所有的 reducer 命名为allReducer
                    const allReducer = combineReducers({
                        countValue:countReducer,
                        personObj:personReducer
                    }) 
                    // 暴露store
                    export default createStore(allReducer, applyMiddleware(thunk))
                    ```
    -   [x] [112 112\_尚硅谷\_react教程\_纯函数\_Duration-18Min](https://www.bilibili.com/video/BV1wy4y1D7JT/?p=112 "112 112_尚硅谷_react教程_纯函数_Duration-18Min")&#x20;
        -   \[笔记] 纯函数[¶](https://www.bilibili.com/video/BV1wy4y1D7JT?t=814.4\&p=112 "¶")
            -   在React中更新数据，比如数组，需要返回一个新的数组，不然更新了数据将不会重新渲染页面
            -   `reducer`必须为一个纯函数
            ![](../image/image_YxA3qg9w0G.png)
    -   [x] [113 113\_尚硅谷\_react教程\_redux开发者工具\_Duration-14Min](https://www.bilibili.com/video/BV1wy4y1D7JT/?p=113 "113 113_尚硅谷_react教程_redux开发者工具_Duration-14Min")
        -   \[笔记][\[JS库\]redux-devtools-extension](\[JS库]redux-devtools-extension_uSSwSmKuJGnZx9pLBsgvkf.md "\[JS库]redux-devtools-extension")的使用
            -   示例：src/redux/store.js
                ```react&#x20;jsx
                /*
                    该文件专门用于暴露一个store对象，整个应用只存在一个store对象
                */

                // 引入createStore 专门用于创建redux中最核心的store对象
                import {legacy_createStore as  createStore, applyMiddleware, combineReducers} from 'redux'
                // 引入Count组件服务的reducer
                import countReducer from './reducers/count.js'
                //
                import personReducer from './reducers/person.js'
                // 用于支持异步action
                import thunk from 'redux-thunk'
                // 引入redux插件
                 import { composeWithDevTools } from 'redux-devtools-extension'; 
                // 汇总所有的 reducer 命名为allReducer
                const allReducer = combineReducers({
                    countValue:countReducer,
                    personObj:personReducer
                })
                // 暴露store
                 export default createStore(allReducer, composeWithDevTools(applyMiddleware(thunk)))
                ```
            ![](../image/image_F11Y9m0_Vf.png)

    -   [x] [114 114\_尚硅谷\_react教程\_最终版\_Duration-23Min](https://www.bilibili.com/video/BV1wy4y1D7JT/?p=114 "114 114_尚硅谷_react教程_最终版_Duration-23Min")
        -   \[笔记]
            -   示例： 优化代码，尽可能的触发简写方式

                ![](../image/image_1I2NgEStMG.png)

                将原本放在store中的汇总reducer放到了src/redux/reducers/index.js中并导出引用
                -   src/redux/reducers/index.js
                    ```react&#x20;jsx
                    // import { combineReducers } from 'redux'
                    // // 引入Count组件服务的reducer
                    // import countReducer from './count.js'
                    // //
                    // import personReducer from './person.js'

                    // // 汇总所有的 reducer 命名为allReducer
                    // export default combineReducers({
                    //     countValue:countReducer,
                    //     personObj:personReducer
                    // })

                    import { combineReducers } from 'redux'
                    // 引入Count组件服务的reducer
                    import count from './count.js'
                    //
                    import person from './person.js'

                    // 汇总所有的 reducer 命名为allReducer
                    export default combineReducers({
                         countValue:count,
                        personObj:person 
                    })


                    ```
                -   src/redux/store.js
                    ```react&#x20;jsx
                    /*
                        该文件专门用于暴露一个store对象，整个应用只存在一个store对象
                    */

                    // 引入createStore 专门用于创建redux中最核心的store对象
                    import {legacy_createStore as  createStore, applyMiddleware } from 'redux'
                    // 引入汇总的reducer
                     import reducer from './reducers' 
                    // 用于支持异步action
                    import thunk from 'redux-thunk'
                    // 引入redux插件
                    import { composeWithDevTools } from 'redux-devtools-extension';

                    // 暴露store
                    // export default createStore(allReducer, applyMiddleware(thunk))
                    export default createStore(reducer, composeWithDevTools(applyMiddleware(thunk)))
                    ```
                优化action中的变量名称
                -   src/redux/actions/count.js
                    ```react&#x20;jsx
                    // 引入常量
                    import { INCREMENT, DECREMENT } from "../constant"

                    // 专门为Calculate组件生成action对象

                    // function createIncrementAction(data) {
                    //     return {type:'increment', data}
                    // }

                    // 简化
                    // 同步 action
                    export const  increment  = (data) => ({type:INCREMENT, data})   // 加的动作
                    export const  decrement  = (data) => ({type:DECREMENT, data})   // 减的动作
                    // 异步 action
                    export const  incrementAsyn  = (data, time) => {                // 异步加的动作
                        // return () => {
                        //     setTimeout(() => {
                        //         store.dispatch(createIncrementAction(data))
                        //     }, time);
                        // }
                        // 因为会传给store，所以这里可以不用引入store
                        // import store from "./store"
                        return (dispatch) => {
                            setTimeout(() => {
                                dispatch(increment(data))
                            }, time);
                        }
                    } 
                    ```
                -   src/container/Count/index.jsx
                    ```react&#x20;jsx
                    // 引入UI组件 // 优化 ， 将UI组件合并到一起
                    // import Count from "../../components/Count";
                    // 引入connect用于连接UI组件与redux
                    import {connect} from 'react-redux'
                     import { increment, decrement,incrementAsyn } from "../../redux/actions/count"; 


                    // 传递给UI组件的状态与方法
                    // 在react-redux已经在传递状态的时候，把state也就是从App中传递过来的store的值放在了state(第一个参数)中
                    //// 从这里传入子组件(UI组件)中的props中，UI组件就只需要从props中调用(来自redux store的参数)既可
                    //// 这步相当于redux api的getState()
                    // function mapStateToProps(state) {
                    //     return {count:state}
                    // }
                    // function mapDispatchToProps(dispatch) {
                    //     // return {increment:()=>{console.log('在容器组件中传递参数给UI组件的方法返回值的执行')}}
                    //     return {
                    //         increment:(number)=>{dispatch(createIncrementAction(number))},
                    //         decrement:(number)=>{dispatch(createDecrementAction(number))},
                    //         incrementAsyn:(number)=>{dispatch(createIncrementAsynAction(number, 500))},
                    //     }
                    // }
                    // // 创建并暴露一个Count的容器组件
                    // export default connect(mapStateToProps, mapDispatchToProps)(Count)
                    // ----------------------简写
                    import React, { Component } from 'react'
                    import Calculate from "../../components/Count/Calculate/Calculate";
                    import Header from "../../components/Count/Header/Header";

                    // UI 组件
                    class Count extends Component {
                      render() {
                        // console.log('Count, this.props', this.props)
                        // console.log('2在UI组件中，在容器中间中传递过来的方法：', this.props.increment)
                        // console.log('4在UI组件中，在容器组件中传递过来的值(状态)：', this.props.count)

                        return (
                          <div>
                            <Header count={this.props.count} />
                            <Calculate count={this.props}/>
                            <div>读取来此Person组件的条目总数：{this.props.totalPerson}</div>
                          </div>
                        )
                      }
                    }

                    // 容器组件
                    // connect(mapStateToProps, mapDispatchToProps)(组件名)
                    export default connect(
                        state => ({
                          count:state.countValue,
                          totalPerson:state.personObj.length
                        })
                        , 
                        {
                            // // increment:createIncrementAction,
                            // // decrement:createDecrementAction,
                            // // incrementAsyn:createIncrementAsynAction,
                            // increment:increment,
                            // decrement:decrement,
                            // incrementAsyn:incrementAsyn,
                             increment,
                            decrement,
                            incrementAsyn, 
                        }
                        )(Count)
                    ```
                -   src/redux/actions/person.js
                    ```react&#x20;jsx
                    // 引入常量
                    import { ADD_PERSON } from '../constant'

                    //
                    export const addPerson = (personObj) => ({type:ADD_PERSON, data:personObj})

                    ```
                -   src/container/Person/Person.jsx
                    ```react&#x20;jsx
                    import React, { Component } from 'react'
                    //
                    // 引入connect用于连接UI组件与redux
                    import {connect} from 'react-redux'
                    // 
                     import { addPerson } from '../../redux/actions/person' 
                    //
                    import SnowFlake from '../../plugin/snowFlake'

                    class Person extends Component {
                      addPerson = () => {
                        const name = this.inputName.value
                        const age  = this.inputAge.value
                        const constObj = {id:SnowFlake(), name, age}
                        // console.log('Person, 输入框中传递过来的值：', constObj)
                        // console.log('Person, this.props', this.props)
                        this.props.addPerson(constObj)  // 调用从容器组件中传递过来的方法用于添加person
                      }
                      render() {
                        return (
                          <div>

                            <div className="container m-0 p-0">
                              <form>
                                <div>
                                  <div className="input-group input-group-sm mb-3">
                                    <span className="input-group-text" id="inputGroup-sizing-sm">人名</span>
                                    <input ref={(a) => {this.inputName = a}} type="text" className="form-control" aria-label="Sizing example input" aria-describedby="inputGroup-sizing-sm" />
                                  </div>
                                  <div className="input-group input-group-sm mb-3">
                                    <span className="input-group-text" id="inputGroup-sizing-sm">年龄</span>
                                    <input ref={(a) => {this.inputAge = a}} type="text" className="form-control" aria-label="Sizing example input" aria-describedby="inputGroup-sizing-sm" />
                                  </div>

                                </div>
                                <div>
                                  <div className="d-grid gap-2">
                                    <button className="btn btn-primary" type="button" onClick={this.addPerson}>添加</button>
                                  </div>
                                </div>
                              </form>
                              <div>读取来此Count组件的求和的值：{this.props.countValue}</div>
                            </div>
                            <ul className='list-group mt-3'>
                              {
                                this.props.personObj.map((person)=>{
                                  return <li key={person.id} className='list-group-item'>{person.name}--{person.age}</li>
                                })
                              }
                            </ul>
                          </div>
                        )
                      }
                    }

                    // 容器组件
                    export default connect(
                      state => ({
                        personObj:state.personObj,
                        countValue:state.countValue   // 获取来自count组件的求和的值
                      })  // 将store中的关于perosn的状态传递给是组件
                      ,
                      {
                        // // addPerson:addPersonAction   // 将函数转递给UI组件
                        // addPerson:addPerson   // 将函数转递给UI组件
                         addPerson 
                      }
                    )(Person)
                    ```
    ***
    -   [x] [115 115\_尚硅谷\_react教程\_项目打包运行\_Duration-7Min](https://www.bilibili.com/video/BV1wy4y1D7JT/?p=115 "115 115_尚硅谷_react教程_项目打包运行_Duration-7Min")
        -   \[笔记]`npm run build`[¶](https://www.bilibili.com/video/BV1wy4y1D7JT?t=116.2\&p=115 "¶")

            放到Web服务器中即用

            ![](../image/image_5x3t1aepx7.png)
    ***
    ## 扩展
    -   [x] [116 116\_尚硅谷\_react教程\_扩展1\_setState\_Duration-26Min](https://www.bilibili.com/video/BV1wy4y1D7JT/?p=116 "116 116_尚硅谷_react教程_扩展1_setState_Duration-26Min")
        -   \[笔记][\[React\]Hooks](\[React]Hooks_cdoA4yVU3YpyLmGC6GsSfF.md "\[React]Hooks"),`setState()`更新状态的2中写法：对象式的setState ：`setState(``stateChange``, [``callback``])`React的状态更新是异步更新()[¶](https://www.bilibili.com/video/BV1wy4y1D7JT?t=753.7\&p=116 "¶"); 函数式的setState： `setState(``updater``, [``])`使用原则

            ![](../image/image_Bxu6KDngWy.png)
            -   示例：对象式的setState ：`setState(``stateChange``, [``callback``])`

                关键

                ![](../image/image_QIwJ5rRtkP.png)

                ![](../image/image_RnWCbw1eaO.png)
            -   示例：函数式的setState： `setState(``updater``, [``callback``])`[¶](https://www.bilibili.com/video/BV1wy4y1D7JT?t=1281.5\&p=116 "¶")

                简化

                ![](../image/image_fEYdgZsVhw.png)

                ![](../image/image_ALW1frNuEf.png)
    -   [x] [117 117\_尚硅谷\_react教程\_扩展2\_lazyLoad\_Duration-20Min](https://www.bilibili.com/video/BV1wy4y1D7JT/?p=117 "117 117_尚硅谷_react教程_扩展2_lazyLoad_Duration-20Min")
        -   \[笔记]
            -   示例：路由懒加载 \[lazyLoad|懒加载,`lazy()`,`Suspense``fallback`]
                -   `lazy()`与`Suspense`需要一起使用，否则报错
                -   v1：懒加载时，加载的样式直接写加载的样式


                    -   效果：在网速慢时&#x20;

                        ![](../image/image_HXF4NZYfLW.png)
                    ![](../image/image_hNzTPBj4JO.png)

                    ![](../image/image_XSj_Wil_LY.png)
                -   v2：懒加载时，加载的样式写一个加载组件并引入

                    1、创建loading组件

                    2、导入loading组件

                    ![](../image/image_aqv6ODN3i7.png)

                    3、加载

                    ![](../image/image_czv_cmcWCr.png)
    -   [x] [118 118\_尚硅谷\_react教程\_扩展3\_stateHook\_Duration-18Min](https://www.bilibili.com/video/BV1wy4y1D7JT/?p=118 "118 118_尚硅谷_react教程_扩展3_stateHook_Duration-18Min")
        -   \[笔记][\[React\]Hooks](\[React]Hooks_cdoA4yVU3YpyLmGC6GsSfF.md "\[React]Hooks")函数式组件

            ![](../image/image_Kzgf2yExt_.png)
            -   示例：求和案例的类式组件与函数式组件的实现
                -   示例：类式组件实现

                    ![](../image/image_fcSEgmXCyR.png)
                -   示例：函数式组件实现 \[`State Hook``React.useState()`[¶](https://www.bilibili.com/video/BV1wy4y1D7JT?t=579.7\&p=118 "¶") [¶](https://www.bilibili.com/video/BV1wy4y1D7JT?t=581.8\&p=118 "¶"),数组的解构赋值]
                    -   写法一：`React.useState()`第二个参数为一个函数`FUN()`，用于更新第一个参数的值; 当调用状态更新函数时，React 会使用前一个状态的值作为默认参数传递给更新函数

                        ![](../image/image_ehWTawRRyw.png)
                    -   写法二：`React.useState()`第二个参数为一个函数`FUN()`，用于更新第一个参数的值; 当调用状态更新函数时，React 会使用前一个状态的值作为默认参数传递给更新函数(与函数式的setState： `setState(``updater``, [``callback``])`相似)

                        ![](../image/image_PLiXjl5c-F.png)
                        -   v1

                            ![](../image/image_chNMAzbwuu.png)
                            -
                    ![](../image/image_JSP6eRWt19.png)
    -   [x] [119 119\_尚硅谷\_react教程\_扩展4\_EffectHook\_Duration-21Min](https://www.bilibili.com/video/BV1wy4y1D7JT/?p=119 "119 119_尚硅谷_react教程_扩展4_EffectHook_Duration-21Min")
        -   \[笔记]

            ![](../image/image_KgGVi9I-cc.png)
            -   示例：数字每秒加1，与卸载组件 \[[\[React\]Hooks](\[React]Hooks_cdoA4yVU3YpyLmGC6GsSfF.md "\[React]Hooks")`React.useEffect()`,`ReactDOM.unmountComponentAtNote()`[¶](https://www.bilibili.com/video/BV1wy4y1D7JT?t=823.9\&p=119 "¶")]
                -   示例：数字每秒加1，与卸载组件：类式组件实现

                    ![](../image/image_UshmD3RQry.png)

                    ![](../image/image_Ze6TbrqCii.png)
                -   示例：数字每秒加1，与卸载组件：函数式组件实现
                    -   v1

                        ![](../image/image_FHaOV9LZfN.png)

                        ![](../image/image_pQrJyIWhxP.png)
                    -   函数式组件中`React.useEffect()`的返回函数相当于`componentWillUnmount()`

                        ![](../image/image_RCQO9iE8VI.png)
                    ![](../image/image_DGipe8jcFk.png)

                    ![](../image/image_l0rFDUkhMk.png)

                    ![](../image/image_LVSyCktcNA.png)
    -   [x] [120 120\_尚硅谷\_react教程\_扩展5\_RefHook\_Duration-4Min](https://www.bilibili.com/video/BV1wy4y1D7JT/?p=120 "120 120_尚硅谷_react教程_扩展5_RefHook_Duration-4Min")
        -   \[笔记]

            ![](../image/image_UDzt_B7vF9.png)
            -   示例：获取输入框中的数据并提示 \[[\[React\]Hooks](\[React]Hooks_cdoA4yVU3YpyLmGC6GsSfF.md "\[React]Hooks")`React.useRef()`]

                1创建

                ![](../image/image_FIqwQcqiGj.png)

                3调用函数

                ![](../image/image_REgakDTJKz.png)

                2设置事件

                ![](../image/image_tc0da9cGpx.png)
    -   [x] [121 121\_尚硅谷\_react教程\_扩展6\_Fragment\_Duration-6Min](https://www.bilibili.com/video/BV1wy4y1D7JT/?p=121 "121 121_尚硅谷_react教程_扩展6_Fragment_Duration-6Min")
        -   \[笔记]
            -   示例：去除return中包含的一层div \[`Fragment`]

                ![](../image/image_B_1rvbKDfi.png)

                ![](../image/image_HUs4I91TGS.png)
    -   [x] [122 122\_尚硅谷\_react教程\_扩展7\_Context\_Duration-26Min](https://www.bilibili.com/video/BV1wy4y1D7JT/?p=122 "122 122_尚硅谷_react教程_扩展7_Context_Duration-26Min")
        -   \[笔记

            ![](../image/image_GOQii3pmHg.png)
            -
                > 传多个值，就传对象既可
                -   方式一：类式组件使用Context

                    ![](../image/image_bg-oSEGagh.png)

                    ![](../image/image_PEj0A-P1Vu.png)
                -   方式二：函数式组件使用Context
                    -   v2：简化代码

                        ![](../image/image_ilVmH4dWP-.png)

                        ![](../image/image_4_-3RrjCW6.png)
                    -   v1&#x20;

                        ![](../image/image__hHqFzkdbV.png)
    -   [x] [123 123\_尚硅谷\_react教程\_扩展8\_PureComponent\_Duration-44Min](https://www.bilibili.com/video/BV1wy4y1D7JT/?p=123 "123 123_尚硅谷_react教程_扩展8_PureComponent_Duration-44Min")
        -   \[笔记] `shouldComponentUpdate()`可接收两个参数[¶](https://www.bilibili.com/video/BV1wy4y1D7JT?t=1115.1\&p=123 "¶")

            ![](../image/image_MioPWw9-8r.png)
            -   示例：[\[React\]组件优化](\[React]组件优化_g7r7iofq8ju6UQsmkXop5c.md "\[React]组件优化")
                -   解决方式1：自己手动重写`shouldComponentUpdate()`

                    ![](../image/image_wy0qyd63Bm.png)
                -   解决方式2：不使用`Component`改用`PureComponent` \[重写了`shouldComponentUpdate()` \[[🖼️ 图片](../image/image_18XPAjjZdy.png "🖼️ 图片")]]

                    ![](../image/image_-pGj_pBpOx.png)
    -   [x] [124 124\_尚硅谷\_react教程\_扩展9\_renderProps\_Duration-25Min](https://www.bilibili.com/video/BV1wy4y1D7JT/?p=124 "124 124_尚硅谷_react教程_扩展9_renderProps_Duration-25Min")
        -   \[笔记][renderProps](renderProps_xt8dBGp9Cm1yVzaUWSihhL.md "renderProps")

            ![](../image/image_TUO_HaOr9j.png)
            -   示例：获取组件包含的标签体内容 \[`children`]

                ![](../image/image_w6s2aFSOaH.png)
            -   示例：组件A中包含组件B的情况下(是否传递props) \[`children`]
                -   不通过props传值的情况

                    ![](../image/image_n-2lrsw9Fl.png)
                -   要通过props传值的情况[¶](https://www.bilibili.com/video/BV1wy4y1D7JT?t=1053.9\&p=124 "¶")

                    ![](../image/image_J-VsPdOmW0.png)

                    ![](../image/image_mV4InY6TJP.png)
                -   示例：(C)将组件插入到指定位置 如Vue中的插槽 \[props,[renderProps](renderProps_xt8dBGp9Cm1yVzaUWSihhL.md "renderProps"),[\[React\]插槽机制](\[React]插槽机制_uuaHRdrQYxNTMe2KLps9ws.md "\[React]插槽机制"), [\[Web\]vue](\[Web]vue_dXjyjimA6khnzQBPjcenKU.md "\[Web]vue")]

                    ![](../image/image_E_37jHn3eU.png)
                -   示例：(C)将组件插入到指定位置 如Vue中的插槽 \[props,[renderProps](renderProps_xt8dBGp9Cm1yVzaUWSihhL.md "renderProps"),[\[React\]插槽机制](\[React]插槽机制_uuaHRdrQYxNTMe2KLps9ws.md "\[React]插槽机制"), [\[Web\]vue](\[Web]vue_dXjyjimA6khnzQBPjcenKU.md "\[Web]vue")]

                    ![](../image/image_E_37jHn3eU.png)
    -   [x] [125 125\_尚硅谷\_react教程\_扩展10\_ErrorBoundary\_Duration-31Min](https://www.bilibili.com/video/BV1wy4y1D7JT/?p=125 "125 125_尚硅谷_react教程_扩展10_ErrorBoundary_Duration-31Min")
        -   \[笔记]  \[`getDerivedStateFromError()`[¶](https://www.bilibili.com/video/BV1wy4y1D7JT?t=1136.3\&p=125 "¶"),`componentDidCatch()`[¶](https://www.bilibili.com/video/BV1wy4y1D7JT?t=1567.3\&p=125 "¶"), 提到`getDerivedStateFromProps()`]

            ![](../image/image_WVWNuTdIym.png)
            1.  `getDerivedStateFromProps()`使用场景十分少(在state在任何时候都取决于props时)，从属性获取派生状态; 需要返回对象属性(如`{count:2}`或者Null
                -   可以接收props与state属性
            ***
            -   示例：发生错误，显示了错误页面并且发送错误信息到服务器进行检测(注意只在生产环境中完全有效)  \[错误边界,`getDerivedStateFromError()`[¶](https://www.bilibili.com/video/BV1wy4y1D7JT?t=1136.3\&p=125 "¶"),`componentDidCatch()`[¶](https://www.bilibili.com/video/BV1wy4y1D7JT?t=1567.3\&p=125 "¶")]
                -   当Child组件发生错误时

                    ![](../image/image_xnyKVSqfIW.png)
                -   v3 发生错误，显示了错误页面之后并且发送错误信息到需要的地方 componentDidCatch()

                    ![](../image/image_ttokj-_FvH.png)
                -   v2 当child组件错误时，显示错误页面 getDerivedStateFromError()

                    ![](../image/image_zuDlg1N9L0.png)

                    ![](../image/image_LzswWUFs08.png)
                -   v1 打印错误到console

                    ![](../image/image_8nEzEzTrLj.png)
    -   [x] [126 126\_尚硅谷\_react教程\_组件间通信方式总结\_Duration-6Min](https://www.bilibili.com/video/BV1wy4y1D7JT/?p=126 "126 126_尚硅谷_react教程_组件间通信方式总结_Duration-6Min")
        -   \[笔记]组件的通信方式总结

            ![](../image/image_59zTY1Bhpl.png)
    ***
    ## React Router 6 (使用函数式组件)
    -   [x] [127 127\_尚硅谷\_ReactRouter6教程\_课程说明\_Duration-4Min](https://www.bilibili.com/video/BV1wy4y1D7JT/?p=127 "127 127_尚硅谷_ReactRouter6教程_课程说明_Duration-4Min")
        -   \[笔记]`@6.x.x``@5.3.4`[\[JS库\]react-router](\[JS库]react-router_k1L1LG82a7A7jcLvv4zgmL.md "\[JS库]react-router"),[\[JS库\]react-route-dom](\[JS库]react-route-dom_jGUgd2TkFiY94rBUA6txun.md "\[JS库]react-route-dom"),[\[JS库\]react-router-native](\[JS库]react-router-native_6Art8Jk4oTaNiDm6c6EfEz.md "\[JS库]react-router-native")

            ![](../image/image_y2TExzeQ69.png)
            -   示例：
    -   [x] [128 128\_尚硅谷\_ReactRouter6教程\_一级路由\_Duration-14Min](https://www.bilibili.com/video/BV1wy4y1D7JT/?p=128 "128 128_尚硅谷_ReactRouter6教程_一级路由_Duration-14Min")
        -   \[笔记]
            -   示例1.1：rotuer6，懒加载 \[[\[JS库\]react-route-dom](\[JS库]react-route-dom_jGUgd2TkFiY94rBUA6txun.md "\[JS库]react-route-dom")`@6.x.x`,`Route`pathelement,`NavLink`,]\[`lazy()``Suspense``fallback`]
                -   ₛₗ新版本注意点`Switch`在`@6.x.x`被`Routes`替代&`Route`必须为的子元素[¶](https://www.bilibili.com/video/BV1wy4y1D7JT?t=849.4\&p=128 "¶") &component->element
                -   src/index.js
                    ```react&#x20;jsx
                    import { createRoot } from "react-dom/client";
                    //
                    import App from "./App";
                    //
                    import { BrowserRouter } from "react-router-dom";

                    const root  = createRoot(document.getElementById('root'))
                    root.render(
                        <BrowserRouter>
                            <App/>
                        </BrowserRouter>
                    )


                    ```
                -   src/App.jsx
                    ```react&#x20;jsx
                    import React, {lazy, Suspense} from 'react'
                    //
                    import { NavLink, Routes, Route } from 'react-router-dom'
                    //
                    // import About from './pages/About'
                    // import Home from './pages/Home'
                    // 改成懒加载
                    const About = lazy(() => import('./pages/About'))
                    const Home = lazy(() => import('./pages/Home'))


                    export default function App() {
                      return (
                        <div>
                          <div className="container">
                            <div className="row">
                              <div className="col-12">
                                <h2>react-router-dom@6.11.1</h2>
                              </div>
                              <div className="col-4">
                                <div className="list-group">
                                  <NavLink className="list-group-item " to='/home'>Home</NavLink>
                                  <NavLink className="list-group-item " to='/about'>About</NavLink>
                                </div>
                              </div>
                              <div className="col-8">
                                {/* 注册路由 以前的component属性换成了element*/}
                                <Suspense fallback={<h2>Loading...</h2>}>    {/* 懒加载与加载文字 */}
                                  <Routes>
                                    <Route path="/home" element={<Home/>} />
                                    <Route path="/about" element={<About/>} />
                                  </Routes>
                                </Suspense>
                              </div>
                            </div>
                          </div>
                      </div>
                      )
                    }

                    ```
                -   src/pages/About/index.jsx
                    ```react&#x20;jsx
                    import React from 'react'

                    export default function index() {
                      return (
                        <div>
                          About content
                        </div>
                      )
                    }

                    ```
                -   src/pages/Home/index.jsx
                    ```react&#x20;jsx
                    import React from 'react'

                    export default function index() {
                      return (
                        <div>
                          Home content
                        </div>
                      )
                    }

                    ```
    -   [x] [129 129\_尚硅谷\_ReactRouter6教程\_重定向\_Duration-10Min](https://www.bilibili.com/video/BV1wy4y1D7JT/?p=129 "129 129_尚硅谷_ReactRouter6教程_重定向_Duration-10Min")

        [https://www.bilibili.com/video/BV1wy4y1D7JT?t=172.4\&p=129](https://www.bilibili.com/video/BV1wy4y1D7JT?t=172.4\&p=129 "https://www.bilibili.com/video/BV1wy4y1D7JT?t=172.4\&p=129")
        -   \[笔记]
            -   \[对比]`Routes`|`Route`[¶](https://www.bilibili.com/video/BV1wy4y1D7JT?t=486.8\&p=129 "¶")

                ![](../image/image_NuXUvjkObd.png)
            -   \[E]No routes matched location "/" >> 没有匹配`/`的路径 >> 示例：`<Route path="/" element={<Navigate to="/home"/>}></Route>`
            ***
            -   示例1.2：✧设定重定向，设置自动跳转倒计时 \[[\[JS库\]react-route-dom](\[JS库]react-route-dom_jGUgd2TkFiY94rBUA6txun.md "\[JS库]react-route-dom"),`Redirect`>`Navigate`replace[¶](https://www.bilibili.com/video/BV1wy4y1D7JT?t=428.0\&p=129 "¶"),`React.useState()``React.useEffect()``[ARR]`,]\[`setInterval()`,`clearInterval()`,\[JS]三元运算符]

                ![](../image/2023-23-06-1227_SUT8hQ-Xv5.gif)
                -   src/App.jsx
                    ```react&#x20;jsx
                    import React, {lazy, Suspense} from 'react'
                    //
                    import { NavLink, Routes, Route,  Navigate  } from 'react-router-dom'
                    //
                    // import About from './pages/About'
                    // import Home from './pages/Home'
                    // 改成懒加载
                    const About = lazy(() => import('./pages/About'))
                    const Home = lazy(() => import('./pages/Home'))


                    export default function App() {
                      return (
                        <div>
                          <div className="container">
                            <div className="row">
                              <div className="col-12">
                                <h2>react-router-dom@6.11.1</h2>
                              </div>
                              <div className="col-4">
                                <div className="list-group">
                                  <NavLink className="list-group-item " to='/home'>Home</NavLink>
                                  <NavLink className="list-group-item " to='/about'>About</NavLink>
                                </div>
                              </div>
                              <div className="col-8">
                                {/* 注册路由 以前的component属性换成了element*/}
                                <Suspense fallback={<h2>Loading...</h2>}>    {/* 懒加载与加载文字 */}
                                  <Routes>
                                    <Route path="/home" element={<Home/>} />
                                    <Route path="/about" element={<About/>} />
                                     <Route path="/" element={<Navigate to="/home"/>}></Route>   {/* 重定向 解决警告：No routes matched location "/"  */}
                                  </Routes>
                                </Suspense>
                              </div>
                            </div>
                          </div>
                      </div>
                      )
                    }
                    ```
                -   src/pages/About/index.jsx
                    ```react&#x20;jsx
                    import React from 'react'
                    //
                    import { Navigate } from 'react-router-dom'

                    export default function Index() {
                       const [value, setValue] = React.useState(0)
                      const [second, setSecond] = React.useState(4)
                      console.log('value', value, 'second', second)
                      // 点击时间 点击按钮加1
                      function add(){
                        setValue(value + 1)
                      }
                      // 点击事件，点击按钮加1s等待跳转时间
                      function addTime(){
                        setSecond(second + 1)
                      }
                      // 时间倒计时，
                      React.useEffect(()=>{
                        let timer =  setInterval(() => {
                          setSecond(second - 1)
                        }, 1000);
                        return ()=>{
                          clearInterval(timer)
                        }
                      }, [second]) 

                      return (
                        <div>
                          <div>
                            <div className="d-grid gap-2">
                               <button id='1' type="button" onClick={add} className="btn border">点击{value}</button> 
                               {/ * 三元判断：如果second为0则跳转到Home页面 */}
                               {second === 0 ? <Navigate to='/home'></Navigate> :
                              <button id='2' type="button" onClick={addTime} className="btn border">准备跳转至Home页面，还剩{second}s</button>
                              } 

                            </div>
                          </div>
                        </div>
                      )
                    }
                    ```
    -   [x] [130 130\_尚硅谷\_ReactRouter6教程\_NavLink高亮\_Duration-6Min](https://www.bilibili.com/video/BV1wy4y1D7JT/?p=130 "130 130_尚硅谷_ReactRouter6教程_NavLink高亮_Duration-6Min")
        -   \[笔记]
            -   示例1.3：\[[\[JS库\]react-route-dom](\[JS库]react-route-dom_jGUgd2TkFiY94rBUA6txun.md "\[JS库]react-route-dom"),`@6.x.x`activeClassName=""->函数回调[¶](https://www.bilibili.com/video/BV1wy4y1D7JT?t=292.4\&p=130 "¶")>isActive[¶](https://www.bilibili.com/video/BV1wy4y1D7JT?t=224.3\&p=130 "¶")]

                ![](../image/image_6u0JG-6hCN.png)
                -   课程示例：

                    ![](../image/image_QQcxINYzrJ.png)
                -   示例：
                    -   public/index.html
                        ```react&#x20;jsx
                        <!DOCTYPE html>
                        <html lang="en">

                        <head>
                            <meta charset="UTF-8">
                            <meta http-equiv="X-UA-Compatible" content="IE=edge">
                            <meta name="viewport" content="width=device-width, initial-scale=1.0">
                            <link rel="icon" href="%PUBLIC_URL%/favicon.ico" />
                            <link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/bootstrap/5.2.3/css/bootstrap.min.css"
                            integrity="sha512-SbiR/eusphKoMVVXysTKG/7VseWii+Y3FdHrt0EpKgpToZeemhqHeZeLWLhJutz/2ut2Vw1uQEj2MbRF+TVBUA=="
                            crossorigin="anonymous" referrerpolicy="no-referrer" />
                             <style>
                                /* 自定义高亮action */
                                .customActionBackgroundColor {
                                    background-color: yellow;
                                    color: black;
                                }
                            </style> 
                            <title>React Router 6.11.1</title>
                        </head>

                        <body>
                            <div id="root"></div>
                        </body>

                        </html>
                        ```
                    -   src/App.jsx
                        ```react&#x20;jsx
                        import React, {lazy, Suspense} from 'react'
                        //
                        import { NavLink, Routes, Route, Navigate } from 'react-router-dom'
                        //
                        // import About from './pages/About'
                        // import Home from './pages/Home'
                        // 改成懒加载
                        const About = lazy(() => import('./pages/About'))
                        const Home = lazy(() => import('./pages/Home'))


                        export default function App() {
                          /*
                          function customActionBackgroundColor(Obj){
                            // 调用时返回一个对象包含两个属性
                            // console.log(Obj)           // >>> {isActive: true, isPending: false}
                            // console.log(Obj.isActive)  // >>> 是否为action(选中状态)，返回真假
                            return Obj.isActive ? 'list-group-item customActionBackgroundColor' : 'list-group-item'
                          }
                          */
                         // 优化
                           function customActionBackgroundColor({isActive}){
                            return isActive ? 'list-group-item customActionBackgroundColor' : 'list-group-item'
                          } 

                          return (
                            <div>
                              <div className="container">
                                <div className="row">
                                  <div className="col-12">
                                    <h2>react-router-dom@6.11.1</h2>
                                  </div>
                                  <div className="col-4">
                                    <div className="list-group">
                                      <NavLink className={ customActionBackgroundColor } to='/home'>Home</NavLink>
                                      <NavLink className={ customActionBackgroundColor } to='/about'>About</NavLink>
                                    </div>
                                  </div>
                                  <div className="col-8">
                                    {/* 注册路由 以前的component属性换成了element*/}
                                    <Suspense fallback={<h2>Loading...</h2>}>    {/* 懒加载与加载文字 */}
                                      <Routes>
                                        <Route path="/home" element={<Home/>} />
                                        <Route path="/about" element={<About/>} />
                                        <Route path="/" element={<Navigate to="/home"/>}></Route>  {/* 重定向 解决警告：No routes matched location "/"  */}
                                      </Routes>
                                    </Suspense>
                                  </div>
                                </div>
                              </div>
                          </div>
                          )
                        }
                        ```
    -   [x] [131 131\_尚硅谷\_ReactRouter6教程\_useRoutes路由表\_Duration-6Min](https://www.bilibili.com/video/BV1wy4y1D7JT/?p=131 "131 131_尚硅谷_ReactRouter6教程_useRoutes路由表_Duration-6Min")
        -   \[笔记]
            -   示例1.4：使用路由表 \[[\[JS库\]react-route-dom](\[JS库]react-route-dom_jGUgd2TkFiY94rBUA6txun.md "\[JS库]react-route-dom")[\[React\]路由表](\[React]路由表_hEc27DZ9mNpXhtJ6jQf6HJ.md "\[React]路由表"),`useRoutes`,lazyLoad|懒加载:`lazy()``Suspense`]
                -   课程示例：在页面中使用路由表

                    ![](../image/image_unmzS_inUh.png)

                    ![](../image/image_a6zaznRIGI.png)
                -   示例：使用路由表
                    -   src/routes/routes.jsx
                        ```react&#x20;jsx
                        // 懒加载
                        import { lazy }  from 'react'
                        // 重定向
                        import { Navigate } from 'react-router-dom'
                        // 懒加载
                        const About = lazy(() => import('../pages/About'))
                        const Home = lazy(() => import('../pages/Home'))
                        // 路由配置
                         const routes = [ 
                            {
                                path:'/home',
                                element:<Home/>
                            },
                            {
                                path:'/about',
                                element:<About/>
                            },
                            {
                                path:'/',
                                element:<Navigate to="/home"/>
                            },
                         ] 
                        export default routes
                        ```
                    -   src/App.jsx

                        [file://xn--%20import%20routes%20from%20%27-b845ccw5pxd0j9spfnusb./routes/routes'](file://xn--%20import%20routes%20from%20%27-b845ccw5pxd0j9spfnusb./routes/routes' "file://xn--%20import%20routes%20from%20%27-b845ccw5pxd0j9spfnusb./routes/routes'")
                        ```react&#x20;jsx
                        import React, {Suspense } from 'react'
                        //
                        import { NavLink,  useRoutes } from 'react-router-dom'
                        // 导入路由表
                         import routes from './routes/routes' 
                        //
                        export default function App() {
                          // 自定义的active样式
                          function customActionBackgroundColor({isActive}){
                            return isActive ? 'list-group-item customActionBackgroundColor' : 'list-group-item'
                          }
                           // 使用路由表
                          const element = useRoutes(routes) 
                          //
                          return (
                            <div>
                              <div className="container">
                                <div className="row">
                                  <div className="col-12">
                                    <h2>react-router-dom@6.11.1</h2>
                                  </div>
                                  <div className="col-4">
                                    <div className="list-group">
                                      <NavLink className={customActionBackgroundColor} to='/home'>Home</NavLink>
                                      <NavLink className={customActionBackgroundColor} to='/about'>About</NavLink>
                                    </div>
                                  </div>
                                  <div className="col-8">
                                    {/* 注册路由 以前的component属性换成了element*/}
                                    <Suspense fallback={<h2>Loading...</h2>}>    {/* 懒加载与加载文字 */}
                                        {element}
                                    </Suspense>
                                  </div>
                                </div>
                              </div>
                          </div>
                          )
                        }
                        ```
    -   [x] [132 132\_尚硅谷\_ReactRouter6教程\_嵌套路由\_Duration-12Min](https://www.bilibili.com/video/BV1wy4y1D7JT/?p=132 "132 132_尚硅谷_ReactRouter6教程_嵌套路由_Duration-12Min")
        -   \[笔记]
            -   示例1.5：子路由 \[[\[JS库\]react-route-dom](\[JS库]react-route-dom_jGUgd2TkFiY94rBUA6txun.md "\[JS库]react-route-dom"),`Outlet`,end]
                -   子示例：设置链接时路径写全路径，要不就不写斜杠

                    ![](../image/image_OTst5Wa7IE.png)

                    ![](../image/2023-23-06-1748_zunDbaix9I.gif)
                -   子示例：加与不加end对比 \[匹配子路由时，父级不active]
                    ```react&#x20;jsx
                                <div className="list-group">
                                  <NavLink className={customActionBackgroundColor} end to='/home'>Home</NavLink>
                                  <NavLink className={customActionBackgroundColor} to='/about'>About</NavLink>
                                </div>
                    ```
                    ![](../image/image_-FJNtn573l.png)

                    ![](../image/image_JrHJDerJNF.png)
                ***
                -   src/pages/Home/index.jsx
                    ```react&#x20;jsx
                    import React from 'react'
                    //
                    import { NavLink,  Outlet  } from 'react-router-dom'
                    //
                    // import Anther from './Anther/Anther'
                    // import News from './News/News'
                    //
                    export default function index() {
                      return (
                        <div>
                          <div className="list-group list-group-horizontal mb-1">
                             {/* 使用路由表，设置链接时路径的写法：全路径; 不写斜杠; 相对路径 ./ */} 
                            <NavLink className="list-group-item" to="/home/news">News</NavLink>
                            <NavLink className="list-group-item" to="/home/anther">Anther</NavLink>
                            <NavLink className="list-group-item" to="news">News</NavLink>
                            <NavLink className="list-group-item" to="./anther">Anther</NavLink>
                          </div>
                          <div className="row">
                            {/* 路由表使用子路由，需要在哪里呈现页面 */}
                             <Outlet /> 
                          </div>
                        </div>
                      )
                    }
                    ```
                -   src/pages/Home/Anther/Anther.jsx
                    ```react&#x20;jsx
                    import React from 'react'

                    export default function Anther() {
                      return (
                        <div>
                          anther
                        </div>
                      )
                    }

                    ```
                -   src/pages/Home/News/News.jsx
                    ```react&#x20;jsx
                    import React from 'react'

                    export default function News() {
                      return (
                        <div>
                          news
                        </div>
                      )
                    }

                    ```
                -   src/routes/routes.jsx
                    ```react&#x20;jsx
                    // 懒加载
                    import { lazy }  from 'react'
                    // 重定向
                    import { Navigate } from 'react-router-dom'
                    // 懒加载
                    const About = lazy(() => import('../pages/About'))
                    const Home = lazy(() => import('../pages/Home'))
                     const News = lazy(()=> import('../pages/Home/News/News'))
                    const Anther = lazy(()=> import('../pages/Home/Anther/Anther')) 
                    // 路由配置
                    const routes = [
                        {
                            path:'/home', element:<Home/>,
                             children:[
                                {path:'news', element:<News/>},
                                {path:'anther', element:<Anther/>}, 
                             ] 
                        },
                        {
                            path:'/about',
                            element:<About/>
                        },
                        {
                            path:'/',
                            element:<Navigate to="/home"/>
                        }
                    ]
                    export default routes
                    ```
                    [path:'/home', element:\<Home/>,        children:\[            {path:'news', element:\<News/>},            {path:'anther', element:\<Anther/>},](<path:'/home', element:\<Home/\>,        children:\[            {path:'news', element:\<News/\>},            {path:'anther', element:\<Anther/\>},> "path:'/home', element:<Home/>,        children:\[            {path:'news', element:<News/>},            {path:'anther', element:<Anther/>},")
    -   [x] [133 133\_尚硅谷\_ReactRouter6教程\_路由的params参数\_Duration-12Min](https://www.bilibili.com/video/BV1wy4y1D7JT/?p=133 "133 133_尚硅谷_ReactRouter6教程_路由的params参数_Duration-12Min")
        -   \[笔记]\(F)路由组件传参方式1：`match.params`>`usePamars`|`useMatch`
            -   示例1.6.1：路由组件传参方式1：params，三级路由 \[[\[JS库\]react-route-dom](\[JS库]react-route-dom_jGUgd2TkFiY94rBUA6txun.md "\[JS库]react-route-dom"),[\[React\]路由表](\[React]路由表_hEc27DZ9mNpXhtJ6jQf6HJ.md "\[React]路由表")\[React路由表]`children`,`Outlet`,`usePamars`,嵌套路由,函数式组件]
                -   子示例：给子路由添加重定向：点击home，直接跳转到home里面news组件的页面 \[`Navigate`]
                    -   Code
                        ```react&#x20;jsx
                        // 懒加载
                        import { lazy }  from 'react'
                        // 重定向
                        import { Navigate } from 'react-router-dom'
                        // 懒加载
                        const About = lazy(() => import('../pages/About'))
                        const Home = lazy(() => import('../pages/Home'))
                        const News = lazy(()=> import('../pages/Home/News/News'))
                        const Anther = lazy(()=> import('../pages/Home/Anther/Anther'))
                        // 路由配置
                        const routes = [
                            {
                                path:'/home', element:<Home/>,
                                children:[
                                    {path:'news', element:<News/>},
                                    {path:'anther', element:<Anther/>},
                                    {path:'/home', element:<Navigate to="/home/news"/>}
                                ]
                            },
                            {
                                path:'/about',
                                element:<About/>
                            },
                            {
                                path:'/',
                                element:<Navigate to="/home"/>
                            }
                        ]
                        export default routes
                        ```
                    ![](../image/image_X8D6VgkML9.png)

                    ![](../image/image_FTZAaUK36W.png)
                -   子示例：路由表的嵌套路由 [\[React\]路由表](\[React]路由表_hEc27DZ9mNpXhtJ6jQf6HJ.md "\[React]路由表")
                    ```react&#x20;jsx
                    const routes = [
                        {
                            path:'/home', element:<Home/>,
                            children:[
                                {
                                    path:'news', element:<News/>,
                                     children:[
                                        {path:'detail', element:<Detail/>}
                                    ] 
                                },
                                {path:'anther', element:<Anther/>},
                                {path:'/home', element:<Navigate to="/home/news"/>},
                            ]
                        },
                        {
                            path:'/about',
                            element:<About/>
                        },
                        {
                            path:'/',
                            element:<Navigate to="/home"/>
                        }
                    ]
                    ```
                -   子示例：了解`useMatch`

                    ![](../image/image_0oxWp2a-4k.png)
                ***
                ![](../image/2023-23-06-2216_ZE9dZlWvLI.gif)
                ***
                -   src/pages/Home/News/News.jsx
                    ```react&#x20;jsx
                    import React, {useState} from 'react'
                    //
                    import { Link, Outlet } from 'react-router-dom'
                    //
                    export default function News() {
                      // 模拟数据
                      const [news] = useState([
                          {id:"01", title:'闻王昌龄左迁龙标遥有此寄'},
                          {id:"02", title:'望天门山'},
                          {id:"03", title:'早发白帝城'},
                      ])

                      return (
                        <div className='list-group'>
                          {
                            news.map((newItem) => {
                              return (
                                // <Link className='list-group-item text-center' key={newItem.id} to='detail'>{newItem.title}</Link>
                                <Link className='list-group-item text-center' key={newItem.id}  to={`detail/${newItem.id}/${newItem.title}`} >{newItem.title}</Link>  // 路由传参:params
                              )
                            })
                          }
                          <hr />
                          <Outlet />
                        </div>
                      )
                    }
                    ```
                -   src/routes/routes.jsx
                    ```react&#x20;jsx
                    // 懒加载
                    import { lazy }  from 'react'
                    // 重定向
                    import { Navigate } from 'react-router-dom'
                    // 懒加载
                    const About = lazy(() => import('../pages/About'))
                    const Home = lazy(() => import('../pages/Home'))
                    const News = lazy(()=> import('../pages/Home/News/News'))
                     const Anther = lazy(()=> import('../pages/Home/Anther/Anther'))
                    const Detail = lazy(()=> import('../pages/Home/News/Detail/Detail.jsx')) 
                    // 路由配置
                    const routes = [
                        {
                            path:'/home', element:<Home/>,
                            children:[
                                {
                                    path:'news', element:<News/>,
                                     children:[
                                        {path:'detail/:id/:title', element:<Detail/>}
                                    ] 
                                },
                                {path:'anther', element:<Anther/>},
                                // home页面重定向的
                                {path:'/home', element:<Navigate to="/home/news"/>},
                            ]
                        },
                        {
                            path:'/about',
                            element:<About/>
                        },
                        {
                            path:'/',
                            element:<Navigate to="/home"/>
                        }
                    ]
                    export default routes
                    ```

                    &#x20;           {path:'/home', element:\<Navigate to="/home/news"/>},
                -   src/pages/Home/News/Detail/Detail.jsx
                    ```react&#x20;jsx
                    import React, { useState }  from 'react'
                    //
                    import { useParams } from 'react-router-dom'
                    //
                    export default function Detail() {
                      // 模拟从数据库取出的数据
                      const [news] = useState([
                        {id:"01", content:[
                          [
                            '杨花落尽子规啼，',
                            '闻道龙标过五溪。',
                            '我寄愁心与明月，',
                            '随风直到夜郎西。',
                          ]
                        ]},
                        {id:"02", content:[
                          [
                            '天门中断楚江开，',
                            '碧水东流至此回。',
                            '两岸青山相对出，',
                            '孤帆一片日边来。',
                          ]
                        ]},
                        {id:"03", content:[
                          [
                            '朝辞白帝彩云间，',
                            '千里江陵一日还。',
                            '两岸猿声啼不住，',
                            '轻舟已过万重山。',
                          ]
                        ]}
                      ])

                       const {id, title} = useParams()   // 接收通过params的参数解构
                      // 找到对应id的值
                      const detailNew =  news.find(newItem => newItem.id === id);
                      // console.log(detailNew.content)  // >>> 输出一个数组，就是诗句
                      //
                      return (
                        <div>
                          {
                            detailNew.content.map(
                              (paragraph, index)=>{
                                return <div key={index} href="#" className="list-group-item list-group-item-action text-center">
                                   <div><strong>{title}</strong></div>
                                   {// 遍历两边就很奇怪...反正不是这次的重点算了
                                    paragraph.map(
                                      (i, index)=>{
                                        return <div key={index} >{i}</div>
                                      }
                                    )
                                   }
                                </div>
                              }
                            )
                          }
                        </div>
                      )
                    }


                    ```
                ***
                -   src/pages/Home/index.jsx 改了一下不重要的地方
                    ```react&#x20;jsx
                    import React from 'react'
                    //
                    import { NavLink, Outlet } from 'react-router-dom'
                    //
                    // import Anther from './Anther/Anther'
                    // import News from './News/News'
                    //
                    export default function index() {
                      return (
                        <div>
                          <div className="list-group list-group-horizontal justify-content-center  mb-1">
                            {/* 使用路由表，设置链接时路径的写法：全路径; 不写斜杠; 相对路径 ./ */}
                            <NavLink className="list-group-item" to="/home/news">News</NavLink>
                            <NavLink className="list-group-item" to="/home/anther">Anther</NavLink>
                          </div>
                          <div className="">
                            {/* 路由表使用子路由，需要在哪里呈现页面 */}
                            <Outlet />
                          </div>
                        </div>
                      )
                    }


                    ```
    -   [x] [134 134\_尚硅谷\_ReactRouter6教程\_路由的search参数\_Duration-9Min](https://www.bilibili.com/video/BV1wy4y1D7JT/?p=134 "134 134_尚硅谷_ReactRouter6教程_路由的search参数_Duration-9Min")
        -   \[笔记]\(F)路由组件传参方式2：`location.search`>`useSearchParams`|`useLoaction`
            -   示例1.6.2：路由组件传参方式2：search \[[\[JS库\]react-route-dom](\[JS库]react-route-dom_jGUgd2TkFiY94rBUA6txun.md "\[JS库]react-route-dom"),[\[React\]路由表](\[React]路由表_hEc27DZ9mNpXhtJ6jQf6HJ.md "\[React]路由表"),`useSearchParams``search.get(str)`setSearch[¶](https://www.bilibili.com/video/BV1wy4y1D7JT?t=366.6\&p=134 "¶"),`Object.entries()``Object.fromEntries()`]
                -   子示例：setSearch[¶](https://www.bilibili.com/video/BV1wy4y1D7JT?t=366.6\&p=134 "¶")

                    ![](../image/image_ks-jbTSSm5.png)
                -   子示例：`useLoaction`

                    ![](../image/image_VeOMYYnMBg.png)

                    ![](../image/image_X6XUJLRnDX.png)

                    ![](../image/image__yQVH9hR93.png)
                ***
                -   src/pages/Home/News/News.jsx
                    ```react&#x20;jsx
                    import React, {useState, Suspense} from 'react'
                    //
                    import { Link, Outlet } from 'react-router-dom'
                    //
                    export default function News() {
                      // 模拟数据
                      const [news] = useState([
                          {id:"01", title:'闻王昌龄左迁龙标遥有此寄'},
                          {id:"02", title:'望天门山'},
                          {id:"03", title:'早发白帝城'},
                      ])

                      return (
                        <div className='list-group'>
                          {
                            news.map((newItem) => {
                              return (
                                // <Link className='list-group-item text-center' key={newItem.id} to='detail'>{newItem.title}</Link>
                                // 通过params传参
                                // <Link className='list-group-item text-center' key={newItem.id} to={`detail/${newItem.id}/${newItem.title}`}>{newItem.title}</Link>  // 路由传参:params
                                <Link className='list-group-item text-center' key={newItem.id} to={` detail?id=${newItem.id}&title=${newItem.title} `}>{newItem.title}</Link>  // 路由传参:params
                              )
                            })
                          }
                          <hr />
                          <Suspense  fallback={<h2>加载诗句中...</h2>}>
                            <Outlet />
                          </Suspense>
                        </div>
                      )
                    }
                    ```
                -   src/routes/routes.jsx
                    ```react&#x20;jsx
                    // 懒加载
                    import { lazy }  from 'react'
                    // 重定向
                    import { Navigate } from 'react-router-dom'
                    // 懒加载
                    const About = lazy(() => import('../pages/About'))
                    const Home = lazy(() => import('../pages/Home'))
                    const News = lazy(()=> import('../pages/Home/News/News'))
                    const Anther = lazy(()=> import('../pages/Home/Anther/Anther'))
                    const Detail = lazy(()=> import('../pages/Home/News/Detail/Detail.jsx'))
                    // 路由配置
                    const routes = [
                        {
                            path:'/home', element:<Home/>,
                            children:[
                                {
                                    path:'news', element:<News/>,
                                    children:[
                                        // {path:'detail/:id/:title', element:<Detail/>}  // 通过params传参
                                         {path:'detail', element:<Detail/>}                 // 通过search传参
                                    ]
                                },
                                {path:'anther', element:<Anther/>},
                                // home页面重定向的
                                {path:'/home', element:<Navigate to="/home/news"/>},
                            ]
                        },
                        {
                            path:'/about',
                            element:<About/>
                        },
                        {
                            path:'/',
                            element:<Navigate to="/home"/>
                        }
                    ]
                    export default routes
                    ```

                    &#x20;           {path:'/home', element:\<Navigate to="/home/news"/>},
                -   src/pages/Home/News/Detail/Detail.jsx
                    ```react&#x20;jsx
                    import React,{ useState } from 'react'

                    // import { useParams } from 'react-router-dom'        // 通过 params 传参
                     import { useSearchParams } from 'react-router-dom'   // // 通过 search 传参
                    //
                    export default function Detail() {
                      // 模拟从数据库取出的数据
                      const [news] = useState([
                        {id:"01", content:[
                          [
                            '杨花落尽子规啼，',
                            '闻道龙标过五溪。',
                            '我寄愁心与明月，',
                            '随风直到夜郎西。',
                          ]
                        ]},
                        {id:"02", content:[
                          [
                            '天门中断楚江开，',
                            '碧水东流至此回。',
                            '两岸青山相对出，',
                            '孤帆一片日边来。',
                          ]
                        ]},
                        {id:"03", content:[
                          [
                            '朝辞白帝彩云间，',
                            '千里江陵一日还。',
                            '两岸猿声啼不住，',
                            '轻舟已过万重山。',
                          ]
                        ]}
                      ])
                      // ++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++
                      // const {id, title} = useParams()                              // 接收 params 的参数
                       const [search] = useSearchParams()                               // 接收 search 的参数
                      // const { id, title } = Object.fromEntries(search.entries());  // 接收 search 的参数 之 取值方式1 虽然是一行，但是看不懂...
                       const id = search.get('id')                                      // 接收 search 的参数 之 取值方式2 单独取，简单明了...
                        const title = search.get('title')                                 // 接收 search 的参数 之 取值方式2 单独取，简单明了...
                      //
                      // 取值检查
                      // console.log('search.entries()', search.entries())
                      // console.log('Detail', id, title)
                      // 找到对应id的值
                      const detailNew =  news.find(newItem => newItem.id === id);
                      // console.log(detailNew.content)  // >>> 输出一个数组，就是诗句
                      //
                      return (
                        <div>
                          {
                            detailNew.content.map(
                              (paragraph, index)=>{
                                return <div key={index} href="#" className="list-group-item list-group-item-action text-center">
                                   <div><strong>{title}</strong></div>
                                   {// 遍历两边就很奇怪...反正不是这次的重点算了
                                    paragraph.map(
                                      (i, index)=>{
                                        return <div key={index} >{i}</div>
                                      }
                                    )
                                   }
                                </div>
                              }
                            )
                          }
                        </div>
                      )
                    }



                    ```
    -   [x] [135 135\_尚硅谷\_ReactRouter6教程\_路由的state参数\_Duration-4Min](https://www.bilibili.com/video/BV1wy4y1D7JT/?p=135 "135 135_尚硅谷_ReactRouter6教程_路由的state参数_Duration-4Min")
        -   \[笔记]\(F)路由组件传参方式3：`location.state`>`useLoaction`
            -   示例：路由组件传参方式3：state \[[\[JS库\]react-route-dom](\[JS库]react-route-dom_jGUgd2TkFiY94rBUA6txun.md "\[JS库]react-route-dom"),[\[React\]路由表](\[React]路由表_hEc27DZ9mNpXhtJ6jQf6HJ.md "\[React]路由表")

                ![](../image/image_CB2zemhKoa.png)
                -   src/pages/Home/News/News.jsx
                    ```react&#x20;jsx
                    import React, {useState, Suspense} from 'react'
                    //
                    import { Link, Outlet } from 'react-router-dom'
                    //
                    export default function News() {
                      // 模拟数据
                      const [news] = useState([
                          {id:"01", title:'闻王昌龄左迁龙标遥有此寄'},
                          {id:"02", title:'望天门山'},
                          {id:"03", title:'早发白帝城'},
                      ])

                      return (
                        <div className='list-group'>
                          {
                            news.map((newItem) => {
                              return (
                                // <Link className='list-group-item text-center' key={newItem.id} to='detail'>{newItem.title}</Link>
                                // 通过params传参
                                // <Link className='list-group-item text-center' key={newItem.id} to={`detail/${newItem.id}/${newItem.title}`}>{newItem.title}</Link> 
                                // 通过search传参
                                // <Link className='list-group-item text-center' key={newItem.id} to={`detail?id=${newItem.id}&title=${newItem.title}`}>{newItem.title}</Link>
                                // 通过state传参
                                <Link className='list-group-item text-center' key={newItem.id}  to='detail' state={{id:newItem.id, title:newItem.title}}> {newItem.title}</Link>
                              )
                            })
                          }
                          <hr />
                          <Suspense  fallback={<h2>加载诗句中...</h2>}>
                            <Outlet />
                          </Suspense>
                        </div>
                      )
                    }
                    ```
                -   src/routes/routes.jsx
                    ```react&#x20;jsx
                    // 懒加载
                    import { lazy }  from 'react'
                    // 重定向
                    import { Navigate } from 'react-router-dom'
                    // 懒加载
                    const About = lazy(() => import('../pages/About'))
                    const Home = lazy(() => import('../pages/Home'))
                    const News = lazy(()=> import('../pages/Home/News/News'))
                    const Anther = lazy(()=> import('../pages/Home/Anther/Anther'))
                    const Detail = lazy(()=> import('../pages/Home/News/Detail/Detail.jsx'))
                    // 路由配置
                    const routes = [
                        {
                            path:'/home', element:<Home/>,
                            children:[
                                {
                                    path:'news', element:<News/>,
                                    children:[
                                        // {path:'detail/:id/:title', element:<Detail/>}  // 通过params传参
                                        // {path:'detail', element:<Detail/>},            // 通过search传参
                                        {path:'detail', element:<Detail/>}                // 通过state传参
                                    ]
                                },
                                {path:'anther', element:<Anther/>},
                                // home页面重定向的
                                {path:'/home', element:<Navigate to="/home/news"/>},
                            ]
                        },
                        {
                            path:'/about',
                            element:<About/>
                        },
                        {
                            path:'/',
                            element:<Navigate to="/home"/>
                        }
                    ]
                    export default routes
                    ```
                -   src/pages/Home/News/Detail/Detail.jsx
                    ```react&#x20;jsx
                    import React,{ useState } from 'react'

                    // import { useParams } from 'react-router-dom'        // 通过 params 传参
                    // import { useSearchParams } from 'react-router-dom'  // 通过 search 传参
                    import { useLocation } from 'react-router-dom';        // 通过 state 传参

                    //
                    export default function Detail() {
                      // 模拟从数据库取出的数据
                      const [news] = useState([
                        {id:"01", content:[
                          [
                            '杨花落尽子规啼，',
                            '闻道龙标过五溪。',
                            '我寄愁心与明月，',
                            '随风直到夜郎西。',
                          ]
                        ]},
                        {id:"02", content:[
                          [
                            '天门中断楚江开，',
                            '碧水东流至此回。',
                            '两岸青山相对出，',
                            '孤帆一片日边来。',
                          ]
                        ]},
                        {id:"03", content:[
                          [
                            '朝辞白帝彩云间，',
                            '千里江陵一日还。',
                            '两岸猿声啼不住，',
                            '轻舟已过万重山。',
                          ]
                        ]}
                      ])
                      // ++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++
                      // const {id, title} = useParams()                              // 接收 params 的参数
                      // const [search] = useSearchParams()                           // 接收 search 的参数
                      // const { id, title } = Object.fromEntries(search.entries());  // 接收 search 的参数 之 取值方式1 虽然是一行，但是看不懂...
                      // const id = search.get('id')                                  // 接收 search 的参数 之 取值方式2 单独取，简单明了...
                      // const title = search.get('title')                            // 接收 search 的参数 之 取值方式2 单独取，简单明了...
                      // 取值检查
                      // console.log('useLocation', useLocation())  // >>> {pathname: '/home/news/detail', search: '', hash: '',  state: {id: '01', title: '闻王昌龄左迁龙标遥有此寄'} , key: 'jh2mmbpe'}
                      // 接收 state 的参数 之 取值方式3
                       const {id, title} = useLocation().state 

                      //
                      // 取值检查
                      console.log('Detail', id, title)
                      // 找到对应id的值
                      const detailNew =  news.find(newItem => newItem.id === id);
                      // console.log(detailNew.content)  // >>> 输出一个数组，就是诗句
                      //
                      return (
                        <div>
                          {
                            detailNew.content.map(
                              (paragraph, index)=>{
                                return <div key={index} href="#" className="list-group-item list-group-item-action text-center">
                                   <div><strong>{title}</strong></div>
                                   {// 遍历两边就很奇怪...反正不是这次的重点算了
                                    paragraph.map(
                                      (i, index)=>{
                                        return <div key={index} >{i}</div>
                                      }
                                    )
                                   }
                                </div>
                              }
                            )
                          }
                        </div>
                      )
                    }


                    ```
    -   [x] [136 136\_尚硅谷\_ReactRouter6教程\_编程式路由导航\_Duration-12Min](https://www.bilibili.com/video/BV1wy4y1D7JT/?p=136 "136 136_尚硅谷_ReactRouter6教程_编程式路由导航_Duration-12Min")
        -   \[笔记]
            -   示例：实现函数式组件的编程式路由导航，页面的前进后退 \[[\[JS库\]react-route-dom](\[JS库]react-route-dom_jGUgd2TkFiY94rBUA6txun.md "\[JS库]react-route-dom"),[\[React\]路由表](\[React]路由表_hEc27DZ9mNpXhtJ6jQf6HJ.md "\[React]路由表"),函数式组件编程式路由导航,\[`useNavigate`,`Link``replace`]]

                ![](../image/2023-23-07-1608_25CK4qWadZ.gif)
                -   src/pages/Home/News/News.jsx
                    ```react&#x20;jsx
                    import React, {useState, Suspense} from 'react'
                    //
                    import { Link, Outlet,  useNavigate  } from 'react-router-dom'
                    //
                    export default function News() {
                      // 模拟数据
                      const [news] = useState([
                          {id:"01", title:'闻王昌龄左迁龙标遥有此寄'},
                          {id:"02", title:'望天门山'},
                          {id:"03", title:'早发白帝城'},
                      ])
                      // 编程式路由
                      // # 创建实例?
                       const navigate = useNavigate() 
                      // # 通过Push模式来跳转到详细页面
                       function showDetailPush(newItem){
                        console.log(navigate.history);
                        navigate('detail',
                        {
                          replace:false,
                          state:{
                            id:newItem.id,
                            title:newItem.title
                          }
                        },
                        )
                      } 
                      // # 通过Replace模式来跳转到详细页面
                       function showDetailReplace(newItem){
                        navigate('detail',
                          {
                            replace:true,
                            state:{
                              id:newItem.id,
                              title:newItem.title
                            }
                          },
                        )
                      } 
                      // # 前进
                       function goForward() {
                        navigate(1);
                      } 
                      // # 后退
                       function goBack() {
                        navigate(-1);
                      } 
                      //
                      return (
                        <div className='list-group'>
                          {
                            news.map((newItem, index) => {
                              return (
                                <div key={newItem.id}>
                                {/*<Link className='list-group-item text-center' key={newItem.id} to='detail'>{newItem.title}</Link>*/}
                                {/*通过params传参*/}
                                {/*<Link className='list-group-item text-center' key={newItem.id} to={`detail/${newItem.id}/${newItem.title}`}>{newItem.title}</Link> */}
                                {/*通过search传参*/}
                                {/*<Link className='list-group-item text-center' key={newItem.id} to={`detail?id=${newItem.id}&title=${newItem.title}`}>{newItem.title}</Link>*/}
                                {/*通过state传参*/}
                                {/*<Link className='list-group-item text-center position-relative' key={newItem.id} to='detail' state={{id:newItem.id, title:newItem.title}}>{newItem.title} </Link>*/}
                                {/*编程式路由导航*/}
                                   <div className='position-relative'>
                                    {/*  正常路由链接(state传参) */}
                                    <Link className='list-group-item text-center' replace={false} to='detail' state={{id:newItem.id, title:newItem.title}}>{newItem.title}</Link>
                                    {/* 编程式路由链接 push 模式 */}
                                    <button onClick={()=>showDetailPush(newItem)} className="btn border position-absolute top-50 start-0 translate-middle-y">Push查看</button>
                                    {/* 编程式路由链接 replace 模式 */}
                                    <button onClick={()=>showDetailReplace(newItem)} className="btn border position-absolute top-50 end-0 translate-middle-y">Replace查看</button>
                                  </div> 
                                </div>
                              )
                            })
                          }
                          {/* 控制页面前进后退的按钮 */}
                          <div className="list-group list-group-horizontal justify-content-center  mt-1">
                            <button  onClick={goForward}  className="list-group-item">前进</button>
                            <button  onClick={goBack}  className="list-group-item">后退</button>
                          </div>
                          <hr />
                          <Suspense  fallback={<h2>加载诗句中...</h2>}>
                            <Outlet />
                          </Suspense>
                        </div>
                      )
                    }


                    ```
            -   示例：在一般组件中使用路由组件的API：在一般组件中直接使用userNavigate既可使用 \[[\[JS库\]react-route-dom](\[JS库]react-route-dom_jGUgd2TkFiY94rBUA6txun.md "\[JS库]react-route-dom"),函数式组件`useNavigate`]
                -   src/pages/Home/News/News.jsx
                    ```react&#x20;jsx
                    import React, {useState, Suspense} from 'react'
                    //
                    import { Link, Outlet, useNavigate } from 'react-router-dom'
                    //
                    export default function News() {
                      // 模拟数据
                      const [news] = useState([
                          {id:"01", title:'闻王昌龄左迁龙标遥有此寄'},
                          {id:"02", title:'望天门山'},
                          {id:"03", title:'早发白帝城'},
                      ])
                      // 编程式路由
                      // # 创建实例?
                      const navigate = useNavigate()
                      // # 通过Push模式来跳转到详细页面
                      function showDetailPush(newItem){
                        console.log(navigate.history);
                        navigate('detail',
                        {
                          replace:false,
                          state:{
                            id:newItem.id,
                            title:newItem.title
                          }
                        },
                        )
                      }
                      // # 通过Replace模式来跳转到详细页面
                      function showDetailReplace(newItem){
                        navigate('detail',
                          {
                            replace:true,
                            state:{
                              id:newItem.id,
                              title:newItem.title
                            }
                          },
                        )
                      }
                      // # 前进
                      function goForward() {
                        navigate(1);
                      }
                      // # 后退
                      function goBack() {
                        navigate(-1);
                      }
                      //
                      return (
                        <div className='list-group'>
                          {
                            news.map((newItem, index) => {
                              return (
                                <div key={newItem.id}>
                                {/*<Link className='list-group-item text-center' key={newItem.id} to='detail'>{newItem.title}</Link>*/}
                                {/*通过params传参*/}
                                {/*<Link className='list-group-item text-center' key={newItem.id} to={`detail/${newItem.id}/${newItem.title}`}>{newItem.title}</Link> */}
                                {/*通过search传参*/}
                                {/*<Link className='list-group-item text-center' key={newItem.id} to={`detail?id=${newItem.id}&title=${newItem.title}`}>{newItem.title}</Link>*/}
                                {/*通过state传参*/}
                                {/*<Link className='list-roup-item text-center position-relative' key={newItem.id} to='detail' state={{id:newItem.id, title:newItem.title}}>{newItem.title} </Link>*/}
                                {/*编程式路由导航*/}
                                  <div className='position-relative'>
                                    {/*  正常路由链接(state传参) */}
                                    <Link className='list-group-item text-center' replace={false} to='detail' state={{id:newItem.id, title:newItem.title}}>{newItem.title}</Link>
                                    {/* 编程式路由链接 push 模式 */}
                                    <button onClick={()=>showDetailPush(newItem)} className="btn border position-absolute top-50 start-0 translate-middle-y">Push查看</button>
                                    {/* 编程式路由链接 replace 模式 */}
                                    <button onClick={()=>showDetailReplace(newItem)} className="btn border position-absolute top-50 end-0 translate-middle-y">Replace查看</button>
                                  </div>
                                </div>
                              )
                            })
                          }
                          {/* 控制页面前进后退的按钮 */}
                          <div className="list-group list-group-horizontal justify-content-center  mt-1">
                            <button onClick={goForward} className="list-group-item">前进</button>
                            <button onClick={goBack} className="list-group-item">后退</button>
                          </div>
                          <hr />
                          <Suspense  fallback={<h2>加载诗句中...</h2>}>
                            <Outlet />
                          </Suspense>
                        </div>
                      )
                    }

                    ```
                -   src/components/Header/Header.jsx&#x20;
                    ```react&#x20;jsx
                    import React from 'react'
                    import { useNavigate } from 'react-router-dom'

                    export default function Header() {
                        // 在一般组件中使用路由组件的API
                        const navigate = useNavigate()
                        // # 前进
                        function goForward() {
                            navigate(1);
                        }
                        // # 后退
                        function goBack() {
                            navigate(-1);
                        }
                        return (
                            <div className='container mt-1'>
                                <div className="row border p-1 bg-info ">
                                    <h2>这里是一般组件</h2>
                                    <span>一般组件中使用路由组件的API</span>
                                    <div className="list-group list-group-horizontal justify-content-center  mt-1">
                                        <button onClick={goForward} className="list-group-item">前进</button>
                                        <button onClick={goBack} className="list-group-item">后退</button>
                                    </div>
                                </div>
                            </div>
                        )
                    }

                    ```
                -   src/App.jsx
                    ```react&#x20;jsx
                    import React, {Suspense } from 'react'
                    //
                    import { NavLink,  useRoutes } from 'react-router-dom'
                    // 导入路由表
                    import routes from './routes/routes'
                    //
                     import Header from './components/Header/Header' 
                    //
                    export default function App() {
                      // 自定义的active样式
                      function customActionBackgroundColor({isActive}){
                        return isActive ? 'list-group-item customActionBackgroundColor' : 'list-group-item'
                      }
                      // 使用路由表
                      const element = useRoutes(routes)
                      //
                      return (
                        <div>
                           <Header /> 
                          <div className="container">
                            <div className="row">
                              <div className="col-12">
                                <h2>react-router-dom@6.11.1</h2>
                              </div>
                              <div className="col-4">
                                <div className="list-group">
                                  <NavLink className={customActionBackgroundColor} to='/home'>Home</NavLink>
                                  <NavLink className={customActionBackgroundColor} to='/about'>About</NavLink>
                                </div>
                              </div>
                              <div className="col-8">
                                {/* 注册路由 以前的component属性换成了element*/}
                                <Suspense fallback={<h2>Loading...</h2>}>    {/* 懒加载与加载文字 */}
                                    {element}
                                </Suspense>
                              </div>
                            </div>
                          </div>
                      </div>
                      )
                    }
                    ```
    -   [x] [137 137\_尚硅谷\_ReactRouter6教程\_useInRouterContext\_Duration-3Min](https://www.bilibili.com/video/BV1wy4y1D7JT/?p=137 "137 137_尚硅谷_ReactRouter6教程_useInRouterContext_Duration-3Min")
        -   \[笔记]`useInRouterContext`[¶](https://www.bilibili.com/video/BV1wy4y1D7JT?t=123.2\&p=137 "¶")[¶](https://www.bilibili.com/video/BV1wy4y1D7JT?t=153.6\&p=137 "¶")
    -   [x] [138 138\_尚硅谷\_ReactRouter6教程\_useNavigationType\_Duration-2Min](https://www.bilibili.com/video/BV1wy4y1D7JT/?p=138 "138 138_尚硅谷_ReactRouter6教程_useNavigationType_Duration-2Min")
        -
            -   示例：`console.log(useNavigationType())` \[`useInRouterContext`]
                -   src/pages/Home/News/News.jsx
                    ```react&#x20;jsx
                    import React, {useState, Suspense} from 'react'
                    //
                    import { Link, Outlet, useNavigate,  useNavigationType  } from 'react-router-dom'
                    //
                    export default function News() {
                       console.log(useNavigationType()) 
                      // 模拟数据
                      const [news] = useState([
                          {id:"01", title:'闻王昌龄左迁龙标遥有此寄'},
                          {id:"02", title:'望天门山'},
                          {id:"03", title:'早发白帝城'},
                      ])
                      // 编程式路由
                      // # 创建实例?
                      const navigate = useNavigate()
                      // # 通过Push模式来跳转到详细页面
                      function showDetailPush(newItem){
                        navigate('detail',
                        {
                          replace:false,
                          state:{
                            id:newItem.id,
                            title:newItem.title
                          }
                        },
                        )
                      }
                      // # 通过Replace模式来跳转到详细页面
                      function showDetailReplace(newItem){
                        navigate('detail',
                          {
                            replace:true,
                            state:{
                              id:newItem.id,
                              title:newItem.title
                            }
                          },
                        )
                      }
                      // # 前进
                      function goForward() {
                        navigate(1);
                      }
                      // # 后退
                      function goBack() {
                        navigate(-1);
                      }
                      //
                      return (
                        <div className='list-group'>
                          {
                            news.map((newItem, index) => {
                              return (
                                <div key={newItem.id}>
                                {/*<Link className='list-group-item text-center' key={newItem.id} to='detail'>{newItem.title}</Link>*/}
                                {/*通过params传参*/}
                                {/*<Link className='list-group-item text-center' key={newItem.id} to={`detail/${newItem.id}/${newItem.title}`}>{newItem.title}</Link> */}
                                {/*通过search传参*/}
                                {/*<Link className='list-group-item text-center' key={newItem.id} to={`detail?id=${newItem.id}&title=${newItem.title}`}>{newItem.title}</Link>*/}
                                {/*通过state传参*/}
                                {/*<Link className='list-roup-item text-center position-relative' key={newItem.id} to='detail' state={{id:newItem.id, title:newItem.title}}>{newItem.title} </Link>*/}
                                {/*编程式路由导航*/}
                                  <div className='position-relative'>
                                    {/*  正常路由链接(state传参) */}
                                    <Link className='list-group-item text-center' replace={false} to='detail' state={{id:newItem.id, title:newItem.title}}>{newItem.title}</Link>
                                    {/* 编程式路由链接 push 模式 */}
                                    <button onClick={()=>showDetailPush(newItem)} className="btn border position-absolute top-50 start-0 translate-middle-y">Push查看</button>
                                    {/* 编程式路由链接 replace 模式 */}
                                    <button onClick={()=>showDetailReplace(newItem)} className="btn border position-absolute top-50 end-0 translate-middle-y">Replace查看</button>
                                  </div>
                                </div>
                              )
                            })
                          }
                          {/* 控制页面前进后退的按钮 */}
                          <div className="list-group list-group-horizontal justify-content-center  mt-1">
                            <button onClick={goForward} className="list-group-item">前进</button>
                            <button onClick={goBack} className="list-group-item">后退</button>
                          </div>
                          <hr />
                          <Suspense  fallback={<h2>加载诗句中...</h2>}>
                            <Outlet />
                          </Suspense>
                        </div>
                      )
                    }
                    ```
    -   [x] [139 139\_尚硅谷\_ReactRouter6教程\_useOutlet\_Duration-1Min](https://www.bilibili.com/video/BV1wy4y1D7JT/?p=139 "139 139_尚硅谷_ReactRouter6教程_useOutlet_Duration-1Min")
        -   \[笔记]`useOutlet`(演示[¶](https://www.bilibili.com/video/BV1wy4y1D7JT?t=60.1\&p=139 "¶"))

            ![](../image/image_UBsF9VLEE7.png)

            ![](../image/image_p7De7aJex-.png)

            ![](../image/image_QPPPnIEhU1.png)
            -   示例：
    -   [x] [140 140\_尚硅谷\_ReactRouter6教程\_useOutletuseResolvedPath\_Duration-1Min](https://www.bilibili.com/video/BV1wy4y1D7JT/?p=140 "140 140_尚硅谷_ReactRouter6教程_useOutletuseResolvedPath_Duration-1Min")
        -   \[笔记]`useResolvedPath`

            ![](../image/image_J1qCBYGU9O.png)

            ![](../image/image_Tg-j0EhxRQ.png)
            -   示例：

    -   [x] [141 141\_尚硅谷\_ReactRouter6教程\_总结\_Duration-6Min](https://www.bilibili.com/video/BV1wy4y1D7JT/?p=141 "141 141_尚硅谷_ReactRouter6教程_总结_Duration-6Min")
    -   \[笔记]
        -   示例：
-   【2022最新】React项目实战(React后台管理系统、TypeScript+React18)(437m)(7h)\[[\[Web\]React](\[Web]React_h3XfA4SNWf9ohgsZECjLr3.md "\[Web]React")] <2023\_05\_10-2023\_05\_10>o

    🔳⬜️⬜️⬜️⬜️⬜️⬜️⬜️⬜️⬜️ 9%
    -   [ ] [1 01-项目课程的介绍\_Duration-5Min](https://www.bilibili.com/video/BV1FV4y157Zx/?p=1 "1 01-项目课程的介绍_Duration-5Min")
        -   \[笔记]
            -   示例
    -   [ ] [2 02-环境准备\_Duration-1Min](https://www.bilibili.com/video/BV1FV4y157Zx/?p=2 "2 02-环境准备_Duration-1Min")
        -   \[笔记]
            -   示例
    -   [ ] [3 03-创建项目并且运行\_Duration-6Min](https://www.bilibili.com/video/BV1FV4y157Zx/?p=3 "3 03-创建项目并且运行_Duration-6Min")
        -   \[笔记]
            -   示例
    -   [ ] [4 04-目录初始化\_Duration-2Min](https://www.bilibili.com/video/BV1FV4y157Zx/?p=4 "4 04-目录初始化_Duration-2Min")
        -   \[笔记]
            -   示例
    -   [ ] [5 05-样式初始化\_Duration-3Min](https://www.bilibili.com/video/BV1FV4y157Zx/?p=5 "5 05-样式初始化_Duration-3Min") \[\[JS库]reset-css]
        -   \[笔记]
            -   示例
    -   [ ] [6 06-scss安装和初步使用\_Duration-8Min](https://www.bilibili.com/video/BV1FV4y157Zx/?p=6 "6 06-scss安装和初步使用_Duration-8Min")
        -   \[笔记]
            -   示例：src/assets/style/global.scss \[`user-select``-webkit-user-drag`]
                ```react&#x20;jsx
                // 全局样式
                $color:rgb(218, 218, 218);
                //
                body{
                    background-color: $color;
                    // 禁用文字选中
                    user-select: none;
                }
                ```
    -   [x] [7 07-路径别名的配置\_Duration-4Min](https://www.bilibili.com/video/BV1FV4y157Zx/?p=7 "7 07-路径别名的配置_Duration-4Min")
        -   \[笔记]
            -   示例
    -   [x] [8 08-配置路径别名的提示\_Duration-2Min](https://www.bilibili.com/video/BV1FV4y157Zx/?p=8 "8 08-配置路径别名的提示_Duration-2Min")
        -   \[笔记]
            -   示例
    -   [x] [9 09-scss文件的全局引入会影响其他组件\_Duration-5Min](https://www.bilibili.com/video/BV1FV4y157Zx/?p=9 "9 09-scss文件的全局引入会影响其他组件_Duration-5Min")
        -   \[笔记]
            -   示例
    -   [x] [10 10-scss的模块化管理样式\_Duration-2Min](https://www.bilibili.com/video/BV1FV4y157Zx/?p=10 "10 10-scss的模块化管理样式_Duration-2Min")
        -   \[笔记]
            -   示例
                -   示例：scss模块化导入：对于同类名的不同模块实现互不影响 \[[SCSS](SCSS_r5zBDEp2iELTgJ9NfwiUSS.md "SCSS")]
                    -   src/components/Header/**Header.module.scss**
                        ```react&#x20;jsx
                        .header{
                            color: red;
                        }
                        ```
                    -   src/components/Header/Header.jsx
                        ```react&#x20;jsx
                        import styles from  './Header.module.scss'
                        //
                        export default function Header() {
                          return (
                            <div className={styles.header}>
                              Header
                            </div>
                          )
                        }

                        ```
    -   [x] [11 11-Antd的初步使用 (2)\_Duration-10Min](https://www.bilibili.com/video/BV1FV4y157Zx/?p=11 "11 11-Antd的初步使用 (2)_Duration-10Min")
        -   \[笔记]
            -   示例
    -   [x] [12 12-配置Antd样式的自动按需引入\_Duration-6Min](https://www.bilibili.com/video/BV1FV4y157Zx/?p=12 "12 12-配置Antd样式的自动按需引入_Duration-6Min")
        -   \[笔记]
            -   示例
    -   [ ] [13 13-路由第1种方式-路由基本配置\_Duration-13Min](https://www.bilibili.com/video/BV1FV4y157Zx/?p=13 "13 13-路由第1种方式-路由基本配置_Duration-13Min")
        -   \[笔记]
            -   示例
    -   [ ] [14 14-路由第1种方式-实现路由跳转\_Duration-3Min](https://www.bilibili.com/video/BV1FV4y157Zx/?p=14 "14 14-路由第1种方式-实现路由跳转_Duration-3Min")
        -   \[笔记]
            -   示例
    -   [ ] [15 15-路由第1种方式-路由重定向\_Duration-2Min](https://www.bilibili.com/video/BV1FV4y157Zx/?p=15 "15 15-路由第1种方式-路由重定向_Duration-2Min")
        -   \[笔记]
            -   示例
    -   [ ] [16 16-路由第2种方式-路由表写法\_Duration-9Min](https://www.bilibili.com/video/BV1FV4y157Zx/?p=16 "16 16-路由第2种方式-路由表写法_Duration-9Min")
        -   \[笔记]
            -   示例
    -   [ ] [17 17-路由第2种方式-路由懒加载\_Duration-4Min](https://www.bilibili.com/video/BV1FV4y157Zx/?p=17 "17 17-路由第2种方式-路由懒加载_Duration-4Min")
        -   \[笔记]
            -   示例
    -   [ ] [18 18-路由第2种方式-路由懒加载的正确写法\_Duration-4Min](https://www.bilibili.com/video/BV1FV4y157Zx/?p=18 "18 18-路由第2种方式-路由懒加载的正确写法_Duration-4Min")
        -   \[笔记]
            -   示例
    -   [ ] [19 19-路由第2种方式-抽取Loading组件函数\_Duration-3Min](https://www.bilibili.com/video/BV1FV4y157Zx/?p=19 "19 19-路由第2种方式-抽取Loading组件函数_Duration-3Min")
        -   \[笔记]
            -   示例
    -   [ ] [20 20-首页布局的解决方案(含侧边栏)\_Duration-7Min](https://www.bilibili.com/video/BV1FV4y157Zx/?p=20 "20 20-首页布局的解决方案(含侧边栏)_Duration-7Min")
        -   \[笔记]
            -   示例
    -   [ ] [21 21-页面右侧结构样式的调整\_Duration-10Min](https://www.bilibili.com/video/BV1FV4y157Zx/?p=21 "21 21-页面右侧结构样式的调整_Duration-10Min")
        -   \[笔记]
            -   示例
    -   [ ] [22 22-点击跳转-点击侧边栏获取到路径\_Duration-4Min](https://www.bilibili.com/video/BV1FV4y157Zx/?p=22 "22 22-点击跳转-点击侧边栏获取到路径_Duration-4Min")
        -   \[笔记]
            -   示例
    -   [ ] [23 23-点击跳转-跳转的实现\_Duration-2Min](https://www.bilibili.com/video/BV1FV4y157Zx/?p=23 "23 23-点击跳转-跳转的实现_Duration-2Min")
        -   \[笔记]
            -   示例
    -   [ ] [24 24-点击跳转-嵌套路由写法(路由跳转和组件内容切换)\_Duration-7Min](https://www.bilibili.com/video/BV1FV4y157Zx/?p=24 "24 24-点击跳转-嵌套路由写法(路由跳转和组件内容切换)_Duration-7Min")
        -   \[笔记]
            -   示例
    -   [ ] [25 25-远程仓库关联\_Duration-3Min](https://www.bilibili.com/video/BV1FV4y157Zx/?p=25 "25 25-远程仓库关联_Duration-3Min")
        -   \[笔记]
            -   示例
    -   [ ] [26 26-菜单栏-展开和回收事件的讲解\_Duration-10Min](https://www.bilibili.com/video/BV1FV4y157Zx/?p=26 "26 26-菜单栏-展开和回收事件的讲解_Duration-10Min")
        -   \[笔记]
            -   示例
    -   [ ] [27 27-菜单栏-设置只能有一个展开项\_Duration-7Min](https://www.bilibili.com/video/BV1FV4y157Zx/?p=27 "27 27-菜单栏-设置只能有一个展开项_Duration-7Min")
        -   \[笔记]
            -   示例
    -   [ ] [28 28-菜单栏-菜单组件抽取\_Duration-6Min](https://www.bilibili.com/video/BV1FV4y157Zx/?p=28 "28 28-菜单栏-菜单组件抽取_Duration-6Min")
        -   \[笔记]
            -   示例
    -   [ ] [29 29-菜单栏-菜单数据的整理\_Duration-8Min](https://www.bilibili.com/video/BV1FV4y157Zx/?p=29 "29 29-菜单栏-菜单数据的整理_Duration-8Min")
        -   \[笔记]
            -   示例
    -   [ ] [30 30-菜单栏-其余路径的配置\_Duration-4Min](https://www.bilibili.com/video/BV1FV4y157Zx/?p=30 "30 30-菜单栏-其余路径的配置_Duration-4Min")
        -   \[笔记]
            -   示例
    -   [ ] [31 31-菜单栏-刷新时默认当前选中项样式的处理\_Duration-7Min](https://www.bilibili.com/video/BV1FV4y157Zx/?p=31 "31 31-菜单栏-刷新时默认当前选中项样式的处理_Duration-7Min")
        -   \[笔记]
            -   示例
    -   [ ] [32 32-菜单栏-配置初始展开项的思路分析\_Duration-6Min](https://www.bilibili.com/video/BV1FV4y157Zx/?p=32 "32 32-菜单栏-配置初始展开项的思路分析_Duration-6Min")
        -   \[笔记]
            -   示例
    -   [ ] [33 33-菜单栏-配置初始展开项的代码实现\_Duration-13Min](https://www.bilibili.com/video/BV1FV4y157Zx/?p=33 "33 33-菜单栏-配置初始展开项的代码实现_Duration-13Min")
        -   \[笔记]
            -   示例
    -   [ ] [34 34-菜单栏-类型约束补充01\_Duration-2Min](https://www.bilibili.com/video/BV1FV4y157Zx/?p=34 "34 34-菜单栏-类型约束补充01_Duration-2Min")
        -   \[笔记]
            -   示例
    -   [ ] [35 35-菜单栏-类型约束补充02\_Duration-1Min](https://www.bilibili.com/video/BV1FV4y157Zx/?p=35 "35 35-菜单栏-类型约束补充02_Duration-1Min")
        -   \[笔记]
            -   示例
    -   [ ] [36 36-登录页面-登录组件的创建和背景设置\_Duration-12Min](https://www.bilibili.com/video/BV1FV4y157Zx/?p=36 "36 36-登录页面-登录组件的创建和背景设置_Duration-12Min")
        -   \[笔记]
            -   示例
    -   [ ] [37 37-登录页面-登录表单组件的构建\_Duration-16Min](https://www.bilibili.com/video/BV1FV4y157Zx/?p=37 "37 37-登录页面-登录表单组件的构建_Duration-16Min")
        -   \[笔记]
            -   示例
    -   [ ] [38 38-登录页面-验证码模块布局\_Duration-8Min](https://www.bilibili.com/video/BV1FV4y157Zx/?p=38 "38 38-登录页面-验证码模块布局_Duration-8Min")
        -   \[笔记]
            -   示例
    -   [ ] [39 39-登录页面-placeholder字体颜色的控制\_Duration-3Min](https://www.bilibili.com/video/BV1FV4y157Zx/?p=39 "39 39-登录页面-placeholder字体颜色的控制_Duration-3Min")
        -   \[笔记]
            -   示例
    -   [ ] [40 40-登录页面-用户输入的用户名的获取\_Duration-8Min](https://www.bilibili.com/video/BV1FV4y157Zx/?p=40 "40 40-登录页面-用户输入的用户名的获取_Duration-8Min")
        -   \[笔记]
            -   示例
    -   [ ] [41 41-登录页面-点击获取用户输入的密码和验证码\_Duration-4Min](https://www.bilibili.com/video/BV1FV4y157Zx/?p=41 "41 41-登录页面-点击获取用户输入的密码和验证码_Duration-4Min")
        -   \[笔记]
            -   示例
    -   [ ] [42 42-redux-dev-tools的安装\_Duration-1Min](https://www.bilibili.com/video/BV1FV4y157Zx/?p=42 "42 42-redux-dev-tools的安装_Duration-1Min")
        -   \[笔记]
            -   示例
    -   [ ] [43 43-react-redux-创建仓库并和项目关联上\_Duration-8Min](https://www.bilibili.com/video/BV1FV4y157Zx/?p=43 "43 43-react-redux-创建仓库并和项目关联上_Duration-8Min")
        -   \[笔记]
            -   示例
    -   [ ] [44 44-react-redux-在组件中获取仓库数据\_Duration-4Min](https://www.bilibili.com/video/BV1FV4y157Zx/?p=44 "44 44-react-redux-在组件中获取仓库数据_Duration-4Min")
        -   \[笔记]
            -   示例
    -   [ ] [45 45-react-redux-在组件中修改仓库数据\_Duration-9Min](https://www.bilibili.com/video/BV1FV4y157Zx/?p=45 "45 45-react-redux-在组件中修改仓库数据_Duration-9Min")
        -   \[笔记]
            -   示例
    -   [ ] [46 46-react-redux-两个TS警告的解决方案\_Duration-8Min](https://www.bilibili.com/video/BV1FV4y157Zx/?p=46 "46 46-react-redux-两个TS警告的解决方案_Duration-8Min")
        -   \[笔记]
            -   示例
    -   [ ] [47 47-react-redux-数据和方法从reducer中进行抽离\_Duration-10Min](https://www.bilibili.com/video/BV1FV4y157Zx/?p=47 "47 47-react-redux-数据和方法从reducer中进行抽离_Duration-10Min")
        -   \[笔记]
            -   示例
    -   [ ] [48 48-react-redux-方法名统一管理\_Duration-2Min](https://www.bilibili.com/video/BV1FV4y157Zx/?p=48 "48 48-react-redux-方法名统一管理_Duration-2Min")
        -   \[笔记]
            -   示例
    -   [ ] [49 49-react-redux-为什么还要模块化reducer\_Duration-6Min](https://www.bilibili.com/video/BV1FV4y157Zx/?p=49 "49 49-react-redux-为什么还要模块化reducer_Duration-6Min")
        -   \[笔记]
            -   示例
    -   [ ] [50 50-react-redux-模块化reducer并组合起来\_Duration-10Min](https://www.bilibili.com/video/BV1FV4y157Zx/?p=50 "50 50-react-redux-模块化reducer并组合起来_Duration-10Min")
        -   \[笔记]
            -   示例
    -   [ ] [51 51-react-redux-【亮点】switch...case语句自动生成\_Duration-14Min](https://www.bilibili.com/video/BV1FV4y157Zx/?p=51 "51 51-react-redux-【亮点】switch...case语句自动生成_Duration-14Min")
        -   \[笔记]
            -   示例
    -   [ ] [52 52-react-redux-【亮点】方法名对象actionNames的自动生成\_Duration-8Min](https://www.bilibili.com/video/BV1FV4y157Zx/?p=52 "52 52-react-redux-【亮点】方法名对象actionNames的自动生成_Duration-8Min")
        -   \[笔记]
            -   示例
    -   [ ] [53 53-react-redux-【亮点】完善各个模块的reducer\_Duration-6Min](https://www.bilibili.com/video/BV1FV4y157Zx/?p=53 "53 53-react-redux-【亮点】完善各个模块的reducer_Duration-6Min")
        -   \[笔记]
            -   示例
    -   [ ] [54 54-redux-thunk-仓库文件store的改造(为了异步)\_Duration-9Min](https://www.bilibili.com/video/BV1FV4y157Zx/?p=54 "54 54-redux-thunk-仓库文件store的改造(为了异步)_Duration-9Min")
        -   \[笔记]
            -   示例
    -   [ ] [55 55-redux-thunk-基本使用\_Duration-4Min](https://www.bilibili.com/video/BV1FV4y157Zx/?p=55 "55 55-redux-thunk-基本使用_Duration-4Min")
        -   \[笔记]
            -   示例
    -   [ ] [56 56-redux-thunk-异步函数从组件抽离到状态仓库中(模仿Vuex)\_Duration-8Min](https://www.bilibili.com/video/BV1FV4y157Zx/?p=56 "56 56-redux-thunk-异步函数从组件抽离到状态仓库中(模仿Vuex)_Duration-8Min")
        -   \[笔记]
            -   示例
    -   [ ] [57 57-react-redux-总结及使用\_Duration-3Min](https://www.bilibili.com/video/BV1FV4y157Zx/?p=57 "57 57-react-redux-总结及使用_Duration-3Min")
        -   \[笔记]
            -   示例
    -   [ ] [58 58-数据交互-获取验证码请求\_Duration-10Min](https://www.bilibili.com/video/BV1FV4y157Zx/?p=58 "58 58-数据交互-获取验证码请求_Duration-10Min")
        -   \[笔记]
            -   示例
    -   [ ] [59 59-数据交互-修改成async+await写法\_Duration-6Min](https://www.bilibili.com/video/BV1FV4y157Zx/?p=59 "59 59-数据交互-修改成async+await写法_Duration-6Min")
        -   \[笔记]
            -   示例
    -   [ ] [60 60-数据交互-规范化请求中的TypeScript的书写\_Duration-3Min](https://www.bilibili.com/video/BV1FV4y157Zx/?p=60 "60 60-数据交互-规范化请求中的TypeScript的书写_Duration-3Min")
        -   \[笔记]
            -   示例
    -   [ ] [61 61-数据交互-完成验证码的业务逻辑\_Duration-6Min](https://www.bilibili.com/video/BV1FV4y157Zx/?p=61 "61 61-数据交互-完成验证码的业务逻辑_Duration-6Min")
        -   \[笔记]
            -   示例
    -   [ ] [62 62-数据交互-登录API和类型约束的书写\_Duration-3Min](https://www.bilibili.com/video/BV1FV4y157Zx/?p=62 "62 62-数据交互-登录API和类型约束的书写_Duration-3Min")
        -   \[笔记]
            -   示例
    -   [ ] [63 63-数据交互-登录的业务逻辑的处理\_Duration-13Min](https://www.bilibili.com/video/BV1FV4y157Zx/?p=63 "63 63-数据交互-登录的业务逻辑的处理_Duration-13Min")
        -   \[笔记]
            -   示例
    -   [ ] [64 64-手写封装前置路由守卫-思路分析和结构的初步实现\_Duration-8Min](https://www.bilibili.com/video/BV1FV4y157Zx/?p=64 "64 64-手写封装前置路由守卫-思路分析和结构的初步实现_Duration-8Min")
        -   \[笔记]
            -   示例
    -   [ ] [65 65-手写封装前置路由守卫-业务实现\_Duration-7Min](https://www.bilibili.com/video/BV1FV4y157Zx/?p=65 "65 65-手写封装前置路由守卫-业务实现_Duration-7Min")
        -   \[笔记]
            -   示例
-   2023年最新珠峰React全家桶【react基础-进阶-项目-源码-淘系-面试题】(8791m)(146h)\[[\[Web\]React](\[Web]React_h3XfA4SNWf9ohgsZECjLr3.md "\[Web]React")] <2023\_05\_11->

    🔳⬜️⬜️⬜️⬜️⬜️⬜️⬜️⬜️⬜️ 13%
    -   [x] [1 01.课程介绍\_Duration-12Min](https://www.bilibili.com/video/BV1sx4y1L7Rg/?p=1 "1 01.课程介绍_Duration-12Min")
        -   \[笔记]
            -   示例[https://www.bilibili.com/video/BV1sx4y1L7Rg?t=2593.3\&p=2](https://www.bilibili.com/video/BV1sx4y1L7Rg?t=2593.3\&p=2 "https://www.bilibili.com/video/BV1sx4y1L7Rg?t=2593.3\&p=2")
    -   [x] [2 02.create-react-app基础操作\_Duration-58Min](https://www.bilibili.com/video/BV1sx4y1L7Rg/?p=2 "2 02.create-react-app基础操作_Duration-58Min")
        -   \[笔记]scripts,eslintConfig,browserslist[¶](https://www.bilibili.com/video/BV1sx4y1L7Rg?t=2593.3\&p=2 "¶")

            ![](../image/image_ZU4iDwx-dH.png)

            ![](../image/image_6gicbe_YsI.png)

            ![](../image/image_CrOumv7_8T.png)
            -   示例
    -   [x] [3 03.脚手架的进阶应用\_Duration-64Min](https://www.bilibili.com/video/BV1sx4y1L7Rg/?p=3 "3 03.脚手架的进阶应用_Duration-64Min")
        -   \[笔记]#3暴露webpack之后的文件 \[`npm run eject`],SE6内置API兼容处理  \[,`./config/`[🖼️ 图片](../image/image_QgNTJ_o7L3.png "🖼️ 图片")`./scripts/`[🖼️ 图片](../image/image_mR-J4Ncmtp.png "🖼️ 图片")[🖼️ 图片](../image/image_JSZa-tI0Dz.png "🖼️ 图片"), 暴露webpack的[./package.json](--package.json_5XzrB1BD9kJ9xyQ72pXvy9.md "./package.json")[¶](https://www.bilibili.com/video/BV1sx4y1L7Rg?t=705.4\&p=3 "¶"),eject,\[JS库]react-app-polyfill[¶](https://www.bilibili.com/video/BV1sx4y1L7Rg?t=3090.0\&p=3 "¶")]
            -   图

                ![](../image/image_bs4lpehhcz.png)

                ![](../image/image_PMP_ZSoxFV.png)

                ![](../image/image_QagRbkuMqx.png)

                ![](../image/image_Rq9DV0MsTu.png)

                ![](../image/image_Glc3waQvNg.png)
            -   处理跨域[¶](https://www.bilibili.com/video/BV1sx4y1L7Rg?t=3207.0\&p=3 "¶")
    -   [x] [4 04.MVC模式和MVVM模式\_Duration-41Min](https://www.bilibili.com/video/BV1sx4y1L7Rg/?p=4 "4 04.MVC模式和MVVM模式_Duration-41Min")
        -   \[笔记] #4 [MVVM](MVVM_qUkvMWRoX5WbrFezDf1Nmi.md "MVVM")[MVC](MVC_6Grg764tEBKQ4c24UR9uM6.md "MVC")

            React框架采用的是[MVC](MVC_6Grg764tEBKQ4c24UR9uM6.md "MVC")体系；Vue框架采用的是[MVVM](MVVM_qUkvMWRoX5WbrFezDf1Nmi.md "MVVM")体系； MVC: model数据层 ，view视图层 controller控制层;  MVVM: model数据层 view视图层 viewModel数据/视图监听层。[🖼️ 图片](../image/image_a3AA0RYmOV.png "🖼️ 图片")

            ![](../image/image_zJdQnyDP5g.png)

            ![](../image/image_wu_C1O7CbU.png)
            -   示例
    -   [x] [5 05.JSX语法使用上的细节\_Duration-38Min](https://www.bilibili.com/video/BV1sx4y1L7Rg/?p=5 "5 05.JSX语法使用上的细节_Duration-38Min")
        -   \[笔记]#5 JSX中可写的语法与花括号可以写的表达式 \[`{}`]

            ![](../image/image_nSgjeNXPTq.png)

            ![](../image/image_DF2GWpHde3.png)
            -   示例
    -   [x] [6 06.JSX的具体应用\_Duration-55Min](https://www.bilibili.com/video/BV1sx4y1L7Rg/?p=6 "6 06.JSX的具体应用_Duration-55Min")
        -   \[笔记]#6 JSX中花括号，中可以嵌入的值。行内样式的书写，使用两层花括号(对象) \[`{}``{{}}`]



            ![](../image/image_Mot3-4YxaU.png)

            ![](../image/image_2RjcBb3zP0.png)

            \[笔记]项目中的命名方式

            ![](../image/image_vcUvgxVPnu.png)
            -   示例：基于值来控制元素的显示隐藏 \[\[JS]三元运算符]

                ![](../image/image_ZN8ipHdWf8.png)
            -   示例：JSX中的循环[¶](https://www.bilibili.com/video/BV1sx4y1L7Rg?t=1993.2\&p=6 "¶") \[`Array.map()`]

                ![](../image/image_mGDF4CTesv.png)
            -   示例：new Array中传值不同的情况 \[`new`Array,稀疏数组密集数组`Array.fill()`]

                ![](../image/image_ZvjLd9IILo.png)
                -   示例：稀疏数组不可迭代，密集数组可以迭代 \[`Array.fill()`返回填充的数组]

                    ![](../image/image_SZUawY49K6.png)

                    ![](../image/image_O2Q3I4sNJO.png)
    -   [ ] [7 07.JSX底层渲染机制「创建virtualDOM」\_Duration-79Min](https://www.bilibili.com/video/BV1sx4y1L7Rg/?p=7 "7 07.JSX底层渲染机制「创建virtualDOM」_Duration-79Min")
        -   \[笔记]#7[\[React\]JSX](\[React]JSX_s6YqU4tzdiXR9faUSdiKqB.md "\[React]JSX")渲染的底层机制 [¶](https://www.bilibili.com/video/BV1sx4y1L7Rg?t=2232.2\&p=7 "¶") [\[React\]虚拟DOM](\[React]虚拟DOM_Snd6fanVfJeXQdXpbDqd8.md "\[React]虚拟DOM")[¶](https://www.bilibili.com/video/BV1sx4y1L7Rg?t=2641.0\&p=7 "¶") \[`Fragment`,`React.createElement()`]

            ![](../image/image_gVJP3xjKDI.png)

            ![](../image/image_thLqARrtMQ.png)
            -   示例
    -   [ ] [8 08.JSX底层渲染机制「创建真实DOM」\_Duration-68Min](https://www.bilibili.com/video/BV1sx4y1L7Rg/?p=8 "8 08.JSX底层渲染机制「创建真实DOM」_Duration-68Min")
        -   \[笔记]#8封装一个对象的迭代方法：获取 所有私有属性 \[Symbol,私有属性,Object`Object.getOwnPropertyNames()`Reflect.ownKeys()]

            ![](../image/image_f2eYCDq7mU.png)
            -   示例8.1：封装一个可以遍历对象私有属性的函数[¶](https://www.bilibili.com/video/BV1sx4y1L7Rg?t=1621.7\&p=8 "¶")[¶](https://www.bilibili.com/video/BV1sx4y1L7Rg?t=1730.4\&p=8 "¶") \[`function(){}`回调函数,箭头函数]



                ![](../image/image_If-zMDvr64.png)

                ![](../image/image_VkCGqjGGOZ.png)


            -   示例8.2：简单时间render把虚拟DOM变成正式DOM[¶](https://www.bilibili.com/video/BV1sx4y1L7Rg?t=3355.5\&p=8 "¶") \[`render()`]

                ![](../image/image_wgEhkp6-Ob.png)

                ![](../image/image_cgFTYbK11f.png)

                ![](../image/image_De8EmQXg01.png)
            [https://www.bilibili.com/video/BV1sx4y1L7Rg?t=1767.4\&p=8](https://www.bilibili.com/video/BV1sx4y1L7Rg?t=1767.4\&p=8 "https://www.bilibili.com/video/BV1sx4y1L7Rg?t=1767.4\&p=8")
    -   [x] [9 09.函数组件的底层渲染机制\_Duration-37Min](https://www.bilibili.com/video/BV1sx4y1L7Rg/?p=9 "9 09.函数组件的底层渲染机制_Duration-37Min")
        -   \[笔记]#9[函数组件的底层渲染机制](https://www.bilibili.com/video/BV1sx4y1L7Rg/?p=9 "函数组件的底层渲染机制") \[props[¶](https://www.bilibili.com/video/BV1sx4y1L7Rg?t=1620.8\&p=9 "¶"),组件化开发,Hooks组件[¶](https://www.bilibili.com/video/BV1sx4y1L7Rg?t=137.3\&p=9 "¶"),函数式组件,`React.createElement()`[\[React\]虚拟DOM](\[React]虚拟DOM_Snd6fanVfJeXQdXpbDqd8.md "\[React]虚拟DOM")]

            ![](../image/image_uPPZA7MJak.png)

            ![](../image/image_AI9hxo46VF.png)
            -   示例：#9函数式组件传递props解析 \[props]

                ![](../image/image_Vguefu7yVg.png)

                ![](../image/image_HBI-kYN6_d.png)
    -   [x] [10 10.关于props属性的细节知识\_Duration-54Min](https://www.bilibili.com/video/BV1sx4y1L7Rg/?p=10 "10 10.关于props属性的细节知识_Duration-54Min")
        -   \[笔记]#10 [props属性的细节知识](https://www.bilibili.com/video/BV1sx4y1L7Rg/?p=10 "props属性的细节知识")：props,属性|参数只读，原因被冻结了

            ![](../image/image_5yasFxGFcg.png)
            -   \[子笔记]：Object的规则设置[¶](https://www.bilibili.com/video/BV1sx4y1L7Rg?t=253.6\&p=10 "¶")&#x20;

                ![](../image/image_hBo05iuFa-.png)
                -   示例：Object的规则设置冻结[¶](https://www.bilibili.com/video/BV1sx4y1L7Rg?t=253.6\&p=10 "¶")，冻结的对象不可修改，不可增加，不能删除，不能劫持\[`Object.freeze()``Object.isFrozen()`]

                    ![](../image/image_sf8XdecUFX.png)
                -   示例：Object的规则设置密封[¶](https://www.bilibili.com/video/BV1sx4y1L7Rg?t=628.8\&p=10 "¶")，密封的对象可以修改，不可增加，不能删除，不能劫持 \[`Object.seal()``Object.isSealed()`]

                    ![](../image/image_JaShdZfYLt.png)
                -   示例：Object的规则设置不可扩展[¶](https://www.bilibili.com/video/BV1sx4y1L7Rg?t=854.0\&p=10 "¶")，扩展的对象可以修改，不可增加，可以删除，可以劫持 \[`Object.preventExtensions()``Object.isExtensible()`]

                    ![](../image/image_Wh1pwAxTQj.png)
            -   \[示例]#10 父传子，设置props的默认值，限制porps \[props,父组件 →传递参数 →子组件 ,[\[JS库\]prop-type](\[JS库]prop-type_ji55v62TxKVe1hhx4LE1Tp.md "\[JS库]prop-type")`PropType.number``.isRequired`) 函数式组件
                -   v1 父传子

                    ![](../image/image_pslSASudC8.png)

                    ![](../image/image_aDUBf1GPub.png)

                    ![](../image/image_qkvlQGG-k6.png)
                -   v2 设置props的默认值

                    ![](../image/image_bwdOXq1GTK.png)
                    -   src/components/Demo/DdefaultProps/DdefaultProps.jsx
                        ```react&#x20;jsx
                        import React from 'react'

                        export default function DdefaultProps(props) {
                            console.log(props)
                            return (
                                <div>
                                父组件传递给子组件(DdefaultProps组件)过来的Props：{props.value}
                                </div>
                            )
                        }
                        // 设置props的默认值，为传值的情况下使用默认值
                         DdefaultProps.defaultProps = {
                            value: 0
                        }
                        ```
                    -   src/App.js
                        ```react&#x20;jsx
                        import React from 'react'
                        //
                        import DdefaultProps from './components/Demo/DdefaultProps/DdefaultProps';
                        //
                        export default function App() {
                          //
                          return (
                            <div>
                               <DdefaultProps value='120'/>
                              <DdefaultProps/> 
                            </div>
                          )
                        }
                        ```
                -   v3 限制 props [¶](https://www.bilibili.com/video/BV1sx4y1L7Rg?t=2252.1\&p=10 "¶")
                    -   src/components/Demo/DdefaultProps/DdefaultProps.jsx
                        ```react&#x20;jsx
                        import React from 'react'
                         import PropType from 'prop-types' 
                        export default function DdefaultProps(props) {
                            console.log(typeof(props.value))

                            return (
                                <div>
                                父组件传递给子组件(DdefaultProps组件)过来的Props：{props.value}
                                </div>
                            )
                        }
                        // 设置props的默认值，为传值的情况下使用默认值
                        DdefaultProps.defaultProps = {
                            value: '0'  // 不传值value默认为 0
                        }
                        // 限制props
                        DdefaultProps.propTypes = {
                             value: PropType.string.isRequired    // 只能为数字类型，且必传
                        }
                        ```
                    -   src/App.js
                        ```react&#x20;jsx
                        import React from 'react'
                        //
                        import DdefaultProps from './components/Demo/DdefaultProps/DdefaultProps';
                        //
                        export default function App() {
                          //
                          return (
                            <div>
                              <DdefaultProps value='120'/>
                              <DdefaultProps/>
                            </div>
                          )
                        }


                        ```
    -   [x] [11 11.React中的插槽处理机制\_Duration-52Min](https://www.bilibili.com/video/BV1sx4y1L7Rg/?p=11 "11 11.React中的插槽处理机制_Duration-52Min")
        -   \[笔记]#11 (F)[\[React\]插槽机制](\[React]插槽机制_uuaHRdrQYxNTMe2KLps9ws.md "\[React]插槽机制")[¶](https://www.bilibili.com/video/BV1sx4y1L7Rg?t=451.7\&p=11 "¶"),`children`,匿名插槽具名插槽

            ![](../image/image_nnTEmuozlb.png)
            -   \[示例]#11 传递children \[React.Children[¶](https://www.bilibili.com/video/BV1sx4y1L7Rg?t=1704.1\&p=11 "¶")React.Children.toArray()[¶](https://www.bilibili.com/video/BV1sx4y1L7Rg?t=1897.0\&p=11 "¶"),匿名插槽具名插槽[¶](https://www.bilibili.com/video/BV1sx4y1L7Rg?t=3033.9\&p=11 "¶")]
                -   v3：使用具名插槽：比如在设置页眉页脚时，v2中父组件的标签体内容顺序不对时，子组件渲染也将是错误的顺序[¶](https://www.bilibili.com/video/BV1sx4y1L7Rg?t=2132.8\&p=11 "¶")

                    ![](../image/image_IXOQZlCcSW.png)

                    ![](../image/image_7_OjcURO0a.png)

                    ![](../image/image_NhCpVPETor.png)
                -   v2 ：使用匿名插槽：在传入不同数量的children时，根据传入的数量来设置渲染的位置[¶](https://www.bilibili.com/video/BV1sx4y1L7Rg?t=1385.3\&p=11 "¶")[¶](https://www.bilibili.com/video/BV1sx4y1L7Rg?t=1513.4\&p=11 "¶")(比如页眉页脚)
                    -   通过React.Children中的方法

                        ![](../image/image_aihplJo2Ui.png)

                        ![](../image/image_0NxFQqQS3x.png)
                    -   自己写判断

                        ![](../image/image_0u9n_hxqVf.png)
                    ![](../image/image_BgjqprdVFC.png)
                -   v1

                    ![](../image/image_1OTUDblxG1.png)
    -   [x] [12 12.初步尝试组件封装\_Duration-21Min](https://www.bilibili.com/video/BV1sx4y1L7Rg/?p=12 "12 12.初步尝试组件封装_Duration-21Min")
        -   \[笔记]
            -   \[示例]#12 封装一个组件，简单 \[[\[React\]插槽机制](\[React]插槽机制_uuaHRdrQYxNTMe2KLps9ws.md "\[React]插槽机制")]

                ![](../image/image_o_GpPMtcfA.png)
                -   src/components/Demo/Dsolt/index.jsx
                    ```react&#x20;jsx
                    import React from 'react'
                    //
                    import PropType from 'prop-types'
                    //
                    import Accordion from 'react-bootstrap/Accordion';
                    import 'bootstrap/dist/css/bootstrap.min.css';

                    //
                    export default function Dsolt(props) {
                         const { title, content, other, children } = props 
                        console.log(title, content, other, children)
                      return (
                        <Accordion defaultActiveKey="0">
                          <Accordion.Item eventKey="0">
                            <Accordion.Header> {title} </Accordion.Header>
                            <Accordion.Body>
                                 {content},
                                {other}
                                {   // 判断是否有子组件，有则展示
                                    children===undefined ? null : <div>{children}</div>
                                } 
                            </Accordion.Body>
                          </Accordion.Item>
                        </Accordion>
                      )
                    }

                    Dsolt.propTypes  = {
                        title: PropType.string.isRequired,
                        content:PropType.string,
                        other: PropType.string
                    }
                    ```
                -   src/App.js
                    ```react&#x20;jsx
                    import React from 'react'
                    //
                    // import DdefaultProps from './components/Demo/DdefaultProps/DdefaultProps';
                    import Dsolt from './components/Demo/Dsolt';
                    //
                    export default function App() {
                      //
                      return (
                        <div>
                           <Dsolt title='标题1' content='标题1的内容' other='不重要提示'/>
                          <Dsolt title='标题2' content='标题2的内容'/>
                          <Dsolt title='带有children的组件' content='标题3的内容'>
                              <button type="button" name="" id="" className="btn btn-primary">Button</button>
                              <button type="button" name="" id="" className="btn btn-primary">Button</button>
                          </Dsolt>
                          <Dsolt title='带有children的组件' content='标题3的内容'>
                              <button type="button" name="" id="" className="btn btn-primary">Button</button>
                          </Dsolt> 
                        </div>
                      )
                    }
                    ```
    -   [ ] [13 13.静态组件和动态组件\_Duration-41Min](https://www.bilibili.com/video/BV1sx4y1L7Rg/?p=13 "13 13.静态组件和动态组件_Duration-41Min")
        -   \[笔记]#13 静态组件动态组件

            ![](../image/image_mt1M8dzvn6.png)

            [https://www.bilibili.com/video/BV1sx4y1L7Rg?t=1318.2\&p=13](https://www.bilibili.com/video/BV1sx4y1L7Rg?t=1318.2\&p=13 "https://www.bilibili.com/video/BV1sx4y1L7Rg?t=1318.2\&p=13")
            -   示例
    -   [ ] [14 14.ES6中class语法和继承的原理\_Duration-34Min](https://www.bilibili.com/video/BV1sx4y1L7Rg/?p=14 "14 14.ES6中class语法和继承的原理_Duration-34Min")
        -   \[笔记]#14 [ES6中class语法和继承的原理](https://www.bilibili.com/video/BV1sx4y1L7Rg/?p=14 "ES6中class语法和继承的原理") \[类式组件,REVIEW:[ES6](ES6_rB5cSLXpPJWFQdqG5dhpnf.md "ES6")[\[JS\]Class](\[JS]Class_fJ1Vahi4EuQg9jYsxwvjmQ.md "\[JS]Class")`static`]
            -   示例
    -   [ ] [15 15.类组件第一次渲染的底层逻辑\_Duration-76Min](https://www.bilibili.com/video/BV1sx4y1L7Rg/?p=15 "15 15.类组件第一次渲染的底层逻辑_Duration-76Min")
        -   \[笔记]
            -   示例
    -   [ ] [16 16.类组件更新的底层逻辑\_Duration-66Min](https://www.bilibili.com/video/BV1sx4y1L7Rg/?p=16 "16 16.类组件更新的底层逻辑_Duration-66Min")
        -   \[笔记]
            -   示例
    -   [x] [17 17.PureComponent和Component的区别「含底层处理机制」\_Duration-60Min](https://www.bilibili.com/video/BV1sx4y1L7Rg/?p=17 "17 17.PureComponent和Component的区别「含底层处理机制」_Duration-60Min")
        -   \[笔记]#17 [PureComponent和Component的区别「含底层处理机制」](https://www.bilibili.com/video/BV1sx4y1L7Rg/?p=17 "PureComponent和Component的区别「含底层处理机制」") \[`Component`,`PureComponent`[¶](https://www.bilibili.com/video/BV1sx4y1L7Rg?t=718.7\&p=17 "¶"),浅比较深比较[¶](https://www.bilibili.com/video/BV1sx4y1L7Rg?t=2786.9\&p=17 "¶"),`Object.is()`[¶](https://www.bilibili.com/video/BV1sx4y1L7Rg?t=2544.1\&p=17 "¶")]

            ![](../image/image_OBV6aHf91E.png)

            ![](../image/image_WMBsQi8eOj.png)

            ![实现浅比较](../image/image_1qqdOJUooL.png "实现浅比较")

            ![](../image/image_-s-JiG-pSV.png)
            -   \[示例]#17 实现浅比较：比较两个对象是否一致 \[Object`Object.is()`,浅比较] >[🖼️ 图片](../image/image_A4q89QM7AB.png "🖼️ 图片")
            -   \[示例]#17 PureComponent中具体的实现方式的代码[¶](https://www.bilibili.com/video/BV1sx4y1L7Rg?t=3042.0\&p=17 "¶") \[`PureComponent`,`shouldComponentUpdate()`[¶](https://www.bilibili.com/video/BV1sx4y1L7Rg?t=3199.2\&p=17 "¶")]

                ![](../image/image_jkv-6eKgd6.png)
    -   [x] [18 18.有关REF操作的详细解读\_Duration-51Min](https://www.bilibili.com/video/BV1sx4y1L7Rg/?p=18 "18 18.有关REF操作的详细解读_Duration-51Min")
        -   \[笔记]#18 [有关ref操作的详细解读](https://www.bilibili.com/video/BV1sx4y1L7Rg/?p=18 "有关ref操作的详细解读") \[REVIEW:refs]

            ![](../image/image_d-Rd_enyz2.png)

            ![](../image/image_rQg6N5W4ST.png)
            -   \[示例]#18 \[方式2/3回调(箭头函数)参数形式的ref \[refs]React开启严格模式时，不能使用,方式1/3字符串形式的ref(不推荐) \[]方式3/3 api参数形式的ref(推荐) \[][¶](https://www.bilibili.com/video/BV1sx4y1L7Rg?t=1341.2\&p=18 "¶")]

                ![](../image/image_bj7QnxGInH.png)
            -   \[示例]#18 在组件中使用ref [¶](https://www.bilibili.com/video/BV1sx4y1L7Rg?t=1973.6\&p=18 "¶"); 在父组件是类组件中获取子组件中是函数组件的DOM元素[¶](https://www.bilibili.com/video/BV1sx4y1L7Rg?t=2372.9\&p=18 "¶") \[refs,`React.forwardRef()`]

                ![](../image/image_YFETbWs92y.png)

                ![](../image/image_RUTjooKm54.png)
            -   \[示例]#18 在父组件是类组件中获取子组件中是类数组件的DOM元素[¶](https://www.bilibili.com/video/BV1sx4y1L7Rg?t=2876.3\&p=18 "¶") \[refs]

                ![](../image/image_pVuQFtfEqX.png)

                ![](../image/image_gvNtTmN4vS.png)
    -   [ ] [19 19.关于setState的进阶处理1\_Duration-64Min](https://www.bilibili.com/video/BV1sx4y1L7Rg/?p=19 "19 19.关于setState的进阶处理1_Duration-64Min")
        -   \[笔记]#19 [关于setState的进阶处理](https://www.bilibili.com/video/BV1sx4y1L7Rg/?p=19 "关于setState的进阶处理") \[`setState()`]
            -   示例
    -   [ ] [20 20.关于setState的进阶处理2\_Duration-83Min](https://www.bilibili.com/video/BV1sx4y1L7Rg/?p=20 "20 20.关于setState的进阶处理2_Duration-83Min")
        -   \[笔记]#20 [关于setState的进阶处理2](https://www.bilibili.com/video/BV1sx4y1L7Rg/?p=20 "关于setState的进阶处理2") \[`setState()`]
            -   示例
    -   [x] [21 21.React合成事件语法\_Duration-45Min](https://www.bilibili.com/video/BV1sx4y1L7Rg/?p=21 "21 21.React合成事件语法_Duration-45Min")
        -   笔记]#21 [\[React\]Synthetic 合成事件](<\[React]Synthetic 合成事件_db71uLQJ5RVbif35zuNMME.md> "\[React]Synthetic 合成事件") \[`event`]

            ![](../image/image_90uc-qqJcJ.png)
            -   \[示例]#21 [\[React\]Synthetic 合成事件](<\[React]Synthetic 合成事件_db71uLQJ5RVbif35zuNMME.md> "\[React]Synthetic 合成事件"),`onClick={}`,REVIEW:箭头函数[¶](https://www.bilibili.com/video/BV1sx4y1L7Rg?t=1195.3\&p=21 "¶")]

                ![](../image/image_rfxwXyVU_r.png)
            -   \[示例]#21 传输的第一个参数为event事件对象，除了通过bind传递的参数为最后一个实参才是event[¶](https://www.bilibili.com/video/BV1sx4y1L7Rg?t=1787.3\&p=21 "¶")  \[`event`,`.bind()`]

                ![](../image/image_-mpF-V6nsb.png)

                传输的第一个参数为event事件对象

                ![](../image/image_nX79mi5MYH.png)

                除了通过bind传递的参数为最后一个实参才是event

                ![](../image/image_Vu5T6RrYl8.png)
    -   [x] [22 22.事件及事件委托\_Duration-57Min](https://www.bilibili.com/video/BV1sx4y1L7Rg/?p=22 "22 22.事件及事件委托_Duration-57Min")
        -   \[笔记]#22 [事件及事件委托](https://www.bilibili.com/video/BV1sx4y1L7Rg/?p=22 "事件及事件委托") \[LEAEN:[JS事件|event](JS事件-event_effm8GTXUad7gAK7ag8zNx.md "JS事件|event")\[JS]事件委托捕获阶段目标阶段冒泡阶段]

            ![](../image/image_m7E9zmUJyK.png)

            ![](../image/image_eJatfW-AcP.png)
            -   \[示例]#22 前置知识讲解案例 \[事件的传播机制]

                ![](../image/image_1nH7EBWSue.png)

                示例：阻止事件传播 \[`.stopPropagation()`阻止事件传播，捕获阶段、冒泡阶段，不包括当前的元素的其他事件。 \[目标阶段[¶](https://www.bilibili.com/video/BV1sx4y1L7Rg?t=1467.9\&p=22 "¶")]

                ![](../image/image_ScoASNfOTK.png)

                ![](../image/image_YaDQ_BY8bn.png)

                示例：\[对比] \[`.stopPropagation()`|`.stopImmediatePropagation()`[¶](https://www.bilibili.com/video/BV1sx4y1L7Rg?t=1735.4\&p=22 "¶")]

                ![](../image/image_KwGsJsrO1M.png)

                ![](../image/image_J9KHeB5Jpi.png)
            -   \[示例]#22 \[JS]事件委托[¶](https://www.bilibili.com/video/BV1sx4y1L7Rg?t=2606.5\&p=22 "¶")[¶](https://www.bilibili.com/video/BV1sx4y1L7Rg?t=2680.4\&p=22 "¶")
                -   v1

                    ![](../image/image_8zyzyOSn3y.png)

                    ![](../image/image__msxQOSTzX.png)
                -   v2 通过事件委托

                    ![](../image/image_Yu-920_Mph.png)
                -   v3
    -   [ ] [23 23.React合成事件原理1\_Duration-90Min](https://www.bilibili.com/video/BV1sx4y1L7Rg/?p=23 "23 23.React合成事件原理1_Duration-90Min")
        -   \[笔记]#23 合成事件原理 \[React:`onXxx`+`Capture``onClickCapture()`,﻿\[JS]事件委托﻿]

            ![](../image/image_ZE9dh8kIYK.png)

            ![](../image/image_BKWhFgK1Zj.png)

            ![](../image/image_3aA3mKd9VE.png)
            -   示例]在`componentDidMount()`中使用[\[React\]Synthetic 合成事件](<\[React]Synthetic 合成事件_db71uLQJ5RVbif35zuNMME.md> "\[React]Synthetic 合成事件")[¶](https://www.bilibili.com/video/BV1sx4y1L7Rg?t=629.5\&p=23 "¶")
                > 与原生顺序不同
                React V17即之后的版本，都是委托给 `#root`容器

                ![](../image/image_kuQg468hR3.png)
                ***

    -   [ ] [24 24.React合成事件的底层机制2\_Duration-76Min](https://www.bilibili.com/video/BV1sx4y1L7Rg/?p=24 "24 24.React合成事件的底层机制2_Duration-76Min")
        -   \[笔记]
            -   示例
    -   [ ] [25 25.React事件中的其它细节知识\_Duration-42Min](https://www.bilibili.com/video/BV1sx4y1L7Rg/?p=25 "25 25.React事件中的其它细节知识_Duration-42Min")
        -   \[笔记]
            -   示例
    -   [ ] [26 26.TASKOA-启动后台\_Duration-19Min](https://www.bilibili.com/video/BV1sx4y1L7Rg/?p=26 "26 26.TASKOA-启动后台_Duration-19Min")
        -   \[笔记] to-do案例目标

            ![](../image/image_-qZ7uO7Kfa.png)
            -   \[示例]#26 to-do案例后端搭建
    -   [x] [27 27.TASKOA-Antd组件库基本应用\_Duration-44Min](https://www.bilibili.com/video/BV1sx4y1L7Rg/?p=27 "27 27.TASKOA-Antd组件库基本应用_Duration-44Min")
        -   \[笔记]
            -   \[示例]#27 to-do案例前端UI页面1/?： 使用类式组件实现
                -   \[子示例]antd组件全局汉化 \[antd语言设置:\<ConfigProvider>zhCN]

                    默认antd中的组件文字提醒等都是英语[¶](https://www.bilibili.com/video/BV1sx4y1L7Rg?t=2243.2\&p=27 "¶")

                    ![](../image/image_PakQTaCuOU.png)
    -   [x] [28 28.TASKOA-头部结构样式处理\_Duration-40Min](https://www.bilibili.com/video/BV1sx4y1L7Rg/?p=28 "28 28.TASKOA-头部结构样式处理_Duration-40Min")
        -   \[笔记]
            -   \[示例]#28 to-do案例前端UI页面2/? ：标题与按钮&#x20;

                ![](../image/image_wGRUITjqz3.png)
                -   子示例：按钮圆角改成直角，去除antd的默认样式[¶](https://www.bilibili.com/video/BV1sx4y1L7Rg?t=1538.1\&p=28 "¶")：找到对应类名，直接覆写在自定义样式中 \[[\[JS库\]antd](\[JS库]antd_caQzfSXshntbdsi9UQvwgX.md "\[JS库]antd")]

                    ![](../image/image_PaO2U_ol2T.png)

                    ![](../image/image_6DlgtEkWl1.png)
    -   [x] [29 29.TASKOA-TABLE组件的使用\_Duration-65Min](https://www.bilibili.com/video/BV1sx4y1L7Rg/?p=29 "29 29.TASKOA-TABLE组件的使用_Duration-65Min")
        -   \[笔记]
            -   \[示例]#29 to-do案例前端UI页面3/? ：to-do表格 \[\<Table>(Table(columnstitle,dataSource),Column(dataIndex[¶](https://www.bilibili.com/video/BV1sx4y1L7Rg?t=1613.2\&p=29 "¶"),render,align[¶](https://www.bilibili.com/video/BV1sx4y1L7Rg?t=3328.8\&p=29 "¶"),ellipsis[¶](https://www.bilibili.com/video/BV1sx4y1L7Rg?t=3441.4\&p=29 "¶")))，\<Popconfirm>(title,onConfirm()),\<Button>]

                ![](../image/image_wiAsbNEYly.png)

                ![](../image/image_QEmZXSKWOV.png)
                -   v1 初始结构

                    ![](../image/image_gC42arCmHV.png)

                    ![](../image/image_XL8no-z2-x.png)
                -   v2 完成[¶](https://www.bilibili.com/video/BV1sx4y1L7Rg?t=3729.5\&p=29 "¶")
                ***
                -   子示例：状态列 \[render]

                    ![](../image/image_vJeJ0jxAvF.png)

                    ![](../image/image_0gWIK0-slz.png)
                -   子示例：完成时间列[¶](https://www.bilibili.com/video/BV1sx4y1L7Rg?t=2147.0\&p=29 "¶") \[render,string.match()]

                    ![](../image/image_jCuzb87fNI.png)

                    ![](../image/image_bB43hJM7AY.png)

                    ![](../image/image_aX-0jG2Zgc.png)
                -   子示例：操作列[¶](https://www.bilibili.com/video/BV1sx4y1L7Rg?t=2669.7\&p=29 "¶") \[\<Popconfirm>(title,onConfirm())[¶](https://www.bilibili.com/video/BV1sx4y1L7Rg?t=2758.1\&p=29 "¶"),\<Button>]
                    -   v3

                        ![](../image/image_EKheQLgAt6.png)
                    -   v2

                        ![](../image/image_ee39iVl-DF.png)

                        ![](../image/image_cSB8axDPrJ.png)
                    -   v1

                        ![](../image/image_OXCpgy36b_.png)

                        ![](../image/image_QjZYeKHEbb.png)
                -   子示例：是否超出换行 \[ellipsis[¶](https://www.bilibili.com/video/BV1sx4y1L7Rg?t=3441.4\&p=29 "¶")]

                    ![](../image/image_o64GLVGrdp.png)

                    ![](../image/image_lob878QLxF.png)
                -   子示例：设置列宽 \[width[¶](https://www.bilibili.com/video/BV1sx4y1L7Rg?t=3546.2\&p=29 "¶")]

                    ![](../image/image_QEmZXSKWOV.png)

                    ![](../image/image_lDgPaD2N7K.png)
    -   [x] [30 30.TASKOA-Modal和Form组件的运用\_Duration-136Min](https://www.bilibili.com/video/BV1sx4y1L7Rg/?p=30 "30 30.TASKOA-Modal和Form组件的运用_Duration-136Min")
        -   \[笔记]
            -   示例#30 to-do案例前端UI页面2/? ：点击按钮弹出对话框 \[[\[JS库\]antd](\[JS库]antd_caQzfSXshntbdsi9UQvwgX.md "\[JS库]antd")\<Modal>[¶](https://www.bilibili.com/video/BV1sx4y1L7Rg?t=150.7\&p=30 "¶")(open,titile,cancelButtonProps[¶](https://www.bilibili.com/video/BV1sx4y1L7Rg?t=512.1\&p=30 "¶"),centered[¶](https://www.bilibili.com/video/BV1sx4y1L7Rg?t=550.9\&p=30 "¶"),confirmLoading[¶](https://www.bilibili.com/video/BV1sx4y1L7Rg?t=589.5\&p=30 "¶"),getContainer[¶](https://www.bilibili.com/video/BV1sx4y1L7Rg?t=1016.4\&p=30 "¶"),onCancel[¶](https://www.bilibili.com/video/BV1sx4y1L7Rg?t=1326.0\&p=30 "¶"))]
                -   v1

                    ![](../image/image_fUUAdi3APK.png)

                    ![](../image/image_9PS2yLiR28.png)

                    ![](../image/image_t6VKiHICD_.png)

                    ![](../image/image_8R5u9silDO.png)
                -   v2 关闭对话框按钮逻辑

                    ![](../image/image_eobnM6opvb.png)

                    ![](../image/image_AbHKTeM1gX.png)
            -   子示例：视图驱动状态的实现 \[[MVVM](MVVM_qUkvMWRoX5WbrFezDf1Nmi.md "MVVM"),[MVC](MVC_6Grg764tEBKQ4c24UR9uM6.md "MVC")[¶](https://www.bilibili.com/video/BV1sx4y1L7Rg?t=2244.7\&p=30 "¶"),`onClick={}``event.target.value`,]

                ![](../image/image_igk63RltCg.png)

                ![](../image/image_UWpBL572hq.png)
            -   \[示例]#30 to-do案例前端UI页面2/? ：弹窗的表单设置 \[\<Form>[¶](https://www.bilibili.com/video/BV1sx4y1L7Rg?t=2453.1\&p=30 "¶")\<Form.Item>[¶](https://www.bilibili.com/video/BV1sx4y1L7Rg?t=2523.1\&p=30 "¶"),\<Input>[¶](https://www.bilibili.com/video/BV1sx4y1L7Rg?t=2556.3\&p=30 "¶")(Input.TextArea[¶](https://www.bilibili.com/video/BV1sx4y1L7Rg?t=2578.6\&p=30 "¶")(rows[¶](https://www.bilibili.com/video/BV1sx4y1L7Rg?t=2666.1\&p=30 "¶"),value[¶](https://www.bilibili.com/video/BV1sx4y1L7Rg?t=3225.4\&p=30 "¶"))),\<DatePicker>[¶](https://www.bilibili.com/video/BV1sx4y1L7Rg?t=2947.5\&p=30 "¶")(showtime[¶](https://www.bilibili.com/video/BV1sx4y1L7Rg?t=3001.1\&p=30 "¶"),value[¶](https://www.bilibili.com/video/BV1sx4y1L7Rg?t=3242.5\&p=30 "¶")[¶](https://www.bilibili.com/video/BV1sx4y1L7Rg?t=3873.7\&p=30 "¶")),`onChange`[¶](https://www.bilibili.com/video/BV1sx4y1L7Rg?t=3301.6\&p=30 "¶")]
                -   ₛₗv1 表单的样式完成

                    ![](../image/image_ZjbAJKmbtz.png)

                    ![](../image/image_qNXuzeQ9PY.png)
                    -   显示日期选择

                        ![](../image/image_hEHZQIQn4T.png)
                -   ₛₗv2 表单逻辑[¶](https://www.bilibili.com/video/BV1sx4y1L7Rg?t=3181.1\&p=30 "¶")：自己手动实现逻辑：获取用户输入的数据进行处理：自己手动实现，不通过antd的表单来实现

                    ![](../image/image_B2vfc8XAQ3.png)

                    ![](../image/image_Vq32Vqc9oP.png)

                    ![](../image/image_ymPd4H3rvM.png)


                -   ₛₗv3 表单逻辑[¶](https://www.bilibili.com/video/BV1sx4y1L7Rg?t=4649.9\&p=30 "¶")：**通过Form表单自带校验实现 **\[\<Form.Item>(label[¶](https://www.bilibili.com/video/BV1sx4y1L7Rg?t=4853.7\&p=30 "¶"),name[¶](https://www.bilibili.com/video/BV1sx4y1L7Rg?t=4922.4\&p=30 "¶"),**rules**[¶](https://www.bilibili.com/video/BV1sx4y1L7Rg?t=5043.5\&p=30 "¶"),trigger[¶](https://www.bilibili.com/video/BV1sx4y1L7Rg?t=5230.0\&p=30 "¶"),validateTrigger[¶](https://www.bilibili.com/video/BV1sx4y1L7Rg?t=5230.0\&p=30 "¶")),\<Form>(initialValues[¶](https://www.bilibili.com/video/BV1sx4y1L7Rg?t=5840.9\&p=30 "¶"))]
                    -   \[完整示例][¶](https://www.bilibili.com/video/BV1sx4y1L7Rg?t=6288.4\&p=30 "¶")[¶](https://www.bilibili.com/video/BV1sx4y1L7Rg?t=7951.2\&p=30 "¶") \[扩展：FormInstance[¶](https://ant.design/components/form-cn#forminstance "¶")]

                        v2

                        ![](../image/image_iyjtoCalLo.png)
                        ***
                        > 表单实例：在表单标签之外获取表单中的数据
                        ![](../image/image_z0GcCMAWeu.png)
                        -   子示例：关闭对话框之后，清除表单内容& 新增任务[¶](https://www.bilibili.com/video/BV1sx4y1L7Rg?t=7206.9\&p=30 "¶") \[refs,resetFields&`await``async`[¶](https://www.bilibili.com/video/BV1sx4y1L7Rg?t=7322.8\&p=30 "¶"),message()[¶](https://www.bilibili.com/video/BV1sx4y1L7Rg?t=7392.6\&p=30 "¶"),`try...catch`[¶](https://www.bilibili.com/video/BV1sx4y1L7Rg?t=7492.2\&p=30 "¶"),getFieldsValue[¶](https://www.bilibili.com/video/BV1sx4y1L7Rg?t=7594.5\&p=30 "¶")]

                            ![](../image/image_8zlyvi69HJ.png)

                            ![](../image/image_1DdiAGNAF3.png)
                            ***
                            ![](../image/image__9hqUB-J6o.png)

                            校验通过时[¶](https://www.bilibili.com/video/BV1sx4y1L7Rg?t=7546.9\&p=30 "¶")

                            ![](../image/image_JA5VL3QB2V.png)
                    ***
                    -   v1 前置代码

                        ![](../image/image_p9bM2yd5g3.png)
                        ***
                    -   v2 设置label

                        ![](../image/image_6U2AP02jgi.png)
                    -   v3 设置校验 \[**rules**[¶](https://www.bilibili.com/video/BV1sx4y1L7Rg?t=5382.9\&p=30 "¶")(message[¶](https://www.bilibili.com/video/BV1sx4y1L7Rg?t=5423.1\&p=30 "¶"),min[¶](https://www.bilibili.com/video/BV1sx4y1L7Rg?t=5491.0\&p=30 "¶"))]

                        ![](../image/image_3USs9PJWNn.png)
                    -   \[子示例]： 出发校验的按钮(提交submit[¶](https://www.bilibili.com/video/BV1sx4y1L7Rg?t=6192.2\&p=30 "¶")) \[\<Button>(htmlType)]

                        ![](../image/image_N-4wNJFaxl.png)
            ***
    -   [x] [31 31.TASKOA-数据接口请求的管理\_Duration-35Min](https://www.bilibili.com/video/BV1sx4y1L7Rg/?p=31 "31 31.TASKOA-数据接口请求的管理_Duration-35Min")
        -   \[笔记]&#x20;
            -   \[示例]#31 to-do案例接口的请求与响应处理|接口的统一管理3/?：\[[\[JS库\]axios](\[JS库]axios_3KLSyeBhEtnvZAkP4DS4aU.md "\[JS库]axios")[¶](https://www.bilibili.com/video/BV1sx4y1L7Rg?t=1454.5\&p=31 "¶")`axios.create`[¶](https://www.bilibili.com/video/BV1sx4y1L7Rg?t=1427.1\&p=31 "¶"),`axios.default.transformRequest`[¶](https://www.bilibili.com/video/BV1sx4y1L7Rg?t=1477.1\&p=31 "¶"),`axios.interceptors.response.use()`[¶](https://www.bilibili.com/video/BV1sx4y1L7Rg?t=1552.8\&p=31 "¶")]
                -   v1：创建axios实例http，src/api/http.js

                    ![](../image/image_qOir6mh8vQ.png)

                    ![](../image/image_Gd6ORrNtE_.png)
                    -   子示例：跨域代理

                        ![](../image/image_WnrpXybZDe.png)
                    -   子示例：axios拦截器，对请求失败的做统一处理 \[`axios.interceptors.response.use()`[¶](https://www.bilibili.com/video/BV1sx4y1L7Rg?t=1562.0\&p=31 "¶")]

                        ![](../image/image_BeQoMWOsyY.png)
                -   v2：使用axios实例http[¶](https://www.bilibili.com/video/BV1sx4y1L7Rg?t=1664.9\&p=31 "¶") ，src/api/index.js
                    -   获取指定状态的任务信息

                        ![](../image/image_JMuqPdqSV3.png)
                    -   api：增加新任务[¶](https://www.bilibili.com/video/BV1sx4y1L7Rg?t=1833.4\&p=31 "¶")

                        ![](../image/image_-FyG4nGMEV.png)

                        ![](../image/image_c8Lpm9PoXz.png)
                    -   api：删除任务

                        ![](../image/image_vQ_ZE1QyiV.png)

                        ![](../image/image_Zct14cLuRp.png)
                    -   api：完成任务

                        ![](../image/image_RKR6adGvWW.png)

                        ![](../image/image_tstBFENKI_.png)
    -   [ ] [32 32.TASKOA-整体功能的实现\_Duration-70Min](https://www.bilibili.com/video/BV1sx4y1L7Rg/?p=32 "32 32.TASKOA-整体功能的实现_Duration-70Min")
        -   \[笔记]#32 [TASKOA-整体功能的实现](https://www.bilibili.com/video/BV1sx4y1L7Rg/?p=32 "TASKOA-整体功能的实现")4/?
            -   示例
    -   [ ] [33 33.useState及底层处理机制\_Duration-85Min](https://www.bilibili.com/video/BV1sx4y1L7Rg/?p=33 "33 33.useState及底层处理机制_Duration-85Min")
        -   \[笔记]
            -   示例
    -   [ ] [34 34.useState细节处理和同步异步\_Duration-39Min](https://www.bilibili.com/video/BV1sx4y1L7Rg/?p=34 "34 34.useState细节处理和同步异步_Duration-39Min")
        -   \[笔记]
            -   示例
    -   [ ] [35 35.useState函数更新和优化机制\_Duration-64Min](https://www.bilibili.com/video/BV1sx4y1L7Rg/?p=35 "35 35.useState函数更新和优化机制_Duration-64Min")
        -   \[笔记]
            -   示例
    -   [ ] [36 36.useEffect的基础知识和底层机制\_Duration-51Min](https://www.bilibili.com/video/BV1sx4y1L7Rg/?p=36 "36 36.useEffect的基础知识和底层机制_Duration-51Min")
        -   \[笔记]
            -   示例
    -   [ ] [37 37.useLayoutEffect和useEffect的细节\_Duration-63Min](https://www.bilibili.com/video/BV1sx4y1L7Rg/?p=37 "37 37.useLayoutEffect和useEffect的细节_Duration-63Min")
        -   \[笔记]
            -   示例
    -   [ ] [38 38.useRef和useImperativeHandle的使用\_Duration-55Min](https://www.bilibili.com/video/BV1sx4y1L7Rg/?p=38 "38 38.useRef和useImperativeHandle的使用_Duration-55Min")
        -   \[笔记]
            -   示例
    -   [ ] [39 39.基于函数组件重构TASKOA案例1\_Duration-59Min](https://www.bilibili.com/video/BV1sx4y1L7Rg/?p=39 "39 39.基于函数组件重构TASKOA案例1_Duration-59Min")
        -   \[笔记]
            -   示例
    -   [ ] [40 40.基于函数组件重构TASKOA案例2\_Duration-39Min](https://www.bilibili.com/video/BV1sx4y1L7Rg/?p=40 "40 40.基于函数组件重构TASKOA案例2_Duration-39Min")
        -   \[笔记]
            -   示例
    -   [ ] [41 41.基于useMemo构建计算缓存\_Duration-25Min](https://www.bilibili.com/video/BV1sx4y1L7Rg/?p=41 "41 41.基于useMemo构建计算缓存_Duration-25Min")
        -   \[笔记]
            -   示例
    -   [ ] [42 42.基于useCallback缓存函数引用\_Duration-41Min](https://www.bilibili.com/video/BV1sx4y1L7Rg/?p=42 "42 42.基于useCallback缓存函数引用_Duration-41Min")
        -   \[笔记]
            -   示例
    -   [ ] [43 43.基于自定义Hook提取公共逻辑\_Duration-27Min](https://www.bilibili.com/video/BV1sx4y1L7Rg/?p=43 "43 43.基于自定义Hook提取公共逻辑_Duration-27Min")
        -   \[笔记]
            -   示例
    -   [ ] [44 44.复合组件通信的起始\_Duration-16Min](https://www.bilibili.com/video/BV1sx4y1L7Rg/?p=44 "44 44.复合组件通信的起始_Duration-16Min")
        -   \[笔记]
            -   示例
    -   [ ] [45 45.父子通信的核心思想「类组件」\_Duration-55Min](https://www.bilibili.com/video/BV1sx4y1L7Rg/?p=45 "45 45.父子通信的核心思想「类组件」_Duration-55Min")
        -   \[笔记]
            -   示例
    -   [ ] [46 46.父子通信的核心思想「函数组件」\_Duration-34Min](https://www.bilibili.com/video/BV1sx4y1L7Rg/?p=46 "46 46.父子通信的核心思想「函数组件」_Duration-34Min")
        -   \[笔记]
            -   示例
    -   [ ] [47 47.基于上下文方案实现祖先和后代的通信「类组件」\_Duration-47Min](https://www.bilibili.com/video/BV1sx4y1L7Rg/?p=47 "47 47.基于上下文方案实现祖先和后代的通信「类组件」_Duration-47Min")
        -   \[笔记]
            -   示例
    -   [ ] [48 48.基于上下文方案实现祖先和后代的通信「函数组件」\_Duration-19Min](https://www.bilibili.com/video/BV1sx4y1L7Rg/?p=48 "48 48.基于上下文方案实现祖先和后代的通信「函数组件」_Duration-19Min")
        -   \[笔记]
            -   示例
    -   [ ] [49 49.React样式私有化处理「基础方案」\_Duration-53Min](https://www.bilibili.com/video/BV1sx4y1L7Rg/?p=49 "49 49.React样式私有化处理「基础方案」_Duration-53Min")
        -   \[笔记]
            -   示例
    -   [ ] [50 50.React样式私有化处理「CSSModules」\_Duration-51Min](https://www.bilibili.com/video/BV1sx4y1L7Rg/?p=50 "50 50.React样式私有化处理「CSSModules」_Duration-51Min")
        -   \[笔记]
            -   示例
    -   [ ] [51 51.React样式私有化处理「ReactJSS」\_Duration-52Min](https://www.bilibili.com/video/BV1sx4y1L7Rg/?p=51 "51 51.React样式私有化处理「ReactJSS」_Duration-52Min")
        -   \[笔记]
            -   示例
    -   [ ] [52 52.React中的HOC高阶组件处理\_Duration-24Min](https://www.bilibili.com/video/BV1sx4y1L7Rg/?p=52 "52 52.React中的HOC高阶组件处理_Duration-24Min")
        -   \[笔记]
            -   示例
    -   [ ] [53 53.React样式私有化处理「styled-components」\_Duration-57Min](https://www.bilibili.com/video/BV1sx4y1L7Rg/?p=53 "53 53.React样式私有化处理「styled-components」_Duration-57Min")
        -   \[笔记]
            -   示例
    -   [ ] [54 54.Redux的基础操作和思想1\_Duration-57Min](https://www.bilibili.com/video/BV1sx4y1L7Rg/?p=54 "54 54.Redux的基础操作和思想1_Duration-57Min")
        -   \[笔记]
            -   示例
    -   [ ] [55 55.Redux的基础操作和思想2\_Duration-96Min](https://www.bilibili.com/video/BV1sx4y1L7Rg/?p=55 "55 55.Redux的基础操作和思想2_Duration-96Min")
        -   \[笔记]
            -   示例
    -   [ ] [56 56.redux部分源码解析\_Duration-38Min](https://www.bilibili.com/video/BV1sx4y1L7Rg/?p=56 "56 56.redux部分源码解析_Duration-38Min")
        -   \[笔记]
            -   示例
    -   [ ] [57 57.复习-redux基础操作流程\_Duration-41Min](https://www.bilibili.com/video/BV1sx4y1L7Rg/?p=57 "57 57.复习-redux基础操作流程_Duration-41Min")
        -   \[笔记]
            -   示例
    -   [ ] [58 58.redux工程化-reducer的拆分和合并\_Duration-40Min](https://www.bilibili.com/video/BV1sx4y1L7Rg/?p=58 "58 58.redux工程化-reducer的拆分和合并_Duration-40Min")
        -   \[笔记]
            -   示例
    -   [ ] [59 59.redux工程化-派发行为标识宏管理\_Duration-22Min](https://www.bilibili.com/video/BV1sx4y1L7Rg/?p=59 "59 59.redux工程化-派发行为标识宏管理_Duration-22Min")
        -   \[笔记]
            -   示例
    -   [ ] [60 60.redux工程化-actionCreator的创建\_Duration-17Min](https://www.bilibili.com/video/BV1sx4y1L7Rg/?p=60 "60 60.redux工程化-actionCreator的创建_Duration-17Min")
        -   \[笔记]
            -   示例
    -   [ ] [61 61.redux工程化-combineReducers源码\_Duration-35Min](https://www.bilibili.com/video/BV1sx4y1L7Rg/?p=61 "61 61.redux工程化-combineReducers源码_Duration-35Min")
        -   \[笔记]
            -   示例
    -   [ ] [62 62.react-redux的基础运用\_Duration-54Min](https://www.bilibili.com/video/BV1sx4y1L7Rg/?p=62 "62 62.react-redux的基础运用_Duration-54Min")
        -   \[笔记]
            -   示例
    -   [ ] [63 63.redux和react-redux的归纳梳理\_Duration-56Min](https://www.bilibili.com/video/BV1sx4y1L7Rg/?p=63 "63 63.redux和react-redux的归纳梳理_Duration-56Min")
        -   \[笔记]
            -   示例
    -   [ ] [64 64.react-redux源码解读\_Duration-45Min](https://www.bilibili.com/video/BV1sx4y1L7Rg/?p=64 "64 64.react-redux源码解读_Duration-45Min")
        -   \[笔记]
            -   示例
    -   [ ] [65 65.redux中间件及处理机制\_Duration-76Min](https://www.bilibili.com/video/BV1sx4y1L7Rg/?p=65 "65 65.redux中间件及处理机制_Duration-76Min")
        -   \[笔记]
            -   示例
    -   [ ] [66 66.基于redux重构TASKOA案例\_Duration-96Min](https://www.bilibili.com/video/BV1sx4y1L7Rg/?p=66 "66 66.基于redux重构TASKOA案例_Duration-96Min")
        -   \[笔记]
            -   示例
    -   [ ] [67 67.fetch的基础语法\_Duration-107Min](https://www.bilibili.com/video/BV1sx4y1L7Rg/?p=67 "67 67.fetch的基础语法_Duration-107Min")
        -   \[笔记]
            -   示例
    -   [ ] [68 68.封装企业级fetch请求库\_Duration-85Min](https://www.bilibili.com/video/BV1sx4y1L7Rg/?p=68 "68 68.封装企业级fetch请求库_Duration-85Min")
        -   \[笔记]
            -   示例
    -   [ ] [69 69.redux-toolkit的应用1\_Duration-50Min](https://www.bilibili.com/video/BV1sx4y1L7Rg/?p=69 "69 69.redux-toolkit的应用1_Duration-50Min")
        -   \[笔记]
            -   示例
    -   [ ] [70 70.redux-toolkit的应用2\_Duration-46Min](https://www.bilibili.com/video/BV1sx4y1L7Rg/?p=70 "70 70.redux-toolkit的应用2_Duration-46Min")
        -   \[笔记]
            -   示例
    -   [ ] [71 71.Object.defineProperty\_Duration-25Min](https://www.bilibili.com/video/BV1sx4y1L7Rg/?p=71 "71 71.Object.defineProperty_Duration-25Min")
        -   \[笔记]
            -   示例
    -   [ ] [72 72.装饰器之类的装饰器处理\_Duration-52Min](https://www.bilibili.com/video/BV1sx4y1L7Rg/?p=72 "72 72.装饰器之类的装饰器处理_Duration-52Min")
        -   \[笔记]
            -   示例
    -   [ ] [73 73.装饰器之属性和方法的装饰器\_Duration-37Min](https://www.bilibili.com/video/BV1sx4y1L7Rg/?p=73 "73 73.装饰器之属性和方法的装饰器_Duration-37Min")
        -   \[笔记]
            -   示例
    -   [ ] [74 74.掌握mobx5的基础知识\_Duration-94Min](https://www.bilibili.com/video/BV1sx4y1L7Rg/?p=74 "74 74.掌握mobx5的基础知识_Duration-94Min")
        -   \[笔记]
            -   示例
    -   [ ] [75 75.mobx的实战运用\_Duration-56Min](https://www.bilibili.com/video/BV1sx4y1L7Rg/?p=75 "75 75.mobx的实战运用_Duration-56Min")
        -   \[笔记]
            -   示例
    -   [ ] [76 76.SPA和前端路由的两种实现方案\_Duration-69Min](https://www.bilibili.com/video/BV1sx4y1L7Rg/?p=76 "76 76.SPA和前端路由的两种实现方案_Duration-69Min")
        -   \[笔记]
            -   示例
    -   [ ] [77 77.react-router-dom的基础运用和细节\_Duration-44Min](https://www.bilibili.com/video/BV1sx4y1L7Rg/?p=77 "77 77.react-router-dom的基础运用和细节_Duration-44Min")
        -   \[笔记]
            -   示例
    -   [ ] [78 78.多级路由的分析和构建\_Duration-35Min](https://www.bilibili.com/video/BV1sx4y1L7Rg/?p=78 "78 78.多级路由的分析和构建_Duration-35Min")
        -   \[笔记]
            -   示例
    -   [ ] [79 79.构建React专属路由表管理机制\_Duration-39Min](https://www.bilibili.com/video/BV1sx4y1L7Rg/?p=79 "79 79.构建React专属路由表管理机制_Duration-39Min")
        -   \[笔记]
            -   示例
    -   [ ] [80 80.React中的路由懒加载方案\_Duration-39Min](https://www.bilibili.com/video/BV1sx4y1L7Rg/?p=80 "80 80.React中的路由懒加载方案_Duration-39Min")
        -   \[笔记]
            -   示例
    -   [ ] [81 81.在组件中获取路由对象信息\_Duration-51Min](https://www.bilibili.com/video/BV1sx4y1L7Rg/?p=81 "81 81.在组件中获取路由对象信息_Duration-51Min")
        -   \[笔记]
            -   示例
    -   [ ] [82 82.路由跳转及传参方案\_Duration-41Min](https://www.bilibili.com/video/BV1sx4y1L7Rg/?p=82 "82 82.路由跳转及传参方案_Duration-41Min")
        -   \[笔记]
            -   示例
    -   [ ] [83 83.NavLink和Link的区别\_Duration-10Min](https://www.bilibili.com/video/BV1sx4y1L7Rg/?p=83 "83 83.NavLink和Link的区别_Duration-10Min")
        -   \[笔记]
            -   示例
    -   [ ] [84 84.routerV6版本的基础操作\_Duration-37Min](https://www.bilibili.com/video/BV1sx4y1L7Rg/?p=84 "84 84.routerV6版本的基础操作_Duration-37Min")
        -   \[笔记]
            -   示例
    -   [ ] [85 85.routerV6中的路由跳转及传参方案\_Duration-53Min](https://www.bilibili.com/video/BV1sx4y1L7Rg/?p=85 "85 85.routerV6中的路由跳转及传参方案_Duration-53Min")
        -   \[笔记]
            -   示例
    -   [ ] [86 86.routerV6中的路由表及统一管理\_Duration-70Min](https://www.bilibili.com/video/BV1sx4y1L7Rg/?p=86 "86 86.routerV6中的路由表及统一管理_Duration-70Min")
        -   \[笔记]
            -   示例
    -   [ ] [87 87.使用useReducer实现对状态统一管理\_Duration-21Min](https://www.bilibili.com/video/BV1sx4y1L7Rg/?p=87 "87 87.使用useReducer实现对状态统一管理_Duration-21Min")
        -   \[笔记]
            -   示例
    -   [ ] [88 88.知乎日报-项目基础概括\_Duration-48Min](https://www.bilibili.com/video/BV1sx4y1L7Rg/?p=88 "88 88.知乎日报-项目基础概括_Duration-48Min")
        -   \[笔记]
            -   示例
    -   [ ] [89 89.知乎日报-REM响应式处理\_Duration-71Min](https://www.bilibili.com/video/BV1sx4y1L7Rg/?p=89 "89 89.知乎日报-REM响应式处理_Duration-71Min")
        -   \[笔记]
            -   示例
    -   [ ] [90 090.知乎日报-配置路由骨架\_Duration-90Min](https://www.bilibili.com/video/BV1sx4y1L7Rg/?p=90 "90 090.知乎日报-配置路由骨架_Duration-90Min")
        -   \[笔记]
            -   示例
    -   [ ] [91 091.知乎日报-redux和请求接口骨架\_Duration-33Min](https://www.bilibili.com/video/BV1sx4y1L7Rg/?p=91 "91 091.知乎日报-redux和请求接口骨架_Duration-33Min")
        -   \[笔记]
            -   示例
    -   [ ] [92 092.知乎日报-培养抽离封装的思想\_Duration-64Min](https://www.bilibili.com/video/BV1sx4y1L7Rg/?p=92 "92 092.知乎日报-培养抽离封装的思想_Duration-64Min")
        -   \[笔记]
            -   示例
    -   [ ] [93 093.知乎日报-完成首页的头部\_Duration-66Min](https://www.bilibili.com/video/BV1sx4y1L7Rg/?p=93 "93 093.知乎日报-完成首页的头部_Duration-66Min")
        -   \[笔记]
            -   示例
    -   [ ] [94 094.知乎日报-完成首页的轮播图\_Duration-73Min](https://www.bilibili.com/video/BV1sx4y1L7Rg/?p=94 "94 094.知乎日报-完成首页的轮播图_Duration-73Min")
        -   \[笔记]
            -   示例
    -   [ ] [95 095.知乎日报-完成首页新闻列表的样式\_Duration-62Min](https://www.bilibili.com/video/BV1sx4y1L7Rg/?p=95 "95 095.知乎日报-完成首页新闻列表的样式_Duration-62Min")
        -   \[笔记]
            -   示例
    -   [ ] [96 096.知乎日报-完成首页新闻列表功能和详情页的样式\_Duration-150Min](https://www.bilibili.com/video/BV1sx4y1L7Rg/?p=96 "96 096.知乎日报-完成首页新闻列表功能和详情页的样式_Duration-150Min")
        -   \[笔记]
            -   示例
    -   [ ] [97 097.知乎日报-完成详情页面数据绑定\_Duration-84Min](https://www.bilibili.com/video/BV1sx4y1L7Rg/?p=97 "97 097.知乎日报-完成详情页面数据绑定_Duration-84Min")
        -   \[笔记]
            -   示例
    -   [ ] [98 098.知乎日报-登录页表单校验处理\_Duration-57Min](https://www.bilibili.com/video/BV1sx4y1L7Rg/?p=98 "98 098.知乎日报-登录页表单校验处理_Duration-57Min")
        -   \[笔记]
            -   示例
    -   [ ] [99 099.知乎日报-Button组件的防抖封装\_Duration-90Min](https://www.bilibili.com/video/BV1sx4y1L7Rg/?p=99 "99 099.知乎日报-Button组件的防抖封装_Duration-90Min")
        -   \[笔记]
            -   示例
    -   [ ] [100 100.知乎日报-登录页的功能1\_Duration-68Min](https://www.bilibili.com/video/BV1sx4y1L7Rg/?p=100 "100 100.知乎日报-登录页的功能1_Duration-68Min")
        -   \[笔记]
            -   示例
    -   [ ] [101 101.知乎日报-redux存储和跳转细节\_Duration-75Min](https://www.bilibili.com/video/BV1sx4y1L7Rg/?p=101 "101 101.知乎日报-redux存储和跳转细节_Duration-75Min")
        -   \[笔记]
            -   示例
    -   [ ] [102 102.知乎日报-登录态校验处理\_Duration-87Min](https://www.bilibili.com/video/BV1sx4y1L7Rg/?p=102 "102 102.知乎日报-登录态校验处理_Duration-87Min")
        -   \[笔记]
            -   示例
    -   [ ] [103 103.知乎日报-首页和详情的登录及收藏管理\_Duration-118Min](https://www.bilibili.com/video/BV1sx4y1L7Rg/?p=103 "103 103.知乎日报-首页和详情的登录及收藏管理_Duration-118Min")
        -   \[笔记]
            -   示例
    -   [ ] [104 104.知乎日报-个人中心和我的收藏\_Duration-78Min](https://www.bilibili.com/video/BV1sx4y1L7Rg/?p=104 "104 104.知乎日报-个人中心和我的收藏_Duration-78Min")
        -   \[笔记]
            -   示例
    -   [ ] [105 105.知乎日报-实现组件的缓存\_Duration-56Min](https://www.bilibili.com/video/BV1sx4y1L7Rg/?p=105 "105 105.知乎日报-实现组件的缓存_Duration-56Min")
        -   \[笔记]
            -   示例
    -   [ ] [106 106.知乎日报-修改个人信息和图片上传\_Duration-121Min](https://www.bilibili.com/video/BV1sx4y1L7Rg/?p=106 "106 106.知乎日报-修改个人信息和图片上传_Duration-121Min")
        -   \[笔记]
            -   示例
    -   [ ] [107 107.React中的DOM-DIFF和Fiber算法\_Duration-90Min](https://www.bilibili.com/video/BV1sx4y1L7Rg/?p=107 "107 107.React中的DOM-DIFF和Fiber算法_Duration-90Min")
        -   \[笔记]
            -   示例
    -   [ ] [108 108.关于索引做为key的优化\_Duration-43Min](https://www.bilibili.com/video/BV1sx4y1L7Rg/?p=108 "108 108.关于索引做为key的优化_Duration-43Min")
        -   \[笔记]
            -   示例
    -   [ ] [109 109.Iterator迭代器和for-of循环原理\_Duration-80Min](https://www.bilibili.com/video/BV1sx4y1L7Rg/?p=109 "109 109.Iterator迭代器和for-of循环原理_Duration-80Min")
        -   \[笔记]
            -   示例
    -   [ ] [110 110.Generator基础和Await原理\_Duration-127Min](https://www.bilibili.com/video/BV1sx4y1L7Rg/?p=110 "110 110.Generator基础和Await原理_Duration-127Min")
        -   \[笔记]
            -   示例
    -   [ ] [111 111.redux-saga的核心处理流程\_Duration-159Min](https://www.bilibili.com/video/BV1sx4y1L7Rg/?p=111 "111 111.redux-saga的核心处理流程_Duration-159Min")
        -   \[笔记]
            -   示例
    -   [ ] [112 112.redux-saga中的API和细节处理\_Duration-122Min](https://www.bilibili.com/video/BV1sx4y1L7Rg/?p=112 "112 112.redux-saga中的API和细节处理_Duration-122Min")
        -   \[笔记]
            -   示例
    -   [ ] [113 113.在create-react-app中使用dva\_Duration-44Min](https://www.bilibili.com/video/BV1sx4y1L7Rg/?p=113 "113 113.在create-react-app中使用dva_Duration-44Min")
        -   \[笔记]
            -   示例
    -   [ ] [114 114.关于dva-cli和roadhog的使用\_Duration-114Min](https://www.bilibili.com/video/BV1sx4y1L7Rg/?p=114 "114 114.关于dva-cli和roadhog的使用_Duration-114Min")
        -   \[笔记]
            -   示例
    -   [ ] [115 115.dva中router的起手式\_Duration-38Min](https://www.bilibili.com/video/BV1sx4y1L7Rg/?p=115 "115 115.dva中router的起手式_Duration-38Min")
        -   \[笔记]
            -   示例
    -   [ ] [116 116.dva中的路由懒加载及动态路由\_Duration-140Min](https://www.bilibili.com/video/BV1sx4y1L7Rg/?p=116 "116 116.dva中的路由懒加载及动态路由_Duration-140Min")
        -   \[笔记]
            -   示例
    -   [ ] [117 117.dva中的路由跳转及传参\_Duration-53Min](https://www.bilibili.com/video/BV1sx4y1L7Rg/?p=117 "117 117.dva中的路由跳转及传参_Duration-53Min")
        -   \[笔记]
            -   示例
    -   [ ] [118 118.dva中Model层的处理流程\_Duration-31Min](https://www.bilibili.com/video/BV1sx4y1L7Rg/?p=118 "118 118.dva中Model层的处理流程_Duration-31Min")
        -   \[笔记]
            -   示例
    -   [ ] [119 119.dva中Model层的详细操作\_Duration-84Min](https://www.bilibili.com/video/BV1sx4y1L7Rg/?p=119 "119 119.dva中Model层的详细操作_Duration-84Min")
        -   \[笔记]
            -   示例
    -   [ ] [120 120.dva中的subscription和dva-loading\_Duration-107Min](https://www.bilibili.com/video/BV1sx4y1L7Rg/?p=120 "120 120.dva中的subscription和dva-loading_Duration-107Min")
        -   \[笔记]
            -   示例
    -   [ ] [121 121.umi4的创建和结构目录\_Duration-78Min](https://www.bilibili.com/video/BV1sx4y1L7Rg/?p=121 "121 121.umi4的创建和结构目录_Duration-78Min")
        -   \[笔记]
            -   示例
    -   [ ] [122 122.umi4中的各种配置项处理\_Duration-83Min](https://www.bilibili.com/video/BV1sx4y1L7Rg/?p=122 "122 122.umi4中的各种配置项处理_Duration-83Min")
        -   \[笔记]
            -   示例
    -   [ ] [123 123.umi4中的路由处理方案\_Duration-101Min](https://www.bilibili.com/video/BV1sx4y1L7Rg/?p=123 "123 123.umi4中的路由处理方案_Duration-101Min")
        -   \[笔记]
            -   示例
    -   [ ] [124 124.综合梳理之对比三大脚手架的区别\_Duration-30Min](https://www.bilibili.com/video/BV1sx4y1L7Rg/?p=124 "124 124.综合梳理之对比三大脚手架的区别_Duration-30Min")
        -   \[笔记]
            -   示例
    -   [ ] [125 125.Antd Pro的基本骨架1\_Duration-176Min](https://www.bilibili.com/video/BV1sx4y1L7Rg/?p=125 "125 125.Antd Pro的基本骨架1_Duration-176Min")
        -   \[笔记]
            -   示例
    -   [ ] [126 126.Antd Pro的基本骨架2\_Duration-111Min](https://www.bilibili.com/video/BV1sx4y1L7Rg/?p=126 "126 126.Antd Pro的基本骨架2_Duration-111Min")
        -   \[笔记]
            -   示例
    -   [ ] [127 127.Antd Pro中的路由配置\_Duration-72Min](https://www.bilibili.com/video/BV1sx4y1L7Rg/?p=127 "127 127.Antd Pro中的路由配置_Duration-72Min")
        -   \[笔记]
            -   示例
    -   [ ] [128 128.CMS内容系统-登录页的结构和功能\_Duration-171Min](https://www.bilibili.com/video/BV1sx4y1L7Rg/?p=128 "128 128.CMS内容系统-登录页的结构和功能_Duration-171Min")
        -   \[笔记]
            -   示例
    -   [ ] [129 129.CMS内容系统-登录态校验处理机制\_Duration-59Min](https://www.bilibili.com/video/BV1sx4y1L7Rg/?p=129 "129 129.CMS内容系统-登录态校验处理机制_Duration-59Min")
        -   \[笔记]
            -   示例
    -   [ ] [130 130.CMS内容系统-表格的相关操作\_Duration-119Min](https://www.bilibili.com/video/BV1sx4y1L7Rg/?p=130 "130 130.CMS内容系统-表格的相关操作_Duration-119Min")
        -   \[笔记]
            -   示例
    -   [ ] [131 01.webpack解决了啥问题\_Duration-39Min](https://www.bilibili.com/video/BV1sx4y1L7Rg/?p=131 "131 01.webpack解决了啥问题_Duration-39Min")
        -   \[笔记]
            -   示例
    -   [ ] [132 02.模块化开发1\_Duration-85Min](https://www.bilibili.com/video/BV1sx4y1L7Rg/?p=132 "132 02.模块化开发1_Duration-85Min")
        -   \[笔记]
            -   示例
    -   [ ] [133 03.模块化开发2\_Duration-78Min](https://www.bilibili.com/video/BV1sx4y1L7Rg/?p=133 "133 03.模块化开发2_Duration-78Min")
        -   \[笔记]
            -   示例
    -   [ ] [134 04.webpack零配置启动及原理\_Duration-54Min](https://www.bilibili.com/video/BV1sx4y1L7Rg/?p=134 "134 04.webpack零配置启动及原理_Duration-54Min")
        -   \[笔记]
            -   示例
    -   [ ] [135 05.webpack基础配置及强缓存机制\_Duration-59Min](https://www.bilibili.com/video/BV1sx4y1L7Rg/?p=135 "135 05.webpack基础配置及强缓存机制_Duration-59Min")
        -   \[笔记]
            -   示例
    -   [ ] [136 06.关于HTML的打包编译\_Duration-42Min](https://www.bilibili.com/video/BV1sx4y1L7Rg/?p=136 "136 06.关于HTML的打包编译_Duration-42Min")
        -   \[笔记]
            -   示例
    -   [ ] [137 07.webpack-dev-server基于语法\_Duration-19Min](https://www.bilibili.com/video/BV1sx4y1L7Rg/?p=137 "137 07.webpack-dev-server基于语法_Duration-19Min")
        -   \[笔记]
            -   示例
    -   [ ] [138 08.实现proxy跨域代理的配置\_Duration-46Min](https://www.bilibili.com/video/BV1sx4y1L7Rg/?p=138 "138 08.实现proxy跨域代理的配置_Duration-46Min")
        -   \[笔记]
            -   示例
    -   [ ] [139 09.CSS全套处理解决方案\_Duration-48Min](https://www.bilibili.com/video/BV1sx4y1L7Rg/?p=139 "139 09.CSS全套处理解决方案_Duration-48Min")
        -   \[笔记]
            -   示例
    -   [ ] [140 10.关于JS的兼容处理和优化项\_Duration-26Min](https://www.bilibili.com/video/BV1sx4y1L7Rg/?p=140 "140 10.关于JS的兼容处理和优化项_Duration-26Min")
        -   \[笔记]
            -   示例
    -   [ ] [141 11.关于图片的处理和别名\_Duration-43Min](https://www.bilibili.com/video/BV1sx4y1L7Rg/?p=141 "141 11.关于图片的处理和别名_Duration-43Min")
        -   \[笔记]
            -   示例









((id#f3VcHqVHYA28pYyNbBTWXN))

((id#s28kbyB1KHhwAUtbxy34BE))

