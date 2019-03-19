### Content

## React

## ES6 Syntax
- const
常量不可以被修改
```Javascript
//Before
var var1 = true
var1 = false
//ES 6
const var1 = true
var1 = false //illegal
```
- Let 使全局变量不受干扰
```Javascript
var var1 = "let"
var var2 = "noLet"
if(var1){
    let var1 = "letEat"
    console.log(var1) // letEat
    var var2 = "letEat"
    console.log(var2) // letEat
}
console.log(var1) // let
console.log(var2) // letEat
```
```Javascript
for(let i=0; i<5; i++)
for(var i=0; i<5; i++)
//通过var定义循环体的计数器i，i是全局变量，取决于循环结束的值
//通过let定义，i是作用域内部变量
```
- 模板字符串 拼接字符串更easy
```html
<h1>${content}</h1>
```
```Javascript
//Before
console.log("Hi,"+firstName+" "+lastName);
//ES 6
console.log('Hi,${firstName} ${lastName}');
```
- 默认参数 没有传入参数时允许函数执行时使用默认值
```Javascript
function foo(firstName="Amy", lastName="Green"){
    console.log('Name: $firstName' 'lastName');
}
```
- 箭头函数
```Javascript
//function
var nameFunc = function(name){
    return 'My name is ${name}'
}
//arrow function
var nameFunc = (name) => 'My name is ${name}'
```
- 解构赋值 将**值从数组**或**属性从对象**提取到不同的变量中
```Javascript
//Object attribute
const user = {name:'Amy', age, 20}
const {name, age} = user
console.log('${name}: ${age}') //Amy, 20
//Array value
const arr = [1,2]
const [foo, bar] = arr
console.log(foo) //1
```

- 对象语义增强 解构的反向操作 将值作为属性赋予对象
```Javascript
const name = 'Amy'
const age = 20
const user = {name, age}
//function 关键字的省略
const user = {
    name,
    age,
    eat(food){
      console.log('yummy',food)
    }
}
```

- 扩展运算符 ... Spread Operator 用于组装数组 获取部分数组
```Javascript
//组装数组
const arr = ['Apple', 'Orange']
[...arr, 'Banana'] //['Apple', 'Orange', 'Banana']
//获取部分数组
const arr = [1,2,3,4]
const [first, ...rest] = arr //rest:[2,3,4]
const [a, b, ...c] = arr //c:[3,4]
```
```Javascript
//Before
const attrs = {
  href: 'http://example.org',
  target: '_blank',
};
<a href={attrs.href} target={attrs.target}>Hello</a>
//dva
const attrs = {
  href: 'http://example.org',
  target: '_blank',
};
<a {...attrs}>Hello</a>
```
- 模块导入导出
```Javascript
import dva from 'dva'//引入全部
import {connect} from 'dva'//引入部分
export default App//导出默认
export class App extend Component {}//部分导出
```

## JS Basic
- prototype 原型 原型链
```Javascript

```
- closure 闭包
- bind 的实现
- call/apply 的实现