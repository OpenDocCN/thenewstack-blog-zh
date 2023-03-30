# 现成的黑客:微控制器的趋势

> 原文：<https://thenewstack.io/off-shelf-hacker-trends-microcontrollers/>

微控制器——那些像小型计算机一样工作的集成电路——在过去的几年里已经取得了长足的进步。

有 Arduino 风格的微控制器和它的复制品。这些设备是基于固件的，这意味着你可以编写你的程序，然后将它上传到芯片上的电可擦可编程只读存储器(EEPROM)中。它的速度很快，并在通电时运行上传的程序。该模块读取一些输入，执行一些计算，并设置一些输出。其他常用的微控制器包括 PIC 和 MSP430。

另一种主要的现成微控制器是单板计算机(SBC)。这些主板通常基于 32 位处理器，具有大容量存储器和操作系统，可以用多种语言编程。Raspberry Pi、BeagleBone 和 CHIP computer 都属于这一类。他们普遍运行某种形式的 Linux。有些甚至可以作为基本的台式电脑。

有很多便宜的现成的单板机。今天，我想把重点放在你可以在项目中利用的近期趋势上。

## 闪存

像 Raspberry Pi 及其克隆产品这样的主板将操作系统及其所有数据都存储在 nano-SD 卡上。这使得改变项目的行为变得简单，只需换一张有您喜欢的操作系统映像和应用程序的不同的卡。

最近的趋势是将操作系统放在闪存中。比格犬骨和芯片板使用这种存储方法。它们预装了 Linux。插上电源，它们就可以开始工作了。可以使用各种工具，像“ **apt-get** ”更新到最新版本，添加应用等等。

如果你不想为 nano-SD 卡映像而烦恼，试试这些基于 FLASH 的板。它们开机快，功能全，可靠。

## 车载 WiFi

板载 WiFi 是 [Pi](https://www.raspberrypi.org/products/raspberry-pi-zero-w/) 、 [BeagleBone](https://beagleboard.org/black-wireless) 和[芯片](https://getchip.com/pages/chippro)上无线连接的热门门票。这三个都有带 WiFi 的版本。通常还包括蓝牙无线电，用于本地连接耳机、键盘/鼠标垫和其他短程小工具。

NotEnoughTech 在内置的 Raspberry Pi WiFi 收音机上做了一些[速度测试](http://www.notenoughtech.com/raspberry-pi/raspberry-pi-internet-speed/)。结果当然不会很糟糕。请记住，可穿戴设备和 DIY 项目通常不会像视频流那样有巨大的数据吞吐量要求。

我认为随着行业对人工智能(AI)和增强现实(AR)的使用增加，WiFi 将成为未来大多数 SBC 的标准配置。这并不意味着不配备 WiFi 的主板将会消失。你贴在板上的任何无线电，无论是 WiFi、蜂窝、蓝牙还是任何耗电的设备。低功耗项目可能不需要任何连接，所以为什么不使用不带无线电的电路板呢？成本也会更低。

## 不在意的

许多人正在发现[【无头】](https://en.wikipedia.org/wiki/Headless_computer)项目的奇迹。

无头仅仅意味着你的小工具没有显示器。通常，显示器连接到 HDMI 端口或小型 TFT LCD 显示器，后者连接到微控制器的数字输入/输出引脚。

没有监视器，您可以做自动化的工作，比如充当网络存储设备或 MQTT 服务器。 [Mosquitto under Glass](https://thenewstack.io/off-shelf-hacker-mosquitto-glass/) 项目是无头的，在客户端设备之间来回传递 MQTT 消息。

通常，您要么临时连接一个监视器来编写程序，要么使用 SSH 从另一台机器远程登录。一旦你习惯了远程登录，通过网络，这种工作方式是非常简单和有用的。

运行项目 headless 还可以让您操作和更新难以访问的小工具。你的设备可能在楼顶或者埋在集装箱里。没有办法使用监视器，所以远程登录到一个无头微控制器是唯一可能的方法。

## 继续看

跟上最新微控制器的一个很棒的页面是 [LinuxGizmos](http://linuxgizmos.com/) 。基于闪存、配有 WiFi 的无头微控制器正变得越来越普遍，可以让您的项目变得更小、更方便。

技术会不断成熟。寻找新的方法来利用未来所有的酷功能。

特写图片:[猎兔犬黑色无线](https://beagleboard.org/black-wireless)。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>