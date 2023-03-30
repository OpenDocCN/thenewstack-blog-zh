# 无需电池的设备依靠无线电波供电，可以无线编程

> 原文：<https://thenewstack.io/battery-free-programmable-devices-run-radio-waves/>

如今，手持、便携技术和可穿戴设备的数量令人难以置信。制造商通常会尽可能缩小他们的设计，但设备尺寸最终会受到电池的限制，所有电池在耗尽之前都有一定的容量，必须再次充电，这使得设计师在电池寿命与功能和美观之间取得平衡成为一项挑战。

但是，如果研究无线能源的科学家们成功了，有一天电池可能会被完全淘汰，从而创造出新一代的无电池设备。到目前为止，我们已经看到了充满希望的研究，从无线信号的[环境反向散射](https://thenewstack.io/delivering-power-with-wi-fi-signals-to-the-next-billion-devices-no-batteries-required/)、由体热供电的[传感器](https://thenewstack.io/battery-free-sensor-patch-harvests-power-body-heat/)和在“生物细胞”上运行的[微芯片](https://thenewstack.io/one-day-may-embedded-biologically-powered-microchips/)中收集到的能量与推动活细胞的过程相同。但是许多这样的设备速度很慢，一旦部署就不能重新编程。

现在，代尔夫特技术大学[和华盛顿](http://www.tudelft.nl/en/)[大学传感器实验室](https://sensor.cs.washington.edu/)的科学家开发出了一种配备传感器和微芯片的无电池系统，该系统可以完全由无线电波供电，速度比类似的环境供电设备快 10 倍。最重要的是，与类似设备相比，它还可以下载可执行文件，允许在需要时重新编程。

[https://www.youtube.com/embed/rvtyZIPyXMs?feature=oembed](https://www.youtube.com/embed/rvtyZIPyXMs?feature=oembed)

视频

## 被动供电和可重新编程

该项目自 2006 年以来一直在开发中，被称为 WISP，即无线识别和传感平台，是目前可用的新兴计算 RFID (CRFID)技术之一。特别是，WISP 能够通过将传统 RFID(射频识别)阅读器(与零售店入口处看到的机器相同)发射的射频转换成电能来被动供电。

该项目的最新成果是增加了 Wisent(无线发送的缩写)，这是一种更快、更可靠的面向下行通信的 CRFIDs 协议，可以容忍工作功率的波动。“Wisent 的新颖性在于它能够根据长度调节机制，自适应地改变阅读器发送的帧长度，从而在不同的信道条件下最小化传输时间，”该团队在他们的研究论文中写道。“Wisent 支持无线 CRFID 重新编程，展示了世界上第一个无线可重新编程(软件定义)的 CRFID。”

WISP 由开源、开放架构 EPC Class 1 Generation 2 RFID 标签构成，除了任何附加传感器之外，该标签还集成了完全可编程的 16 位微控制器。它不同于普通的 RFID 标签，因为它是可编程的，并且可以是多功能的。

“与 WISP 不同，传统的 RFID 标签是黑匣子，不能执行任意的计算机程序，也不支持传感器，”研究人员解释说。“我们已经向全世界的合作者发出了信息。许多应用都与检测相关，但我们也惊讶地发现，通过 WISPs 可编程性，加密和安全领域也有许多应用。”

当然，它还远没有智能手机或笔记本电脑强大——但 WISP 在需要低功耗、无电池传感和计算的情况下仍然非常有用。

“它不会运行视频游戏，但它可以跟踪传感器数据，完成一些最小的处理任务，并与外界通信，”华盛顿大学的研究员艾伦·帕克斯告诉 [Fast Company](http://www.fastcodesign.com/3059141/this-battery-free-computer-sucks-power-out-of-thin-air) 。“想象一下，如果你的壁纸可以运行应用程序，或者改变颜色以适应你的照明，而不必将其连接到任何东西上。这不再是不可能的了。”

## 熏肉包裹的一缕

该团队认为，基于 WISP 的设备也可以用于监测地震多发地区的建筑结构完整性，在这些地区，更换大量使用电池的有线传感器可能是一个后勤噩梦。传感器增强农业也是一种可能性，可以提高效率和作物产量。

WISP 技术作为医疗设备、下一代起搏器或血糖监测植入物也可能特别有效，因为它们不再需要电池来维持长期功能。研究小组测试了通过用塑料薄膜包裹 WISP 来创造可重新编程的组织植入型 CRFID 的可能性。然后在每一面放上六层熏肉，以模拟植入皮下的植入物，并放在离天线不远的地方。“我们能够在 63.55 秒内成功地用完整的 RFID 堆栈对 WISP 重新编程，尽管来自肉类的反向散射信号有所衰减，”该团队写道。

研究人员现在正在研究一种将数据安全传输到多个 CRFID 标签的方法，以及数据压缩和在出现故障时恢复传输的方法。因此，虽然免电池的强大笔记本电脑可能还有很长的路要走，但这项技术可能很快就会被用于将可重新编程的物体连接到不断增长的物联网。

在 WISP Wiki 上阅读更多内容。

图片:代尔夫特大学和华盛顿大学传感器实验室

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>