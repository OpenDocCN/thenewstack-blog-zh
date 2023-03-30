# Metal3 使用 OpenStack 的讽刺来声明裸机 Kubernetes

> 原文：<https://thenewstack.io/metal3-uses-openstacks-ironic-for-declarative-bare-metal-kubernetes/>

[红帽](https://www.openshift.com/)赞助本帖。

上周在科罗拉多州丹佛市举行的开放基础设施峰会上，游戏的名字是裸机。

OpenStack 基金会吹捧其[裸机供应和管理工具 Ironic](http://openstack.org/bare-metal) ，在主题演讲期间走上舞台，不仅表明[裸机是其最新版本](https://thenewstack.io/bare-metal-moves-to-the-forefront-with-openstack-ironic/)的主要焦点，还公布了一个新项目 [Metal3](https://github.com/metal3-io/baremetal-operator) (发音为“metal cubed”)，根据公司声明，该项目使用 Ironic“作为 Kubernetes 裸机基础设施的声明性管理的基础”。主题演讲的描述还提供了以下内容，这有助于将事情放在上下文中——“虽然[OpenStack Ironic]经常被用作 Nova 等云基础架构的计算驱动程序，但我们将展示一个新项目如何使用 Ironic 作为 Kubernetes 裸机基础架构的声明式管理的基础。”

当然，裸机并不是什么新鲜事。就在 Ironic 和 Metal3 发布之前，雅虎的架构师 James Penick 对威瑞森媒体在 OpenStack 上使用裸机做出了解释，指出该公司管理着数十万台机器和数百万个内核。

“虚拟机、容器、功能都很棒，但每样东西都位于底层，它们都位于裸露金属的基础之上。佩尼克说:“裸机并不华丽，也不迷人，它不是人们在博客上气喘吁吁地谈论的最新酷的新玩具，但你必须面对它，所以我们在那里投资。”“我们改变了业务，让基础架构即服务裸机成为一个选项，然后成为一个默认选项，最后成为强制选项。曾经是异端的想法，变成了常识。”

在佩尼克之后，[open stack 基金会高级战略项目经理 Chris Hoge](https://www.linkedin.com/in/hogepodge) 和[open stack 讽刺项目团队负责人 Julia Kreger](https://www.linkedin.com/in/juliaashleykreger) 上台演示了 [Metal3](https://github.com/metal3-io/baremetal-operator) ，这是一个新项目，提供“为 Kubernetes 提供裸机主机供应集成”

在与新堆栈的电子邮件采访中，Kreger 解释说，她认为 Metal3 是一个更大趋势的一部分，用户正在寻找更好、更有效的方式来做他们正在做的事情，特别是使用通用工具和方法。

“我认为，我们开始看到的更大趋势是，人们认识到，通用工具和基板有助于每个人更快、更高效地成功，”Kreger 写道。“这与运营商选择大规模解决问题的方式的转变相结合，特别是在隔离、成本或性能方面。”

当被问及 Metal3 将解决什么问题以及它的目标是谁时，Kreger 给出了以下答案。

Kreger 解释说:“Metal3 为 Kubernetes 友好控制和编排的裸机提供了一条简单的途径，这些裸机在内部利用 OpenStack Ironic，因此能够利用 Ironic 中的许多经验教训和技术。“总是有不同类型的用户。一些用户需要或想要更多的声明性方法和模式来管理他们的基础设施。Metal Cubed 在 Ironic 的基础上提供了这一功能，以便通过 Kubernetes 的“自定义资源定义”来帮助达到声明的端点，这有助于用户使用单一工具进行交互。

当在较小的规模上操作时，或者根据应用或组织的需要，声明性模型，例如由 Kubernetes CRD 接口驱动的那些，允许通过 Kubernetes API 接口消费建模语言。这允许后端逻辑在内容方面重用相同的模型/文档契约，这在相似性和更容易采用方面帮助了用户，”Kreger 在后续的电子邮件中写道。“CRD 最终允许在与 API 的基本交互方面的跨供应商相似性，这是非常强大的，但是如果标准最终没有从这些交互中创建和形成，碎片化也会损害有用性。Metal3 最强大的方面在于它利用了 OpenStack Ironic，它已经并将继续抽象和公开通用的供应商中立接口。”

有关详细信息，请查看主题演讲的视频，其中包括使用 Metal3 为三台裸机服务器快速配置 Kubernetes 的演示:

[https://www.youtube.com/embed/Nzq2S53nk9U?feature=oembed](https://www.youtube.com/embed/Nzq2S53nk9U?feature=oembed)

视频

来自 Pixabay 的 Jarkko Mä nty 的专题图片。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>