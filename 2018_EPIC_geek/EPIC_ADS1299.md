# ADS1299手册内容
<!-- TOC -->

- [ADS1299手册内容](#ads1299手册内容)
    - [1、电气特性](#1电气特性)
        - [1.1 电压和电流](#11-电压和电流)
        - [电压特性测试](#电压特性测试)
        - [1.2 electrical characteristics](#12-electrical-characteristics)
        - [1.3 SYSTEM MONITORS](#13-system-monitors)
        - [1.3 [SPS](https://blog.csdn.net/iini01/article/details/80084124)](#13-spshttpsblogcsdnnetiini01articledetails80084124)
    - [2. ADC特性](#2-adc特性)
        - [2.1 ADC特性--[差模、共模信号、公模抑制比](https://blog.csdn.net/augusdi/article/details/17204255)](#21-adc特性--差模共模信号公模抑制比httpsblogcsdnnetaugusdiarticledetails17204255)
            - [共模抑制比结论](#共模抑制比结论)
            - [公模信号](#公模信号)
            - [差模信号](#差模信号)
        - [2.2 ADC特性--[电源抑制比DC-PSRR](https://blog.csdn.net/gang_life/article/details/50363131)](#22-adc特性--电源抑制比dc-psrrhttpsblogcsdnnetgang_lifearticledetails50363131)
        - [2.3 ADC特性--[总谐波失真THD](https://blog.csdn.net/wordwarwordwar/article/details/53208503)](#23-adc特性--总谐波失真thdhttpsblogcsdnnetwordwarwordwararticledetails53208503)
        - [2.4 ADC特性--[INL非线性度]()](#24-adc特性--inl非线性度)
    - [3. 参数测量信息](#3-参数测量信息)
        - [3.1 噪声测量(P16)](#31-噪声测量p16)
    - [4. Anlog Input](#4-anlog-input)
        - [4.1 BIAS(patient bias drive block )](#41-biaspatient-bias-drive-block-)
        - [4.2 特征描述](#42-特征描述)
        - [4.3 寄存器配置_P20](#43-寄存器配置_p20)
        - [4.4 Anlog Input](#44-anlog-input)
        - [4.5 PGA and bandwidth setting](#45-pga-and-bandwidth-setting)
        - [4.6 Input Common-Mode Range ----P23](#46-input-common-mode-range-----p23)
        - [4.7 参考噪声VREFP是不影响系统噪声的](#47-参考噪声vrefp是不影响系统噪声的)
    - [5. Digitial Funcation](#5-digitial-funcation)
        - [5.1 Digital Filter](#51-digital-filter)
        - [5.2 Sinc filter---尽量找到图形的关系](#52-sinc-filter---尽量找到图形的关系)
        - [5.3 Clock-- P27](#53-clock---p27)
        - [5.4 GPIO](#54-gpio)
        - [5.5 MUXn[2:0]](#55-muxn20)
        - [5.6 BIAS Driver Signal](#56-bias-driver-signal)
        - [5.7 电极的阻抗检测](#57-电极的阻抗检测)
        - [5.8 DC Lead-OFF DC的开始](#58-dc-lead-off-dc的开始)
        - [5.9 AC Lead-off](#59-ac-lead-off)
        - [5.10 BIAS lead off detaction at power-on](#510-bias-lead-off-detaction-at-power-on)
        - [5.11 BIAS Drive](#511-bias-drive)
    - [6、设备工作条件](#6设备工作条件)
        - [6.1 Start](#61-start)
        - [6.2 DRDY pin -->数据连续阅读](#62-drdy-pin---数据连续阅读)
        - [6.3  Single-Shot Mode（数据间断阅读）](#63--single-shot-mode数据间断阅读)
        - [6.4 SPI interface](#64-spi-interface)
        - [6.5 SPI Command Definitions](#65-spi-command-definitions)
        - [6.6 Register Map --P44页](#66-register-map---p44页)
    - [7. Applications and Implementation](#7-applications-and-implementation)
        - [7.1 Applications](#71-applications)
            - [7.1.1 Unused Inputs and Outputs](#711-unused-inputs-and-outputs)
            - [7.1.2 信号处理流程](#712-信号处理流程)
            - [7.1.3 Establishing the Input Common-Mode](#713-establishing-the-input-common-mode)
    - [8. 采集前端的电容电阻匹配](#8-采集前端的电容电阻匹配)
- [ADS1299EEG-FE](#ads1299eeg-fe)
    - [关于ADS1299EEG-FE演示版的资料](#关于ads1299eeg-fe演示版的资料)
        - [手册的相关参考](#手册的相关参考)
        - [有相关的原理图](#有相关的原理图)
    - [ADS1299--Ti论坛](#ads1299--ti论坛)
    - [OPENBCI -- 采集套件](#openbci----采集套件)
    - [MCU的处理功能](#mcu的处理功能)

<!-- /TOC -->
## 1、电气特性
### 1.1 电压和电流
|Power|value|
|:-:|:-:|
|AVDD|5V|
|DVDD|3.3V|
|VREFP|4.5V|
|Curite_P11页|ads1299-6 I(Avdd)=5.57mA < 10mA| 
|Curite|ads1299-6 (DVDD = 3.3 V) I(Dvdd)=0.66mA|
+ The internal reference generates a low noise 4.5 V internal voltage when enabled and the internal oscillator
generates a 2.048-MHz clock when enabled
### 电压特性测试
|EEG1.0|Power|value|EEG2.0|Power|value|
|:-:|:-:|:-:|:-:|:-:|:-:|
||INXN--not input|5v
||IN2N--IN2P|71.6mv--74.9mv
||VREFP|4.49v|
||VCAP4|2.25V
||VCAP1|1.19V|
||VCAP2|2.5V

### 1.2 electrical characteristics
|Power|value|
|:-:|:-:|
|External_clock input|2.048MHZ
|Resolution_分辨率|24Bit|
|Data rate|250sps--16000sps|
|增益gain|12(1, 2, 4, 6, 8, 12, 24)|
### 1.3 SYSTEM MONITORS
|Control|State|value|
|:-:|:-:|:-:|
|Device wake up|From power-up to DRDY low|150ms|
||STANDBY mode|31.25us|
|t(SCLK)_P12页|2.7 V ≤ DVDD ≤ 3.6 V |50 ns
|关于数据传输速率中时间的设置|ADS1299 手册|P12页
|共模抑制比，Common-mode rejection ratio|f=50-60hz,gain=12|CMRR=-120|
### 1.3 [SPS](https://blog.csdn.net/iini01/article/details/80084124)
+ sps:在adc中相当于每秒钟采样的次数；也成为波特率
## 2. ADC特性
### 2.1 ADC特性--[差模、共模信号、公模抑制比](https://blog.csdn.net/augusdi/article/details/17204255)
#### 共模抑制比结论
+ 差模信号电压放大倍数Aud越大，共模信号电压放大倍数Auc越小，则CMRR越大。此时差分放大电路抑制共模信号的能力越强，放大器的性能越好。
#### 公模信号
+ 双端输入时，两个信号相同
+ 在电路中，是不需要的，所以需要抑制
#### 差模信号
+ 双端输入时，两个信号的相位相差180度
+ 会进行放大，有放大器
### 2.2 ADC特性--[电源抑制比DC-PSRR](https://blog.csdn.net/gang_life/article/details/50363131)
+ 定义：运放电源电压的变化，引起运放输入失调电压的变化，两个变化电压的比。
### 2.3 ADC特性--[总谐波失真THD](https://blog.csdn.net/wordwarwordwar/article/details/53208503)
+ 定义：指输出信号比输入信号多出的谐波成分。谐波失真是系统不是完全线性造成的。
+ eg: 16位ADC中的信噪比的值不是理想计算值，因为系统不是完全线性
### 2.4 ADC特性--[INL非线性度]()
+ 定义：MAX [拟值值-真实值]，输出数值偏离线性最大的距离。单位是LSB（即最低位所表示的量）
## 3. 参数测量信息
### 3.1 噪声测量(P16)
+ **优化噪声**：减少data rate, 增加PGA(gain);
+ 有一个对应表格：RMS and peak to peak noise
## 4. Anlog Input
### 4.1 BIAS(patient bias drive block )
+  The versatile patient bias drive block allows the average of any
electrode combination to be chosen in order to generate the patient drive signal.----任意电极就行
### 4.2 特征描述
|符号|含义|
|:-:|:-:|
|f（CLK）| CLK pin signal frequency|
|t(clk)| CLK pin signal period|
|f(DR)| output data rate|
|t(DR)|output data time period|
|f(MOD)|调制器采样输入的频率|
|f（MOD） = CLK / 2 |
|(t(SETTLE)|转换器输出完全固定的数据所需的时间|
|t（SDSU）|DRDY PIN由高到低的时间，停止数据的转换
|t (DSHD)| start pin 由高到低的时间，为了停止数据的转换
|t(SENDCODE)==4 t(clk)|The ADS1299-x serial interface decodes commands in bytes and requires 4 t CLK cycles to decode and execute
| t POR|Delay for Power-On Reset and Oscillator Start-Up
### 4.3 寄存器配置_P20
|功能位|修改的寄存器|作用
|:-:|:-:|:--:|
|BIAS_MEAS| CHnSET[3:0] register|
| SRB1 bit| MISC1 register|
| CHnSET[2:0] = 001|设置公模电压V，作为两个通道的输入|测试设备固有的噪声|
| CHnSET[2:0] = 101|TEST_AMP and TEST_FREQ|通过呢欧比信号进行测试输出，控制幅值和频率
### 4.4 Anlog Input
- 公模信号和差模信号的体现
+  差分输入电压差（differential input voltage）: (–V_REF/gain) < [V_INxP – V_INxN ] < (V_REF/gain)
+ P22
### 4.5 PGA and bandwidth setting
+ gain = 12 ; bandwitch = 55
### 4.6 Input Common-Mode Range ----P23
+ 公模电压范围：限制输出电压，防止增益变成非线性
+ CM --> 有一个计算公式
### 4.7 参考噪声VREFP是不影响系统噪声的
## 5. Digitial Funcation
### 5.1 Digital Filter
+ 调节滤波器的数量：在 resolution and data rate（分辨率和数据速率） 折中
+  filter more for higher resolution, filter less for higher data rates
+  Higher data rates are typically used in EEG applications
-  CONFIG1 register 的 DR bits 能调节 Sinc filter 的采样速率
### 5.2 Sinc filter---尽量找到图形的关系
+ sinc滤波器减弱了调制器的高频噪声，然后将数据流分成并行数据
- 关于F（in）/ F(mod) 和 DR[2:0]--P46位的数据曲线 ————P26
- f（MOD） = CLK / 2
+ Gain(db)和gain=12--之间的关系 20(lgx)的关系
### 5.3 Clock-- P27
+ CLKSEL pin ：selects the internal or external clock
+  CLK_EN bit( CONFIG1 register) :决定 CLK pin 输出/不输出 oscillator clock
### 5.4 GPIO
+ GPIOD bit ：配置为输入或者输出
+ GPIO 不使用 ：Link DGND and don't float
### 5.5 MUXn[2:0] 
+ 关于8路信号的一些设置
+ eg：之前用于噪声的测量-->确定板子的噪声幅值
+ eg: 通过板子产生测试的信号-->查看正确信号的波形？
### 5.6 BIAS Driver Signal
+ **测量BIAS Driver Singal**
+  (1)配置MUX[2:0],配置为只在第八通道读（ADS1299-6第六通道）,类似于 图 Figure 34 
+ （2）BIASREF_INT =1/0 决定 BIASREF pin是内部还是外部源
+ （3） BIASREF pin 进行测量 BIASOUT signal
### 5.7 电极的阻抗检测
+ 判断电极是否接触：input 励磁电流；检测电压
+  LOFF_SENSP and LOFF_SENSN registers：起到调节作用
### 5.8 DC Lead-OFF DC的开始
+ （1）这个模式，需要一个DC信号作为激励，有三种方式提供
+ 判断电极是否关闭，使用这个比较器
+ 比较器的输出存储在：the LOFF_STATP and LOFF_STATN registers
### 5.9 AC Lead-off
+ 这个模型使用，需要内部激励频率设置：FLEAD_OFF[1:0] bits in the LOFF register， selections (7.8 Hz or 31.2 Hz)
+ 测量输出频率的量级，计算出电极的阻抗
### 5.10 BIAS lead off detaction at power-on
+ 可以检测电极是否连接成功
+ 偏置增益开始时，比较器comparator能感知，偏置放大器的输出电压。 voltage at the output of the BIAS amplifier
+ The comparator thresholds are set ： the same LOFF[7:5] bits --》其他的输入信号
### 5.11 BIAS Drive
+ bias drive voltage select : (1)internal  [(AVDD + AVSS) / 2] ;(2)externally 
+ set : BIASREF_INT bit ==1 (选择internal) in the CONFIG2 register -----选择internal
+ 可以不用使用引脚BIASIN
+ 多个设备连接时，是一个偏置放大器；将BIASINV连接在一起。
+ 多重设备连接的话，如果BIASINV连接在一起，但是BIASOUT这个怎么办，他不也连在一起了吗？
## 6、设备工作条件
### 6.1 Start
+ START pin : 控制信号的AD转换
+ + 要保持数据的连续转换，保持 START==1 不变
+ 单设备：SINGLE_SHOT(bit 3 of the CONFIG4 register)，两种转换方式，连续或者单发
+ 多设备： synchronize devices

|状态1|状态2|状态3|结果||
|:--:|:-:|:-:|:--:|:-:|
|START-->high|and DRDY-->high|next DRDY-->falling edge|转换数据转备好，可以读取|
+ 所需要的时间是 t(SETTLE)
+ t(SETTLE) : 取决于 f CLK and the decimation ratio（通过DR[2:0]-->进行设置）
+ DRDY pin 应该是一个输出信号
### 6.2 DRDY pin -->数据连续阅读
+ DRDY --> OUTPUT PIN
+ STATUS : 从 high --> low，表示数据准备完成。
- Data retrieval 有两种方式：
- （1）RDATAC : 连续阅读模式，无需设置
- （2）RDATA : 指令控制数据，进入移位寄存器
+ 转换数据的读取 : 在DOUT中读取
+ 在SCLK第一个下降沿时，DRDY将被拉高，DRDY 读取 DOUT数据的最高位MSB。
- **输出数据计算** ：
-  [(24 status bits + 24 bits × 8 channels) = 216 bits]
- The format of the 24 status bits is: (1100 + LOFF_STATP + LOFF_STATN + bits[4:7] of the GPIO register)
### 6.3  Single-Shot Mode（数据间断阅读）
+ control : START signal low and back high 
### 6.4 SPI interface
+ SPI通信的前提条件：DRDY output pin is low 


|SPI pin|use|status|
|:-:|:-:|:-:|
|CS| activates SPI communication|low and stay low --> all SPI communication period
|DRDY| 不依赖于 CS pin|
|SCLK|data shifted signal|falling edge --> data shifed into DIN; rising edge --> data shifted out from DOUT|
||f(sclk) 有一个最小值限制，t(sclk)就有个最大值限制|t(sclk) < [ t(DR)-4t(clk) ] / [ N(bits) * N(channel) +24 ] |
|DIN|falling edge --> Data on DIN are shifted into the device(应该是ADS1299); |Digitial Input |
|DOUT|rising edge --> DOUT is used with SCLK to read conversion and register data from the device|Digital output|
||CS --> high|DOUT-->high-impedance|
### 6.5 SPI Command Definitions
+ Register Read Command : RREG and WREG
+ Support sending multi-byte commands 
- SPI 命令间的发送得相隔 4 t（clk）

### 6.6 Register Map --P44页
|寄存器名称|哪一位|设置值和作用|||
|:-:|:-:|:-:|:-:|:-:|
|ID Control Register| NU_CH[1:0] |表示采用及通道的设备
|Configuration Register 1| DAISY_EN |多个设备级联的方式下，默认值为0，多重反馈模型目前还不知道
|| CLK_EN | 多设备级联时，CLK作为设备的内部时钟信号
||DR[2:0]| Output data rate
|Configuration Register 2|INT_CAL|Test signal 来源
| Configuration Register 3|主要是讲 BIAS 偏置信号的配置
||BIASREF_INT ==1|偏置驱动非反相输入，设置为1，我们取内部的信号作为偏置
| Lead-Off Control Register|COMP_TH[2:0] |Lead-off 比较器的阈值设置
||FLEAD_OFF[1:0] |Lead-off检测频率的选择
|CHnSET: Individual Channel Settings |GAINn[2:0] | determine the PGA gain setting.
||MUXn[2:0] |Channel input or measurement
|BIAS_SENSP|BIASP-x|这里选择positive里面的8个通道里面的某一个作为BIAS的电极，相当于内部电极信号，获取偏置电压
|BIAS_SENSN|BIASN-x|这里选择8个通道里面的某一个作为BIAS的电极，相当于内部电极信号，获取偏置电压
|||对于多设备的话，选择一个共同的偏置电极吗？还是各自用各自内部的电极
|LOFF_SENSP|LOFFP-x|检测Positive某一个电极是否连接成功
|LOFF_SENSN|LOFFM-x|检测Negative某一个电极是否连接成功
|LOFF_FLIP|LOFF_FLIP-x|上下翻转 INxP 和 INxN 的极性，检测电极|
|LOFF_STATP/LOFF_STATN||寄存器存储了电极是 on/off|
|GPIO register|GPIOC[4:1] |input/output|
|MISC1: Miscellaneous 1 Register|SRB1=0/1 |Switches open/close
|CONFIG4|| configures the conversion mode and enables the lead-off comparators
||SINGLE_SHOT=0/1| Continuous conversion mode / Single-shot mode
||PD_LOFF_COMP=0/1| Lead-off comparators disable / enable
## 7. Applications and Implementation
### 7.1 Applications 
#### 7.1.1 Unused Inputs and Outputs
+ BIASIN can also float or can be tied directly to AVSS if unused.--使用内部参考输入，不用外部参考，接地
+ Tie BIASREF directly to AVSS or leave floating if unused. 此脚也没有用到，接地
+ Tie SRB1 and SRB2 directly to AVSS or leave them floating if unused. 用到SRB1
- unused digital inputs :  high to DVDD or low to DGND through ≥10-kΩ resistors
#### 7.1.2 信号处理流程
+ CLKSEL==1：给引脚一个高电平，使用内部振荡器
+ VCAP >= 1.1v,可以作为一个判断依据，电源和振荡器才会开始工作
+ PD_REFBUF=1,我们使用内部的参考电压，VREFP作为输出引脚 = 4.5V
#### 7.1.3 Establishing the Input Common-Mode
+ BIAS electrode：工作时，作为一个参考驱动输入，使得电压值达到要求
+ BIAS 电路是需要连接的，但是还是没有确定，用同一个电极的输入
## 8. 采集前端的电容电阻匹配
+ [参考ADS1299-FE的设计](http://tech.hqew.com/fangan_726253)

# ADS1299EEG-FE
+ Front-End
## 关于ADS1299EEG-FE演示版的资料
+ [ADS1299EEG-FE](http://www.eeboard.com/ziliao/ads1299eeg-fe%E6%80%A7%E8%83%BD%E6%BC%94%E7%A4%BA%E5%A5%97%E4%BB%B6/)
### 手册的相关参考
+ Analog Input : 他们的输入参考是地，和手册上连接SRB1不一样
### 有相关的原理图
## ADS1299--Ti论坛
+ [Ti论坛](https://e2echina.ti.com/search?q=ads1299)
## OPENBCI -- 采集套件
+ [OPENBCI](https://openbci.com/)
## MCU的处理功能
+ [去除工频干扰](https://wenku.baidu.com/view/1b499eb73186bceb19e8bbe8.html)
+ 脑电信号非常微弱，为微伏量级的信号，功率较大的工频干扰成分严重影响到纯净脑电信号的提取及分析，所以必须加入陷波器。
+ 而数字陷波器设计通过软件配置达到设定或改变陷波频率的目的（工频是50或60Hz），且实时性能够满足脑电采集的需要。
+ 同理，数字带通滤波器可通过软件配置灵活调整滤波器的截止频率。