# 修补程序:物联网的开源软件更新程序

> 原文：<https://thenewstack.io/mender-open-source-iot-software-updater/>

对[特斯拉](https://www.usatoday.com/story/tech/2017/07/28/chinese-group-hacks-tesla-second-year-row/518430001/)和[吉普切诺基](https://www.theverge.com/2016/8/2/12353186/car-hack-jeep-cherokee-vulnerability-miller-valasek)嵌入式设备的网络攻击已经清楚地表明了与物联网相关的安全风险，不仅系统被征用，而且被“砖化”——就像恶意软件菌株 [BrickerBot](https://techcrunch.com/2017/04/25/brickerbot-is-a-vigilante-worm-that-destroys-insecure-iot-devices/) 在永久拒绝服务攻击中一样毫无用处。

更好地更新软件肯定有助于减轻这种攻击，尽管由于带宽和处理能力的限制，更新远程设备可能会很棘手。总部位于旧金山的 [Mender](https://mender.io/) 为联网的 Linux 设备提供开源的空中下载(OTA)软件更新程序，专注于安全性、健壮性和易用性。

“当我们开始时，在物联网设备中没有标准的软件更新方法。我们交谈过的人中，大约有一半人根本没有办法做更新，这很可怕；另一半人建立了自己的更新程序。这似乎是浪费，并导致设备不稳定，因为这是一件很难做好的事情，”Eystein Stenberg ， Mender 首席技术官和联合创始人说。

“所以我们决定是时候有人来建立一个每个人都可以使用的开源更新程序了。”

[修补器](https://github.com/mendersoftware)由管理服务器和客户端设备组成，两者都受 Apache 版许可。它目前是一个本地解决方案，托管版本仍在测试阶段。

这是一个基于数据块而不是基于文件的系统，通过消除不同文件版本或仅部分更新带来的风险，增强了健壮性。什么都更新或者什么都没有。如果由于电源故障或网络连接不良而导致完整映像更新失败，设备会自动回滚到之前的工作状态。

社区开发负责人 Ralph Nguyen 表示，开发者喜欢使用相同的机制来更新 Linux 内核和应用程序。

用 Golang 编写，客户端定期通过 HTTPS 轮询管理服务器以检查更新，因此不需要在客户端打开任何端口。如果有的话，客户端从管理服务器获取更新，这是一种限制攻击面的方法。只允许传输层安全性(TLS)连接；服务器拒绝不安全的连接。

开发人员可以使用[状态脚本](https://docs.mender.io/artifacts/state-scripts)进行额外的检查，以确保设备和应用程序正常工作。

这是一个双分区系统，使用一个包含 U-Boot 引导程序的引导分区和一个包含数据文件的数据分区，这些数据文件在两次更新之间是持久的。此外，还有两个根文件系统，称为主动和被动分区。更新在一个分区上加载，而在另一个分区上运行，然后切换到新的分区。如果有问题，它会切换回原来的状态。

修补程序更新客户端可以通过 CLI 或自定义集成以独立模式运行，也可以以托管模式运行，在托管模式下，它作为守护程序运行，并将定期轮询服务器、自动应用更新、重新启动、报告和提交更新。

Mender 与 [Yocto 项目](https://www.yoctoproject.org/)紧密集成，这是一个开源合作项目，为嵌入式产品创建定制的基于 Linux 的系统提供模板、工具和方法，而不管硬件架构如何。然而，它可以移植到[非 Yocto](https://mender.io/blog/porting-mender-to-a-non-yocto-build-system) 构建系统，如 Debian、Ubuntu 和 Raspbian。

Mender 支持通过网关作为代理更新传感器和其他较小的设备，网关使用 ZigBee、蓝牙低能耗和其他本地网络技术等网络协议，无需在这些设备上运行代理。

客户包括“智能着色”玻璃供应商[Kinestral](https://www.kinestral.com/)； [IOTAS](http://www.iotashome.com/) ，为租房者提供智能家居技术；以及实用技术厂商 [GridX](https://gridx.de/) 。

Mender 与第一代 OTA 软件供应商竞争，如被三星收购的 Artik 和被德尔福汽车收购的 Movimento。托管物联网后端，如 [Mode](http://www.tinkermode.com/) 和 [Kuzzle](http://kuzzle.io/) 提供一些更新功能，以及应用性能管理、日志管理、认证和其他服务，如 [Resin.io、](https://github.com/resin-io)等完整平台以及来自 IBM、SAP 和 Oracle 等主要厂商的平台。

德国英特尔公司的软件工程师 Patrick Ohly 在去年的嵌入式 Linux 大会上讨论了基于文件的[与基于块的](https://www.linux.com/news/event/open-source-summit-na/2017/4/pros-and-cons-system-update-and-integrity-protection-schemes)更新程序，他负责 Yocto 项目和面向英特尔架构的物联网参考操作系统套件。

他指出“它们都有利弊，在某些情况下，需要进一步的工作。”

像 [SWUpdate](https://sbabic.github.io/swupdate/swupdate.html) 和 [Mender](https://mender.io/) 这样的基于块的系统有固定的分区大小，他说，这意味着“你不能有一个更新流提供给不同硬盘的不同设备，因为它们必须以相同的方式分区。”他补充说，像 swupd 和 OSTree 这样基于文件的系统使得支持各种设备变得更加容易。

Stenberg 说，基于文件的更新可以更小更快，但 Mender 专注于安全性，并认为回滚的“全有或全无”方法提供了必要的健壮性。

展望未来，该公司计划扩大其 Linux 发行版的范围，首先是 Ubuntu 和 Debian，并通过代理部署支持越来越小的设备。

通过 Pixabay 的特征图像。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>