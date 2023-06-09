# 黑客硬件:蒸汽朋克名字徽章发展的永无止境的传奇

> 原文：<https://thenewstack.io/hacking-hardware-the-never-ending-saga-of-steampunk-name-badge-development/>

我的会议徽章的目标很简单:

*   创造一种对话的破冰方式来帮助我认识新的人。
*   探索可穿戴设备在现实世界中的作用。
*   确定并培养新的可穿戴计算堆栈所需的技能

我也喜欢让我的技术变得有趣。蒸汽朋克主题的小玩意当然吸引了人们的注意力，并允许大量的设计创意和古怪行为。

今天，我们将介绍我的“电子会议个性识别装置”的发展，通常称为姓名牌。即使像这样的小型硬件开发项目也有许多可移动的部分，特别是当你加入网络，使其可穿戴并通过多次迭代进行修改时。我的任务是帮助读者了解当你着手下一个面向硬件的可穿戴计算项目时，你可以期待什么。

## 版本 1.0

你可能还记得几个月前徽章的[原始版本 1.0](https://thenewstack.io/wearable-computing-electro-matic-conference-personality-identification-device/) 。第一个蒸汽朋克名称徽章有一个 1.8 英寸的彩色 TFT 屏幕，一个 Arduino Pro-Mini 微控制器，四节 AA 电池，一个小电压调节模块和一个蒸汽朋克风格的黄铜框架，以将整个作品结合在一起。固件在显示 160×128 像素位图图像和 DS18B20 温度传感器测量的室温之间切换。

这个设备用标准的会议徽章挂绳挂在我的脖子上。

> 在佩戴徽章参加了几次当地活动后，我意识到它有点像你日常生活中常见的定时炸弹，就像任何流行的 Looney Tunes 卡通短片中看到的那样。可能不是会议演讲者的最佳选择，尤其是在旅行时，如果你明白我的意思。

尽管我犯了令人讨厌的公关过失，但这个徽章绝对在活动中和网上引起了相当多的关注。我认为这是构建物理计算可穿戴设备的第一步。

## 版本 2.0

在随后的文章中，我谈到了使用 Arduino Yun 将徽章联网。在进行原型开发时，很快就发现试图将板载 SD 卡(在 LCD 模块上)库与 Yun 的桥接功能结合使用存在巨大的冲突。你必须将彩色位图图像存储在 SD 卡上，而桥接库需要联网。我探索了许多解决这个问题的方法，除了重写这两个库之外，没有找到可行的解决方案。此外，Yun 80%的可执行代码空间仅用于将图像显示在彩色 LCD 屏幕上，没有留下多少空间来将酷的新徽章功能添加到固件中。遗憾的是，我已经不再使用 Yun 来进一步开发徽章了。

硬件经常出现死胡同。好消息是，只花了大约一周的时间，我就意识到云并不完全适合我的特定应用程序。它仍然是一个非常有能力和强大的板，可能会出现在未来具有不同要求的徽章中。

快速失败，并重新定向到您认为可能有效的硬件项目原型制作。

## 模块化

在 Yun 崩溃后，我回到了基础，并决定我也需要使事情模块化，这样组件可以在项目迭代甚至项目之间交换，而不必不断地焊接和拆卸一切。

3.0 版本带来了模块化，同时将网络功能放在了次要位置。为了简化原型制作，我还回到了标准的 Arduino Duemilanove。LCD 分线板使用 10 针插头进行连接，然后将我使用的任何微控制器与某种类型的母匹配连接器连接起来，这是完全有意义的。事实证明，10 针可堆叠接头是制作我自己的电缆和连接器的经济实用的解决方案。

我还通过构建一条两英尺长的电缆来连接 LCD(显示单元)和微控制器(控制单元)，将模块化向前推进了一步。独立的模块允许显示单元简单地连接到我的蒸汽朋克夹克的翻领上，然后将控制单元连接到我的腰带或护腕上。一个皮革护腕，小的微控制器的发光二极管闪烁着，肯定符合蒸汽朋克的装饰美学，非常显眼。

模块化组件也让我可以用几个黄铜螺栓将 LCD 拧回原来的 1.0 版徽章，以便在我想演示 1.0 版徽章时使用。

## 最新最棒的

所有这些开发和实验将我们带到了 4.0 版本。

我不仅模块化了名称徽章，还尝试使用了 Beagle Bone Black 和 Raspberry Pi 2 板。

再次，像云，我发现小猎犬骨可能不适合我的目的。互联网上的一切都说，使用 Beagle Bone Black board 的彩色 TFT LCD 需要重建 Linux 内核以使用 framebuffer 驱动程序。Arduino 平台有处理这些细节的库。构建一个新的 BBB 内核比我当时想做的要多得多。

树莓派也是同样的情况，除了有所改变。有很多关于将 1.8 英寸 Adafruit 彩色 TFT 显示屏与树莓 Pi 相结合的文档——你必须编译一个新的内核才能让它工作。

事实证明，我读到的大部分内容都有点过时了，正确的驱动程序实际上已经内置到了最新版本的 Raspbian 中。所有需要做的就是在启动时加载适当的帧缓冲驱动程序，然后你就可以在微型屏幕上显示东西了。将内置驱动程序与四核 Raspberry Pi 2 的速度相结合，似乎是一个电池供电的联网蒸汽朋克名称徽章的潜在可怕平台。

在几次错误的启动之后，我能够在 LCD 上调出 Linux 桌面。鼠标光标甚至移动了。你肯定不能浏览 Drudge report 或 Y-Combinator，尽管我现在有一个适合电池供电操作的小屏幕——就像一个姓名牌。

在我的研究中，我还发现一些人使用 MPlayer 在小 TFT 屏幕上播放视频。

> 果然，通过一些精心选择的命令行选项，MPlayer 可以毫不费力地以 20 到 30 FPS 的速度运行视频。

正如您所料，音频不一定能跟上视频，尤其是当它们达到 150 MB 的文件范围时。我不需要准确的音频跟踪我的姓名牌上的视频。下面是我使用的命令行:

```
mplayer  -nosound  -loop  0  -vo fbdev2:/dev/fb1  -x  160  -y  128  -zoom  -flip  -vf rotate  1  time-for-choosing.mp4

```

所有的初始测试都是通过 HDMI 连接的大屏幕、插入板载网络连接器的 LAN 电缆和罗技 USB 无线键盘/鼠标垫完成的。一切正常后，Edimax USB Wi-Fi 芯片被用来建立与我的本地无线局域网的连接。

那时，从 Linux 笔记本通过 SSH 进入 Pi 并运行 MPlayer 来播放视频是一件很简单的事情。这个装置非常好用。

顺便说一下，创建 19 世纪 80 年代风格的蒸汽朋克视频的一个简单方法是在 Kdenlive 中编辑电影时应用棕褐色、旧电影、划痕和灰尘效果滤镜。

我将 Pi 和 LCD 与 2200 mAh 的手机应急电池配对，以获得 3 个半小时的视频播放时间。

最后，我在`/etc/modules`文件中添加了以下文本，这样驱动程序就会自动加载:

```
fbtft_device name=adafruit18 verbose=0

```

我还在`/etc/rc.local`文件中放了 MPlayer 命令行，在开机后立即启动视频。

## 结论

可穿戴设备是新的平板电脑和物联网。这甚至更好，因为硬件变得如此强大，相当容易使用，几乎任何人都负担得起。

我有很多新功能和即将到来的蒸汽朋克会议徽章版本的修改。这是黑客硬件史上最伟大的时代。

你会打造什么样的“可穿戴”？

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>