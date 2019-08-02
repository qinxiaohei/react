### ref

> 挂到组件（有状态组件）上的ref表示对组件实例的引用
>
> 挂载到元素上时表示具体的dom元素节点
>
> 不要在render或render之前对Refs进行调用
>
> 不会通过props传递
>
> 第一种 不建议使用，有可能废弃
>
> ```javascript
> class App extends Component {
>   render() {
>     return (
>       <div>
>         登录名：<input ref='name' type="text"/>
>         <br />
>         <button onClick={this.login}>登陆</button>
>       </div>
>     );
>   }
>   login = () => {
>     console.log(this.refs.name.value)
>   };
> ```
>
> 第二种
>
> ```javascript
> class App extends Component {
>   render() {
>     return (
>       <div>
>         登录名：<input ref={ name => this.name =name} type="text"/>
>         <br />
>         <button onClick={this.login}>登陆</button>
>       </div>
>     );
>   }
>   login = () => {
>     console.log(this.name.value)
>   };
> ```
>
> 第三种
>
> ```javascript
> class App extends Component {
>   constructor() {
>     super();
>     this.login = React.createRef();
>   }
>   render() {
>     return (
>       <div>
>         登录名：<input ref={this.login} type="text" />
>         <br />
>         <button onClick={this.handleLogin}>登陆</button>
>       </div>
>     );
>   }
>  
>   handleLogin = () => {
>     console.log(this.login.current.value);
>     
>   };
> ```

### ref与无状态组件（函数组件）

> **无状态组件是不会被实例化的**,父组件中通过`ref`来获取无状态子组件时，其值为`null`
>
> 法通过`ref`来获取无状态组件实例
>
> ```javascript
> const Fun = ()=>{
>   let funRef = React.createRef()
>   function getRef(){
>     console.log(funRef.current)
>   }
>   return (
>     <div>
>     <p ref={funRef} onClick={getRef}>这是一个函数组件</p>
>   </div>
>   )
> }
> ```
>
>

### findDOMNode

> 得到实际Dom的方法
>
> 引入
>
> ```javascript
> import {findDOMNode} from 'react-dom'
> ```



### unmountComponentAtNode

```javascript
import {unmountComponentAtNode} from 'react-dom'
```





