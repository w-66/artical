# \[React]Synthetic 合成事件

Synthetic /sin'Setik/ Event
合成事件是围绕浏览器原生事件，充当跨浏览器包装器的对象； 它们将不同浏览器的行为合并为一个API，这样做是为了确保事件在不同浏览器中显示一致的属性！让API兼容不同游览器。

## \[React]event

在React中，事件（Event）是用户在浏览器中执行的动作，比如点击、输入、鼠标移动等。React通过事件处理机制允许开发者在组件中定义并处理这些事件。

在React中，事件处理函数（Event Handler）是一种特殊的函数，用于处理组件中定义的事件。事件处理函数通常通过将其作为属性传递给组件的 JSX 元素，从而在组件中注册事件监听器。

React事件处理函数的语法和普通JavaScript函数类似，但有一些特定的约定。在事件处理函数中，事件对象（Event Object）通常作为第一个参数传递给事件处理函数，并被称为 `event`、`e` 或其他类似的变量名。通过访问事件对象，可以获取有关事件的详细信息，例如事件类型、目标元素、鼠标坐标等。

React事件处理函数应该在组件的类中定义，并使用箭头函数、`.bind()` 方法或属性初始化器（Property Initializer）语法来确保正确的函数绑定。这样可以保证事件处理函数在组件中的正确作用域，并且可以访问组件的状态和属性。 \[`.bind()`]

React还提供了一些常见的事件处理函数，如 `onClick`、`onChange`、`onSubmit` 等，用于处理常见的用户交互事件。这些事件处理函数可以通过将其作为属性传递给组件的 JSX 元素来注册，并在事件触发时自动调用相应的处理函数。

需要注意的是，React中的事件处理是合成事件（Synthetic Event），而不是原生浏览器事件。合成事件是React为了解决跨浏览器兼容性问题而实现的一种事件系统，它封装了原生事件，并提供了一些优化和便利的功能，如事件委托、事件池等。

***

合成事件语法：`onXxx`：`on`+[JS事件|event](JS事件-event_effm8GTXUad7gAK7ag8zNx.md "JS事件|event")(首字母大写)

`onXxx`

`onXxx`：`on`+[JS事件|event](JS事件-event_effm8GTXUad7gAK7ag8zNx.md "JS事件|event")(首字母大写)

`onXxx`+`Capture`

`onXxx`+`Capture`表示事件为捕获阶段



***

`onClick={}`

`onClick={}`=`onclick`

`onSubmit={}`

`onChange={}`

`onClickCapture()`

`onClickCapture()`从捕获阶段出发

***

`onChange`

***

## 合成事件原理

-   [\[React\]Synthetic 合成事件](<\[React]Synthetic 合成事件_db71uLQJ5RVbif35zuNMME.md> "\[React]Synthetic 合成事件")都是基于\[JS]事件委托处理的
-   React V17即之后的版本，都是委托给 `#root`容器
-   React V17之后的版本，都是委托给document容器
-   对于没有实现事件的传播机制的事件，才单独做事件绑定

![](../image/image_90uc-qqJcJ.png)

![](../image/image_ZE9dh8kIYK.png)

![](../image/image_3aA3mKd9VE.png)

***

-   `event`
    -   获取合成事件时，默认传递的第一个参数
    -   `event.target`
        -   `event.target.value`
            > 获取输入框内容的值

