# Mini-Mesos:一个优秀的 XPer 在这样的公司做什么？

> 原文：<https://thenewstack.io/mini-mesos/>

Mini-Mesos 是 Cisco Intercloud Services 和 Container Solutions 合作开发的。它是开源的，在 Apache 许可证下发布，版本 2.0。

大多数人都知道我喜欢极限编程(XP)以及与 XP 相关的东西:面向对象编程、测试驱动开发、测试数据管理和有效的构建系统。对于一些人来说，我们在容器解决方案和 XP 之间的联系可能看起来很脆弱或者不存在。然而，仔细观察，你会发现两者之间的联系非常紧密。

极限编程就是要缩短反馈循环。这是经典的洋葱图:

反馈循环在 XP 中很重要，因为这种方法试图帮助开发团队更好地响应客户的需求。这就是为什么，尽管面向对象(或面向组件)开发不是 XP 的一部分，但它是重要的，因为设计良好的对象可以被快速重组以服务于新的客户需求。这就是为什么重构和测试驱动的开发是 XP 的重要部分。

## 重构和测试驱动的开发

重构就是在不改变代码功能的情况下改进代码。如果没有一套测试来证明代码的行为是相同的，那么这样做是很危险的。

测试驱动开发(TDD)是关于设计的；通过首先编写测试，我们被迫考虑我们的接口和我们的对象之间的交互。由 Steve Freeman 和 Nat Pryce 推广的带有模拟对象的 TDD 是开发面向对象系统的特别好的方法。

TDD 的一个很大的副作用是留给你一套像样的测试，这意味着你可以或多或少安全地重构你的代码。(一旦测试写好了，测试套件就是一种安全网，一个检查的集合，以确保一切都或多或少地像重构开始之前一样工作。)

## 测试基础设施

除了使用 TDD 之外，我们中的许多人还曾经为基础设施编写测试。例如，我过去常常编写测试来 pinged 所有的数据库、消息系统，确保支付系统在那里，等等。我们这样做有两个原因。首先，因为如果出了问题，测试套件会指出问题所在；这些测试用于诊断目的。其次，我们这样做是因为我们常常无法控制基础设施。这些测试帮助我们将信息传递给运营团队，他们负责试运行、预生产和生产环境。

## 云

一旦云开始流行，我们就不得不考虑如何在不破坏我们已经习惯的紧密反馈循环的情况下部署到云上。换句话说，我们必须仔细考虑如何部署、测试和重构我们基于云的系统。这可不是小事。例如，我们如何在云上启动一个虚拟机，然后根据新的用户需求更新它？我们如何在本地重建云以解决任何基础设施问题？

## 梅索斯

随着云技术的发展，我们可以构建的解决方案也在发展。大约一年前，阿帕奇 Mesos 闯入了我们的生活。该工具使我们能够更有效地利用我们的硬件。对于拥有大量计算资产的客户来说，这很重要，因为使用 Apache Mesos 可以为他们节省数百万欧元。(关于 Mesos 优势的更详细解释可以在 Container Solutions 网站上由 Phil Winder 撰写的[文章](http://container-solutions.com/reasons-use-apache-mesos-frameworks/)中找到。)

对于我们来说，一旦 Mesos 到来，一个新的问题出现了:我们如何为 Mesos 开发容器化的应用程序和框架，同时仍然执行 TDD 和持续集成的核心 XP 实践？

## 进入迷你 Mesos

容器化解决方案提供了两个关键服务。一方面，它们支持在生产环境中顺利部署和管理应用程序。另一方面，他们提供应用程序开发。因此，我们必须想出既有助于应用程序开发又有助于基础设施设计的工具。

快速解决操作问题的一种方法是在笔记本电脑上重现完整的生产环境。Docker Compose 朝这个方向迈出了一小步。遗憾的是，它对 Mesos 没有任何支持。这意味着我们必须设置我们的 Mesos 集群，部署到它，然后手动运行我们的测试。这可能需要几分钟，对于更复杂的框架，可能需要几十分钟。因此，XP 提供的反馈回路被彻底破坏了。我们意识到我们必须创建自己的测试工具来构建 Mesos 框架。我们称这个工具为迷你 Mesos。

Mini-Mesos 有三个主要特点:

*   它允许开发人员在本地机器上启动一个 Mesos 集群，完成他们正在开发的任何框架。
*   它有一个 API，用于以编程方式操作集群。我们称之为“容器 API”
*   它有一个查询集群状态的 API。我们称之为“集群状态 API”这个 API 让我们获得集群的状态，以便运行自动化测试。

由于这些特性，我们能够首先构建我们的容器化应用程序和我们的 Mesos 框架测试，这改进了设计并允许我们执行快速重构。因为我们可以在几秒钟内实例化集群、运行测试套件并销毁它，所以我们的开发周期很快；也就是说，在验证我们最近的更改之前，我们不必部署到真正的云，或者签入我们的代码。

简而言之，Mini-Mesos 允许我们使用我们最喜欢的开发方法:极限编程来开发应用程序和框架。

## 结论

1998 年，当我还是个学生的时候，我摆弄过 Java 的反射库，并创建了一个测试运行程序，寻找以“test”开头的方法。后来我发现了 JUnit，也许我笑着说我偶然发现了一个好主意。

那时，我们需要构建自己的工具来实践 XP。现在也一样；我们必须构建工具，让我们能够针对云进行 XP。Mini-Mesos 是一个允许我们这样做的工具。它是现在列表中的一个新品种，几乎肯定包括 Apache 的 Mesos、Hashicorp 的 Terraform、各种 CI 工具，当然还有 JUnit。总之，这些新工具和旧经典构成了开发分布式系统的新 SDK 的基础。

关于如何使用 Mini-Mesos 的例子，请参见 [Git](https://github.com/mesos/elasticsearch/tree/master/system-test/src/systemTest/java/org/apache/mesos/elasticsearch/systemtest) 上的 Mesos/ElasticSearch 项目。更多在[迷你米索斯](http://minimesos.org/)。

思科和 Docker 是新堆栈的赞助商。

专题图片:“ [OMG！](https://www.flickr.com/photos/lilivc/4191500662/in/photolist-7oox7N-dd5prD-a2n6by-nqvtjd-iZnQgJ-rPMG2f-m7vUfa-qces6E-axv1UW-c5oaL5-8W95ob-58aVnJ-nvYWnf-fSCHXq-bCZPZ2-j9ysun-qj1F1c-dCHDUU-kaayPr-85UJSR-8bbpR7-7cXqC1-NAeYv-mqTZDp-khFBhG-ebr3Ec-kJ75DX-qGEp2j-p5Eck4-jKGkxF-8kr92T-9FHT33-G1gZd-m9xxyq-7JQhy5-dCz8m6-optAJc-8YR5Wr-iYKtZW-bDK882-6Qs7T7-asoaFG-nv4Pem-dgUFtx-h3E6vs-dzeh5E-8BJyvq-8r1Gh8-9cfXcy-qq5wJ8)由[莉莉维埃拉德卡瓦略](https://www.flickr.com/photos/lilivc/)在 [CC BY-ND 2.0](https://creativecommons.org/licenses/by-nd/2.0/) 下授权。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>