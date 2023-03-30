# 现成的黑客:在可穿戴设备上运行 MQTT

> 原文：<https://thenewstack.io/off-shelf-hacker-run-mqtt-wearable/>

上周，我们[看着](https://thenewstack.io/off-shelf-hacker-give-screen-gauges-new-face/)读取超声波测距仪，并在一个漂亮的屏幕上显示距离。我演示了如何在可穿戴设备上使用计量器，比如一个[蒸汽朋克会议徽章。](https://thenewstack.io/hacking-hardware-the-never-ending-saga-of-steampunk-name-badge-development/)

由于徽章是“连接的”，也就是说，通过 WiFi 连接到局域网，我们也可以将它用作数据收集设备。实用？也许吧。这个概念可以转移到一个不那么引人注目的小工具上，比如一个你可以夹在腰带上的小盒子，[放在桌子上](https://thenewstack.io/off-shelf-hacker-mosquitto-glass/)或者集成到一个产品中。

将数据从一个设备可靠地传输到另一个设备是一个叫做 [MQTT](http://mqtt.org/) 的甜蜜数据传输协议的工作。这是一个[订阅发布服务器模型](https://thenewstack.io/off-shelf-hacker-putting-mqtt-broker-work-chip-platform/)，可以在徽章或任何数量的其他机器上运行，包括笔记本和服务器。在 MQTT 语言中，服务器通常被称为代理。甚至有一个客户在 ESP8266 上工作。服务器本身很轻，所以将其安装在会议徽章上并不是很大的负担，即使配备了 Raspberry Pi model 2 板也是如此。

今天，我们将安装 MQTT，从测距仪捕获数据，然后将其发布到服务器，就在徽章上。我使用外部 HDMI 显示器和键盘进行测试，尽管一旦一切正常，它们当然是可选的。我们还将看到数据出现在联网的 Linux 笔记本上，使用现成的 MQTT 客户机。数据可以很容易地从按钮、光电池、温度传感器或其他传感装置中获取。您需要安装 [python-rpi.gpio](https://pypi.python.org/pypi/RPi.GPIO) 软件来使用这些带有 pi 的设备。

在接下来的故事中，我们将看看如何将徽章上的 MQTT 服务器传感器概念与我们上周构建的光滑的屏幕仪表相结合，在笔记本上远程运行。MQTT 比自主开发的协议要好得多。

## 在徽章上安装 MQTT

用 apt-get 或像 synaptic 这样的包管理器安装 MQTT 服务器和客户机软件。这里有一个关于 [Raspberry Pi MQTT 安装](http://jakemakes.eu/installing-mqtt-brokermosquitto-on-raspberry-pi/)的快速概要。

测试非常简单。

首先，打开一个终端(在 Pi 上)并执行 mosquitto 订阅命令。然后，终端将坐在那里等待数据进入“rangeval”主题。

```
mosquitto_sub  -t  rangeval

```

在另一个终端，发布一些“测试”数据到 rangeval 主题。

```
mosquitto_pub  -t  rangeval  -m  "test"

```

每次运行发布命令时，您应该会看到“测试”一词出现在订阅终端窗口中。

Python 通常包含在 Linux 版本中，在 Raspberry Pi 上运行。如果没有，很容易补充。

```
sudo apt-get install python

```

你可能还需要安装 pip，Python 的内置应用安装工具。

```
sudo apt-get install python-pip

```

接下来打开浏览器，去 GitHub 下载 [Paho Python-MQTT 库 zip 文件](https://github.com/eclipse/paho.mqtt.python#installation)到树莓 Pi 2，在徽章上。将文件和 cd 解压缩到结果目录中。

查找 setup.py 文件，并使用 Python
运行它

安装好所有东西后，是时候使用 Python 脚本和 MQTT 库发布测距仪数据了。

## 通过 MQTT 发送真实数据

下面是一个简单的 Python 脚本，用于读取串行数据并将其发布到徽章的 MQTT 服务器。回想一下，徽章上有一个 Arduino，它管理测距仪并通过串行端口将数据发送到 Raspberry Pi。串行端口有时不可靠，所以一定要先运行 stty 命令。

```
stty  -raw  -crnl  -F  /dev/ttyAMA0  115200

```

将以下代码复制到文本文件中，然后用 Python 执行。

```
import paho.mqtt.publish as publish
import serial

ser  =  serial.Serial('/dev/ttyAMA0',  115200)  
while True:  
  serial_line  =  ser.readline()
  print  (serial_line)
  publish.single("rangeval",  serial_line,  hostname="localhost")

```

如果订阅终端仍在运行，您应该会看到测距仪数据立即在窗口中滚动。否则，请再次运行订阅命令。

```
mosquitto_sub  -t  rangeval

```

## Linux 笔记本上的 MQTT

在 Linux 笔记本上安装 MQTT 也没什么大不了的。使用 **apt-get** 或者你喜欢的包管理器。确保包含 MQTT 客户机应用程序。

确保徽章正确连接到本地网络，并且 Python 脚本仍在向服务器传输数据。

您需要知道徽章上 MQTT 服务器的 IP 地址，以便在笔记本上远程使用 MQTT 客户机。

在终端中，在 Pi 上执行 [ifconfig 命令](https://en.wikipedia.org/wiki/Ifconfig)以获取 IP 地址。寻找与您的 WiFi 卡相关的“inet”线路，通常标记为 wlan0。

确保笔记本在同一个网络上，并在终端窗口中执行 MQTT 订阅命令。

```
mosquitto_sub  -h  192.168.1.120  -t  rangeval

```

-h 选项只是 Pi 的 IP 地址，而-t 代表 rangeval 的 MQTT 主题。你应该能在终端上看到测距仪的数据流。回头看看 Pi 上的订阅窗口，您也会看到完全相同的数据。

这就是 MQTT 一对多和多对一发布订阅模型的美妙之处。如果愿意，您可以让数十、数百或数千个 MQTT 客户机使用这些数据。同样，你也可以发布大量的数据，反其道而行之，同样容易。

## 下一步是什么

一旦我在笔记本上使用 MQTT 解决了处理蒸汽朋克屏幕上的仪表程序的错误，我将写一个关于这个主题的小故事。请记住，我们不必局限于在远程仪表上显示测距仪数据。我们还可以使用 Python-MQTT 客户端脚本来提供图表或进行分析或任何其他工作。

我对物理计算的挑战是识别并敲定这一令人敬畏的技术的实际用途。工具在那里。以富有成效的方式利用这些能力是现成的黑客们所做的事情。

通过 Pixabay 的特征图像。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>