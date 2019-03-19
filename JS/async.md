### 异步语法糖

-   async/await
```JavaScript
 async () => {
     await http.get("/api/getAll")
    //promise对象
    //...看似同步 实际是异步操作
 }

 //可以加try catch
 //循环的时候需要注意 foreach函数的上下文
```
-   generator
```JavaScript
 //迭代器 通过yield暂停 使异步看起来像同步
```
-   promise
```JavaScript
 http.get("/api/getAll")
 .then(callback())
 .catch(function(err))
 ```
