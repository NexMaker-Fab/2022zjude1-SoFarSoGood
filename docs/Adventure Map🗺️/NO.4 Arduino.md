## NO.4 Arduino
### 【1】Arduino简介
<img src="https://raw.githubusercontent.com/HOY78778/picstore/main/img/202211052217686.png"/>

Arduino 是一个开源嵌入式硬件平台，用来供使用者制作可交互式的嵌入式项目。   
Arduino 项目[始于2005年](https://web.archive.org/web/20220424201949/https://ieeexplore.ieee.org/document/6750433)，作为意大利伊夫雷亚地区伊夫雷亚交互设计研究所的学生项目，目的是为新手和专业人员提供一种低成本且简单的方法，以创建使用传感器与环境相互作用的设备执行器。   
软件编程方面，通常使用C/C++編程語言，官方提供了一个[Arduino IDE网站](https://www.arduino.cc/)用于开发。    

#### Arduino安装中遇到的问题
由于学校提供的是创客主板，需要下载驱动才能在arduino“工具”一栏中显示端口。但是主板本身的说明书并没有提供mac电脑的驱动安装方式。再加上我们组员在过去遇到过类似的情况，所以我们在网络上寻找解决方法。    
我们找的的[案例](https://blog.csdn.net/HappyLittleMouse/article/details/99706032)是针对ATmega8板子的，不过经过实验可以成功。    
1. **下载VCP驱动**
   驱动可以在[VCP官方网站](https://ftdichip.com/drivers/vcp-drivers/)上下载，只要选择对应的系统即可。
   <img src="https://raw.githubusercontent.com/HOY78778/picstore/main/img/202211101742465.png"/>

2. **电脑安装**
   需要注意的是，对于最新的mac电脑，下载安装的是Beta版本的驱动。
   <img src="https://raw.githubusercontent.com/HOY78778/picstore/main/img/202211101742301.png"/>
   不同于普通安装方式，这个dmg文件下载后，需要先打开找到Installer软件，拖入应用程序中双击打开，然后跟着弹窗指示开放权限即可。成功安装之后再连接创客主板，就能看到Arduino的端口了。
   <div align=center>  <img src="https://raw.githubusercontent.com/HOY78778/picstore/main/img/202211101742760.png" width = 80%/> </div>

----
### 【2】其他开源软件
<div align=center>  <img src="https://raw.githubusercontent.com/shishang00/picstore/main/img/20221105174958.png"> </div>

#### 1.树莓派 Raspberry Pi
<img src="https://raw.githubusercontent.com/HOY78778/picstore/main/img/202211052217376.png"/>

树莓派 Raspberry Pi是 英国树莓派基金会开发的微型单板计算机，目的是以低价硬件及自由软件促进学校的基本电脑科学教育。其官方网站为https://www.raspberrypi.org/ 。   
相比Arduino，树莓派提供更高性能的处理能力，可以轻松实现I/O控制、高速数据通信、视频处理、实时运算等，创客可以在Debian Linux环境下编程，实现各种过去需要在PC环境实现的功能。   
**树莓派的独特优势：**  
- 树莓派仅有信用卡大小，可以直接插入到电视中。
- 传统电脑平替，实现文字处理、电子表格和游戏等功能。
- 运算能力强大，适配众多热门编程语言（Python、Java、C/C++等），可搭载的Linux或Windows系统。
因此，涉及到人工智能、人脸识别等需要高运算力的功能开发时。树莓派会成为比较合适的选择。
- 只有树莓派能做的：机器视觉、视频解码、3D游戏等。  

**劣势：**    
- Arduino对于传感器和硬件都是随插随用，树莓派在使用传感器前需要安装与之匹配的驱动程序以及编写程序才能控制硬件。
- 硬件控制需要的系统和操作复杂。Arduino直接编写程序代码就能完成指令，树莓派需要安装操作系统后，安装代码库来控制GPIO引脚（硬件链接处）才能实现对硬件的控制。
- Arduino只需要输入几行代码就能轻松完成的工作，树莓派需要数小时才能完成。
<div align=center>  <img src="https://raw.githubusercontent.com/shishang00/picstore/main/img/20221105175029.png" width = 120%/> </div>
<div align=center>  <img src="https://raw.githubusercontent.com/shishang00/picstore/main/img/20221107113933.png" width = 130%/> </div>

#### 2.狗板 BeagleBone
<div align=center>  <img src="https://raw.githubusercontent.com/HOY78778/picstore/main/img/202211052217375.png" width = 200%/> </div>

BeagleBone是为喜爱嵌入式Linux系统的玩家量身打造的产品，其价格低廉，硬件扩展性强。其官方网站为：https://beagleboard.org/bone ，汇聚了Beagle的介绍、教程与相关项目。  
**狗板能做什么？**    
BeagleBone拥有Arduino良好的可扩展性，兼具Raspberry Pi快速处理器和Linux灵活的开发环境。因为它的输入输功能完善，并便于接入网络，所以我们可以通过Web端监测它回传的数据。BeagleBoard有一个更大，性能更强的版本——BeagleBoard。如果你需要更强的扩展性，那么BeagleBoard是一个不错的选择。BeagleBone还可以当做BeagleBoard或Beagleboard-xM的外接USB或网络扩展模块。
<div align=center>  <img src="https://raw.githubusercontent.com/shishang00/picstore/main/img/20221107114051.png" width = 140%/> </div>

**狗板适合哪些人群？**    
BeagleBone能够满足包括游戏外设、家庭和工业自动化、消费类医疗器械、打印机、智能收费与称重系统、教育终端和高级玩具等在内的各个领域的不同需求。   
beaglebone无疑是树莓派的最佳竞争者，对于树莓派来说可能个人玩家更多，很多天马行空的个人创作项目都来自树莓派，而beaglebone更多用于物联网和工业应用，因为丰富的接口更适用于这些。


#### 3.micro:bit
<div align=center>  <img src="https://raw.githubusercontent.com/HOY78778/picstore/main/img/202211052217687.png" width = 250%/> </div>

Micro Bit（也叫做BBC Micro Bit，或风格化为micro:bit）是基于ARM架构的嵌入式系统，由BBC设计用于英国的计算机教育。其官方网站为：https://www.microbit.org。  
**硬件方面**    
micro:bit的微控制器用的是NXP KL26Z,板载低功耗蓝牙芯片nRF51822,三轴磁力计MAG3110和三轴加速度计MMA8652。
有复位按键，显示用的25个LED,拓展的IO都有金手指引出来了。相对于Arduino,由于板子上多了蓝牙芯片和加速度传感器，磁力计，板子的可玩性提高了不少。    
开发板可以与手机的蓝牙相连，实现手机与micro: bit 相互通信，还可以通过传感器做记步和指南针的实验，用上了传感器，功能更加丰富样。    
**软件方面**    
micro: bit支持JavaScript 模块编辑器，Python 编辑器，也可以用安卓，IOS软件将应用程序通过蓝牙无线下载到micro: bit 开发板。    
用户可以选择自己觉得容易上手编程环境。像网页版micro: bit编程界面，模块化编程，支持一键下载，用起来并不难。  
**Micro Bit的独特优势**
- Micro Bit响应快速
它允许你编写简单的程序上传后可以马上执行显示出来，帮助你快速了解计算机运行和编程的原理。
- 适用范围广泛
不管你只是想学习编程的初级原理还是想做一些真实的项目，这个主板都可以支持，它现在支持三种编程方式，分别是图形化编程（积木拖拽），python，javascript。任何一种都能让你学习基本编程思路。
- 降低入门门槛
学习纯软件编程可能需要学习非常深入才能做一个可玩有意义的东西。前期对时间和精力的投入，让你会有99.9%的可能性从入门放放弃。而这个主板能即刻执行你编写的程序，即使只是一句点亮LED的代码，及时的反馈能帮助你坚持学习和激发创造的灵感。  

<div align=center>  <img src="https://raw.githubusercontent.com/shishang00/picstore/main/img/20221105175236.png"> </div>

<div align=center>  <img src="https://raw.githubusercontent.com/shishang00/picstore/main/img/20221105175251.png"> </div>


#### 4.虚谷号
<div align=center>  <img src="https://raw.githubusercontent.com/HOY78778/picstore/main/img/202211052217684.jpeg" width = 250%/> </div>

虚谷号是一个中国原创的开源硬件平台，面向人工智能教学和Python编程学习。板内集成高性能处理器和通用单片机，内置多功能扩展接口和多种通信接口，可以看成是树莓派3与Arduino UNO的合体。其官方网站为：http://www.vvboard.com.cn/

**硬件方面：**    
虚谷号是一款面向人工智能教学和Python编程学习的中国原创开源硬件，板内集成了高性能处理器和通用单片机，内置多功能扩展接口和多种通信接口，为人工智能和Python编程教学提供了完整的课程资源包。同时，它具有Li nux的操作系统，又支持Arduino生态系统的各种开源硬件，这就类似于一块树莓派加一块Arduino板，而且还具备U盘模式。因此，它既可以连接上显示器、键盘鼠标成为一款独立卡片电脑，又可以通过数据线连到计算机上作为一个类似于Micro：bit的外接开源硬件  
**软件方面：**    
虚谷号运行完整的Linux系统，同时预装了部分编程教学软件。   
虚谷号预装的是Arduino1.86版，它可以支持Arduino代码编程教学，且内置了Ardublock图形化编程工具，Ardublock类似于Mixly( 米思奇)，可以实现图形化编程，支持上传到Arduino板，实现脱机运行，支持Linux的Ardublock版本，还可以选择中文界面，并且支持的硬件类型也很多，完全可以胜任开源硬件的教学。   
虚谷号预装了Python 2.7和Python 3.5，可以方便地开展Python教学，且编程环境预装了jupyter notebook，但是jupyternotebook占有资源比较大，建议使用IDLE。如果在Windows环境安装Python，系统一般默认同时安装了IDLE，在虚谷号上可以用“sudo apt-get install idle3”完成安装，且在网络环境比较好的情况下很快就能完成。    

<div align=center>  <img src="https://raw.githubusercontent.com/shishang00/picstore/main/img/20221105175057.png"> </div>

<div align=center>  <img src="https://raw.githubusercontent.com/shishang00/picstore/main/img/20221105175130.png"> </div>


**虚谷号能做什么？**    
1. Python编程：学习Python要装太多的库，借助虚谷号可以不用装任何软件，利用浏览器就能学习。
2. 人工智能体验和编程：虚谷号内置了百度AI开放平台，可以实现很多人工智能的应用，打开内置的学习笔记，既可以运行体验，也能修改代码在线编程。
3. 物联网和智能家居：作为“虚谷物联”项目的最重要组成部分，虚谷号内置了SIoT服务器和必要的库，加上GPIO功能，做物联网数据采集和远程控制非常方便。

**虚谷号适合哪些人使用？**    
虚谷号面向高年级学生，尤其是中学生，重点关注Python的代码编程。你可以将虚谷号看成是一台“Linux电脑+Arduino”，用Linux系统处理复杂的信息，用Arduino来获取传感器信息和控制各种执行器。在虚谷号的帮助下，无论是物联网还是人工智能作品，都可以快速搭建。  
<div align=center>  <img src="https://raw.githubusercontent.com/shishang00/picstore/main/img/20221105175149.png" width = 140%> </div>  


#### 开源硬件特点以及如何选择
- 如果开发的产品需要保证尺寸较小，推荐Arduino。Arduino的款式多样，但让Arduino区别于其他平台的特性在于，它拥有特别的微处理器，以及一些软件。它使用Atmel公司的一款微处理器嵌入式系统，体积小，价格实惠。对于那些需要尺寸非常小巧的项目来说，你可以花费1到2美元购买Atmel的这些芯片，并使用Arduino Bootloader（一个赋予Arduino基本功能的程序），安装后，你就又拥有了一个Arduino。
- 对于需要电池供电的项目，推荐Arduino。Arduino功耗是最低地。但是Arduino拥有更广泛的空间，因为他可以和很多不同的输入电压的设备一起工作。这样就要求Arduino需要使用不同型号的电池，并且就算电池没电也能继续运转。Arduino是一个扩展性很好的平台，便于与各种设备交互。对于初学者来说，在进行一些小型项目时，它是绝佳的选择。
- 如果需要支持用户界面，推荐使用Raspberry Pi。因为它拥有一个HDMI输出。这意味着，你可以接入键鼠和直接接入到你的电视。在这点看来，你拥有了一台功能全备的电脑，并且拥有用户操作界面。这样使得Raspberry Pi可以用于在需要与用户交互的项目中，以低成本构建web浏览设备。事实上，只是出于娱乐性质，我们把Arduino开发工具安装在Raspberry Pi上，并在Raspberry Pi写以一个简单程序并下载到Aruduino上。Raspberry Pi适合用于需要用户界面和需要网络支持的项目，其性价比较高。
- 如果你的项目需要连接网络，比较推荐BeagleBone或Raspberry Pi。这两款都是真正的Linux电脑。他们都内建以太网接口和USB，便于用来连接网络。通过USB接口，你可以连接一个无线模块，那样就可以无需网线就能接入网络。另外，Linux系统拥有很多内置组件，提供高级的网络特性。
- 如果你的项目需要接入外部感应设备，推荐Arduino和BeagleBone。Arduino使用的电压不同（3.3V 或者 5V），这样就可以轻易的连接到不同的外部设备。而BeagleBone只能连接3.3V的外部设备，并在某些情况下，还需要加入电阻或者其他外部电路才能连接外部设备。Arduino和BeagleBone都有模拟数字信号接口，这让你轻松的连接输出不同电压的设备。
- 如果你是刚入门的小白，没有编程和电子基础，可以拿microbit，图形化编程，可以培养编程的思维能力，并且只要传感器多，就可以学一些基础。

信息来源：    
https://hujiaweiyinger.lofter.com/post/1e55ea_6a6f8a    
三大主流开源硬件对比：Arduino vs BeagleBone vs Raspberr(https://hujiaweiyinger.lofter.com/post/1e55ea_6a6f8a)     
https://openprocessing.org    
http://stackoverflow.com/questions/5291769/open-framework-v-s-processing    
http://sodaplay.com/    
http://lightcycle.org/       
http://www.tom-carden.co.uk/tag/applets/page/3/     
http://www.airtightinteractive.com/category/processing/       
http://www.local-guru.net/blog/pages/processing-sketches      
http://cs.smith.edu/dftwiki/index.php/CSC220_Processing_Sketch_Examples     
http://hascanvas.com/     
http://www.local-guru.net/blog/pages/processing-sketches     
http://processingjs.nihongoresources.com/processing%20on%20the%20web/      
http://staticvoidgames.com/tutorials/deployment/basicProcessingExample      
http://www.learningprocessing.com/       
https://www.processing.org/     

----
### 【3】实践项目-LCD屏显示文字
我们按照[Nexmaker网站](https://www.nexmaker.com/doc/5arduino/Arduino_output.html)里的示意图和代码，还原了LCD屏显示“Hello World”的项目。
最终效果如图所示，涉及的图片和代码不再赘述。
<img src="https://raw.githubusercontent.com/HOY78778/picstore/main/img/202211061136030.jpeg"/>
为了有趣，我们对代码进行了简单的改动，让LCD屏显示我们的组名：
<img src="https://raw.githubusercontent.com/HOY78778/picstore/main/img/202211061135951.jpeg"/>
我们连接的线路如图
<img src="https://raw.githubusercontent.com/HOY78778/picstore/main/img/202211061136579.jpeg"/>
<img src="https://raw.githubusercontent.com/HOY78778/picstore/main/img/202211061136472.png"/>

使用的代码如下
<img src="https://raw.githubusercontent.com/HOY78778/picstore/main/img/202211061136377.png"/>

#### 遇到的问题与解决
1. 显示屏闪烁的问题  
在此过程中，我们一开始遇到显示屏闪烁的情况。  
检查后发现是某根线接口出现松动，同时RW线未连接。  

2. 显示屏不显示文字的问题  
将滑动变阻器逆时针转到底之后，屏幕上的方格开始出现，但是显示了没有意义的乱码。  
将arduino板重启后，内容正常显示。  

---
### 【4】实践项目-LCD屏显示障碍物距离
我们结合Nexmaker网站中的[LCD屏幕显示案例](https://www.nexmaker.com/doc/5arduino/Arduino_output.html)和[超声波测距案例](https://www.nexmaker.com/doc/5arduino/Arduino_Input.html)，制作了LCD屏显示障碍物距离的硬件。   
其连接线路如图：   
<img src="https://raw.githubusercontent.com/HOY78778/picstore/main/img/202211101727473.jpeg"/>
<img src="https://raw.githubusercontent.com/HOY78778/picstore/main/img/202211101727645.png"/>
最终呈现的结果可以通过[此链接🔗](https://b23.tv/67iPBWi)看到。    
我们最后使用的代码如下：    
<pre> 
/*LiquidCrystal Library - Hello World
Demonstrates the use a 16x2 LCD display. The LiquidCrystal
library works with all LCD displays that are compatible with the
Hitachi HD44780 driver. There are many of them out there, and you
can usually tell them by the 16-pin interface.
This sketch prints "Hello World!" to the LCD
and shows the time.
The circuit:
* LCD RS pin to digital pin 12
* LCD Enable pin to digital pin 11
* LCD D4 pin to digital pin 5
* LCD D5 pin to digital pin 4
* LCD D6 pin to digital pin 3
* LCD D7 pin to digital pin 2
* LCD R/W pin to ground
* LCD VSS pin to ground
* LCD VCC pin to 5V
* 10K resistor:
* ends to +5V and ground
* wiper to LCD VO pin (pin 3)
Library originally added 18 Apr 2008
by David A. Mellis
library modified 5 Jul 2009
by Limor Fried (http://www.ladyada.net)
example added 9 Jul 2009
by Tom Igoe
modified 22 Nov 2010
by Tom Igoe
This example code is in the public domain.
http://www.arduino.cc/en/Tutorial/LiquidCrystal
*/

/*
Arduino SR04
5V --- VCC
A0 --- Trig
A1 --- Echo
GND --- GND
*/

// include the library code:
#include <LiquidCrystal.h>

// initialize the library with the numbers of the interface pins
LiquidCrystal lcd(12, 11, 5, 4, 3, 2);

#define TrigPin A0 
// __|^|_____________
// 10us or more HITH SIGNAL will drive it work for one time

#define EchoPin A1 
// ______|^^^^^^^^|__ 
// PULSE WIDTH stand for distance(the time of ultrasound transmit, both go and back)

// pulse width WILL NOT long than 38ms, it means timeout
// Distance = Speed x Time
// Speed of sound ~= 340m/s = 0.340mm/us
int count = 0;
long duration;
// PULSE WIDTH

void setup() {
    // set Serial communication
    Serial.begin(115200);
    // set pin mode
    pinMode(TrigPin, OUTPUT);
    pinMode(EchoPin, INPUT);
    // init pin
    digitalWrite(TrigPin, LOW);
    // set up the LCD's number of columns and rows:
    lcd.begin(16, 2); 
    delay(1);
}

void loop() { 
    // set the cursor to column 0, line 1
    // (note: line 1 is the second row, since counting begins with 0):
    lcd.setCursor(0, 0);
    lcd.print("the distance is:");
    lcd.setCursor(14, 1);
    lcd.print("mm");
    // Print a message to the LCD.
    lcd.setCursor(0, 1);
    lcd.print(getDistance() );

    delay(1000);
    lcd.clear();
}

long getDistance() {
    // trig
    digitalWrite(TrigPin, LOW);
    delayMicroseconds(2);
    digitalWrite(TrigPin, HIGH);
    delayMicroseconds(10);
    digitalWrite(TrigPin, LOW);
    // echo
    duration = pulseIn(EchoPin, HIGH); // unit: us
    return duration * 0.34029 / 2; // unit: mm
}</pre>

