# \[React]JSX

-   JSX
    -   React 开发者使用了一种名为 “JSX” 的特殊语法，JSX 可以让你更轻松地书写这些结构。

***

## JSX渲染底层机制

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

## JSX语法规则

> 小驼峰写法

***

#### 显示数据

```react&#x20;jsx
return (
  <h1>
    {user.name}
  </h1>
);
```

```react&#x20;jsx
return (
  <img
    className="avatar"
    src={user.imageUrl}
  />
);
```

```react&#x20;jsx
alt={'Photo of ' + user.name}
```

#### 条件渲染 \[[\[JS\]if](\[JS]if_cNSkTrWJmTaq7tAtcdRMNT.md "\[JS]if")\[JS]三元运算符,`&&`]

在 React 中，没有特殊的语法来编写条件。因此，你将使用与编写常规 JavaScript 代码时相同的技术。例如，你可以使用 [if](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Statements/if...else "if") 语句根据条件引入 JSX：

```react&#x20;jsx
let content;
if (isLoggedIn) {
  content = <AdminPanel />;
} else {
  content = <LoginForm />;
}
return (
  <div>
    {content}
  </div>
);
```

如果你喜欢更为紧凑的代码，你可以使用 [条件 ](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Operators/Conditional_Operator "条件 ")[?](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Operators/Conditional_Operator "?")[ 运算符](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Operators/Conditional_Operator " 运算符")。与 `if` 不同的是，它工作于 JSX 内部：

```react&#x20;jsx
<div>
  {isLoggedIn ? (
    <AdminPanel />
  ) : (
    <LoginForm />
  )}
</div>
```

当你不需要 `else` 分支时，你还可以使用 [逻辑 ](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Operators/Logical_AND#short-circuit_evaluation "逻辑 ")[&&](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Operators/Logical_AND#short-circuit_evaluation "&&")[ 语法](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Operators/Logical_AND#short-circuit_evaluation " 语法")：

```react&#x20;jsx
<div>
  {isLoggedIn && <AdminPanel />}
</div>
```

所有这些方法也适用于有条件地指定属性。如果你对 JavaScript 语法不熟悉，你可以从一直使用 `if...else` 开始。

#### 渲染列表 \[`Array.map()`]

```react&#x20;jsx
const products = [
  { title: 'Cabbage', id: 1 },
  { title: 'Garlic', id: 2 },
  { title: 'Apple', id: 3 },
];

const listItems = products.map(product =>
  <li key={product.id}>
    {product.title}
  </li>
);

return (
  <ul>{listItems}</ul>
);

```

#### 响应事件

```react&#x20;jsx
function MyButton() {
  function handleClick() {
    alert('You clicked me!');
  }

  return (
    <button onClick={handleClick}>
      Click me
    </button>
  );
}
```

***

`className`DOM中定义class \[**\[HTML]****`class`**]

`style`¶定义样式; 内联样式，要用`style=({key:value}}`的形式去写。&#x20;

-   \[笔记]#5 JSX中可写的语法与花括号可以写的表达式 \[`{}`]

    ![](../image/image_nSgjeNXPTq.png)

    ![](../image/image_DF2GWpHde3.png)
    -   示例
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

`className`

`style`



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

1.  定义虚拟DOM时，不要写引号。

2.  标签中混入JS表达式时要用`{}`。
    1.  `{}`使用的JS表达式，允许语法：[🖼️ 图片](../image/image_jjJnNE74nE.png "🖼️ 图片")
3.  样式的类名指定不要用class，要用className。

4.  内联样式，要用`style=({key:value}}`的形式去写。&#x20;
5.  只有一个根标签
6.  标签必须闭合&#x20;
    1.  组件单闭合
    2.  组件双闭合
        1.  组件双闭合可以传递 `children`
7.  标签首字母&#x20;
    1.  若小写字母开头，则将改标签转为htm1中同名元素，若htm1中无该标签对应的同名元素，则报错
    2.  若大写字母开头，react就去染对应的组件，若组件没有定义，则报错。
8.  JSX注释 `{\**\}`
9.  render中可以使用`<></>`，空文档标签，幽灵标签

***





-   示例： JSX小练习：动态的展示如下列表 \[[\[React\]虚拟DOM](\[React]虚拟DOM_Snd6fanVfJeXQdXpbDqd8.md "\[React]虚拟DOM"),箭头函数,`Array.map()`]

    ![](../image/image_40jPG_bEwQ.png)

    ![](../image/image_GELdFV60vA.png)


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



