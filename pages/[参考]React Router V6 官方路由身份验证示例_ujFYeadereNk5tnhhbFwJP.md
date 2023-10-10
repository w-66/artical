# \[参考]React Router V6 官方路由身份验证示例

-   [https://juejin.cn/post/7075948824845352990](https://juejin.cn/post/7075948824845352990 "https://juejin.cn/post/7075948824845352990")
-   Login.jsx  \[`useLoaction``useNavigate`,`?.`₁₉,]
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
