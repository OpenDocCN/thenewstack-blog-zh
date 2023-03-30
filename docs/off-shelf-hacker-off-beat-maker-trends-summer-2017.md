# 现成黑客:2017 年夏季创客趋势

> 原文：<https://thenewstack.io/off-shelf-hacker-off-beat-maker-trends-summer-2017/>

夏季带来了炎热的天气、烧烤，通常还会稍微减缓科技发展的步伐。这是一个很好的时间去探索和总结独特的发展，在懒散的日子里溜进来，这可能会对近期或即将到来的技术产生很大的影响。

我是一个蓝天使，我的工作经常被认为是“不实际的”哦，好吧，这就是[现成黑客](/tag/off-the-shelf-hacker/)的本性，拿一张白纸，实际上制作一个工作原型。所有最新的技术都实用吗？很多时候，我们只是还不知道。

例如，700 美元的触摸屏、Wi-Fi、四核和配备 GPS 的小型化工程奇迹实用吗？我们都知道它是现代手机。我们都有一个。实用吗？你决定吧。

对于今天的潮流话题，我们也可以这么说。很高兴看到组织和个人在那里提出想法，而在过去人们肯定会问“你为什么要这样做？”

## 汽车级 Linux

丰田最近宣布将在其车载娱乐系统中使用[汽车级 Linux](https://www.automotivelinux.org/) (AGL)。我在二月份的嵌入式 Linux 会议上看到了一个演示。大部分工作都集中在人机界面上，如仪表组和平视显示器(hud)。

根据[电子设计](http://www.electronicdesign.com/automotive/toyota-including-automotive-grade-linux-platform-2018-camry)的说法，AGL 背后的大想法是开发一个标准，OEM(原始设备制造商)可以使用该标准将第三方应用和支持引入他们的各种品牌的车辆。

演示软件在几个硬件平台上运行，包括 Raspberry Pi，所以如果你想尝试一下，这是你的机会。

考虑在车辆中使用 Linux 很有趣。今天的汽车有许多内置功能，如 Wi-Fi 连接，可以被黑客攻击和增强。有多少会成为现实，我们将拭目以待。

## 为什么 Alexa 很重要？

凭借 Alexa 助手，亚马逊已经彻底击败了下一个购买零售商品的主导界面:你的声音。

该公司没有任何其他竞争对手，至少在零售领域没有。是的，这个双关语很糟糕。像沃尔玛这样的零售商一直依赖顾客出现在他们的店里买东西。亚马逊把商品直接送到顾客手中。快速交货是最重要的。

现在有了 Alexa 驱动的亚马逊 Echo 和 Dot，你只需要问一下，你的东西很快就会出现在你家门口。亚马逊悄无声息地建立了这个物理计算栈的后端，以优化订购和交付。天衣无缝，毫无痛苦。

我们已经[介绍了在树莓 Pi](https://thenewstack.io/off-shelf-hacker-virtual-physical-alexa-using-3-internet-services/) 上设置 Alexa，并使用语音服务在芯片计算机上闪烁灯光。我还没有用我的 Dot 购物。我确实听电台谈话节目，要求数学转换之类的。

## 说到 Alexa 和芯片

[LinuxGizmo 网站](http://linuxgizmos.com/alexa-ready-digital-alarm-clock-radio-runs-on-hackable-chip-pro/)提醒我注意一款支持 Alexa 的数字闹钟收音机，它使用了可破解芯片 Pro。

即使在三年前，谁会想到这一点。实用？我会说是的。

在过去的项目中，我们已经讨论过芯片。[Mosquitto Under Glass MQTT Broker](https://thenewstack.io/off-shelf-hacker-mosquitto-glass/)，使用芯片板。该芯片的母公司 Next Thing Company 最近发布了 CHIP Pro。这是一台生产就绪的单板计算机，运行 Linux，带有一堆通用输入/输出引脚。两种型号都有车载 Wi-Fi。

现在，初创公司[帕洛阿尔托创新](https://www.paloaltoinnovation.com/) (PAI)有一个 [Kickstarter](https://www.kickstarter.com/projects/paloaltoinnovation/sandman-doppler-the-worlds-best-alarm-clock?utm_source=PAI) 将把它的第二代睡魔闹钟收音机“多普勒”推向市场。

把 Dot 想象成一个支持 Alexa 的极简音频小工具。它还有一个很酷的 LED 环，一个小扬声器和多个麦克风。

睡魔多普勒向完全相反的方向前进。这是一个激活了 Alexa 的类固醇闹钟。前面有一个大的数字时钟显示器，控制各种功能的按钮和一个变色的 LED 条。您可以使用多普勒的六个 USB 端口为您的所有数字设备充电。当然，还有 Wi-Fi 和蓝牙。PAI 的网站大谈该公司在完善扬声器声音方面投入的时间。对我来说，唯一缺少的东西可能是一个彩色液晶显示器。

它与其他“商业”产品不同的另一点是，它运行 Linux，你可以通过一个“隐藏”的 USB 端口进入该软件。我怀疑你可以运行你自己的程序，也许可以安装服务器并使用 SSH 设置远程访问。您是否可以使用 Python 和一些 MQTT 函数来跟踪您的闹钟习惯，从物联网服务器接收命令，或许可以使用 MQTT 或改变面板 led 和数字显示以获得有趣的新效果？

现成的黑客肯定会认识到这种产品的可能性。

我必须研究一下多普勒是如何在 Pro 芯片上实现 Alexa 语音控制的。那里可能会有一些很酷的项目。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>