---
title: Github Pages + Hexo 写博客
date: 2016-04-08 15:02:28
categories: 未完成
tags: 
	- 工具
	- 实践
---


## 博客地址
*	`http://hopelyn.github.io/`
* 	`http://blog.hopeleft.com/`

## 配置环境
### Github Pages Prjoect 搭建

### Hexo配置
#### 安装
*	安装 Node 环境: [https://hexo.io/docs/index.html#Install-Node-js](https://hexo.io/docs/index.html#Install-Node-js)
	* 	`curl https://raw.github.com/creationix/nvm/master/install.sh | sh`
	*  	或者使用 nvm : `nvm install 4`

* 	安装 Git 环境: [https://hexo.io/docs/index.html#Install-Git](https://hexo.io/docs/index.html#Install-Git)
	*  	使用 homebrew: `brew install git`
	*  	使用 macports: `port instal git`

* 	安装 hexo (使用 npm 安装):`npm install -g hexo-cli`

* 	安装 `hexo-deployer-git` => 可以发布 hexo 到相应的 git rep 上: `npm install hexo-deployer-git --save` 

#### 自定义配置
*	修改 `_config.yml` 文件:
		
	```yml
	// _config.xml
	deploy:
		type: git
		repo: git@github.com:HopeLyn/hopelyn.github.com.git
		branch: master
	```
*	在 **./public** 文件夹下添加 `CNAME` 文件，并写下需要重定向的域名 

	```js
	// CNAME
	blog.hopeleft.com
	```
*	修改 theme
	* 	下载主题到 **./themes** 文件夹下

		````js
		// 安装 Next 主题
		git clone https://github.com/iissnan/hexo-theme-next themes/next

		// 或者安装 yilia 主题
		git clone https://github.com/litten/hexo-theme-yilia.git themes/yilia
		````

	*	修改 `_config.yml` 文件

		```js
		// #theme: next
		theme: yilia
		```
*	`sitemap`: 
	*	普通的 **sitemap** 插件
		*	安装
	
			```js
			npm install hexo-generator-sitemap --save
			```
		*	修改 `_config.xml`
		
			```js
			// _config.xml
			sitemap:
	           path: sitemap.xml
			```
	*	**baidu-sitemap** 插件
		*	安装
		
			```js
			npm install hexo-generator-baidu-sitemap --save
			```
		*	修改 `_config.xml`
		
			```js
			// _config.xml
			baidusitemap:
				path: baidusitemap.xml
			```
*	生成 `RSS`:
	* 	安装插件: `npm install hexo-generator-feed --save`
	*	修改设置:

		```js
		// _config.xml
		feed:
			type: atom
			path: atom.xml
			limit: 20
		```
*	`yilia`主题的自定义配置
	* 	language: 在主目录下的 `_config.yml` 中修改
	
		```js
		language: zh-Hans #简体中文
		```

### 使用方法
*	新建文章: `hexo new 'My Post Name'` => 就会在 **./source/_posts** 下新建一个 `My Post Name.md` 文件

*	通过 `hexo d -generate` 生成 html 文件(在 public 文件夹下)，并发布到 github 上

*	`hexo s`: 启动本地服务，方便调整和配置

### 写文章方法
* 	文章的头部
	*  	用`hexo new 'My Post Name'`命令新建文章的话会自动生成开头，如下所示
	
		```js
		---
		title: Github Pages + Hexo 写博客
		date: 2016-04-09 16:11:31
		tags:
		---
		```

*	文章的主体
	*	基本按照 [Markdown](http://www.appinn.com/markdown/) 语法
	* 	**注意一点** 在写副标题的时候，需要在`##` 和标题名中间留下空格，如 `## 使用方法`，否则会显示 `##使用方法` 在页面上，而不转义

### 常见问题
*	`WARN  No layout: index.html`: 当使用 git 来保存 hexo 文件夹时，因为 yilia 和 next 是单独的 git project，所以当你换电脑，或者重新 clone 这个工程时，yilia 和 next 只剩下空的文件夹
	* 	解决方法一: 重新拉取 => 但是当你用 git 管理 hexo 项目的时候，这些主题并不会 push 上去

		```bash
		git clone https://github.com/litten/hexo-theme-yilia.git themes/yilia
		git clone https://github.com/iissnan/hexo-theme-next.git themes/next
		```
	*	解决方法二: 通过 git subtree 来管理

		```bash
		// 新建一个指向远程仓库的 remote 
		git remote add yilia https://github.com/litten/hexo-theme-yilia.git
		
		// 在指定路径下建立 subtree，并同步代码
		git subtree add —-prefix=themes/yilia/ yilia master
		
		// 或者直接建立
		git subtree add --prefix=themes/next --squash https://github.com/iissnan/hexo-theme-next.git master
		```
