# 现成的黑客:使用 MQTT 的轻量级设备间消息传递

> 原文：<https://thenewstack.io/off-shelf-hacker-lightweight-inter-device-messaging-mqtt/>

[![](img/35b093e3df4fbf0740b121a7fa4cd9ba.png)](http://mqtt.org/) 在过去[现成的黑客](/tag/off-the-shelf-hacker/)项目中，像 [PIR 码传感器](https://thenewstack.io/off-shelf-hacker-deploying-testing-esp8266-pir-yard-sensor/)，数据只是通过网络用我的 Linux 笔记本与 ESP8266 交换，使用文本。该方法创建了一个服务器(笔记本电脑)和一个客户端(ESP8266 设备)。

虽然这对于原型制作和了解物联网基础知识很有用，但它并不适合部署一系列传感器。如果你想要一个院子传感器在房子的东南角，另一个指向后院的中间呢？如果我走极端，想要设置 24 个传感器来保护我简陋的四分之一英亩的财产免受外星人或其他不良分子的侵害，那该怎么办？显然，要将多个传感器集成到一个有用的监控系统中，需要建立一个标准化的客户端-服务器设置。

今天，我们将看看用于设备间通信的 [MQTT 消息协议](http://mqtt.org/)。

## MQTT 是什么？

MQTT 是一个成熟的客户机-服务器消息传递系统，它使用轻量级的发布者/订阅者模型，运行在 TCP/IP 网络上。它是为远程位置的设备之间的连接而设计的，具有有限的带宽和可能的高延迟。该标准的早期形式出现在 20 世纪 90 年代末。

在正常的操作过程中，使用 MQTT 的设备或客户机将它们的数据“发布”到一个中央服务器上的“主题”上，这个服务器称为代理。其他设备或客户端在代理上“订阅”该“主题”,并可以获取数据。该系统速度很快，允许一对多的关系。

例如，如果您向“mqtt”主题发布一条“hello，world”消息，并且有五个客户端订阅了“mqtt”，连接到同一个代理，那么一旦发送了数据，所有五个客户端都会收到这条消息。

MQTT 的另一个可取之处是客户机可以从代理“拉”出数据。每当有内容发布到某个主题，订阅的客户端就会收到消息。代理还可以有效地将数据“推”给客户机。如果另一个客户机将数据发布到代理上的一个主题，它会自动“推”到连接到该代理的任何类似主题订阅的客户机。

有一个很棒的 MQTT 客户机-服务器应用程序，[Eclipse mosquito](https://mosquitto.org/)，它运行在 Linux 机器上。它易于安装，使在设备之间分发数据变得轻而易举。适合 Arduino(以及 ESP8266)和 Python 的库也可以从 Web 上的各种来源获得。您可能希望使用片上 Python 或 Raspberry Pi 构建一个监控应用程序，从 MQTT 代理获取数据。

您可以在 Linux 机器上运行 MQTT 服务器和客户机，然后使用库在小型设备上构建客户机，比如 ESP8266。数据通过通用协议在所有设备之间无缝流动。

## 在芯片上设置一个 Mosquitto MQTT 服务器

要开始使用 MQTT，只需使用 Mosquitto 在芯片计算机上建立一个快速系统。

我通过网络使用 [SSH](https://www.openssh.com/) 完成很多芯片方面的工作。没有显示器和键盘/鼠标垫，通过 SSH 远程访问的全功能计算机通常被称为“无头计算机”虽然一开始看起来很神奇，但当你习惯了这种工作方式后，就没什么大不了的了。我的无线网络 [Raspberry Pi 蒸汽朋克徽章](https://thenewstack.io/hacking-hardware-the-never-ending-saga-of-steampunk-name-badge-development/)是无头的，我通常从联网的 Linux 笔记本上远程更改设置、调整软件和调整脚本。

启动芯片计算机，并确保它连接到您的本地网络。我只是把芯片板放在桌子上，用一个通过微型 USB 电缆连接的三星手机壁式电源供电。我以前连接到我的局域网，所以能够 SSH 到设备没有麻烦。芯片网页有[小教程](https://bbs.nextthing.co/t/setting-up-chip-as-a-headless-server-with-minimal-tools/1505)如果你需要帮助。

从 Linux 笔记本电脑上，使用 SSH 登录芯片。为您的芯片插入合适的网络地址。

```
rob-notebook%  ssh  -X  chip@192.168.1.113

```

我从关于 [Hackaday](http://hackaday.com/) 的[“Minimal MQTT:Building A Broker”](http://hackaday.com/2016/05/09/minimal-mqtt-building-a-broker/)文章中获得了在芯片计算机上构建 Mosquitto 的灵感。它只有七个命令行，所以您可以从网页复制并粘贴到您的 SSH 连接的芯片终端。本质上，这是一个简单的安装蚊子的练习。

安装后，Mosquitto 会自动启动。安装脚本将其添加到系统中，因此 Mosquitto 服务器也在重启芯片后重启。

要测试设置，请在芯片终端输入 Mosquitto subscribe 命令。

```
chip-term1%  mosquitto_sub  -h  localhost  -t  “mqtt”

```

然后终端会耐心地坐在那里，直到有消息发布到“mqtt”主题。要做到这一点，用 SSH 打开芯片的第二个终端，然后键入以下内容。

```
chip-term2%  mosquitto_pub  -h  localhost  -t  “mqtt”  -m  “hello,  world”

```

几乎同时，“你好，世界”会在第一个终端窗口弹出。你可以用芯片的 IP 地址替换本地主机，它仍然可以工作。

## 在 ESP8266 上设置 MQTT 客户端

正如我在过去的文章中指出的，ESP8266 很容易使用 Arduino IDE 进行编程，所以这就是我使用的。Web 上有许多不同复杂程度的 Arduino MQTT 库。Adafruit 有一个关于设置和使用 MQTT 服务器、客户机、硬件和服务的[综合指导系列](https://learn.adafruit.com/mqtt-adafruit-io-and-you/overview)。

我在 GitHub 上找到了一个相对简单的客户端库，可以与 ESP8266 一起工作。

第一步是将 zip 文件下载到您的 Linux 笔记本上。通过点击 Sketch→Include Library→Add ZIP Library 菜单并选择您下载的库文件，将其拖入 Arduino IDE。我将在我的 **/home/rob/Downloads** 目录中找到的 **pubsubclient-master.zip** 重命名为 **pubsubclient.zip，**并将其拉入 Arduino 库管理器。

一旦库被安装在 Arduino IDE 中，进入文件→示例→ PubSubClient 找到示例程序。打开 **mqtt_esp8266** ，我所要做的就是用我的本地设置修改以下三行代码，然后上传到 ESP8266 PIR 码传感器进行测试。

```
const char*  ssid  =  "my-network-name";
const char*  password  =  "my-ap-password";
const char*  mqtt_server  =  "my-CHIP-computer-IP-address";

```

继续往下看文件，您会注意到 **reconnect()** 函数中的 **client_publish** 和 **client_subscribe** 行。使用 ESP8266 上的库真的没什么用。这段代码只是每 2 秒钟向“outTopic”主题发送一条新的“hello world”消息。我冒昧地将测试中的“outTopic”改为“mqtt”。

一旦 ESP8266 连接到网络并向芯片代理发送消息，请返回终端并订阅主题。192.168.1.113 是芯片的 IP 地址。

```
chip-term1%  mosquitto_sub  -h  192.168.1.113  -t  “mqtt”

```

终端上每两秒钟就会弹出一个连续的“hello world”消息。

我还使用 [Synaptics 应用管理器](http://www.nongnu.org/synaptic/)在 Linux 笔记本上安装了 Mosquitto。安装后，通过 Linux 笔记本上的终端窗口(指向 mqtt 代理芯片)订阅“MQTT”主题，每 2 秒钟就会产生相同的消息。

```
rob-notebook%  mosquitto_sub  -h  192.168.1.113  -t  “mqtt”.

```

当 ESP8266 向经纪人发布“hello world”消息时，我坐在那里，看着芯片和 Linux 笔记本订阅更新。

整个事情进行得非常顺利。它运行了一整天，没有一个问题。

## 下一步是什么？

MQTT 是设备间双向消息传递的一个非常可行的解决方案。它轻量级且快速，同时允许机器之间的一对多关系。

看看 Adafruit 教程，然后建立自己的系统。还有更多特性和功能，比如设备离线后的消息传递，您可能想了解并使用。我肯定会在未来的项目中使用 MQTT，尤其是在 ESP8266、Raspberry Pi 和芯片计算机上。它应该可以很好地与我的联网可穿戴设备配合使用。

通过 Pixabay 的特征图像。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>