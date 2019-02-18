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

### 3. 提交本地文件到远程的Github仓库
```bash
cd E:\Gitbook\GitbookNotes
右键打开Git的shell终端
完成两步测试：$ gitbook install 
			$ gitbook build
			$ gitbook serve
登录http://localhost:4000/ 感觉排版没有问题的话就可以准备提交到Github仓库了。
执行如下命令即可：（适当调整哈）
$ git init
Initialized empty Git repository in E:/Gitbook/GitbookNotes/.git/
$ git remote add origin https://github.com/fengjunhuii/gitbooknotes.git
$ git add .
$ git commit -m "第一次接触gitbook的学习笔记"

​```
*** Please tell me who you are.
Run
  git config --global user.email "1888xxx@163.com"  (你的Github邮箱)
  git config --global user.name "fengbaobao"        （你的Github用户名）
再次提交则OK
$ git commit -am "第一次接触gitbook的学习笔记"
​```
$ git push -u origin master       （登录你的用户名和密码--后期添加秘钥了再更新）
​```
 今天使用在自己笔记本本地磁盘上使用Git命令行执行"git push"然后输入github的用户名和密码之后，报如下错误：
![rejected]  master->master(fetch first)  
error:failed to push some refs to 'https://github.com/xxx/xxx.git'
解决思路：
	执行(先备份你的文件)
	$ git pull，
	然后再执行push就可以了
	$ git push
​```



git checkout -b gh-pages
git add .
git commit -am "Update"
git push git@github.com:dunwu/gitbook-notes gh-pages --force"
```

默认访问地址是：

```
https://Github用户名.gitbooks.io/Github 仓库/content/
```

例如：我的用户名为 dunwu，Github 仓库名为 gitbook-notes，则访问路径是：

[https://dunwu.gitbooks.io/gitbook-notes/content/](https://dunwu.gitbooks.io/gitbook-notes/content/)

### 托管到 Github Pages

也许你以前也了解 Github 的一个功能： [GitHub Pages](https://pages.github.com/) 。它允许用户在 GitHub 仓库托管你的个人、组织或项目的静态页面（自动识别 html、css、javascript）。

**建立 xxx.github.io 仓库**

要使用这个特性，首先，你必须建立一个严格遵循以下命名要求的仓库：`Github账号名.github.io`举例，我的 Github 账号为 dunwu，则这个仓库应该叫 `dunwu.github.io`。通常，这个仓库被用来作为个人或组织的博客。

**建立 gh-pages 分支**

完成第1步后，在任意一个 Github 仓库中建立一个名为 `gh-pages` 的分支。只要 `gh-pages` 中的内容符合一个静态站点要求，就可以在如下地址中进行访问：`https://Github用户名.gitbooks.io/Github 仓库` 。例如：我的一个 Github 仓库名为 react-notes，则访问路径是：`https://dunwu.github.io/react-notes`

**自动化发布到 gh-pages**

如果每次都手动 git push 到远程 gh-pages 分支，略有点麻烦。

怎么实现自动化发布呢？

有两种方法：

**使用 gh-pages 插件**

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

**脚本**

写一个执行 git 命令的脚本就搞定了。

下面的脚本无论是在 bat 或 sh 脚本中都可以执行。

```
cd build
git init
git checkout -b gh-pages
git add .
git commit -am "Update"
git push git@github.com:dunwu/gitbook-notes gh-pages --force"
```

-----

-----

## 托管到 gitbook.com

[GitBook.com](https://www.gitbook.com/ )  是使用 GitBook 格式创建和托管图书的在线平台。它提供托管，协作功能和易于使用的编辑器。----不推荐，bug太多，推荐使用Github,全球通用。

**创建新书**
如下图所示，根据个人需求，选择一个模板创建你的电子书。
![gitbook-settings](https://raw.githubusercontent.com/dunwu/gitbook-notes/master/assets/images/gitbook-new-book.png)

**设置书的基本信息**
![gitbook-settings](https://raw.githubusercontent.com/dunwu/gitbook-notes/master/assets/images/gitbook-settings.png)

**clone 到本地**
Gitbook.com 会为每本书创建一个 git 仓库。

如下图所示，拷贝 git 地址，然后 `git clone` 到本地。
![gitbook-settings](https://raw.githubusercontent.com/dunwu/gitbook-notes/master/assets/images/gitbook-clone.png)

**发布**
在本地按照 Gitbook 规范编辑电子书，然后 `git push` 到 Gitbook 的远程仓库。

默认访问地址是：https://用户名.gitbooks.io/项目名/content/

例如：我的用户名为 dunwu，一个电子书项目名为 test，则访问路径是： `https://dunwu.gitbooks.io/test/content/`

当然，如果你有自己的域名，也可以设置 Domains 选项，来指定访问路径为你的域。
