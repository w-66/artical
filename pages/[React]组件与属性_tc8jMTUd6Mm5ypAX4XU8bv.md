# \[React]组件与属性

## 概念碎片

-   组件命名需要使用大写字母开头(PascalCase大驼峰命名)

***



-   \[笔记]组件与模块介绍

    ![](../image/image_euBqLl1IM5.png)

\[React]模块

\[React]组件

\[React]模块化

\[React]组件化

组件化开发

-   灵活的复用组件
    -   [\[React\]插槽机制](\[React]插槽机制_uuaHRdrQYxNTMe2KLps9ws.md "\[React]插槽机制"),props

### \[React]组件分类

-   \[React]组件按编程方式分为：函数式组件类式组件,Hooks组件

***

-   静态组件
-   动态组件
-   复合组件

#### 按包含关系

-   父组件
    -   子组件
-   兄弟组件(非嵌套组件)
-   任意组件
-   祖组件(跨级组件)
    -   后代组件

#### 按功能分类

-   一般组件
-   路由组件
    -   路由组件的会接收三个props [🖼️ 图片](../image/image_eKUtbtcWuW.png "🖼️ 图片")
    -   \[对比]一般组件|路由组件
        -   一般组件：直接写、路由组件：通过Router
        -   例如：一般组件：直接写、路由组件：通过Router

            ![](../image/image_5MTsoW_wO8.png)
        -   例如：路由组件的会接收三个props&#x20;

            ![](../image/image_7nHI7knLeF.png)



### 组件的通信方式

-   组件通信方式1/4：props
-   组件通信方式2/4：[\[React\]消息订阅&消息发布](\[React]消息订阅&消息发布_prwmsFoDKTvHDdrrD4DvXQ.md "\[React]消息订阅&消息发布")：[\[JS库\]PubSubJS](\[JS库]PubSubJS_xPdUSX2Zq1GZCEBDd9RK4.md "\[JS库]PubSubJS")
-   组件通信方式3/4：状态属性全局共享|集中式管理：[\[JS库\]redux](\[JS库]redux_wYUdBtUF4wPMD74fXKn7zd.md "\[JS库]redux")
-   组件通信方式4/4：Context：`React.createContext()`,`Provider`,`Consumer`; `React.useContext()`

***

#### 推荐的组件之间的通信方式

1.  父组件 →传递参数 →子组件&#x20;
    1.  父组件 →传递参数 →子组件 可以通过 ：组件通信方式1/4：props
2.  父组件 ←传递参数 ←子组件&#x20;
    1.  父组件 ←传递参数 ←子组件 可以通过 组件通信方式1/4：props，但是需要一个前提，父组件提前传递的是一个函数
3.  任意组件,兄弟组件(非嵌套组件)通信方式：组件通信方式2/4：[\[React\]消息订阅&消息发布](\[React]消息订阅&消息发布_prwmsFoDKTvHDdrrD4DvXQ.md "\[React]消息订阅&消息发布")：[\[JS库\]PubSubJS](\[JS库]PubSubJS_xPdUSX2Zq1GZCEBDd9RK4.md "\[JS库]PubSubJS")
4.  任意组件组件通信方式3/4：状态属性全局共享|集中式管理：[\[JS库\]redux](\[JS库]redux_wYUdBtUF4wPMD74fXKn7zd.md "\[JS库]redux")
5.  祖组件(跨级组件)后代组件组件通信方式4/4：Context：`React.createContext()`,`Provider`,`Consumer`; `React.useContext()`

[\[React\]消息订阅&消息发布](\[React]消息订阅&消息发布_prwmsFoDKTvHDdrrD4DvXQ.md "\[React]消息订阅&消息发布")

***

