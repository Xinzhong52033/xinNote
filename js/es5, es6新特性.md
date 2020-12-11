### es6新特性

##### 1.块级作用域 

let

1. 不存在变量提升 2.块级作用域 3. 不允许重复声明

const

1. 不提升 2.块级作用域 3.  值不能修改,但是其只保证指针不发生改变，因此可以修改保存的对象的值

使用let 替代var, 然后使用const由于let

`const`声明常量还有两个好处，一是阅读代码的人立刻会意识到不应该修改这个值，二是防止了无意间修改变量值所导致的错误。

##### 2.字符串

````
// bad
const a = "foobar";
const b = 'foo' + a + 'bar';

// acceptable
const c = `foobar`;

// good
const a = 'foobar';  静态字符串使用单引号
const b = `foo${a}bar`;  动态字符串使用反引号
````

