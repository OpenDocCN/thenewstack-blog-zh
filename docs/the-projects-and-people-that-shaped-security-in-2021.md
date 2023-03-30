# 塑造 2021 年安全的项目和人物

> 原文：<https://thenewstack.io/the-projects-and-people-that-shaped-security-in-2021/>

随着假期旺季的到来，大多数人都在精干的团队中运行，可能没有资源来应对严重的网络攻击，log4j 日志库的最新利用让开发人员陷入了混乱。这次入侵利用了网络安全领域又一年的旋风，漏洞百出的技术不断增加开发人员的工作量。

不断扩大的云原生环境和开源软件的广泛采用面临着加速发布周期的更大压力，这使得许多企业今年面临更大的风险。对于许多人来说，勒索软件攻击和现代供应链的战场给了对手许多可探索的漏洞，而美国总统行政当局发布了一项行政命令，要求制造和分发软件的供应商在软件材料清单(SBOM)中详细说明他们产品中的实际内容，特别是开源软件。

从在应用生命周期的早期构建安全流程，到用不断发展的新实践重新审视现有的安全技术，这些都是影响开发人员将黑客挡在云原生生态系统之外的年度顶级安全故事。

**2021 年重大安全事件:**

**# 1:**[**Web 应用防火墙已死，我们知道是谁杀死了它**](/the-web-app-firewall-is-dead-and-we-know-who-killed-it)——Web 应用防火墙(WAFs)于 20 世纪 90 年代末进入市场，传统上用于保护数据和资产免受利用和攻击。但是现在，随着许多组织在更快的应用程序发布周期下运行，传统的 WAF 能跟上吗？查看我们的赞助商 [Check Point](https://www.checkpoint.com/products/cloud-native-security/?utm_content=inline-mention) 的这个故事，了解最新的见解，以保持 WAFs 跟上 DevOps 的速度。

**#2:** [**无外壳 Kubernetes: Talos Systems 引入了通用操作系统接口**](/shell-less-kubernetes-talos-systems-introduces-the-common-operating-system-interface) —通常，Kubernetes 运行在标准的 Linux 发行版之上，但 Talos Systems 对其特定于容器的操作系统(CSOS)Talos 采取了不同的方法，该操作系统由应用程序编程接口(API)s 驱动。Talos Systems 认为，在 CSOS 上运行 Kubernetes 比在通用 Linux 上更好，因为它避免了不必要的开销，并且缺乏与 Kubernetes 的任何内置协调此外，与通用主机操作系统相比，攻击面更小，破坏特定于容器的主机操作系统的机会更少。

**#3:** [**捍卫核心:Kubernetes 每一层的安全性**](/defend-the-core-kubernetes-security-at-every-layer) — Kubernetes 的广泛采用率已激增至 88%，然而[Red Hat 的](https://www.redhat.com/en/resources/kubernetes-adoption-security-market-trends-2021-overview)[最新调查中超过一半的](https://www.openshift.com/try?utm_content=inline-mention)受访者表示，由于安全问题，他们已经推迟将 Kubernetes 应用程序部署到生产中。在这个故事中，Fastly 的安全研究主管 Jimmy Mesta 研究了容器的含义，并提供了他的最佳实践建议，以帮助将黑客拒之门外。

**#4:** [**为什么开源项目维护者不愿使用数字签名，双因素认证**](/why-open-source-project-maintainers-are-reluctant-to-use-digital-signatures-two-factor-authentication) —开源继续被无良开发者滥用。事实上，[最近的一项调查](https://www.linuxfoundation.org/tools/foss-contributor-survey-2020/)显示，当被问及他们从事的开源项目是否需要使用 2FA 时，例如 [GitHub 组织设置“需要双因素认证](https://docs.github.com/en/enterprise-server@2.21/admin/user-management/requiring-two-factor-authentication-for-an-organization)”，几乎一半的开发人员说他们没有使用它。那么开源组织应该如何管理程序员说出他们是谁呢？

**# 5**:[**帕勒的数据是如何被收割的**](/how-parlers-data-was-harvested)——当右翼社交网络帕勒被[亚马逊网络服务](https://aws.amazon.com/?utm_content=inline-mention) (AWS)关闭后，帕勒的数据，包括死亡威胁和有地理标记的已删除消息，被抓取并发布在众多公共网站上。被删除的信息也被捕获，因为 Parler 的专有程序实际上并没有删除它们。相反，它将它们标记为对用户不可见，这暴露了糟糕的安全编程。下面是新堆栈的史蒂文 j 沃恩尼科尔斯的故事，讲述了帕勒的前成员如何成为社区的受害者。

**#6:** [**用 AWS Secrets Manager**](/managing-kubernetes-secrets-with-aws-secrets-manager) 管理 Kubernetes Secrets 领先的虚拟主机公司之一 GoDaddy 开源了一个名为 Kubernetes External Secrets 的内部项目。在 Janakiram & Associates 的首席分析师 [Janakiram MSV](/author/janakiram/) 的这一系列报道的最后一个故事中，他介绍了该项目如何用于配置由亚马逊网络服务的秘密管理器支持的秘密。作为亚马逊面向开发者的 CodeGuru 服务的一部分，亚马逊今年推出的 Secrets Detector 机器学习功能可以自动找到可能隐藏在源代码中的机密系统凭据，帮助找到错误和安全漏洞，然后提出补救措施。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>