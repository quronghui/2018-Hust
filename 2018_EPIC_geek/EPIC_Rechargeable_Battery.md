
# 可充电纽电池回路
## 1、MCP73831
### 1.1 引脚特性
|特性|值|
|:-:|:-:|
|充电电流|15mA-500mA|
|选择结束充电|5%-20%|
+ 考虑：充两个纽扣电池的时候，能进行串联充电吗？
+ 充电模块充电的时候只能并联进行的，没有测试过串联充电，有坑呢是充不满的。
### 1.2 引脚
|name|Pin|Value
|:-:|:-:|:-:|
|Supply Voltage|VDD|3.75-6v|
|UVLO Start Threshold|V_Start|3.3-3.6v
|UVLO Stop Threshold|V_Stope|3.2-3.5




