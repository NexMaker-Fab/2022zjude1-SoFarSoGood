## NO.6 laser cutting
### 激光切割背景知识
激光切割又名镭射切割（英语：Laser cutting）是一种使用激光光切割材料的技术，通常用于工业制造应用，但也开始被学校、小企业和业余爱好者使用。   
<img src="https://raw.githubusercontent.com/HOY78778/picstore/main/img/202212081429144.jpg"/>

* 非金属激光切割
  * [气体（CO2）激光切割](https://baike.baidu.com/item/CO2%E6%BF%80%E5%85%89%E5%88%87%E5%89%B2%E6%9C%BA/8386634)
    * 一般靠激光电源带动激光管发光，通过几个反光镜的折射，使光线传输到激光头，再由激光头上安装的聚焦镜将光线汇聚成为一点，而这一点可以达到很高的温度，从而将材料瞬间升华为气体，由抽风机吸走，这样就达到切割的目的。一般激光切割机使用的激光管内填充的主要气体为CO2，因此这种激光管称为CO2激光管。
    * CO2激光器适用于切割、钻孔和雕刻，可用于许多材料的工业切割，包括钛、不锈钢、低碳钢、铝、塑料、木材、工程木材、蜡、织物和纸张。
  * [固体（光纤）激光切割](https://baike.baidu.com/item/%E5%85%89%E7%BA%A4%E6%BF%80%E5%85%89%E5%88%87%E5%89%B2%E6%9C%BA/5924412)
    * 新型光纤激光器输出高能量密度的激光束，并聚集在工件表面上，使工件上被超细焦点光斑照射的区域瞬间熔化和气化，通过数控机械系统移动光斑照射位置而实现自动切割。
    * 光纤激光器已逐渐发展成为高精度激光加工、激光雷达系统、空间技术、激光医学等领域中的重要候选者。
* 金属激光切割
  * 钕 (Nd) 和钕钇铝石榴石 (Nd:YAG) 激光器在类型上相同，仅在应用上有所不同。
    * Nd 用于钻孔和需要高能量但低重复的地方。
    * Nd:YAG 激光器用于需要非常高功率的地方以及用于钻孔和雕刻。

---
### arduino和激光切割结合的案例
#### Hackvent 圣诞日历
> 除了树木和坐在架子上的精灵的典型圣诞装饰品外，Tom Goff  受到儿子要求的启发，开始制作一个 DIY“Hackvent”日历。该项目与传统的降临节日历的不同之处在于，它具有一排两打彩色灯——一个代表 12 月 1 日至 24 日——只要按下按钮，它们就会依次亮起。25 日，随着铃儿响叮当的响起，所有的小灯都熄灭了，一颗白色的大星星开始闪烁。
>
<img src="https://raw.githubusercontent.com/HOY78778/picstore/main/img/202212211405100.webp"/>

为了创建日历，此处设计了一个 2D面板，每个LED都有对应切口，还有一个按钮用于单个按钮。面板使用一个简单的2D CAD包——AutoCAD LT 2022，后期使用LightBurn 软件来实现激光切割机的兼容。  
<div align=left><img src="https://raw.githubusercontent.com/HOY78778/picstore/main/img/202212211405126.webp" width = 51%/> <img src="https://raw.githubusercontent.com/HOY78778/picstore/main/img/202212211405125.webp" width = 48%/> </div>

激光切割一块胶合板后，是电路的设计。这些组件包括一个Arduino Mega、25 个 LED 和直接由 Mega 的 GPIO 引脚驱动的电阻器、一个从其嵌入式 ROM 发出音乐的 ISD1760 模块，以及一个 3W 扬声器。 其电路组成与焊接示意如下：  
<div align=left><img src="https://raw.githubusercontent.com/HOY78778/picstore/main/img/202212211409267.webp" width = 47%/> <img src="https://raw.githubusercontent.com/HOY78778/picstore/main/img/202212211405710.jpeg" width = 52%/> </div>

最后，涉及的代码如下：
<pre> 
int LEDpins[25] = {31, 2, 3, 4, 5, 6, 7, 8, 9, 10, 11, 12, 13, 14, 15, 16, 17, 18, 19, 20, 21, 22, 23, 24, 25};

int incrementButtonPin = 30;
int incrementButtonValue;
int toneButtonPin = 27;

void setup()
{
  for (int i = 0; i < 26; i++)
  {
    pinMode(LEDpins[i], OUTPUT);
    digitalWrite(LEDpins[i], LOW); 
  }

  pinMode(incrementButtonPin, INPUT_PULLUP); // this is what you want
  pinMode(toneButtonPin, OUTPUT); // this is what you want
  digitalWrite(toneButtonPin, HIGH);
}


void loop()
{

  incrementButtonValue = digitalRead(incrementButtonPin);
  if (incrementButtonValue == LOW) {
    for (int i = 0; i < 25; i++)
    {
      if (digitalRead(LEDpins[i]) == LOW)
      {
        digitalWrite(LEDpins[i], HIGH);
        break; // no carry to other lights so no more loops
      }

    }
  }


  if (digitalRead(25) == HIGH) {
    delay(200);

    for (int j = 24; j >= 0; j--)
    {
      if (digitalRead(LEDpins[j]) == HIGH)
      {
        digitalWrite(LEDpins[j], LOW);
        delay(100);
      }
    }

    for (int j = 1; j <= 40; j = j + 1) { // Start our for loop
      digitalWrite(toneButtonPin, LOW);
      digitalWrite(25, HIGH); //Turn red LED on
      delay(200);             //Leave on for redOnTime
      digitalWrite(25, LOW); //Turn red LED off
      delay(200);            //Leave off for redOffTime
    }


  }

  delay(10); // debounce switch
  while ( incrementButtonValue == LOW) { // wait until switch is high again
    incrementButtonValue = digitalRead(incrementButtonPin);
  }
  digitalWrite(toneButtonPin, HIGH);
}
</pre> 

详细信息参考[此网站](https://www.instructables.com/Hackvent-Calendar/)
