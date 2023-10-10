# \[E\&Q]React

-   \[E]A component suspended while responding to synchronous input. This will cause the UI to be replaced with a loading indicator. To fix, updates that suspend should be wrapped with startTransition.  \[[suspended](suspended_nn8qr5dxktnQ36AfNLyifo.md "suspended")[while](while_jCBSJx9dMeDsis1aKFXpPT.md "while")]
    -   翻译：一个组件在响应同步输入时挂起了，这将导致用户界面被替换为一个加载指示器。为了解决这个问题，挂起更新应该使用 "startTransition" 包装。
    -   分析：这个错误通常发生在当一个组件在响应同步输入时被挂起，而且挂起时间较长时会出现。
    -   Fix bug
        ```react&#x20;jsx
        import { startTransition } from 'react';

        function handleClick() {
          startTransition(() => {
            // 处理更新操作的代码
          });
        }

        ```
-   \[E]Line 4:29:  React Hook "React.useState" is called in function "index" that is neither a React function component nor a custom React Hook function. React component names must start with an uppercase letter. React Hook names must start with the word "use"  react-hooks/rules-of-hooks. React component names must start with an uppercase letter. React Hook names must start with the word "use"  react-hooks/rules-of-hooks \[[neither](neither_tYrhjo2C9SQ15zJHFGSXbF.md "neither")...[nor](nor_taeLLkHFdEmT19ASPqdNCk.md "nor")...]
    -   Translate & GrammaticalAnalysis

        第4行，React Hook "React.useState" 被调用在是"index"函数中，但是那既不是React组件 也不是 自定义React钩子函数。React 组件名称必须开头是大写字母。React Hook的名称在开头必须使用"use"

        主语：React Hook "React.useState" 谓语：is called 宾语：in function "index" that is neither a React function component nor a custom React Hook function.

        其中，“in function "index"”是介词短语，修饰谓语动词“is called”；“that is neither a React function component nor a custom React Hook function”是定语从句，修饰宾语“in function "index"”。
    -   BugCode
        ```react&#x20;jsx
        import React from 'react'

        export default function index() {
          const [value, setValue] = React.useState(0)
          function counter() {
            setValue(value+1)
          }
          return (
            <div>
              <div>{value}</div>
              <div>
                <button type="button" onClick={counter} className="btn border">点我+1</button>
              </div>
            </div>
          )
        }

        ```
    -   FixCode
        ```react&#x20;jsx
        import React from 'react'

        export default function Index() {
          const [value, setValue] = React.useState(0)
          function counter() {
            setValue(value+1)
          }
          return (
            <div>
              <div>{value}</div>
              <div>
                <button type="button" onClick={counter} className="btn border">点我+1</button>
              </div>
            </div>
          )
        }
        ```
-   \[E]react-dom.development.js:86 Warning: validateDOMNesting(...): \<div> cannot appear as a descendant of \<p>. \[[appear](appear_8J5WZLGvXNTbVswGam75Pq.md "appear")[descendant](descendant_mxkhzvxanaA9eWztsGRXuG.md "descendant")]

    div不能作为p标签的后代出现
