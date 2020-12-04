## `js`延迟加载

#### `js`延迟加载是什么?

使用不同的方法延迟`js`的加载

#### 为什么要延迟加载?

`js`的延迟加载有助于提高页面的加载速度

#### 如何延迟加载?

##### 1. `defer`属性

````html
<script src="file.js" defer> </script>
````

浏览器会并行下载 `file.js`和其它有` defer` 属性的`script`，而不会阻塞页面后续处理。`defer`属性在`IE 4.0`中就实现了，超过10多年了！`Firefox`从 3.5 开始支持`defer`属性 。

注：所有的defer脚本保证是按顺序依次执行的。

##### 2.`async`属性

````html
<script src="file.js" async> </script>
````

`async`属性是`HTML5`新增的。作用和`defer`类似，但是它将在下载后尽快执行，不能保证脚本会按顺序执行。它们将在`onload` 事件之前完成。

##### 3.动态创建`DOM`方式 (使用的最多)

Google帮助页面的推荐方案

````html
<script type="text/javascript">
  function downloadJSAtOnload() {
   var element = document.createElement("script");
   element.src = "defer.js"; // 需要加载的外部js
   document.body.appendChild(element);
  }
  if (window.addEventListener) //添加监听事件
   window.addEventListener("load",downloadJSAtOnload, false); //事件在冒泡阶段执行
  else if (window.attachEvent)
   window.attachEvent("onload",downloadJSAtOnload);
  else
   window.onload = downloadJSAtOnload;
</script>
````

##### 4.使用`setTimeout`延迟方法的加载时间

````html
<script language="JavaScript" src="" id="my"></script>
<script>
setTimeout("document.getElementById('my').src='include/common.php'; ",3000);//延时3秒
</script>
````

##### 5.让`js`最后加载

例如引入外部js脚本文件时，如果放入`html`的`head`中,则页面加载前该js脚本就会被加载入页面，而放入`body`中，则会按照页面从上倒下的加载顺序来运行`javascript`的代码~~~ 所以我们可以把`js`外部引入的文件放到页面底部，来让`js`最后引入，从而加快页面加载速度。

注意：不应该把那些页面正常加载需要依赖的`javascript`代码放在这里。而应该将`JavaScript`代码分成两组。一组是因页面需要而立即加载的`javascript`代码，另外一组是在页面加载后进行操作的`javascript`代码(例如添加click事件或其他东西)。这些需等到页面加载后再执行的JavaScript代码，应放在一个外部文件，然后再引进来。

