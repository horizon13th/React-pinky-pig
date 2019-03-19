# React
## React DOM
### JSX
> 类似XML/DOM的js和HTML混合体
> #使用JSX
> React.render(
>     <div>
>         <div>
>             <div>content</div>
>         </div>
>     </div>,
>     document.getElementById('example')
> );
> 
> #不使用JSX
> React.render(
>     React.createElement('div', null,
>         React.createElement('div', null,
>             React.createElement('div', null, 'content')
>         )
>     ),
>     document.getElementById('example')
> );

* { }里写js代码
### CSS
* className
* classNames
* bem命名
* > Block（模块）、Element（元素）、Modifier（修饰符）。
* > bb__ee--mm
* > form__submit--disabled

### Virtual DOM
> React抽象出来的一个对象，描述dom通过这个Virtual DOM去更新真实的DOM，由这个Virtual DOM管理真实DOM的更新。
> React有个diff算法，更新Virtual DOM并不保证马上影响真实的DOM，React会等到事件循环结束，然后利用这个diff算法，通过当前新的dom表述与之前的作比较，计算出最小的步骤更新真实的DOM。
> 
> 作者：RK_CODER
> 链接：https://www.jianshu.com/p/ae482813b791
> 來源：简书
> 简书著作权归作者所有，任何形式的转载都请联系作者获得授权并注明出处。

## React Component
### Component
* 无状态函数式组件
* > HelloComponent = (name) => {
* >   return <div>Hello {name}</div>
* > }

* class
* > class App extends React.Component {
* >   handleClick() {
* >     this.props.dispatch({ type: 'app/create' });
* >   }
* >   render() {
* >     return <div onClick={this.handleClick.bind(this)}>${this.props.name}</div>
* >   }
* > }

* React.createClass
* > getInitialState
* > this指向问题
* > mixins
* > propTypes
* > -----
* > 快被弃用了

### State/Props
> state 是让组件控制自己的状态，props 是让外部对组件进行配置。

* Props 属性
* > props 的主要作用是让使用该组件的父组件可以传入参数来配置该组件。它是外部传进来的配置参数，组件内部无法控制也无法修改。除非外部组件主动传入新的 props，否则组件的 props 永远保持不变。

    * propTypes
    * data/function
* state 状态
* > state 的主要作用是用于组件保存、控制、修改自己的可变状态。你可以认为 state 是一个局部的、只能被组件自身控制的数据源。
* > state 在组件内部初始化，可以被组件自身修改，而外部不能访问也不能修改。
* > state 中状态可以通过 this.setState 方法进行更新，setState 会导致组件的重新渲染。

    * setState
     * > 异步
     * > setState({dataName:data},()=>{})

## React Lifecycle
### 创建时
* constructor
    * getInitialState
    * getDefaultProps
### 挂载时
* ComponentWillMount
* Render
* ComponentDidMount
### 更新时
* props
    * componentWillReceiveProps(props,nextProps)
    * shouldComponentUpdate
    * ComponentWillUpdate
    * Render
    * ComponentDidUpdate
* state
    * shouldComponentUpdate
    * ComponentWillUpdate
    * Render
    * ComponentDidUpdate
### 卸载
* componentWillUnmount
## Redux
## JavaScript (ES 6)
### 变量声明 
* const 常量
* let 变量
### 模板字符串
> //Before
> console.log("Hi,"+firstName+" "+lastName);
> //ES 6
> console.log(`Hi,${firstName} ${lastName}`);
> ```

### 默认参数
> function foo(firstName="Amy", lastName="Green"){
>     console.log(`Name: ${firstName} ${lastName}');
> }

### 箭头函数
> //function
> var nameFunc = function(name){
>     return 'My name is ${name}'
> }
> //arrow function
> var nameFunc = (name) => 'My name is ${name}'

### 对象操作 Object
* Destructuring assignment 解构赋值
* > // 对象
* > const user = { name: 'guanguan', age: 2 };
* > const { name, age } = user;
* > console.log(`${name} : ${age}`);  // guanguan : 2
* > 
* > // 数组
* > const arr = [1, 2];
* > const [foo, bar] = arr;
* > console.log(foo);  // 1

* Object initializer 对象字面量改进
* > const name = 'duoduo';
* > const age = 8;
* > 
* > const user = { name, age };

* Spread Operator ...
* > 可用于组装数组。
* > 
* > const todos = ['Learn dva'];
* > [...todos, 'Learn antd'];  // ['Learn dva', 'Learn antd']
* > 也可用于获取数组的部分项。
* > 
* > const arr = ['a', 'b', 'c'];
* > const [first, ...rest] = arr;
* > rest;  // ['b', 'c']
* > 
* > // With ignore
* > const [first, , ...rest] = arr;
* > rest;  // ['c']

### Import/Export
### 异步语法糖
* async/await
* > async () => {
* > 	await http.get("/api/getAll")
* >    //promise对象
* > 	...看似同步 实际是异步操作 
* > }
* > 
* > //可以加try catch
* > //循环的时候需要注意 foreach函数的上下文

* generator
* > //迭代器 通过yield暂停 使异步看起来像同步

* promise
* > http.get("/api/getAll")
* > .then(callback())
* > .catch(function(err))

## JS Utils
### Lodash
* sort
* forEach
* map
* includes
* pick/pickBy
* find/findIndex
* map
*  isEmpty / isNull / isUndefined / isNil 
* cloneDeep
* isEqual
### JS
* map
* forEach
* ==/===
* join
## Why React
### 组件复用
### 数据与DOM单向绑定
### 内部状态管理state/外部配置管理props

*XMind: ZEN - Trial Version*