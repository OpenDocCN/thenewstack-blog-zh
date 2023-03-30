# AWS 和赛门铁克都重新定义了云的“单一控制台”

> 原文：<https://thenewstack.io/aws-and-symantec-each-redefine-the-single-pane-of-glass-for-the-cloud/>

[Twistlock](https://www.paloaltonetworks.com/prisma/cloud) 赞助了这篇帖子。

一般企业努力的规模往往会鼓励软件蔓延，并且经常需要通过“单一窗口”来查看和管理所有孤立的软件，从而实现统一。这场斗争在上个月亚马逊以安全为重点的 [AWS re:Inforce](https://reinforce.awsevents.com/) 会议上得到了展示，亚马逊和赛门铁克都为此发布了新产品。

亚马逊[率先将](https://aws.amazon.com/blogs/aws/aws-security-hub-now-generally-available/)其 [AWS 安全中心](https://aws.amazon.com/security-hub/)推向全面上市，为 AWS 合作伙伴和用户提供一个中央仪表盘，以汇总来自各种系统的安全发现和补救途径，并实现自动化合规性检查，首先是[互联网安全中心(CIS) AWS 基础基准](https://www.cisecurity.org/benchmark/amazon_web_services/)。在他的开幕主题演讲中，AWS 首席信息安全官 Stephen Schmidt 总结了这项新的服务。

“有了 Security Hub，您现在可以在一个地方汇总、组织和优先排序您的安全警报、您从多个 AWS 服务(如 Guard Duty、Inspector 或 Amazon Macy)以及 AWS 合作伙伴解决方案中发现的问题，”施密特说。“您的调查结果会直观地汇总在一个集成的仪表盘上，带有可操作的图形和表格，有助于您在正确的时间将调查工作集中在正确的地点。这里的要点是，如果您使用合作伙伴集成，您不仅可以获得警报，还可以在警报发生后向安全环境采取行动。采取行动总是更重要。”

AWS Marketplace 副总裁戴夫·麦肯(Dave McCann)在接受新堆栈采访时表示，虽然他认为安全中心不仅仅是一个单一的玻璃面板，但它确实为单个企业经常使用的各种服务提供了一个单一的可见点——所有这些都是由一种叫做[亚马逊安全发现格式](https://docs.aws.amazon.com/securityhub/latest/userguide/securityhub-findings-format.html)的东西实现的。

“我们了解到，在大公司中，您可能有十几种不同的安全工具。我们创造了亚马逊安全发现的概念，而不是必须去十几个不同的控制台了解发生了什么。这是一种元数据格式。McCann 说:“通常在大公司中，一个部门使用赛门铁克，另一个部门使用趋势科技，这个部门使用 Palo Alto Networks，大厅里的某个人使用 CrowdStrike，他们都有自己的搜索格式。“我们已经标准化了调查结果格式，并鼓励 20 多家合作伙伴采用这种格式，因此现在您可以通过一个控制台，即安全中心，查看所有的安全调查结果。这是一个集中的地方，可以从内部查看您的所有安全工具。”

Security Hub 目前提供来自 [AWS Guard Duty](https://aws.amazon.com/guardduty/) 、 [Amazon Inspector](https://aws.amazon.com/inspector/) 、 [Amazon Macie](https://aws.amazon.com/macie/) 以及来自 30 家 AWS 合作伙伴安全解决方案的发现，但任何人都可以使用 [Security Hub API](https://docs.aws.amazon.com/securityhub/1.0/APIReference/Welcome.html) 来创建自己的集成。除了提供一个中心点来查看调查结果，Security Hub 还提供了一种使用 [CloudWatch](https://aws.amazon.com/cloudwatch/) 规则和事件来设置自动补救的方法，这些规则和事件可以通过[亚马逊简单通知服务(SNS)](https://aws.amazon.com/sns/) 主题、[亚马逊简单队列服务(SQS)](https://aws.amazon.com/sqs/) 队列和 [AWS Lambda](https://aws.amazon.com/lambda/) 功能来响应。

## 多云的单一窗口

作为亚马逊的合作伙伴，赛门铁克发布的核心是赛门铁克的[云工作负载保护(CWP)](https://www.symantec.com/products/cloud-workload-protection) 和[亚马逊守卫职责](https://aws.amazon.com/guardduty/)之间的集成，为 AWS 工作负载和存储提供自动化补救和增强的威胁情报，以及为亚马逊简单存储服务(亚马逊 S3)桶提供 DLP 保护。赛门铁克也是参与安全中心集成的 30 家合作伙伴之一。该公司还推出了[集成网络防御平台](https://www.symantec.com/theme/integrated-cyber-defense)，该平台提供了自己的集中仪表板，用于查看和补救。

当然，鉴于消息来自 AWS re:Invent，主要焦点放在 Amazon 拥有交互并让其安全中心成为中央安全仪表板上。然而，在我们当前的多云世界中，可能会有一个合作伙伴，而不是亚马逊、谷歌、微软或其他公司，来提供这种可见性和补救的中心点。在围绕 Security Hub 的所有讨论中，没有提到与其他公共云的集成。然而，在与赛门铁克业务发展副总裁 Peter Doggart 的采访中，有人指出，集成网络防御平台将与所有公共云一起工作。

“在过去的三到四年里，我们一直非常关注构建云一代。许多年前，我们做了一个大的转变，以确保我们所有的解决方案都适合公司、开发人员以及任何可能使用和构建云的人，并确保云之旅是安全的，”Doggart 说。“我们提出了综合网络防御的概念。我们真的相信集成的网络防御是最好的防御，不仅是我们自己的工具协同工作，还有你在这里看到的一切(在 re:Inforce ),还有亚马逊网络服务、Azure 和谷歌云。”

道格特描绘了一幅类似的软件蔓延的画面，将责任归咎于安全行业倾向于创建专注异常的公司。

“在过去的十几年里，(安全部门)创造了所有这些一次性工具，这些所谓的功能公司在一件事情上做得非常非常好，但在集成方面做得并不好。客户购买了这些工具集，我们最终拥有了 150 个。这是一种疯狂的复杂，”道格特说。“我们试图做的是确保我们能够将所有这些部分整合在一起。我们现在可以在两家公司之间用我们都能理解的日常简单语言进行交流，而不必在单个产品和单个产品之间建立联系，这种联系会产生可怕的网状效应。”

集成的网络防御平台使安全团队能够深入研究部署在多个云中的工作负载等，不仅提供可见性，还能够消除任何地方的问题工作负载。

“20 年来，我们一直在开发我们的终端技术。因此，我们正在应用我们在视觉端点上使用的相同技术，并将其应用于多个工作负载。因此，坐在主机上，但我们本质上正在做一些我们可以理解的事情，看到所有的容器和服务旋转起来，跟踪所有的 id 和标签，看到数据，我们可以强化环境，”道格特说。“我们已经将多年来获得的所有技术和知识应用到了云计算中。我们现在可以为您的所有工作负载提供一个中央控制台，无论是在 AWS、Azure、Google Cloud、内部部署还是虚拟专用网络上，都没有关系。我们应用相同级别的策略，并对所有内容应用类似的保护补救措施。”

图片由来自 Pixabay 的 Bernd Hildebrandt 提供。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>