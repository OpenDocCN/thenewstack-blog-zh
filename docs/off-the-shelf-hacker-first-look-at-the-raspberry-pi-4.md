# 现成黑客:先看树莓 Pi 4

> 原文：<https://thenewstack.io/off-the-shelf-hacker-first-look-at-the-raspberry-pi-4/>

一个闪亮的新[树莓 Pi 4](https://www.raspberrypi.org/products/raspberry-pi-4-model-b/) 板上周抵达 Torq 博士总部，还有一个[树莓 Pi Zero W](https://www.raspberrypi.org/products/raspberry-pi-zero-w/) ，一些霍尔效应传感器和一个 3.0 安培的壁式电源插座。

Pi 4 有点难得到，我很高兴终于有一个放在我的桌子上。我很想看看这个东西在几个项目中是如何工作的。网络上的报道和规格表明，Pi 4 在性能上比旧型号有了显著的飞跃。通过 Sparkfun 订购 4GB 内存版本花了我 59 美元。3.0 安培的电源又是 8 美元。

本周我将分享我对使用 Pi 4 完成一些日常计算任务的初步观察。比老款快吗？它能作为桌面使用吗？它会在未来现成的黑客项目中发挥作用吗？

我很高兴地告诉大家，它比以前的 Pi 板快了很多。是的，它可以作为桌面使用。而且，我认为它将在即将到来的项目构建中发挥巨大作用。能够进行常规的桌面工作也可能加快物理计算开发工作流程，因为对硬件和软件的破解都可以在一台机器上进行。开发机器成为工作原型和演示单元。太棒了。

更具体的细节可能有助于您决定如何在自己的项目中利用最新的 Raspberry Pi 单板计算机(SBC)。让我们来看看。

### 绝对是一台通用计算机

要做的第一件事是在一个新的 SanDisk Extreme 64GB 微型 SD 卡上安装[最新的桌面，安装推荐的软件版本 Raspbian Linux(Buster:07-10-2019)](https://www.raspberrypi.org/downloads/raspbian/)，使用的是破旧的华硕 Linux 笔记本。的。img 文件大小大约为 3.6 GB。即使卡上“只有”64GB 的空间，对于我们在可预见的未来将要开展的任何物理计算项目来说，这也可能是足够多的文件系统空间。亚马逊上大约 15 美元，我不认为需要更大、更贵的 SD 卡。能够在 Pi 4 上运行双显示器需要 Raspbian Linux 的 Buster 版本。

下载的文件在 Linux 笔记本终端窗口中解压。

`linux-notebook% unzip 2019-07-10-raspbian-buster.zip`

产生的。然后使用 dd 命令将 img 文件刻录到 SD 卡上。

`linux-notebook% sudo dd bs=4M if=2019-07-10-raspbian-buster.img of=/dev/mmcblk0 conv=fsync`

之后，我将 SD 卡放在 Pi 4 卡槽中，连接了几个 HDMI 显示器，并将罗技无线键盘/鼠标垫插入其中一个 USB-2.0 端口。最后，我使用 Raspberry Pi Foundation 批准的 3.0 安培壁式电源适配器将 USB-C 连接器连接到电路板上。

Pi 4 马上启动，我按照正常程序设置了 wifi 和默认用户密码。

我喜欢使用新立得软件包管理器，所以这是第一个添加到系统中的新软件。在 Synaptic 下，我加载了 guvcview、luvcview、webcamoid 和标准的 LibreOffice 生产力套件。

## Pi 4 的应用印象

webcam viewer 程序是查看 JeVois 智能机器视觉传感器的视频所需的程序，我已经使用了很长时间。遗憾的是， [guvcview](http://guvcview.sourceforge.net/) 和 [webcamoid](https://webcamoid.github.io/) 不能开箱即用，需要几个命令行选项或稍加调整才可行。在这点上和 Pi 3 没有太大区别。和往常一样，luvcview 使用简单的高度和宽度命令行选项。Luvcview 作为一个实时网络摄像头查看器从未让我失望过，尤其是在会议技术会谈期间，所以我可能会坚持将其作为我的默认设置。

[pi4 上的 LibreOffice](https://www.libreoffice.org/) 终于是一个真正的使用乐趣。从按下回车键开始，作者花了大约 10 秒钟准备开始撰写有力、发人深省的现成黑客专栏。LO Impress 只用了大约五秒钟就进入了包含所有菜单和初始幻灯片模板的主演示窗口。

想象一下我在加载我的 2018 [OSCON 机器人头骨演示](https://conferences.oreilly.com/oscon/oscon-or-2018/public/schedule/detail/67506)并开始幻灯片放映时的惊讶，看到小型 10.1 英寸彩色液晶显示器(HDMI-1)显示幻灯片演示者控制台，而更大的 LG 19 英寸显示器(HDMI-2)显示实际的幻灯片。上下移动幻灯片的速度快如闪电，而幻灯片的视觉质量非常好。这与过去的日子相去甚远，当时最新最棒的 Raspberry Pi 3 model B。使用 Pi 3 作为演示机器需要使用缩小图形。png 格式，并且仍然需要等待新幻灯片的加载。Pi 4 的性能非常好，即使 Chrome 浏览器在后台运行。

说到 Chrome 浏览器，这也是一次非常愉快的用户体验。如果没有缓冲，Pi 3 几乎无法加载 [Nelson Racing Engines](https://www.youtube.com/watch?v=VZydsZYppRQ) 视频和播放音频，Pi 4 肯定不会这样。在我的古董 19 英寸 LG 电视/显示器上使用 1920×1080 的分辨率，Pi 4 可以轻松播放 1080p 视频，没有任何缓冲、丢失或视频与人类语音不同步的问题。在这台机器上观看全屏电影是一件很容易的事情。我没有 4K 显示器，所以只能播放 1080p 和 720p 的视频。它非常清澈，没有像素化。音频也可以通过模拟或 HDMI 扬声器进行选择。我没有通过蓝牙测试音频，尽管 Pi 3 与我的亚马逊 Dot 兼容。

默认的桌面加载在主菜单上有一个最小的应用程序集。您将希望根据您正在构建的项目类型来挑选您的特定程序集。我还需要下载 Arduino 交互开发环境(IDE)和处理语言组。

本质上，Pi 4 是一台成熟的 nano-Linux 机器，可以处理大多数常规的桌面计算任务。我认为大多数现成的黑客都会对 Raspberry Pi 4 感到满意，特别是如果你有 4GB 的型号和一个坚固的名牌高速微型 SD 卡。

[https://www.youtube.com/embed/1S15jaBGWuY?feature=oembed](https://www.youtube.com/embed/1S15jaBGWuY?feature=oembed)

视频

## 下一步是什么

请务必与 Pi 4 一起订购 3.0 安培或以上的电源。虽然我有那个大喇叭 15，000 mAh 12 伏锂离子电池，但我可能不得不重新考虑我在便携式情况下为 Pi 4 供电的策略。我可能会订购一个 12 伏到 5 伏的转换器，能够可靠地提供 3.0 安培以上的电流。Banggood 和 Amazon 有一些不同的产品。

使用两个显示器，您需要使用微型 HDMI 电缆连接到 Pi 4。我在亚马逊上花了大约 9 美元买了一个两包微型标准 HDMI 适配器电缆，连接到我手头的普通 HDMI 电缆上效果很好。

我马上要解决的另一个问题是冷却新的 Pi 4。我的主板没有任何过热问题，尽管只是运行 Chrome 浏览器和视频以及 LibreOffice 并不那么费力。如果电路板被封闭起来，或者我开始做人工智能/神经网络类型的工作，冷却肯定会被考虑。

这就是了。Pi 4 已经推出，将为物理计算带来新的机遇。当我将该平台集成到新的现成的黑客项目中时，请期待进一步的报道。

*赶【Torq 博士的 [现成黑客专栏](https://thenewstack.io/tag/off-the-shelf-hacker/)，每周六，只上新栈！在[doc@drtorq.com](mailto:doc@drtorq.com)或 407-718-3274 联系他咨询、演讲、委托项目。*

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>