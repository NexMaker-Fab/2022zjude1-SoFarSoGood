## NO.4 Arduino
### Arduino简介

### 其他开源软件

### 开源硬件特点以及如何选择

### LCD屏显示文字
我们按照[Nexmaker网站](https://www.nexmaker.com/doc/5arduino/Arduino_output.html)里的示意图和代码，还原了LCD屏显示“Hello World”的项目.
最终效果如图所示，涉及的图片和代码不再赘述。
<img src="https://raw.githubusercontent.com/HOY78778/picstore/main/img/202211061136030.jpeg"/>
为了有趣，我们对代码进行了简单的改动，让LCD屏显示我们的组名
<img src="https://raw.githubusercontent.com/HOY78778/picstore/main/img/202211061135951.jpeg"/>
我们连接的线路如图
<img src="https://raw.githubusercontent.com/HOY78778/picstore/main/img/202211061136472.png"/>
<img src="https://raw.githubusercontent.com/HOY78778/picstore/main/img/202211061136579.jpeg"/>
使用的代码如下
<img src="https://raw.githubusercontent.com/HOY78778/picstore/main/img/202211061136377.png"/>

#### 相关问题
1-显示屏闪烁的问题  
在此过程中，我们一开始遇到显示屏闪烁的情况。  
检查后发现是某根线接口出现松动，同时RW线未连接。  

2-显示屏不显示文字的问题  
将滑动变阻器逆时针转到底之后，屏幕上的方格开始出现，但是显示了没有意义的乱码。  
将arduino板重启后，内容正常显示。