# \[React]路由表

也就是将`Routes`组件中的属性单独拿出来，进行配置

-   `Routes`
    -   `Switch`在`@6.x.x`被`Routes`替代，完成与之相同的功能(单一匹配)，且为必须
    -   `Route`必须为`Routes`的子元素
    ***



-   \[React路由表]`children`
    -   设置嵌套路由(子路由)



-   示例：修改Routers、Route组件为路由表的形式 \[`Routes``Route`,`useRoutes`,[\[参考\]React Router V6 官方路由身份验证示例](<\[参考]React Router V6 官方路由身份验证示例_ujFYeadereNk5tnhhbFwJP.md> "\[参考]React Router V6 官方路由身份验证示例")]

    ![](../image/image_zPxVWuEz7h.png)
    -   使用Routers、Route组件
        -   src/components/Demo/TestAuth/Public.jsx
            ```react&#x20;jsx
            import React from 'react'

            export default function Public() {
              return (
                <div>
                  <h3>Public 公共页</h3>
                </div>
              )
            }

            ```
        -   src/components/Demo/TestAuth/Protected.jsx
            ```react&#x20;jsx
            import React from 'react'

            export default function Protected() {
              return (
                <div>
                  <h3>Protected 限制验证页</h3>
                </div>
              )
            }

            ```
        -   src/components/Demo/TestAuth/Layout.jsx
            ```react&#x20;jsx
            import React from 'react'
            import { Link, Outlet } from 'react-router-dom'
            import AuthStatus from './AuthStatus'

            export default function Layout() {
              return (
                <div>
                  <AuthStatus />
                  <p>Layout 页面</p>
                  <ul>
                    <li>
                      <Link to={'/'}>Public 公共页</Link>
                    </li>
                    <li>
                      <Link to={'/protected'}>Protected 限制验证页</Link>
                    </li>
                  </ul>
                  <br />
                  <hr />
                  <Outlet />
                </div>
              )
            }

            ```
        -   src/components/Demo/TestAuth/AuthProvider.jsx
            ```react&#x20;jsx
            // 路由全局接收 <AuthProvider> 路由拦截组件属性
            import React, { useState } from 'react'
            import { fakeAuthProvider } from './auth'

            // 验证上下文空间
            let AuthContext = React.createContext()

            // 利用useContext导出验证上下文，供其它组件使用
            export function useAuth() {
              return React.useContext(AuthContext)
            }

            // 验证提供者
            export default function AuthProvider({ children }) {
              // 创建验证组件状态
              let [user, setUser] = useState(null)

              // 登录验证
              let signin = (newUser, callback) => {
                return fakeAuthProvider.signin(() => {
                  setUser(newUser)
                  callback()
                })
              }

              // 退出登录
              let signout = (callback) => {
                return fakeAuthProvider.signout(() => {
                  setUser(null)
                  callback()
                })
              }

              let value = { user, signin, signout }

              // 传递验证上下文(AuthContext)属性给嵌套的插槽children子组件(App)
              return <AuthContext.Provider value={value}>{children}</AuthContext.Provider>
            }

            ```
        -   src/components/Demo/TestAuth/auth.js
            ```react&#x20;jsx
            const fakeAuthProvider = {
                isAuthenticated: false,
              
                signin(callback) {
                  fakeAuthProvider.isAuthenticated = true
                  setTimeout(callback, 100) // 模拟异步登录，执行回调函数
                },
              
                signout(callback) {
                  fakeAuthProvider.isAuthenticated = false
                  setTimeout(callback, 100) // 模拟异步退出，执行回调函数
                },
              }
              
              export { fakeAuthProvider }
              
            ```
        -   src/components/Demo/TestAuth/Login.jsx
            ```react&#x20;jsx
            // import React from 'react'

            // export default function Login() {
            //   return <div>Login</div>
            // }


            import React from 'react'
            import { useLocation, useNavigate } from 'react-router-dom'
            import { useAuth } from './AuthProvider'

            export default function LoginPage() {
              let navigate = useNavigate()
              let location = useLocation()
              let auth = useAuth() // 导入验证上下文属性
              
              // 获取URL来路，/ or /protected
              //// location.state.from.pathname存在，则将其赋值给from变量，否则将'/'赋值给from变量。
              let from = location.state?.from?.pathname || '/'
              function handleSubmit(event) {
                event.preventDefault() // 阻止元素发生默认的行为

                let formData = new FormData(event.currentTarget) // 获取FormData对象
                let username = formData.get('username').toString() // 获取username数据

                // 模拟登陆验证，传递登录回调函数给 AuthProvider
                auth.signin(username, () => {
                  navigate(from, { replace: true })
                })
              }

              return (
                <div>
                  <h3>必须登录才能访问路由地址: {from}</h3>
                  <form onSubmit={handleSubmit}>
                    <label>
                      用户名: <input type='text' name='username' />{' '}
                      <button type='submit'>Login</button>
                    </label>
                  </form>
                </div>
              )
            }

            ```
        -   src/components/Demo/TestAuth/RequireAuth.jsx
            ```react&#x20;jsx
            // 请求验证路由拦截组件
            // 未登陆的请求利用 <Navigate> 导航组件进行重定向

            import React from 'react'
            import { Navigate, useLocation } from 'react-router-dom'
            import { useAuth } from './AuthProvider' // 引入验证上下文

            export default function RequireAuth({ children }) {
              let auth = useAuth() // 获取验证对象
              let location = useLocation() // 获取URL参数

              if (!auth.user) {
                // 未登入，使用Navigate组件重定向到登录页，传入state属性以保存当前URL位置信息
                return <Navigate to='/login' state={{ from: location }} replace />
              }

              return children // 验证通过，返回插槽内容，例如： ProtectedPage 页面(显示页面)
            }

            ```
        -   src/components/Demo/TestAuth/AuthStatus.jsx
            ```react&#x20;jsx
            import React from 'react'
            import { useNavigate } from 'react-router-dom'
            import { useAuth } from './AuthProvider'

            export default function AuthStatus() {
              let auth = useAuth()
              let navigate = useNavigate()

              if (!auth.user) {
                return <p>您还没有登录.</p>
              }
              return (
                <p>
                  欢迎 {auth.user}!{' '}
                  <button
                    onClick={() => {
                      auth.signout(() => navigate('/'))
                    }}
                  >
                    退出
                  </button>
                </p>
              )
            }

            ```
        -   src/App.js
            ```react&#x20;jsx
            // // // 2023_06_02
            // // 测试 Auth
            // 引入router
            import { Route, Routes } from 'react-router-dom'
            // 引入两个页面
            import Protected from './components/Demo/TestAuth/Protected'
            import Public from './components/Demo/TestAuth/Public'
            // 
            import AuthProvider from './components/Demo/TestAuth/AuthProvider'
            import Layout from './components/Demo/TestAuth/Layout'
            import RequireAuth from './components/Demo/TestAuth/RequireAuth'
            //
            import Login from './components/Demo/TestAuth/Login'

            //
            function App() {
              return (
                 <AuthProvider>
                  <h2>React Router V6 官方路由身份验证示例</h2>
                  <Routes>
                    <Route element={<Layout />}>                       {/* 在导航组件中 包裹 子页面 */}
                      <Route path='/'          element={<Public />} /> {/* 公共的页面 映射根路由 */}
                      <Route path='/login' element={<Login />} />      {/* 登录页面 */}
                      <Route path='/protected' element={            // {/* 受保护的页面 */}/>
                                                          <RequireAuth>
                                                            <Protected />
                                                          </RequireAuth>
                                                        }
                      />
                    </Route>                                           {/* 导航组件 结尾 */}
                  </Routes>
                </AuthProvider> 
              )
            }
            export default App
            ```
    -   修改为路由表的形式
        -   src/App.js
            ```react&#x20;jsx
            import AuthProvider from './components/Demo/TestAuth/AuthProvider'
            //
            // 导入路由表
             import routes from './components/Demo/TestAuth/routers' 
             import { useRoutes } from 'react-router-dom' 
            function App() {
              // 使用路由表
               const element = useRoutes(routes) 
              return (
                <AuthProvider>
                  <h2>React Router V6 官方路由身份验证示例</h2>
                   {element} 
                </AuthProvider>
              )
            }

            export default App
            ```
        -   src/components/Demo/TestAuth/routers.js
            ```react&#x20;jsx
            import Protected from './Protected'
            import Public from './Public'
            //
            import Login from './Login'
            import Layout from './Layout'
            //
            import RequireAuth from './RequireAuth'
            //
            const routers = [
                {
                    element: <Layout />,
                    children: [
                        {
                            path: '/',
                            element: <Public />
                        },
                         {
                            path: 'protected/',
                            element:
                                <RequireAuth>
                                    <Protected />
                                </RequireAuth>
                        }, 
                        {
                            path: 'login/',
                            element: <Login />
                        }
                    ]
                },

            ]

            export default routers
            ```
