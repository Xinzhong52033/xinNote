## `js`同步, 异步和事件循环

###### 拓展: `js`的单线程

`js`为什么是单线程: 是因为`js`的用途是用户互动, 操作`dom`, 所有如果是多线程, 两个线程同时对`dom`同一个节点进行操作就会混乱.

`HTML5`提出`web worker` , 允许脚本创建多个线程, 但是子线程完全受主线程控制, 且不能操作`dom`.