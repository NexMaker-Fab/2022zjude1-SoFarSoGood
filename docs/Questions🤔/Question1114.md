## Question11.14
**关于Arduino和processing互传的问题**
在进行[nexmaker](https://www.nexmaker.com/doc/10Interface-application-programming/processingwitharduino.html)上的两个实验的时候，我们遇到了两个问题。

*Q1:电脑缺少jssc最新的库*
在完成arduino和processing的代码填写后，在运行时processing出现以下界面：   
<div align=center>  <img src="https://raw.githubusercontent.com/HOY78778/picstore/main/img/202211142121739.png" width = 80%/> </div>
经过查询我们在一个[github网址](https://github.com/processing/processing4/issues/525)上找到了答案——对于m1芯片的mac电脑，这个包是没有更新的。解决方法就是在[相关网站](https://github.com/java-native/jssc/)上下载最新的jssc.jar文件并进行替换。    
<img src="https://raw.githubusercontent.com/HOY78778/picstore/main/img/202211142121738.png"/>

*Q2:连接后processing无法找到端口*
在完成jssc.jar的替换之后，我们再一次运行软件，然而processing报出新的错误：  
<div align=center>  <img src="https://raw.githubusercontent.com/HOY78778/picstore/main/img/202211142121740.png" width = 80%/> </div>

这个问题到目前仍然没有得到解决。经过观察，我们发现arduino的串口窗户在按钮按下后出现了对应的字母： 
<div align=center>  <img src="https://raw.githubusercontent.com/HOY78778/picstore/main/img/202211142121125.png" width = 80%/> </div>
然而processing无法进行工作，打开窗口后鼠标会一直处于加载状态，也不会有对应效果。
<div align=center>  <img src="https://raw.githubusercontent.com/HOY78778/picstore/main/img/202211142121127.png" width = 80%/> </div>  
