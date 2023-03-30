# 现成的黑客:人工智能进入创客市场

> 原文：<https://thenewstack.io/off-the-shelf-hacker-ai-comes-to-the-maker-market/>

上周，我沿着记忆的小路漫步，谈论旧零件和早期的硬件回收时代。谁能想到我们会让“旧的”五六岁的微控制器在我们的零件箱里积灰？

技术继续以极快的速度发展。Arduino 等基于固件的微控制器已经克隆到 ESP8266 和 ESP32 等支持 WiFi 的微型印刷电路板中。基于 Linux 的设备，如 Raspberry Pi model 3，现在是四核、配备 WiFi、支持桌面的模块，几乎可以以很低的价格买到。

当然，我的重点是你现在就能买到的现成零件。在我看来，只要有点主动性和开放的心态，几乎任何人都可以构建实用、相对便宜的微控制器项目。

这里有一些我认为将在未来两三年内成为“旧技术”的最新进展。我的专家建议是不要让苔藓在你脚下生长太久。最好继续前进。

## 带板载 FPGA 的 Arduino

Arduino bunch 最近推出了他们的新 MKR 维多 4000 板。这款新设备结合了微控制器和现场可编程门阵列(FPGA)。这使设计人员能够在一个易于使用的封装中创建数字信号处理和大规模输入/输出任务所需的硬件逻辑电路。虽然 FPGAs 已经存在了很长一段时间，但它们现在才真正在普通爱好者/黑客中流行起来。可以把它们想象成可重新编程的硅芯片，如美国国家仪器公司[“FPGA 简介:五大优势”](http://www.ni.com/white-paper/6984/en/)页所述。Hackster 有一篇关于董事会的不错的小文章和视频。你基本上不用试验板或烙铁就能构建硬件电路。

另一个与 Arduino 相关的话题是他们转向在线编程。它叫做 [Arduino Create](https://create.arduino.cc/) ，让开发者编写代码，搭建他们的电路板，分享他们的工作。Arduino 项目中心页面值得快速浏览，寻找新的项目创意，看看其他设计师在做什么。据说，Vidor 4000 板的预配置 FPGA 逻辑构建模块和可视化编程环境的集合将很快在线提供，大概是在 Arduino Create 系统中。

## 计算机视觉

我们过去已经介绍过 [JeVois 机器视觉传感器模块](https://thenewstack.io/off-shelf-hacker-machine-vision-meets-robotic-skull2/)。这是一台独立的四核 Linux 机器，配有一台小型摄像机，使用先进的人工智能(AI)算法以每秒 120 帧的速度处理视频流。当我在“赫德利”的视野前走动时，我用我的[机器人头骨](https://thenewstack.io/machine-vision-camera-meets-robot-skull/)中的一个来跟踪我。

[OpenMV](https://openmv.io/) 是另一个机器视觉项目。它的模型使用 [MicroPython](https://en.wikipedia.org/wiki/MicroPython) 编程环境来简化开发人员与传感器的交互方式。功能包括面部检测和眼睛跟踪，以及彩色斑点检测和跟踪。

JeVois 和 OpenMV 传感器之间有相当大的区别。JeVois 远远超出了眼睛和颜色斑点跟踪，进入了使用 Darknet 和 TensorFlow 人工智能模型的对象识别。JeVois 还可以找到消失点，用于道路导航，并记录一段时间内的“惊喜”事件。设置摄像头来监视你的前门，如果有任何变化，比如有人敲门，摄像头会录制一段简短的视频。如果场景没有变化，镜头只是一直看着，没有任何动作。

另一方面，OpenMV 传感器有三个脉宽调制(PWM)端口，因此您的 MicroPython 代码可以直接从板上控制伺服系统，类似于旧的 CMU Pixy 相机的工作方式。Wifi 连接、LCD 和电机控制通过[插件屏蔽](https://openmv.io/collections/shields)集成。有一个非常酷的[交互式开发环境(IDE)](https://openmv.io/pages/download) 可用于编写 OpenMV 设备。

JeVois 和 OpenMV 模块相当巧妙，其他玩家肯定会加入进来。

## 不要眨眼

我认为像 Arduino FPGA 板和机器视觉传感器这样的努力正在兴起，这很有趣。

看看这个 [Vidor 板演示](https://youtu.be/v9lIn2mYdlo)在刚刚过去的周末的湾区制造商博览会上实时进行视频解码和二维码识别。

没错，机器视觉和人工智能相结合的可编程硬件逻辑现在就在这里。谈谈你不断变化的风景。

所有这些活动的主要收获是，我们生活在历史上一个绝对令人惊叹的时代。现成的魔法就在我们身边，相当便宜，而且容易获得。我认为最好的计划是保持消息灵通，不断学习，努力保持相关性。

最好戴上安全帽，因为与未来的碰撞是不可能的。

特征图像: [JeVois](https://youtu.be/7cTfOckkGlE) 。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>