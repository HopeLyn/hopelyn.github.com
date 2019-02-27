---
title: VSCode 基本操作
date: 2019-02-27 15:17:17
tags:
---

# VS Code
## 基本操作
*   命令面板：cmd + shift + p
    *   Code Cli 的安装

*   光标移动
    *	  单词：option + 左右
    *	  行：cmd + 左右
    *   **代码块**：cmd + shift + \ => **很关键**
    *   **文件**：cmd + 上下

*   文本选择 + `shift`
    *   单词：option + 左右 + shift
    *   行：cmd + 左右 + shift

*	操作
    *   删除代码
        *   删除行
            *   cmd + fn + delete 右侧所有代码
            *   cmd + delete 左侧所有代码
        *   删除单词
            *   option + fn + delete 右侧所有代码
            *   option + delete 左侧所有代码
        *   删除当前行 cmd + shift + k
        *   剪切当前行 cmd + x
    *   移动一行代码：option + 上下

*   `keyboard` 查看键位绑定：cmd + k cmd + s

## 进阶操作
*   代码格式化：format
    *   option + shift + f

*   排序：sort line ascending => cmd + shift + p

*   多光标操作 => **？** `https://time.geekbang.org/column/article/40261`
	*	cmd + d => 选中左边第一个单词
	*	选中多行后，option + shift + i => 多行行尾添加光标

#### 文件跳转
	*	cmd + p => 最近的文件列表(或者查找文件)
		*	cmd + enter => 新窗口里打开 => **可以对比不同**
		*     打开以后发现它是可切换状态，因为你没有编辑，你可以手动 cmd + s 去固定这个标签页
		![](media/15481297883580/15482156645261.jpg)

	*	ctrl + tab 切换
	*	cmd + option + 左右 => 浏览器里可以通用

*   行跳转：ctrl + g => 在查看 git 冲突的时候 => vim 模式 `:number`

#### 符号跳转
*   cmd + shift + o：跳转类(类似于大纲，在组件的功能了解中很方便)
*   cmd + t：跨文件查找调用方法的定义(比如查找接口调用的时候)

#### 函数跳转
*   cmd + f12：跳转方法实现
*   f12: 跳转方法定义
*   shift + f12：查看方法调用
    *   space 打开

*	f2：快速修改方法/函数名(相关的调用/定义)

*	cmd + option + [/] => 代码折叠，看代码逻辑的时候特别好用，和 cmd + shift + 左右 都特别适合看代码
*	cmd + k -> cmd + 0 => 折叠文件
	*	cmd + k -> cmd + j

### 自动补全、快速修复、重构 => https://time.geekbang.org/column/article/40847

### 代码折叠、小地图、面包屑
#### 面包屑 => 可能有人更喜欢这个而不是文件资源管理器
*   打开面包屑 cmd + shift + .
*   option + 左/右 => 切换层级

### 极速搜索
*   cmd + f：自动选中当前光标所在的单词
*   cmd + g：搜索，但是光标仍在编辑区

大小写敏感，全单词匹配、正则匹配

替换：cmd + option + f

### 全局查找
*	cmd + shift + f 查找
*	cmd + 下 切换到相应搜索结果
*	o 打开搜索列表


### 查找/定位
*	cmd + f 
	*	enter => 下一个
	*	shift + enter => 上一个

### 切换工作区
*	cmd + shift + e => 文件资源管理器
*	cmd + shift + x => 插件管理
*	ctrl + shift + g => 源代码管理

右击工作区即可
![](media/15481297883580/15481522955441.jpg)


### 切换窗口
支持多工作区模式，但是更支持多窗口，一个工作区对应一个窗口
*	ctrl + w => 切换多窗口

#### markdown 预览
cmd + k 、v

#### 查找键位绑定 keyboard
*   录制按钮

![](media/15481297883580/15482407032089.jpg)


### 编辑器配置
*   垂直标尺 => "editor.rulers": [120] => 120字符
*   缩进参考线 => "editor.renderIndentGuides": true
*   lineNumber
*   空格处填充符号 => "editor.renderWhitespace": "boundary"
*   左侧行号也添加了背景号 =>  "editor.renderLineHighlight": "all"

#### 其它配置
*   tabSize、lineHeight、autoSave/autoSaveDelay
*  `terminal.integrated.shell.osx`: zsh
*   "files.exclude":  { "**/node_modules": true } => 加快编辑器运行速度

#### 悬浮注解
![](media/15481297883580/15482581731361.jpg)

### 编辑器管理
#### 窗口管理
*	cmd + \ => 打开新窗口
    *   cmd + 1/2/3 => 切换窗口
    *   cmd + option + 0(数字) => 切换布局方向(垂直/水平)

#### Tab 管理
*   ctrl + tab
*   option + cmd + 左/右
*   cmd + p

### 视图切换
*	cmd + B => 左侧边栏的展示/隐藏
*	zen => 只留下代码
*	cmd + j => 查看 code spell check 的报错
![](media/15481297883580/15482397619087.jpg)

### 插件篇
#### BASIC 
*   code spell checker：检查单词拼写错误
*   Bracket Pair Colorizer：彩色的括号
*   Document This：为 function、class 等自动生成文档
*   Gitlens：Git 集成工具
    *   当前行展示 git blame 信息
