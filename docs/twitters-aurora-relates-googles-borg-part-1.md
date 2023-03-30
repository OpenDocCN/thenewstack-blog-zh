# Twitter 的 Aurora 及其与 Google 的 Borg 的关系(第 1 部分)

> 原文：<https://thenewstack.io/twitters-aurora-relates-googles-borg-part-1/>

这是我们关于 Twitter 的极光项目系列的第一部分。在第二部分中，Scott 探索了 Aurora 如何应用于任何公司，无论其规模如何。

21 世纪剩下的时间里，信息工作将不再由操作系统来管理。今天，我们认为 Twitter 是极少数以“互联网规模”运行的服务之一——其规模如此之大，以至于其域名的大小毫无意义。然而，Twitter 实际上是一个例子，说明在我们有生之年的大部分时间里，有一天，Twitter 将被视为一项日常工作，那种你希望由成千上万的集群服务器网络来做的事情。

Twitter 正在建立一个名为[极光](http://aurora.incubator.apache.org/)的服务自动化平台。这还没有完成；它的当前版本号是 0.7。这是一种作业控制系统，但它不是控制运行作业的服务器(就像操作系统在控制数据中心时所做的那样),而是控制约束服务器的作业。

但与首要的“互联网规模”服务谷歌不同，Twitter 正在公开构建 Aurora。

> 这是为了塑造一个推特、谷歌和脸书不再是超能力的世界……仅仅是权力。

## 一个大的操作系统

“像 Twitter 这样的平台运行在数万台机器上，每天有数百名工程师部署软件，”[上周在 Twitter 的工程博客](https://blog.twitter.com/2015/all-about-apache-aurora)上的一篇帖子写道。“Aurora 是一种软件，可在多种类型的故障面前保持服务运行，并为工程师提供了一种方便、自动化的方法来创建和更新这些服务。”

Aurora 的灵感来自于谷歌的一个内部项目，名为 Borg(这是谷歌的习惯)。这是该公司在其整个全球基础设施中实现服务自动化的首批努力之一。

Aurora 的首席工程师比尔·法纳(Bill Farner)之前在谷歌工作，并亲自观察了博格的转移。在与新堆栈的电子邮件交流中，Farner 指出，谷歌从一开始就全力投资 Borg，本质上，它的目标是尽快将谷歌现有的基础设施吸收到一种新的更自动化的运营方法中。

“但是，在我看来，博格软件本身变得非常复杂，难以管理，”法纳说。“在这方面，当开发 Aurora 时，我们(Twitter)能够从 Borg 那里借鉴一些我们应该做的事情，但更重要的是，一些我们不应该实施或支持的事情。”

Twitter 对 Aurora 的态度有些不同，首先是因为它在早期的态度更加谨慎，但也因为它的透明度。Aurora 是作为 Apache 项目 Mesos 的框架而构建的，旨在为互联网规模的工作构建一个操作系统，这是从底层硬件中移除的一个抽象层。

在去年 9 月制作的 YouTube 视频中，两位适马系统架构师 David Greenberg 解释了类似于 Linux 的 Mesos。他提醒圣路易斯的 StrangeLoop 会议的与会者，在 Linux 系统中，当操作系统给一个进程自己的内存地址空间、一组专用的文件描述符和单独的默认数据流“标准输出”(stdout)时，进程隔离就完成了。

Greenberg 把 Mesos 描述为一个独立的操作系统，它通过在 Linux 容器中运行作业来实现互联网规模的进程隔离。这种容器——随着 Docker 的惊人成功，最近几个月变得更加流行——为其中包含的进程获得独占的 CPU、内存和名称空间。

“因此，当我们在 Mesos 上的这些 Linux 容器中运行我们的应用程序时，”Greenberg 说，“那么您可以在同一台物理机上运行两个或三个或四个不同的系统，Linux 容器将确保每个系统都获得分配的配额，并且每个系统都不会耗尽其他系统的网络、磁盘、内存或 CPU。”

可以把 Mesos 想象成逆向虚拟化。虚拟机在物理机内部构建了一个抽象层，其中封装了一个独立的操作系统及其自己的应用程序集。通常，虚拟机有自己的桌面，驱动程序认为它们在直接运行硬件，而实际上并不是。

Mesos 是物理机器之外的一个抽象层，它升华了物理机器，使它们充当非独特服务器的池。通过这种方式，可以将任务分配给这些服务器，并提供容错和受控冗余。Mesos 使用开放的 API，而不是桌面，这使得它可以通过任何标准的 Web 客户端进行远程监控。

Aurora 成为了这个环境中的任务主。与操作系统将进程线程分配给单台计算机中的各个内核一样，Aurora 将作业(实际上，“作业”是一个技术术语)部署到网络中的多个集群。但是，与传统的操作系统模型不同，出于 Twitter 的目的，Aurora 可以分阶段部署作业。Aurora 不会强迫 Mesos 在其域中编排相同版本的作业，而是可以将较新的版本分发到指定的故障域，如果发现部署有问题，还可以回滚部署。

## 人的因素

当一个作业的两个或多个版本在同一个域中同时运行时，Aurora 如何缓解这种情况？有没有可能，一个任务的未来版本，泄露到与它自己的前任相同的系统中，会破坏更广泛的工作？想象一下如果 Microsoft Windows 必须管理多个版本的。NET 框架不断。(哦，等一下…)

我向 Twitter 的法纳提出了这些问题，他回答说，其中一些因素仍然被人类所缓解。

“这里有几个因素，不仅仅是勤奋的 API 和数据模型管理，”Farner 说。

> 他说，通过严格使用界面描述语言，可以将理智注入到过程中。

Twitter 选择的 IDL 是 [Apache Thrift](https://thrift.apache.org/docs/idl) ，它详细说明了函数期望接收的输入数据类型、函数输出的明确类型以及这些期望可能受限的领域。IDL 允许函数变得可变并自然进化，同时保持对将要交换的数据的固定预期。

换句话说，IDL 是现代服务所绑定的契约的通用语言。法纳补充道，或者，乔布斯可以利用更复杂的*数据序列化系统*，该系统定义了交换数据集应该遵循的更复杂的模式或结构。例如，Farner 提供了 [Google Protocol Buffers](https://developers.google.com/protocol-buffers/) ，它利用一种形式的源代码来定义更结构化的数据表示，以及 [Apache Avro](http://avro.apache.org/) ，它使用 JSON 来定义丰富的数据模式，使用动态数据类型而不是静态数据类型，尽管不生成代码。

Farner 补充说，对于负责帮助确保分阶段升级顺利进行的开发人员来说，更广泛的动机是“接受分布式服务系统不能安全地以原子方式更新。扳动开关并开始向新代码发送流量是非常危险的。相反，优雅的更新可以让人们及早发现故障，而且只影响一小部分流量。”

这里的关键是观察。虽然 Aurora 提供了分布式系统可能从未有过的自动化程度，但它也引入了人工干预、监控和最佳实践实施的新任务——完全“控制论”自动化系统(由“Borg”名称的原始灵感所暗示)可能缺乏的功能。

由于不同的服务器集群表现出不同的性能特征(延迟、访问时间、可用性)，Aurora 如何在不对服务产生负面影响的情况下实时解决这些差异？在我们讨论的第二部分，这是我将向 Twitter 的 Bill Farner 提出的问题之一。

图片 [via](https://www.flickr.com/photos/16927804@N07/8608176284/in/photolist-e7F9Uu-5VGWSd-dEK365-cxjCms-8KtqdM-6ehBWy-e7zsj2-7Q5KDt-dStNbB-dSznT5-dT2UFG-htZpk6-cxjDNw-4uq8Vc-e4b6br-fHodPG-bBXQ4R-q5pub8-dUVUc8-9k4MpQ-kyukDH-gngYNC-htXHVP-ekjAeS-3bGjb-6YqrcW-8JZzoA-dStNkv-5SM563-eFc7to-nY6EHZ-kFudt9-q7uu7W-ps4Hvo-56Qbwc-iWQDa-98auvz-7ALQRH-9hkB2k-htXWsT-k9GTfD-8Roph6-m4nq9p-oeQKVu-oeHPyn-6rhssr-nXwfjb-98asTg-dc2rHP-2XiTsU) Flickr 知识共享。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>