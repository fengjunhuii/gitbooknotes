# Typora极简教程

> ” **Markdown** 是一种**轻量级**标记语言，创始人是**约翰·格鲁伯**（John Gruber）。它允许人们 “使用易读易写的纯文本格式编写文档，然后转换成有效的 HTML 文档。”
>
> 现在很多软件 (如 Visual Studio Code、Leanote、为知笔记、有道云，Simplenote、Atom) 或网站 (如 Github、维基、简书) 都已支持 Markdown 语法了。很多下载回来的软件说明也是 .md 或 .markdown 格式的文本文档，不管你是想要写作还是需要阅读，都需要一个简单好用的 Markdown 编辑器/阅读器。
> **我选择Typora **

![Typora心情](https://tse3.mm.bing.net/th?id=OIP.K7VytgeHysfJoBGy43mQ3AHaEo&pid=Api)

## 安装 Typora 编辑器
+ Typora 下载地址：https://typora.io/
（注：Gitbook editor相对Typora来说不是太好用,哈哈，个人感觉，非喜勿喷。）

+ 虽然现在的 [**Markdown 编辑器**](https://www.iplaysoft.com/tag/markdown)多如牛毛，但他们的交互形式基本都是将「编辑」和「预览」分离开来的，要么是直接左右排列编辑和预览窗口，要么是要在两种模式之间来回切换，实在是麻烦且不够直观。
+ 而 Typora 则是用创新完全颠覆了这种传统的交互模式，它只使用一个窗口，却能优雅地实现同时将代码编辑与预览「一体化」结合起来！从而为用户带来更加流畅直观的「所见即所得的 Markdown 写作体验」。

## 如何使用呢？
你只需在 Typora 打字时输入正确的 Markdown 语法标记 (如 ##二级标题、 **粗体**)，软件就像触发了键盘快捷键一样，将对应的文字会即时转变为它们应该成为的样子。斜体、加粗、插入图片、引用、插入图片、代码、表格、有序列表等等操作就在你敲完代码的一瞬间通通魔法般地“变成现实”，你在编辑器上看到的直接就是 Markdown 最终的排版效果了，这种行云流水般的写作体验真的非常非常的棒！

![Typora](https://img.iplaysoft.com/wp-content/uploads/2016/typora/typora-gif.gif)

## Typora操作

** [官网教程](https://support.typora.io/) :https://support.typora.io/**

这里放一个小姐姐的视频，声音特别好听，讲的也很不错。

<iframe src="https://www.bilibili.com/video/av18508430/" scrolling="no" border="0" frameborder="no" framespacing="0" allowfullscreen="true"> </iframe>



### 1. 基本操作

#### 1.1 内容目录
------
- 语法
```
目录
[toc]  放到开头就可以了
```

#### 1.2 标题
------
```
#       一级标题    
##      二级标题    
###     三级标题    
####    四级标题    
#####   五级标题    
######  六级标题    
```
#### 1.3 引用
------
```
> 引用内容1
> 引用内容2
>> 引用内容3
```
- 效果
> 引用内容1
> 引用内容2
>
> > 引用内容3

### 2. 代码
#### 2.1 单行代码
------
```
`String str1 = "hello";`
```
- 效果
```
String str1 = "hello";
```
#### 2.2 多行代码
------
```
~~~java c 回车，右下输入语言,效果如下：
```

```
int a = 10;
int b = 20;
```
#### 2.3 html的div格式
<div>
Markdown here will not be **parsed**
</div>

### 3. 列表
#### 3.1 无序列表
------
```
* 无序列表1
+ 无序列表2
- 无序列表3
```
#### 3.2 多行无序列表
------
- 语法
```
* 多行无序列表1
TAB * 多行无序列表2
TAB TAB * 多行无序列表3
```
- 效果
- 多行无序列表1
  - 多行无序列表2
    - 多行无序列表3

#### 3.3 有序列表
------
```
1. 有序列表1
2. 有序列表2
3. 有序列表3
```
- 效果
1. 有序列表1
2. 有序列表2
3. 有序列表3

#### 3.4 表格
------
```
ctrl + T 同时按下 可以设置行和列以及对齐方式
|姓名|性别|年龄|手机号|
|:---|:--:|:--:|---:|
|张三|男|21|18975346876|
|李四|女|23|17789548964|
|王五|男|25|15876513546|
```

- 效果
| 姓名 | 性别 | 年龄 | 手机号      |
| ---- | ---- | ---- | ----------- |
| 张三 | 男   | 21   | 18975346876 |
| 李四 | 女   | 23   | 17789548964 |
| 王五 | 男   | 25   | 15876513546 |


### 4. 链接

#### 4.1 图片
+ 好的图片网站：https://imgur.com/

------
- 语法1（*本地图片*）
```
[图片上传失败...需要指定图片的路径，容易失败(image-61fd19-1520850984854)]
可以使用与链接类似的方式创建图像：只需在方括号前使用感叹号。链接文本将成为图像的替代文本，链接URL指定图像源：
An image: ![gras](img/image.jpg)
```
An image: ![gras](img/image.jpg)

- 语法2（*网络图片*）
```
![typora.jpg](http://upload.art.ifeng.com/2017/0425/1493105660290.jpg)
```
![typora.jpg](http://upload.art.ifeng.com/2017/0425/1493105660290.jpg)

- 效果2
![img](http://upload.art.ifeng.com/2017/0425/1493105660290.jpg)

#### 4.2 超链接
------
- 语法1（*行内式链接*）
```
[百度][https://www.baidu.com/]
```
- 效果1
[百度][[https://www.baidu.com/\]](https://img.laonanren.com/Public/pageimg/20170531/1496202128997579.jpg)

- 语法2（*参考式链接*）
```
[CSDN网址]:https://www.csdn.net/
```
- 效果2
[CSDN唐宇迪]:https://www.csdn.net/


- 语法3（*自动链接*）
[https://github.com/](https://edu.csdn.net/lecturer/1079)

#### 4.3 视频链接
----
```
<iframe src="xxx://xxx.com/视频资源具体.mp4" scrolling="no" border="0" frameborder="no" framespacing="0" allowfullscreen="true"> </iframe>
注意：1）替换链接的地址即可，注意添加https:的协议名 2）注意allowfullscreen一定要为TRUE。
最近的哔哩哔哩嵌入代码有问题，所以只能用原始地址咯。

```
<iframe src="https://www.bilibili.com/video/av17983189/?p=3" frameborder="0" width="640" height="430"  allowfullscreen="true"></iframe>

----
```
附：加一个YouTube的视频供大家参考。
```
<iframe width="560" height="315" src="https://www.youtube.com/embed/w2itwFJCgFQ" frameborder="0" allow="accelerometer; autoplay; encrypted-media; gyroscope; picture-in-picture" allowfullscreen></iframe>


### 5. 其他
#### 5.1 斜体
------
```
*斜体*
_斜体_
```
#### 5.2 加粗
------
```
**加粗**
__加粗__
```
#### 5.3 下划线
------
```
<u>下划线</u>
```
#### 5.4 删除线
------

```
~~删除线~~
```

- 效果

~~删除线~~

#### 5.5 分隔线
------

```
四个及以上的-，三个及以上的* 回车
```
- 效果

-------

#### 5.6 注脚
------
```
Typora[^1]
[^1]A markdown editor
```
- 效果
Typora[[1\]](https://www.jianshu.com/p/a6a6a22e9393#fn1)

#### 5.7 上下标
------
```mathematica
数学公式
$$回车 或者行内$f(x)=$
先$$回车，然后输入你要输入的东西
^上小标   _下划线 下角标
注意学习英文字母的表示方法，否则后面都不明白怎么写。
{\displaystyle f(x\mid \mu ,\sigma ^{2})={\frac {1}{\sqrt {2\pi \sigma ^{2}}}}e^{-{\frac {(x-\mu )^{2}}{2\sigma ^{2}}}}}
先$$回车，3^2=9
先$$回车，3^{(3-1)}=9
先$$回车，H_2SO_4
先$$回车，H_{2SO_4}
如果数学公式实在写不出来，那么进入![wiki](https://en.wikipedia.org/wiki/Normal_distribution),复制wiki的数学表达式就可以看到写法，是通用的。
```

$$
{\displaystyle f(x\mid \mu ,\sigma ^{2})={\frac {1}{\sqrt {2\pi \sigma ^{2}}}}e^{-{\frac {(x-\mu )^{2}}{2\sigma ^{2}}}}}
$$

$$
3^2
$$

$$
3^{(3-1)}=9
$$

$$
H_2SO_4
$$

HTML
GitBook支持在文本中使用原始HTML，不处理HTML中的Markdown语法：


#### 5.8 符号的输入

------
\#可以将#作为本身输出

```
\\   反斜线   \`   反引号    \*   星号
\_   底线     \{ \}  花括号  \[ \]  方括号
\( \)  括弧   \#   井字号    \+   加号  
\.   英文句点  \!   惊叹号    \-   减号
```
- 效果
\ ` * _ { } [ ] ( ) # + - . !


#### 5.9 特殊字符
------
- 语法
```HTML
&copy;      版权        
&reg;       注册商标  
&trade;     商标
&nbsp;      空格       
&lt;        小于号       &gt;        大于号
&ne;        不等号       &le;        小于等于     &ge;        大于等于
&yen;       元
&times;     乘号    &divide;    除号   &plusmn;    正负号
```

- 效果
  ©  ®  ™     <     \>    ≠    ≤   ≥
  ¥   ×   ÷   ±
  
- 附
[HTML特殊字符编码对照表](https://www.jb51.net/onlineread/htmlchar.htm)

~~~
未完待续....
~~~