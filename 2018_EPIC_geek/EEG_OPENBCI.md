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
### AVDD
+ 接 0.1 uf and 1uf 到地
+ 有接AVSS 和 AGND 的