# Pulumi 将基础设施视为具有 CrossCode 的通用代码

> 原文：<https://thenewstack.io/pulumi-takes-infrastructure-as-code-universal-with-crosscode/>

![](img/fd0dd00b200d44f5ff36be8ea8838b1d.png)

乔·达菲

[乔·达菲](https://www.linkedin.com/in/joejduffy/)一直致力于将 [Pulumi](https://www.pulumi.com/) 打造成首屈一指的云工程平台，随着以 Pulumi [基础设施为代码(IaC)](https://thenewstack.io/infrastructure-as-code-increase-security-scale-development/) universal)的新功能的最新发布，他已经成功实现了这一目标。

Pulumi 的联合创始人兼首席执行官 Duffy 创办了这家公司，专注于为基础设施团队、开发人员和安全工程师提供软件工程流程，以更快更好地交付现代云应用。

![](img/9f356d098daa6dbd509ac2c61ad2c93e.png)

埃里克·鲁德尔

达菲本人是前微软 DevDiv 大佬，他与另一位微软开发者部门传奇人物[埃里克·鲁德尔](https://www.linkedin.com/in/ericrudder/)(前微软首席技术官兼执行副总裁，现任 Pulumi 执行董事长)和其他人一起在 2017 年创立了 Pulumi。他们还选择了另一位前微软软件工程天才卢克·霍班担任首席技术官。

## 交叉代码是关键

使 Pulumi IaC 通用化的背后是该公司在上周的虚拟会议上推出的 Pulumi CrossCode 翻译技术。Pulumi CrossCode 是 Pulumi 基础设施的通用翻译层，作为代码引擎，使开发和运营团队能够以最流行的编程语言构建基础设施；将任何基础设施转换为代码格式，包括 Terraform、CloudFormation、Azure Resource Manager、Kubernetes 配置，转换为 Pulumi 并作为代码系统与由其他基础设施管理的所有现有基础设施进行互操作。

事实上，正是 CrossCode 使得 Pulumi 能够为 Java 和 YAML 提供新的支持。Pulumi 现在支持任何 Java 虚拟机(JVM)语言(Java、Scala、Clojure)，增加了对。NET (C#、F#、PowerShell)、Node.js (JavaScript、TypeScript)、Go、Python。Pulumi 还宣布了对 YAML 的支持，提供了一种简单的声明式格式，用于以代码形式生产或消费基础设施，实现了简单的用例并提高了可工具性。

VirtusLab 首席技术官 Pawel Dolega 表示，VirtusLab 将其 JVM 生态系统经验应用于 Pulumi，以帮助将对 Java 和其他 JVM 语言的支持引入 Pulumi 开源项目，现在又引入了主线产品。

此外，通过对 Java 的新支持，Pulumi 将其平台扩展到了数百万 Java 开发人员。根据 2021 年 [StackOverflow 开发者调查](https://insights.stackoverflow.com/survey/2021#most-popular-technologies-language)，Java 目前被超过 35%的开发者使用。

“我们支持 Java 作为 Pulumi 生态系统中的一种新语言。而且不仅仅是 Java 语言，而是整个 Java 生态系统，”Duffy 告诉 New Stack。“所以这包括任何 JVM 语言，包括 Scala、Clojure、Groovy 和 Kotlin——我们已经看到人们对 kot Lin 很感兴趣。我们支持所有的工具、所有的包管理器，比如 Maven、所有的测试框架……我们所有的 80 多种不同的云集成都适用于 Java。”

CrossCode 由 Pulumi 的开源代码生成、程序生成、schema 和 packages 软件组成。

达菲说，本质上，“CrossCode 基本上是一个语言和云无关的类型系统，使你能够向这些云提供商(我们有很多)投射任何可以同时被模式化为所有这些语言的东西。“这就是我们提出 Java 的第一天，我们可以支持整个 Pulumi 平台的原因。这都要感谢 CrossCode。CrossCode 是一个库，你可以依赖它。”

随着时间的推移，Pulumi 将会播种一个依赖于这项技术的跨语言工具的生态系统。

## 秘密武器

Duffy 说，CrossCode 多语言技术实际上是 Pulumi 如何工作的“秘方”。

“CrossCode 在不同语言之间翻译相同的基础设施和策略构建块。企业管理协会(EMA)的分析师[托尔斯滕·沃尔克](https://www.linkedin.com/in/torstenvolk/)说:“这是不同语言之间一致的应用程序堆栈的基础，也为 YAML 提供了一座‘桥梁’。”。“让 Java 人员、Python 人员和 JavaScript 人员对 AWS、Azure、GCP、Kubernetes 等的基础设施对象进行一致的配置、审计和治理。在一个应用堆栈包含数十个(通常是特定于云的)层的世界里，这是一件大事。CrossCode 在语言之间提供了一致的控制，允许开发人员编写应用程序和基础设施，使它们能够以最佳方式协同工作，而不会产生无法控制的管理噩梦。

## Microsoft Connection

![](img/9277c2bc7798f10d46f9cc3257a01f18.png)

从左到右:卢克·霍班、埃里克·鲁德尔、乔·达菲

达菲和鲁德尔在微软工作时，都致力于组件对象模型(COM)和公共语言运行时(CLR)的研究。COM 是微软旧的软件组件二进制接口标准，创建该标准是为了在大量编程语言中实现进程间通信对象的创建。CLR 是的虚拟机组件。NET 框架。它有助于设计跨语言交互对象的组件和应用程序。

“COM 和 CLR 基本上是关于跨不同环境的可移植性和操作，所以交叉代码翻译是相关的，尽管考虑到 Pulumi 与微软的相对规模，在根本上是不同的规模，”RedMonk 的分析师 [Stephen O'Grady](https://www.linkedin.com/in/sogrady/) 说。

尽管如此，共享的历史还是派上了用场。

“显然，我们与微软有着共同的历史。在我早期，我从事 COM 的工作，”达菲说。“COM 是一个多语言运行时，与我们在这里用 CrossCode 构建的东西有很多相似之处。显然，我从事公共语言运行时的工作，这方面也有相似之处。在我们的职业生涯中，Eric 和我都曾多次处理过这种运行时。我们在 Pulumi 的工作中吸取了很多经验教训。

Duffy 和 company 通过分叉 [V8](https://v8.dev/) /Node.js 运行时启动了 Pulumi。很快，他们决定要超越 JavaScript 来支持其他语言，他们知道他们最终需要建立一个多语言运行时，但不确定它会采取什么形式。然后大约两年前，该公司开始认真研究将成为 CrossCode 的东西——允许需要多语言支持的关键客户试用并帮助调整它。

达菲说:“我很感激我们有 CLR 和 COM 的经验可以借鉴。

就这一点而言，CrossCode 的关键思想类似于 COM，但上下文是不同的。

“交叉代码层使 Pulumi 的 [CrossGuard](https://www.pulumi.com/docs/guides/crossguard/) 策略能够作为代码平台，在 Python、Java、JavaScript 和其他支持的语言之间监控和执行相同的合规包，”Volk 告诉新的堆栈。“这使您能够对一个通用的合规性服务进行更改，然后该服务将跨语言一致地实施您的特定控制集。这允许您用 Java、Python 等语言声明一组成功构建应用程序所必须满足的要求。基于这些声明性要求，您可以提供自动补救、审批工作流等。”

## 没有 YAML 区？

与此同时，对 YAML 的新支持，Pulumi 实现了一种更简单的行业标准标记格式，用于将基础设施表达为代码，该公司表示，这将继续利用其多语言生态系统。

“很多人认为普鲁米是‘无 YAML 区’之类的，但 L 代表语言，对吗？”他说。“我们很高兴欢迎各种语言加入这个平台，但我们真的了解 YAML 的重要性。”

## 现代语言支持

为了构建其区块链平台即服务， [SettleMint](https://www.settlemint.com/) 需要一个现代化的基础设施作为代码平台，可以满足多种云、区块链协议和分布式架构的需求，[公司首席技术官兼创始人罗德里克·范德维尔](https://www.linkedin.com/in/roderik/?originalSubdomain=be)说。

“Pulumi 对现代语言的支持及其编程 API 接口是一个独特而强大的组合，使我们能够为 SettleMint 平台动态自动化基础设施供应，”他说。

## 新的包、组件

Pulumi 还增加了 30 个新包，包括支持 [Oracle](https://developer.oracle.com/?utm_content=inline-mention) Cloud、Databricks 和 EventStore，增加了对 [Amazon Web Services](https://aws.amazon.com/?utm_content=inline-mention) 、微软 Azure、谷歌云、Kubernetes、Auth0、CloudFlare、 [Confluent](https://www.confluent.io/?utm_content=inline-mention) Cloud、Datadog、DigitalOcean、Docker、GitHub、Kong、 [MinIO](https://min.io/?utm_content=inline-mention) 、 [MongoDB](https://www.mongodb.com/cloud/atlas/?utm_content=inline-mention) Atlas、 [PagerDuty](https://www.pagerduty.com/?utm_content=inline-mention) 、[雪花](https://www.snowflake.com/?utm_content=inline-mention)。

此外，新组件包括对容器应用程序、Kubernetes 集群、无服务器应用程序等的现成支持。一个新的 [AWS 云开发工具包(CDK)](https://aws.amazon.com/cdk/) 适配器允许从 Pulumi 使用任何 CDK 包。

RedMonk 的分析师 KellyAnn Fitzpatrick 说:“通过这些新功能，Pulumi 努力满足各种各样的 IaC 实践者，无论他们是喜欢 Java 等编程语言的开发人员还是更熟悉 YAML 的操作员。“随着基础设施设置变得越来越多样和复杂，组织努力为提供和维护基础设施的团队配备人员和技能，Pulumi 使其用户能够更轻松地利用现有的技能和专业知识。考虑到 Java 与企业的历史渊源，增加对 Java 编程语言的支持对企业尤为重要。”

该公司表示，所有这些新功能都与 Pulumi 云工程平台集成，包括可重复使用的多语言组件、秘密管理、CI/CD 集成、策略即代码和 Pulumi 注册表。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>