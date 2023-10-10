# \[React]create-react-app(脚手架)

create-react-app是一个由Facebook团队维护的官方React应用程序脚手架工具，用于快速创建基于React的单页面应用（[SPA](SPA_dRpTki5ypsK6niwgePfbz9.md "SPA")）。它提供了一个现代化的React开发环境，包括预配置的开发服务器、构建工具、自动化的开发工作流以及一些常见的React开发依赖。使用create-react-app可以快速初始化一个新的React项目，无需手动配置和安装多个工具，可以更加专注于React应用的开发而不必花费过多精力在构建和配置开发环境上。create-react-app还提供了一些额外的特性，如热模块替换（HMR）、代码分割（Code Splitting）和生产构建等，使得React应用的开发和部署更加便捷和高效。

***

## 安装

-   在Linux(Ubuntu)中安装
    -   示例：安装[\[React\]create-react-app(脚手架)](\[React]create-react-app\(脚手架\)_iKRevG9qrfgg38wTCrMLDx.md "\[React]create-react-app(脚手架)") \[[npm](npm_6L2ASmevicELg4gRE57X4j.md "npm")`npm start`,Linux]
        -   Linux(Ubuntu)安装npm
            -   apt-get update & apt-get install -y npm
            -   下载并执行 NodeSource 安装脚本：`curl -sL https://deb.nodesource.com/setup_14.x | sudo -E bash -`
                -   之后就可以下载14版本的node
                    ```react&#x20;jsx
                    apt install nodejs
                    ```
        -   安装create-react-app
            ```react&#x20;jsx
            root@59f6c9bea13b:/www# npm install -g create-react-app
            npm WARN deprecated tar@2.2.2: This version of tar is no longer supported, and will not receive security updates. Please upgrade asap.
            /usr/local/bin/create-react-app -> /usr/local/lib/node_modules/create-react-app/index.js
            npm WARN notsup Unsupported engine for create-react-app@5.0.1: wanted: {"node":">=14"} (current: {"node":"10.19.0","npm":"6.14.4"})
            npm WARN notsup Not compatible with your version of node/npm: create-react-app@5.0.1
            npm WARN notsup Unsupported engine for fs-extra@10.1.0: wanted: {"node":">=12"} (current: {"node":"10.19.0","npm":"6.14.4"})
            npm WARN notsup Not compatible with your version of node/npm: fs-extra@10.1.0

            + create-react-app@5.0.1
            added 67 packages from 27 contributors in 19.649s
            ```
        -   创建项目 `create-react-app react_app`
            ```react&#x20;jsx
            root@59f6c9bea13b:/www# create-react-app react_app

            Creating a new React app in /www/react_app.

            Installing packages. This might take a couple of minutes.
            Installing react, react-dom, and react-scripts with cra-template...


            > core-js@3.30.1 postinstall /www/react_app/node_modules/core-js
            > node -e "try{require('./postinstall')}catch(e){}"


            > core-js-pure@3.30.1 postinstall /www/react_app/node_modules/core-js-pure
            > node -e "try{require('./postinstall')}catch(e){}"

            + cra-template@1.2.0
            + react-scripts@5.0.1
            + react@18.2.0
            + react-dom@18.2.0
            added 1434 packages from 627 contributors in 809.752s

            234 packages are looking for funding
              run `npm fund` for details


            Initialized a git repository.

            Installing template dependencies using npm...
            npm WARN @apideck/better-ajv-errors@0.3.6 requires a peer of ajv@>=8 but none is installed. You must install peer dependencies yourself.
            npm WARN fork-ts-checker-webpack-plugin@6.5.3 requires a peer of typescript@>= 2.7 but none is installed. You must install peer dependencies yourself.
            npm WARN tsutils@3.21.0 requires a peer of typescript@>=2.8.0 || >= 3.2.0-dev || >= 3.3.0-dev || >= 3.4.0-dev || >= 3.5.0-dev || >= 3.6.0-dev || >= 3.6.0-beta || >= 3.7.0-dev || >= 3.7.0-beta but none is installed. You must install peer dependencies yourself.
            npm WARN optional SKIPPING OPTIONAL DEPENDENCY: fsevents@2.3.2 (node_modules/fsevents):
            npm WARN notsup SKIPPING OPTIONAL DEPENDENCY: Unsupported platform for fsevents@2.3.2: wanted {"os":"darwin","arch":"any"} (current: {"os":"linux","arch":"x64"})

            + web-vitals@2.1.4
            + @testing-library/jest-dom@5.16.5
            + @testing-library/react@13.4.0
            + @testing-library/user-event@13.5.0
            added 55 packages from 81 contributors in 57.666s

            234 packages are looking for funding
              run `npm fund` for details

            Removing template package using npm...

            npm WARN @apideck/better-ajv-errors@0.3.6 requires a peer of ajv@>=8 but none is installed. You must install peer dependencies yourself.
            npm WARN fork-ts-checker-webpack-plugin@6.5.3 requires a peer of typescript@>= 2.7 but none is installed. You must install peer dependencies yourself.
            npm WARN tsutils@3.21.0 requires a peer of typescript@>=2.8.0 || >= 3.2.0-dev || >= 3.3.0-dev || >= 3.4.0-dev || >= 3.5.0-dev || >= 3.6.0-dev || >= 3.6.0-beta || >= 3.7.0-dev || >= 3.7.0-beta but none is installed. You must install peer dependencies yourself.
            npm WARN optional SKIPPING OPTIONAL DEPENDENCY: fsevents@2.3.2 (node_modules/fsevents):
            npm WARN notsup SKIPPING OPTIONAL DEPENDENCY: Unsupported platform for fsevents@2.3.2: wanted {"os":"darwin","arch":"any"} (current: {"os":"linux","arch":"x64"})

            removed 1 package and audited 1489 packages in 30.359s

            234 packages are looking for funding
              run `npm fund` for details

            found 1 high severity vulnerability
              run `npm audit fix` to fix them, or `npm audit` for details

            Created git commit.

            Success! Created react_app at /www/react_app
            Inside that directory, you can run several commands:

              npm start
                Starts the development server.

              npm run build
                Bundles the app into static files for production.

              npm test
                Starts the test runner.

              npm run eject
                Removes this tool and copies build dependencies, configuration files
                and scripts into the app directory. If you do this, you can’t go back!

            We suggest that you begin by typing:

              cd react_app
              npm start

            Happy hacking!
            ```
        -   启动 `npm start`
            ```react&#x20;jsx
            Compiled successfully!

            You can now view react_app in the browser.

              Local:            http://localhost:3000
              On Your Network:  http://10.0.3.3:3000

            Note that the development build is not optimized.
            To create a production build, use npm run build.

            webpack compiled successfully

            ```

    -   示例：安装[\[React\]create-react-app(脚手架)](\[React]create-react-app\(脚手架\)_iKRevG9qrfgg38wTCrMLDx.md "\[React]create-react-app(脚手架)") \[[npm](npm_6L2ASmevicELg4gRE57X4j.md "npm")`npm start`,Windows]
        -   创建项目 `npm create-react-app helia-examples`



