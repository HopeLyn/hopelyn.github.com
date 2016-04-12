---
title: Markdown语法学习
date: 2016-04-09 16:01:28
categories: 未完成
tags: 
	- 工具
	- 语法
---
**备注**: 待完成，从开头到"图片大小"部分尚未处理

## 语法总结
*	段落与换行:
	* 	行尾多加两个空格，就可以换行
	*	`<br>`

*	标题:
	*	#标题1

	*	标题2
		===

	*	标题2
		-

*	引用: 
	*	单行引用
	
	*  	>单行引用

	*	>嵌套引用
		>>嵌套嵌套
		
	*	>引用中使用 ***`markdown`*** 语法

*	列表:
	* 	无序列表
		* 	第一项
		+ 	第二项 
		-	第三项

	*	有序列表
		1.	有序列表以`数字`和`.`为首
		2. 	数字的序列并不会影响生成的列表序列: 
		4. 	比如这样
		5. 	也可以转义来取消序列的作用
		6\. 

*	代码
	* 	代码块
	<html>
	<div style='color:#69d'>蓝色的代码</div>
	</html>

	*	内嵌代码: `<title>Markdown</title>`

*	分割线

	* * *
	---
	_ _ _


*	超链接:
	*	本地文件:[icon.png](./images/icon.png)

	* 	[Google](http://www.google.com/)

	*  	[Google][]
		[Google]: http://www.google.com/ "Google"
	*	自动转换为链接
		* 	URL: <http://www.google.com/>
		*	Email: <123@email.com>
*	图片: 
	* 	行内式  
	
		````js
		![GitHub](https://avatars2.githubusercontent.com/u/3265208?v=3&s=100 "GitHub,Social Coding")
		````
		![GitHub](https://avatars2.githubusercontent.com/u/3265208?v=3&s=100 "GitHub,Social Coding")
	*	参考式

		````js
		// 注: hexo 中出不来结果
		![GitHub][github]
		[github]: https://avatars2.githubusercontent.com/u/3265208?v=3&s=100 "GitHub,Social Coding"
		````
		
		![GitHub][github]
		[github]: https://avatars2.githubusercontent.com/u/3265208?v=3&s=100 "GitHub,Social Coding"

	*	图片大小:
		
		````js
		<img src="https://avatars2.githubusercontent.com/u/3265208?v=3&s=100" alt="GitHub" title="GitHub,Social Coding" width="200" height="200" />
		````
		<img src="https://avatars2.githubusercontent.com/u/3265208?v=3&s=100" alt="GitHub" title="GitHub,Social Coding" width="200" height="200" />
*	强调
	* 	*斜体* or _斜体_

		```js
		*斜体* or _斜体_
		```
	*  	**粗体** or __粗体__

		```js
		**粗体** or __粗体__
		```

*	扩展语法
	* 	语法高亮

		````
			// 用法
			```js
			window.addEventListener('load', function(){
				console.log('window loaded');
			})
			```
		````
		````
			// 结果
			window.addEventListener('load', function(){
				console.log('window loaded');
			})
		````
	*	表格: 
		*	`|` 区分单元格
		*	`-` 分隔表头和其它行
		*	用法

			```
			| 链接 | 结果 | 原因 |
			|-----|---|----------|
			|文本内容| **`是`** |同协议同域名同端口|
			|文本内容| **`是`** |同协议同域名同端口|
			|文本内容| **`是`** |同协议同域名同端口|
			```
		*	结果 

| 链接 | 结果 | 原因 |
|-----|---|----------|
|文本内容| **`是`** |同协议同域名同端口|
|文本内容| **`是`** |同协议同域名同端口|
|文本内容| **`是`** |同协议同域名同端口|

	
## 注意问题
*	想要引用反引号(`` ` ``)的时候，使用多个反引号将其括起来(注意包括的反引号和内容中的反引号不能是连续的，需要用空格隔开)，如``` `` ` `` ```
