# 需要内部开发者平台吗？

> 原文：<https://thenewstack.io/do-you-need-an-internal-developer-platform/>

计算趋势经常看起来像一个“跟随领导者”的游戏。如果谷歌、微软或另一家大型科技公司做到了，我们不也应该这样做吗？

这种逻辑有一定的规律性。网站可靠性工程(SRE)源自谷歌实践，例如一本同名的书。SRE 的角色随后在各行各业的技术团队中扩散开来。

只要我们在可靠性的话题，混沌工程开始作为一个内部工具和实践在网飞；现在是一套[成文的原则](https://principlesofchaos.org/)、[开源工具](https://github.com/Netflix/chaosmonkey)和商业工具[在越来越广的范围](https://thenewstack.io/chaos-engineering-business-value/)的企业中使用。

这种模式在内部开发平台(IDPs)中再次出现。最初是网络巨头和其他大型公司的权限，IDPs 为开发人员提供了丰富的自助服务能力，以快速提供他们需要的各种环境和其他资源，现在正在吸引更广泛的软件团队。

这不仅仅是一种跟风的趋势。相反，IDP 是云和云原生生态系统大规模增长的自然副产品，以及相应的 [DevOps](https://thenewstack.io/category/devops/) 和 [DevSecOps](https://thenewstack.io/ebooks/devsecops/best-of-devsecops-trends-in-cloud-native-security-practices/) 、 [CI/CD 管道](https://thenewstack.io/category/ci-cd/)以及其他现代工具和学科的兴起。 [Puppet](https://puppet.com/?utm_content=inline-mention) 的 [2020 年 DevOps 报告](https://puppet.com/resources/report/2020-state-of-devops-report)甚至将使用自助服务平台列为高绩效团队的共同特征。

“现代开发需要来自许多不同领域的信息，如质量、卫生、安全、不仅是你的第一方代码的许可，还有第三方代码的许可，”Sonatype 的首席技术官 Brian Fox 告诉新的堆栈。

“唯一明智的方法是通过一种系统化的方法，将适当的工具集成到开发过程中，从而使项目更加一致。”

## 减少周转时间

对于越来越多的组织来说，这种系统化的方法就是内部开发平台。国内流离失所者有各种其他名称，如自助服务平台和 Kubernetes 平台。不管怎么说，它们本质上是将一个组织的开发团队需要的所有东西整合到一个地方

如果你正在构建容器化的应用，猜猜开发者会在哪里找到被批准的容器注册？在国内流离失所者。新环境也是如此:需要新的测试或沙盒机器吗？开发人员可以很快为自己做好准备——没有几天或几周的准备时间，或者在一些特别痛苦的遗留过程中，几个月。平台方法在定义的参数内实现了这一点和更多，这些参数通常是根据开发运维、[安全](https://thenewstack.io/category/security/)和其他领域专家的输入来设置的。

“把你的开发管道想成一个平台是你如何实现大规模分析的一致性和完整性，”Fox 说。

凯捷工程创新总监 Raghu Kishore Vempati 告诉我们，IDP 通常在“迫切需要提高开发人员生产力和自主权的地方实施，从而大幅缩短服务和产品新功能的周转时间”。

鉴于当今软件开发的狂热步伐，这一主张似乎很有卖点。但是 IDP 不一定适合每个团队或组织。就启动和运行以及平台的持续开发和维护而言，可能会有很大的开销。因此，他们自然倾向于大型组织，尤其是那些具有复杂、异构环境的组织。

许多成本效益分析可以归结为简单的术语:IDP 将允许我们明天做什么，而我们今天不能做什么？如果你的答案比 IDP 的初始和持续成本更有价值，那么你应该认真考虑。

就开销而言，首先是平台本身:你必须构建它。

虽然存在争议，但经典的 IT 构建与购买并不一定适用于此:纯粹主义者可能会告诉您,“真正的”IDP 是在内部从头构建的，即使它可能在其构建中使用了关键组件，如开源的 Kubernetes。商业 PaaS 就是这样，对许多团队来说是一个可行的选择，但是现成的，它本身不是一个 IDP。

搭建自己的平台需要一个平台工程团队。即使在最小的规模上，您也需要从一个平台工程师开始。IDP 模型通常需要一个独立的平台团队，其中包括多名工程师，与您的开发人员或 DevOps 团队截然不同，正如最近在新堆栈中描述的 [Weaveworks](https://www.weave.works/?utm_content=inline-mention) 首席运营官史蒂夫·乔治[。这需要对人的持续投资，而不仅仅是对技术的投资。](https://thenewstack.io/what-a-self-service-developer-platform-is-and-why-it-matters/)

成本效益分析应确定您的组织是否适合 IDP。为此，问这六个问题。你回答“是的”、“这就是我们”或类似的问题越多，你就越有可能找到投资回报。

## 1.您的基础架构准备好了吗？

境内流离失所者不仅仅是一个成本效益问题。这也是一个“本末倒置”的问题:如果您运行的基础设施和流程破旧不堪，急需更新，那么您可能还没有准备好应对 IDP 的冲击。

Iterate.ai 首席技术官 [Brian Sathianathan](https://www.linkedin.com/in/briansathianathan) 表示，基础设施问题是组织在评估他们是否会从 IDP 中受益时应该从哪里开始

“第一:你的基础设施现代化了吗？您正在使用云堆栈吗？”Sathianathan 问道。“如果您的部署管道中有重要的遗留部分，那么您将需要做更多的工作才能达到 IDP 的起点。”

## 2.你有很多开发者吗？

这是一个有点沉重的问题，但却是一个重要的问题:你的组织有很多开发人员吗？含义:如此之多，以至于你有多个不同的开发人员或 DevOps 团队，每个团队都有他们自己不同的需求、代码库、基础设施需求等等？

Sathianathan 说，当“您的组织中有足够大的开发人员基础来处理不同的需求和不同的语言、代码库和基础设施需求时，IDPs 是有意义的。”

你不需要达到什么神奇的门槛。但是，随着组织中开发人员和/或开发团队数量的增长，他们从 IDP 中受益的可能性通常也会增加。一个单一的、相对较小的团队，可以标准化相同的语言、工具等等，可能不会获得好处。

## 3.您的构建-部署流程运行得如何？

对于一个已经在大部分气缸上点火的团队来说，IDP 应该是一个进化阶段。在 DevOps 或 DevSecOps 上下文中，这有时被称为成熟度。

Sathianathan 说，如果你的软件交付管道中有许多已知的，也可能是未知的瓶颈，那么你最好先缓解和改善这些瓶颈。IDP 可以在速度和部署频率方面增加一个数量级，但它本身无法解决中断的流程或文化问题。

## 4.你的开发团队有多少自主权？

开发人员自主权是 IDP 方法最常被提及的好处之一。自助服务的本质是促进和鼓励自主性，通过一些适当的防护来保持事情可靠、安全地运行，并且不会超出预算。

Sathianathan 说:“你需要很好地意识到自助服务是否会带来数量级的好处，或者分数级的好处，并了解好处是否会超过成本。”

这个问题的另一个版本是:我们希望我们的开发团队有多少自主权？如果答案不是“很多！”或者接近它，考虑一下你为什么考虑一个 IDP。他们非常适合 DevOps 团队的原因之一是自治所需的信任应该已经到位。

## 5.您的运营治理工作进展如何？

这是另一个本末倒置的问题:如果你对这个问题的回答是“我们的什么？”那你可能还没准备好接受 IDP。

自助服务并不是“随心所欲”的同义词护栏必须来自某个地方，如果您当前的 IT 治理模型类似于蛮荒西部的淘金城，那么您可能想要暂停 IDP 项目。

“是集中模式吗？”Sathianathan 问道。“如果没有一个集中的模型，企业的不同部分在做不同的事情，那么在实施 IDP 战略之前，绝对需要解决治理问题。”

## 6.您的 SLA 有多重要？

好吧，大多数组织可能会回答，“他们是一个大问题”。但是，关于服务级别协议(SLA)的这个问题，Vempati 特指高可用性和弹性是底线问题或类似高风险的业务，例如在公共卫生或安全环境中。

如果速度也是一个基本问题，那种秒至关重要的问题，那么 IDP 可能也是有益的。Vempati 分享了这个问题更具体版本的例子:

*   我们的公司是否向内部或外部客户提供需要快速周转时间的服务？
*   我们的公司是否是多个大型组织的合作伙伴，这些组织交付特性和解决错误的周转时间肯定比我们的短得多？
*   是否有要求高可用性和弹性的 SLA？

Vempati 说，你对这些问题的肯定回答越多，“对一个国内流离失所者来说，就越有价值，越有说服力。”

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>