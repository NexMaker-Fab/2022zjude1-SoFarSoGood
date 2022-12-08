## NO.1 Website Setup
### 网站搭建
第一节课，我们学习了网站的搭建
网站搭建原理可以参考notion网站
> notion是一款功能强大的笔记网站，其强大功能之一就是数据库和对应的呈现。如图，database以表格的形式储存，表格的不同维度代表不同的标签、分类，而数据呈现的view可以选择画廊形式、TODO形式、表格形式等等。
> 
<div align=center>  <img src="https://raw.githubusercontent.com/HOY78778/picstore/main/img/202210081920298.png" width = 80%/> </div>

 <div align=center> <img src="https://raw.githubusercontent.com/HOY78778/picstore/main/img/202210081920796.png" width = 80%/> </div>
  
对于本节课而言，我们将数据储存在github上（包括图片、文本等），经过html/markdown语言的翻译，成为网页架构。
在实际操作中，我们需要经历：
* github上建立数据库
* 利用github desktop进行本地下载
* 通过visual studio code进行本地编辑
* 上传和html编译。  
具体的步骤请参考[本页面](https://www.nexmaker.com/doc/1projectmanage/github&docsify.html)

### 网站搭建遇到的问题
整个过程中，我们组很多学生都遇到了相同的问题：文档初始化（npm i docsify-cli -g）的部分在终端里报错了。
<div align=center> <img src="https://raw.githubusercontent.com/HOY78778/picstore/main/img/202210081936086.png"
width = 70%/> </div>
经过网络查询，我们了解到可能是安装包和mac系统的不兼容（因为问题多发于mac系统），具体参见[此博客](https://blog.csdn.net/Sunny_lxm/article/details/105642296)。
网上给出的解决方案是在命令行之前加上sudo语句，并在之后输入个人密码。在如此操作之后安装包下载成功，我们又经过基本初始化，本地文件夹成功出现docs！
<div align=center> <img src="https://raw.githubusercontent.com/HOY78778/picstore/main/img/202210081935308.png" width = 70%/> </div>

### 图片上传
图床和图片上传我们在之前就遇到过。有一些较为老旧的论坛网站是没有图片上传功能的，此时有需要的用户会通过网络图床+html代码粘贴的方式实现图片呈现。PicGo的原理本质上也是相同的。
在实际操作中，我们需要进行以下步骤：
* 图床的Github进行基本设置
* 在上传区对图片进行上传
* 去相册里复制对应格式的代码并进行粘贴   
具体的步骤请参考[本页面](https://www.nexmaker.com/doc/1projectmanage/imageuploadservice.html)

### 图片上传遇到的问题
我们在使用PicGo时，最先遇到的问题是app无法打开。这个问题在mac上被观察到，无论如何点击图标都没有弹窗，检查应用程序也没问题，遇到问题的同学感到非常无助。
实际上，我们发现PicGo在底层栏没有图标，而是在顶栏有图标。这种情况在一些mac上的小软件上是存在的（比如腾讯柠檬杀毒软件）。  

<div align=center> <img src="https://raw.githubusercontent.com/HOY78778/picstore/main/img/202210081937769.png"
width = 60%/> </div>

因为电脑版本的问题，实际设置时我们遵循了[知乎网站](https://zhuanlan.zhihu.com/p/489236769)上的步骤。  
实际操作时，我们并不理解“设定存储路径”的意义，向老师询问后了解，这个路径是github上图片储存的路径。PicGo上的图片会储存在github特定的文档中，以减轻网页文件的负担.

### 关于Markdown
在利用Markdown搭建网站的时候，我们对成员介绍页面进行了别致的安排。  
首先，我们找到包含[Markdown语言网](https://markdown.com.cn/basic-syntax/htmls.html)，利用上面的指南进行编写。  
其次，我们利用[emoji网站](https://emojipedia.org/woman-zombie/)获取对应emoji的代码。  
最后，我们通过[虚拟形象建模网站readplayer](https://readyplayer.me/hub)来表示我们的成员形象。  

### 视频嵌入
为了提供足够的内容，我们对部分项目的展示采用了视频形式。我们将相关视频传到B站，这是一个没有广告同时在分享按钮提供嵌入代码的视频网站。   
<img src="https://raw.githubusercontent.com/HOY78778/picstore/main/img/202212081438767.png"/>

在使用原始的嵌入代码时，我们发现视频效果不好。其高度受到限制，只能展示很小的画面（尤其对于竖屏视频）。   
<img src="https://raw.githubusercontent.com/HOY78778/picstore/main/img/202212081441810.png"/>
<img src="https://raw.githubusercontent.com/HOY78778/picstore/main/img/202212081441809.png"/>

为了解决这个问题，我们在网上寻找了很多方法，在[CSDN网站](https://blog.csdn.net/a5563184/article/details/105349728/?utm_medium=distribute.pc_relevant.none-task-blog-2~default~baidujs_baidulandingword~default-0--blog-104306140.pc_relevant_aa2&spm=1001.2101.3001.4242.1&utm_relevant_index=3)上我们找到了可行的方案。   

我们使用的嵌入代码如下：   
<pre> 

<iframe width="560" height="315" src="视频框代码" frameborder="0" allowfullscreen></iframe>

</pre>


### 未解决的问题
- [x] 目前搭建的网页没有顶栏
- [ ] 未来考虑使用html实现更出色的UI和更灵活的交互