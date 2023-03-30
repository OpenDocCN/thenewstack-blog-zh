# 现成的黑客:添加立体声音频到您的 DIY 小工具

> 原文：<https://thenewstack.io/off-the-shelf-hacker-add-stereo-audio-to-your-diy-gadgets/>

上周，我们看了如何通过树莓派主板将一个单声道 5 瓦音频放大器连接到我的会说话的机器人头骨赫德利上。声音将来自他口腔顶部的一个小扬声器，再加上同步的下颌运动，将使他说话。我目前正在寻找适合他脑袋的完美扬声器。快看，伊戈尔，它还活着！

随着赫德利的声音，我偶尔需要从他的树莓 Pi 3 输出立体声，比如当他用[便携式蒸汽朋克监视器](https://thenewstack.io/off-the-shelf-hacker-building-the-skull-top-computer-monitor/)在“骷髅顶”模式下运行时。蒸汽朋克会议徽章(带有 Raspberry Pi 模型 2)还具有音频输出功能，我想在做小型技术演示时利用这一功能。最后，由于华硕 Linux 笔记本电脑的扬声器非常小，所以在听该设备的音频时，如果能有多一点的功率就太好了。

让我们为这项工作做些准备。

## 制作便携式放大器

我的最新解决方案是将一个小型音频放大器板集成到便携式蒸汽朋克监视器中。[显示器的视频驱动板](https://www.banggood.com/10_1-Inch-1280x800-HD-Display-TFT-LCD-Module-Kit-For-Raspberry-Pi-p-1109750.html?rmmds=buy&cur_warehouse=CN)，虽然支持 HDMI 视频，但没有 HDMI 音频。有些视频板确实支持音频，如果您想简化项目中的设备数量，您可以专门寻找该功能。然而，不难拼凑出一个配套的音频放大器来集成显示器和我的其他小工具。

我选择的每通道 10 瓦立体声放大器仅仅是一个 1-1/2 英寸的方形板，前面有一个电位计和用于开/关和静音开关的插座。

![](img/16f243d74e0721f5e2215426cea64047.png)

带有电源模块和蒸汽朋克监视器的放大器和扬声器

电路板的后边缘有两对扬声器输出螺丝端子板、12 伏电源输入插座和一个音频输入端口。

连接放大器非常简单。我重新利用了一套旧的电脑扬声器，把它们从塑料外壳中取出来，并在它们的端子上加了一小段电线。电线的另一端被简单地剥掉，拧入放大器板上的端子板。

音频输入通过标准的双通道电缆提供，您可以使用该电缆将智能手机连接到汽车上的收音机。大多数人称之为“辅助”电缆。我实际上使用我的智能手机进行了初步测试，尽管连接器套筒必须稍微削减以进行连接。我的 Galaxy 8+有一个鹈鹕保护壳，耳机连接的孔对于电缆插头来说太小了。我使用 Dremel 和一个打磨鼓来缩小塑料连接器盖的外部，这样它就可以毫无干扰地穿过手机壳上的孔。

音频输入电缆对位置非常敏感。如果连接器没有完全正确地插入插座，一个或两个通道上会有静电干扰、60 赫兹的嗡嗡声或失真的音频。也许只需从一元店购买一根新的辅助电缆就能解决问题。

## 后续步骤

有了好的输入信号，音量相当不错。我用 12 伏壁式电源插座和[紧凑型便携式电源插座](https://thenewstack.io/off-the-shelf-hacker-building-your-own-compact-portable-power-brick/)运行放大器，声音没有任何差异。

重新设计的电脑扬声器听起来对我的口味来说有点小。对于普通的声音，比如 YouTube，这不是什么大问题。播放歌曲和音乐是可以的，但不要指望音频发烧友级别的性能。我在寻找更好的演讲者。

另一方面，现有的小型扬声器可以很好地集成到蒸汽朋克显示器的基础上。我需要找到一种方法来安装它们，以便在折叠和运输显示器时保护它们。

将立体声音频添加到您的物理计算项目是相当容易的，并且在通常的来源中有很好的放大器选择。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>