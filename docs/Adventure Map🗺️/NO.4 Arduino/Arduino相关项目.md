### 实践项目-LCD屏显示文字
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

### 实践项目-LCD屏显示障碍物距离
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
