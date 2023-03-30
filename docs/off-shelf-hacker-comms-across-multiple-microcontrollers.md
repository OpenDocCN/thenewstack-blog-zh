# 现成的黑客:微控制器间的通信

> 原文：<https://thenewstack.io/off-shelf-hacker-comms-across-multiple-microcontrollers/>

到目前为止，我们还没有在[现成黑客](/tag/off-the-shelf-hacker/)专栏中花太多时间讨论“设备间”通信。

所谓设备间，我指的是让微控制器相互对话，以及与 nano-Linux 系统对话。例如，对一些模拟输入使用 Arduino，然后将数据发送到 Raspberry Pi 进行分析。Arduinos 是实时的，可以很好地处理模拟输入。Pi 根本不能读取模拟输入，尽管它当然可以处理数据，然后显示在网页上，并发送到云端。如果将这两者结合在一起，你可以提出一些非常有趣和复杂的项目，而这些项目是无法用简单的单个微控制器方法来完成的。

今天，我们将介绍三种可能用于现成黑客项目的主要机器对机器接口，看看它们的行为，并研究它们在现实世界中的应用。我将掩饰大部分以极客为中心的细节，因为在现成的黑客项目中使用这些接口，你并不真的需要知道本质的深层技术。无论如何，大多数操作细节都是通过软件库抽象出来的。未来的文章将深入探讨你应该知道的重要物理方面，常见的实际应用和你自己项目的提示/技巧。

我们还将关注“串行”通信方法，而不是并行。串行意味着通过一条线路发送比特序列，也可能通过同一条或第二条线路接收比特序列。并行通过几组电线同时以脉冲形式发送比特。无论如何，微控制器和相连设备之间的几乎所有通信都是串行的，所以这就是我们要讨论的内容。

## 传统“连载”

你可能已经熟悉了微控制器之间的[传统“串行”通信](https://en.wikipedia.org/wiki/Serial_communication)。例如，在 Linux 笔记本电脑和 Arduino 之间使用 USB 电缆，以便通过 Arduino IDE 实现固件上传和数据监控功能。通常一次只能将两个设备连接在一起。

Arduino 和笔记本电脑之间的 USB 连接是串行连接。从操作和编程的角度来看电气连接，就从一台机器向另一台机器获取数据而言，笔记本电脑上的 USB 和 Arduino 上的 TX/RX 引脚是可以互换的。请务必检查 Arduino IDE 中的“通信”示例。您可能还想用您选择的语言扩展您的“串行通信”知识。以下是几个有用的链接:

Arduino 的[软件序列示例](https://www.arduino.cc/en/Tutorial/SoftwareSerialExample)。
T3【Processing.org】连环处理。
[Python py serial 库的文档](https://media.readthedocs.org/pdf/pyserial/latest/pyserial.pdf)。

传统串行用于中等高速的有线数据传输。因为几乎所有的微控制器都可以使用它，所以用它来做低带宽的工作，比如来回发送几个字符，既便宜又容易，而且非常普遍。示例包括在 Arduino 和笔记本电脑之间传输传感器、固件和可能的音频数据。你也可以用它来连接树莓皮和芯片计算机。或者，将一个覆盆子酱连接到另一个上。它也可以处理视频数据。

它通常使用两根导线和一根地线来传输数据。

## 串行外设接口

[串行外设接口](https://en.wikipedia.org/wiki/Serial_Peripheral_Interface_Bus) (SPI)用于短距离、高速有线通信，通常在微控制器和外设之间进行。例子包括用 SD 卡和 LCD 显示器发送和接收数据。

[我的蒸汽朋克会议徽章](https://thenewstack.io/hacking-hardware-the-never-ending-saga-of-steampunk-name-badge-development/)，包含 Arduino Pro Mini 和 Raspberry Pi model 2 版本的 SPI 通信。

我的徽章使用 Adafruit 的 1.8 英寸彩色 TFT LCD 显示屏。SPI 是这种情况下的首选通信方法，因为它是为快速数据传输作业而设计的。我在我的 Torq 博士徽章上显示全动态彩色 MP3 视频，没有任何像素化、图像撕裂或滞后于常规的旧 Raspberry Pi model 2。连接到 Arduino 时，显示速度同样快。当然，当连接到基于 Arduino 的微控制器时，我们仅限于文本和固件生成的形状和动画。

SPI 使用两条线传输串行数据，一条线用于器件选择，一条线用于时钟同步，另一条线用于地线。每个总线设置只有一个主机。每个从设备都需要自己的电线来选择设备。当你增加奴隶的时候，线的数量迅速增加，这是它的缺点之一。

## 内部集成电路

Inter-IC ( [I2C](https://en.wikipedia.org/wiki/I%C2%B2C) )使用简单的双线总线安排来处理相当低速的数据(高达 400Khz)，以促进芯片和设备之间的通信。它是由 Phillips 在 20 多年前创建的，在当前的微控制器生态系统中非常常见。它的主要优点是通常允许一个主节点和多个从节点(最多 120 个)通过其双线总线(加上地)进行通信。一个缺点是高阻抗限制了物理总线的长度，只有几英尺。尽管如此，当您有一堆设备连接到微控制器模块时，这是一个不错的选择。另一个重要特性是，微控制器可以根据需要单独寻址每个器件。

我目前在旧工作台上没有任何 I2C 项目。Adafruit 有一个小的[教程](https://learn.adafruit.com/adafruits-raspberry-pi-lesson-4-gpio-setup/configuring-i2c)关于设置 I2C 总线，用树莓派，可能有助于你的理解。该页面还提供了到几个示例项目的链接，您可以构建。

我会挑选一些 I2C 设备，把它们放在我的圣诞清单上。当你见到圣诞老人时，请随意向他提起。这一年我一直是个不错的小黑客。

## 摘要

人们仍然会问我这个问题，“[我应该使用哪种微控制器？](https://thenewstack.io/off-shelf-hacker-arduino-raspberry-pi/)“看情况。

在您的项目中让设备相互通信也是如此。也许，你的项目需要一个芯片来和一个树莓派说话。传统的串行通信可能是合适的。也许你有一个彩色液晶显示器连接到你的 Arduino。SPI 方法是您的首选武器。最后，您可能有十几个设备需要向/从您的 [Beaglebone Black board](https://beagleboard.org/black) 发送数据。用 I2C。

与任何其他工程解决方案一样，每种沟通方法都针对项目的特定功能和需求。有些方法适用于一种情况，但不适用于另一种情况。像往常一样，设计物理计算堆栈总是要做出妥协。

希望你现在对自己的选择有了更好的理解。

特征图片:[维基百科](https://en.wikipedia.org/wiki/Serial_communication#/media/File:Parallel_and_Serial_Transmission.gif)。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>