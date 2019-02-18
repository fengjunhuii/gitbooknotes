# GitBook 安装

## 目录

[TOC]

## 本地安装

### 环境要求

安装 GitBook 是很简单的。您的系统只需要满足这两个要求：
- Git  （Windows下安装推荐）
- NodeJS（推荐使用 node-v9.3.0-x64.msi 及以上版本）
- Windows，Linux，Unix 或 Mac OS X

#### 安装Git
Git功能很强大，这里就不介绍了，下载安装 [**Git**](https://git-scm.com/)

<img src="https://git-scm.com/images/logo@2x.png" align="left" border="3" width="1040" height="400" >

安装Git主要是为了右键快速启动命令行 Git Bash Here，方便实用。

当然另一个在指定目录打开命令行的方式是，按住shift键，同时按下右键，可以直接在当前目录打开命令行。

#### 安装 Node.js
GitBook 是一个基于 Node.js 的命令行工具，下载安装 [**Node.js**](https://nodejs.org/en/)(注意：不要选择最新版本)

<img src="https://nodejs.org/static/images/logo.svg" align="left" border="3" width="220" height="138" usemap="#planetmap">

安装完成之后，你可以使用下面的命令来检验是否安装成功。
```bash
$ node -v
v9.3.0
```
### 通过NPM安装gitbook

安装 GitBook 的最好办法是通过 **NPM**。在终端提示符下，只需运行以下命令即可安装 GitBook：

```bash
$ npm install gitbook-cli -g     （执行该命令的时候最好翻个墙）
```

`gitbook-cli` 是 GitBook 的一个命令行工具。它将自动安装所需版本的 GitBook 来构建一本书。

执行下面的命令，查看 GitBook 版本，以验证安装成功。

```bash
$ gitbook -V
```
使用 `gitbook ls-remote` 会列举可以下载的版本。


## 创建一本书

### 初始化

GitBook可以设置一个样板书：

```bash
$ gitbook init
```
通过这个命令就会在当前目录下创建gitbook的模版，目录如下：
```bash
├── README.md
└── SUMMARY.md
```
README.md 是介绍页。
SUMMARY.md 是目录页。

如果您希望将书籍创建到一个新目录中，可以通过运行 `gitbook init ./directory` 这样指定目录创建。

### 构建

使用下面的命令，会在项目的目录下生成一个 `_book` 目录，里面的内容为静态站点的资源文件：

```bash
$ gitbook build
```

#### Debugging

您可以使用选项 `--log=debug` 和 `--debug` 来获取更好的错误消息（使用堆栈跟踪）。例如：

```bash
$ gitbook build ./ --log=debug --debug
```

### 书本预览

```bash
$ gitbook serve
Live reload server started on port: 35729
info: 7 plugins are installed
info: loading plugin "livereload"... OK
......
info: loading plugin "theme-default"... OK
info: found 10 pages
info: found 8 asset files
info: >> generation finished with success in 2.3s !

Starting server ...
Serving book on http://localhost:4000
```
使用下列命令会运行一个 web 服务, 浏览器访问 `http://localhost:4000/` 可以预览书籍