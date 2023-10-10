# \[Web]DOM

[https://developer.mozilla.org/zh-CN/docs/Web/API/Document\_Object\_Model](https://developer.mozilla.org/zh-CN/docs/Web/API/Document_Object_Model "https://developer.mozilla.org/zh-CN/docs/Web/API/Document_Object_Model")

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

***

页面文档对象模型

Document Object Model页面文档对象模型

**文档对象模型 (*****DOM)*** 将 web 页面与到脚本或编程语言连接起来。通常是指 JavaScript，但将 HTML、SVG 或 XML 文档建模为对象并不是 JavaScript 语言的一部分。DOM 模型用一个逻辑树来表示一个文档，树的每个分支的终点都是一个节点 (node)，每个节点都包含着对象 (objects)。DOM 的方法 (methods) 让你可以用特定方式操作这个树，用这些方法你可以改变文档的结构、样式或者内容。节点可以关联上事件处理器，一旦某一事件被触发了，那些事件处理器就会被执行。

***

<https://developer.mozilla.org/zh-CN/docs/Web/API/Document_Object_Model/Introduction>

DOM提供访问和操作网页内容的方法和接口

***

-   根据HTML标签生成的JS是对象，将页面作为对象进行处理
-   [\[JS\]document](\[JS]document_rmn21mqHBYoFCmcAN3xwXW.md "\[JS]document")是[\[Web\]DOM](\[Web]DOM_hA1J7qvXNRdJxg7CoGu7X.md "\[Web]DOM")中提供的一个对象，网页的所有内容都在里面

***

修改对象属性,`对象.属性 = 'value'`

> Object宿主对象：由浏览器提供的对象; [\[Web\]DOM](\[Web]DOM_hA1J7qvXNRdJxg7CoGu7X.md "\[Web]DOM")、[\[Web\]BOM](\[Web]BOM_jqw3qTusddqCzaELVZVcDF.md "\[Web]BOM")

***



## 示例

-   示例：获取与修改页面属性(标签)的颜色 \[`.querySelector()``querySelectorAll()`,修改对象属性,`对象.属性 = 'value'`Object宿主对象,[\[JS\]for](\[JS]for_7VhrG44qkyaMFiKNoy7bEn.md "\[JS]for")\[`for(a; b; c)`,`for of`],`.dir()`,`.log()`]
    ```javascript
    <body>
        <div id="a1">123</div>
        <div class="c1">456</div>
        <div class="c1">789</div>

        <script>
            const getobj1 = document.querySelector('#a1')     //获取单个元素(标签)
            console.dir(getobj1)  // 通过dir获取(打印)对象属性，打印它(dir专门打印对象的)
            console.log(getobj1)  // 通过log获取(打印)对象属性，打印它(不同浏览器可能不一样，火狐也可以打印出对象的属性，谷歌不行)
            const getobj2 = document.querySelectorAll('.c1')  //获取多个元素(标签)
            console.dir(getobj2)  // 获取多个对象，打印它
            //
            // console.log(getobj1.textContent.charAt(0)) // 获取字符串下标值
            getobj1.style.color = 'blue'  // 修改单个对象(#ai)的样式颜色为蓝色
            // 遍历方式1
            // for(let i = 0; i < getobj2.length; i++){  // 循环遍历多个元素
            //     // console.log(i)
            //     console.dir(getobj2[i])  // 输出每个元素值
            //     getobj2[i].style.color = '#00FA9A'  // 设置每个元素的字体颜色为绿色
            // }
            // 遍历方式2
            for(let i of getobj2){
                console.dir(i)  // 输出每个元素值
                i.style.color = '#00FA9A'  // 设置每个元素的字体颜色为绿色
            }
        </script>
    </body>
    ```
    ![](../image/image_FNlnhYqreY.png)


-   示例：修改标签内的文字; 修改元素的textConten属性 \[`innerText()``innerHTML()`]
    ```javascript
    <body>
       <div id="a1">
        there is only one heroism in the world: to see the world as it is and to love it. 
       </div>
       
       <script>
        const getobj1 = document.getElementById('a1')  // 获取元素
        // console.dir(getobj1)
        // console.log(getobj1.innerText)  // 打印#a1元素中的文本
        // getobj1.innerText = '世界上只有一种英雄主义: 看清世界的本来面目并爱它。'  // 修改文字内容
        // getobj1.innerText = '<i>世界上只有一种英雄主义: 看清世界的本来面目并爱它。</i>'  // 修改文字内容，不识别标签
        getobj1.innerHTML = '<i>世界上只有一种英雄主义: 看清世界的本来面目并爱它。</i>'  // 修改文字内容，识别标签
       </script>
    </body>
    ```

-

