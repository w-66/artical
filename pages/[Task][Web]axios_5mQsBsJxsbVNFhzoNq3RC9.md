# \[Task]\[Web]axios

| 标签   | 进行中 |
| ---- | --- |
| Date |     |
| 类型   |     |

-   axios从小白到入土(143m)(2h) \[[\[JS库\]axios](\[JS库]axios_3KLSyeBhEtnvZAkP4DS4aU.md "\[JS库]axios")]

    🔳⬜️⬜️⬜️⬜️⬜️⬜️⬜️⬜️⬜️ 14%
    -
    [ ]     -   \[笔记]
            -   示例：axios基础使用 \[`axios``url``method`,`then()`]
                -   基础使用
                    ```react&#x20;jsx
                    <!DOCTYPE html>
                    <html lang="en">
                    <head>
                        <meta charset="UTF-8">
                        <meta http-equiv="X-UA-Compatible" content="IE=edge">
                        <meta name="viewport" content="width=device-width, initial-scale=1.0">
                        <script src="https://cdnjs.cloudflare.com/ajax/libs/axios/1.3.6/axios.min.js" integrity="sha512-06NZg89vaTNvnFgFTqi/dJKFadQ6FIglD6Yg1HHWAUtVFFoXli9BZL4q4EO1UTKpOfCfW5ws2Z6gw49Swsilsg==" crossorigin="anonymous" referrerpolicy="no-referrer"></script>
                        <title>axios_01</title>
                    </head>
                    <body>
                        <script>
                             axios({
                                // url:'http://qwertyui.vip:22285/point_info/favormusic/',          // 请求所有
                                url:'http://qwertyui.vip:22285/point_info/favormusic/6990145295342505984/',  // 请求一项
                                method:'get'  // 请求方法，不写默认为get
                            }).then(src=>{
                                console.log(src)
                            }) 
                        </script>
                    </body>
                    </html>
                    ```
                -   示例：拼接URL请求 \[`params`[¶](https://www.bilibili.com/video/BV1QA411b7TR?t=1335.2 "¶")]

                    ![](../image/image_36U89SPY1o.png)
                    ```react&#x20;jsx
                    ```
                -

                    ![](../image/image_aH2j-fdsLq.png)
                -   示例：带参数的post请求 \[`method`]
    -   [ ] [2 2.axios的post,get请求\_Duration-27Min](https://www.bilibili.com/video/BV1QA411b7TR/?p=2 "2 2.axios的post,get请求_Duration-27Min")
    -   [ ] [3 3.axios并发请求\_Duration-8Min](https://www.bilibili.com/video/BV1QA411b7TR/?p=3 "3 3.axios并发请求_Duration-8Min")
    -   [ ] [4 4.axios全局配置\_Duration-7Min](https://www.bilibili.com/video/BV1QA411b7TR/?p=4 "4 4.axios全局配置_Duration-7Min")
    -   [x] [5 5.axios的实例\_Duration-8Min](https://www.bilibili.com/video/BV1QA411b7TR/?p=5 "5 5.axios的实例_Duration-8Min")
        -   \[笔记]


            -   示例：两个axios实例，两个不同的接口请求 \[`axios.create`[¶](https://www.bilibili.com/video/BV1QA411b7TR?t=186.5\&p=5 "¶")]

                ![](../image/image_jvzi6qzjNF.png)

                ![](../image/image_fdcyiTpR8q.png)
    -   [ ] [6 6.axios的拦截器\_Duration-18Min](https://www.bilibili.com/video/BV1QA411b7TR/?p=6 "6 6.axios的拦截器_Duration-18Min")
    -   [ ] [7 7axios在vue中的模块封装\_Duration-37Min](https://www.bilibili.com/video/BV1QA411b7TR/?p=7 "7 7axios在vue中的模块封装_Duration-37Min")
-   [ ] 尚硅谷Web前端axios入门与源码解析(237m)(3h)

    🔳🔳🔳⬜️⬜️⬜️⬜️⬜️⬜️⬜️ 28%
    -   [ ] [1 01-课程介绍\_Duration-5Min](https://www.bilibili.com/video/BV1wr4y1K7tq/?p=1 "1 01-课程介绍_Duration-5Min")
    -   [ ] [2 02-json-server的介绍与服务搭建\_Duration-5Min](https://www.bilibili.com/video/BV1wr4y1K7tq/?p=2 "2 02-json-server的介绍与服务搭建_Duration-5Min")
    -   [ ] [3 03-axios的介绍与页面配置\_Duration-4Min](https://www.bilibili.com/video/BV1wr4y1K7tq/?p=3 "3 03-axios的介绍与页面配置_Duration-4Min")
    -   [ ] [4 04-axios的基本使用\_Duration-9Min](https://www.bilibili.com/video/BV1wr4y1K7tq/?p=4 "4 04-axios的基本使用_Duration-9Min")
        -   \[笔记]
            -   示例：`data`[¶](https://www.bilibili.com/video/BV1wr4y1K7tq?t=299.8\&p=4 "¶")


    -   [x] [5 05-axios其他方式发送请求\_Duration-5Min](https://www.bilibili.com/video/BV1wr4y1K7tq/?p=5 "5 05-axios其他方式发送请求_Duration-5Min")
    -   [x] [6 06-axios请求响应结果的结构\_Duration-2Min](https://www.bilibili.com/video/BV1wr4y1K7tq/?p=6 "6 06-axios请求响应结果的结构_Duration-2Min")
    -   [x] [7 07-axios配置对象详细说明\_Duration-14Min](https://www.bilibili.com/video/BV1wr4y1K7tq/?p=7 "7 07-axios配置对象详细说明_Duration-14Min")
    -   [x] [8 08-axios的默认配置\_Duration-3Min](https://www.bilibili.com/video/BV1wr4y1K7tq/?p=8 "8 08-axios的默认配置_Duration-3Min")
    -   [x] [9 09-axios创建实例对象发送请求\_Duration-5Min](https://www.bilibili.com/video/BV1wr4y1K7tq/?p=9 "9 09-axios创建实例对象发送请求_Duration-5Min")`axios.create`
    -   [x] [10 10-axios拦截器\_Duration-13Min](https://www.bilibili.com/video/BV1wr4y1K7tq/?p=10 "10 10-axios拦截器_Duration-13Min")interceptors 拦截器
        -   \[笔记]`axios.interceptors.request.use()`[¶](https://www.bilibili.com/video/BV1wr4y1K7tq?t=202.4\&p=10 "¶")`throw`[¶](https://www.bilibili.com/video/BV1wr4y1K7tq?t=485.1\&p=10 "¶")`Promise()``reject()`,`axios.interceptors.response.use()`[¶](https://www.bilibili.com/video/BV1wr4y1K7tq?t=760.4\&p=10 "¶")
            -   演示：在定义了两个拦截器时，请求拦截器后定义的会先执行，响应拦截器则是按顺序执行[¶](https://www.bilibili.com/video/BV1wr4y1K7tq?t=609.5\&p=10 "¶")
            -   演示：在请求或响应被then或chtch处理前拦截他们，可以处理|修改config配置 \[config][¶](https://www.bilibili.com/video/BV1wr4y1K7tq?t=652.6\&p=10 "¶")

                ![](../image/image_f6LKW50WVk.png)

                000

                ![](../image/image_b6mMXaP3Uo.png)

                000

                ![](../image/image_jaxBDF9o8c.png)
            000

            ![](../image/image_tyZyrLcywl.png)

            ![](../image/image_Wv0TBbv-mn.png)

            ![](../image/image_vYDmsVLT_a.png)
    -   [ ] [11 11-axios取消请求\_Duration-8Min](https://www.bilibili.com/video/BV1wr4y1K7tq/?p=11 "11 11-axios取消请求_Duration-8Min")

        \[笔记]
        -   示例：
            ```react&#x20;jsx
            import React from 'react'
            import { Col, Row } from 'antd';
            import axios from 'axios';

            export default function TestAxios02() {
                //
                function accessLog(response) {
                    console.log('服务器响应的数据:', response.data)
                }
                function errorLog(error) {
                    console.log('错误信息:',error);
                }
                //
                function getAxios() {
                    axios.interceptors.request.use((config) => { console.log('请求拦截 成功'); return config }, (err) => { console.log(err) })
                    axios.interceptors.response.use((response) => { console.log('响应拦截 成功'); return response }, (err) => { console.log(err) })
                    axios.get('https://tenapi.cn/v2/color').then(accessLog).catch(errorLog)
                }

                return (
                    <>
                        <div>axios 拦截器</div>
                        <Row className='m-3'>
                            <Col span={6}>
                                <button onClick={getAxios}>axios.get</button>
                            </Col>
                        </Row >
                    </>
                )
            }

            ```
    -   [ ] [12 12-axios文件结构说明\_Duration-12Min](https://www.bilibili.com/video/BV1wr4y1K7tq/?p=12 "12 12-axios文件结构说明_Duration-12Min")
    -   [ ] [13 13-axios的创建过程\_Duration-15Min](https://www.bilibili.com/video/BV1wr4y1K7tq/?p=13 "13 13-axios的创建过程_Duration-15Min")
    -   [ ] [14 14-axios对象创建过程模拟实现\_Duration-13Min](https://www.bilibili.com/video/BV1wr4y1K7tq/?p=14 "14 14-axios对象创建过程模拟实现_Duration-13Min")
    -   [ ] [15 15-axios发送请求过程详解\_Duration-17Min](https://www.bilibili.com/video/BV1wr4y1K7tq/?p=15 "15 15-axios发送请求过程详解_Duration-17Min")
    -   [ ] [16 16-模拟实现axios发送请求\_Duration-19Min](https://www.bilibili.com/video/BV1wr4y1K7tq/?p=16 "16 16-模拟实现axios发送请求_Duration-19Min")
    -   [ ] [17 17-axios拦截器工作原理\_Duration-18Min](https://www.bilibili.com/video/BV1wr4y1K7tq/?p=17 "17 17-axios拦截器工作原理_Duration-18Min")
    -   [ ] [18 18-模拟实现axios拦截器功能\_Duration-19Min](https://www.bilibili.com/video/BV1wr4y1K7tq/?p=18 "18 18-模拟实现axios拦截器功能_Duration-19Min")
    -   [ ] [19 19-axios取消请求工作原理\_Duration-15Min](https://www.bilibili.com/video/BV1wr4y1K7tq/?p=19 "19 19-axios取消请求工作原理_Duration-15Min")
    -   [ ] [20 20-模拟实现axios取消请求功能\_Duration-17Min](https://www.bilibili.com/video/BV1wr4y1K7tq/?p=20 "20 20-模拟实现axios取消请求功能_Duration-17Min")
    -   [ ] [21 21-axios源码分析总结\_Duration-8Min](https://www.bilibili.com/video/BV1wr4y1K7tq/?p=21 "21 21-axios源码分析总结_Duration-8Min")

