### 													`HTML`与`CSS`

##### 栅格布局的原理：

​		弹性

##### 响应式布局：

###### 						原理：手写媒体查询

###### 						什么是响应式：随着页面视口大小而发生响应改变布局，能够兼容多个终端

###### 				如何兼容低版本`IE`：`IE8`以下浏览器之所以不支持响应式网站是因为其不支持选择器，要实现这点需要`respond.js`解决。

##### 浏览器兼容：

###### 		`normalize.css`

​		解决不同浏览器的默认样式差异，或者订制自己的`reset.css`

###### 		`html5shiv.js`

​		解决`IE9`以下浏览器对`html5`新增标签不识别问题

###### 		`respond.js`

​		解决`IE9`以下浏览器不支持`CSS3 Media Query`的问题

###### 		`picturefill.js`

​		解决`IE9、10、11`等浏览器不支持`<picture>`标签的问题

###### 		`IE`条件注释

​		`&lt;、&gt;....`

###### 		`IE`属性过滤器

​		常用的`hack`方法

##### `reset.css`:

​		使不同浏览器的默认样式统一，

##### `CSShack`：

###### 

##### 视觉隐藏网页内容：

​		1.`display：none`：搜索引擎可能会认为被隐藏的是垃圾而忽略

​											屏幕阅读器会忽略被隐藏的文字

​		(`ps`:为视觉上有障碍的人设计的读取屏幕内容的程序，这也是要语义化`HTML`的原因之一)

​		`2.visibility：hidden`：会占据物理空间内容

​		3.`overflow：hidden`：方法是转化为块级(`block`)然后设置宽高为0，超过部分隐藏

##### 几种布局方式:

​		表格布局、流式布局、弹性布局、响应式布局

##### `CSS`预处理：

###### 		通过加入一些编程元素，让`CSS`能像其他程序语言一样可以做一些预定的处理。

###### 		用一种专门的编程语言，为`CSS`增加了一些编程的特性，将`CSS`作为目标生成文件，然后开发者就只要使用这种语言进行编码工作，让`CSS`更加简洁、适应性更强、可读性更佳，更易于代码的维护等诸多好处。

​		`less`、`sass`和`stylus`

​		`sass`：最早也是最成熟的，是`Ruby`语言写的。`Sass`声明变量必须是“$”开头，`Sass`支持条件语句。现在的Sass已经有了两套语法规则：一个依旧是用缩进作为分隔符来区分代码块的；另一套规则和`CSS`一样采用了大括号(｛｝)作为分隔符。后一种语法规则又名`SCSS`，在`Sass3`之后的版本都支持这种语法规则

​		`less`：供了多种方式能平滑的将写好的代码转化成标准的`CSS`代码，采用了缩进作为分隔符来区分代码块，变量名前面使用的是“@”字符，`less`不支持条件语句

​		`stylus`：提供一个高效、动态、和使用表达方式来生成`CSS`，同时支持缩进和`CSS`常规样式书写规则。声明变量没有任何限定，但不要使用“@”符号开头声明变量

##### 三种定位：

​		`relative`、`absolute`、`fixed`

​		`relative`：相对于自己发生偏移

​		`absolute`：相对于拥有`relative`的祖先级元素定位，没有就相对于body

​		`fixed`：定位在视口的固定位置

##### 居中：

​		1.`margin：0 auto`

​		2.`width:2xpx;height:2ypx; float:left position：relative;left:50%;top:50%; margin: -ypx 0 0 -xpx;`

​		3.`width:2xpx;height:2ypx; position: absolute;left:50%;top:50%; margin: -ypx 0 0 -xpx;`

​		4.`transform:translate(父元素width-自身width/2，父元素height-自身height/2);`

##### `margin`与`padding`：

​		`margin`：`border`外、取不到本级背景色、可取负值、上下取大值，一正一负取和的绝对值

​		`padding`：`border`内、会被一同上背景色、上下相距取和

##### `display`设置`inline-block`时，`li`与`li`之间有空白间隔，是因为代码换行的产生了空格；`ul`的`font-size`设置为0

##### 请解释下为什么会出现浮动和什么时候需要清除浮动？清除浮动的方式？

​		设置了`float`，为了并排显示，所以要设置浮动

​		父元素高度坍塌，所以要清除浮动

