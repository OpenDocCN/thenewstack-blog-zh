# 单核如何更好地防御 DDoS 攻击

> 原文：<https://thenewstack.io/unikernels-can-better-defend-ddos-attacks/>

在 [The New Stack Makers](https://thenewstack.io/podcasts/Makers) 播客中，云管理部门和首席技术官办公室的 EMC 首席技术官戴尔 EMC 首席技术官[艾迪特·莱文](https://www.linkedin.com/in/iditlevine)讨论了 unikernels 如何准备提供开发人员为容器提供的所有灵活性，同时努力实现更好的安全性以及与当今许多顶级容器平台的集成。在 KubeCon 2016 大会上，她采访了[网络安全管理软件产品](http://www.solarwinds.com/)云技术负责人[李·卡尔科特](https://www.linkedin.com/in/leecalcote):

[单核如何更好地防御 DDoS 攻击](https://thenewstack.simplecast.com/episodes/how-unikernels-can-better-defend-against-ddos-attacks)

[https://www.youtube.com/embed/fysw3Le34jc?feature=oembed](https://www.youtube.com/embed/fysw3Le34jc?feature=oembed)

视频

在本月早些时候的 KubeCon 上，Levine 和开源 unikernel 编译和管理平台背后的团队的其他成员宣布了 Unik 的新特性，旨在促进 unikernel 的采用和社区参与项目的发展。这些变化包括 [Kubernetes](http://kubernetes.io) 集成，用户能够与 Kubernetes 并行运行 Unik，以及在社区不断请求后增加对[谷歌云平台](https://cloud.google.com/)的支持。

最重要的是，没有社区的参与，unikernels 和 Uniq 等项目就无法发展和改进。“Unik 是开源的。我们在寻找拉取请求。去帮助我们做得更好，”莱文说。

讨论还涵盖了单内核的安全优势，从最近的 [Dyn 为中心的拒绝服务攻击，上个月](http://www.forbes.com/sites/kalevleetaru/2016/10/31/the-dyn-ddos-attack-and-the-changing-balance-of-online-cyber-power/#5f1b27d5e230)阻止了对许多顶级网站的访问。莱文写了一篇[的帖子](https://github.com/emc-advanced-dev/unik/wiki/Worried-about-IoT-DDoS%3F-Think-Unikernels)，认为如果 [Mirai 未来组合僵尸网络](https://www.incapsula.com/blog/malware-analysis-mirai-ddos-botnet.html)遇到了基于单核的物联网设备，攻击根本不可能发生。“在本文中，我们回顾了所有流行的方法(到 DDoS ),如 shell 注入、目录遍历等等，试图理解如果在那里运行 unikernels 会发生什么。这是不可能的，那次袭击不会发生，”莱文说。

“单核的美妙之处在于你只运行一个进程。即使你能以某种方式进入 unikernel，它也没有外壳可以使用，所以你不能执行任何外壳脚本。它的美妙之处在于，你实际上无法运行一个危险的额外二进制文件，这很好，”莱文说。

思科是新堆栈的赞助商。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>