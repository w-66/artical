# \[React]示例

-   示例：✧获取表单|输入框的数据 \[`React.useState()`,`onChange={}`,`onSubmit={}`]
    1.  设置状态容器&#x20;
    2.  每次不同的表单发生改变时 获取 表单数值，更新到状态中
    3.  根据状态的内容进行表单提交的逻辑操作
    -   注意点

        `prevFormData` 是一个默认参数名称，它通常用来表示前一个状态的数据。在使用 `useState` 钩子创建的状态中，状态更新函数的第一个参数会自动接收前一个状态的值。

        `useState` 钩子的语法是：`const [state, setState] = useState(initialState);`

        其中，`state` 是当前的状态值，`setState` 是用于更新状态的函数，`initialState` 是状态的初始值。

        当调用状态更新函数时，React 会使用前一个状态的值作为默认参数传递给更新函数。这样做是为了确保在状态更新过程中不会丢失或混淆之前的状态数据。

        除了前一个状态的默认参数外，`setState` 函数还可以接收其他参数。例如，可以传递一个新的状态值作为参数来直接更新状态，而不需要依赖前一个状态的值。这在某些情况下可能会有用，但需要注意状态更新的正确性。

        在本示例中，使用箭头函数 `(prevFormData) => ({ ...prevFormData, [name]: fieldValue })` 来更新状态，其中 `prevFormData` 就是默认的前一个状态值。这样可以确保我们在更新状态时基于前一个状态的值进行修改，并保留其他字段的数据。\[第二个参数为一个函数`FUN()`，用于更新第一个参数的值; 当调用状态更新函数时，React 会使用前一个状态的值作为默认参数传递给更新函数]ₛₗ

        需要注意的是，这种默认参数的行为是由 React 自身实现的，而不是 JavaScript 语言本身的特性。这种默认参数的机制是为了方便管理状态，并确保在状态更新过程中不会发生意外的数据丢失或混淆。
    -   code
        ```react&#x20;jsx
        import React, { useState } from 'react';
        import Button from 'react-bootstrap/Button';
        import Form from 'react-bootstrap/Form';

        function BasicExample() {
          // 设置状态容器
           const [formData, setFormData] = useState({
            username: '',
            password: '',
            rememberMe: false,
          });
           
           const handleChange = (event) => { 
            // 每次不同的表单发生改变时 获取 表单数值
             const { name, value, type, checked } = event.target; 
             console.log( event.target); 
            // 如果发生改变的表单类型是复选框，则赋值checked给fieldValue，其他这是赋值输入框的表单参数
             const fieldValue = type === 'checkbox' ? checked : value; 
            // 设置变化的状态的值，通过获取之前的状态值prevFormData来更新变化的值。 prevFormData是setFormData的默认传递的一个参数，参数内容为之前的状态的值
             setFormData((prevFormData) => ({
              ...prevFormData,
              [name]: fieldValue,
            })); 
           }; 

           const handleSubmit = (event) => { 
            // 阻止默认事件
            event.preventDefault();  
            // 在这里处理表单提交逻辑，可以使用 formData 对象中的数据
            console.log(formData);
           }; 

          return (
            <Form  onSubmit={handleSubmit} >
              <Form.Group className="mb-3" controlId="formBasicEmail">
                <Form.Label>Username</Form.Label>
                <Form.Control
                  type="username"
                  placeholder="Username"
                  name="username"
                  value={formData.username}
                   onChange={handleChange} 
                />
              </Form.Group>

              <Form.Group className="mb-3" controlId="formBasicPassword">
                <Form.Label>Password</Form.Label>
                <Form.Control
                  type="password"
                  placeholder="Password"
                  name="password"
                  value={formData.password}
                   onChange={handleChange} 
                />
                <Form.Text className="text-muted">
                  We'll never share your password with anyone else.
                </Form.Text>
              </Form.Group>

              <Form.Group className="mb-3" controlId="formBasicCheckbox">
                <Form.Check
                  type="checkbox"
                  label="Remember me"
                  name="rememberMe"
                  checked={formData.rememberMe}
                   onChange={handleChange} 
                />
              </Form.Group>

              <Button variant="primary" type="submit">
                Login
              </Button>
            </Form>
          );
        }

        export default BasicExample;
        ```
-   示例：建立一个todo任务列表页面

    1、创建基本样式

    [56 056\_尚硅谷\_react教程\_TodoList案例\_静态组件\_Duration-24Min](https://www.bilibili.com/video/BV1wy4y1D7JT/?p=56 "56 056_尚硅谷_react教程_TodoList案例_静态组件_Duration-24Min") &#x20;

    2、

    [57 057\_尚硅谷\_react教程\_TodoList案例\_动态初始化列表\_Duration-20Min](https://www.bilibili.com/video/BV1wy4y1D7JT/?p=57 "57 057_尚硅谷_react教程_TodoList案例_动态初始化列表_Duration-20Min")
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



