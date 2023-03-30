# 无服务器 vs. Kubernetes:人民的投票

> 原文：<https://thenewstack.io/serverless-vs-kubernetes-the-peoples-vote/>

就可扩展性、成本和安全性而言，Kubernetes 和无服务器架构哪个更好？

在[亚马逊网络服务](https://aws.amazon.com/?utm_content=inline-mention)最近的 Re:Invent 会议上，一个分组会议“现代工作负载的竞争:AWS 上的无服务器与 Kubernetes”是对[无服务器](https://thenewstack.io/serverless-impacts-on-business-process-and-culture/)与 [Kubernetes](https://thenewstack.io/primer-how-kubernetes-came-to-be-what-it-is-and-why-you-should-care/) 的六点比较，以最终确定哪个架构更好，由支付提供商 [Melio](https://meliopayments.com/about-us/) 的 DevOps 负责人 [Niv Yungelson](https://aws.amazon.com/developer/community/heroes/niv-yungelson) 和[dat 的联合创始人兼首席执行官 Shimon Tolts](https://www.linkedin.com/in/tolts/?originalSubdomain=il) 提出

这些类别涵盖了从可维护性到日志记录以及两者之间的所有内容。每位与会者都有机会在每一轮结束时通过举手投票，如果你愿意，也可以现场直播赞成和反对。

Tolts 站在 Kubernetes 一边，自称是众多使用 Kubernetes 的大规模应用程序的提交者和维护者，见过好的、坏的，一生只有一次。就关联性而言，他知道权衡以及如何在灰色地带工作。

Yungelson 是 Melio 的第一位 DevOps 工程师，现在领导该公司的无服务器团队。她认为，无服务器处于创新尺度的更低端。首先是内部部署，然后每个人都迁移到了云，但他们的思维模式与内部部署相同:首先是基础架构，然后根据需求进行扩展。然后，无服务器出现了，首先从需求开始，然后再构建，彻底颠覆了一切。

## **类别 0–可维护性**

作为开场白，永格尔森引用了沃纳·威格尔(AWS 首席技术官)的话:“没有服务器比没有服务器更容易管理。”另一方面，Kubernetes 需要大量的维护——定期更新和偶尔的随机生产级代码折旧。

亚马逊的弹性 Kubernetes 服务 (EKS)确实有助于 Kubernetes 的可维护性，它提供了自动版本升级等便利。

观众以压倒性优势支持无服务器，这并不奇怪。

**无服务器 1**

Kubernetes 0

## **类别 1–成本**

*我们怎么买这个？我们如何支付这个？*

Kubernetes 权衡归结为集群优化。利用正确的 I/O、计算和内存密集型工作负载比率构建优化的集群。这需要很高的开发成本。潜在开发成本的节约？只有具体的组织才能作出这一决定。

“谁的 DevOps 职位是他们无法填补的？”这是永杰尔松的回答。许多与会者举起了手。这并不是说无服务器架构不是一个挑战，而是工程专业在别处。

还有两件事要考虑。可靠性。Kubernetes 是可靠的。大流量峰值不会影响成本，并且不需要像使用无服务器时那样精确地估计或预测工作负载，因为无服务器成本会快速增长。

无服务器的一个主要优点是，唯一需要付费的服务是使用的服务，而 Kubernetes 不是这种情况。

举手的人数平均分配。

**无服务器 2**

**Kubernetes 1**

## **类别 2–可扩展性**

Kubernetes 和 serverless 在设计时考虑了可伸缩性，但功能不同。这真的归结为无服务器的配额与 Kubernetes 所需的大量保姆服务。对于反对者，Tolts 承认扩展 Kubernetes 比无服务器扩展更复杂，但也补充说 AWS 确实提供自动扩展。它确实存在。

为了在配额系统中舒适地工作，Melio 创建了多个帐户(即 staging、production 等)，因为 AWS 不允许超过硬性限制，但他们有友好的选项。

观众仍然没有完全接受无服务器。领带。

**无服务器 3**

**Kubernetes 2**

## **第 3 类——开发者友好型**

这两者都不容易，但有了 Kubernetes，一旦有人理解了这项技术，他们就知道如何使用它。输入门槛高，但只需输入一次，因为 Kubernetes 是跨运行时的单个 API。挑战在于编排一个大环境。

无服务器有一个更长的缺点列表，但它们可以归类为特定于供应商。每个供应商都有自己的技术，自己的规则，以及随之而来的一切。特别是在 Melio 的情况下，开发人员需要理解 [AWS Lambda](https://thenewstack.io/aws-lambda-is-a-step-towards-creating-a-new-normal/) 的局限性，并且在相同的资源上工作更加困难(模拟器并不完全相同)。

梅利奥的解决方案是私人账户。每个人都有自己的 AWS 帐户，并通过脚本和简短的反馈循环连接到主帐户，而不是让每个开发人员都使用一个主帐户并对不同的环境进行故障排除。不是部署整个代码文件更新，而是只部署它们的特定更改。

Kubernetes 得一分。

**无服务器 3**

库伯内特 3 号

## **第 4 类——生态系统**

整个开发人员世界或由云提供商创造的世界。Severless 是供应商锁定的(至少在 [AWS Lambda](https://aws.amazon.com/lambda/) 的情况下)，Kubernetes 是由供应商中立的[云本地计算基金会](https://cncf.io/?utm_content=inline-mention) (CNCF)管理的开源软件，用户社区 Kubernetes 有一个丰富的生态系统，可以使用任何提供商的任何服务，但 serverless 被锁定到一个提供商，但它是首选提供商。并不是只有一种无服务器选项。

Yungelson 对 AWS 及其大量的创新服务感到满意，她说，“她不觉得自己错过了什么。供应商锁定是我们的选择。”

不过，与会者还没有做好承诺的准备。Kubernetes 的另一点。

**无服务器 3**

**Kubernetes 4**

## **类别 5–监控和记录**

这一个把它带回到早期的想法，无服务器是一种新的思维方式。使用 Kubernetes，开发人员可以使用他们从其他地方了解并喜欢的相同工具进行监控和日志记录(即“这是我们监控 Linux 的方式”)，但是使用 serverless，没有服务器基础设施来进行监控和日志记录。尽管所有标准监控软件都支持无服务器，但使用可能有所不同，因此没有硬件或硬件管理限制。

Kubernetes 的主要缺点是要监控多个层和对象。

推动无服务器还不足以赢得胜利。这是一个平局。

**无服务器 4**

**Kubernetes 5**

## **类别 6–安全**

他们都有安全方面的帮助。Kubernetes 从定期更新和无服务器的云提供商，但仍有开发工作。例如 Kubernetes，如果它们运行在 EC2 实例上，开发人员需要保护 EC2 实例。在无服务器的情况下，私奔工作来自于确保代码满足安全要求，lambdas 构建在虚拟私有云(VPC)内，没有任何虚拟公共云。

无服务器赢了！

**无服务器 5**

库伯内特五号

最后打成了平局！

演讲中讨论的两个应用程序都运行在 Amazon bracket 上。

这是一种非常吸引人的谈论技术权衡的方式。这是引人入胜和增长见识的。这个空间被挤满了，就像溢出的空间一样，演讲者们都很有见识。五星。千万推荐。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>