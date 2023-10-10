# \[React]生命周期

React生命周期回调函数|生命周期钩子函数|生命周期函数|生命周期钩子

***

## 理解概念

![](../image/image_51Ri0Xyuvl.png)

-   旧版本生命周期流程图(v16)

    ![](../image/image_FgEUlQW-5U.png)

    ![](../image/react生命周期\(旧\)_99TBCI8wXa.png)

<!---->

-   新版本生命周期流程图(v17)

    ![](../image/image_CJIyU3jvnv.png)

    ![](../image/react生命周期\(新\)_BN7shXupxS.png)

***

## React钩子函数

> `componentWillMount()``componentWillReceiveProps()``componentWillUpdate()`在v17版本已经不推荐使用，如要使用需要添加前缀：`UNSAFE_`[🖼️ 图片](../image/image_Jk3LU61znm.png "🖼️ 图片")

1.  `constructor`构造方法
2.  `componentWillMount()`弃用，组件将要挂在时，执行的方法(函数)
3.  `componentDidMount()`组件挂在完毕后，执行的方法(函数)，一般作初始化之用
4.  `componentWillUnmount()`在组件将要卸载前，执行的方法(函数)
5.  `shouldComponentUpdate()`组件更新state时，此方法(函数)返回为true才能被更新，默认返回true \[state`setState()`]

    可接收两个参数
6.  `componentWillReceiveProps()`弃用，组件将要接收参数时，执行(但是第一次接收不执行)
7.  `componentWillUpdate()`弃用，即将更新参数时
8.  `componentDidUpdate()`组件更新完成，执行的方法(函数)，可传入两个参数，更新之前的state 与 props 属性的值
9.  `getDerivedStateFromProps()`使用场景十分少(在state在任何时候都取决于props时)，从属性获取派生状态; 需要返回对象属性(如`{count:2}`或者Null
    -   可以接收props与state属性
10. `getSnapshotBeforeUpdate()`[¶](https://react.dev/reference/react/Component#getsnapshotbeforeupdate "¶")必须返回一个快照值或者Null，并可以将快照值(返回值)传给`componentDidUpdate()`，作用：获取更新之前 的快照值
11. `render()`挂载(渲染)组件到真正的DOM中 \[[\[Web\]DOM](\[Web]DOM_hA1J7qvXNRdJxg7CoGu7X.md "\[Web]DOM")]
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

***

***

1.  `constructor`
2.  `componentWillMount()`
3.  `componentDidMount()`
4.  `render()`
5.  `componentWillReceiveProps()`
6.  `shouldComponentUpdate()`
7.  `componentWillUpdate()`
8.  `componentDidUpdate()`
9.  `componentWillUnmount()`
10. `getDerivedStateFromProps()`
11. `getSnapshotBeforeUpdate()`

***



***

`getDerivedStateFromError()`当所在组件的子组件发生错误时执行

在出现错误的组件的父组件中应用

`componentDidCatch()`捕获渲染时的错误



-   错误边界
-   `getDerivedStateFromError()`
-   `componentDidCatch()`



***

## 课程

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



((id#gnPXUoBuGqPfLXgC5Nf7jJ))
