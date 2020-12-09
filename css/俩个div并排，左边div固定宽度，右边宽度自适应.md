## 俩个div并排，左边div固定宽度，右边宽度自适应

1. 左边div设置浮动, 右边overfflow 触发bfc ,**兼容ie8+，其他浏览器都是ok的**
2. 设置容器浮动,右边项目flex: 1 **flex兼容性不行，ie11都不支持**
3. float+margin-left , **右边的div高度计算会不一样，高度不是由子元素撑开的，而是默认100%的高度。兼容ie8、IE8+**
4. calc计算宽度 **ie9兼容**

````
.left{
	float:left;
	width:200px; height:100%;background:gray;
}
.right{
	height:100%;
	float:right;
	background:#f00;
	width:calc(100% - 200px);
}
````

