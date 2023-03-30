# 将 SBOMs 与安全数据相结合:Chainguard 的 OpenVEX

> 原文：<https://thenewstack.io/combining-sboms-with-security-info-chainguards-openvex/>

软件材料清单告诉你什么是程序中的代码。Chainguard 的 OpenVEX 会告诉你什么是错的，什么是不太对的，但在你的代码中是 OK 的。

Chainguard 已经是安全编程的领导者，现在它又向前迈进了一步，增加了对[漏洞利用交换(VEX)](https://www.cisa.gov/sites/default/files/publications/VEX_Use_Cases_Aprill2022.pdf) 到 [软件材料清单(SBOMs](https://thenewstack.io/how-to-create-a-software-bill-of-materials/) ) 的支持。这个草案实现叫做 [OpenVEX](https://github.com/openvex/spec) 。

## 烦恼吗？

你问维克斯？这是一个新的[网络安全和基础设施安全局(CISA](https://www.cisa.gov/sbom) )的工作规范。这是一个机器可读的安全建议。因此，它被集成到现有的安全管理工具和更广泛的漏洞跟踪平台中。VEX 数据与 SBOM 数据整合。您可以通过在现有的 SBOM 或专用的 VEX SBOM 中表示 VEX 数据来实现这一点。

在 VEX 记录中，您会发现以下元素:

*   VEX 元数据包括 VEX 格式标识符、VEX 文档的标识符字符串、作者、作者角色和时间戳。
*   产品详细信息必须包括标识符或系列标识符。例如，唯一标识符或供应商名称、产品名称和版本字符串的组合。
*   漏洞详细信息包括漏洞数据，如常见漏洞和暴露(CVE)以及漏洞描述。
*   四种产品漏洞状态通知之一:
    *   不受影响:不需要对此漏洞进行补救。
    *   受影响:建议采取措施补救或解决此漏洞。
    *   已修复:这些产品版本包含漏洞的修复程序。
    *   正在调查中:尚不清楚该漏洞是否会影响这些产品版本。更新将在以后的版本中提供。

VEX 从[公共安全顾问框架](https://oasis-open.github.io/csaf-documentation/)中获取其漏洞数据。这是一份 [OASIS](https://thenewstack.io/oasis-combines-open-source-and-open-standards-with-open-projects/) 参考资料，以结构化数据的形式描述了安全公告的创建、更新和可互操作的交换，包括产品、漏洞以及影响和补救的状态。这些信息在 [JSON](https://thenewstack.io/an-introduction-to-json/) 中共享。

## OpenVEX

Chainguard 已经采取了下一个合乎逻辑的步骤，并发布了 OpenVEX 规范和参考工具链。公司并不是完全靠自己做到的。它是在几个行业领导者的支持下开发的，包括安克雷奇、HPE、谷歌、evidency sec、 [VMware、](https://tanzu.vmware.com?utm_content=inline-mention)和[Linux 基金会。](https://training.linuxfoundation.org/training/course-catalog/?utm_content=inline-mention)

VEX 也得到了美国[国家电信和信息管理局](https://thenewstack.io/orion-go-beyond-package-manager-discovery-for-your-sbom/)的支持和 CISA[的支持。VEX 的目标是提高组织识别和缓解关键安全威胁的能力。](https://thenewstack.io/cisa-lays-out-security-rules-for-zero-trust-clouds/)

## 补充工具

OpenVEX 是 SBOM 工具的补充，允许供应商直接向消费者和最终用户传达关于产品漏洞状态的精确元数据。它是与 CISA VEX 工作组合作开发的，是满足 VEX 最低要求的第一种格式。Chainguard 还将 OpenVEX 投入生产其 [Wolfi Linux (un)发行版](https://www.chainguard.dev/unchained/introducing-wolfi-the-first-linux-un-distro)和 [Chainguard Images 产品](https://www.chainguard.dev/chainguard-images)。

OpenVEX 规范使开发人员能够交流精确的、可操作的元数据，以提高软件消费者的信噪比。OpenVEX 使软件生产商能够轻松准确地描述他们的工件的可利用性。

同样重要的是，OpenVEX 使软件消费者更容易从漏洞扫描器中过滤掉误报。这意味着安全专家要花更多的时间调查有价值的安全问题，花更少的时间剔除错误的发现。OpenVEX 对误报进行编码，使消费者能够更有效地优先处理漏洞报告。

这很重要，因为根据谷歌云的首席信息安全官菲尔·维纳布尔斯的说法，我们对问题的知识增加会导致小安全问题的“恐怖谷”。缺少上下文，这些小问题可能看起来比实际情况大得多，导致人们认为他们代码的安全性变得更差。

提供 SBOMs 的运动将极大地增加整个软件供应链的透明度。具有前瞻性思维的组织已经意识到，尽管透明性很好，但漏洞生态系统中的噪音会阻碍 SBOMs 的采用和使用。

OpenVEX 允许开发人员使用发行版的配套工具为 [Wolfi](https://github.com/wolfi-dev/) 软件包生成 VEX 数据，`wolfictl.`用户也可以使用 vexctl 的过滤功能从 VEX 数据的扫描结果中过滤掉噪音，如误报。

## 入门指南

您可以通过以下步骤从今天开始使用 OpenVEX:

*   您可以使用`[vexctl create](https://github.com/openvex/vexctl#1-creating-vex-documents)`搭建新文档，它从命令行创建新的 vex 文档。
*   从上游开始，你可以使用发行版的配套工具`wolfictl.`为 Wolfi 包生成 VEX 数据，使用`wolfictl vex package -h`为 Wolfi 包生成 VEX 文档，或者使用`wolfictl vex sbom -h`为 Wolfi 包的整个 SBOM 生成 VEX 文档。
*   你可以使用`vexctl`的[合并功能从现有的 vex 源中收集 VEX 数据。](https://github.com/openvex/vexctl#merging-existing-documents)
*   最重要的是，你可以使用`vexctl`的[过滤](https://github.com/openvex/vexctl#3-vexing-a-results-set)来过滤 VEX 数据中的噪音，比如扫描仪结果中的假阳性

## 最终结果

最终结果是 OpenVEX 简化了软件漏洞管理的补救过程。这仍是一项进行中的工作。我们需要一起工作来构建可以轻松集成到现有开发实践中的格式和工具。

OpenVEX 公开发布和维护，以鼓励协作并简化所有利益相关方的补救流程。最终，SBOM 和 VEX 的结合将导致比以往任何时候都更快、更安全地构建程序。

正如 Chainguard 的首席软件工程师 Ariadne Conill 所说，“管理软件发行版中的漏洞蔓延是一项重大挑战，因为每个漏洞都必须由安全团队进行研究，以确定它们是否适用于软件发行版中的版本。

“OpenVEX 的推出允许所有利益相关者，从上游开发者到发行版和最终用户，在软件使用的任何地方就漏洞修复进行合作，简化了每个人的修复过程。”

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>