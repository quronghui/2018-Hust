# OPENBCI
## 文档一 ：OPENBCI-DIY手册
### 塑料支柱的安装
+ 防止板子短路
### 供电
+ 使用电池供电
+ 买电池的级联器盒子
+ 电池的供电线性比较好，没有细微波动，对脑电没有干扰，正
常的适配器或者充电器或者电脑 USB 供电（只要源头是交流电）均会收到交流电的干扰，
频率为 50Hz
### 固体硬件FW
- usb dongle ？ 蓝牙适配器
- Arduino   ？ 开源计算机硬件和软件的公司，同时兼有项目和用户社区，
+  USB Dongle 串口芯片为 FT231XQ，驱动为 D2XX 型
+ USB Dongle 与 OpenBCI 的无线蓝牙会进行握手和连接
#### 确定硬件是否正常
- Arduino UNO 已经和 OBCI 成功握手并建立连接;
- **看一下UNO的连接，UNO复位后，输出 ADS 设备 ID 为 0x3E**
#### OpenBCI GUI/FW  问题
1. SRB
    + 通道默认设置为使用 BIAS、开启 SRB2、关闭 SRB1
    + N 通道的检测效果好于 P 通道
2. BIAS
    + 对于 EEG 来说上述的 BIAS 有必要打开
    + BIAS：简单来说就相当于我们所说的地 Ground ？？
    + 查BIAS怎么连接的
## 文档二：原理图
### Power --> 使用的是电源管理芯片

#### 5V LDO Regulator 线性稳压芯片
+ 对比他们线性稳压之间的区别
    + AMS1117-5V
    + LP2992IM5-5.0
#### 3.3V
+ LP5907 SM
####  AVDD
+ 接 0.1 uf and 1uf 到地
+ 有接AVSS 和 AGND 的
### SD Card
+ 使用SPI的通行方式？？
### LIS3DHTR Acceleromerer

+ MEMS数字输出,超低功耗3轴运动加速传感器
### Anlog Input 
+ 为啥每个电极通道都要按照第二种方式进行连接
+ 把AVDD AGND 都通过了TPD4E1B06
#### [TPD4E1B06](https://pdf1.alldatasheet.com/datasheet-pdf/view/847223/TI1/TPD4E1B06DRLR.html) 
+ 双向 4 通道高速 ESD 保护器件
+ 采用第二种连接方式；
+ 电路中保持了两种连接方式，通过软件配置进行选择 --> 这种思想不错
+ [购买链接](https://item.taobao.com/item.htm?spm=a230r.1.14.21.386e6cdbIWeOqt&id=578983690696&ns=1&abbucket=10#detail)
#### [CAY16-3322F4LF](https://pdf1.alldatasheet.com/datasheet-pdf/view/597832/BOURNS/CAY16-49R9F4LF.html)
+ [命名规则](https://wenku.baidu.com/view/9750d359f01dc281e53af097.html)
+ 
+ 电阻阵列
+ 阻值：2.2k
#### [CKCL44X7R1H102M085AA](https://product.tdk.com/en/search/capacitor/ceramic/mlcc/info?part_no=CKCL44X7R1H102M085AA)
+ 电容阵列
+ 容值：102
### BLE
+ 蓝牙模块
+ [BLE RFD22301](https://pdf1.alldatasheet.com/datasheet-pdf/view/816191/TDK/CKCL44X7R1H102M085AA_16.html) 
### [ATMEGA328P-AU](https://www.alldatasheet.com/view.jsp?Searchword=ATMEGA328P-AU)
+ 主控芯片

### ADS1299
+ _PWDN : 上拉到 DVDD
+ RESET : 高电平
#### BIASIN 和 BIASINV 区别 ？？
- 连接方式和ADS1299 的不同
- BIASINV 用做级联的时候
- 用 BIASIN 没有问题
#### 它的模拟地和数字地采用的是电容连接
+ 它的 AVSS 和 AGND 连接方式：使用电容
+ 并没有严格的划分出数字地和模拟地
#### start
+ Start pin 没有使用