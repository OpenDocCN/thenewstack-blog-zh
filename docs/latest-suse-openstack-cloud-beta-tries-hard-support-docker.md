# SUSE:准备 OpenStack 运行 Docker 的三大挑战

> 原文：<https://thenewstack.io/latest-suse-openstack-cloud-beta-tries-hard-support-docker/>

去年 7 月，Linux 发行商 SUSE 在 SUSE Enterprise Linux 的最新版本中正式支持 Docker。[发行版包括](https://thenewstack.io/suse-containers-dockers-role-and-avoiding-fragmentation-in-an-open-world/) Portus，该公司与 Docker Hub 和其他注册表交互的门户网站。上周二，在东京举行的 [OpenStack 峰会上，该公司宣称其即将发布的 OpenStack Cloud 6 也将支持 Docker，这一基于 SUSE Linux 的软件包的 beta 测试正在进行中，该软件包由 OpenStack 的 Liberty 版本构建。](https://thenewstack.io/tns-makers-openstack-tokyo-canonical-ubuntu-project-midokura-ibm/)

开源生态系统发展迅速。就在去年，OpenStack 支持 Docker 的想法似乎和 Windows 支持 Android 一样令人难以置信。然而，SUSE 和其他公司正在实现这一目标，为其客户提供了过渡到基于云的微服务时代的工具。这对组合有好处:根据英特尔的研究[，与采用 KVM 和 VMware 等传统虚拟机管理程序的 Docker 相比，在 OpenStack 上运行 Docker 可以提供更好的资源利用率和整体卓越的性能。](https://software.intel.com/en-us/blogs/2014/12/28/experimenting-with-openstack-sahara-on-docker-containers)

但是在 OpenStack 上支持 Docker 并非没有相当大的挑战，所以我们在与 SUSE 和 openSUSE 项目[的项目经理 Vincent Untz 的坦率讨论中了解到。Untz 详细介绍了他和他的团队在装备 SUSE 的 OpenStack Liberty 实现以实现容器的部署和管理时面临的三个具体挑战。每个挑战都围绕 OpenStack 的不同组件展开:](https://www.opensuse.org/)

## 1.新星

正如 OpenStack 资深人士所知，Nova(也称为 OpenStack Compute)是该平台的主要结构控制器。为了能够利用不同类别的虚拟机，Nova 使用了可插拔的驱动程序。到目前为止，这些驱动程序已经处理了特定的虚拟机管理程序(KVM、Xen、Hyper-V 等。).这种驱动程序以前缀“libvert”命名，因此 Xen hypervisor 驱动程序将会是`libvert/xen`。

但是有一个非官方的“树外”项目正在四处传播，用于构建一个`nova-Docker`驱动程序。正如 Untz 解释的那样，有了它，Nova 实例可以有效地成为 Docker 容器。

“还有一个`libvirt/LXC`驱动程序也允许启动容器，”Untz 指出，他指的是最初产生容器的 LXC 工作负载分区方法。“Docker one 更容易使用，并且还可以从 Docker Hub 使用容器，以及使用 Docker 工具与实例进行更多的交互——尽管它们不应该用于启动容器，否则 OpenStack 不会知道它们。”

Untz 承认使用`nova-Docker`驱动有一些明显的缺点，至少在目前的状态下是这样。其中一个对 SUSE 非常关键:Nova 使用 Glance 作为它的图像注册中心，这意味着容器必须上传到那里，而不是 Docker Hub。根据 Untz 的说法，这意味着 Portus 不能用于这种设置，至少现在不能。此外，因为 Glance 缺乏像容器注册表那样复杂的版本控制特性，所以版本控制必须是一种包含快照的杂牌产品。

Untz 说，目前，一些 OpenStack 功能与 Docker 容器图像不兼容，例如用于跟踪遥测和性能数据的[云高计](https://wiki.openstack.org/wiki/Ceilometer)。“但最令人恼火的是，你不能将卷附加到容器上，”他写道。“有些事情的运作方式也不同，比如网络。您不需要绑定容器端口，因为您实际上获得了容器的 IP 地址。”(更多关于 OpenStack 和 Docker 不兼容的细节可以在[这里](http://kb.brightcomputing.com/faq/index.php?action=artikel&cat=24&id=275&artlang=en)找到。)

## 2.热

Heat 是 [OpenStack 基于模板的编排引擎的名称。Untz 告诉我们，通过一个插件为 Docker 添加新的资源类型，Heat 可以用来编排 Docker 容器，就像它们是 VM 实例一样。他说，可以想象，人们可以使用一个加热器模板来启动一个 VM 实例，然后从该 VM 中，使用任何想要使用的东西来启动虚拟化平台上的 Docker 容器。](https://thenewstack.io/a-guide-openstack-kilo-developer-contributions/)

“这是一种以高级协调方式实现‘安全容器’魔法(VM 中的容器)的好方法，”Untz 写道。“我们的目标是能够开始使用容器，并从 Docker 的一些特性中获益。与虚拟机相比，它的优势在于，你可以更快地启动容器，它们对资源的需求也更少，此外，你还可以从 Docker hub 获得所有容器，作为在 OpenStack 中上传图像的良好起点。”

## 3.大酒瓶

提示[麦克发布音乐](https://www.youtube.com/watch?v=Gznsptq97pA&noredirect=1)。Magnum 是 OpenStack [组件，它开放了基础设施](https://thenewstack.io/magnum-is-the-name-docker-container-management-is-the-game/),不仅供 Docker 等容器系统使用，还供客户希望监管该系统的任何编排系统使用。

Vincent Untz 告诉我们，SUSE 现在面临的挑战是“无论如何”的部分。

“这里的好处是[Magnum]不会在 OpenStack 模型中强制 Docker 容器，”Untz 写道。“相反，它使用 OpenStack 作为获取 CPU、网络、存储等的方法。，为了做一些对 Docker 来说更原生的东西。”

然而，他补充道，“SUSE 并没有推出这款产品，而且它实际上还没有出现在路线图上。但是我们期待它会出现。

[![Suse](img/d1913173d9d3c865039296a5731fd280.png)](https://thenewstack.io/wp-content/uploads/2015/11/Suse.jpg)

“也就是说，从产品的角度来看，这需要与容器模块中发生的事情紧密合作，因为还没有决定在那里使用什么编排工具(不过我想它最终会成为 Kubernetes)”Untz 写道。“我们希望将 Magnum 中允许的内容与此保持一致。这是一个值得深入研究的问题，因为有些客户确实非常重视 Docker 和 open stack——他们会想要的。这是一个需要进一步探索的领域，以便充分理解人们为什么要使用它。”

这些是来自一个开源供应商的工程师的坦率承认，该供应商认真对待其对公式中“开放”部分的承诺。Untz 承认有一些需要社区参与的艰苦工作，以便 SUSE 为 OpenStack Cloud 6 中 Docker 支持的最终呈现确定最佳的架构方向。

关键是，正如 SUSE 或任何真正有价值的开源软件的情况一样，许多项目的最佳工程师都在公司之外。这就是 SUSE 发布 OpenStack Cloud 6 测试版的原因。

Docker、IBM 和 VMware 是新堆栈的赞助商。

专题图片:G. Stolyarov 的[“长寿之塔】在](http://www.rationalargumentator.com/index/minecraft-skyscrapers-stolyarov/)[知识共享许可](https://creativecommons.org/licenses/by-sa/4.0/)下转载于此。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>