​		父元素下最后加一个冗余元素，`clear:both`

​		或者`::after{content:"";display:table;clear:both;}`，`IE6、7`不支持

​		或者使用`zoom：1`触发`hasLayout`（`IE6`）

​		或者父元素`BFC`(块级格式化上下文)

##### `BFC`：

​		内部盒子垂直方向排列放置，

​		同一`BFC`上下`Box`的`margin`会重叠

​		每个元素的左边会与包括的盒子左边接触

​		`BFC`的区域不会与`float`重叠

​		`BFC`是页面上一个独立容器，内部的子元素不会影响外面的元素

​		计算`BFC`的高度时，浮动元素会参与计算

##### 盒子模型

​		`IE`盒子与`W3C`盒子；又称为框模型

​		标准盒子模型即`W3C`包括：`content`、`padding`（填充）、`border`和`margin`;宽高是`content`

​		`IE`盒子是指`IE5.5`及以下的盒子宽高则包括`padding`与`border`；

​		`box-sizing`：`content-box（default），border-box，padding-box`；`IE8+`支持

##### `link`和`@import`的区别

​		`link`属于`HTML`标签，而`@import`是`css`提供的，且只能加载`CSS`

​		页面被加载时，`link`会被同时加载，而`@import`引用的`css`会等到页面被加载完再加载

​		`@import`只有在`IE5`以上才能被识别，而`link`是`HTML`标签，无兼容问题

​		`link`方式的样式的权重高于`@import`的权重

​		当使用JavaScript控制`DOM`去改变样式的时候，只能使用`link`方式，因为`@import`眼里只有`css`，不是`DOM`可以控制的

​		`@import`导入`css`是异步的，对优化性能有一定的影响

##### `keep-alive`:

​		keep-alive标签用于切换组件时保留隐藏组件的状态,使其数据不会被初始化

##### 语义化的`HTML`：

语义化的好处：

​	1.去掉或样式丢失的时候能让页面呈现清晰的结构：

​	2.屏幕阅读器（如果访客有视障）会完全根据你的标记来“读”你的网页

​	3.`PDA`、手机等设备可能无法像普通电脑的浏览器一样来渲染网页（通常是因为这些设备对`CSS`的支持较弱

​	4.搜索引擎的爬虫也依赖于标记来确定上下文和各个关键字的权重.

​	5.你的页面是否对爬虫容易理解非常重要,因为爬虫很大程度上会忽略用于表现的标记,而只注重语义标记

​	6.便于团队开发和维护；语义化的`HTML`就是：标题用`h1-h6`，文字段落用`p`，列表用`ul`、 `li`，大致如此

##### `document.write`和`innerHTML`:

​		1.`document.write`直接写入到页面的内容流，会导致页面全部重绘。重绘的原因：在写之前没有调用`dudocument.open`, 浏览器会自动调用open，每次写完关闭之后重新调用该函数，会导致页面被重写。

​		2.`innerHTML`是`DOM`页面元素的一个属性，不会导致重绘

​		3.通过`document.write`插入`<script></script>`元素会自动执行其中的脚本；

​			大多数浏览器中，通过`innerHTML`插入`<script></script>`元素并不会执行其中的脚本

​		`innerHTML`很多情况下都优于`document.write`，其原因在于其允许更精确的控制要刷新页面的那一个部分。

------

### 														框架

##### 对`Vue`的理解：

​		基于`MVVM`的轻量级开发框架

###### 			优点：

​		实现单页面开发

​		渐进式开发

​		通过指令实现开发的快捷与便利

​		组件化开发的特点

​		响应式的数据绑定

​		预处理`DOM`操作，即虚拟`DOM`，减少页面渲染以防卡顿

###### 			缺点：

​		向下兼容性低

​		不适于`seo`(搜索引擎)优化，而且封装的比较厉害，报错不明显，适合单人开发，适合中小型项目

##### `MVVM`：

​		`Model-View-ViewModel`的架构模式

​		模型（`Model`）： 数据保存—存放着各种数据，有的是固定写死的，大多数是从后端返回的数据

​		视图 （`View`）：用户界面，也就是`DOM`

