## Question10.27

*Q1:之前改了文件夹名称，导致可以clone但是上传失败。*

![](https://cdn.jsdelivr.net/gh/shishang00/picstore@main/img/f0a5bc5de1ec7ec4f87f34952e828e5.jpg)
![](https://cdn.jsdelivr.net/gh/shishang00/picstore@main/img/733742152d7494b4cfa0afdd6b02392.jpg)

remove了文件和文件夹，重新clone项目并选择正确的存储路径解决了这个问题。  

*Q2:我们在picgo中上传图片时屡屡显示上传失败。*

![](https://raw.githubusercontent.com/shishang00/picstore/main/img/20221027213921.png)

我们发现是由于进行图床设置时，“设定仓库名”一栏我们直接从github网页上复制了  [username]/[用户名]  ，而复制过来的字符间存在英文空格，在删除了英文空格后我们能够成功将图片上传。

![](https://raw.githubusercontent.com/shishang00/picstore/main/img/20221027213858.png)
