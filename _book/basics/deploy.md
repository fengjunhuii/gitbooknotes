# Gitbook 部署


## 托管到 Github

下载Git软件: <https://git-scm.com/downloads>

<img src="https://git-scm.com/images/logo@2x.png" align="left" border="3" width="1040" height="400" >

1. master 分支保存书籍的源码
2. gh-pages 分支保存书籍编译后的 HTML 文件 
3. 安装Git主要是为了右键快速启动命令行 Git Bash Here，方便实用。
   当然另一个在指定目录打开命令行的方式是，按住shift键，同时按下右键，可以直接在当前目录打开命令行。（不推荐）

如果你不希望使用 Gitbook 的仓库，而是想直接使用 Github 的仓库，可以参考如下教程。

### 1. 打开注册Github账号
	打开[https://github.com/](https://github.com/) ,如果没有Github账号，建议你立马申请一个，因为全球最大的“同性”交友网站在等你;
### 2. 登录你的 Github 账号。
	点击 + --->New repository--->Create a new repository--->Repository name 仓库名（最好和你本地的文件夹名字一样）gitbooknotes-->Description 项目的描述--->public--->Initialize this repository with a Readme --->点击Create  repository ，OK，这个时候你已经成功的创建了自己的一个项目。

### 3. 配置Git

首先在本地创建`ssh key；`

```bash
$ ssh-keygen -t rsa -C "your_email@youremail.com"
```

后面的`your_email@youremail.com`改为你在github上注册的邮箱，之后会要求确认路径和输入密码，我们这使用默认的一路回车就行。成功的话会在`~/`下生成`.ssh`文件夹，进去，打开`id_rsa.pub`，(默认路径：C:\Users\Administrator\.ssh)复制（ctrl+a ctrl +c进行复制）里面的`key`。

回到github上，进入 Account Settings（账户配置），左边选择SSH Keys，Add SSH Key,title随便填，粘贴在你电脑上生成的key。

![Add SSH Key](http://www.runoob.com/wp-content/uploads/2014/05/github-account.jpg)

为了验证是否成功，在git bash下输入：

```bash
$ ssh -T git@github.com
```

如果是第一次的会提示是否continue，输入yes就会看到：
```bash
You've successfully authenticated, but GitHub does not provide shell access 。这就表示已成功连上github。
```
接下来我们要做的就是把本地仓库传到github上去，在此之前还需要设置username和email，因为github每次commit都会记录他们。

```bash
$ git config --global user.name "your name"
$ git config --global user.email "your_email@youremail.com"
```

进入要上传的仓库，右键git bash，添加远程地址：
```bash
$ git remote add origin git@github.com:yourName/yourRepo.git
```

后面的yourName和yourRepo表示你再github的用户名和刚才新建的仓库，加完之后进入.git，打开config，这里会多出一个remote "origin"内容，这就是刚才添加的远程地址，也可以直接修改config来配置远程地址。

### 3. 提交本地文件到远程的Github仓库

```bash
执行如下命令即可：
$ cd  /yourbookpath
$ git init
$ git remote add origin https://github.com/fengjunhuii/gitbooknotes.git
$ git add .
$ git commit -m "Gitbook的学习笔记"
$ git push -u origin master
```

默认访问地址是：

```C
https://github.com/yourname/repositoryname
```

例如：我的用户名为 fengjunhuii，Github 仓库名为 gitbooknotes，则访问路径是：

[https://github.com/fengjunhuii/gitbooknotes](https://github.com/fengjunhuii/gitbooknotes)

----



### 托管到 Github Pages

```bash
cd E:\Gitbook\GitbookNotes
右键打开Git的shell终端
完成两步测试：$ gitbook install 
			$ gitbook build
			$ gitbook serve
登录http://localhost:4000/ 感觉排版没有问题的话就可以准备提交到Github仓库了。
```

也许你以前也了解 Github 的一个功能： [GitHub Pages](https://pages.github.com/) 。它允许用户在 GitHub 仓库托管你的个人、组织或项目的静态页面（自动识别 html、css、javascript）。

**建立 xxx.github.io 仓库**

要使用这个特性，首先，你必须建立一个严格遵循以下命名要求的仓库：`Github账号名.github.io`举例，我的 Github 账号为 fengjunhuii，则这个仓库应该叫 `fengjunhuii.github.io`。通常，这个仓库被用来作为个人或组织的博客。

**建立 gh-pages 分支**

完成第1步后，在任意一个 Github 仓库中建立一个名为 `gh-pages` 的分支。只要 `gh-pages` 中的内容符合一个静态站点要求，就可以在如下地址中进行访问：`https://Github用户名.gitbooks.io/Github 仓库` 。例如：我的一个 Github 仓库名为 react-notes，则访问路径是：`https://dunwu.github.io/react-notes``

**自动化发布到 gh-pages**

如果每次都手动 git push 到远程 gh-pages 分支，略有点麻烦。

怎么实现自动化发布呢？

有两种方法：

**方法1：使用 gh-pages 插件**

如果你了解 Nodejs，那么最简单的发布方式就是使用 `gh-pages` 插件。

先在本地安装插件

```
$ npm i -D gh-pages
```

然后，在 package.json 文件中添加脚本命令：

如下：`-d` 命令参数后面是要发布的静态站点内容的目录

```json
"scripts": {
  "deploy": "gh-pages -d build"
},
```

**方法二：脚本**

写一个执行 git 命令的脚本就搞定了。

下面的脚本无论是在 bat 或 sh 脚本中都可以执行。

```
cd buildpath
git init
git checkout -b gh-pages
git add .
git commit -am "Update"
git push git@github.com:fengjunhui/gitbook-notes gh-pages --force"
```

-----

-----


