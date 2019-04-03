# 访问吴哥的虚拟机：   \\192.168.3.208
+ adb push \\192.168.3.208\Android\prog\sensor\sensor /data
+ 公司名称：武汉艾瓦客机器人有限公司 纳税人识别号：91420100MA4KWP0725
开发票或者收据
+ 地址：武汉市东湖新技术开发区关东工业园东信路11号C栋三层3196、3216室
+ 电话：027-65525216
+ 开户行：中国建设银行股份有限公司武汉佳园支行 账号：42050112714400000416
+ 嘉立创：该客户编号为：330791R，密码为：A11111

# 一、A33 CPU + AXP223电源管理芯片 

## 1、性能
+  DC --> DC manager  
+  Over Voltage/Current/Temperature Protection  and Under voltage protection  
+ System management : support soft reset and hard reset  
+ Power On/Off/Rest : automatically identify long press/short press
+ By IRQ tell A33 core

## 2、封装
+ 8mm * 8mm QFN 68pin (方形扁平无引脚封装（Quad Flat No-lead Package))    
+ 2.9V - 6.3V USB/AC apdaptor for voltage   

## 3、Pin
+ CHGLED : used to show status and warning  
+ TS : detection the battery temperature  

## 4、Price  <7元
+ [A33+AXP233 价格-24](https://detail.1688.com/offer/548966466989.html?spm=a261b.2187593.1998088710.24.saGN8S "A33+axp233的价格")  

## 5、A33 CPU
+ A33 平板电脑CPU芯片 四核处理器 --18元

## 二、内存、闪存

### 1、内存 RAM、 DDR  
**区别 ： 工作频率的大小**
| 内存       | 英文全称    | 子类    |  
| :-----: | :----------: | :-------: |  
| RAM | Random Access Merory | SARM 、DRAM、SDRAM--同步动态随机存储器 |
| DDR | Double DAT a Rate |  准确的将应该叫DDR SDRAM，双倍速率同步动态随机存储器 |
| DDR*(1-3) | 时钟频率提高，数据传输速率提高 |   

example ： DDR333 ---> 工作频率 = 333/2 = 166MHZ  

### 2、闪存 

| 闪存 | 分类--->> feature |
| :-----: | :-----: |  
| ROM | PROM（可编程RO7M）、EPROM（可编程可擦除ROM）、EEPROM（电可编程可擦除ROM） |  
| FLASH | NOR FLASH和NAND FLASH ， 具备EEPROM的性能，较快速的读取数据 |
| EMMC | 为了减少版本更换时，兼容时间

**异同 ：RAM、DDR为内存，掉电信息就没了，ROM、FLASH、EMMC为闪存，掉电信息还可以保存**   
+ Gb--对应的单位是bit；转化为 GB = Gb/8 

## 三、DDR3 SDRAM  

### 1、DDR3 Feature
+ 存储阵列，将数据填充进阵列
+ B --> Bank的地址编号；C --> 列地址编号；R --> 行地址编号  
+ 寻址方式：先找到第几Bank，然后定位到列，行  
+ 8 Bank设计 --> 就是有8个表格     

| 内存大小 | 型号 |  封装 |单价 |  
| :----:  | :--: | :--: | :--: |  
| 1Gb DDR3L SDRAM | H5TC8G63CMR-xxA | FBGA 98 BALL | 53一片 |  

### 2、Notes
+ 高频信号 ---> 考虑电磁干扰
+ 贴片 ---> STM工艺  

## 四、EMMC

### 1、emmc 芯片参数的介绍
 + [KLM8G1WEPD-B031](https://www.elnec.com/en/device/Samsung/KLM8G1WEPD-B031+%5BFBGA153%5D/ )  
 ——介绍了芯片参数各位的含义

| 型号 | size |  封装 |单价 | datesheet |  
| :----:  | :--: | :--: | :--: | :----: |  
| KLM8G1WEPD-B031 | 8G | FBGA ball 153 | 53/piece | 没有PD的手册，A33 上是 eMMC-BGA169 |
| KLM8G1WEMB-B031 | 8G | 

## 五、自己制作计算价格
| A33厂家 | 型号 | AXP223 | CPU | DDR3 | Flash | PCB裸板-4层 | Other | Price|
| :----:  | :---: |:--: | :--: | :--: | :---: | :---: | :---: | :---: |
| 锐尔威视RERVISION | ARM Cortex-A7、1.2GHZ主频 | 7 | A33-18 | 1G - 53 | 8G - 53 | 10-piece 200 | 10 | 161 |

## 六、厂家订购
## 1、锐尔威视RERVISION 
+ ARM Cortex-A7、1.2GHZ主频 
+ DDR+FLASH 1G+8G  DDR+FLASH 512M+4G

| Piece | Price（Vstar）|   512M+4G（Vstar）_price  |  Price (插针)|
| :----:| :----:| :----: |  :----:|
| 1-9 | 168 | Vstar-定制，无现货 | 135|
| 10-100 | 165 | 价格介于两者之间 | 130 |
| 100-500 | 160 | | 127|
| 500-1K | 155 | | 120 |
| 1K-3K | 145 | 115 | 110 |
| 3K-1w | 135 | | 100 |
| > 1W | 130 | |97|

# AXP223 电源管理芯片
## 一、Question
### 1、线性稳压器 —— 作用？
+ 电压可调
+ 驱动能力通过电流体现

### 2、CHGLED
+ CHGLED：Internal integration NMOS with 100mA drive capability ，can be used to drive vibration motor and charge LED (驱动马达和电源指示灯)
+ 当REG32[2]=0 , PIN驱动能力100mA,将微型马达接至3.3V，串联限流电阻，可以直接驱动马达。
+ REG32[2]=1，pin为充电状态、过压过温等报警指示
+ 寄存器的设置通过，与和或来实现，对某一位的设置

### 3、DC-DC同步电压转换器
+ 电压调节范围 + 驱动时电流的大小
### 4、E-Gauge 电量计系统
+ 提供电源管理信息 ： 剩余电量、充电状态、剩余电池使用时间和充电时间
+ 低电警告及保护
+ 芯片温度信息

### 5、System Management
+ Suport Soft Reset and Hard Reset
+ Suport Soft Power-off and Hard-Power-off and external Wakeup Triggers
### 6、Voltage
- ACIN 直流电源的输入，并不是电池
- ACIN -- Input Voltage -- -0.3-11V -- Limit_Voltage
- ACIN -- **Input** -- 3.8-6.3 V -- Normal_ Voltage
- ACIN Under Voltage Lochout (欠压锁定保护) -- 3.8V
- 我们的Demo板上没有的
+ VBUS --  同上
+ Mirco_USB的电压输入
- VBAT 外接电池电压
- BAT Charge Target Voltage -- 4.2V
+ NTC -- 高温/低温下故障限压
- DCDC 1
- 用不到某路DC-DC时，将对应的LX管脚悬空就行
- DCDC1 Output_Voltage --> 3 V 
- Output  -->  VCC-3V0  and  VCC-LCD  
- Link 10uF 电容过滤
- Input Source -->**PS**  <--> 作为所有DC-DC 的电压输入
- **PS** --> 点亮 LED 1
+ VCC-RTC 
+ Output --3 V
- DLDOs 
- Input Voltage --> PS
- DLDO 1/2 --> Output_Voltage --> VCC-IO-WIFI --> 3.3 V
- DLDO 3 --> Output_Voltage --> DOVDD-CSI  --> 2.8 V
- Link 4.7 uF 电容进行过滤
+ ELDOs 
+ Input_Voltage --> VCC-3V0
+ ELDO 2 --> Output_Voltage --> DVDD1V8-CSI  --> 1.8 V
+ Link 4.7 uF 电容进行过滤
- CHGLED
- R = 2 OHM 
- OHM --> **阻抗** 当输入1KHz的正弦波信号，它呈现的阻抗值是二欧姆
- CHGLED：Internal integration NMOS with 100mA drive capability ，can be used to drive
vibration motor and charge LED (驱动马达和电源指示灯)
- 没有说输出电压值？

## 三、工作模式和复位
### 1、Power Enable Key
- Power 电源一开始是低电平，当输出电压达到稳定值时，Power拉高，实现上电复位
+ 识别：长按和短按 ——> 做出相应的动作
- 开机
- 开机：PEK > ONLEVEL （时间）
- DC-DC 和LDO 按设定的时序顺序软启动
+ 关机
+ 要求：PEK_time > IRQLEVEL AXP223进入关机状态时，写寄存器 “1” 通知AXP223计入关机状态
+ 除LDO1 :其余电源全部关闭
+ 当 PEK > OFFLEVEL（ = 6s ）系统自动关闭除LDO1以外的输出
- 此处的指示灯：VCC-3V0 这个电压作为开关机的指示灯就行
### 2、Sleep and Wakeup
+ 打开唤醒： REG31[3] 设置为 1 ；
+ 唤醒触发源：PEK下降沿唤醒 REG44[5] = 1 ;
### 3、自适应充电过程
+ 充电：AXP223向Host发出IRQ,充电开始，同时，CHGLED输出低电平，驱动外部发光二极管
+ 充电电流 ：配置REG33H[3：0] = 450mA/1200mA
### 4、CHGLED的两种指示灯驱动模式
### 5、温度监控，并不是测值
+ NTC温敏电阻:25度，10KOhm、1%的NTC温敏电阻
+ TS 输出 REG84H 设置的恒定电流，此电流 I 流过温敏电阻，得到检测电压 V , V与设置值比较。
+ REG 84H ADC采样速率设置，TS管脚控制
+ 电池需要有温敏电阻，不用外加温敏电阻了
### 6、E-Gauge电量计系统
+ 各路ADC的使能控制和采样速度，REG84H 进行设置
+ 电池电流方向是充电还是放电由REG00H[2]指示
### 7、REG33H 充电控制 
+ 默认值：AXP223 寄存器篇
+ 充电目标电压设置 和 充电电流的设置
+ 充电环路限流设置：REG 35H
### 8、REG 36H KEY 按键参数设置
+ 长按键时间设置
+ 长按自启设置
+ 开机时间设置
### 9、VLTF-charge 电池充电 低/高温门限设置
+ V L/H TF - charge 电池充电 低/高温门限设置
+ + V L/H TF - discharge 电池放电 低/高温门限设置
### 10、REG E6H 电池电量低电报警门限设置
+ 5% - 20%
+ 0% - 15%

# AP6210
## 1、蓝牙信号线问题
+ BT_WAKE :HOST wake-up Bluetooth device :V=3V
+ BT_HOST_WAKE :Bluetooth device to wake-up HOST : Robot-->Host 唤醒的时候出现瞬间电压值，Host接收到信息
+ BT_RST_N : HOST enable the pin -- low, the BT is OFF.  一直为高，正常。
## 2、两路电源
+ VBAT : -0.5 - 5.5 V  Typ -- 3.6
+ VDDIO: -0.5 - 3.6 V  Typ -- 3.3V --VCC-WIFI
## 3、接口定义
+ WiFi Interface :SDIO V2.0
+ BT Interface : UART/PCM
## 4、BlueTooth Specification
+ VBAT=3.6V ; VDDIO=3.3V ; Temp:25°C
+ Host interface :UART
+ 四线的UART Interface 作为 Bluetooth Interface
## 5、BT and WLAN 的 enabled pin
+ WL_REG_ON : HOST enable the pin -- low, the wlan is OFF/Reset
+ BT_RST_N : HOST enable the pin -- low, the BT is OFF.

# Audio Code
+ **audio Code** 在理想状况下，对于录音过程，只需要将麦克风获取到的analog信号通过ADC转换为digital信号并存储即可，对于播放音过程，只需要将digital信号通过DAC转换为analog并输出到speaker播放即可.
+ 实现回音消除，噪音抵消，以及ALC/Limiter等，当然它也实现了最重要的AD和DA功能
+ [audio code 内部功能](https://blog.csdn.net/xiaolei05/article/details/7216348)
## 1、Analog（模拟） Audio Codec
### a. SNR
-  Support stereo audio DAC ：100 dB SNR
- 8KHz to 192KHz DAC sample rate
+ **SNR信噪比**为有用信号功率(Power of Signal)与噪声功率(Power of Noise)的比。因此为幅度（Amplitude）比的平方.
+ [分贝与信噪比](https://blog.csdn.net/xiahouzuoxin/article/details/10949887)
### b. Input/Output
+ Support four analog audio inputs:  Two microphone differential inputs for main mic
- Output : Support two analog audio outputs
### c. PCM interface
+ Two PCM interface connected with BB and BT.
## 2、audio code
+ It provides a stereo DAC for playback and stereo ADC for recording
### a. microphone input
+ 两组 MIC input ，A33引出一组。（核心板尝试引出两组MIC input）

# PXVF3000-KIT XMOS 麦克风阵列评估板
+ [XMOS](http://www.xmos.com/products/silicon/xcore-voice/xvf)
## 1、Define
+ Suport 4 路数字 PDM 麦克风圆形或线形阵列
+ 阵列前端算法完成了远场拾音、回音消除、波束成型、噪声抑制及声源定位功能
- Output：三种--USB UAC1.0 协议传输音频给操作系统平台
- Input: 三种--USB 传输播放的声音信号，同时作为参考信号
### a. MIC
+ MIC 1~6 圆形均匀分布， 半径 43mm
+ Invensence ICS-41350 PDM 麦克风
### b. PXVF3000
+ 需要外接 4 个 PDM 麦克风和 USB 5V 电源供电
+ 4个PDM mic: 使用MIC1/3/4/6
+ 支持 AEC，语音唤醒及打断
+ 噪声抑制（高达 15dB 抑制优化）
#### (1)  Micro_usb 与OTG
+ usb 接口有5Pin :Vbus、GND、D+、D-、ID-悬空
+ 主动供电：由Host（电脑） 向 device（手机） 进行供电
- OTG 接口有5Pin :Vbus、GND、D+、D-、ID-接地
- 被动供电：OTG ——手机得启动供电，供给设备
### c、**PDM 麦克风** ？
+ [PDM](https://blog.csdn.net/wzz4420381/article/details/51477725)
### d、BT蓝牙
+ 内部音频信号的无线传输
+ 集成：变成有线
## 2、Use
### a、特定软件 -- 如何集成？
+ 录音软件: Audacity 
+ 播放器软件: AIMP 
### b. 回音消除
- 回音消除（AEC）: 能够实现主机设备自身播放的声音不会被再录制回去.（audio Code-可以实现）
+ 条件：主机设备自身播放的声音需要进入 PXVF3000 的作为声音参考信号来实现回音消除。
+ 原理：录制环境的全部声音，会“减去”主机设备提供的--参考播放声音，实现回音消除功能。也就是--需要“告诉” PXVF3000-KIT 现在主机设备在播放的声音。
+ 连接方式：USB（UAC 1.0）、Line-in 3.5mm 耳机座和 I2S 接口（主从兼容） 
### c. 语音增强
+ 4路MIC
+ 波束成型(Beamforming)和自动增益（AGC）算法可以实现语音增强功能
## 3、固件
### a. 针对场景
+ “ASR” —— 语音识别应用
+ Con”—— 会议系统应用
### b. 更新和调试
+ USB DFU 的方式更新
+ 调试参数《PXVF3000-KIT USB Control Tool使用说明_v2》
### c. **USB输出 channel 意思？**
+ uac1 代表什么 ： USB (UAC1.0)输出麦克风阵列前端算法处理后的 1 通道声音信号
### d. 测试场景
+ 针对的是：USB（UAC1.0）
+  Line-out & Line-in 3.5mm 耳机座或者 I2S_in & I2S_out 数字接口：单独申请
## 4、固件和硬件适配
+ 使用相应固件时，匹配的硬件电路也需要做相应的跳电阻改变才能匹配
+ 先做好硬件跳线，跳回其他模式下的硬件电路，之后再去 DFU 升级
### a. USB+板载CODEC （使用）
+ 默认硬件：无需改动
+ 此模式 无 —— BT 蓝牙和 I2S 音频传输接口
### b. USB+外部I2S
+ 通过 I2S 接口输出来自操作系统的音频信号，没有使用板载的 Codec
+ 使用 P2 作为 I2S 接口
### c. BT蓝牙
+ 通过 BT 蓝牙接口输出来自操作系统的音频信号，没有使用板载的 Codec 和 I2S 接口
- （只是使用MIC进行录音吗？）
- （板载的CODEC起什么作用？）
## 5、USB DFU固件control tool
### a. 参数调试
+ 目前 PXVF3000-KIT_USB_DFU_Tool 仅支持 Windows 系统运行
+ 每次 PXVF3000-KIT 断电，所有的算法参数都重置为固件默认的参数，如需固化参数，需完成附录 A.1 表格和联系木瓜电子提供固化固件。——进行参数的记录
### b. 参数定义
+ AEC Adaptive Echo Canceler-- 自适应回应消除
+ RT60 ?
+ AGC --Automatic Gain Control 自动增益控制
+ Keyword detected; current value needs polling（轮询） (read-only)
+ ASR ? -- 
#### (1) HPFONOFF
+ HPFONOFF-麦克风信号的高通滤波器
+ 0-180Hz cut-off 在声音中的状态
#### (2)Parameter description for the BF and PP (linear and circular arrays)
+ BF?
+ PP?
## 6、PXVF3000规格书
### a. 硬件特点
+ 5V 电源供电，功耗 500mW(典型)
+ Pb-Free 封装， 40mm *36 mm 尺寸
### b. 麦克风阵列
+ 算法： 4 路麦克风阵列的自适应波束成型 -- 自动指向声音最大 dB 的发出方向
- 麦克风坐标 ：间距 > 30mm
### c. 功能
+ 集成噪声抑制（高达 15dB 抑制优化） 、 混响抑制和自动增益（AGC）
+  PXVF3000 主要负责声音信号处理，将 4 路麦克风阵列声音信号经过了回音消除（AEC）,
波束成型（Beamforming） ,噪声抑制（NC）和自动增益（NC）等算法流程后，输出一路干净
的声音输出给用户自定义使用。
### c. 配置
+ PXVF3000（算法） + PDM麦克风阵列（拾音）