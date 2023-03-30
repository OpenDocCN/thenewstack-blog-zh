# Deepfence 监控生产中的云原生应用

> 原文：<https://thenewstack.io/deepfence-monitors-cloud-native-applications-in-production/>

近年来，云原生安全产品爆炸式增长，解决方案旨在确保网络、数据和应用程序的安全。这种繁荣在一定程度上是由警示故事推动的，如 2020 年的[太阳风崩溃](https://thenewstack.io/solarwinds-the-worlds-biggest-security-failure-and-open-sources-better-answer/)，2021 年的 [Log4j 漏洞](https://thenewstack.io/log4shell-we-are-in-so-much-trouble/)，以及对[保护软件供应链的新关注](https://thenewstack.io/the-challenges-of-securing-the-open-source-supply-chain/)。

“Logj4 为行业敲响了警钟，因为它是一个如此灾难性的漏洞，”Deepfence 的产品和社区负责人 [Owen Garrett](https://www.linkedin.com/in/owengarrett/) ，deep fence 是一家[云原生](https://thenewstack.io/category/cloud-native/) [可观察性](https://thenewstack.io/category/monitoring/)公司，他在[参加了 5 月在这里举行的](https://thenewstack.io/shift-left-where-cloud-native-computing-security-is-going/)[kube con+CloudNativeCon Europe](https://www.cncf.io/kubecon-cloudnativecon-events/?utm_content=inline-mention)的安全问题小组会议后告诉新堆栈。

“这是灾难性的，因为很容易找到易受攻击的实例。一旦你找到了它们，就很容易利用它们。”

他补充说，“我们的企业合作伙伴不得不在他们的开发团队中争分夺秒，花了一周时间试图在生产中找到 Log4j 的实例，并修补这些实例。”

## 左移位

[“左移”运动](https://thenewstack.io/shift-left-how-security-pros-should-prepare-developers-for-devsecops/)将许多工具交到了开发人员手中，以确保尽可能安全地构建应用程序。“但是一旦应用程序被部署到生产中，即使有少量的潜在漏洞，攻击者仍然可以找到利用的方法，”Garrett 说。“挑战在于通过监控应用程序如何执行操作来领先于攻击者。”

一旦应用程序投入生产，漏洞就会出现。Garrett 说，在生产中运行的应用程序的组件可能没有被扫描——在应用程序被推向生产之前，严格的应用程序构建过程可能会出现例外。

因此，他说，“所以你需要继续监控生产中那些应用的[安全性](https://thenewstack.io/category/security/)。你不能在左移项目结束时停下来。

加勒特的公司 [Deepfence](https://deepfence.io/) 使用了左移应用程序开发中嵌入的安全实践，并在应用程序的整个生命周期中持续扫描应用程序的漏洞。Deepfence 的深度数据包检测(DPI)扫描工具 [ThreatMapper](https://github.com/deepfence/ThreatMapper) ，旨在检查特定时间点的应用程序，并生成[软件物料清单(SBOM)](https://thenewstack.io/securing-the-software-supply-chain-with-a-software-bill-of-materials/) 。

“然后你看着 SBOM 说，‘这些材料中有已知的弱点吗？’”盖瑞特说我们所做的是定期回到每个应用程序，并生成 SBOM。然后我们将其与当前的漏洞列表进行比对。因此，如果明天有人在 Log4j 中发布另一个漏洞，人们会使用我们的工具。他们会发现新的漏洞，并加以匹配。"

在 KubeCon 期间，该公司宣布了 Deepfence Cloud，旨在为寻求保护其应用程序的企业减少障碍。该产品允许用户在云中运行完全托管的 ThreatStryker 控制台(ThreatStryker 是 Deepfence 的商业运行时保护解决方案)。

加勒特在宣布该平台的公司博客中写道，Deepfence Cloud 是为了帮助缓解网络安全专业人员的短缺而创建的。([根据国家网络安全教育倡议 2021 年的一份报告，全球存在 275 万安全专家的缺口](https://www.nist.gov/system/files/documents/2021/12/03/NICE%20FactSheet_Workforce%20Demand_Final_20211202.pdf)。)

## 开源作为一种公司价值观

Deepfence 于 2017 年由首席执行官 [Sandeep Lahane](https://www.linkedin.com/in/sandeep-lahane-b9520a4/) 、首席技术官 [Shyam Krishnaswamy](https://www.linkedin.com/in/shyamk/) 和首席科学家 [Swarup Kumar Sahoo](https://www.linkedin.com/in/dr-swarup-kumar-sahoo-8b981a39/) 创立。此前，Krishnaswamy 在 LiveReach Media 担任工程总监，Lahane 和 Sahoo 共同创立了 Vercept，该公司专注于内存安全，并将预防逻辑应用于 Linux 进程。

2020 年 11 月，Deepfence 宣布获得 950 万美元的 A 轮融资，由 AllegisCyber 领投，Sonae IM 和 Chiratae Ventures 参与。

加勒特说，这家初创公司的 30 名员工“非常分散”。Deepfence 的总部位于加州帕洛阿尔托，在英国诺丁汉和印度班加罗尔设有办事处，工程人员遍布世界各地。

Garrett 说，自两年前新冠肺炎疫情成立以来，远程工作的转变为这家初创公司提供了招聘机会。

“我们不再需要考虑在特定的地理区域雇佣员工，”他说。“我们通过社区开展工作。例如，如果我们看到一个人围绕我们使用的技术之一 [eBPF](https://thenewstack.io/ebpf-finds-a-home-with-a-new-foundation/) 开展了一个令人兴奋的项目，那么我们将寻求与他们合作，支持他们正在做的事情，或者作为承包商或员工为他们提供机会，帮助支持我们正在做的事情。”

2021 年初，Deepfence 发布了 [SecretScanner](https://github.com/deepfence/SecretScanner) ，定位容器镜像和文件系统中的秘密和密码；作为它的第一个开源项目。从那以后，它还向开源社区贡献了 [ThreatMapper](https://github.com/deepfence/ThreatMapper) (现在包括 secret scanner)[packet streamer](https://github.com/deepfence/PacketStreamer)，这是一个用于云原生环境的分布式 tcpdump，以及[流量计](https://github.com/deepfence/FlowMeter)，它使用[机器学习](https://thenewstack.io/category/machine-learning/)将流量和数据包分类为良性或恶意。

“开源是我们工作的核心，”加勒特说。“原因是我们坚信安全是每个人都应该受益的东西。人们利用开放的安全信息不应该有任何障碍或成本。”

## 过滤掉噪音

Garrett 说，在可观察性方面，下一个前沿是看到应用程序内部活动的能力。

正如他所说，虽然可观察性堆栈可以生成“数百万个小信号，但这些信号中没有一个会明确指向攻击。挑战是试图收集信号，收集并解释它们，告诉你是否有攻击正在发生。”

他将开发人员过滤出异常应用程序活动的最重要信号的能力比作聪明侦探的悟性。“如果你想到一部抢劫电影，总会有警察队伍中稍微古怪、不受重视的侦探第一个举起手说，‘发生了一些别人没有注意到的事情。’"

“在一个应用程序中，这是同样的挑战，”Garrett 说。“你看到这些细微的信号，你需要迅速举起手说，‘这里有点不对劲。’最大的挑战是在跨多个云环境的大型应用程序中大规模实现这一点，其中包含复杂的应用程序和大量的信号。"

解决这一挑战是 Deepfence 的一个研究重点，该公司正在致力于使用机器学习技术来过滤掉“噪声”并呈现最具预测性的信号。

“我们需要做的是减少威胁管理团队的工作量负担，”加勒特说。“所以我们只给他们信号，有很高的概率，它与攻击相关。”

他说，等到关键警报出现时，阻止或减轻攻击可能已经太晚了:“艺术是看着威胁等级升级，你会越来越确信这是某种不好的行为。”

加勒特建议，复杂的云本地安全性和可观察性环境需要许多互补的解决方案。

“安全领域有这么多不同的利基市场，没有万灵药，”他说。“这是一个成熟的企业为了保护他们的应用程序和基础设施所需要的众多技术之一。”

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>