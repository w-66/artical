# \[React]路由

[\[JS库\]react-route-dom](\[JS库]react-route-dom_jGUgd2TkFiY94rBUA6txun.md "\[JS库]react-route-dom")`@5.3.4`

## [\[JS库\]react-route-dom](\[JS库]react-route-dom_jGUgd2TkFiY94rBUA6txun.md "\[JS库]react-route-dom")`@5.3.4`

#### 路由的懒加载lazyLoad|懒加载

-   问题：在默认情况下，路由的所有页面都会被在第一次访问时全部加载

***

1.  `lazy()`
    1.  `lazy()`React中的方法
2.  `Suspense`
    1.  `Suspense`React中的组件，用于对加载路由页面时，显示的页面[🖼️ 图片](../image/image_CT4nFcyjaU.png "🖼️ 图片")
    -   `fallback`
        -   加载时的部份页面

## [\[JS库\]react-route-dom](\[JS库]react-route-dom_jGUgd2TkFiY94rBUA6txun.md "\[JS库]react-route-dom")`@6.x.x`

[\[React\]路由表](\[React]路由表_hEc27DZ9mNpXhtJ6jQf6HJ.md "\[React]路由表")

-   路由组件传参





## 示例

-   示例：使用路由表 \[[\[JS库\]react-route-dom](\[JS库]react-route-dom_jGUgd2TkFiY94rBUA6txun.md "\[JS库]react-route-dom")]
    -   1、src/routes/routes.jsx 创建路由表&#x20;
        ```react&#x20;jsx
        //
        import Home from '../pages/Home'
        //
        const routes = [
            {
                path: '/',
                element: <Home />
            },
        ]
        export default routes
        ```
    -   2、src/App.jsx 引入路由表
        ```react&#x20;jsx
        //
        import React, {  Suspense  } from 'react'
        //
        import {  useRoutes  } from 'react-router-dom'
        // 导入路由表
         import routes from './routes/routes' 
        //
        export default function App() {
          // 使用路由表
           const element = useRoutes(routes) 
          return (
            ...
             <Suspense fallback={<Spin delay={500} />}>  {/*懒加载 loading动画设置*/}
              {element}
            </Suspense> 
          )
        ```
    -   3、src/index.js Route组件需要在Router组件上下文中
        ```react&#x20;jsx
        //
        import { BrowserRouter } from "react-router-dom";
        // 导入App组件
        import App from './App';
        //
        const root = ReactDOM.createRoot(document.getElementById('root'));
        root.render(
            <>
            <BrowserRouter>
                <App />
            </BrowserRouter>
            </>
            
        );

        ```

-   登录验证

    [\[参考\]React Router V6 官方路由身份验证示例](<\[参考]React Router V6 官方路由身份验证示例_ujFYeadereNk5tnhhbFwJP.md> "\[参考]React Router V6 官方路由身份验证示例")
    -   [https://juejin.cn/post/7195572628958167095](https://juejin.cn/post/7195572628958167095 "https://juejin.cn/post/7195572628958167095")
    -   [https://juejin.cn/post/7071086182116884487](https://juejin.cn/post/7071086182116884487 "https://juejin.cn/post/7071086182116884487")
