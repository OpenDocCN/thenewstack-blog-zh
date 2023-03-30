# 向左移动:云计算原生计算安全性的发展方向

> 原文：<https://thenewstack.io/shift-left-where-cloud-native-computing-security-is-going/>

在 [Kubecon Europe 2022](https://events.linuxfoundation.org/kubecon-cloudnativecon-europe/) 大会上，一些云计算领域最优秀、最聪明的安全专家谈论了我们现在所处的位置以及未来的发展方向。真正简短的版本是，“我们将尽快[将安全转移到 DevSecOps](https://thenewstack.io/4-reasons-to-shift-left-and-add-security-earlier-in-the-sdlc/) 但是所有的专家都承认，说起来容易做起来难。

安全转移的根本原因是威胁可能来自任何地方。[云本地观察公司](https://www.linkedin.com/in/owengarrett/?originalSubdomain=uk) [Deepfence](https://deepfence.io/) 的产品和社区负责人 Owen Garrett 指出,“在过去，当我们构建一个应用程序时，它就像一座城堡。我们建造了一堵高墙，安装了一扇大门和一名守门人，以此来保护它，因为我们知道城堡是什么，人们从哪里进入，我们可以通过阻止人们进入来保护它。”

现在不再是这样了。加勒特继续说，今天，我们的应用程序不再是城堡，它们“就像城市一样，随着时间的推移而成长和变化。他们有漏洞百出的边界，你不能把它围起来，威胁来自外部或内部，在某种程度上，城市里的对手并不完全可信。因此，对于如何保护应用程序，您必须从更广泛的团队角度出发。从开发到运营，以确保我们应用程序的完整性。”

## 文化变迁

正如云原生安全公司的首席开源官 Liz Rice 所说，“围绕开发和部署的速度和灵活性，有一种文化上的改变。”此外，“在 cloud native 中，我们将应用部署到 pod 中，这些 pod 会动态分配 IP 地址。使用 IP 地址和端口号的传统网络安全工具在云原生环境中并不真正有意义。这就是云原生一代安全工具在我们今天尝试的传统方法之上的优势所在。”

因此，云原生安全咨询公司[控制平台](https://control-plane.io/)的首席执行官[安德鲁·马丁](https://www.linkedin.com/in/andr3wmartin/?originalSubdomain=uk)指出，我们正在看到一种“责任的变形”。 [Gitops](https://thenewstack.io/getting-started-with-gitops/) 让开发人员能够访问供应基础设施，从而做出可能影响整个系统安全性的决策。”他说，这意味着“安全成为每个人的责任。”这就是自动化和左移如此重要的原因。为了快速前进，我们需要将安全测试工具应用到离开发人员更近的地方，并确保每个人都了解他们的基础设施变化可能带来的影响。"

## 现在有什么不同？

但是，正如一名记者问的那样，“我们多年来一直听到团队对安全的责任，这次有什么不同？”

首先，我们现在没有太多的选择。要么你做对了，要么你的软件出现在安全新闻的头条。尽管如此，赖斯承认，“这并不简单明了。这需要文化上的改变。”

关于这一变化，Martin 说，“这一变化的实际具体实施是在团队中设立一个安全冠军。这个人也必须被授权硬停止功能发布，除非它已经检查了正确的安全标准。”也就是说，加勒特补充说，安全不是一个人的工作。"安全责任现在由团队共同承担."

## 自动化安全性

同时。Veeam 的产品和合作伙伴副总裁 Gaurav Rishi ， [Kasten](https://www.kasten.io?utm_content=inline-mention) 说，虽然“没有人喜欢检查清单”，但这可以通过使用备份和数据保护等方法通过[策略即代码](https://thenewstack.io/policy-as-code-or-policy-as-data-why-choose/)实现自动化安全来解决。

所有人都同意，安全必须尽可能自动化。Garrett 说，我们都知道，“激励开发人员的是完成工作，许多开发人员没有全球视野，或者甚至在行业中没有成熟到将安全性视为完成工作的障碍之外的任何东西。”

可以做的一部分是让开发人员在安全漏洞变成安全问题之前发现它们，这是有价值的。正如 Rice 所观察到的，“我们在漏洞奖金等方面给予黑客可衡量的奖励，这非常引人注目，但我还没有看到下一步的任何事情——奖励修复漏洞的人。”

当然，安全专业知识如此分散也于事无补。Rice 回答说，您必须有合适的工具来涵盖扫描、签名、运行时保护等，并在不同的开发阶段和不同的基础架构层应用它们。因此，“你不只是有一层，你有许多薄的安全层，累积成一个厚层。”

## 创建软件物料清单(SBOM)

专家们还谈到了创建[软件材料清单(SBOM)](https://thenewstack.io/sbom-everywhere-the-openssf-plan-for-sboms/) 的困难。当然，加勒特说，“汽车行业非常擅长维护车辆的库存。但事实是，在整个基础架构中保持准确的 SBOM 非常非常困难。这是因为每个第三方插件都有自己的依赖项和组件，总体情况是不断变化的。”

尽管如此，每个人都同意，问题需要解决。他们希望像[开源软件基金会(OpenSFF)](https://openssf.org/) [Alpha-Omega](https://openssf.org/community/alpha-omega/) 这样寻求改善大多数关键开源项目的供应链安全性的项目，将有希望改善每个人的 SBOM 安全性。

最后，我想我们都知道，安全性，不管喜欢与否，正在成为云本地计算的一个越来越重要的问题。我们必须使用自动化工具尽可能地将它部署到左侧，同时鼓励每个人认真对待安全性。在这件事上我们真的没有任何选择。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>