# 一个完整的应用程序堆栈，即将出现在您身边的硬盘上

> 原文：<https://thenewstack.io/a-full-application-stack-coming-soon-to-a-drive-near-you/>

在佐治亚州亚特兰大举行的 OpenStack 峰会上，西部数据公司 HGST[展示了其新的“开放式以太网驱动器架构”，旨在展示应用程序如何可以直接在硬盘和固态硬盘上运行。该体系结构的目的是支持软件定义的存储、大数据、分析和其他应用程序等使用情形，这些应用程序受益于最大限度地减少延迟和增加存储与计算之间的带宽。借助这一新架构，HGST 将完整的计算堆栈(包括 CPU、RAM 和网络)集成到驱动器上。](http://www.hgst.com/press-room/press-releases/HGST-)

正如演示的那样，每个 4TB 驱动器(如果我们甚至可以称之为“驱动器”)包含一个 ARM CPU、板载 RAM，并且运行一个完整的 Linux 环境。这使得每一个都可以运行现成的横向扩展存储软件——GlusterFS、Ceph ( [现已展示了 Red Hat technologies](https://thenewstack.io/red-hat-seeks-to-bolster-openstack-position-with-inktank-acquisition/) )和 Swift 并作为分布式存储集群中的一个节点充分参与。

虽然每个驱动器都包含一个完整的以太网堆栈，但驱动器本身通过 SAS 连接到 4U 60 插槽驱动器盒中嵌入的交换网络结构。该结构通过 10Gbps 以太网将每个设备作为 Linux 服务器公开。4U 机箱中的 0.25 千兆字节并不坏，尤其是考虑到旅途中附带的计算能力。

### 利用全堆栈磁盘驱动大数据

虽然 HGST 的使用案例是横向扩展存储，但更进一步考虑这种模式的含义是很有意思的，因为整个应用程序堆栈都位于单个硬盘上。至少在理论上，这项技术最引人注目的用途之一可能是 Hadoop、Spark 或运行在类似设备上的其他分析堆栈。

Hadoop 的成功很大程度上来自于它能够确保计算在包含被操作数据的节点上运行，这种特性称为数据局部性。通过将 CPU 与驱动器本身集成在一起，并用高速总线将两者连接起来，数据路径得到了进一步优化，应用程序离数据更近了。

当然，在试图让 Hadoop 在 HGST drive 这样的微设备上充分运行时，还有一些问题需要克服，但是[已经完成了](http://www.dzone.com/articles/big-data-processing-arm-0)。向上扩展处理器可能会成为更好的大数据节点，但热量可能是一个问题。不过现在，对于演示的用例，HGST 的产品营销高级总监 Mario Blandini 向我保证，热量的增加可以忽略不计。

Blandini 说，公司正在小心地管理期望，他很快强调这只是开放以太网驱动器概念的演示。软件定义的存储使用情形恰好特别适合该架构，因为它对 CPU 和内存的要求不高，但很容易看出它的发展方向。

希捷凭借去年秋天发布的[动能技术](http://www.seagate.com/about/newsroom/press-releases/Seagate-breakthrough-fundmentally-alters-cloud-economics/)在这场游戏中领先一点，尽管马里奥指出他的公司采取的开放方法是一个优势。

图片来源 [通过](https://www.flickr.com/photos/freetheimage/11452593526/in/photolist-is2x45-uS4D4-GvwY5-6qSkbD-5RVXtQ-knM6Qx-5ButcM-5Xcbgy-5zHYiu-9TFLS8-5xcoEn-n7HoGv-6cPHz4-m47Win-cFMMd-8VUxst-iNmvEe-fpptu4-fpDJm9-fpDJos-fpptuK-fpptv8-fpDJpL-fpDJoU-fpptti-fpptvD-fpDJp9-fpDJpY-fpDJpf-fpDJmy-fpDJn7-fppttK-fpptsH-fpptt4-fpDJnQ-fpptvg-fppttP-fpDJnY-fpDJmJ-uS4xz-iJXpA4-9db8Ms-5cwAAc-48sikG-hbXubC-uS4sz-6qacEP-uS4Gc-4eDujh-dDWYq) 在 Flickr 上创建共享资源

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>