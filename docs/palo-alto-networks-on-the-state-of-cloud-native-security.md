# Palo Alto Networks 的云原生安全性现状

> 原文：<https://thenewstack.io/palo-alto-networks-on-the-state-of-cloud-native-security/>

随着软件安全几乎每天都在遭受打击，我们比以往任何时候都更加认真地对待保护我们的程序和云变得更加重要。但是在我们这样做之前，我们必须知道今天什么是不安全的。这就是安全公司[帕洛阿尔托网络(PANW)](https://www.paloaltonetworks.com/cloud-security?utm_content=inline-mention) 发布其最新[云本地安全报告](https://www.paloaltonetworks.com/resources/research/state-of-cloud-native-security-2022)的原因。

然而，云及其安全性的一个最大因素超出了任何技术公司的控制。根据 PANW 的说法，新冠肺炎疫情代表了自第二次世界大战以来最深刻的世界性社会和经济剧变之一。结果是:

*   向远程工作、学校和医疗保健的快速转变推动了在线协作和会议工具的激增。
*   对云交付的业务关键型应用程序的突然而强烈的需求
*   广大消费者转向接触较少的网上购物和外卖餐饮。
*   从社交服务到供应链管理，对云基础设施支持的需求日益增加。

## 增加向云的迁移

就数量而言，在疫情期间，组织对云的使用总体上增加了 25%以上。此外，目前 69%的组织将超过一半的工作负载托管在云中，而 2020 年这一比例仅为 31%。今天真的是一个云 It 世界。

企业也在平台即服务(PaaS)和无服务器上花费更多。这可能与他们向云的快速过渡有关。与此同时，集装箱和集装箱即服务(CaaS)出现了较为温和的增长。这最后一部分让我感到惊讶。我猜想集装箱，在很大程度上是因为 [Kubernetes](https://kubernetes.io/) ，会占用更多的资金。

太糟糕了，他们没有花那么多钱来保护他们的新云服务。尽管有如此巨大的增长，公司在他们的云上平均支付更少的费用。现在，这可能是因为全面的预算削减；重新分配欠疫情的资金；或者，它可能只是反映了云活动的“正常化”和预算。

或者，我怀疑是公司降低了云部署的成本。我想我们都知道，当企业急于部署新技术时，安全性会成为预算的短板。

## 扩大云安全团队

这不是 PANW 发现的。这只是我愤世嫉俗的猜测，因为我花了太多的时间报道技术。虽然顶线云预算下降，但云安全预算保持稳定。事实上，PANW 认为，虽然组织在云上的总体支出减少了，但他们并没有动摇他们的安全预算。PANW 也看到了公司扩展他们的云安全团队。53%的组织报告拥有超过 30 人的安全团队，高于去年的 41%。我希望这意味着每个人在保护他们的云方面确实做得更好了。我真的很想，但是让我变得愤世嫉俗。

有趣的是，那些在云迁移方面做得最好的人往往拥有最强的安全态势，81%的人被评为强或非常强。然而，那些快速采用云技术并且在这方面做得很差的公司通常安全性很差。这让我想到，成功部署的聪明公司知道安全性很重要，而那些在云方面遇到麻烦的公司也在安全性方面遇到麻烦。换句话说，如果你不擅长部署和迁移，你也会不擅长安全。

所有这一切本身就足以成为一个挑战。但是，当公司竞相满足这些新的、意想不到的需求时，他们发现自己正面临一个直接摆在他们技术肩上的全球性威胁:网络攻击。

## 突发事件

正如 PANW 指出的那样，从疫情的前六个月开始，与组织增加云支出相关的“安全事件激增”。结论是“快速的云规模和复杂性，而没有嵌入整个开发管道的自动化安全控制，是一个有害的组合。”

情况没有改善。多亏了奥米克隆，疫情才得以延续。组织继续将工作负载推向云，同时仍在努力实现云安全自动化并降低云风险。

PANW 没有制造恐慌。其他人也注意到了这个持续的问题。 [NCC 组](https://www.nccgroup.com/us/)已经评论了[持续集成/持续交付(CI/CD)](https://practical-tech.com/2018/07/10/continuous-integration-and-delivery-tool-basics/) [管道攻击正在蓄势待发](https://research.nccgroup.com/2022/01/13/10-real-world-stories-of-how-weve-compromised-ci-cd-pipelines/)。这是对软件供应链日益增长的攻击的一部分。

有趣的是，拥有一流安全运营的公司在工作效率和满意度方面看到了员工的最大收益。80%的安全状况良好的员工表示工作效率有所提高。

## 薄弱的安全态势

不幸的是，大多数组织(55%)报告说安全状况不佳，并认为他们需要改进其底层活动。不是开玩笑吧？如今运行不安全的云无异于自找灾难。

PANW 还发现，80%主要使用开源安全工具的组织的安全状况很差或非常差，相比之下，26%的组织主要利用云服务提供商，52%的组织依赖第三方。然而，问题不在于开源安全工具。那就是很难用不同的工具拼凑出一个平台。简而言之，如果你不擅长使用开源安全工具，就找擅长的人。如果你不知道开源工具是如何组合在一起的，那么把它们放在一起就是一种错误的节约。

公司似乎得到了这个教训。PANW 发现，近四分之三的企业现在使用 10 种或更少的安全工具。他们还发现，与 2020 年的数据相比，仅使用一到五家安全供应商的组织数量增加了 27%。这表明他们正在寻求更少的安全供应商来提供更多的功能。

## 自动化是关键

PANW 还发现，越多的团队实现了安全自动化，他们就越有可能拥有强大的安全性。与此同时，PANW 发现，那些在采用和实施 [DevSecOps](https://thenewstack.io/10-steps-to-simplify-your-devsecops/) 方法方面做得很好的组织往往拥有同类最佳的安全性。具体来说，紧密集成 DevSecOps 原则的组织拥有非常强大的安全态势的可能性是其他组织的七倍多。

总之，PANW 认为“将云基础设施作为企业战略重点的组织会更加成功。此外，云安全显然是业务成果的促成因素。对于世界上任何地方的任何类型的组织，安全最佳实践都是一致的，并且可以作为云成功的关键驱动因素来实施。”

当然，更好的安全性本身并不意味着在你的云上一切都会很好。“但是，控制安全性—整合工具和供应商以及使用成熟的 DevSecOps 和安全自动化策略—设定了一个基准，让开发团队能够更好地完成工作，并使组织能够成功完成云转型。”

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>