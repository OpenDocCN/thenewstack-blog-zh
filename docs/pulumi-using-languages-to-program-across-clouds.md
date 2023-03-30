# Pulumi:使用语言跨云编程

> 原文：<https://thenewstack.io/pulumi-using-languages-to-program-across-clouds/>

西雅图初创公司 Pulumi 发布了其平台，旨在消除云软件开发的复杂性和管理所有这些 YAML 文件的麻烦。

联合创始人乔·达菲和 T2·埃里克·鲁德来自微软，首席技术官 T4·卢克·霍班来自亚马逊。

在一篇博客文章中，Duffy 在微软的 12 年里领导着软件开发团队，也是微软开源项目的一员。NET 开发者环境，强调了云软件开发的困难，特别是对于容器和无服务器工作负载:

“对于每个无服务器功能，我都有几十行 JSON 或 YAML 配置。为了将它连接到 API 端点，我需要学习晦涩的概念，并执行复制粘贴的垃圾工作。当我在我的机器上运行一个小集群时，Docker 很棒，但是在生产中运行它需要手动管理 etcd 集群，设置网络和 iptable 路由，以及一大堆远离我的应用领域的事情。Kubernetes 至少让我这样做了一次，并跨云重用它，但感到陌生和分心。

“我认为我是一个相当有经验的工程师，在这个行业工作了 20 年，但试图将我的代码放入云端让我觉得自己很笨。而且很沮丧！”

Pulumi 基于基础设施即代码的思想，提供了一种一致的方法，包括容器、无服务器功能、API 和基础设施，并使用 DevOps 团队已经知道的编程语言，如 JavaScript、TypeScript、Python 和 Go。包括 Java 和 C#在内的其他语言也在开发中。