*   Material Icon Theme/vscode-icons：文件夹icon的多样性
*   TODO Highlight：List TODO list
![](media/15481297883580/15482559630550.jpg)

*   Vim：
*   vscode-fileheader：ctrl + option + i 生成新文件的文档 => 孙悟空到此一游
*   Path Intellisense：补全文件路径名
*   Faker：生产 fake name => 就像名字一样废...

#### ADDITIONS
*	pigment：可以直接看到当前的色彩
*	settings sync：generate key => 保存到 gists 上
*	project manager => 保存以后很方便可以切换(打开的/未打开的)工程
*	live share => 登录就可以修改别人的工程文件，而不需要拉代码

*	.vscode 中添加 recommendations => vscode 会提示安装

![](media/15481297883580/15482563560237.jpg)


## mac note 的使用
*	ctrl + shift + tab 或者 ctrl + tab

## 浏览器
*   f12 调出来控制台
*   debugger 控制台
	*	f8、f10、f11
	*	esc：source debugger 的时候可以调出 console 控制台
*	cmd + shift + n 打开隐身窗口
*	shift + w => 在新的窗口打开浏览页


### 插件
*	vimium
	*	j、k 上下挪动页面
	*	yy：复制当前 url
	*	p/P：当前剪贴板的 url 复制到地址栏
	*	o/O：打开bookMark、收藏栏、历史记录中的页面
	*	T：查找当前打开的 tab
	*	r：reload page
	*	shift + ? 查看快捷键
	*	查找模式
		*	/xxx：查找 xxx
		*	n/N：上/下一个

### 其它插件
*   有道划词/网易有道词典鼠标取词：查询方便，划词翻译快速
*   二维码生成
*   great suspender
*   各种 devtools：redux、MobX、vue、React
*   Github 相关的文件管理侧边栏

## iTerm 2 使用
*	选择文本: `cmd + f`搜索 ＋ `tab`选中文本，会自动添加到剪切板，使用`cmd + v`即可使用
* 	临时调用iterm: 通过hotkey的设置 => `shift + space` => **可以尝试使用cal看今天是周几，不过使用台历也没有问题**
 ![](media/15481297883580/15482137824196.jpg)


*  	命令行标记: `cmd + shift + m`可以为某一行(或者说某一屏幕添加标记),之后可以使用`cmd + shift + j`跳回这里
    *   比如一些安装步骤或者看到日志需要对比的时候可以打标记
*  	剪贴板历史: `cmd + shift + h`可以查看(iterm)剪贴板历史纪录
*  	查看操作历史(快照): `cmd + option + B`可以查看之前一段时间内的操作的快照(阴险)

![](media/15481297883580/15482140578138.jpg)

*   option + b、option + f
*   iTerm2
	*  	1. 分窗口操作：`shift+command+d`（横向）command+d（竖向）
		*  	`cmd + opt + 方向键`: 切换窗口内的面板 
	*	2. 查找和粘贴：command+f，呼出查找功能，tab 键选中找到的文本，`option+enter` 粘贴
	* 	3. 全屏快捷键是 `cmd+enter` 而不是默认的 `ctrl+cmd+f`

*   cmd + k 清屏
*   cmd + r 刷新屏幕(上面的记录会保留)

## 切换显示器
因为没有别的切换快捷键，所以可以通过 alfred/spotlight 来实现，所以需要保留一个功能，不要在不同显示屏打开同一个应用，这会导致切换的问题

*	注意，ctrl + 左/右 只会切换鼠标所在位置的屏幕，所以需要使用别的方式切换打开了多个窗口的应用
	*	vscode: ctrl + w
	*	chrome: vimium 插件的 T 

## MAC 常用快捷键
*   ctrl + cmd + f => toggle full screen
*   cmd + m => 最小化窗口
*   ctrl + 方向 => switch screen 
*   ctrl + 上 => list screens
*   cmd + tab => switch apps 可以使用 alfred/spotlight 替代
*   cmd + option + esc => 强制关闭程序

### 终端常用快捷键(https://www.cnblogs.com/mangosoft/p/6375266.html)
*   `ls`
*   mkdir、cd、cp、mv、rm、pwd
*   history、ctrl + r
*   env => 配置环境时需要
*   cat、find、head/tail、diff(在进行一些实验的时候，可以用来对比实验结果)
*   wc：看代码量(行、词、字母)
*   ps、kill
*   `du -h 1`

## 其它电脑配置
### vim
![](media/15481297883580/15482589171116.jpg)


参看： 
*   [Python环境配置](https://realpython.com/vim-and-python-a-match-made-in-heaven/)
*   [阮一峰-vim 配置入门](http://www.ruanyifeng.com/blog/2018/09/vimrc.html)

*   插件管理 Vundle
*   Powerline
*   Line Numbering
*   File Browsing
*   Color Schemes
*   Syntax Checking/Highlighting
*   Auto-Complete

#### 其它链接
*   [Vim配置](https://github.com/spf13/spf13-vim)
*   [oh-my-zsh](https://github.com/robbyrussell/oh-my-zsh)
*   [渐进配置vim](https://www.cnblogs.com/zhongcq/p/3642794.html)


### zsh 插件
![](media/15481297883580/15482590011608.jpg)



## VIM
*   zM/zR => 全文折叠/展开
*   zc/zo: 代码块折叠/展开
*   多级折叠
*   