​		视图模型（`View-Model`）:连接`View`和`Model`的桥梁，当数据变化时，`ViewModel`够监听到数据的变化（通过`Data Bindings`），自动更新视图，而当用户操作视图，`ViewModel`也能监听到视图的变化（通过`DOM Listeners`），然后通知数据做改动，这就实现了数据的双向绑定。

`MVVC`设计模式的优点

​	1.低耦合。`View`可以独立于Model而进行变化和修改。同时，一个`ViewModel`可以绑定到不同的`View`上。

​	2.可重用性。可以把一些视图逻辑放在一个`ViewModel`里面，让很多`View`进行重用。

​	3.独立开发。通过`MVVM`，开发人员可以专注于逻辑开发在`ViewModel`里面，而设计人员也可以专注于页面设计

​	4.可测试。通常来说，要进行界面测试比较困难，而`MVVM`可以对`ViewModel`进行测试。

##### `Vuex`:

​		`state`：`vuex`的基本数据，用来存储变量

​		`mutations`：提交更新数据的方法，必须是同步的(如果需要异步使用`action`)。每个 `mutation` 						都有一个字符串的事件类型 (`type`) 和 一个 回调函数 (`handler`)。

​		`actions`：和`mutation`的功能大致相同，不同之处在于

​					1.`action` 提交的是 `mutation`，而不是直接变更状态

​					2.`action` 可以包含任意异步操作。

​		`getters`：从基本数据(`state`)派生的数据，相当于state的计算属性

​		`modules`：模块化`vuex`，可以让每一个模块拥有自己的`state`、`mutation`、`action`、`getters`,使					得结构非常清晰，方便管理。

##### 组件传参：

##### `v-if`和`v-show`：

​		`v-if`是删除该部分，而`v-show`是设置`display:none`

##### 前端的缓存方式：

###### 				`WebStorage`：

​		`localStorage`：本地储存，会一直保存在页面上；

​		`sessionStorage`：会话储存，只会在页面会话期间储存，当页面结束会话会清除储存，`sessionStorage`的数据不会在不同页面共享，而`localStorage`和`cookie`会在同源页面共享

​		关闭页面时应该使用`localStorage.clear()`和`sessionStorage.clear()`清除储存，否则导致数据的不安全性。`WebStorage`有`5MB`的存储空间

###### 				`cookie`：

​			`cookie`仅有`4KB`的存储空间，仅能存储`id`等小量数据

​			`cookie`会发送到服务器端														

------

### 															数据

##### `ajax`：

###### 什么是：

​		`asynchronous JavaScript and Exstensible Markup Language`

###### 		优点：

​			可以使得页面不重载全部内容的情况下加载局部内容，降低数据传输量

​      	  避免用户不断刷新或者跳转页面，提高用户体验

######   	  缺点：

​			对搜索引擎不友好

​       	 要实现`ajax`下的前后退功能成本较大

​       	 可能造成请求数的增加

​       	 跨域问题限制

###### 四步：		

​		`var xhr=new XMLHttpRequest();`

​		`xhr.open('get','/接口'，true);`

​		`xhr.send();`

​		`xhr.onreadystatechange=function(){`

​				`if(xhr.readyState==4 & xhr.state==200){`

​						`var text = xhr.responseText;`

​				`}`

​		`}`

​		如果是`post/put`方法，需要设置请求头信息

​		`xhr.setRequestHeader("Content-Type","application/x-www-form-urlencoded");`

​		创建请求主体

​		`var formdata='uid=${$uid}&...;'`

​		然后发送

​		`xhr.send(formdata);`

##### 状态码：

##### `post`传参：

​		`this.$axios.post('/接口',参数).then(result=>{`

​				`this.data=parseJOSN(result.data.results)`

​		`})`

​		重点是`json`解析

------

### 													JavaScript

##### `let`、`var`和`const`：

​		`const`：声明必赋值，赋值不可改，块级作用域，不能再重名，值为对象，对象属性可修改

​		`let`：块级作用域，同域不能重复定义，不会覆盖window同名属性只会屏蔽

​		`var`：全局作用域，变量提升，绑定window，会覆盖window同名属性

##### `js`的数据类型：

​		原始类型：`number`：专门保存数字类型

​							`string`：保存字符串

​							`boolean`：保存真或假的类型

​							`null`：没有对象，不存在

​							`undefined`：有但未赋值

​		引用类型：`Object`：`Object`包括:

​							`object`：对象

