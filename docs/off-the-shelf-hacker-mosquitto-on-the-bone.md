# 现成的黑客:骨头上的蚊子

> 原文：<https://thenewstack.io/off-the-shelf-hacker-mosquitto-on-the-bone/>

MQTT 是一种在物理计算设备和机器之间分发数据的成熟方法。早在 2017 年，我们就探索过使用芯片单板计算机来运行 [Mosquitto MQTT 经纪人](/off-shelf-hacker-mosquitto-glass/)。虽然这个小工具运行良好，但由于其他项目，它被推到了桌子后面。

不幸的是，基于芯片的经纪人在大约六个月前就死了。主板不再启动，供应商也已经停业。

如何处理即将出现的几个新 MQTT 项目？零件箱中的老 BeagleBone Black 应该是一个很好的 MQTT 代理。本周的部分涵盖了在“骨头”上运行[蚊子经纪人](https://mosquitto.org/)的要点

## 为什么是骨头而不是圆周率？

比格犬骨在它第一次出现的时候就已经走在了时代的前面。它使用 eMMC 闪存来存放 Linux 操作系统，而不是通常的微型 SD 卡。芯片也有类似的排列。

我一直喜欢在微控制器板上运行 Linux 的想法，没有移动部件。我认为微型 SD 卡是一个移动部件。如果你不小心，卡会意外地从插槽中弹出，并移动到某个再也找不到的地方。我在卡片上贴了一条胶带，作为额外的保险，确保它不会脱落，尤其是在会议上做技术演讲的时候。现在许多主板都使用“非卡嗒声”插座，这可能会减少卡丢失。我在所有的 Pi 板上都用胶带。胫骨上不需要任何东西。

其他一些单板计算机使用闪存，正如我上周收到的最近的 [Rock Pi 4 评测样品](http://rockpi.org/)所见证的那样。Linux 可以从一个类似于 BeagleBone 的微型 SD 卡上刷新到可移动的 eMMC 存储器上。一旦我找到一个带 USB-C 连接器的 5 伏 4 安培的电源模块，我会给它一个测试。

顺便说一下，Raspberry Pi 计算模块使用 Linux 的 eMMC 内存。据我所知，Raspberry Pi 基金会并没有计划在他们的传统产品线中摆脱 micro-SD 卡存储设置。

## 在骨骼上更新 Linux

将 Linux 放在旧的 BeagleBone Black 上非常简单，在 [BeagleBone 页面](https://beagleboard.org/bone)上有很好的介绍。

去 BeagleBone 网站下载 Debian Linux 的最新版本。如果你愿意，你可以运行其他的，过程是一样的。我选择的是 [Debian 9.5 2018-10-07 4GB eMMC 物联网闪光器](https://debian.beagleboard.org/images/BBB-blank-debian-9.5-iot-armhf-2018-10-07-4gb.img.xz)(下载)版本。这是为无头操作设置的，没有任何正常的桌面功能。它很紧凑，您可以在命令行上使用 **apt-get** 来安装 Mosquitto 代理和客户端。安装后，我将通过 SSH 在网络上维护设备。

一旦。xz 文件下载到你的 Linux 笔记本上，用 [unxz 程序](https://linux.die.net/man/1/unxz)解压。这将生成。需要把 img 文件放到 micro-SD 卡上。是的，我们仍然需要一个微型 SD 卡来更新骨骼，但安装后不会使用它。我使用了一个通用的 8GB 卡插入 USB SD 卡适配器。

接下来，我们安装 [balena-etcher](https://www.balena.io/etcher/) 程序来复制。img 文件到卡上。将图像写入卡后，可以将其移除并插入未通电的 BeagleBone Black 的 micro-SD 插槽中。

我暂时将一个显示器连接到 BeagleBone 上的 micro-HDMI 端口，以及一个 Logitech 无线键盘/鼠标垫，然后握住用户按钮(在电路板顶部的 SD 卡插槽上方)，使用一个 5 伏、2.5 安培的带管状连接器的壁式电源适配器供电。

当四个蓝色发光二极管亮起时，你可以松开按钮，然后微型 SD 卡就会开始工作。Linux 将自动刷新到骨骼，一旦操作完成，它将关闭电源。取出 SD 卡。不按住任何按钮重启骨骼。您应该会在监视器上看到一个登录提示。将正常工作的网线插入骨骼的以太网端口。使用“debian”和“temppwd”登录。您应该更改默认密码。

## 将 Mosquitto 添加到代理和客户端

Mosquitto 不包含在映像中，所以它是使用 apt-get 安装的。

首先，添加 Debian 测试库。

```
beaglebone%  cd  /etc/apt
beaglebone%  sudo vi sources.list

```

在文件底部添加“德布 http://httpredir.debian.org/debian 伸展主要贡献非自由”。写入并关闭文件。

```
beaglebone%  sudo apt-get update
beaglebone%  sudo apt-get install mosquitto
beaglebone%  sudo apt-get install mosquitto-clients

```

注销，然后重新登录。

使用 ifconfig 查找您的网络地址。

比格犬骨显示 192.168.1.101。Mosquitto 代理被配置为在启动时自动启动，所以我们现在可以用它来传递消息。

转到您网络上的另一台 Linux 机器，订阅 Bone 的 MQTT 代理。我们将观看“消息”主题。

```
linux-notebook%  mosquitto_sub  -h  192.168.1.101  -t  messages

```

现在返回到 BeagleBone monitor 并向代理发布一条消息。

```
beaglebone%  mosquitto_pub  -h  localhost  -t  messages  -m  otsh

```

Linux 笔记本电脑的屏幕上应该会立即弹出“otsh”文本。

[https://www.youtube.com/embed/BlnBkKR06QI?feature=oembed](https://www.youtube.com/embed/BlnBkKR06QI?feature=oembed)

视频

此时，只需使用 shutdown 关闭 BeagleBone 即可。

```
beaglebone%  sudo shutdown  -h  now

```

从 USB 端口拔下连接显示器和无线键盘发射器的 HDMI 电缆。重新启动骨骼，开始向您的心脏内容发送 MQTT 消息。

## 下一步是什么？

我计划将 BeagleBone 放在某种外壳中，这样我就可以用它来整合来自我的洒水控制器和室外入侵检测网格的 MQTT 消息。如果能开始记录我的 ESP8266 灯具的内部照明使用情况，那当然更好。

*赶【Torq 博士的 [现成黑客专栏](https://thenewstack.io/tag/off-the-shelf-hacker/)，每周六，只上新栈！在[doc@drtorq.com](mailto:doc@drtorq.com)或 407-718-3274 联系他咨询、演讲、委托项目。*

Pixabay 的 skeeze 的专题图片。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>