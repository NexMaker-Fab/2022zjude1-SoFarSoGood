## NO.4 Arduino
### Arduino简介
<img src="https://raw.githubusercontent.com/HOY78778/picstore/main/img/202211052217686.png"/>

Arduino 是一个开源嵌入式硬件平台，用来供使用者制作可交互式的嵌入式项目。   
Arduino 项目[始于2005年](https://web.archive.org/web/20220424201949/https://ieeexplore.ieee.org/document/6750433)，作为意大利伊夫雷亚地区伊夫雷亚交互设计研究所的学生项目，目的是为新手和专业人员提供一种低成本且简单的方法，以创建使用传感器与环境相互作用的设备执行器。   
软件编程方面，通常使用C/C++編程語言，官方提供了一个[Arduino IDE网站](https://www.arduino.cc/)用于开发。    

### Arduino安装中遇到的问题
由于学校提供的是创客主板，需要下载驱动才能在arduino“工具”一栏中显示端口。但是主板本身的说明书并没有提供mac电脑的驱动安装方式。再加上我们组员在过去遇到过类似的情况，所以我们在网络上寻找解决方法。    
我们找的的[案例](https://blog.csdn.net/HappyLittleMouse/article/details/99706032)是针对ATmega8板子的，不过经过实验可以成功。    
1. **下载VCP驱动**
   驱动可以在[VCP官方网站](https://ftdichip.com/drivers/vcp-drivers/)上下载，只要选择对应的系统即可。
   <img src="https://raw.githubusercontent.com/HOY78778/picstore/main/img/202211101742465.png"/>

2. **电脑安装**
   需要注意的是，对于最新的mac电脑，下载安装的是Beta版本的驱动。
   <img src="https://raw.githubusercontent.com/HOY78778/picstore/main/img/202211101742301.png"/>
   不同于普通安装方式，这个dmg文件下载后，需要先打开找到Installer软件，拖入应用程序中双击打开，然后跟着弹窗指示开放权限即可。成功安装之后再连接创客主板，就能看到Arduino的端口了。
   <img src="https://raw.githubusercontent.com/HOY78778/picstore/main/img/202211101742760.png"/>
   