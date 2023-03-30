# 现成的黑客:让 MQTT 代理在芯片平台上工作

> 原文：<https://thenewstack.io/off-shelf-hacker-putting-mqtt-broker-work-chip-platform/>

MQTT 消息传递协议非常适合物理计算项目和机器对机器的消息传递，因为它独立于内容。您可以在消息中放入任何您想要的内容，而不用担心格式或内部结构。消息结构在发送端和接收端被定义、解释和作用。发布到主题的消息可以有不同的解释，这取决于您编写的代码。一个边缘设备可能会将“1”消息解释为打开 LED 的命令，而笔记本电脑在查看相同主题的相同“1”消息时，可能会在用户的桌面仪表盘上点亮一个绿点。

在这一期的[现成黑客](/tag/off-the-shelf-hacker/)专栏中，我们将看看在联网到基于[芯片低成本处理器](https://www.engadget.com/2015/05/10/chip-is-a-9-raspberry-pi-killer/)的数据中心的几个实际设备上使用 MQTT 作为消息传输方法。

听起来很复杂。幸运的是，我们可以使用 [Python](https://www.python.org/) ，它可以在几乎所有基于 Linux 的系统上运行。

## Python 和库是编程粘合剂

早在发现 MQTT 之前，我就开始在 Raspberry Pi 上用 Python 编写程序，因为它被捆绑到了 Raspbian Linux 中。事实证明，Python 很容易安装在芯片上，我的 Xubuntu Linux 笔记本也是如此。更重要的是，所有这些平台都有 Python MQTT 库。

Paho 项目是一个流行的 MQTT 库。它很容易安装在树莓派和芯片上。我只是在 Xubuntu 笔记本上使用了 Synaptic 包管理器来加载 Paho-MQTT 库。

首先，如果你需要把 Python 放到芯片上或者你的 Xubuntu Linux 笔记本上，使用下面的命令行:

```
sudo apt-get install python

```

Python 有自己的包管理器，叫做 [pip](https://packaging.python.org/installing/) 。只需在 Raspberry Pi 和芯片上运行 pip 来安装 mqtt 库。

```
sudo pip install paho-mqtt

```

安装完成后，继续将库集成到一些 Python 代码中。

## 读取芯片上的按钮

作为发布者和订阅者的 MQTT 代理和客户机可以在同一个设备上愉快地工作。考虑到芯片或 Raspberry Pi 等设备上提供的所有通用输入/输出(GPIO)引脚，它还是一个强大的工具。

考虑到这一点，一个简单的 Python 脚本并不多，它在芯片上运行，等待按钮按下，然后在“mqtt”主题下向代理(在我们的例子中是本地的)发布消息。

```
import paho.mqtt.client as mqtt
import CHIP_IO.GPIO as GPIO
import time
import os
import paho.mqtt.publish as publish

GPIO.setup("XIO-P0",  GPIO.IN)
GPIO.input("XIO-P0")

while True:
    input_state  =  GPIO.input("XIO-P0")
    if input_state  ==  True:
 time.sleep(.5)
 publish.single("mqtt",  1,  hostname="172.20.0.1")

GPIO.cleanup()

```

首先，在程序中导入并初始化各种库。

接下来，按钮的 GPIO 引脚被初始化。按钮连接在芯片 U14L 接头上的 XIO-P0 引脚和地之间。面对芯片的顶部，USB 端口在顶部，引脚在右侧双接头上，左侧大约向下 1/3 处。

“while”循环只是停留在那里查看 XIO-P0 引脚。当它看到一个按钮被按下时，一个“1”被发布到 mqtt 代理上的“MQTT”主题。芯片是代理和 MQTT 发布客户端。回想一下，上次我们在芯片中添加了独立接入点(AP)功能，因此有了一次性的 172.20.0.1 IP 地址。芯片的接入点 SSID 是“dr-torq-1”

该循环实际上足够快来捕捉[触点反弹](https://en.wikipedia.org/wiki/Switch#Contact_bounce)，所以我在代码中加入了第二个延迟，以最小化这种影响。看看能否在其他应用中找到利用这一速度的方法。

还要记住，由于 MQTT 数据中枢(芯片)是一个独立的 AP，所以在从另一个设备执行任何操作之前，您需要连接到那个 SSID。

要编写和运行 Python 脚本，从 Linux 笔记本 SSH 到芯片。

```
drtorq-notebook%  ssh chip@172.20.0.1

```

进入芯片后，使用以下代码编辑并运行 Python 脚本。

```
chip%  sudo python button1.py

```

**sudo** 是必需的，因为普通用户没有权限直接控制 GPIO 管脚。

通过订阅 Linux 笔记本中的“mqtt”主题来检查按钮的操作。

```
drtorq-notebook%  mosquitto_sub  -h  172.20.0.1  -t  mqtt

```

每次按下微动开关，您应该会看到屏幕上弹出一个“1”。

接下来，我们将解决“订户”方面的问题。

## 点亮“臭氧管”

当您可以重新利用现有设备作为概念验证原型时，为什么还要增加新硬件呢？聪明点，通过回收项目，从你工作台上堆积如山的零件中获取最大价值。目前业界的一个热门话题是如何构建硬件，改变物理计算结果只需要一个软件模块。

当然，徽章需要贴在芯片 AP (dr-torq-1 SSID)上，得到一个 172.20.0.xxx 的地址。我将把它作为一个实际的网络练习留给读者。我们已经将 Linux 笔记本连接到 dr-torq-1 SSID。在我的例子中，Pi 从芯片 AP 获取了 172.20.0.137 IP 地址。

```
drtorq-notebook%  ssh pi@172.20.0.137

```

在 Pi 上编辑和运行“subscribe”(我称之为 mqtt-sub.py) Python 脚本与在芯片上编辑和运行“publish”脚本完全一样。

```
pi%  sudo python mqtt-sub.py

```

这个 Python 脚本读取芯片代理上的 mqtt 订阅主题(“MQTT”)，并对消息进行操作，打开一个绿色 LED。

```
import time
import paho.mqtt.client as mqtt
import RPi.GPIO as GPIO 

GPIO.setwarnings(False)
GPIO.setmode(GPIO.BCM)
GPIO.setup(27,  GPIO.OUT)

def on_connect(client,  userdata,  rc):
    print

def on_message(client,  userdata,  msg):
    if str(msg.payload)  ==  "0":
 GPIO.output(27,False)
    elif str(msg.payload)  ==  "1":
 GPIO.output(27,True)
  time.sleep(1)
 GPIO.output(27,False)
    else:
 print

client  =  mqtt.Client()
client.connect("172.20.0.1",  1883,  60)
client.subscribe("mqtt")

client.on_connect  =  on_connect
client.on_message  =  on_message

client.loop_forever()

```

首先是导入库。请注意，[芯片](https://github.com/xtacocorex/CHIP_IO)和[树莓派](https://pypi.python.org/pypi/RPi.GPIO)的 GPIO 库是不同的。不同的平台有多个库，尽管它们的功能都非常相似。选择一个，阅读文档，你应该可以让它工作。我认为不管平台如何，熟悉使用库的“过程”对于现成的黑客来说是一项非常有价值的技能。库是硬件行业在软件中整合功能的方式。

接下来，初始化 GPIO 引脚 27 以进行输出。此引脚连接到徽章臭氧管中的绿色 LED。

然后我们定义一个小函数来检查 MQTT 消息中的“0”、“1”或其他值。如果它收到一个“0 ”,它关闭 LED。“1”打开它，任何其他值都不打印，也不采取任何行动。

最后，我们连接到 172.20.0.1 上的 mqtt 代理，并无限循环，查找主题“MQTT”中的任何值。

在 Pi 上启动脚本，每次按下芯片上的微动开关时，您应该会看到绿色 LED 灯亮起。还要注意，我在代码中添加了几行代码，以便在一秒钟后自动关闭 LED。如果你按下按钮，LED 已经亮了，那就没什么用了。

## 后续步骤

对于物理计算系统来说，能够同时在许多设备之间发送和接收消息是一种超级能力。我们已经看到了如何通过 MQTT 代理发布和订阅，以实际控制物理行为。

有了这个框架，下一步可能是探索控制电机，伺服，步进器和其他驱动器。我们能做到近乎实时的控制吗？谁知道呢。这个设置是否足够快，能够使用 MQTT 消息远程控制机器人？我也不知道那个。这会有任何应用或意义吗？

而且，我们甚至还没有谈到在联网的 Linux 笔记本电脑或 Android superphone 上面向 MQTT 的仪表板，以在我们的边缘设备上显示输入、趋势等。一条消息可以点亮一个 LED，同时驱动桌面图上的一个数据点。

我们可以选择任何不同的方向。

您希望便携式无线数据中枢具备哪些功能和特性？我很想看看现成的黑客如何将这种物理计算堆栈技术应用到他们的项目中。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>