​							`array`：数组

​							`function`：函数方法

​		区别：

​			原始类型的值不可变、不可添加属性和方法、只可进行简单赋值、存放在栈中、之间的比较是值的比较

​			引用类型的值可变、可添加属性和方法、赋值是对象引用、同时存放在栈区和堆区、比较的是引用的比较

##### `js`的`typeof`返回哪些数据类型：

​		`Undefined`、`string`、`boolean`、`number`、`symbol(ES6)`、`Object`、`Function`

##### `js`的本地对象，内置对象和宿主对象？

​    	本地对象：`Object`、`Function`、`Array`、`String`、`Boolean`、`Number`、`Date`、`RegExp`、`Error`、`EvalError`、`RangeError`、`ReferenceError`、`SyntaxError`、`TypeError`、`URIError`官方定义好了的对象

   	 内置对象： `Global` 和 `Math`，内置对象是本地对象的一种

​    	宿主对象：所有的`BOM`和`DOM`对象都是宿主对象，是那些官方未定义，你自己构建的对象加上`DOM`和`BOM`对象组成的

##### `split`和`join`：

​		join() 方法用于把数组中的所有元素放入一个字符串。通过指定的分隔符进行分隔的

​		split()方法：用于把一个字符串分割成字符串数组，与join()相反

##### `pop`、`push`、`unshift`、`shift`：

​		`push`：末尾加、`pop`：末尾减；

​		`unshift`：首位加，`shift`：首位减；

​		加可以多个，减只能一个

##### `use strict`严格模式：

​		第一行，前面不能有实际运行结果的语句，老版浏览器会当做普通字符串忽略

​		消除不合理、不严谨之处，减少怪异行为

​		消除不安全之处

​		提高编译效率

​		为未来版本`js`做铺垫

##### `JSON`解析：

​		`parseJSON()`、`obj.toJSONString()`和`evel()`

​		`Json`字符串：`var json_str = ‘{"name":"xiao","age":12}';`

​		`Josn`对象：`var obj = {"name":"xiao","age":12};`

​		`JS`对象：`Object {name: "xiao", age: 12}`

​		`var obj=eval('('+str+')')`

##### 遍历的方法：

​		`for in`、`for of`、`do while`、`while`、`forEach`、`filter`、`every`、`some`、`reduce`、`map`、`set`、`find`

​		`set`：Set 结构不会添加重复的值

​		`map`：提供了“值—值”的对应，是一种更完善的 `Hash` 结构实现。当需要“键值对”的数据结构时使用

##### `ES6`常用的命令：

​		箭头函数、`call()`、`apply()`、`bind()`、`let`、`const`、`promise`

##### `Promise`：

​		`promise`的出现是为解决因异步操作而引发的回调地狱情况

​		`promise`有三种状态`pending`、`resolve`、`reject`

​		如果结果判断是成功，`pending`状态会变成`resolve`，输出`result`；否则变回`reject`输出`error`

`var promise=new Promise((resolve,reject)=>{`

  	 `if(){`

  			`resolve();`

​		`}else{`

 			 `Reject();`

​		`}`

`});`

`promise.then((result)=>{`

​		      `Console.log(result);`

​		`}, (err)=>{`

​				`Consolr.log(err);`

​		`}`

`});`

##### 线程与进程：

​		一个程序至少一个进程、一个进程至少一个线程

​		进程拥有独立的内存单元；线程共享内存，提高程序的运行效率

##### 同步和异步：

​		同步是单线程的结果，程序会顺序执行，

​		异步是在进程中不影响主线程的情况下添加其他线程，不用等待未完成事件，可以解决单线程效率低的问题

##### 内存泄漏：

​		函数内部不用的局部变量及时清理，在清理时要考虑它的所有引用函数。

​		如果一定要引用局部变量，请用非匿名函数，否则难以销毁引用。

##### `ES6`中构造函数和类：

###### 					面向对象：

（1）特点

抽取对象共有的属性和行为封装为一个类

对类进行实例化获取类中的对象

###### 三大特性：

###### 封装：隐藏对象的属性和实现细节，仅对外提供公共访问方式，将变化隔离，便于使用，提高复用性和安全性。

###### 继承：提高代码复用性；继承是多态的前提

