# Table Schedule
## 时间安排
|data|start|end|project|
|--:|:-:|:-:|:-:|
|2018.11.8|14:30|16：30|血压检测的调研|
||16:40|17：56|口气检测仪|
|2018.11.9|10.10|11:10|arduino学习|
||14：00|15:20|arduino学习|
|2018.11.10|9:30|11.10|搭建VS code 开发 Arduino 成功|
||15：20|16:53|实现驱动LCD屏幕|
|2018.11.12|14:30|15:50|读取了MQ-135的值|
||16:00|17：30|Arduino的语法规则|
||19:00|21：00|Arduino的语法规则|
|2018.11.13|8：30|9：40|变量类型|
||11：00|12：00|变量类型的代码实现|
||14：10|15：30|时间函数学习|
|2018.11.14|10: 00|11:20|数学函数的map映射|
||14：30|16:30|通过arduino实现气体硫化物的测量|
|2018.11.15|9：00|11.36|调试蓝牙|
||14:00|17:00|玩新手机|
|2018.11.16|8：40|11:20|完成蓝牙的传输|
||15：00|16：00|需要设计成盒子式的产品|
|2018.11.17|9：00|11：30|听师兄们的PPT讲座|
|第二周||||
|2018.11.19|14:30|16:00|pro mini 焊接优化|
||19：00|22：00|宋老师谈项目|
|2018.11.20|8：30|11：30|焊接板子|
||14：30|17：30|焊接板子|
|2018.11.21|14:30|17:00|写本科毕业设计的任务书|
|2018.11.22|9:00|21:00|找一下arduino的数组传参的方式|
|第四周||||
|2018/12/4|14：00|16：00|完成ESP8266的wifi调试|
|||||


###  2018.11.22 任务

1. 调试代码，显示等级和显示浓度，（1）循环显示；（2）只显示某一刻时刻的数；（3）有清屏的功能； 
    + 能不能写成switch case 的语句进行调用
    + 
2. 搭建两块arduino pro mini，测试 MQ_135 和 TP 的准确度
3. 做一个盒子
4. 搭建博客
5. 又要加WiFi模块了
### 第三周
1. 搭建两种传感器的测试电路；
2. 调试蓝牙模块，更改AT指令 -- OK
3. 增加WiFi模块
4. MQ135模块的原理图，看一下他的预热模块能移植到TP410
### 第四周
1. 换了传感器MP135，为了做小。
2. 调通WiFi模块  -- OK
3. 下一步：结合arduino，进行

## 口气检测仪项目调整

