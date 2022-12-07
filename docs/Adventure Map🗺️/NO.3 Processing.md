## NO.3 Processing
### 关于Processing
> [Processing](https://processing.org/)是一门开源编程语言，提供了对图片，动画和声音进行编程的环境。  
> 
Processing起初是专门为视觉交互和媒体艺术设计而创建的，它是面向艺术家和设计师所开发的语言，类似Adobe全家桶这样的工具。相比昂贵的全家桶，Processing是开源免费的，而且有着广泛的参考案例和库。  

Processing的发明者最初将Processing视作一个代码素描本。因其强大的功能，常被用作更自由的艺术创作，用于网页制作和平面设计。  
<img src="https://raw.githubusercontent.com/HOY78778/picstore/main/img/202210301409065.webp"/>
<img src="https://raw.githubusercontent.com/HOY78778/picstore/main/img/202210301409476.webp"/>
随着Processing的发展，它可以和arduino合作控制各种互动硬件。再加上对动画、声音编辑的强大功能，Processing常被用于制作交互和展览装置  
<img src="https://raw.githubusercontent.com/HOY78778/picstore/main/img/202210301409182.webp"/>  

### 其他交互类软件
我们了解到，和processing类似的交互软件还包括[TouchDesign](https://derivative.ca/)
> TouchDesigner是一门[视觉化程式设计语言](https://zh.m.wikipedia.org/wiki/視覺化程式設計語言)，它采用图形化界面建立节点或OP元件并将它们相互连接，进而实现用户想要的多媒体特效。它可以被用于实现投影、虚拟现实、艺术装置控制、各类演出等功能。
> 

### 用鼠标、键盘控制界面
在相关领域，Processing有很多有趣的网站，比如[**Openprocessing**](https://openprocessing.org)，这是一个开放式的社群平台，拥有各种有趣的案例。优秀案例每周都会被推出，同时提供新手一键入门的简单案例。  
<img src="https://raw.githubusercontent.com/HOY78778/picstore/main/img/202211061202482.png"/>

- [*SayHi&Enter*](https://openprocessing.org/sketch/1583233)
该项目可以将你输入的文字、emoji转化为网页里的图形，并提供堆叠、旋转、甩出等交互效果。  
<img src="https://raw.githubusercontent.com/HOY78778/picstore/main/img/202211061207860.png"/>

- [*A Shooter Game*](https://openprocessing.org/sketch/453716)
该项目让你通过键盘操作，对目标进行射击并获得胜利，是一个有趣的小游戏。  
<img src="https://raw.githubusercontent.com/HOY78778/picstore/main/img/202211061207976.png"/>


### Processing和Arduino连接
我们按照[nexmaker网站](https://www.nexmaker.com/doc/10Interface-application-programming/processingwitharduino.html)的要求进行连接.实验过程中我们遇到了两个问题：  

*Q1:电脑缺少jssc最新的库*    
在完成arduino和processing的代码填写后，在运行时processing出现以下界面：   
<div align=left>  <img src="https://raw.githubusercontent.com/HOY78778/picstore/main/img/202211142121739.png" width = 80%/> </div>

经过查询我们在一个[github网址](https://github.com/processing/processing4/issues/525)上找到了答案——对于m1芯片的mac电脑，这个包是没有更新的。解决方法就是在[相关网站](https://github.com/java-native/jssc/)上下载最新的jssc.jar文件并进行替换。    
<img src="https://raw.githubusercontent.com/HOY78778/picstore/main/img/202211142121738.png"/>

------
*Q2:连接后processing无法找到端口*   
在完成jssc.jar的替换之后，我们再一次运行软件，然而processing报出新的错误：  
<div align=left>  <img src="https://raw.githubusercontent.com/HOY78778/picstore/main/img/202211142121740.png" width = 80%/> </div>
这个问题到目前仍然没有得到解决。经过观察，我们发现arduino的串口窗户在按钮按下后出现了对应的字母： 
<div align=left>  <img src="https://raw.githubusercontent.com/HOY78778/picstore/main/img/202211142121125.png" width = 80%/> </div>
然而processing无法进行工作，打开窗口后鼠标会一直处于加载状态，也不会有对应效果。
<div align=left>  <img src="https://raw.githubusercontent.com/HOY78778/picstore/main/img/202211142121127.png" width = 80%/> </div>  


我们参考老师的方法，更改了processing里COM口的名称。  
<img src="https://raw.githubusercontent.com/HOY78778/picstore/main/img/202211161011870.png"/>
尝试之后仍然是port not found： 
<img src="https://raw.githubusercontent.com/HOY78778/picstore/main/img/202211161012676.png"/>
我们还将串口名称改为全名，但是依然没有变化。和其他同学交流后了解到，win系统的串口名称为“COMX”，mac系统的则不一样，那位同学换成win电脑之后尝试成功了。
<div align=left>  <img src="https://raw.githubusercontent.com/HOY78778/picstore/main/img/202211161012929.png" width = 80%/> </div>

这个问题在mac电脑上比较常见，在外网检索的时候我们发现了很多类似的情况。最终，我们在[arduino论坛](https://forum.arduino.cc/t/com-port-issue-on-processing-3-3-app-on-macbook-pro/445834)上找到了答案   
<img src="https://raw.githubusercontent.com/HOY78778/picstore/main/img/202211171407549.png"/>
最终我们采用同样的格式，实现了processing和arduino之间的连接
<img src="https://raw.githubusercontent.com/HOY78778/picstore/main/img/202211171407119.png"/>
<div align=left>  <img src="https://raw.githubusercontent.com/HOY78778/picstore/main/img/202211171407558.png" width = 80%/> </div>    

----
最终，我们实验的展示如下：
* [Processing控制arduino的LED小灯](https://b23.tv/9Hsjq8y)
<iframe width="315" height="560" src="//player.bilibili.com/player.html?aid=432690443&bvid=BV1ZG411F7Eb&cid=894192137&page=1" frameborder="0" allowfullscreen></iframe>

* [arduino控制processing图形](https://b23.tv/tCGHfwK)
<iframe width="315" height="560" src="//player.bilibili.com/player.html?aid=220131443&bvid=BV1e841187wZ&cid=894267741&page=1" frameborder="0" allowfullscreen></iframe>