-   \[E] Warning: You provided a `checked` prop to a form field without an `onChange` handler. This will render a read-only field. If the field should be mutable use `defaultChecked`. Otherwise, set either `onChange` or `readOnly`.[¶](https://www.bilibili.com/video/BV1wy4y1D7JT?t=763.6\&p=63 "¶")
    ```react&#x20;jsx
    import React, { Component } from 'react'

    export default class Bottom extends Component {
      render() {
        const {todos} = this.props
        const doneCount = todos.reduce((count, curTodo)=>{
          if (curTodo.done){
            count ++
          } 
          return count // 返回已经完成的数目
        }, 0)
        // 计算总条目
        const todosCount = todos.length
        //
        return (
          <div>
            <label htmlFor="">
               <input type="checkbox" name="" id="" checked={doneCount === todosCount} /> 
            </label>
            <span>已完成{doneCount} / 总数{todosCount} </span>
            <button>清除已完成的任务</button>
          </div>
        )
      }
    }
    ```
-   \[E]报错`babel.min.js:24 You are using the in-browser Babel transformer. Be sure to precompile your scripts for production `&#x20;

    前期暂时这样

    ![](../image/image_hqnnG4xn4j.png)

    [¶](https://www.bilibili.com/video/BV1wy4y1D7JT?t=1244.0\&p=2 "¶")


-   \[E]`[eslint] src/component/Item/Item.jsx Line 24:8:  Unexpected use of 'confirm'  no-restricted-globals`

    这个警告信息是由 `eslint` 的规则 "no-restricted-globals" 引发的，它限制了使用全局对象的一些特定方法，包括了 `confirm()` 函数。
    -   示例：添加删除todo条目的功能，并添加删除确认提示 <注意：在React中confim()需要`windom.confirm()`才能生效> \[`Array.filter()`，`.confirm()`]
        -   App 创建删除函数
            ```react&#x20;jsx
            import React, { Component } from 'react'
            // 我的组件
            import Header from './component/Header/Header'
            import List from './component/List/List'
            import Bottom from './component/Bottom/Bottom'
            // 我的CSS
            import './App.css'
            //
            export default class App extends Component {

              // 初始化状态
              state = {todos:[
                              {id: '001', name:'吃饭', done:true},
                              {id: '002', name:'睡觉', done:false},
                              {id: '003', name:'Codeing', done:false},
                              {id: '004', name:'学开飞机', done:false},
                      ]}
              // 通过props传递函数，来添加 state 中 todos 的条目
              addTodo = (todoObj) => {
                // 接收来自子组件的数据
                const {todos} = this.state
                // console.log(typeof(todos))  // 是个对象object
                const newTodos = [todoObj, ...todos]

                this.setState({todos:newTodos})
              }
              // 通过props传递函数，来修改 state 中 todos 中 done 的值
              isDone = (id, done)=>{
                // 获取原状态
                const {todos} = this.state
                // 遍历，判断每一条数据的id是否与传入的id相同，如果相同则，修改done的值为传入的done的值，否则不修改
                // 最后存入newTodos
                const newTodos = todos.map((i)=>{
                  if (i.id === id) return {...i, done:done}
                  else return i
                })
                this.setState({todos:newTodos})
              }
              // 通过props传递函数，来删除 state 中 todos 的 todo
               delTodo = (id)=>{ 
                // 获取原状态
                 const {todos} = this.state 
                // 过滤数组，删除
                // const newTodos = todos.filter((todo)=> {return todo.id !== id} )
                // this.setState({todos:newTodos})
                //// 简写上方的组数过滤
                 const newTodos = todos.filter((todo)=> todo.id !== id )
                this.setState({todos:newTodos})
              } 

              render() {
                const {todos} = this.state
                return (
                  <div>
                    <div id='totoContainer'>
                      <Header addTodo={this.addTodo}/>
                      <List todos={todos} isDone={this.isDone}  delTodo={this.delTodo} />
                      <Bottom />
                    </div>
                  </div>
                )
              }
            }
            ```
        -   List 传递删除函数给Item
            ```react&#x20;jsx
            import React, { Component } from 'react'
            import PropTypes from 'prop-types' 
            // my component
            import Item from '../Item/Item'
            //
            export default class List extends Component {
              // 限制 props 参数，从父组件中传过来的todos必须是一个数组，idDone 必须是一个函数
              static propTypes =  {
                todos:PropTypes.array.isRequired,
                isDone:PropTypes.func.isRequired,
                delTodo:PropTypes.func.isRequired
              }
              render() {
                const {todos, isDone,  delTodo } = this.props   // 通过App.jsx中定义的props 参数 todos={todos}，传递到了这里，通过解构赋值取出todos
                // console.log(typeof(todos), todos)
                return (
                  <div>
                    {
                      todos.map((todo) => {
                        return <Item key={todo.id} todo={todo} isDone={isDone}  delTodo={delTodo}  />
                        // isDone 是是通过父类App中的props传过来的，然后将它再传给Item组件实现孙子给爷爷传递数据
                      })
                    }
                  </div>
                )
              }
            }
            ```
        -   Item 调用删除函数，删除指定的todo条目
            ```react&#x20;jsx
            import React, { Component } from 'react'

            export default class Item extends Component {
              // 鼠标移入移出条目状态
              state = {mouse:false}

              // 鼠标移入移出 的回调
              handleMouse(flag){
                return ()=>{
                  this.setState({mouse:flag})
                }
              }
              // todo是否完成; 取消或勾上某个 todo 的回调
              handleCheck(id){
                return (event)=>{
                  // console.log(id, event.target.checked)
                  // 从父组件(List)的父组件(App)中传过来的props.isDone参数(函数)
                  this.props.isDone(id, event.target.checked)
                }
              }
              // 删除一条todo 的回调，这里不使用高阶函数的方式
               handleDelete(id){
                // console.log(id)  // 获取删除的条目ID
                // 进行删除确认 判断是否删除
                if(window.confirm('是否删除')){
                  this.props.delTodo(id)
                }
              } 
              //
              render() {
                const {todo} = this.props
                const ismouse = this.state.mouse
                return (
                  <div>
                    {
                      <li style={{backgroundColor:ismouse? '#ddd' : 'white'} } onMouseEnter={this.handleMouse(true)} onMouseLeave={this.handleMouse(false)}>
                        <label  htmlFor="">
                          {/* 复选框 发生改变(onChange)时，调用函数 */}
                          <input type="checkbox" onChange={this.handleCheck(todo.id)} defaultChecked={todo.done}/>
                          <span>{todo.name} </span>
                          <span>{todo.id} </span>
                          <a style={{display:ismouse?'inline':'none'}}  onClick={()=>this.handleDelete(todo.id)}  href='#123'>
                            Del
                          </a>
                        </label>
                      </li>
                    }
                  </div>
                )
              }
            }
            ```
-   \[E]Warning: Each child in a list should have a unique "key" prop. ; 关于其中的map中的index参数，如果不写将报此警告 \[`Array.map()`]
    ```react&#x20;jsx
    <div id="demo1"></div>

    <script type="text/babel">
        class List extends React.Component{
             state = {newsArray:[]} 
            componentDidMount(){
                setInterval(() => {
                    // 获取原状态
                     const {newsArray} = this.state 
                    // 模拟一条新闻
                    const news = '新闻' + (newsArray.length+1)
                    // 更新状态
                     this.setState({newsArray:[news,...newsArray]}) 
                    // console.log(newsArray)
                }, 1000);
            }
            getSnapshotBeforeUpdate(){
                // 返回当前滚动条的整体高度
                 return this.refs.list.scrollHeight 
            }
            // componentDidUpdate(preState,perProps,perSnapshot){
            //     console.log(preState,perProps,perSnapshot)
            // }
             componentDidUpdate(preState,perProps,perSnapshot){ 
                // perSnapshot 为更新前的滚动条整体高度，通过getSnapshotBeforeUpdate取值
                // this.refs.list.scrollHeight 为更新后的滚动条整体高度
                // this.refs.list.scrollTop 为更新之后，计算 当前的滚动位置
                 this.refs.list.scrollTop += this.refs.list.scrollHeight - perSnapshot 
            }
            render(){
                return(
                    <div>
                        {/* 注释
                        <div className="list list-group m-2">
                            <a href="#" className="news list-group-item list-group-item-action ">新闻2</a>
                            <a href="#" className="news list-group-item list-group-item-action ">新闻1</a>
                        </div>
                        */}
                        <div  ref='list'  className="list list-group m-2">
                            {
                                 this.state.newsArray .map((n, index)=>{  // n是状态中的数组中的每个单独的值 index是遍历之后的唯一值
                                    return <div key={index} className="news list-group-item list-group-item-action">{n}</div>
                                })
                            }
                        </div>
                    </div>
                )
            }
        }
        ReactDOM.render(<List/>, document.getElementById('demo1'))
    </script>
    ```
    在 React 中，每个组件渲染出来的多个子元素都需要有一个 `key` 属性来区分彼此。这个 `key` 属性不需要是唯一的，但它应该在这个组件的同级子元素之间是唯一的。当我们使用 `map()` 方法渲染一个列表时，我们需要在遍历的子元素中添加 `key` 属性。`key` 属性可以是数组中每个元素的唯一标识，例如它们的 ID 或索引。在这种情况下，`index` 是 `map()` 方法中回调函数的第二个参数，它是当前遍历的元素在数组中的索引值。因此，在 `map()` 方法中，我们通常会将 `key` 属性设置为 `index` 值，以确保每个子元素都有一个唯一的标识符。

    index 的值从哪里来的?
    -   `index`：当前元素在数组中的索引

        在 `map` 方法中，`index` 参数表示当前遍历到的元素在原数组中的索引位置。React 在使用 `map` 方法渲染列表时，通常需要为每个子组件设置一个 `key` 属性，这个属性的值通常设置为对应元素在数组中的索引值，这样 React 就能正确地比较新旧元素，实现高效的更新。因此，`index` 值就是数组中元素的索引位置。

