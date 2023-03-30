# 现成的黑客:Linux 可穿戴设备的展示时间

> 原文：<https://thenewstack.io/off-the-shelf-hacker-showtime-with-a-linux-wearable/>

我正在狂热地准备我的蒸汽朋克会议徽章(v5 ),以迎接即将于 7 月在 OSCON 举行的技术演讲。[我的演讲](https://conferences.oreilly.com/oscon/oscon-or/public/schedule/detail/67363)涵盖了徽章制作细节、各种功能以及我对设计的思考过程。我会戴着它在会议上走来走去，在演讲前播放一段简短的“Torq 博士”宣传片。

戏剧性的开场白是一种由来已久的开始会话的方式，尤其是当它涉及到硬件的时候。让它令人难忘对于积极的观众体验很重要。

## 要么做大，要么回家

我想出的计划是站在房间的后面，穿着我的蒸汽朋克大礼帽、粗花呢夹克和佩斯利领带，在与会者进来演讲时向他们打招呼。在放映的时候，我会走到房间的前面，从脖子上取下徽章，然后把它插到投影仪上。在快速重启和几句鼓舞人心的话之后，我们将开始我的节目。

你认为有人会注意到我刚刚佩戴的徽章上的图书馆幻灯片吗？

经验表明，有很多事情可能会出错，导致我拿着徽章四处摸索，耽误了整个操作。这不是吸引观众的积极方式。

我决定使用一点自动化魔法，从徽章模式变形到桌面模式，以避免爆发成一个巨大的表象火球。你必须喜欢可穿戴设备上的 Linux。

## 在 LCD 和 HDMI 之间切换

徽章有一个树莓 Pi 2，[，一个 3.5 英寸的彩色液晶触摸屏](https://www.adafruit.com/product/2441)，一些传感器和一个蒸汽朋克主题的底盘和铭牌。您可以将大屏幕或投影仪插入 HDMI 连接器。

我发现在 Raspberry Pi 上的 3.5 英寸显示器和 HDMI 端口之间来回切换的最可靠的方法是在目录之间移动配置文件并重新启动。

很长一段时间，我使用两个小的命令行脚本来完成这项工作。在查看 LCD 或 HDMI 连接的显示器时，我会使用无线键盘键入适当的命令，徽章会以正确的模式重新启动。它的工作原理是将 framebuffer 配置文件(用于 LCD)复制到/etc/X11 目录，然后重新启动。LCD 的 X11 目录中没有配置文件，HDMI 的 X11 目录中没有配置文件。

这里是代码 lcd.sh 代码。

```
sudo cp  /home/pi/99-fbdev.conf  /etc/X11/xorg.conf.d/
sudo shutdown  -r  now

```

这里是 hdmi.sh 的代码

```
sudo mv  /etc/X11/xorg.conf.d/99-fbdev.conf  /home/pi
sudo shutdown  -r  now

```

它们从命令行运行如下:

或

当然，这种方法也有缺点。你看起来有点傻，带着一个可佩戴的 Linux 会议徽章，在键盘上走来走去。不仅要无头(没有显示器)，挂在脖子上也要无键盘。

如果我只想关闭徽章，而手边没有键盘，会发生什么？我们不想通过拔掉插头来破坏 Pi 上的 SD 卡。

不仅如此，使用“-r”，重新启动选项不允许在 Linux 再次启动备份之前拔下或插入监视器。

## 一键解决方案

一个非常实用的解决方案是使用几个按钮来运行适当的脚本。我们还应该用“-h”选项将其更改为暂停系统，这样我就有机会更换电缆或打包徽章以便运输。

在当前配置中，Raspberry Pi 使用 SPI 引脚以及 GPIO 引脚#24 和#25 来控制 LCD 屏幕(SCK、MOSI、MISO、CE0、CE1)。我们也可以使用 GPIO #18 来调暗显示器。这仍然留下 20 个 GPIO 引脚供可能的按钮使用。

我选择 GPIO #16 和 GPIO #20 作为关机按钮。按钮通过 1K 欧姆的电阻器从地连接到每个相应的引脚。我在 Pi 中使用了内置的上拉电阻，这样就不会因为浮动(随机电压)引脚读数而产生奇怪的行为。

一旦硬件引脚准备就绪，我就使用 Python 脚本来检测按钮何时被按下。

下面是 switch-down.py 代码。

```
import RPi.GPIO as GPIO
import time
import os

GPIO.setmode(GPIO.BCM)

GPIO.setup(16,  GPIO.IN,  pull_up_down=GPIO.PUD_UP)
GPIO.setup(20,  GPIO.IN,  pull_up_down=GPIO.PUD_UP)

while True:
    # USB side button
    input_state16  =  GPIO.input(16)
    # ultrasonic sensor side button
    input_state20  =  GPIO.input(20)

    if input_state16  ==  True:
        print('Button 16 Pressed')
        os.system("sudo cp /home/pi/99-fbdev.conf /etc/X11/xorg.conf.d/")
  os.system("sudo shutdown -h now")
  # os.system("./test.sh")
        time.sleep(0.2)

    if input_state20  ==  True:
        print('Button 20 Pressed')
        os.system("sudo mv /etc/X11/xorg.conf.d/99-fbdev.conf /home/pi")
        os.system("sudo shutdown -h now")
        time.sleep(0.2)

GPIO.cleanup()          # clean up GPIO on CTRL+C exit

```

为了让方案在重启后自动工作，我在/etc/rc.local 文件中添加了 Python 脚本执行。编辑文件时你必须使用 sudo，因为普通用户没有适当的权限。

```
pi%  sudo vi  /etc/rc.local

```

这是我的/etc/rc.local 文件。

```
#!/bin/sh -e
#
# rc.local
#
# This script is executed at the end of each multi-user runlevel.
# Make sure that the script will "exit 0" on success or any other
# value on error.
#
# In order to enable or disable this script just change the execution
# bits.
#
# By default this script does nothing.

python  /home/pi/py-scripts/switch-down.py  &amp;

exit  0

```

在 bootup 上，switch-down.py Python 脚本在后台永远循环，等待两个按钮中的一个被按下。

现在，当我走到房间前面并按下 HDMI 按钮时，徽章将切换到桌面模式。我会拔掉电池，插上投影仪，用壁式电源插座通电。

演示结束后，我将按下 LCD 按钮，徽章将恢复到“走动”(徽章)模式。我会拔掉墙上的电源插头和投影仪。我会把徽章重新挂在脖子上，用电池组重新供电。

## 后续步骤

我已经测试了几次 LCD/HDMI 切换过程，效果非常好。当然，程序和时间安排会在彩排中进行微调。

我认为在徽章模式下重新开机时，在 3.5 英寸的液晶屏幕上自动播放宣传片视频可能会很好。

徽章模式界面使用按钮有很多可能性。我们不局限于微型开关。笔和隐形眼镜有用吗？不知道。或者，磁簧开关怎么样。多按钮有线吊坠有意义吗？也许我们可以用它来控制幻灯片。我们可以使用 Python 脚本甚至处理语言以多种方式感知按钮的按下。

走出去，在你的下一个可穿戴项目中利用 Linux 自动化的力量。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>