###### 多态：类或接口定义的引用变量可以指向子类或具体实现类的实例对象。提高了程序的拓展性

（2）对象

一个具体的事物，用属性和方法来描述一个对象

（3）类

用class关键字声明一个类，类抽象出了对象的公共部分，它泛指某一大类

类是对象的抽象，而对象是类的具体事例

##### 闭包：

​		能够读取其他函数内部变量的函数

​		只有函数内部的子函数才能读取局部变量，因此可以把闭包简单理解成“定义在一个函数内部的函数”。

​		最大用处有两个，一个是前面提到的可以读取函数内部的变量，另一个就是让这些变量的值始终保持在内存中

​    	重用变量不会造成全局污染

##### `js`中有一个函数，执行对象查找时，永远不会去查找原型，这个函数是什么

​    	`hasOwnProperty`,判断对象是否包含特定的自身（非继承）属性。

##### `this`的理解

​		`this`是一个关键字，它代表函数运行时，自动生成的一个内部对象，只能在函数内部使用

​		作为纯粹的函数调用 this指向全局对象, `fn() -->window`

​		作为对象的方法调用 this指向调用对象, `obj.fn() -->obj`

​		作为构造函数被调用 this指向新的对象,`var obj = new person() -->obj`（`new`会改变`this`指向）

​		`apply`调用 `this`指向`apply`方法的第一个参数,`fn.apply() -->apply`(第一个实参)

箭头函数中的`this`永远指向 该函数定义的位置所在作用域的`this`

​		默认绑定、隐式绑定、显式绑定、隐式丢失、`new`绑定

##### `data-`属性：

​		自定义属性,通过对象的`dataset`属性获取，`.dataset`只有`Chrome`和`Opera`支持，不支持该属性的浏览器可以用`getAttribute`

​		`data-`的`-`之后应使用驼峰命名

##### 事件代理：

​		把事件处理器添加到父级元素，避免添加到多个子元素

​		得益于冒泡机制与目标元素节点

​		`function getEventTarget(e) {`

​        		`e = e || window.event;`

​    		    `return e.target || e.srcElement;`

​	     `}`

------

### 网络

##### `http`和`https`：

​		`https`的`ssl`加密是在传输层实现，需要ca证书，费用高，链接方式不同，端口不同

##### `websocket`：

------

### 优化

##### 编码习惯

​		用`EditorConfig`的规范 

​		保持一致

​		`alt+shift+f`

##### 懒加载与预加载：

​		懒加载：延迟加载：111

##### 网站文件与资源优化

##### 对网站文件、资源进行优化

​		文件合并，减少`http`请求，合并`js`和`css`文件，`css sprite`(精灵图)、图像映射(`image map`)、使用`data uri`来编码图片

​		文件最小化/压缩：`YUI Compressor`

​		`CDN`托管：尽可能避开会影响数据传输速度和稳定的环节

​		缓存的使用：多个域名提供缓存

​		`GZIP`压缩`JS`和`CSS`文件

##### `Data URI`

​		`data`协议头、`MIME`、编码设置、`base64`编码设定、内容

##### 多个域名提供网站资源：

​		主流原因：

​			`CDN`缓存更方便

​			突破浏览器并发限制

​			`cookie`,安全隔离，节省带宽，

​		非主流原因：

​			`UGC`的内容和主站隔离，防止不必要的安全问题

​			数据做了划分，子域名分流省事

##### 浏览器与内核

###### 五大浏览器：`IE`、`Firefox`、`Chrome`、`Safari`、`Opera`

###### 四大内核：`Trident`、`Gecko`、`Blink`和`Webkit`



五大浏览器使用的单内核、有些浏览器使用的双内核

`IE`：`Trident`,俗称`IE`内核,

`Chrome`：以前是`Webkit`，现在是`Blink`

`Firefox`：`Gecko`内核，俗称`Firefox`内核,

`Safari`：`Webkit`内核，`Webkit`俗称`Chrome`内核,

`Opera`：`presto`=>`webkit`=>`Blink`

360、猎豹：`Trident`、`Webkit`双内核

搜狗、`QQ`：`Trident`（兼容）、`Webkit`（高速）

百度：`Trident`



`-ms-`:`IE`

`-moz-`:`Firefox`

`-webkit-`:`Chrome`、`Safari`

`-o-`：`Opera`

