# SUSE 用一个新的 Linux 发行版 MicroOS 正式确定了容器策略

> 原文：<https://thenewstack.io/micro-os-suses-answer-container-os/>

可以说，CoreOS Linux 可以被称为第一个为集群计算、容器/微服务设计的基于 Linux 的操作系统。即使 CoreOS Linux(后来被重命名为“ [Container Linux](https://coreos.com/products/premium-managed-linux/) ”)植根于传统的 Linux 操作系统，它也提供了一种新的操作系统方法:Container Linux 最重要的特性之一是过渡升级，无需用户干预即可保持系统最新。

红帽用[项目原子](https://thenewstack.io/project-atomic-creates-infrastructure-for-linux-containers/)回应，Canonical 出了[爽快核](https://developer.ubuntu.com/core)。这就把 Linux 世界的三位一体之一 SUSE 抛在了后面。在行业转型期间，SUSE 正在经历一个过渡时期，其母公司 Novell [被 Attachmate Group】收购，并于 2011 年剥离出来成为自己的业务部门。并且在 2014 年 Attachmate 本身](https://www.cnet.com/news/attachmate-acquires-novell-for-2-2-billion/)[被](http://www.pcworld.com/article/2684352/micro-focus-buying-novell-suse-linux-owner-for-12-billion.html)[微焦](https://www.microfocus.com/)收购。

虽然观察人士指出，Attachmate 为 SUSE 提供了德国公司在 Novell 领导下所缺乏的急需的领导力，但 Micro Focus 的合并/收购给了 SUSE 再次展翅所需的自由和财政支持。该公司开始大举投资雇佣工程师，并推广其技术和产品组合。SUSE 已经准备好应对新的需求。

公司[一直在开发一个叫做 SUSE Container 的平台](https://www.suse.com/communities/blog/introducing-suse-containers-service-platform/)作为服务平台。SUSE CaaSP 将[SUSE Linux Enterprise MicroOS](http://containerjournal.com/2016/11/16/suse-launches-microos-caas-offering/)和基于 [Kubernetes](/category/kubernetes/) 的容器编排软件放在一起，前者是 SUSE Linux Enterprise Server 的一个变种，针对运行 Linux 容器进行了优化[也在开发中](http://containerjournal.com/2016/11/16/suse-launches-microos-caas-offering/)。

在一次采访中，SUSE 的新任首席技术官托马斯·迪·吉亚科莫博士告诉我们，有许多客户正在运行传统系统，但他们希望随着时间的推移迁移到现代技术。今天，如果你想从头开始，你将从容器开始。“我们希望确保拥有传统基础设施和传统应用程序的公司可以转移到现代技术，在现代技术中，容器即服务通过操作系统本身提供，”T 博士(他在 SUSE 圈子中的绰号)说。这就是 CaaSP 和 MicroOS 的设计目的。

## 世界是不够的

那些了解 SUSE 历史和技术组合的人可能听说过 SUSE 的 [JeOS](https://www.suse.com/products/server/jeos/) (刚好够用的操作系统)。SUSE 为什么不用 JeOS 而不是发明一个新的操作系统？[SUSE 产品经理新美乐股份公司·阿尔森](https://twitter.com/grey_pm)解释说，就像 SUSE Linux 企业服务器一样，JeOS 实际上是一个多用途的操作系统。“这意味着它不仅专注于集装箱。它可以在任何其他虚拟环境中使用。它可供嵌入式系统使用。它可以在任何其他虚拟机环境中使用。”

还有用 SUSE Linux Enterprise Server 或者 JeOS 这样的多用途操作系统有什么问题？“现在，当你试图在 SUSE 技术上构建你的容器化解决方案时，会遇到一些挑战，我们正试图用 MicroOS 平台解决这些问题，”Arsene 解释道。“是的，你有 SUSE Linux Enterprise Server，它是一个多用途的操作系统，可以做很多事情，但它并没有真正针对容器进行优化。”

“我们在 2015 年推出了 JeOS，我们试图将其定位为一个容器主机操作系统。我们意识到这是不够的，我们必须做出决定:要么我们调整 JeOS，要么我们寻找其他东西，”阿瑟纳说。“JeOS 在嵌入式系统领域非常受欢迎，所以我们需要为市场的特定部分保留它，但这些不是容器用户。在过去的几个月里，我们一直在讨论开发一些专门针对容器的东西，一些只关注这个领域的东西。我们决定保留 JeOS 作为多用途操作系统，因为它在自己的市场上非常有意义。”

“通过 CaaS 平台和 MicroOS，我们的目标是为客户提供一个易于使用的解决方案，满足他们在容器中运行应用程序的需求，”她补充道。“然而，正如 SUSE Linux Enterprise Server 和 JeOS 作为容器操作系统不理想一样，MicroOS 对于其他情况也不理想。它不是 SUSE Linux 企业服务器的继任者。”

“如果客户仍然运行混合环境，如果客户不一定关注容器，那么 MicroOS 不是他们的答案。这对我们来说很好，因为我们有适合每个人的东西:我们有 SUSE Linux Enterprise Server 和 JeOS，”Arsene 说。

MicroOS 不会蚕食 JeOS 或 SUSE Linux Enterprise Server。SUSE 的产品经理 Andreas Jaeger 认为“MicroOS 拓展了 SUSE 的市场。现在你可以用 SUSE Linux Enterprise Server、Kubernetes 和一些工具集以一种困难的方式建立一个集群，但是我们想让它变得更容易。通过为这项工作开发 MicroOS，我们为 SUSE Linux Enterprise Server 打开了更多的大门。现在，您可以针对不同的工作负载使用不同的技术，成为一个完整的 SUSE 商店。”

“我们现在在市场上推出的实际上是一种集装箱解决方案，这两种解决方案都不能满足新世界围绕集装箱建立的所有需求，”Arsene 说。

### SUSE CaaS 平台讲解:核心组件

SUSE 的新平台 CaaSP 有三个组件:MicroOS、Kubernetes，第三个是一个配置，用户将拥有 [Salt](https://saltstack.com/) 配置工具和一个容器引擎，如 Docker。

进入 MicroOS 的东西相当于 SLES 的最小系统。SUSE 杰出的工程师和高级架构师[托尔斯滕·库库克](http://www.thkukuk.de/)解释道:“它包含了能够在您的机器上启动的一切，无论是裸机还是虚拟机，如 KVM、Xen、VMware。”它包含内核、glibc、systemd、依赖项以及我们启动机器和启动 Docker、Kubernetes 等所需的所有内容。，无论我们需要什么。"

然后是用于事务性更新的工具。整个系统配置为使用 [cloud-init](https://cloudinit.readthedocs.io/en/latest/) 启动。那些有云经验的人知道 cloud-init 并能配置它。“与 SUSE Linux Enterprise Server 不同的是，在 MicroOS 中，根文件系统是只读的，所以不能写入。只有 etc 是可写的，但无论你写什么，下次重新启动时都会被删除，所以每次重新启动时，你都有一个干净的系统，然后你可以使用 cloud-init 来应用你的系统所需的配置，”Kukuk 说。

简而言之，“我们试图用 MicroOS 从 SUSE Linux Enterprise Server for containers 中‘提取’出一个目标系统，”Arsene 说。

## 秘制酱:Btrfs

MicroOS 将提供事务性更新，这样系统就会一直更新，不再有未打补丁或不安全的代码在生产中运行。这正是现代操作系统应该被设计的方式。

领先的 Linux 内核开发者之一 Greg Kroah-Hartman 在一次采访中说:“你必须能够运行一个能够自我升级的系统。许多人运行的系统不接受他们不能更新内核，或者他们认为如果他们坚持使用内核，如果什么都没有改变，那就很好。不是这样的。我们每天都在修复大约 10 个内核错误。并非所有问题都是安全问题，但有时最大的问题是我们不知道某个问题是否是安全问题。”

但是这些系统也需要故障安全。如果更新破坏了某些东西，它不应该停止服务。MicroOS 依赖于 [Btrfs](https://btrfs.wiki.kernel.org/index.php/Main_Page) 文件系统的快照特性，这使其区别于 CoreOS 的容器 Linux、Ubuntu Core 和 Project Atomic。其他系统有两个分区，其中一个被更新，而另一个运行，并且它们在重新启动后切换。使用 Btrfs，您只有一个分区，但是您可以保留任意多的快照，并在它们之间切换。所有更新都创建为快照，并且在系统重新启动后运行最新的快照后，如果出现故障，它会自动引导到以前的工作快照。因为我们谈论的是集群，所以不存在停机时间。

MicroOS 的目标不是成为另一个容器操作系统。“当我们对已经存在的解决方案进行一些研究时，我们意识到几乎没有什么东西可以完全指导你完成整个过程，”耶格说，“你仍然需要做大量的研究。你仍然需要进行大量的自学，以了解你拥有的机器之间的比例，你希望从中获得的性能，以及这些东西应该如何构造，我们正在努力做的就是降低这种入门水平，因此要有相同的默认设置，为用户提供建议，然后基本上他们可以接受或修改，但基本上你已经可以从一些准备好的东西开始，即使你从未接触过它，就像你以前从未接触过它一样。”

### Kubernetes 是将所有这些结合在一起的粘合剂

CaaSP 的第二个支柱是 Kubernetes，SUSE 与 Kubernetes 合作提供容器编排。“我们赌的就是这个。我称之为将两种技术粘合在一起，所以不仅仅是 SUSE Linux Enterprise Server。Kubernetes 是它的核心组成部分。CaaSP 的目标是与 Kubernetes 合作，为您提供一个开箱即用的堆栈，您不必担心操作系统是什么以及如何完成所有这些工作。您只需要部署解决方案。它适用于您的集群。”

SUSE 技术项目经理 [Federica Teodori](https://www.linkedin.com/in/fteodori) 说:“很明显，我们将把一切都提升到 Kubernetes 层，一旦进入 Kubernetes 层，它是什么集群就真的无关紧要了。如果您想在 Kubernetes 部分添加一些东西，这真的没关系，所以我们会确保您有一个现成的 Kubernetes 集群。我们将负责栈的部署，然后由用户决定他们想在 Kubernetes 上运行什么。

第三个支柱将是 Salt 和一个容器引擎，比如 Docker。SUSE 大量使用盐，有时人们想知道 SUSE 是否会获得这项技术。

那你什么时候能拿到？SUSE 将于 2017 年 3 月开始 CaaSP 的公开测试，最终产品预计将于 2017 年 7 月发布。SUSE 已经创建了一个邮件列表，这是大多数 Linux 项目的运行方式，因此对此感兴趣的客户或潜在用户可以订阅[邮件列表](http://lists.suse.com/mailman/listinfo/casp)并保持消息灵通。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>