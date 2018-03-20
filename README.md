## sublime高级教程
文章引自：[这里](referfrom 'peter的sublime高级教程')

## 常用快捷键
-------------------

| 快捷键 | 效果 |
| :----------------: | :-------------- |
| `ctrl + 鼠标左击` | 多点编辑，`esc`退出 |
| `shift + 鼠标右滑` | 垂直选中，`esc`退出 |
| `ctrl + p` | 根据文件名查找文件用#来查找文件内容例如：filename#searchtext |
| `ctrl + j` | 合并当前行和下一行 |
| `ctrl + L` | 选择当前行 |
| `ctrl + ]` | 当前行向右缩进一个制表符的距离 |
| `ctrl + [` | 当前行向左缩进一个制表符的距离 |
| `ctrl + shift + enter` | 在光标上方开辟新的一行 |
| `ctrl + enter` | 在光标下方开辟新的一行 |
| `alt + 左右方向键` | 选中（范围为一行，粒度为单词） |
| `shift + 上下左右方向键` | 选中（范围未限制，粒度为字符或者行） |
| `ctrl + shift + 上下方向键` | 整行移动 |
| `ctrl + ++/--` | 字体放大或者缩小 |
| `ctrl + shift + f` | 多文件查找 |
| `ctrl + shift + p` | 命令面板，敲模糊命令，就能转到命令 |
| ` ctrl + k + b` | 组合按键，打开侧边栏 |


## 小技巧
-------------------

> 使用ctrl+shift+p,可以打开检索栏，输入Side bar，可以查到如何隐藏 侧滑栏。

> 也可以输入keymap binding 查看所有的快捷键

> 少用鼠标，多用键盘

## 绑定自己的快捷键
-------------------
  命令面板中敲 Key Binding，会给出两项，一个是 Default 这个前面说过了，是系统默认的快捷键设置文件，这个文件是不允许改的。 如果想重新绑定快捷键，那就在 User 这一项，打开后是一个空文件。可以从 Default 中拷贝内容过来，然后自己再改。

``` 
[
  { "keys": ["shift+tab"], "command": "reindent" , "args": { "single_line": false } },
]
```

有一个问题，你怎么知道一个操作的精确的命令名是什么呢？用 Ctrl加 tab 键上面这个“反引号”，这样可以打开控制台，输入

```
sublime.log_commands(True)
```
这样再次执行操作就可以看到操作的精确命令名字了。

## emmet插件快捷方式
-------------------
安装 sublime 之后，默认安装的包里面就自带很多自动补齐的功能，比如在一个 css 文件里面敲
```
c<tab>
bg<tab>
```

在 html 文件中可以敲

```
link<tab>
a<tab>
```
是可以补齐的。自动补齐这个功能后面会有视频做详细的介绍。但是默认的这些自动补齐功能在做 Web 前端开发的时候还不是很够用。所以这一集来讲一个超级实用的包，叫做 emmet，这个我会说是一个必装的包。

#### 补齐操作

现在打开一个文件，把文件类型设置成 html

```
!<tab>
link:css<tab>
```
这个跟原有的触发词比较类似，但是原来没有的，但是用上了就放不下的是这个
```
.nav<tab>
.nav>.item<tab>
ul>li*5<tab>
```
再把文件类型调成 css ，也有些很 cool 的新玩意
```
p10<tab>
m0-auto<tab>
```
更多骚操作在[这里](completions-tab '丰富的 tab 补齐功能').

## 自定义代码片段（snippet）
-------------------
操作方法：tools->插件开发->新建代码片段
保存文件的后缀名：.sublime-snippet
```
<snippet>
	<content>
		<![CDATA[
			你的代码片段${1:说明}
      ${2}
 		]]>
	</content>
	<tabTrigger>ys</tabTrigger>
	<scope>text.html.markdown, text.plain</scope>
</snippet>
</snippet>
```

#### 说明
> CDATA里设置你的代码片段:使用`${1:说明}`来识别tab  
> tabTrigger里设置你的snippet触发关键词   
> scope设置在哪些类型的文件下可以响应此片段     


## 自制补全
-----------------

参考[这里](completions)

文件后缀名是.sublime-completions

## 批处理任务
-----------------
参考[这里](build)

文件后缀名是.sublime-build



------------------------------------------
[build]:http://sublime-text-unofficial-documentation.readthedocs.io/en/latest/reference/build_systems.html
[completions]:http://sublimecodeintel.github.io/SublimeCodeIntel/
[completions-tab]:http://docs.emmet.io/actions/
[referfrom]:http://happypeter.github.io/happysublime/
