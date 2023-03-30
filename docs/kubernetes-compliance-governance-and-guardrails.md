# Kubernetes 合规性:治理和护栏

> 原文：<https://thenewstack.io/kubernetes-compliance-governance-and-guardrails/>

云原生技术正在帮助各种规模的组织成长，更快地开发功能并建立竞争优势。[云原生](https://thenewstack.io/category/cloud-native/)的不足之处在于满足合规性要求。这是因为在许多情况下，合规经理、 [DevOps](https://thenewstack.io/category/devops/) 领导和平台工程师“不知道他们不知道的事情”，特别是对于 [Kubernetes](https://thenewstack.io/category/kubernetes/) 。

我们需要的是一个集中的框架——一套治理和防护——来帮助他们获取并保持知识。

## Kubernetes 治理和护栏

 [乔·佩尔蒂埃

Joe 是 Fairwinds 的产品战略副总裁，负责领导团队构建解决方案，在开发人员、安全性和运营之间架起桥梁。](https://www.linkedin.com/in/josephpelletier/) 

成功的 Kubernetes 合规植根于强大的治理和护栏。虽然合规性可能很棘手，但使用 Kubernetes guardrails 解决这一问题有助于组织利用安全网构建生产就绪型环境。

Kubernetes guardrails 允许开发人员[安全、合规且经济高效地与 Kubernetes](https://thenewstack.io/do-i-really-need-kubernetes/) 合作，以便他们的代码可以进入生产。它植根于 Kubernetes 服务所有权，让开发人员能够根据组织的策略配置容器和 Kubernetes，而不会降低它们的速度。那么如何把护栏安装到位呢？

第一步是建立护栏。组织需要遵循什么政策？it 需要遵守哪些法规遵从性要求— SOC 2、CIS 基准控制、NSA 强化指南或 PCI？需要遵循哪些内部政策？这些政策需要考虑并转化为 Kubernetes 护栏。

例如，组织可能希望遵守国家安全局和网络安全与基础设施安全局最近更新的关于 pod 安全性的强化指南。这包括通过使用非根容器、使用不可变的文件系统运行容器或扫描容器映像来防止根执行。

另一种情况是提供 SOC 2 特定的检查和文档。跟踪 SOC 2 检查的适当位置是什么？例如，保持基于角色的访问的合规性需要什么防护？所有这些例子都应该被翻译成 guardrails，但是仅仅写下来是不够的，这些 guardrails 需要在整个开发生命周期中被编码和执行。

通过对护栏进行编码，DevSecOps 领导者能够根据护栏扫描工作负载，以查看哪些预生产代码不符合要求。作为这个过程的一部分，真正的 Kubernetes 治理使用软件来审查从开发到生产的所有代码，以扫描任何违反法规的行为。

软件有助于消除 DevSecOps 团队手动审查和记录所有问题(通常在电子表格中)并试图让开发团队修复问题的负担。相反，软件不仅可以帮助防止问题进入生产，还可以帮助开发团队了解什么不符合以及如何修复它。

## 速度与合规性

监管合规面临的一大挑战是:对速度的需求。如前所述，云原生是关于上市速度。平衡速度收益与实现合规性不应该是一种折衷。DevSecOps 和 Kubernetes 服务所有权的原则寻求利用法规遵从性和 DevOps 的力量来建立一个为两者无缝工作的过程。这是通过将最佳实践、工具和策略统一在一个保护伞下实现的，这样护栏就可以在安全、开发和运营团队中保持一致。

当安全、开发和运营团队之间的孤岛被打破时，速度和合规性确实可以找到平衡。结果是满足了合规性要求、降低了安全风险、优化了成本并提高了性能。

实现合规性的压力要求从手动 Kubernetes 审查转变为自动审查。合规性的好处将是深远的，因为团队实现护栏不仅是为了安全和法规要求，也是为了节省资金和提高性能。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>