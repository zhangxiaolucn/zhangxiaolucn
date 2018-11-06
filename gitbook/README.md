### GitBook
GitBook 是一个基于 Node.js 的命令行工具，可使用 Github/Git 和 Markdown 来制作精美的电子书，GitBook 并非关于 Git 的教程。

### Markdown
Markdown是一种可以使用普通文本编辑器编写的标记语言，通过简单的标记语法，它可以使普通文本内容具有一定的格式。

### GitBook安装
1. 需要先安装NodeJS
2. 通过NPM安装GitBook

```
$ npm install gitbook-cli -g
```
3. 验证安装是否成功！

```
$ gitbook -V
```

# 创建一本书
### 初始化

GitBook可以设置一个样板书：
```
$ gitbook init
```
如果您希望将书籍创建到一个新目录中，可以通过运行` gitbook init ./directory `这样做。
### 构建

使用下面的命令，会在项目的目录下生成一个 `_book` 目录，里面的内容为静态站点的资源文件：
```
$ gitbook build
```

### Debugging

您可以使用选项 `--log=debug` 和 `--debug` 来获取更好的错误消息（使用堆栈跟踪）。例如：

```
$ gitbook build ./ --log=debug --debug
```

### 启动服务
使用下列命令会运行一个 web 服务, 通过 http://localhost:4000/ 可以预览书籍
```
$ gitbook serve
```
你在你的图书项目的目录中多了一个名为
_book的文件目录，而这个目录中的文件，即是生成的静态
网站内容。
使用build参数生成到指定目录
与直接预览生成的静态网站文件不一样的是，使用这个命令，
你可以将内容输入到你所想要的目录中去：

```
$ mkdir /tmp/gitbook
$ gitbook build --output=/tmp/gitbook
```
### 输出PDF文件
输入为PDF文件，需要先使用NPM安装上gitbook pdf：
```
$ sudo npm install gitbook-pdf -g
```

### 生成电子书
GitBook 可以生成一个网站，但也可以输出内容作为电子书（ePub，Mobi，PDF）。
```
$ gitbook pdf ./ ./mybook.pdf

$ gitbook epub ./ ./mybook.epub

$ gitbook mobi ./ ./mybook.mobi
```

### 插件
1. 插件名称：toggle-chapters
2. 效果：默认只在目录导航中显示章的标题，而不会显示小节的标题，点击每一章或者每一节会显示当前章或节的子目录，如果有的话，但是同时会收起其它之前展开的章节。
3. 插件安装
```
$ npm install gitbook-plugin-toggle-chapters -g (此时gitbook的根目录下的node_modules文件夹中已经有了该插件了)
```
插件参考：http://gitbook.zhangjikai.com/plugins.html#ace-plugin
## gitbook 常用的命令：
```
gitbook init //初始化目录文件
gitbook help //列出gitbook所有的命令
gitbook --help //输出gitbook-cli的帮助信息
gitbook build //生成静态网页
gitbook serve //生成静态网页并运行服务器
gitbook build --gitbook=2.0.1 //生成时指定gitbook的版本, 本地没有会先下载
gitbook ls //列出本地所有的gitbook版本
gitbook ls-remote //列出远程可用的gitbook版本
gitbook fetch 标签/版本号 //安装对应的gitbook版本
gitbook update //更新到gitbook的最新版本
gitbook uninstall 2.0.1 //卸载对应的gitbook版本
gitbook build --log=debug //指定log的级别
gitbook builid --debug //输出错误信息
```

## 常见错误
```
Error: ENOENT: no such file or directory, stat 'D:\book\_book\gitbook\gitbook-pl
ugin-fontsettings\fontsettings.js'
```
把.gitbook\versions\3.2.2\lib\output\website\copyPluginAssets.js 里面112行改成confirm：false
例如：C:\Users\Administrator\.gitbook\versions\3.2.3\lib\output\website\copyPluginAssets.js


## 其他教程
https://dunwu.gitbooks.io/gitbook-notes/

https://www.imooc.com/article/22889
