# 二、脑电极
## 2018/8/21
+ 研究方向：脑电这块的运动想象继续进行，找到脑电专注力和情绪之间的交叉点，找到源头--自圆其说
+ 要求：脑电信号采集能达到22路信号，采集到EEG信号。
+ 硬件需求：（1）先买到22路信号进行数据采集；（2）自己设计板子完成
### 1、脑电极帽资料
+ 神经科学与神经工程领域的前沿期刊[eLife](https://elifesciences.org/)
+ 《科技导报》--> [2017 年脑机接口研发热点回眸](https://mp.weixin.qq.com/s?__biz=MzA3MDM4MDkyMA==&mid=2650919296&idx=1&sn=100270f16e78597f606875eb16ef8fb8&chksm=84c8cd97b3bf4481f96ddb92d82064eb3836e3aa7628e7b69bbfd0d6b40b9936673a79d6d523&mpshare=1&scene=1&srcid=0206PL0BpMBz8pcBlcBvZ6uI#rd)
+ [基于脑电的无创脑机接口研究进展](https://mp.weixin.qq.com/s?__biz=MzA3MDM4MDkyMA==&mid=2650920373&idx=1&sn=10c4ff4fb006ddb09e964e87b1f07400&chksm=84c8c9a2b3bf40b46d85b10f71c8e986cf2f63fd00a1d649877b44b86f30dfb038679ed94b1d&mpshare=1&scene=1&srcid=0814PAVC1zOVKoGQkryrFKhL#rd)
+ [Smarting]一篇文章-->武汉格林泰克科技
+ 美国加州大学圣迭戈分校的研究团队在《IEEE Transactions on Neural Systems and Rehabilitation Engineering》报道了一种将电极放置在耳后无毛发覆盖区域的稳态视觉诱发电位脑机接口系统---没找到
- [
An Online Brain-Computer Interface Based on SSVEPs Measured From Non-Hair-Bearing Areas]
- [Correlated Component Analysis for Enhancing the Performance of SSVEP-Based Brain-Computer Interface]
- 基于稳态视觉诱发电位（steady-state visual evoked potential，SSVEP）的脑机接口、基于运动起始时刻视觉诱发电位（motion onset VEPs，mVEP）的脑机接口等诸多新范式相继涌现并日益成熟
### 2、脑电极帽的报价
#### （1）采集装置分为两部分报价：
+ 武汉格林泰克科技有限公司---> 电极帽+电极
+ 合作伙伴[Smarting](https://mbraintrain.com/smarting/#references)---> EEG信号处理+PC端或者手机端显示的软件
#### （2）武汉格林泰克科技有限公司
+ 22通道电极帽+电极：5000；
+ 32通道电极帽+电极：9000；
+ 64通道电极帽+电极：13500。
+ 定制方案是另外提供的
+ 区分：大中小3个帽子的型号
#### （3）合作伙伴[Smarting]放大器
+ 不同通道数匹配不同的放大器
+ 8通道放大器：大概7万
+ 22通道整套放大：价格13万
+ 32通道放大器价格：也接近30万
+ 64通道的放大器价格：在50万
#### （4）今天展示的22路EEG装置
+ 销售成本价：22通道整套放大器价格13万，配套软件5万，采集耗材2万
+ 成交价：15万左右
#### （5）联系人
+ 李明哲 -phone- 15926282558
#### （6）单电极
+ 银氯化银粉末电极 -- 300块
+ 谷歌学术，百度  粉末电极+加一个脑电

### 3、脑电极的放大器分类
+ 脑电采集比较知名的还有neuroscan放大器，
+ brainproducts放大器，
+ g.tec，ant neuro放大器
## 2018/8/26
### 1、格林公司的电极帽
+ [db25 并口购买链接](https://item.jd.com/10581179015.html#crumb-wrap)
+ [DB25 规格书](https://wenku.baidu.com/view/8aae340710661ed9ad51f3b7.html)
## 2018/8/27
### 1、硬件制作问题
+ 22路信号：包括REF信号
+ BIAS electrode 要占电极信号
### 2、多重芯片连接
+  Multiple Device Configuration 信号链接---P63
+  two devices when synchronized with the START signal
### 3、Daisy-Chain Mode
+ DOUT of the second device is connected to the **DAISY_IN**
+ Daisy-chain mode is enabled by setting the **/DAISY_EN** bit in the CONFIG1 register
- BIAS1 驱动电极能多个设备共用不？
+ DRDY--信号不复用，都是从device1进行读数据
#### 3.1链式模型使用
+ CLK:用于内部时钟同步
+ START：用于内部时钟同步
+ DOUT(device2)-->DAISY_EN(device1)：进行链式连接，从device1_DOUT进行输出
+ DRDY_2device:拉高

### 4、电源部分的修改
+ 在AVCC哪里就爱上一个电阻和一个电感