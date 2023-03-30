# 现成的黑客:这是黑客的季节

> 原文：<https://thenewstack.io/off-shelf-hacker-tis-season-hacking/>

啊，是的，圣诞节就要到了。我喜欢一年中的这个时候，所有的灯光，快乐的脸庞和愉快的心情。与朋友和家人重新联系，同时分享对未来的乐观，这很好。

零售商们正如火如荼地进行着，用优惠和巧妙的折扣轰炸我的邮箱。虽然很多人都为最新的 iPhone(或 Galaxy)、大屏幕甚至一辆新车而疯狂，但我的要求通常都很适中。我关注的是更实用的东西，有些人可能会说是“非常规”的东西。Torq 博士这个绰号和写“[现成黑客](/tag/off-the-shelf-hacker/)”专栏，对我的神秘圣诞老人将在我的清单上找到的事情类型来说，并不是那么明显。

## 圣诞节过去了

例如，几年前，我的大女儿给我买了几块 [Digispark 板](http://digistump.com/products/1)，每块大约 8 美元。这些小奇迹被宣传为简单、轻便、几乎一次性的微控制器。我用它们做了一些三色的庭院灯。它们用 Arduino IDE 编程，直接插入 USB 端口。正如您所料，虽然它们看起来可靠且健壮，但是功能非常有限。对于简单的项目来说，这是一个很棒的小设备。

最近，我很高兴地在树下发现了一个[树莓 Pi 3](https://www.adafruit.com/product/3055) 和 [3.5 英寸彩色 TFT 触摸屏 LCD](https://www.adafruit.com/product/2097) 。这些部分很快就融入了最新一代的会议徽章。Pi 和 display 来自 Adafruit。如果使用 Pi 运行显示，请确保使用 Adafruit 提供的自定义图像。此外，在尝试升级到新版本时要非常小心，因为之后会有无穷无尽的挑战。我可以忍受它，因为这个徽章基本上是长期使用的，使用它的定制版 Raspbian。

顺便说一句，当你在一个非 3.5 英寸的 LCD 显示器上使用它时，最新的“拉伸”版本的 Raspbian 比旧版本要快得多。当我将徽章的 Pi 3 移动到[机器人头骨](https://thenewstack.io/machine-vision-camera-meets-robot-skull/)上时，我简直不敢相信 Stretch 的性能显著提高。我只是把 nano-SD 卡换成了一个旧的 Pi 2，让徽章再次工作。对于这项工作来说，Pi 2 肯定够快了。现在， [guvcview](http://guvcview.sourceforge.net/) 工作得很好，连同 [JeVois 摄像机](http://jevois.org/)甚至 [LibreOffice 给](https://www.libreoffice.org/discover/impress/)留下深刻印象，这一切都是一次性的。

## 圣诞礼物

现在什么样的事情引起了我的兴趣？

当我思考未来的黑客故事时，新的硬件、传感器和设备总是在我脑海中浮现。跟上最新的小玩意和小发明是永无止境的追求。当然，“下架”运动已经达到了临界质量。对于物理计算黑客来说，这是一个激动人心的时刻。

树莓派克隆的新作物是疯狂的。

最近，几乎所有的笔记本电脑都配备了板载 WiFi 和蓝牙，以及四核处理器、外置天线连接器和不断缩小的外形。一些运动 USB 3.0 端口和板载麦克风。新型 USB 非常重要，因为像 JeVois 机器视觉设备这样的智能传感器在 5 伏电压下需要大约 800 毫安的电流。USB 3.0 通常可以通过一根电缆提供这样的电量。此外，[使用 Pi 克隆构建 Alexa 设备](https://thenewstack.io/off-shelf-hacker-virtual-physical-alexa-using-3-internet-services/)将更容易使用板载麦克风，而不必求助于 USB 端口的丢失和外部音频输入部分的费用。

Lowkeytech.com 有一个很好的，当前运行的最新树莓 Pi 3 替代品。

## 圣诞节的未来

就在最近，这只[袖珍猎犬](https://beagleboard.org/pocket)出现在我的雷达上。这是一个缩小版的[比格犬黑色](https://beagleboard.org/black)，大约有两个 50 美分硬币那么大。

我还没有钩住一个，虽然它看起来像一个不错的齿轮。

袖珍小猎犬配备了 Octavo Systems OSD 3368 ARM Cortex-A8 芯片，运行频率为 1 GHz。还有 1 GB 的 DDR3 内存，两个可编程实时单元(pru)，8 个模拟和 44 个数字输入/输出引脚。

当然，减少 Beaglebone 的占用空间意味着没有任何标准的 USB 或以太网端口。WiFi 和蓝牙也需要适配器或斗篷。

这一切都没问题，因为 Bone 系列面向需要高性能计算能力以及大量输入和输出的机器人和项目。无论如何，机器人通常使用 I2C、SPI 或其他硬件类型的接口在机载系统之间进行通信。你可能还会将骨骼连接到一个额外的 Raspberry Pi，它将处理用户界面和外部世界的通信任务。随着越来越多的人对这项技术感到舒适，在 DIY/现成的世界中，为多设备项目使用硬件接口正逐渐成为主流。

所以，这一季有一些关于极客礼物的想法。还有时间让你的订单运转起来。

## 附录:RIP Linux 日志

我还想提一下 Linux Journal 进入天空中那个伟大的网络服务器的过程。遗憾的是，他们最近停止了运营，就像科技出版行业的许多其他公司一样。

自 1994 年以来，它们是 Linux 文章、新闻和事件的黄金标准。我很荣幸在网站和印刷杂志上发表了一些我的专题报道。走进一家巴诺书店，看到我的故事出现在一本顶级杂志的封面上，这种激动是相当令人兴奋的。他们是很好的合作伙伴，总是对我很好。

我相信所有的 Linux 期刊人才都会找到新的机会。我祝他们一切顺利。

通过 Pixabay 的特征图像。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>