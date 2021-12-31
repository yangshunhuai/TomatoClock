# TomatoClock
自制番茄钟

## 介绍

现在市面上的番茄钟都很贵，因此打算自己做一个。

### 功能

1. 可以实现基本的番茄钟功能（计时）和到时提醒。
2. 这是一个特别功能，包含一个超声波传感器。将传感器正对着人体，如果在工作时离开了书桌，那么传感器检测到距离将会变大，将会触发一个惩罚机制，番茄钟会通过升压电路将电压升到60伏左右，释放给人体，使人疼痛，达到惩罚效果。
3. 可以查看学习情况（如离开座位几次等）

### 硬件方案

* 主控芯片：STM32F103C8T6 at 8MHz
* 屏幕：SSD1306 (I2C)
* 超声波模块：HC-SR04
* 目前版本没有升压电路。

目前所有的硬件方案都在Hardware文件夹下保存。每一个版本都会有PCB。

外壳将会考虑使用3D打印件。

### 软件方案

原本所有程序都计划使用Arduino IDE开发，但是后来发现了大问题，**Arduino对STM32的支持库几乎完全是bug般的存在**，项目非常不完善，并且无法访问片内很多资源如RTC等。因此现在计划使用Keil MDK开发STM32版本，而ESP32版本将会重新使用Arduino IDE，因为Arduino对ESP32的支持是很完善的。
