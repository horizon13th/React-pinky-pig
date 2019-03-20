## JS Basic
- Object

- prototype 原型：每个JS对象都有一个内部属性 [[Prototype]] ，不能被外部访问
通过下列方法得到 prototype：

```Javascript
//Object.getPrototypeOf()
let a = new Object();
Object.getPrototypeOf(a);
//{constructor: ƒ, __defineGetter__: ƒ, __defineSetter__: ƒ, hasOwnProperty: ƒ, __lookupGetter__: ƒ, …}

//__proto__ 是对象的一个属性，通过这个属性暴露出其prototype，这个属性已经弃用了，在某些浏览器中不再支持，
x.__proto__
//{constructor: ƒ, __defineGetter__: ƒ, __defineSetter__: ƒ, hasOwnProperty: ƒ, __lookupGetter__: ƒ, …}


```

- closure 闭包
- bind 的实现
- call/apply 的实现
