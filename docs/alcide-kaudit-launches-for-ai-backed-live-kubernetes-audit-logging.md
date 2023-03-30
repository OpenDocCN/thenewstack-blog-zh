# Alcide kAudit 推出人工智能支持的实时 Kubernetes 审计日志记录

> 原文：<https://thenewstack.io/alcide-kaudit-launches-for-ai-backed-live-kubernetes-audit-logging/>

今天， [Alcide，【Kubernetes 和 DevOps 的运行时安全宣布了 kAudit 的公开测试版。Alcide kAudit 是 Kubernetes 审计日志的取证工具，由正在申请专利的人工智能提供支持。KAudit 会随着时间的推移了解审计日志的模式，然后针对该模式的异常情况启用安全性和合规性强制措施。](https://www.alcide.io/)

Alcide 首席技术官 [Gadi Naor](https://www.linkedin.com/in/gadinaor/) 告诉新的堆栈，审计日志仍然是网络安全领域最成熟的方法，可以用来查看系统是否已经被入侵。他说，这是确定什么“闻起来像虐待”——不协调的活动或奇怪的用户行为——的最佳方式。

然而，手动检查审计日志是乏味且耗时的。这仅仅是人脑无法处理的数据。尤其是以捕捉漏洞所需的速度。

## kAudit 支持 SecOps

安全团队开始使用 Alcide kAudit，通过创建主动策略来识别不符合规定的行为。例如，在生产环境中，您可能希望有一个例外，即没有人能够从日志中转储兼容的数据。任何从事法规遵从性工作的人都希望在此活动标记出数据违规时得到提醒。

当 kAudit 开始检查您组织的审计日志时，它会适应您的系统，以基于行为模式执行合规性规则。

接下来，Alcide kAudit 通过运行自动证书测试来调查您的安全问题。

Naor 表示，这包括“所有涉及数据泄露的事情，包括对数据服务器的特权访问以及围绕这一点进行的后续访问(扫描)。”

默认情况下，Kubernetes 仍然不够安全。其中一个缺陷是，直到最近，Kubernetes 实际上还需要对 API 服务器的特权访问，这意味着获得对一个集群的访问权的危害可能会访问整个环境。

Naor 说:“类似地，在一些 Kubernetes 管理的部署中，审计日志不一定是默认启用的，或者至少它不是方便地落在用户腿上的东西。”。[也可以阅读:零信任、服务网格和基于角色的访问控制如何防止基于云的安全混乱](https://thenewstack.io/how-zero-trust-service-meshes-and-role-based-access-control-can-prevent-a-cloud-based-security-mess/)。

> “实际情况是，当发生违规时，用户被蒙在鼓里。直到新闻报道说数据是从集群中提取的，他们才会知道。”——加迪·瑙尔，阿尔西德。

kAudit 的人工智能主干对用户和自动化服务如何与环境做出反应进行持续的行为分析。Naor 说，任何偏差都会被标记给 SecOps，“以提供对 Kubernetes 的见解，这在很多方面是一个盲点”。

## 自动化 Kubernetes 威胁检测

Naor 说，Kubernetes 生成的审计跟踪数据量可能特别大。这就是为什么你需要自动化工具来理解所有的概念。

“依靠积极主动的政策是一回事，但这实际上并没有涵盖整个威胁范围，”他说。

诺尔回忆起牧场主去年发现的第一只库伯内特 CVE。这是一个与对 API 服务器的未经验证的访问相关的高严重性 CVE，使得牧场主内部攻击者能够提升权限，以便能够访问整个集群。Naor 表示，这是一个非常严重的漏洞，导致了 CNCF 的建议，发布了补丁程序，云提供商更新了他们的 API 服务器。

Naor 将 kAudit 的黄金特性描述为正在申请专利的人工智能技术，该技术可以自学用户和自动化服务如何访问您的集群。这意味着未来的 CVE 可以被一个不需要笔测试的系统发现。

## kAudit 在人工智能/人工智能领域的未来

随着 Alcide kAudit 获得更多采用，他们正在寻求利用人工智能群体智能来揭示跨组织的常见攻击模式。

目前，从他们以前的小用户群中，他们已经发现了一些非常严重的共享威胁模式。

“自从我们开始封闭的测试周期以来，我们已经看到 Kubernetes API 服务器端点在世界各地被互联网扫描器积极探测，”Naor 说，最常见的是中国和东欧的攻击者。

> “在测试期间，我们在我们的系统和客户的系统中看到的东西有点令人担忧。”—加迪·瑙尔，阿尔西德。

kAudit 检测到的最常见的漏洞之一是凭证盗窃。这可能是因为队友未上锁的笔记本电脑被盗。攻击者可以获得进入 Kubernetes 集群的权限，并可以代表您的队友执行操作。

阿尔西德·考迪特将能够检测并标记这些动作，以及它们何时被执行，何时它们与你的队友通常执行的那些动作非常不同。

这只是人工智能和机器学习将继续推动越来越多的网络安全和欺诈保护分析的一个例子。

这种模式异常检测已经在一般的云安全中发生，但 Naor 说 kAudit 在将这些挑战应用到 Kubernetes 空间方面是独一无二的。

正如他所说[Kubernetes API 转向](https://www.twistlock.com/2019/03/14/kubernetes-auditsink-real-time-k8s-audits-forensics/)使数据流作为集群 API 的一部分更容易获得，这只会有所改善。这意味着您不再需要复杂的基于云的集成来访问这些数据流。

卢卡·布拉沃在 [Unsplash](https://unsplash.com/s/photos/mountains?utm_source=unsplash&utm_medium=referral&utm_content=creditCopyText) 上的照片。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>