# \[Web]jquery

[https://jquery.com/download/](https://jquery.com/download/ "https://jquery.com/download/")

[https://cdnjs.com/libraries/jquery](https://cdnjs.com/libraries/jquery "https://cdnjs.com/libraries/jquery")

***

-   示例：导入juqery并测试
    ```python
    {%load static%}

    <!DOCTYPE html>
    <html lang="en">
    <head>
        <meta charset="UTF-8">
        <meta http-equiv="X-UA-Compatible" content="IE=edge">
        <meta name="viewport" content="width=device-width, initial-scale=1.0">
        <title>Document</title>
        <!-- <script src="https://cdnjs.cloudflare.com/ajax/libs/jquery/3.6.3/jquery.min.js" ></script> -->
        <!-- <script src={%static 'jquery-3.6.3/jquery.min.js'%}></script> -->
        <script src={%static 'jquery-3.5.1/jquery.min.js'%}></script>
    </head>
    <body>
        <script>
            console.log($)
        </script>
    </body>
    </html>

    ```
    ![](../image/image_hicS4K_xgH.png)

***

基于[JavaScript](JavaScript_w7M7UmgSNLmfSHDWMLjuEi.md "JavaScript")，主要用于操作[\[Web\]DOM](\[Web]DOM_hA1J7qvXNRdJxg7CoGu7X.md "\[Web]DOM");

特殊标签

`window`



1.  `$()`
2.  `$().method();`
3.  `$().css();`
4.  `$().attr();`
5.  .prop()

CSS方法

1.  `$().height();`
2.  `$().resize();`

<!---->

1.  `$()`获取节点
2.  `$().method();`操作节点
3.  `$().css();`设置元素
4.  `$().attr();`设置属性



1.  `$().height();`设置标签高度
2.  `$().resize();`对浏览器窗口调整大小进行计数;监控对象的大小





1.  `outerHeight()`

    \$(*selector*).outerHeight(*includeMargin*)返回元素的宽度（包含 padding 和 border）[¶](https://www.runoob.com/jquery/html-outerwidth.html "¶")
    -   *includeMargin*
        -   可选
        -   *false* - 默认。不包含 margin。
        -   *true* - 包含 margin。
2.  [width()](https://www.runoob.com/jquery/css-width.html "width()") - 设置或返回元素的宽度
3.  [height()](https://www.runoob.com/jquery/css-height.html "height()") - 设置或返回元素的高度
4.  [innerWidth()](https://www.runoob.com/jquery/html-innerwidth.html "innerWidth()") - 返回元素的宽度（包含 padding）
5.  [innerHeight()](https://www.runoob.com/jquery/html-innerheight.html "innerHeight()") - 返回元素的高度（包含 padding）





-   示例`$().attr();`.prop()
    ```javascript
    $("div").attr({
      "class": "example",
      "data-name": "John"
    });
    以上代码将设置 <div> 元素的 class 属性为 "example"，data-name 属性为 "John"。

    如果要在 HTML 元素上添加新的属性，可以使用 prop() 方法，例如：
    $("input[type='text']").prop("disabled", true);

    ```
-   示例：通过[AJAX](AJAX_wHuD3kDmRw9xCz51ifFezV.md "AJAX")发送异步http请求&#x20;

    在 jQuery 中，可以使用 `$.ajax()` 方法发送异步 HTTP（Ajax）请求。

    其中 `url` 指定请求的 URL，`type` 指定请求的方法（GET 或 POST），`data` 指定请求发送的数据，`success` 和 `error` 是请求成功和失败后的回调函数。在请求成功时，`success` 回调函数会被调用，并且 `response` 参数包含了响应的数据。在请求失败时，`error` 回调函数会被调用，并且 `xhr` 参数包含了一个 XMLHttpRequest 对象，`status` 参数包含了错误的状态码，`error` 参数包含了错误的信息
    ```python
    $.ajax({
        url: "example.php",
        type: "POST",
        data: { name: "John", location: "Boston" },
        success: function(response){
            console.log(response);
        },
        error: function(xhr, status, error){
            console.log(xhr.responseText);
        }
    });
    ```
-   示例：通过jquery获取标签高度，设置标签高度 \[`outerHeight()`,`$().height();`,`$().resize();`,`window`]
    ```javascript
    <script>
        // 调用设置高度的函数
        setTopUnit2Height()

        // 通过jquery获取 高度 来设置首页下方图标的位置为首图的底部位置
        function setTopUnit2Height(){
            var topunit1=$("#topunit1");
            var topunit1Height = (topunit1.outerHeight(true));
            console.log(topunit1Height)

            var topimgHeight=$("#topimg");
            var topimgHeight1 = (topimgHeight.outerHeight(true));
            console.log(topimgHeight1)
            var topunit2Height = topimgHeight1 - topunit1Height
            console.log(topunit2Height)
            addHeightForTopUnit2()
            // 设置标签高度
            function addHeightForTopUnit2(){
                // var h=$('#topunit2')
                $('#topunit2').height(topunit2Height-10);
            }
        };

        $(window).resize( function  () {
            // 当网页变化时，调用函数修改#topunit2的高度
            setTopUnit2Height()
        });

    </script>
    ```

    ```javascript
    <!-- 首图 -->
    <section id="topimg" class="vh-100 spotlight parallax bg-cover bg-size--cover" data-spotlight="fullscreen">
        <span class="mask bg-primary alpha-7 "></span>
        <div class="spotlight-holder py-lg pt-lg-xl" style="height: 588px;">
            <div class="container d-flex align-items-center no-padding" id="topunit1">
                <div class="col">
                    <div class="row cols-xs-space align-items-center text-center text-md-left justify-content-center">
                        <div class="col-7">
                            <div class="text-center mt-5">
                                <img src="{% static 'img/w-logo.svg' %}" style="width: 200px;" class="img-fluid animated"
                                    data-animation-in="jackInTheBox" data-animation-delay="1000">
                                <h2 class="heading display-4 font-weight-400 text-white mt-5 animated"
                                    data-animation-in="fadeInUp" data-animation-delay="2000">
                                    <span class="font-weight-700 text-info">Qusay</span> Site
                                </h2>
                                <p class="lead text-white mt-3 lh-180 c-white animated" data-animation-in="fadeInUp"
                                    data-animation-delay="2500">
                                    welcome <strong class="text-primary"">(๑‾ ꇴ ‾๑)</strong>
                                </p>
                            </div>
                        </div>
                    </div>
                </div>
            </div>
            <!-- 首图下部份内容 -->
             <div class="container  d-flex align-items-end justify-content-center" id="topunit2">
                    <!-- 图标1 -->
                        <div class="row mb-5 justify-content-between w-20">
                            <div class="d-flex">
                                <button class="continue-application  col-sm-6 m-1">
                                    <div>
                                        <div class="pencil"></div>
                                        <div class="folder">
                                            <div class="top">
                                                <svg viewBox="0 0 24 27">
                                                    <path
                                                        d="M1,0 L23,0 C23.5522847,-1.01453063e-16 24,0.44771525 24,1 L24,8.17157288 C24,8.70200585 23.7892863,9.21071368 23.4142136,9.58578644 L20.5857864,12.4142136 C20.2107137,12.7892863 20,13.2979941 20,13.8284271 L20,26 C20,26.5522847 19.5522847,27 19,27 L1,27 C0.44771525,27 6.76353751e-17,26.5522847 0,26 L0,1 C-6.76353751e-17,0.44771525 0.44771525,1.01453063e-16 1,0 Z">
                                                    </path>
                                                </svg>
                                            </div>
                                            <div class="paper"></div>
                                        </div>
                                    </div>
                                    Write
                                </button>
                                <button class="continue-application col-sm-6 m-1">
                                    <div>
                                        <div class="pencil"></div>
                                        <div class="folder">
                                            <div class="top">
                                                <svg viewBox="0 0 24 27">
                                                    <path
                                                        d="M1,0 L23,0 C23.5522847,-1.01453063e-16 24,0.44771525 24,1 L24,8.17157288 C24,8.70200585 23.7892863,9.21071368 23.4142136,9.58578644 L20.5857864,12.4142136 C20.2107137,12.7892863 20,13.2979941 20,13.8284271 L20,26 C20,26.5522847 19.5522847,27 19,27 L1,27 C0.44771525,27 6.76353751e-17,26.5522847 0,26 L0,1 C-6.76353751e-17,0.44771525 0.44771525,1.01453063e-16 1,0 Z">
                                                    </path>
                                                </svg>
                                            </div>
                                            <div class="paper"></div>
                                        </div>
                                    </div>
                                    read
                                </button>
                        </div>
                    </div>

              </div> 
        </div>
    </section>
    ```
