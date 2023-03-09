## NO.7 IoT
### IoT背景知识
物联网（ IoT ，Internet of things ）即“万物相连的互联网”，是互联网基础上的延伸和扩展的网络，将各种信息传感设备与网络结合起来而形成的一个巨大网络，实现任何时间、任何地点，人、机、物的互联互通。   
<img src="https://raw.githubusercontent.com/HOY78778/picstore/main/img/202212151530349.jpg"/>

### IoT常见硬件
#### NodeMCU
NodeMCU,是一个开源的物联网平台。 它使用Lua脚本语言编程。该平台基于eLua 开源项目,底层使用ESP8266 sdk 0.9.5版本。该平台使用了很多开源项目, 例如 lua-cjson, spiffs. NodeMCU包含了可以运行在 esp8266 Wi-Fi SoC芯片之上的固件,以及基于ESP-12模组的硬件。
[NodeMCU官网地址](http://www.nodemcu.com/index_cn.html)
<div align=center><img src="https://raw.githubusercontent.com/HOY78778/picstore/main/img/202212151539145.jpeg" width = 32%/> <img src="https://raw.githubusercontent.com/HOY78778/picstore/main/img/202212151539147.jpeg" width = 32%/> <img src="https://raw.githubusercontent.com/HOY78778/picstore/main/img/202212151539148.jpeg" width = 32%/> </div>

#### 鸿蒙OS
华为鸿蒙系统（HUAWEI Harmony OS），是华为公司在2019年8月9日于东莞举行华为开发者大会（HDC.2019）上正式发布的操作系统。   
<div align=center>  <img src="https://raw.githubusercontent.com/HOY78778/picstore/main/img/202212151545493.jpeg" width = 80%/> </div>   

华为鸿蒙系统是一款全新的面向全场景的分布式操作系统，创造一个超级虚拟终端互联的世界，将人、设备、场景有机地联系在一起，将消费者在全场景生活中接触的多种智能终端，实现极速发现、极速连接、硬件互助、资源共享，用合适的设备提供场景体验。其核心特点就是物联网，并提供一种可视化编程方案。  
[鸿蒙OS官网](https://consumer.huawei.com/cn/harmonyos-3/?utm_medium=cpc&utm_source=bdpz&utm_campaign=zdpz_PC_harmony_tab1_title1)
<div align=center>  <img src="https://raw.githubusercontent.com/HOY78778/picstore/main/img/202212151545325.jpeg" width = 80%/> </div>   

### IoT常见软件
#### 阿里云
阿里云，阿里巴巴集团旗下云计算品牌，全球卓越的云计算技术和服务提供商。创立于2009年，在杭州、北京、硅谷等地设有研发中心和运营机构。其应用服务中包括物联网套件，帮助用户快速搭建稳定可靠的物联网应用。  
[阿里云官网](https://www.aliyun.com/?utm_content=se_1013083955)

#### 机智云
机智云是广州机智云物联网科技有限公司注册商标及主营产品名称。是AIoT开发和云服务平台，工业互联网平台服务商。于2014年推出机智云物联网开发和云服务平台。  
[机智云官网](https://www.gizwits.com)

#### homekit
HomeKit，是苹果2014年发布的智能家居平台。支持网关、智能音箱、各类传感器的连接和使用，适用于家居、安防、娱乐等多种场景。   
[HomeKit官网](https://www.apple.com.cn/home-app/accessories/)


### IoT实践
我们使用esp8266模块（一个类似arduino的模块）和阿里云平台进行实践，具体操作参考[以下网址](https://www.nexmaker.com/doc/9IOT/NodeMCUESP8266_ALiYun.html)。

在实践过程中发现几个问题：
- 首先是阿里云界面调整，带来一定的理解难度。注意，必须先开通“公共实例”模块才能进入产品界面。
<div align=center>  <img src="https://raw.githubusercontent.com/HOY78778/picstore/main/img/202303091948352.png" width = 44%/> <img src="https://raw.githubusercontent.com/HOY78778/picstore/main/img/202303091948144.png" width = 54%/> </div>

- 其次，在arduino IDE文件编辑时，忘记确认wifi名的大小写问题，导致联网失败。检查后成功。  
<div align=center>  <img src="https://raw.githubusercontent.com/HOY78778/picstore/main/img/202303091950785.png" width = 60%/> </div>   
<div align=center>  <img src="https://raw.githubusercontent.com/HOY78778/picstore/main/img/202303091950382.png" width = 60%/> </div>   

- 最后，联网成功后控制界面仍然没有对应模块，是因为“功能定义”栏下的功能尚未发布。
<div align=center>  <img src="https://raw.githubusercontent.com/HOY78778/picstore/main/img/202303091951249.png" width = 33%/> <img src="https://raw.githubusercontent.com/HOY78778/picstore/main/img/202303091951224.png" width = 32%/> <img src="https://raw.githubusercontent.com/HOY78778/picstore/main/img/202303091951226.png" width = 33%/>  </div>

成功后，演示视频：
<iframe width="315" height="560" src="//player.bilibili.com/player.html?aid=695629425&bvid=BV1g24y1b7Xq&cid=1045864752&page=1" frameborder="0" allowfullscreen></iframe>