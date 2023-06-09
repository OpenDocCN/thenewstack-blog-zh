# 混沌工程超越“打破东西”来突出商业价值

> 原文：<https://thenewstack.io/chaos-engineering-business-value/>

10 年前，当网飞用其[混沌猴子](https://netflix.github.io/chaosmonkey/)工具首次开创混沌工程时，流行的想法是随机关闭系统的部分，看看整个系统是否会瘫痪。

从那时起，混沌工程已经发展成为一种更成熟的实践，供应商和企业正在更广泛地采用它，不管他们是否称之为混沌工程。今天的最佳实践包括关于测试设计的初始战略规划、将从这些测试中获得的知识转化为可操作计划的具体计划，以及开发和运营团队之间的沟通和协作。因此，公司开始从混沌工程中看到真正的商业价值。

“早在 2011 年，混沌工程只是随机关闭实例，”诺拉·琼斯说，[帮助创建了网飞大学的混沌工程科学学科，](https://twitter.com/nora_js)[写了关于这个主题的书](https://www.amazon.com/Chaos-Engineering-System-Resiliency-Practice/dp/1492043869)。她现在是事件分析平台公司 [Jeli](https://www.jeli.io/) 的创始人兼 CEO。

她说，事实上，这就是仍有多少人在考虑混沌工程。

“这是向人们介绍它的一种简单方式，”琼斯补充道。“但如果你这样想，它就不会在组织中存在，也不会带来投资回报。”

因此，举例来说，许多组织将花费时间和金钱来建立混沌工程工具，这将允许他们打开和关闭系统。这是一个有趣的技术挑战，她说，而且不容易做到。它耗费时间和金钱，并耗尽工程资源。

但是许多公司都过不了这个阶段。事实上，与在混沌工程中发现价值相比，构建工具是容易的部分。

琼斯说:“难的是思考我们应该在哪里进行实验，为什么要这样做。”。“如果我们发现一些不好的东西，我们需要修复它吗？你必须在你的其他功能需求和业务优先级中优先考虑它。你怎么知道你所做的事情是否会在未来重演？”

## 对已经损坏的东西进行优先排序

如果做得好，混沌工程可以帮助公司更好地理解其系统的实际工作方式。

事实上，一些供应商正在脱离术语“混乱工程”,更少地关注打破事物的部分，而更多地关注等式中的规划和补救部分。

琼斯创立的 Jeli 公司自称是一个“事件分析平台”。它不是帮助公司打破东西，而是专注于东西自己打破的事件，然后找出发生了什么以及如何防止它再次发生。Jeli 认为 job site 和 3D 开发平台 Unity 是其客户中的佼佼者。

对于公司来说，进入混沌工程是一种更容易的方式，因为他们从已经出错的事情开始。“他们发现他们的组织是如何真正运作的，而不是他们认为它是如何运作的，”她说。

进行这种初步分析也有助于公司掌握协作，确定补救措施的优先顺序，甚至确定预算的优先顺序。

“你不能不先研究一下就进行混沌工程，”她说。

该领域的其他供应商对此类测试和补救提出了不同的术语。例如，Verica 称之为“持续验证”

但琼斯承认，这个领域的参与者并不多。大多数情况下，公司使用开源工具，或者依赖内置于云平台的功能。[例如，亚马逊网络服务](https://aws.amazon.com/?utm_content=inline-mention)有其 AWS [故障注入模拟器](https://aws.amazon.com/fis/)，微软提供 Azure [故障分析服务](https://docs.microsoft.com/en-us/azure/service-fabric/service-fabric-testability-overview)。

一家有趣的新供应商 Auxon 自称是一家“持续验证和确认”公司，正在将混沌工程原理应用于无人驾驶汽车和其他自主系统，如手术机器人。

“这个领域现在真的刚刚起步，”琼斯说。

## 混沌工程作为一个特征

除了 AWS 和 Azure 将混沌工程作为其云产品的一部分，其他供应商也将混沌工程工具作为其服务组合的一部分。

例如，[launch darky](https://launchdarkly.com/?utm_content=inline-mention)是一个特性工程平台，在混沌工程实践中是一个有用的工具。它允许部署软件更新的公司以精细的方式发布它们，从一小组用户开始，允许团队在出现问题时快速回滚更新。

LaunchDarkly 的客户中有 22 家是财富 100 强企业，包括 NBC、GoDaddy、丰田、Meetup、阿迪达斯和 IBM。

LaunchDarkly 的转型倡导者 Heidi Waterhouse 指出，尽管混沌工程越来越受欢迎，但它也有风险，尤其是在生产环境中进行测试时。

“人们说，‘我不想因为产量下降而赔钱，’”她说。“但你已经在生产中测试了——只是你没有意识到。”

现实世界的混沌工程一直在发生。事物会破碎，而且是以不受控制的方式破碎——这可能会带来灾难性的后果。

“如果你想一想，勒索软件是别人在未经同意的情况下在你的基础设施上进行混沌工程实验，”沃特豪斯说。“我们为您提供了在生产中安全地进行这种测试的工具，以一种立即可逆和可审计的方式，因此您可以确保它不会那么可怕。”

Forrester Consulting 最近代表 LaunchDarkly 做了一项关于其平台的总体经济影响的[调查](https://learn.launchdarkly.com/total-economic-impact/)，特别关注为客户子集打开或关闭单个软件功能的能力。该平台的投资回报率为 245%，这是由于降低了生产前环境的成本，节省了开发人员的工作效率，并避免了维护自主开发的功能管理系统的成本。

“我认为混沌工程是软件交付周期结束时性能测试的一种非常积极的形式，”Intellyx 的首席分析师 Jason English 说。

行业正在经历一个“左移”的过程，更多的测试工作发生在开发过程的开始。但也有一种“向右转移”，他说:“开发周期变得如此之短，以至于测试也向右转移——进入生产。”

English 说,“混沌工程”的有效性正在帮助它从像网飞这样的网络本土公司起步，扩展到更成熟的企业。

“你会看到较大的公司，甚至是受到高度监管的公司，意识到这是整体合规检查的一部分，”他说。

越来越多的供应商以各种名义提供混沌工程，将来可能会有更多的供应商这样做。

“任何进行非功能性测试的大型或小型测试公司都默认在进行某种形式的混沌工程，尽管他们可能不会这样称呼，”他说。

例如，NS1 是一家应用流量管理公司，它有一个对 DNS 服务器和网络进行压力测试的工具。该公司在 2019 年将其作为一个名为[喷火器](https://github.com/DNS-OARC/flamethrower)的开源项目发布。

[NS1](https://www.ns1.com/?utm_content=inline-mention) 的研究副总裁 [Shannon Weyrick](https://www.linkedin.com/in/weyrick/) 说:“现有的解决方案没有我们需要的功能，这限制了我们进行现实测试的能力。

她说，该工具允许公司模拟现实的交通模式，并了解实际生产环境中应用程序和基础设施的潜在变化的影响。它还可以用来模拟组织在 DDoS 攻击或故障转移压力测试系统期间可能看到的流量激增，使其成为战争游戏和混沌工程的理想工具

## 混沌工程的业务影响

混沌工程领域的另一个主要供应商是 [Gremlin](https://www.gremlin.com/) ，其客户包括 Charter Communications、摩根大通、Mailchimp、Expedia、Target 和沃尔玛。

Gremlin 系统的工作方式是，Gremlin 代理安装在云服务器或本地服务器上，它们可以根据命令创建受控干扰。

例如，代理可以“黑掉”一项服务，使它看起来对公司基础设施的其余部分完全不可见。或者他们可以模拟延迟问题、数据包丢失和数据包损坏—各种各样的问题。

Gremlin 的高级混沌工程师 Ana Margarita Medina 说:“这将有助于您发现系统中的弱点，以便您可以优先考虑它们，开始解决它们，并使系统和应用程序更加可靠。

但她强调说，这不仅仅是随机开关。

“混沌工程是深思熟虑和有计划的，”她说。“你用了科学方法。你思考你在之前的测试中看到的弱点，或者你思考你的心理模型，看看它的脆弱点。如果我在数据库中引入延迟，会出现缓存错误吗？”

测试运行后，是时候回去评估结果，改进系统和应用程序，并重新运行实验。

“你从很小的地方开始实验，”麦地那说。“不要一开始就攻击整个基础设施。用一个主机做。然后，您可以在两台主机上运行它，继续这样做，并扩展到整个组织。”

Gremlin 的宣传主管 Jason Yee 说，公司不必从生产环境开始。他说，它可以从桌面事故响应演习开始。

“最终，你必须进行桌面练习，并在一个阶段或开发环境中运行它，”他说。"最终，在生产中."

4 月，Gremlin 通过添加服务发现工具扩展了其产品，该工具可以帮助公司识别在其环境中运行的所有服务和微服务，并识别它们如何相互关联。

## 行业采用

今年 1 月，Gremlin 发布了一项调查的结果，该调查追踪混沌工程如何帮助公司提高正常运行时间的百分比。

在服务可用性低于 99%的公司中，有一半从未进行过混沌工程实验。在报告服务可用性为 99%到 99.9%的公司中，64%的公司至少运行过一次混沌工程实验。

在报告服务可用性高于 99.9%的公司中，74%的公司至少进行过一次实验，23%的公司每周甚至每天都进行实验。

大企业认真对待混沌工程并不奇怪。

但这种情况正在全面发生:

*   根据 Gartner [的一份报告，到 2023 年，40%的组织将实施混沌工程实践作为 DevOps 计划的一部分，将计划外停机时间减少 20%。](https://www.gartner.com/smarterwithgartner/the-io-leaders-guide-to-chaos-engineering/)
*   LogicMonitor 在二月份发布的一份[报告](https://www.globenewswire.com/news-release/2021/02/02/2167880/0/en/New-LogicMonitor-Study-Reveals-that-51-of-Enterprises-Experienced-an-Increase-in-IT-Downtime-During-Pandemic.html)发现，97%的全球 IT 领导者称他们经历过 IT 限电，94%的人称他们经历过断电。接受调查的超过一半的 IT 领导者表示，自疫情开始以来，他们发现 IT 停机时间有所增加。
*   根据 Zerto 赞助的 IDC 四月份发布的一份报告，停机的成本从每小时几千美元到几十万美元不等。在过去的一年中，公司的计划外停机时间平均超过 29 小时。

## 混沌工程也测试人

混沌工程不仅仅是按下一个按钮，让系统的一个随机部分去测试弹性。

O'Reilly Media 负责新兴技术内容的副总裁 Mike Loukides 说，这也考验了运营基础设施的人的弹性。

“你不可能建立不会失败的系统，”他说。“那是不可能的。但是你可以建立知道如何处理失败的团队。要做到这一点，就要给他们实践的机会。”

测试公司 [Eurofins](https://www.eurofins.com/) 的高级安全顾问 Nuno Povoa 说，混沌工程也让团队更深入地了解系统如何工作，并让公司更加相信技术团队拥有足够的知识来有效地处理问题。

他说，这不仅有助于帮助公司处理网络中断等运营问题，也有助于网络安全。

“它允许公司使用这些工具来调整他们的系统，所以如果这些攻击真的发生了，他们可以看到它看起来像什么，”Povoa 说。

他说，它可以让团队在可控的环境下体验网络安全灾难，“而不是第一次被恶意软件入侵，并试图弄清楚需要做什么，何时做，与谁一起做，并到达分散的信息孤岛来处理事件。”

例如，琼斯回忆起她在网飞时代的一个插曲。她作为网站可靠性工程师进行的早期测试之一是关闭该公司的书签服务。

“如果你看了网飞的一个节目，但没有看完，你可以点击暂停，几天后再回来，它会从你停下的地方继续播放。这叫做书签服务，”琼斯解释道。

她说，这被认为是一项非关键服务，所以尝试混沌工程似乎是安全的。

“但我们不在书签队，”她说。“当我们把它拿下来的时候，它并没有让网飞停机，但是我们看到很多客户在播放他们的视频时遇到了很多问题。”

这是因为当书签服务关闭时，网飞自动默认认为客户没有观看任何视频，并不断将它们发送回起点。

“这给用户带来了非常糟糕的体验，”她说。

然后混沌工程团队将其测试结果交给书签团队。“他们可能会做些什么，也可能不会。这不是我们能控制的，”琼斯说。

撇开混沌工程团队成员的沮丧不谈，不明确的后续行动意味着公司没有从他们的混沌实验中获得最大的商业价值。

那次经历告诉琼斯，混沌工程需要更多关于测试哪些服务的战略思考，更多部门间的合作，以及测试完成后如何处理测试结果的计划。

# 资源

## 开源混沌工程工具集

**[猿猴军](https://github.com/Netflix/SimianArmy)**

网飞混沌猴工具的最新进化

**[混沌工程工具包](http://chaostoolkit.org/)**

运行并验证实验

**[格拉法纳](https://grafana.com/)**

可观测平台

**[瓦兹蒙基](https://github.com/smarx/WazMonkey)**

重启随机 Azure 实例

## 供应商

亚马逊的 AWS [故障注入模拟器](https://aws.amazon.com/fis/)

微软的 Azure [故障分析服务](https://docs.microsoft.com/en-us/azure/service-fabric/service-fabric-testability-overview)

**[小妖精](https://www.gremlin.com/)**

混沌工程平台

**[稳定位](https://www.steadybit.com/chaos-engineering)**

混沌工程平台

**[黑暗发射](https://launchdarkly.com/)**

特征工程平台

**[威瑞卡](https://www.verica.io/)**

持续验证平台

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>