-   示例：函数式组件的父组件 →传递参数 →子组件 [¶](https://zh-hans.react.dev/learn#sharing-data-between-components "¶") \[`React.useState()`]

    ![](../image/sharing_data_parent_clicked_DR4E-DShu-.webp)
    -   父组件
        ```react&#x20;jsx
        export default function MyApp() {
           const [count, setCount] = useState(0); 

          function handleClick() {
            setCount(count + 1);
          }

          return (
            <div>
              <h1>Counters that update together</h1>
              <MyButton count={count} onClick={handleClick} />
              <MyButton count={count} onClick={handleClick} />
            </div>
          );
        }
        ```
    -   子组件
        ```react&#x20;jsx
        function MyButton( { count, onClick } ) {
          return (
            <button onClick={onClick}>
              Clicked {count} times
            </button>
          );
        }
        ```
-   示例：祖组件(跨级组件)后代组件组件通信方式4/4：Context：`React.createContext()`,`Provider`,`Consumer`; `React.useContext()`



    2、使用MyContext.Provider传参 \[2/3 `Provider`]

    3、导入，使用useContext(MyContext)接参数 \[3/3 `React.useContext()`]

    我的示例code：F:\Code\Web\React\react\_learn\src\components\Demo\DemoCreateContext
    ***
    在React中，`useContext`是一个钩子函数（hook），它允许你在函数组件中直接访问上下文（context）的值。上下文提供了一种在组件之间共享数据的方式，而不必手动在每个组件层级上传递props。

    以下是如何使用`useContext`的基本示例：

    首先，你需要使用`createContext`函数创建一个上下文：并导出
    ```react&#x20;jsx
    import React, { createContext } from 'react';

    // 创建上下文
    export const MyContext = createContext();
    ```
    然后，你可以使用`Provider`组件为上下文提供一个值：
    ```react&#x20;jsx
    function App() {
      const contextValue = '你好，世界！';

      return (
        <MyContext.Provider value={contextValue}>
          <ChildComponent />
        </MyContext.Provider>
      );
    }
    ```
    现在，你可以在子组件中使用`useContext`钩子来访问上下文的值：<注意需要导入：MyContext>
    ```react&#x20;jsx
    import React, { useContext } from 'react';
    import { MyContext } from './App'     // 

    function ChildComponent() {
      const contextValue = useContext(MyContext);

      return <div>{contextValue}</div>;
    }
    ```
    或者使用
    ```react&#x20;jsx
    import MyContext from './App'   //

    // 方式2
    export default function Third() {

        return (
          <div>
            <MyContext.Consumer>
              {
                (send)=>{
                  return 
                    <div>
                        第三层
                        接收来自第一层的参数：{send.a},{send.b}
                    </div>
                }
              }
            </MyContext.Consumer>
          </div>
        )
    }

    ```
    在这个例子中，`ChildComponent`将显示在`App`组件中通过上下文提供的值"你好，世界！"。

    使用`useContext`时，记得从 'react' 包中导入所需的模块（`useContext`，`createContext`）。

    请注意，`useContext`只能在函数组件中使用，而不能在类组件中使用。

***



<1>

## React面向\[React]组件编程

函数式组件使用[\[JS\]函数](\[JS]函数_q8pKc3ptUXDq5rmKUp42UD.md "\[JS]函数")定义的组件，拥有属性：props

执行过程

类式组件使用[\[JS\]Class](\[JS]Class_fJ1Vahi4EuQg9jYsxwvjmQ.md "\[JS]Class")定义的组件：拥有属性：state,props

-   类式组件必须的条件：1、必须继承`React.Component`、必须有`ReactDOM.render()`; 3、render必须有返回值

Hooks组件包含[\[React\]Hooks](\[React]Hooks_cdoA4yVU3YpyLmGC6GsSfF.md "\[React]Hooks")的函数式组件

函数式组件

类式组件

Hooks组件

`React.Component`



***

## 类式组件

### 组件实例的三大核心属性

\[React]组件实例的三大核心属性:state,props,refs

***

### state属性解析

-   状态提升
    -   状态提升在几个组件都需要使用同一个状态时，放在他们共有的父组件中
-   状态在哪里，操作状态的方法就在哪里
-   概念详解：state：是组件中最重要的属性，值是对象(可以包含多个key-value的组合)

    组件被称为"状态机" 通过更新组件的state来更新对应的页面显示(重新煊染组件)
    -   \[笔记]总结state

        ![](../image/image_VGs7aG0SDw.png)

<!---->

-   `setState()`React设定的api，通过它修改state的值&#x20;
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
    -   对象式的setState ：`setState(``stateChange``, [``callback``])`
        -   `stateChange`
            -   所需要更新的状态
        -   React的状态更新是异步更新
            -   调用完setState后的更新为异步更新
    -   函数式的setState： `setState(``updater``, [``callback``])`
        -   `updater`
            -   `updater`为函数，返回一个状态修改的对象相等于`stateChange`的格式
            -   `updater`可以接收state,props
    -   `callback`
        -   `callback`在状态更新完毕之后，执行的回调(可选)
    -   使用原则



state

-   `setState()`



***

### props属性

#### 构造方法中的props

-   \[笔记][类式组件中的构造器与props](https://www.bilibili.com/video/BV1wy4y1D7JT/?p=24 "类式组件中的构造器与props")

    结论：构造方法中的props能省则省
    -   截图

        ![](../image/image_IqS73RtvaI.png)

#### props属性|参数

-   一个组件接收一些props属性|参数，我们把这些参数叫做 props（“props” 是 “properties” 简写），然后通过`ReactDOM.render()`返回需要展示在屏幕上的视图的层次结构。
-   props属性|参数只读，原因被冻结了
-   属性参数
-   标签体参数
    -   `children`

<!---->

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


<!---->

-   props

[renderProps](renderProps_xt8dBGp9Cm1yVzaUWSihhL.md "renderProps")





#### 对props属性进行限制

-   对props属性进行限制所用到外部JS文件：[📄 prop-types.js](../file/prop-types_chTGDCHjda.js "📄 prop-types.js")
-   [\[JS库\]prop-type](\[JS库]prop-type_ji55v62TxKVe1hhx4LE1Tp.md "\[JS库]prop-type")模块用于限制props属性

**`PropTypes`**

props属性|参数类型限制

**`defaultProps`**

1.  **`defaultProps`**设置props属性|参数的默认值



-   示例：对props属性进行限制
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
        -   v3：需要增加新的js文件 用于限制组件标签属性限制，模板文件：react\_import\_tmplate.html \[[📄 prop-types.js](../file/prop-types_cd8Lz7kEAT.js "📄 prop-types.js")][¶](https://www.bilibili.com/video/BV1wy4y1D7JT?t=837.9\&p=22 "¶")
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
    -   示例：对props属性进行限制 \[`PropType.string`,`.isRequired`]
        ```javascript
                Person.propTypes = {
                    name:PropTypes.string  // 限制name只能是字符串类型，否则将报错
                }

        ```
        ```javascript
                Person.propTypes = {
                    name:PropTypes.string.isRequired,  // 限制为，name只能是字符串类型，且非空，否则将报错
                }
        ```





***

### refs属性解析

函数式组件调用refs属性的方式：`React.useRef()`

类式组件调用refs属性的三种方式

1.  方式1/3字符串形式的ref(不推荐) \[refs]
    1.  React开启严格模式时，不能使用
2.  方式2/3回调(箭头函数)参数形式的ref \[refs]
3.  方式3/3 api参数形式的ref(推荐) \[refs]

-   示例
    -   \[示例]#18 \[方式2/3回调(箭头函数)参数形式的ref \[refs]React开启严格模式时，不能使用,方式1/3字符串形式的ref(不推荐) \[]方式3/3 api参数形式的ref(推荐) \[][¶](https://www.bilibili.com/video/BV1sx4y1L7Rg?t=1341.2\&p=18 "¶")]

        ![](../image/image_bj7QnxGInH.png)
-   在参数是ref时，才会帮你调用函数
-   1

    ![](../image/image_yniusP4esD.png)

<!---->

-   refs



***

### 收集表单数据

1.  受控组件
2.  非受控组件



-   受控组件可以省略refs的设置(推荐)

***



## 示例

-   示例：对props属性进行限制
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
        -   v3：需要增加新的js文件 用于限制组件标签属性限制，模板文件：react\_import\_tmplate.html \[[📄 prop-types.js](../file/prop-types_GhdaixZjfH.js "📄 prop-types.js")][¶](https://www.bilibili.com/video/BV1wy4y1D7JT?t=837.9\&p=22 "¶")
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
    -   示例：对props属性进行限制 \[`PropType.string`,`.isRequired`]
        ```javascript
                Person.propTypes = {
                    name:PropTypes.string  // 限制name只能是字符串类型，否则将报错
                }

        ```
        ```javascript
                Person.propTypes = {
                    name:PropTypes.string.isRequired,  // 限制为，name只能是字符串类型，且非空，否则将报错
                }
        ```



## 碎片

React事件绑定

`.hsetState()`

-

