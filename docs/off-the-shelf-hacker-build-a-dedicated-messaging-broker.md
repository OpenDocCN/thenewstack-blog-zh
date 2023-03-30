# 现成的黑客:构建专用的消息传递代理

> 原文：<https://thenewstack.io/off-the-shelf-hacker-build-a-dedicated-messaging-broker/>

[洒水控制器](/off-the-shelf-hacker-adding-mqtt-and-cron-to-the-lawn-sprinkler-project/)和[庭院灯项目](/off-the-shelf-hacker-build-a-sensor-system-to-watch-the-backyard/)都使用 [MQTT](https://thenewstack.io/mqtt-protocol-iot/) 消息进行数据通信。到目前为止，我的 Linux 笔记本在最初的开发工作中充当代理。我也用我的笔记本进行日常咨询工作，所以随着项目的进展，转移到经纪人的专用机器上是有意义的。

最终，我将在我的房子周围安装一系列庭院传感器，在车库里安装自动喷水灭火控制器，静静地等待命令。MQTT 非常容易使用，我可以肯定地看到，在许多尚待想象的未来项目中，它可以用于设备之间的本地网络通信。

今天，我们将看看如何在 Raspberry Pi 上设置一个非常基本的 MQTT 代理。Pi 是可靠的、相当便宜的，并且通过各种编程语言和应用程序具有内置的分析和接口能力。在以后的文章中，我们将研究添加安全特性、通过脚本和图形用户界面应用程序记录数据。

## MQTT 101

MQTT 是一种机器对机器协议，它简化了计算设备之间的通信。它使用客户机-服务器模型，可以在 Linux、Windows 和其他操作系统上使用。在 Ubuntu 和 Raspbian Linux 上，我很幸运地使用了客户端和代理的 Mosquitto 版本。你也可以使用库通过 Arduino 固件和 Python 或者处理程序传递消息。您甚至可以直接从命令行收发消息，这对于原型设计非常有用。

所有这一切都是通过 MQTT 代理实现的。代理协调消息，是一个软件程序。客户端订阅代理上的主题，当消息发布时，它会出现在客户端。同样，如果客户机向代理上的某个主题发布消息，订阅该主题的所有客户机都会看到该消息。您可以有许多客户端和许多主题都通过代理来回传递消息。你甚至可以让经纪人和客户在同一台机器上交谈。

你不会相信把蚊子放在树莓酱上有多容易。

## 莫斯基托码头

我从在 Raspberry Pi model B+上安装一个相对较新的 Raspbian Linux 开始。MQTT 是非常轻量级的，您不需要很大的马力来运行代理。我还通过 HDMI 电缆和无线罗技键盘/鼠标垫连接了一台显示器。我的路由器通过一根 Cat 5 电缆连接到本地网络。您可以通过 WiFi 轻松运行代理，比如在 Raspberry Pi 3 的情况下。标准的 2.0 安培手机充电器和电缆用于供电。有一天，我可能会转换到一个小的 5 伏专用电源。当一切稳定后，我将在 Pi 上运行代理，不使用监视器或键盘。

将 Linux 升级到最新版本总是一个好主意。从命令行输入以下内容，并根据需要输入您的密码。

```
pi%  sudo apt-get upgrade

```

接下来，使用下面的代码安装 Mosquitto MQTT 代理包。

```
pi%  sudo apt-get install mosquitto

```

该命令安装 Mosquitto 代理。它还将设置代理在 Raspberry Pi 重启时自动启动。

同时，你也可以安装 mosquitto 客户端。这样，您可以直接从命令行订阅和发布消息。便于测试。

```
pi%  sudo apt-get install mosquitto-clients

```

为了发送/接收消息，您需要知道代理的 IP 地址。在终端中使用以下命令找到它。

我用的是有线以太网接口，不是无线的，所以地址出现在 eth0 设备名称下。

现在我们可以测试设置。

首先，在终端中启动 mosquitto 客户端来查看消息。我随机选择了“mqtt”这个话题。

```
pi%  mosquitto_sub  -h  192.168.1.118  -t  mqtt

```

在一个单独的终端窗口中，我发出了一个 mosquitto 命令，向“mqtt”主题发布一条消息。

```
pi%  mosquitto_pub  -h  192.168.1.118  -t  mqtt  -m  hello

```

我的经纪人的 IP 是 192.168.1.118。您需要为您的安装使用您自己的特定 IP。单词“hello”应该立即出现在您的 **mosquitto_sub** 终端屏幕上。

这就是让 Raspberry Pi 准备好与联网的 MQTT 客户机交换消息的全部工作。

## 更进一步

Pi 上的一个专门的 MQTT 代理使我的基于 WiFi 的传感器项目更接近实际使用这些东西来收集数据、监视入侵者以及打开灯和洒水器。

在过去的几周里，我已经介绍了码传感器的 MQTT 程序。显然，NodeMCU 板的固件需要反映基于 Raspberry Pi 的 MQTT 代理的新 IP 地址。

此外，你可以看看用[处理编程语言](https://processing.org/)编写的[简单用户界面程序](https://thenewstack.io/off-the-shelf-hacker-super-simple-app-for-the-yard-sensor/)。该 IP 地址也需要指向新服务器。

所有这些中真正的精华是 MQTT 抽象出了通信过程的细节。在你的网络上放一个经纪人，然后订阅发布消息做事。如果传感器检测到移动，只需发布数据，其他客户端就会看到。客户端可以连接一个灯、一个蜂鸣器或一个文本文件来记录活动。客户端也可以是屏幕上的用户界面，按下屏幕上的按钮，显示状态或发布开灯命令。或者……它可能是一个小盒子上的硬件按钮。

有了 MQTT 和一个 Raspberry Pi，只需一点点努力就可以做很多远程控制的事情。

图片由来自 Pixabay 的 Antonio Doumas 提供。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>