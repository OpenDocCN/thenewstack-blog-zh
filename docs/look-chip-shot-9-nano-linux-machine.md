# 现成的黑客:看看芯片，9 美元的纳米 Linux 机器

> 原文：<https://thenewstack.io/look-chip-shot-9-nano-linux-machine/>

我的[芯片电脑板](https://getchip.com/)上周六到了。不到一个小时，我就通过复合视频输出将它连接到了我的大屏幕上，并连接到了我的 WiFi 局域网。一个普通的日常 5 伏三星手机充电器提供电源，久经考验的罗技 K400r 无线键盘/鼠标垫让我可以控制字符输入。启动花了大约半分钟。

## 什么是芯片计算机？

像其他微控制器一样，该芯片是一个基于 Linux 的板，能够运行完整的桌面，各种命令行和基于 GUI 的应用程序，以及各种可访问的数字输入/输出引脚。它花了我 9 美元，外加 6 美元的运费。以下是规格:

*   无线宽带/宽带/无线
*   蓝牙 4.0
*   1.0 GHz R8 ARM 处理器
*   4.0 GB 高速存储
*   512 KB 内存
*   复合视频输出
*   带接头的 2.4 英寸 x 1.6 英寸 x .5 英寸主板尺寸

该芯片从一开始就声称它是第一台 9 美元的电脑。它还利用内置的 Linux 网络堆栈，将 WiFi 和蓝牙无缝集成到主板上。

## 我喜欢的是…

我喜欢这款芯片的一点是，Linux 驻留在板载闪存中，就像 Beagle Bone Black 一样，而不是像 Raspberry Pi 一样驻留在 micro-SD 卡上。正如预期的那样，4 GB 的可用空间中还有大约 2.3 GB 用于应用程序和数据。您可以将一些应用程序和相当多的数据塞进这个空间。使用板载内存也应该比 micro-SD 卡更强大。

在我的 Raspberry Pi 项目中，我总是在微型 SD 卡的末端添加一小块透明胶带，这样当我四处搬运设备时，它就不会弹出来。就算我没有 32 GB 的空间。当然，我永远不会丢失芯片上的卡。

将 WiFi 和蓝牙放在电路板上也是芯片的一大优势。很容易在桌面系统托盘中调出 WiFi 小程序，然后简单地选择我的接入点。我注意到信号也很强，表明嵌入式 WiFi 芯片相当敏感。

该芯片使用 Debian Linux 的一个变种，称为芯片操作系统。默认情况下，这个小机器启动到桌面，没有密码。从命令行使用新立得程序管理器，以及旧的备用程序 **apt-get** ，可以很容易地添加应用程序。

## 集成到小工具中

感知和控制环境的基本输入和输出能力是物理计算的基础。由于当前 nano-Linux 机器的所有桌面、连接和便携式选项，很容易被忽略，而没有意识到这些小小的主板通过访问输入和输出引脚，引领了 DIY 物理计算的潮流。

因此，作为对该芯片的几个 GPIO 引脚易用性的快速测试，我从早期项目中盗版了有线点击器，并将其连接到标有 XIO-P0 和 XIO-P1 的 GPIO 引脚。开关的另一端接地。我没有使用任何上拉电阻，它似乎工作正常。顺便说一下，XIO 名称出现在标题上。这是一个很有用的特征，你可能需要一个放大镜才能看出来。

该芯片还包括 Python，就像树莓派一样。我上传了在 Raspi 演示机器中使用的 scrollslides.py 脚本，并简单地更改了库和 GPIO 引脚名称。NextThing 网站上有[关于加载 Adafruit 芯片 gpio 库](https://bbs.nextthing.co/t/adafruit-gpio-library-for-chip/2696)的说明，你需要在脚本运行之前完成这些。xtacocorex GitHub 页面上也有一堆[有用的 GPIO 信息。这些库似乎没有任何上拉/下拉电阻的设置代码，所以我假设它们在电路板内部。或者，也许不是。](https://github.com/xtacocorex/CHIP_IO)

我还通过 Synaptic 程序管理器添加了 xdotool 实用程序。Xdotool 每次被调用时都会输出一个字符。这有点像 Python 脚本中的编程按键。

下面是新的 scrollslides.py 代码。

```
import CHIP_IO.GPIO as GPIO
import time
import os

GPIO.setup("U14_13",  GPIO.IN)
GPIO.setup("U14_14",  GPIO.IN)

while True:
    input_state  =  GPIO.input("U14_13")
    if input_state  ==  False:
  os.system("xdotool search --name 'Impress' key Up")
        print('Button Pressed')
        time.sleep(0.2)

    input_state  =  GPIO.input("U14_14")
    if input_state  ==  False:
  os.system("xdotool search --name 'Impress' key Down")
        print('Button Pressed')
        time.sleep(0.2)

```

完成所有这些后，我只需将一份演示文稿加载到 LibreOffice(你可能也需要安装它)，打开一份幻灯片演示文稿，然后点击进入幻灯片放映。然后，我使用终端启动 scrollslides.py 脚本。

```
chip%  sudo python scrollslides.py

```

每次我按下按钮，LibreOffice 就会在幻灯片堆栈中向前或向后移动。

你应该知道复合视频的分辨率限制在 640×480 左右。然而，幻灯片的文字和图片清晰明了。

芯片上 LibreOffice 的性能给我留下了深刻的印象。虽然肯定没有笔记本电脑或四核 Raspberry Pi 3 快，但我将在未来的会议技术演讲中使用该芯片管理我的幻灯片。

## 后续步骤

我认为芯片是一个很酷的小型纳米 Linux 机器。它毫无怨言地运行 Python 和 LibreOffice，默认运行 SSH，看起来相当稳定。微控制器世界似乎已经在 Python 上安顿下来，因为它们是通用编程语言，这使得编写代码变得容易，无论你是在 Raspberry Pi、Beagle Bone 还是 CHIP 上。

别忘了芯片有一大堆数字 gpio 引脚。现有黑客可能研究的一个尚未开发的用途是简单的面向按钮/开关的界面。我们将在以后的专栏中讨论这个想法。

让我们知道你在用你的芯片做什么。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>