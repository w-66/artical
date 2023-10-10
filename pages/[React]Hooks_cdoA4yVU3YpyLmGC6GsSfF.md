# \[React]Hooks

-   教程与参考资料
    1.  Hooks的集合与Demo：[https://github.com/zenghongtu/react-use-chinese/blob/master/README.md](https://github.com/zenghongtu/react-use-chinese/blob/master/README.md "https://github.com/zenghongtu/react-use-chinese/blob/master/README.md"), [https://github.com/streamich/react-use](https://github.com/streamich/react-use "https://github.com/streamich/react-use")
    2.  [https://streamich.github.io/react-use/?path=/story/components-usekey--demo](https://streamich.github.io/react-use/?path=/story/components-usekey--demo "https://streamich.github.io/react-use/?path=/story/components-usekey--demo")

Hooks用于函数式组件

以 `use` 开头的函数被称为 **Hook**。`useState` 是 React 提供的一个内置 Hook。你可以在 [React API 参考](https://zh-hans.react.dev/reference/react "React API 参考") 中找到其他内置的 Hook。你也可以通过组合现有的 Hook 来编写属于你自己的 Hook。

***

1.  `State Hook`
2.  `Effect Hook`
3.  `Ref Hook`
4.  路由组件Hook

***





`React.useState()`

`React.useEffect()`

`React.useRef()`

current.innerText

`React.useContext()`

***

`usePamars`

***





`React.useState()`接收一个初始化的参数，返回一个数组

```react&#x20;jsx
const [value, fun] = React.useState(initValue)

```

-   接收一个参数：`INIT_VALUE`初始值
    -   `INIT_VALUE`
-   返回两个参数
    -   `VALUE`
        -   `VALUE`状态值
    -   `FUN()`
        -   `FUN()`设置`VALUE`的函数
    -   第一个参数`VALUE`为传入的一个值
    -   第二个参数为一个函数`FUN()`，用于更新第一个参数的值; 当调用状态更新函数时，React 会使用前一个状态的值作为默认参数传递给更新函数
-   `React.useState()`相当于类式组件中的`componentDidMount()`,`componentDidUpdate()`,`FUN`的返回值其中相当于`componentWillUnmount()` \[类式组件[\[React\]生命周期](\[React]生命周期_daGsiUspap6JwY68rVudND.md "\[React]生命周期")]

`React.useEffect()`监控某个参数`[ARR]`发生变化时，执行对应操作`FUN`(比如log)

-   接收两个参数

<!---->

-   `FUN`
-   `[ARR]`

<!---->

-   `FUN`第一个参数：为函数或执行的操作，可以有返回值
-   `[ARR]`接收的第二个参数：为数组，监测状态(来自useState的参数)，在不写时，监测所有状态 (状态是第一个参数`VALUE`为传入的一个值)
    -   在第二个参数`[ARR]`中的 状态**挂载时**或**更新时**，执行参数(`React.useState()`返回的`VALUE`)所对应的函数(返回的`FUN()`)



***

`React.useRef()`

current.innerText获取标签内容的所有children值





-   示例：`React.useState()`

    `useState` 是 React 中用于管理组件状态的 Hook。它允许你在函数组件中添加状态，并在状态发生变化时重新渲染组件。以下是一个简单的 `useState` 示例：
    ```javascript
    import React, { useState } from 'react';

    function Counter() {
      // 使用 useState 来声明一个状态变量（count），并设置初始值为 0
      const [count, setCount] = useState(0);

      // 定义一个函数来处理点击事件，更新 count 的值
      const handleIncrement = () => {
        setCount(count + 1); // 更新 count 的值
      };

      const handleDecrement = () => {
        setCount(count - 1); // 更新 count 的值
      };

      return (
        <div>
          <h1>计数器</h1>
          <p>当前计数：{count}</p>
          <button onClick={handleIncrement}>增加</button>
          <button onClick={handleDecrement}>减少</button>
        </div>
      );
    }

    export default Counter;
    ```
    在上面的示例中，我们首先导入 `useState` 钩子，然后在函数组件 `Counter` 中使用它来创建一个名为 `count` 的状态变量，并将初始值设为 0。我们还声明了两个事件处理函数 `handleIncrement` 和 `handleDecrement`，它们分别用于增加和减少 `count` 的值。当按钮被点击时，我们使用 `setCount` 函数来更新状态，并在组件中显示当前计数。

    这是一个非常简单的示例，但它演示了如何使用 `useState` 来管理组件的状态。每当状态发生变化时，React 会重新渲染组件，以确保 UI 显示的值是最新的。
-   示例：`React.useRef()`current.innerText



