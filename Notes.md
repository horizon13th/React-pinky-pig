# Ch 02

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