1. 蓝牙模块：手机需要写一个APP接受数据，可以往后台发送，本地绘制波形。
2. wifi 模块：手机端得先写一个APP，进行网络的连接；数据发送到[yeelink](http://www.yeelink.net/developer/doc/43) 平台；后台去写对应的接口读取数据。
3. 蓝牙和WiFi的使用，我们的口气检测应用场景应该用不到；除非是需要长时间采集数据，并且需要对数进行分析。
4. 是否制板进行

## 项目进展
|data|project|Progress
|:-:|:-:|:-:|:-:|
|2018.11.8|血压检测的调研|可行性看性能，采用光电传感器实现|
|2018.11.8|口气检测仪|文献支撑太少了的|
|2018.11.9|口气检测|搭建开发环境|
|2018.11.12|发现一个让LED灯渐变的方式|LED_charge
|2018.11.14|实现气体硫化物的检测,动态显示在OLED|
|2018.11.21|焊接在一块板子后，电路出现短路现象|
||
|**以后的调试板，不要直接焊接，通过排母和排针焊接就行**|
||

## 项目调研方法
### 心电监测调研
1. 先明白血压是个啥？
    + 知网中文论文--专业
2. 血压检测的调研是检测哪些方面
    + 检测血压的舒张度和收缩度
3. 如何通过具体的方式进行检测，可行性分析

# [2018.10.28]项目进度
## Boxing
|日期|完成|问题|解决方式|
|:-:|:-:|:-:|:-:|
|10.16||代码的CH559和C52的转换调试问题|询问唐在洋
|10.23|1.用开发板实现IIC的通信|
||2.搭建一个MPU6000的板子|
## 催眠按键
|日期|完成|问题|解决方式|
|:-:|:-:|:-:|:-:|
|10.16|电容按键模块的购买|查看手册设计电容触觉片|
|||如何记录按键的时长和节奏

## 触摸式按键芯片的检测方式
### 1、点动式的触摸
+ 触摸式输出为高电平
+ 灵敏度很高，可以覆盖检测
+ 电极材料是个啥
# Arduino UNO 
## Arduino Uno 网址
+ [Arduino IDE](https://www.jianshu.com/p/7938400cda40)
+ [Fritzing](https://www.jianshu.com/p/f0a09982913a?utm_campaign=maleskine&utm_content=note&utm_medium=seo_notes&utm_source=recommendation)
+ [Microsoft Robotics Studio](https://www.jianshu.com/p/5ea7c47546fd)
+ [简书-Arduino studying](https://www.jianshu.com/c/285a8928581a)
+ [arduino 官网](https://www.arduino.cn/)
## VS Code 开发 Arduino 
+ [VS Code 开发 Arduino](https://blog.csdn.net/wowocpp/article/details/81175478)
1. 安装VS code
2. 在VS code 中搜索加载 Arduino
3. 配置 Arduino 的 User Setting ;
    + **注意** 不是 command path ,是User path
4. 在VS code 中搜索加载 platformIO IDE
5. New project , 观看那些文件是用于干啥的
6. 加载库方法 --》 全局加载
    + 在 PIO Home 中加载库
    + 在 项目中的 platformio.ini 中加载库文件名
    + lib_deps = U8glib_ID7
7.  加载库方法 --》 局部加载
    + 在 PIO Home 中加载库
    + 复制到Project 里面的 lib 下 
    + 在 项目中的 platformio.ini 中加载库文件名
    + lib_deps = U8glib
## Arduino 书籍
+ 《Arduino软硬件协同设计实战》
+ [Arduino程序设计基础》函数参考文档](https://arduino-wiki.clz.me/?file=home-%E9%A6%96%E9%A1%B5)

## Arduino 语法
+ [创客智造_语法](https://www.ncnynl.com/archives/201606/34.html)
### 常用语法
1. For 循环实现，led灯的渐亮和渐灭，但是血药模拟电压的输出口，才行。
2. return: 用于跳出大段的错误代码，便面注释
3. Serial.println 和Serial.print 区别： 
    + Serial.println 多了回车换行
### 算术运算
1. 取模运算：不能用浮点类型。
2. 逻辑运算符： &&  ||  ！ ； 位运算符： &  |  ~
3. 异或（^）：(a = 1) ^ (b = 1) = 0 ; // a和b相同时，异或为0
4. 逻辑移位：左移n --> 相当于原来的数 * ( 2^n )；
5. 逻辑右移：相当于除的运算
### 语法常量和变量
1. High --> 
    + Input : DigitalRead --> Pin >3 V , return High;
    + Output : DigitalWrite --> Pin = 5 V , 输出;
2. Low -->
    + Input : DigitalRead --> Pin <2 V , return low;
    + Output : DigitalWrite --> Pin = 0 V , 接地;
### 变量类型
1. int -->
    + 占两个字节,但是包含负数
    + 从（-2^15 -- (2^15-1) ）
    + -32,768到32,767
2. usigned int -->
    + 占两个字节，不包含负数
    + 0-65535
3. word -->
    + 等同于usigned int
4. long -->
    + 长整型 ： 四个字节
5. Float -->
    + Arduino 中的 double 和 float 精度是一样的
    + 存储为32位（4字节）
6. **string(字符串)** -->
    + 字符串类型
    + char[8] = {'a', 'r', 'd', 'u', 'i', 'n', 'o', '\0'}: '\0' 空转的字符，系统会自动加上
        + 字符串长度 = 元素 + 1
    + char* mystring[] = { }  ; “指针”数组-->所有的数组名实际上是指针
    + 通过 char 进行定义
7. **String(c++)类型说明** -->
    + 字符串数组 --> string; String类的实例 --> String表示 
8. Array 字符串 -->
    + 字符串和数组区别：数组是可以索引的
    + 注意空字符的访问
### 变量作用域
1. 在Arduino的环境中，任何在函数（例如，setup(),loop()等）外声明的变量，都是全局变量
    + C中的全局变量，是要通过 define 吧？
2. const -->
    + 代表不可改变的常量,变量状态为只读;
3. sizeof() -->
    + sizeof(variable) : 返回一个变量类型的字节数，或者该数在数组中占有的字节数。
### 函数
1. pulseIn -->
    + unsigned long pulseIn (uint8_t pin, uint8_t state, unsigned long timeout)   
    + 读引脚从HIGH到LOW跳变的时间
2. millis(days) -->
    + unsigned long millis (void)
    + 获取机器运行的时间长度, 单位毫秒. 系统最长的记录时间接近50天, 如果超出时间将从0开始.
3. void delay(ms) -->
    + 数据是 (-(2^15)-->(2^15-1)) 位的值
    + delay(60000UL); 当数据超过(2^15-1),加 Unsigned long进行转换
4. delayMicroseconds(us)
    + 延时函数，单位是 us
    + 1s = 1000 ms = 10^6 us
5. Map -->
    + map 函数实现值在范围内的映射
    + long map(long x, long in_min, long in_max, long out_min, long out_max)
6. 三角函数
    + float 4个字节表示
7. 随机函数
    + void randomSeed  ( unsigned int  seed)
        + seed 随机种子的设置会对随机序列产生影响。
    + long random(long howsmall, long howbig)
        + 生成 [ howsmall, (howbig-1)] 之间的数
### 位操作
1. 位操作，都是通过define进行定义的；
2. 我目前没有找到该怎么用；
### 中断
1. 这个也是没怎么看懂
### Uart 通信
+ 库函数是 Serial
1. Serial.begin (long speed)
    + 设置波特率的
2. Serial.print
    + 以人类可读的ASCII码形式向串口发送数据
    + Serial.print(78, format )
    + format -->
        + 二个参数用于指定数据的格式
        + 允许的值为：BIN (binary二进制), OCT (octal八进制), DEC (decimal十进制), HEX (hexadecimal十六进制)
        + 对于浮点数，该参数指定小数点的位数
    + Serial.print("\t") : 增加一个空格
## Arduino Library
+ [创客制造--库函数](https://www.ncnynl.com/archives/201608/608.html)
+ Uart 通信 -- SoftwareSerial库

## MQ_135和TP401T对比
### MQ135测试数据
1. Arduino + MQ135

|测试气体|未测试数据范围|测试数据范围|
|:-:|:-:|:-:|
|酒精|value <= 90| 110 < value < 130|
|甲烷|value <= 100 | 180 < value < 480|


# open JUMPER Bluetooth V2.0
## Introduction
1. 功能
+ 把您原来的有线串口变成无线串口通讯，所以模块自身并不涉及软件编程；
2. 串口蓝牙的功能：将有线的串口，转化为了无限的串口
## 串口回环测试
1. 需要电脑有蓝牙功能

# arduino pro mini
+ [arduino pro mini](https://detail.tmall.com/item.htm?spm=a230r.1.14.1.36de4460SHdZY9&id=550032593686&ns=1&abbucket=11)
### 2. MQ-135气敏传感器
+ [气敏](https://www.ncnynl.com/category/arduino-gas/)