Kubernetes 的联合创始人 [Brendan Burns](https://www.linkedin.com/in/brendan-burns-487aa590/) ，现在为[微软](https://azure.microsoft.com/en-us/?v=17.14) Azure 工作，去年 12 月在 KubeCon 展示了一个类似的想法和他的[超粒子](https://metaparticle.io/)项目。

## 云对象模型

Rudder 解释道:“我们希望摆脱基础设施配置、使容器和无服务器变得简单的孤立方法，以及供应商锁定。”

团队中的每个人都看到了构建和管理 YAML 配置文件的过程变得多么扭曲。

“YAML 有自己的抽象概念，部署服务有点疯狂，大约 10 分钟后部署失败，因为 YAML 文件中有多余的空间。这对我们来说是一件令人震惊的事情。人们试图扩展 YAML 文件的语义，但然后你有疯狂的转义机制，把代码放在 YAML 文件中，然后人们在他们的源代码之间复制代码，然后他们有一个宏，会把它塞进配置文件——这只是不太适合，”鲁德说。

“如今，使用所有这些 YAML 工具，你打开一个 IDE(集成开发环境),你得不到 IDE 的帮助，因为它只是 YAML 的一个不透明的斑点。你得不到任何重构支持，当你犯错时，它不会给你交互错误，你没有测试支持。他说:“作为开发人员，我们期望我们的工具具备所有这些东西。

“真正的编程语言解决了许多我们想要解决的问题，我们想要拥抱开发人员和开发人员更加紧密合作的趋势，”鲁德尔说，他曾被认为是比尔·盖茨的可能继任者。

Pulumi 使用一个云对象模型，结合一个云中立的评估运行时，该运行时可以理解以任何语言编写的程序以及运行它们所需的云资源，然后以一种健壮的方式规划和管理这些资源。

Duffy 解释说，Pulumi 不是 PaaS——你的程序总是直接运行在你选择的云上，而云的所有功能仍然完全可供你使用。它的夏威夷主题包括拥抱它所谓的“CoLaDa 架构”——由容器、lambda 函数和数据服务组成的应用程序。

[https://www.youtube.com/embed/YMAe59BYzm4?feature=oembed](https://www.youtube.com/embed/YMAe59BYzm4?feature=oembed)

视频

## 语言的力量

这家成立于去年的公司还宣布了来自 Madrona Venture Group 和 Tola Capital 的 500 万美元系列种子投资。

学习机是它的第一批客户之一，将 25，000 行代码削减到仅仅 500 行。它的联合创始人之一，[丹·休斯](https://www.linkedin.com/in/danieljameshughes/)，现在的总裁兼首席运营官这样解释它的经历:

“我们需要将我们的企业区块链工具集引入主要企业和政府客户的数据中心，他们有特定的本地或云供应商要求，这意味着我们必须在我们支持的每个新环境中重写数千行代码。这将使我们的上市时间和代码行数显著增加。”

在与 Pulumi 团队会面后，它决定尝试一下。

“这个决定对我们来说至关重要。在一次性移植到 Pulumi 云编程模型的过程中，我们能够淘汰 25，000 行代码来换取几百行代码，并且我们消除了 DevOps 单点故障。一个月后，我们的解决方案就能够完全按照客户的预期进行部署。Pulumi 在不同的平台上统一了我们的实践，并使 DevOps 成为一流的功能，整个团队现在都是其中的一部分。”

Pulumi 有两个部分:

*   **Pulumi 核心**是工具和编程模型，语言和框架。这是开源的，可以在 [GitHub](https://github.com/pulumi/pulumi) 上获得。
*   **普鲁米服务**。公开预览版的 SaaS 产品。该团队将其描述为“git 对于 GitHub 的意义”

“这实际上是让你的 Pulumi 代码进入云——连接到你的源代码所在的任何地方，并进入 Azure、Google Cloud 或它要去的任何地方。这两者旨在协同工作。对于开发人员来说，它只是工作，方便，他们不一定会察觉到这两者之间的界限，”鲁德尔说。

Pulumi 用多个服务的统一日志记录了谁更新了什么、什么时候更新的以及为什么更新。它链接回源代码。它使用户能够在基础结构的副本上测试更改。

虽然你可以专门为 AWS、Azure、Kubernetes 等等编写程序，但你也可以在更高的层次上编程，并使用你选择的包管理器。

“我们发现的一件事是，我们可以将最佳实践封装在包中，我们可以发布这些包以与您自己的团队和社区共享……您可以利用其他人的贡献。对于人们管理软件的方式来说，这是一个游戏规则的改变，”Rudder 说。

公司也可以将其安全最佳实践打包。

Pulumi 已经为 AWS、Azure 和 Kubernetes 创建了包，但也提供了一个面向可以在多个云中运行的高级编程的云包。例如，您可以使用它来创建 Docker 容器，这是一个与 Travis 或 Jenkins 等持续集成系统集成的特性。

“这是一个只运行 Docker 映像的计算。大多数试图在生产中使用 Docker 的人不得不管理疯狂的构建管道，并以某种方式将其与他们的应用程序部署同步。这是一种统一的方法，只要有 Docker 文件，就可以在代码中引用它，Pulumi 就会发挥它的魔力。它构建、同步它，确保它与您的代码一起部署。你不用想了。”

Rudder 强调交互性是这项技术的首要特征。

“通常你会为文档打开另一个窗口，你会试图判断它是否正确。没有工具会告诉你它是否正确。我们可以以此为基础。我们计划进行更好的交互式分析——静态分析来发现错误、漏洞，我们可以发现安全问题和可能的成本问题。我们相信语言能让我们获得所有这些(能力)。”

微软是这一新技术的赞助商。

专题图片: [Carlos Madrigal](https://www.flickr.com/photos/carlitosmadrigal/) 创作的《 [A](https://www.flickr.com/photos/carlitosmadrigal/441090273/in/photolist-EYGLH-26xzRcU-GQSNpT-W3f3jT-8S6Qre-67uVh1-LmCUuG-XQmuLG-VDJDSf-dMNRiJ-6mne61-JK88yF-c7hiuL-s2P1Aa-EjPmmd-24GzWNq-XR6TTj-GvRgdb-9datsv-HSEYoA-273nJKs-EmRv6-27cSFSu-24c8EQ9-JCjzbR-aiB2Fy-27cSKLm-6p7dye-27TJv1A-YBxaDu-qwqWWV-dACPRL-pEiZYn-Y9Zrn-qdsWVT-6mBp7v-bAwVUj-65Z2JZ-Ay9ME8-25zBQdz-UAfoyU-WHXvsA-4tLuHQ-67kNC6-pDZsh8-JkmJUf-6jxrXF-T9onXv-9ddAW3-24izpMs) [s 美味多彩](https://www.flickr.com/photos/carlitosmadrigal/441090273/in/photolist-EYGLH-26xzRcU-GQSNpT-W3f3jT-8S6Qre-67uVh1-LmCUuG-XQmuLG-VDJDSf-dMNRiJ-6mne61-JK88yF-c7hiuL-s2P1Aa-EjPmmd-24GzWNq-XR6TTj-GvRgdb-9datsv-HSEYoA-273nJKs-EmRv6-27cSFSu-24c8EQ9-JCjzbR-aiB2Fy-27cSKLm-6p7dye-27TJv1A-YBxaDu-qwqWWV-dACPRL-pEiZYn-Y9Zrn-qdsWVT-6mBp7v-bAwVUj-65Z2JZ-Ay9ME8-25zBQdz-UAfoyU-WHXvsA-4tLuHQ-67kNC6-pDZsh8-JkmJUf-6jxrXF-T9onXv-9ddAW3-24izpMs)》，获得 [CC BY-SA 2.0](https://creativecommons.org/licenses/by/2.0/) 授权。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>