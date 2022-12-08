## NO.5 3D printer
### 3D打印背景知识
3D打印（3DP）是一种快速成型技术，其根据数字模型文件，运用粉末状金属或塑料等可粘合材料通过逐层打印实现物体的构造。
<img src="https://raw.githubusercontent.com/HOY78778/picstore/main/img/202212081429141.jpg"/>

* 3D打印常用材料：尼龙、石膏、合金、橡胶、PLA等。
* 3D打印常用领域：3D打印常在模具制造、工业设计等领域被用于制造模型，后逐渐用于一些产品的直接制造，已经有使用这种技术打印而成的零部件。该技术在珠宝、鞋类、工业设计、建筑、工程和施工（AEC）、汽车，航空航天、牙科和医疗产业、教育、地理信息系统、土木工程、枪支以及其他领域都有所应用。
* 3D打印步骤：
  * 通过建模软件建立数字模型文件
  * 3D打印软件将三维模型进行逐层分区生成截面，即切片
  * 打印机设备根据文件内容进行逐层打印，层层堆叠形成立体模型

### 3D打印实践项目
#### 1-图纸和建模
3D打印的实践结合了final project，其中建模部分可以分为主体面板和果蔬积木：  
<div align=center>  <img src="https://raw.githubusercontent.com/HOY78778/picstore/main/img/202212081638486.png" width = 80%/> </div>   
<div align=center>  <img src="https://raw.githubusercontent.com/HOY78778/picstore/main/img/202212021615153.png" width = 80%/> </div>   
<div align=center>  <img src="https://raw.githubusercontent.com/HOY78778/picstore/main/img/202212072050194.png" width = 80%/> </div>   

* 存在的问题：
  目前模型超过了打印机最大的打印尺寸（20*20），且目前阶段没必要将全部的项目使用3d打印。
* 解决方案：
  将目标模型进行切割后，选择小块的迷宫进行打印。目的是为了将打印的模型运用到后期原型实现的实验中，同时测试目前磁吸棒牵引小球的方案可行性。

#### 2-模型导入打印软件
我们使用的软件为flashprint，这个软件可以在[flashprint官网](https://www.flashforge.com/)下载。  
<div align=center>  <img src="https://raw.githubusercontent.com/HOY78778/picstore/main/img/202212081644765.png" width = 80%/> </div> 

##### flashprint使用步骤
1. 打开软件，在左下角选择对应的打印机硬件型号（实验室是 Guider Ⅱs）和喷头直径（0.4mm、0.6mm、0.8mm）。    
<div align=center>  <img src="https://raw.githubusercontent.com/HOY78778/picstore/main/img/202212081643928.png" width = 80%/> </div> 

2. 将需要进行打印的文件（.stl）分别导入到软件中，手动调整打印位置，也可选择“置于地面”、“居中”等。注意，多个模型间应留有2cm左右的间隙。如果超出打印范围，软件会显示红框提醒修改。   
<div align=center>  <img src="https://raw.githubusercontent.com/HOY78778/picstore/main/img/202212081643929.png" width = 80%/> </div> 
<div align=center>  <img src="https://raw.githubusercontent.com/HOY78778/picstore/main/img/202212081643930.png" width = 80%/> </div> 

3. 调整打印参数，可根据不同模型的精度要求调整打印层数、喷头移动速度、填充密度、裙边范围、封底封顶厚度等。不同的参数都会在一定程度上影响打印时间和耗材量。   
<div align=center>  <img src="https://raw.githubusercontent.com/HOY78778/picstore/main/img/202212081643931.png" width = 80%/> </div> 

4. 保存参数设置后开始切片，可以在切片预览页面下方拽动层数或打印路径对切片模型进行预览。   
<div align=center>  <img src="https://raw.githubusercontent.com/HOY78778/picstore/main/img/202212081643933.png" width = 80%/> </div> 
<div align=center>  <img src="https://raw.githubusercontent.com/HOY78778/picstore/main/img/202212081643934.png" width = 80%/> </div> 

5. 保存切片文件（.gx）将电脑与打印机连接，或使用u盘等移动设备将文件传输到打印机中，打印机会本地保存文件数据，录入后即可断开连接。    
<div align=center>  <img src="https://raw.githubusercontent.com/HOY78778/picstore/main/img/202212081648938.png" width = 80%/> </div> 

6. 待打印机喷头和底板预热到目标温度后，开始打印。  

#### 3-3D打印机使用
##### 打印前步骤
1. 打开打印机后部总电源和前方显示屏开关
2. 导入打印文件
3. 开始打印
<div align=center>  <img src="https://raw.githubusercontent.com/HOY78778/picstore/main/img/202212072050013.jpg" width = 80%/> </div> 
<div align=center>  <img src="https://raw.githubusercontent.com/HOY78778/picstore/main/img/202212072050642.jpg" width = 80%/> </div> 

##### 打印结果展示
<div align=left><img src="https://raw.githubusercontent.com/HOY78778/picstore/main/img/202212081657805.jpg" width = 48%/> <img src="https://raw.githubusercontent.com/HOY78778/picstore/main/img/202212072253772.jpeg" width = 49%/> </div>

##### 打印后模型处理
1. 打印完成后取下底板，左右轻掰底板或使用铲刀取下附着在底板的模型。
2. 拆除裙边、支撑
  工具：斜口钳、水口钳
  由于没有以上工具，使用美工刀和老虎钳进行拆除，还可以使用台虎钳进行固定，降低手受伤的风险。
3. 打磨
4. 上色

##### 失败得到的经验和教训
模型与打印机底部没有成功粘连导致打印机空打，耗材融化粘连在喷头上。  
<div align=left><img src="https://raw.githubusercontent.com/HOY78778/picstore/main/img/202212081654571.jpeg" width = 58.5%/> <img src="https://raw.githubusercontent.com/HOY78778/picstore/main/img/202212081654282.jpg" width = 38%/> </div>


可能原因：  
1. 打印平面没有水平，在机器的口令下进行了两次校正
2. 打印文件参数存在问题，不能成功打印
教训：
1. 在打印开始的前1-3层，应等待在打印机旁，以防打印突发状况，有机会进行及时的调整。
2. 参数调整对于模型打印成功与否有巨大影响。
3. 使用3d打印建立模型demo在尺寸比较、方案可行性等方面十分占优势。