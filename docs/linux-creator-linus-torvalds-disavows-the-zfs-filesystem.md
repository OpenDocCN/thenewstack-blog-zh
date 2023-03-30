# Linux 创建者 Linus Torvalds 否认 ZFS 文件系统

> 原文：<https://thenewstack.io/linux-creator-linus-torvalds-disavows-the-zfs-filesystem/>

Linux 的创造者和主要开发者 Linus Torvalds 已经站出来反对 ZFS 的文件系统。这个时机不容忽视，因为就在最近 [ZFS 在一个主要的发行版中发现了它的第一个正式实现](/how-to-create-and-destroy-zfs-snapshots-on-ubuntu-19-10/)。所说的版本是 [Ubuntu 19.10](/ubuntu-19-10-promises-an-improved-experience-for-ai-ml-developers/) ，其中 ZFS 文件系统被吹捧为 Canonical 对 Linux 的最新迭代的主要特性之一。

在[论坛的一篇帖子](https://www.realworldtech.com/forum/?threadid=189711&curpostid=189841)中，托沃兹写道，“如果有人添加了像 ZFS 这样的内核模块，他们只能靠自己了。我维护不了，也不能被别人的内核改动所束缚。”

如果只考虑托瓦尔兹的职位，很容易得出结论，他与 ZFS 的问题源于[潜在的许可问题](/canonical-encounters-messy-legal-questions-bringing-zfs-ubuntu/)。他写道，“除非我收到甲骨文公司的正式信函，由他们的主要法律顾问或者最好是拉里·埃里森本人签字，表示可以这样做，并将最终结果视为 GPL，否则我无法合并 ZFS 的任何努力。”。

许可的问题更加深入。考虑 Linux 端口上的 ZFS 依赖于两个不推荐使用的内核函数， **__kernel_fpu_begin()** 和 **__kernel_fpu_end()** 。替换了 **__kernel_fpu_begin()** 和 **__kernel_fpu_end()** 的函数被故意发布为 GPL 专用。

因此，如果 Oracle 还没有签署 ZFS 被 GPL 化，并且 ZFS 依赖的两个被否决的函数已经被纯 GPL 函数所取代，那就有问题了(即使这只是暂时的意识形态问题)。

但是这不全是关于 GPL 的。引发这个问题的原因是有人抱怨 Linux 内核最近破坏了树外 ZFS 模块。对此，托沃兹说，“请注意，‘我们不破坏用户’实际上是关于用户空间的应用程序，以及我维护的内核。”接着，托沃兹又一次把话题拉回到许可问题上，他说，“但是考虑到甲骨文好打官司的本性，以及关于许可的问题，我不可能觉得这样做是安全的。”

ZFS 还有其他问题。最大的是它打破了 [OSI 七层模型](https://www.networkworld.com/article/3239677/the-osi-model-explained-how-to-understand-and-remember-the-7-layer-network-model.html)。具体来说，ZFS 通过使用自己的错误纠正来规避开放系统互连(OSI)模型的较低层的信任。记住，OSI 7 层模型的目标是不同通信系统与标准[通信协议](https://en.wikipedia.org/wiki/Communication_protocols)的互操作性。所以你有一个完整的文件系统，它避开了 Linux 所依赖的模型。

让事情变得复杂的是，ZFS 提供了在少数生产就绪的 Linux 文件系统中发现的特性。唯一接近的文件系统是 Btrfs，它经常被认为对于生产系统不够稳定。

最后，托沃兹说，“不要用 ZFS。就这么简单。我觉得，它一直是一个流行词，而不是其他任何东西，许可问题只是让它对我来说不可行。”他说，“我所看到的基准并没有让 ZFS 看起来那么伟大。据我所知，它背后也不再有真正的维护，所以从长期稳定性的角度来看，为什么你会想要使用它呢？”

至于 Canonical 对这一发展的看法？“鉴于最近 ZFS 的讨论，我们的客户和用户告诉我们，他们希望在 Ubuntu 中安装 ZFS，因为它有许多可取的功能，可以防止数据损坏，支持高存储容量，提供高效的数据压缩，快照和写入时复制克隆，等等，”Canonical 的 Canonical 工程总监马丁·温普里斯(Martin Wimpress)通过电子邮件写道。“我们将继续与 OpenZFS 项目中的朋友合作，改进 Ubuntu 上的 ZFS 故事。”

人们只能想知道 ZFS 文件系统中存储了什么。Oracle 会重新许可代码，使其变得对主线内核“友好”吗？否则，托沃兹和 ZFS 之间的对峙可能会继续下去。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>