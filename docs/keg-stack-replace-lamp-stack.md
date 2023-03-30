# “桶”栈应该取代灯栈吗？

> 原文：<https://thenewstack.io/keg-stack-replace-lamp-stack/>

编者按:这篇文章的技术真实性受到多方质疑。特别是，对于分布式键值存储 etcd 可以替代关系数据库 MySQL 的断言，人们表示了极大的怀疑。点击此处了解更多详情。

多年来， [LAMP stack](http://www.webopedia.com/TERM/L/LAMP.html) (Linux、Apache、MySQL、PHP/Python/Perl)一直是开发人员的绿洲，他们希望构建现代应用程序，而不会陷入某个大供应商生态系统的沙漠中。它是一个方便的、广泛使用的开源框架，使得应用程序架构对开发人员来说很容易。

然而，正如快速变化的技术格局为 LAMP stack 在 20 世纪 90 年代末的崛起奠定了基础一样，web 开发的新变化和趋势现在正导致您可能会称之为“夕阳时期”的到来

 [西里什·拉古拉姆

作为首席执行官，Sirish 负责 Platform9 的团队，platform 9 是一家提供托管私有云部署的公司。在某一天，他的工作范围可能从战略和路线图到发布代码和运行测试。在共同创建 Platform9 之前，Sirish 是 VMware 的一名工程师，他在 VMware 担任技术和管理领导职务，并帮助发布了多种 vSphere 产品。Sirish 的工作已经反映在几项专利、VMworld 会谈和 VMware 工程内部的产品创新中。Sirish 拥有印度浦那大学的计算机科学学士学位。在 9 号平台之外，Sirish 关注板球，逗他的女儿笑，并收集快速镜头和未经处理的照片。](http://www.platform9.com) 

今天，如果您不将应用程序分解成更小的组件，这些组件可以独立地部署和伸缩，并具有灵活性和故障恢复能力，那么您实际上就完蛋了。两个主要趋势强调了这一转变:首先，堆栈的每一层现在都可以“作为服务”使用，这使得开发人员能够外包许多曾经深深嵌入堆栈的职责，并最终更快地交付更好的产品。

其次，近几年移动使用模式的兴起加速了这种重组。移动现在是用户与应用程序联系的主要方式。这意味着开发人员必须构建具有高度弹性的应用程序，这些应用程序可以在世界各地使用，并且具有足够的可伸缩性来处理数百万个客户端。无论你如何切割，灯堆栈架构根本无法处理这些需求。

那么接下来会发生什么呢？从开发框架到编程语言以及两者之间的一切，今天的开发人员比以往任何时候都有更多的选择——而且这个工具箱只会越来越大。出于这个原因，开发者应该让我们一直称之为 LAMP 的组件栈不断进化。现在，如果我们用更现代的工具和框架来重新铸造，这里有一个新的灯堆栈的快照:

## Kubernetes 取代了 Linux 和 Apache

传统上，应用程序是根据特定的操作系统来设计的。对于 LAMP 堆栈，这意味着 Linux。然而，今天，新的思维方式比 Linux 能提供更多的可移植性。这使得 [Kubernetes](https://thenewstack.io/ebooks/use-cases/use-cases-for-kubernetes/) 开源容器编排引擎成为 Linux 的一个很好的替代平台。它将 Linux 抽象化的能力使 Kubernetes 成为当今许多应用程序的操作系统。

另外，Kubernetes 还擅长路由网络流量，这意味着它也可以取代 Apache。多亏了 Kubernetes，开发人员不再需要在需要更改时处理配置文件和静态配置。使用 Kubernetes 构造(如 Ingress、Services 和 LoadBalancer)来路由网络请求，开发人员可以自由地采用一种更加分布式和弹性的方法，这种方法还具有高度的动态性和适应性。

## Etcd(可能)取代 MySQL

MySQL 仍然是一个流行的关系数据库管理工具。但是，如果您想要具有弹性的持久数据，那么您需要将它存储在某个地方，该地方自然允许水平伸缩，并且可以透明地处理节点故障。换句话说，你想分布数据层来启用这样的属性，MySQL 可能不是最好的选择。

今天有很多服务可以满足这种需求，其中最受欢迎的是 [Etcd](https://thenewstack.io/etcd-may-next-project-cloud-native-computing-foundation/) 。其他还有[领事](https://www.consul.io/)(来自 hashi corp)[doozerd](https://github.com/ha/doozerd)、[cocroach db](https://thenewstack.io/cockroachdb-1-0/)、谷歌【PDF】的[扳手。最终，正确的选择取决于您的应用程序的性质。](https://research.google.com/archive/spanner-osdi2012.pdf)

CockroachBD 和 Spanner 最适合需要更高级的数据管理系统来存储大量数据、满足传统的 [ACID 数据库保证](https://vladmihalcea.com/2014/01/05/a-beginners-guide-to-acid-and-database-transactions/)以及使用 SQL 等传统查询语言的应用程序。对于大多数其他人来说，Etcd，领事，和 DoozerD 就可以了。

除了提供数据持久性的服务之外，应用程序还越来越依赖于附加的数据处理服务，如消息队列。为了满足应用程序的需求，这些服务还需要具有高度的可伸缩性和可靠性。

## Go 取代 Python

Go 语言正在吃掉 Python 的午餐，成为开发现代应用程序(尤其是微服务)的首选语言。

与 Python 相比，Go 的一个关键优势是所有依赖关系都在构建时解决。这有助于开发人员消除代码中潜伏的任何意外，并保证他们的应用程序在部署时不会意外中断。

最重要的是，Go 还允许应用程序利用多个 CPU 内核。基本上，这些天来 CPU 的速度没有任何提高，这意味着获得更快速度的最好方法是增加更多的 CPU 内核。Go 在这方面也有优势:它对并发的优雅支持使得开发人员可以轻松利用多核。由于 GO 程序是静态类型的，并被编译成本机代码，因此它们的运行速度要比 Python 等解释型或动态编译型语言快得多。

结合这些观察，你可能会说“桶”栈是一个很好的替代灯栈的候选。但这忽略了更重要的一点:不管喜欢与否，标准“栈”的整个概念正在被分解。

今天的开发人员比以往任何时候都可以使用更大、更丰富、更强大的工具集，这意味着遵循 LAMP 甚至 KEG 这样的规范方法是错误的。在这个新世界中，关键是识别支撑应用程序的行为、模式和原则。只有到那时，合适的工具才会变得清晰。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>