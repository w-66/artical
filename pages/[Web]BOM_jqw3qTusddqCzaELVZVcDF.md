# \[Web]BOM

BOM（浏览器对象模型）

-   参考
    -   [https://juejin.cn/post/6844903576859328526](https://juejin.cn/post/6844903576859328526 "https://juejin.cn/post/6844903576859328526")

***

BOM 的一些常见对象包括：

-   window对象：表示浏览器的窗口，是 BOM 的顶层对象，提供了访问和操作浏览器窗口的方法和属性，如打开新窗口、关闭窗口、设置窗口大小和位置等。\[[\[JS\]window](\[JS]window_snhwUXnJn5t8WbhABkxRnZ.md "\[JS]window")]

1.  navigator 对象：提供了关于浏览器的信息，如浏览器的名称、版本、用户代理字符串等。
2.  document 对象：表示当前浏览器窗口中的 HTML 文档，提供了访问和操作文档内容的方法和属性，如获取元素、修改元素内容、修改样式等。 \[[\[JS\]document](\[JS]document_rmn21mqHBYoFCmcAN3xwXW.md "\[JS]document")]
3.  history 对象：提供了访问浏览器历史记录的方法和属性，如前进、后退、跳转到指定页面等。 \[[\[JS\]history](\[JS]history_wknz5W9Lwmeoi1yVtPWX2q.md "\[JS]history")]
4.  location 对象：提供了访问当前页面 URL 信息的方法和属性，如获取 URL 参数、修改 URL 等。

***



-   \[Q]JavaScript 与 ecmascript 、Webapi、DOM、BOM之间的关系 \[[JavaScript](JavaScript_w7M7UmgSNLmfSHDWMLjuEi.md "JavaScript"),[Web API](<Web API_xqfMA9k6EZ7DqSNzYScTDF.md> "Web API"),[\[Web\]DOM](\[Web]DOM_hA1J7qvXNRdJxg7CoGu7X.md "\[Web]DOM"),[\[Web\]BOM](\[Web]BOM_jqw3qTusddqCzaELVZVcDF.md "\[Web]BOM")]

    JavaScript 是一种脚本语言，用于编写网页的交互功能和动态效果。ECMAScript 是 JavaScript 的标准化版本，它规定了 JavaScript 语言的语法、类型、运算符、对象和内置函数等方面的规范。

    Web API 指的是 Web 应用程序编程接口（Application Programming Interface），它包括了 DOM 和 BOM。DOM（文档对象模型）指的是 HTML 和 XML 文档的编程接口，允许 JavaScript 修改和交互网页的内容和结构。BOM（浏览器对象模型）是指浏览器窗口及其相关组件（如地址栏、按钮等）的编程接口，允许 JavaScript 控制浏览器的行为。

    JavaScript 可以通过 Web API 访问 DOM 和 BOM 提供的功能，实现与网页的交互。同时，ECMAScript 也是 JavaScript 的一部分，JavaScript 实现了 ECMAScript 规范。因此，JavaScript 包含 ECMAScript，同时也可以通过 Web API 访问 DOM 和 BOM。
    ```mermaid
    graph LR
        JS[JavaScript] --> ES[ECMAScript]
        JS --> WebAPI
        WebAPI --> DOM
        WebAPI --> BOM
        DOM -->|提供|WebAPI
        BOM -->|提供|WebAPI
    ```