## 创建项目中文件解析

`./node_modules/`依赖

`./public/`静态资源文件夹，页面的根路径 \[%PUBLIC\_URL%]

[index.html](index.html_oXFx66fQXLz7A9RnU9pr87.md "index.html")初始页，且只需要一个页面; [SPA](SPA_dRpTki5ypsK6niwgePfbz9.md "SPA")

`./src/`源码文件夹

[App.js](App.js_smsVFfHWYrYu6vAuTn3Ks.md "App.js") React app 组件

[index.js](index.js_6jYd8AoBx9reoEKZN96D5o.md "index.js") [Webpack](Webpack_6tozYheuLN7uJtWbcWkoXJ.md "Webpack")入口文件

[reportWebVitals.js](reportWebVitals.js_6U54hsu8J7S4QuaCdq7QVi.md "reportWebVitals.js")记录页面性能

[setupTests.js](setupTests.js_mtEGph5ptzZivnqguhYWi1.md "setupTests.js")组件测试

[setupProxy.js](setupProxy.js_uhNfFMw6QZ2A5BQokWtCtM.md "setupProxy.js")设置多个代理，解决[CORS](CORS_hk5DR43g1YhbKADigy2VLv.md "CORS")

[./package.json](--package.json_5XzrB1BD9kJ9xyQ72pXvy9.md "./package.json")添加代理

`./README.md`

`./package-lock.json`

`./node_modules/`

`./public/`

[index.html](index.html_oXFx66fQXLz7A9RnU9pr87.md "index.html")

`./src/`

[App.js](App.js_smsVFfHWYrYu6vAuTn3Ks.md "App.js")

[index.js](index.js_6jYd8AoBx9reoEKZN96D5o.md "index.js")

[reportWebVitals.js](reportWebVitals.js_6U54hsu8J7S4QuaCdq7QVi.md "reportWebVitals.js")

[setupTests.js](setupTests.js_mtEGph5ptzZivnqguhYWi1.md "setupTests.js")

[setupProxy.js](setupProxy.js_uhNfFMw6QZ2A5BQokWtCtM.md "setupProxy.js")

[./package.json](--package.json_5XzrB1BD9kJ9xyQ72pXvy9.md "./package.json")

`./README.md`

`./package-lock.json`

暴露webpack之后的文件 \[`npm run eject`]

`./config/`[🖼️ 图片](../image/image_Dvdtla2-uq.png "🖼️ 图片")

`./scripts/`[🖼️ 图片](../image/image_pTNNZVqmdv.png "🖼️ 图片")[🖼️ 图片](../image/image_gEFf-jcaKp.png "🖼️ 图片")

[./package.json](--package.json_5XzrB1BD9kJ9xyQ72pXvy9.md "./package.json")修改了[🖼️ 图片](../image/image_tb2FKI2GWy.png "🖼️ 图片")



执行顺序：[index.js](index.js_6jYd8AoBx9reoEKZN96D5o.md "index.js")>[index.html](index.html_oXFx66fQXLz7A9RnU9pr87.md "index.html")>[App.js](App.js_smsVFfHWYrYu6vAuTn3Ks.md "App.js")

## 样式模块化

-   \[笔记]样式模块化
    -   因为不同组件之间之间import CSS文件会导致相同选择器的相互冲突，所以...
    -   示例：
        -   1、修改组件中的CSS文件为\*.module.css

            ![](../image/image_c6nPk6ICan.png)
        -   2、导入CSS

            ![](../image/image_vDepWPYGln.png)

## 编码流程(过程)



## 碎片

-   处理跨域

[SPA](SPA_dRpTki5ypsK6niwgePfbz9.md "SPA")

-   示例：配置导入的根路径为@ ，前提是暴露了webpack \[`npm run eject`]
    ```python
              'react-dom$': 'react-dom/profiling',
              'scheduler/tracing': 'scheduler/tracing-profiling',
            }),
            ...(modules.webpackAliases || {}),
             '@': path.join(__dirname, '..', 'src'), 
          },
    ```

