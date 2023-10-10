# \[React]组件与模块

***

*   \[笔记]组件与模块介绍

    ![](../image/image_WH-Cts-lRj.png)

\[React]模块

\[React]组件

\[React]模块化

\[React]组件化



***



<1>

## React面向\[React]组件编程

\[React]组件分为：函数式组件类式组件

函数式组件使用[\[JS\]函数](\[JS]函数_q8pKc3ptUXDq5rmKUp42UD.md "\[JS]函数")定义的组件，拥有属性：props

执行过程

类式组件使用[\[JS\]Class](\[JS]Class_fJ1Vahi4EuQg9jYsxwvjmQ.md "\[JS]Class")定义的组件：拥有属性：state,props

*   类式组件必须的条件：1、必须继承`React.Component`、必须有`.render()`; 3、render必须有返回值

函数式组件

类式组件

`React.Component`



***

## 类式组件

### 组件实例的三大核心属性

\[React]组件实例的三大核心属性:state,

### state组件状态

*   \[笔记]总结state

    ![](../image/image_FAJHYaw2-N.png)



state

***

### props组件状态

#### 构造方法中的props

*   \[笔记][类式组件中的构造器与props](https://www.bilibili.com/video/BV1wy4y1D7JT/?p=24 "类式组件中的构造器与props")

    结论：构造方法中的props能省则省

    *   截图

        ![](../image/image_OvpDpd-Gxx.png)

#### props属性|参数

*   一个组件接收一些props属性|参数，我们把这些参数叫做 props（“props” 是 “properties” 简写），然后通过`.render()`返回需要展示在屏幕上的视图的层次结构。

*   props属性|参数只读[¶](https://www.bilibili.com/video/BV1wy4y1D7JT?t=63.5\&p=23 "¶")

<!---->

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

props





#### 对props标签属性进行限制

对props标签属性进行限制所用到外部JS文件：[📄 prop-types.js](../file/prop-types_9OyYE60v1X.js "📄 prop-types.js")

**`PropTypes`**

props属性|参数类型限制

1.  `.string`限制为字符串[¶](https://www.bilibili.com/video/BV1wy4y1D7JT?t=1338.9\&p=22 "¶")

    1.  `PropTypes.string`

2.  `.isRequired`限制为非空[¶](https://www.bilibili.com/video/BV1wy4y1D7JT?t=1338.9\&p=22 "¶")

    1.  `PropTypes.string.isRequired`

3.  `.func`限制为函数[¶](https://www.bilibili.com/video/BV1wy4y1D7JT?t=1320.2\&p=22 "¶")

***

1.  `.string`

2.  `.number`

3.  `.func`

4.  `.isRequired`

5.

***

**`defaultProps`**

1.  **`defaultProps`**设置props属性|参数的默认值



*   示例：对props标签属性进行限制

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

        *   v3：需要增加新的js文件 用于限制组件标签属性限制，模板文件：react\_import\_tmplate.html \[[📄 prop-types.js](../file/prop-types_hhrAo7X3-h.js "📄 prop-types.js")][¶](https://www.bilibili.com/video/BV1wy4y1D7JT?t=837.9\&p=22 "¶")

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

    *   示例：对props标签属性进行限制 \[`.string`,`.isRequired`]

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

## 示例

*   示例：对props标签属性进行限制

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

        *   v3：需要增加新的js文件 用于限制组件标签属性限制，模板文件：react\_import\_tmplate.html \[[📄 prop-types.js](../file/prop-types_Y-DF_flmvk.js "📄 prop-types.js")][¶](https://www.bilibili.com/video/BV1wy4y1D7JT?t=837.9\&p=22 "¶")

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

    *   示例：对props标签属性进行限制 \[`.string`,`.isRequired`]

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

