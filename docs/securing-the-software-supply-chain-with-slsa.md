# 保护 SLSA 软件供应链的安全

> 原文：<https://thenewstack.io/securing-the-software-supply-chain-with-slsa/>

我们都知道[软件供应链是脆弱的](https://thenewstack.io/the-challenges-of-securing-the-open-source-supply-chain/)。根据 Sonatype 的 2021 年[软件供应链状态](https://www.sonatype.com/resources/state-of-the-software-supply-chain-2021)报告，2021 年的攻击与前一年相比增长了惊人的 650%，总共发生了 12，000 起恶意事件。

而且情况可能会变得更糟: [Gartner 预测](https://www.gartner.com/en/documents/4003625)“到 2025 年，45%的组织将经历过对其软件供应链的攻击，这是 2021 年的三倍。”

但是，解决这一日益增长的挑战仍然是应用程序[安全性](https://thenewstack.io/category/security/)中未得到满足的重大需求。

在这种背景下，谷歌在六月提出了软件产品的供应链层次。受供应商的内部“[Borg](https://cloud.google.com/docs/security/binary-authorization-for-borg)二进制授权”流程(几十年来一直是谷歌生产工作负载的强制要求)的启发，SLSA 是一个确保软件工件完整性以防止攻击的框架。

该项目在 OpenSSF 的赞助下进行管理，已经有 30 多个贡献者，包括 Chainguard、Citi、Datadog、Intel 和 VMware。

## 为什么软件供应链受到威胁？

专注于软件供应链安全的 Cycode 公司的联合创始人兼首席技术官 Ronen Slavin 表示，从攻击生产系统转向攻击供应链有三个主要原因。

第一个与可见性有关。在许多组织中，安全团队不负责组成 [CI/CD 管道](https://thenewstack.io/category/ci-cd/)的工具。“现代开发方法带来了许多工具，这些工具由工程实现和运行，而没有安全的参与；这造成了可见性差距，”Slavin 通过电子邮件告诉新堆栈。

“此外，工程团队与安全团队有不同的优先级。毫不奇怪，工程团队建立了工程生产力工具，强调开发人员的敏捷性和特性速度，而安全性通常是事后才想到的。”

供应链攻击增加的第二个原因与攻击面有关，工具本身成为攻击媒介。“这些攻击比传统的入侵更具破坏性，”Slavin 告诉我们。

他列举了新一轮攻击破坏力如此之大的四个原因:

1.  诸如一切如代码和 [GitOps](https://thenewstack.io/what-is-gitops-and-why-it-might-be-the-next-big-thing-for-devops/) 等趋势使得攻击者一旦站稳脚跟，就更容易横向移动或危及整个软件开发生命周期(SDLC)。
2.  这种类型的攻击通常绕过大多数组织依赖的标准安全措施，如防火墙、[、web 应用程序防火墙(WAFs)](https://thenewstack.io/waf-securing-applications-at-the-edge/) 、空中间隔、子网划分、VPN 等。
3.  供应链攻击通常会向下游蔓延，破坏客户。
4.  在经历供应链攻击后，恢复代码通常更加困难和耗时，因为违规的程度通常更深、更广、更敏感，因此重建需要更彻底的过程。

“因此，从攻击者的角度来看，这种攻击的投资回报率要高得多，”Slavin 总结道。

第三个问题是缺少工具；相对来说，很少有工具能够跨越软件开发生命周期的不同阶段。“从安全性的角度来看，SDLC 是孤立的，几乎没有能力连接各个点，”Slavin 说。

## SLSA 是如何工作的？

SLSA 框架的运作原则是，如其官方文件所述，“实现理想的安全状态可能需要数年时间，中间里程碑非常重要。”

鉴于此，我 [t 定义了一个分级的方法来为你的构建采用供应链安全。总而言之:](https://slsa.dev/spec/v0.1/levels)

*   **第一级:**构建过程必须完全脚本化/自动化，并生成出处——关于工件如何构建的元数据，包括构建过程、顶级源代码和依赖关系。这个级别不能防止篡改，但是它提供了一个基本的代码源识别级别，并且有助于漏洞管理。
*   **第二级:**需要使用版本控制和托管构建服务来生成经过认证的出处。在这个级别上，起源防止了在构建服务受信任的范围内的篡改。
*   **第三级:**源和构建平台分别满足特定的标准，以保证源的可审核性和来源的完整性。理论上，通过防止特定类别的威胁，如交叉构建污染，这比以前的级别提供了更强的防篡改保护，但它确实需要某种尚未定义的认证流程才能工作。
*   第四级:需要两个人对所有的变更进行审查，以及一个密封的、可重复的构建过程。密封的构建保证了出处的依赖列表是完整的。

据正在 SLSA 工作的 VMware 开源软件工程师 [Joshua Lock](https://www.linkedin.com/in/joshua-g-lock/?originalSubdomain=uk) 称，这种渐进式方法是关键。

“特别是对于开源项目，我们都可以说拥有 SLSA 四级是最理想的，但我们也可以认识到，对于大多数由一个人在业余时间构建和维护的开源项目来说，这是不可能实现的，”Lock 说。

所以我们可以选择说，“好吧，也许我对第二级或第三级感到满意，我会就此打住，如果项目真的启动了，也许我会走得更远。"

## SLSA 帮助指导代码政策

同样，通过了解 SLSA 级别，开发人员和组织可以推断软件包或构建平台的安全状态，并决定信任什么。

“最初的目标是达到这样一种状态，公司可以说，‘嘿，我不会在我的生产系统中部署任何不符合 SLSA 三级标准的代码’，并将其作为一项严格的政策。或者他们的供应商需要在签署合同前达到更高的 SLSA 水平，”[金·莱万多夫斯基](https://www.linkedin.com/in/kimsterv)告诉新的 Stack，她在谷歌时致力于并推出了 SLSA，后来又创立了 Chainguard。

这本身就很重要，正如 Lock 告诉我们的那样:“当你看到云原生系统以及它们正在引入的成百上千个依赖项时，能够想象未来你可以说，‘好吧，我不希望任何东西攻击我的集群，不是 SLSA 三级或以上’真的很强大。”

换句话说，“SLSA 实际上是许多现有最佳实践的结合，”洛克说。

“我打了个比方，许多 SLSA 需求是 Linux 发行版已经做了很长时间的事情，”他说。“所以 Linux 发行版会复制他们正在构建的源代码；他们不会依赖上游位置不变或不被篡改。

“他们通常有一个相当严格的过程来接受新的包维护者——所以有了‘可信贡献者’的概念。你写一种包装你的软件的方法，然后你把代码推到某个地方，中央分发机器构建这个包，在它被引入到普通分发用户可以接受的流之前，它通过各种级别的测试和质量保证。这符合 SLSA 的构建要求；被定义为代码，使用隔离环境，等等。”

## 用于检查安全声明的可验证元数据

然而，一个挑战是，消费者如何知道他们可以信任声称的安全级别？SLSA 旨在通过自动创建可验证的元数据来解决这个难题。

“在我看来，这是与 SLSA 的区别之一——它不仅仅是一系列要求和最佳实践，”莱万多夫斯基说。“您实际上必须拥有数据，即您正在生产的可验证数据，这样包装的消费者才能看到显示其符合不同 SLSA 要求的实际数据。”

> “SLSA 实际上是许多现有最佳实践的结合。”

—Joshua Lock，VMware 开源软件工程师

Slavin 附和了这一观点:“该标准非常关注构建过程及其安全性，这是一个巨大的进步。它引入了起源的概念，这是证明构建过程的一种方式，并推动了可再现构建的想法，这也是迈向安全管道的非常重要的一步。”

莱万多夫斯基说，SLSA 提出的另一个问题是，“整个供应链都存在弱点。在过去的几年里，我们在每一个点上都看到了攻击。”

有鉴于此，SLSA 框架为软件交付供应链提供了一个[威胁模型](https://slsa.dev/spec/v0.1/threats)，它涵盖了源代码和构建完整性，并展示了 SLSA 可以如何提供帮助。

然而，应该强调的是，SLSA 在很大程度上仍然是一项正在进行中的工作，并且[正在积极讨论](https://github.com/slsa-framework/slsa/issues/276)哪些措施应该在范围之内。威胁模型突出了规范目前没有涵盖的许多领域，包括代码审查绕过或管理员更改安全配置以推送恶意代码等风险。

此外，如前所述，供应链安全工具仍处于萌芽状态。但是像 [sigstore](https://www.sigstore.dev) 这样的计划，旨在使工件的加密签名变得非常容易和开发者友好的开源工具，显示出了希望，特别是当与 SLSA 规范结合时。

对于想要开始的读者，SLSA 项目出版了一本“[入门](https://slsa.dev/get-started)”指南，可以帮助你达到第一级。Chainguard 也开始发布一些博客([这里](https://blog.chainguard.dev/building-trust-in-our-software-supply-chains-with-slsa/)、[和这里](https://blog.chainguard.dev/slsa-vs-software-supply-chain-attacks/))，提供有用的额外信息。另外，[Cloud Native Computing Foundation](https://cncf.io/?utm_content=inline-mention)保留了一份由社区维护的活文档:[软件供应链安全论文](https://github.com/cncf/tag-security/tree/main/supply-chain-security/supply-chain-security-paper)，旨在为社区提供“一系列推荐的实践、工具选项和设计考虑，可以降低成功的供应链攻击的可能性和整体影响。”

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>