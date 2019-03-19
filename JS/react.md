# React

## Why React
- 组件复用
- 数据与DOM单向绑定
- 内部状态管理state/外部配置管理props

## React DOM

### JSX

类似XML/DOM的js和HTML混合体

```JavaScript
//{ }里写js代码    
//使用JSX
React.render(
     <div>
         <div>
             <div>content</div>
         </div>
     </div>,
     document.getElementById('example')
 );

//不使用JSX
React.render(
     React.createElement('div', null,
         React.createElement('div', null,
             React.createElement('div', null, 'content')
         )     ),
     document.getElementById('example')
);
```



### Virtual DOM

> React抽象出来的一个对象，描述dom通过这个Virtual DOM去更新真实的DOM，由这个Virtual DOM管理真实DOM的更新。
> React有个diff算法，更新Virtual DOM并不保证马上影响真实的DOM，React会等到事件循环结束，然后利用这个diff算法，通过当前新的dom表述与之前的作比较，计算出最小的步骤更新真实的DOM。


## React Component

### Component
```JavaScript
//无状态函数式组件
HelloComponent = (name) => {
   return <div>Hello {name}</div>
}

//class
class App extends React.Component {
   handleClick() {
     this.props.dispatch({ type: 'app/create' });
   }
   render() {
     return <div onClick={this.handleClick.bind(this)}>${this.props.name}</div>
   }
 }

//快被弃用的方式
React.createClass
```


### State/Props

state 是让组件控制自己的状态，props 是让外部对组件进行配置。

-   Props 属性
props 的主要作用是让使用该组件的父组件可以传入参数来配置该组件。它是外部传进来的配置参数，组件内部无法控制也无法修改。除非外部组件主动传入新的 props，否则组件的 props 永远保持不变。
propTypes 用来限制传入属性的类型
data/function props可以传数据 也可以传入方法

-   state 状态
state 的主要作用是用于组件保存、控制、修改自己的可变状态。你可以认为 state 是一个局部的、只能被组件自身控制的数据源。
state 在组件内部初始化，可以被组件自身修改，而外部不能访问也不能修改。
state 中状态可以通过 this.setState 方法进行更新，setState 会导致组件的重新渲染。
setState是一个异步法 可以通过 setState({dataName:data},()=>{})传入回调函数

## React Lifecycle

#### 创建时
-   Constructor
  - getInitialState
  - getDefaultProps

#### 挂载时
-   ComponentWillMount
-   Render
-   ComponentDidMount

#### 更新时
-   更新 props
    -   componentWillReceiveProps(props,nextProps)
    -   shouldComponentUpdate
    -   ComponentWillUpdate
    -   Render
    -   ComponentDidUpdate
-   更新 state
    - shouldComponentUpdate
    - ComponentWillUpdate
    - Render
    - ComponentDidUpdate

#### 卸载
-   componentWillUnmount
