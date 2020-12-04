### `promise`

##### 1.为什么要使用`promise`?

传统的异步编程会造成回调地狱，一旦嵌套次数过多，使代码难以理解和维护。`Promise`可以通过链式调用的方法解决回调嵌套的问题

##### 2.如何使用`promise`?

**ES6**给我们提供了一个原生的构造函数**Promise**

````javascript
// 下面的代码可以直接运行在浏览器的控制台中（Chrome浏览器）
> typeof Promise
"function" // 可以看出这是一个构造函数
> Promise
function Promise() { [native code] } // ES6的原生支持函数, 无法看到源码
````

**ES5**创建**promise**

````javascript
// 我们先使用ES5的语法
var promise = new Promise(function(resolve, reject) { 
    var flag = Math.random();
    setTimeout(function() {
        if(flag > 0.5) {
            resolve('success');
        }
        else {
            reject('fail');
        }
    }, 1000);
});

console.log(promise); // 在浏览器的控制台运行的话，它返回的是一个包含了许多属性的Promise对象；在Node.js环境中控制台输出 Promise { <pending> }。

promise.then(function(result) {
    console.log(result);
}, function(err) {
    console.log(err);
}); // 1s后这里的输出可能是fail也可能是success
````

构造函数promise参数是一个回调函数, 这个回调函数有两个参数, 一个是resolve解决函数, 一个是reject拒绝函数

**ES6**简写

````JavaScript
let p = new Promise((resolve, reject) => {
    setTimeout(() => {
        Math.random() > 0.5 ? resolve('success') : reject('fail');
    }, 1000)
});

console.log(p);

p.then((result) => { // .then参数有两个回调, 一个是成功时候执行, 一个是失败后执行, resove和reject分别传递给第一个和第二个函数作为参数
    console.log(result);
}, (err) => {
    console.log(err);
});
````

