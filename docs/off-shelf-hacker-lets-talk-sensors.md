# 现成的黑客:让我们谈谈传感器

> 原文：<https://thenewstack.io/off-shelf-hacker-lets-talk-sensors/>

我们已经讨论了 Arduino、Raspberry Pi、 [Pine 64](https://thenewstack.io/off-shelf-hacker-linux-runs-pine64-last/) 和其他几款设备。我已经解释了各种“[微控制器](https://thenewstack.io/wireless-connectivity-low-cost-set-stage-fascinating-new-products/)之间的区别，以及哪个用于哪个项目。

传感器呢？

今天，我们将讨论物理计算项目中可用于微控制器和纳米计算机系统的“传感器”。我听到很多关于人们是否应该使用 Arduino 或 Raspberry Pi 的讨论，但传感器也会对你的决定产生巨大影响。

## **传感器 101**

我将传感器分为三类:模拟、数字和其他。

### 模拟的

模拟传感器检测非离散的物理行为。一个常见的例子是光落在光电池上。光电池的电阻随着照射到其表面的光量而变化。

您需要一个模数转换器(ADC)来测量电压，因为光电池的电阻变化，并将其改变为一系列步进值，微控制器可以理解。这都是通过一个[分压电路](https://en.wikipedia.org/wiki/Voltage_divider)完成的。

Pro-Mini 是我最喜欢的 Arduino 模块之一，内置 ADC 电路。模拟输入引脚以 10 位(2^10)分辨率(1024 个值)测量从 0 到电源电压的范围。因此，例如，如果您测量 0 至 5 伏电压，引脚上零伏电压的模拟读取功能返回的值将为零。同样，当引脚上施加 5 伏电压时，该值将为 1024。如果你有 2.5 伏，那就是 512 伏。你明白了。

Pro-Mini 有八个带模数转换器的模拟引脚。需要更多，Arduino Mega 有 16 个。Raspberry Pi 没有任何模拟引脚。

这是为什么呢？

请记住，Arduino 使用您为每个程序上传的专用固件。它没有所谓的“操作系统”。这意味着它专注于非常快速地跟踪模拟或数字传感器。

Raspberry Pi 运行 Linux，因此它能够进行多用户和多任务活动。这意味着它可能会共享一些计算周期来运行桌面，检查网络数据包和运行用户应用程序，同时观察其通用输入/输出引脚。随着所有其他工作的进行，跟踪模拟信号是一个挑战。Pi 仅支持数字输入。

底线:对于以模拟为中心的项目，使用 Arduino 或类似的微控制器。

模拟传感器的一个例子可能是可变电位计。这是一个三端子装置，中间的端子连接到一个小臂上，当轴旋转时，小臂擦过碳元件。当臂靠近一个端子时，电阻较低，并随着轴的转动而增加。

另一种模拟器件可能是压力传感器、热敏电阻甚至应变仪。当受到某种外力(压力、温度、光线、扭曲等)时，这些器件中的电阻都会发生变化。)被应用。

### 数字的

好了，模拟传感器会改变电阻，而电阻又可以通过内置 ADC 的模拟 Arduino 引脚以电压形式测量。然后，该值在 Arduino 程序中作为十位数字使用。

数字传感器要简单得多，因为它们测量离散的物理行为。要么开启，要么关闭。微控制器很容易检测到 0 或 1 值，并且不需要 ADC。

数字传感器可能包括开/关开关、[簧片开关](http://www.explainthatstuff.com/howreedswitcheswork.html)、按钮、霍尔效应传感器等等。数字输入通常非常快，以至于所谓的“开关弹跳”可能会成为一个问题。当一些电子在触点靠近时跳过触点之间的间隙，但彼此并不完全接触时，就会发生这种情况，导致在按下按钮时产生多个数字“1”。而且，这可能发生在毫秒的时间范围内。在读数之间建立一点时间延迟或一些过滤通常是一个好主意，以“去抖”开关，所以每次按下只能得到一个读数。

一个[霍尔效应传感器](https://www.adafruit.com/products/158)，当磁铁经过时记录关闭，当附近没有磁铁时记录打开。你可以用其中的一个来测量旋转轴的转速。

Raspberry Pi 有一系列数字输入，你可以用一个简单的 0 或 1 器件测量很多东西。例如，不使用带电位计的 ADC 来测量轴转动了多远，你可以从一个起点开始计数脉冲，用一个光电池、一个 LED 和一个切割在轴上的小模板上的狭缝。它叫做编码器，而且是纯数字的。

### 其他的

我喜欢将最后一组传感器抽象到一个层次，说它们是“数据供应”设备，尽管它们在操作中是数字的。

这些传感器提供数据作为微控制器的输入，而不是测量电压(模拟)或计数脉冲(数字)。

网络摄像头就属于这一类。它用其感光材料阵列捕捉一个视图，并将其转换为数据流，通过 USB 端口发送到微控制器或纳米计算机。它使用各种协议在设备(摄像机)和微控制器之间进行通信。当数据流入微控制器时，它会得到处理，并决定采取什么行动，是开灯、触发继电器还是将数据发送到另一个设备，甚至可能通过网络发送。这种类型的“数据”传感器可以很好地与 Raspberry Pi 等复杂的纳米计算机配合使用。你不会在 Arduino 上使用网络摄像头传感器，因为它没有足够的处理能力。

然而，Pro Mini 可以使用来自[像素图像处理传感器](http://charmedlabs.com/default/pixy-cmucam5/)的数据。Pixy 在其视野范围内检测彩色物体，并输出一个数据流，告诉 X-Y 坐标和物体的相对大小。数据流通过一些数据链路(USB、I2C、串行等)。)到微控制器。举例来说，Arduino Pro Mini 可以解释这些 X-Y 坐标，以激活马达，将一个小机器人转向一个色彩鲜艳的球。树莓派可以很容易地做同样的事情。

另一个提供数据的传感器是流行的 [DS18B20 数字温度计](http://www.banggood.com/DS18B20-Temperature-Sensor-DALLAS-18B20-TO-92-Encapsulation-p-91798.html)。要获得器件的温度，可以从微控制器上的一个数字引脚发送一个小脉冲，过一会儿，DS18B20 就会以数字形式返回一个唯一的序列号和温度读数，微控制器可以解释这些数据。往返读取大约需要 750 毫秒。

其他数据提供设备包括 [GPS 模块](https://www.sparkfun.com/products/8975)、 [BMP180 气压/温度/海拔传感器](https://www.adafruit.com/products/1603)或者甚至另一个通过数据线发送数据的微控制器。这些都适用于 Arduino 或树莓 Pi。

## **总结**

我们已经讨论了三大类传感器。如果你看看主要的零件供应商，你会发现几乎无限多的设备可以测量你能想象的任何东西。

您的项目中可能混合了模拟、数字或数据供应传感器。这只是取决于你在物理世界中试图测量什么。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>