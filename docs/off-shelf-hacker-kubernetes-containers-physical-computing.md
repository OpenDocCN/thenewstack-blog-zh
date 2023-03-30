# 现成的黑客:物理计算的 Kubernetes 和容器？

> 原文：<https://thenewstack.io/off-shelf-hacker-kubernetes-containers-physical-computing/>

上周，在柏林举行的 CloudNativeCon + Kubecon 欧洲会议对我来说是一场旋风。因为这是我第一次去欧洲，我不仅沉浸在所有的文化中，而且对云、容器、Kubernetes 和所有其他相关技术的接触对我来说也是巨大的。

我参加了青少年 Lucas kld strm 的演讲，题目是“使用 kubeadm 构建的多平台 Kubernetes 集群的自动扩展”他因[将 Kubernetes 容器编排器移植到 ARM 设备](https://github.com/luxas/kubernetes-on-arm)而闻名，现在维护着 [kubeadm 项目](https://github.com/kubernetes/kubernetes/projects/7)。他是一个很好的演讲者，在深入探讨他的话题时，他让大约 150 名观众参与进来。他的演示在位于讲台上的几个 ARM 和 Intel 设备上运行:

https://www.youtube.com/watch?v = 3-vbggng 8 TC & index = 75 & list = plj 6h 78 yzym 2 paavlvbv 0 izkod 4 IVH _ iGqV

我从 kld strm 的演讲中得到的启示是，容器和 Kubernetes 肯定可以在像 Raspberry Pi 这样的纳米 Linux 设备上运行。

对于正在部署新产品、自动化流程并为物联网提供无数纳米计算设备的现成黑客来说，这可能是一件大事。

## 超越出血边缘

Linux 和微控制器是尖端的，对吗？

几年前，我把自己的未来寄托在 Linux 上，因为我知道它最终会吞噬信息技术世界。的确如此。随便看看。Linux 运行在世界各地的服务器上，管理着网络，为数百万的应用程序和公司提供了可靠的基础设施。

当然，Linux 桌面从未实现过，现在我们有了云、超复杂的网络应用和超级手机。Linux 在桌面上的相关性似乎正在消退。但是，像我这样的老家伙仍然在我们老旧的支持 Linux 桌面的笔记本上敲打科技文章。

毫无疑问，Linux 在最新的信用卡大小的微控制器设备上也有巨大的足迹。

像 Kubernetes 这样的云、容器和容器管理平台正在成为下一个大事件，特别是在物联网方面。我们还没到那一步。但该行业刚刚开始将“大规模”思维应用于边缘设备和传感器节点。积极的一面是，管理不同硬件和分割软件集合的工具正在迅速成熟。

随着服务的扩展和推广，打包新功能和软件更新以及将新节点投入生产的能力对于高效运营至关重要。这是云、容器和 Kubernetes 的工作。

Ticketmaster 的平台和技术运营高级副总裁 Justin Dean 在 2016 年 CoreOS structural Summit 上就该公司的云和 Kubernetes 战略进行了精彩的演讲。在演讲中，Dean 强调向上自动化和抽象开发和部署过程将使整个开发/运营/生产团队的生活更加轻松。把所有东西都放在容器里，用软件管理容器，比如 Kubernetes。

[https://www.youtube.com/embed/wqXVKneP0Hg?feature=oembed](https://www.youtube.com/embed/wqXVKneP0Hg?feature=oembed)

视频

## 边缘的容器

我一直在尝试为我构建的设备设计自己的云、容器和 Kubernetes 用例。

一个例子是使用容器来存放我的会议徽章。我用树莓派在小彩色液晶屏幕上播放一个. mp4 视频，用的是 [MPlayer](https://www.mplayerhq.hu/design7/dload.html) 。“臭氧管”只不过是一个三色发光二极管，被拼凑成一个重新设计的抽油烟机灯泡。Python 程序使用脉冲宽度调制(PWM)使 LED 亮度上下循环，给它带来酷炫的视觉效果。

现在想象一下，对于一屋子的与会者，收集这些徽章。微控制器徽章如今在会议上风靡一时。DEF CON 徽章一年比一年复杂。

把每个徽章的软件放在一个容器里，通过 WiFi 无线更新他们的程序，难道不是很有意义吗？也许你想让每个徽章播放不同的. mp4 视频。或者，在三色 LED 上使用不同的颜色/图案。使用容器和可能的 Kubernetes 将所有徽章捆绑在一起，这似乎会使推出更改甚至新徽章变得轻而易举。否则你怎么可能管理 3000 个微控制器供电的徽章？我将不得不探索各种可能性。

## 下一步是什么？

我刚刚开始了解如何将容器应用到我的一些项目中。与编程和推出传统的基于 Raspberry Pi 的设备的实际操作相比，容器是一个高度抽象的主题。

微控制器已经过了“你好，世界点亮 LED”的阶段。强大的基于 Linux 的主板，如 Raspberry Pi、Beagle Bone 等，提供了轻松自动化开发、运营和新产品推出的能力。

您可能会在项目中的什么地方使用容器？

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>