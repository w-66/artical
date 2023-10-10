# \[Web]E\&Q

-   前端一段文字既有中文又有英文，但是一个字体只有英文字母，如果想对这段话单独设置中文字体怎么设置?|对中英文单独设置字体

    From chatGPT4 &#x20;

    实测，可行

    在网页设计中，常见的方式是通过在CSS中指定不同的字体，分别用来渲染中文和英文文字。然而，CSS目前并不支持直接在一种语言中选择一种字体。换句话说，你不能简单地为一个"混合"的文字字符串中的中文部分指定一种字体，而为英文部分指定另一种字体。但是，你可以通过利用“Unicode-range”属性的CSS @font-face规则来实现这个效果。

    这里是一个例子：
    ```react&#x20;jsx
    @font-face {
        font-family: 'MyChineseFont';
        src: url('MyChineseFont.woff2') format('woff2'),
             url('MyChineseFont.woff') format('woff');
        unicode-range: U+4E00-9FFF;
    }

    @font-face {
        font-family: 'MyEnglishFont';
        src: url('MyEnglishFont.woff2') format('woff2'),
             url('MyEnglishFont.woff') format('woff');
        unicode-range: U+00-FF;
    }

    body {
        font-family: 'MyChineseFont', 'MyEnglishFont', serif;
    }

    ```
    在上面的代码中，'MyChineseFont'只应用在Unicode range在 U+4E00-9FFF（中文字符）的文字上，而'MyEnglishFont'只应用在Unicode range在 U+00-FF（基本的拉丁字符，包括了大部分的英文字母和一些希腊字母，等等）的文字上。

    然后，在最后的body选择器中，指定了字体列表。如果前面的字体无法在该字符上应用，就会尝试下一个字体。在这个例子中，如果一个字符不在中文的Unicode range中，那么就会尝试'MyEnglishFont'，最后如果都无法匹配，则会使用默认字体"serif"。

    注意：请替换"MyChineseFont.woff2"和"MyEnglishFont.woff2"等为你自己字体文件的URL。

    本次消耗tokens: 1063
-   前端input输入框怎么取消历史提示? > [\[HTML\]autocomplete](\[HTML]autocomplete_rrbTCQPqbJyh345WNJBB7X.md "\[HTML]autocomplete")设置浏览器的历史记录，off取消历史输入提示


-   bootstrap 绝对位置 标签 居中

    Bootstrap没有相关设置，需要CSS：
    ```sql
    <div class="parent">
      <div class="child">I am a child element</div>
      <div class="child">I am another child element</div>
    </div>
    ```
    ```sql
    .parent {
      display: flex;
      justify-content: center;
    }
    ```

