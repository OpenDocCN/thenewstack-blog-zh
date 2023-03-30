# AWS 的 Log4Shell 需要修复

> 原文：<https://thenewstack.io/awss-log4shell-fix-needs-fixing/>

[Log4Shell](https://thenewstack.io/log4shell-we-are-in-so-much-trouble/) ，开源 Java 日志库 [Apache Log4j](https://logging.apache.org/log4j/) 的问题一直让人头疼！现在，雪上加霜的是，[帕洛阿尔托网络公司的安全研究小组第 42 单元](https://unit42.paloaltonetworks.com/)发现了几个[亚马逊网络服务](https://aws.amazon.com/?utm_content=inline-mention) (AWS) [热补丁修复](https://alas.aws.amazon.com/announcements/2021-001.html)自带严重的安全漏洞。

总是有事！

那么，这些洞有多糟糕？一句话:“糟透了。”

具体来说，在将补丁服务安装到服务器或集群之后，[每个容器都可能被利用来接管其底层主机。](https://unit42.paloaltonetworks.com/aws-log4shell-hot-patch-vulnerabilities/)例如，如果您[将热补丁安装到 Kubernetes 集群](https://github.com/aws-samples/kubernetes-log4j-cve-2021-44228-node-agent)，那么集群中的每个容器现在都可以逃到更高的级别，直到您禁用热补丁或升级到修复版本。除了容器之外，无特权的进程也可以被用来利用补丁程序来提升特权和获得根代码执行。

## 事情变得更糟

你猜怎么着？情况变得更糟。

Unit 42 报告说，无论容器是否运行 Java 应用程序，或者它们的底层主机是否运行 [Bottlerocket](https://aws.amazon.com/bottlerocket/) ，AWS 针对容器的强化 Linux 发行版，容器都可能会逃逸。即使你的容器使用[用户名称空间](https://docs.docker.com/engine/security/userns-remap/)运行，或者作为非根用户运行，它们仍然可以被利用。Unit 42 为这些漏洞分配了常见漏洞和暴露(CVE) CVE-2021-3100、CVE-2021-3101、CVE-2022-0070 和 CVE-2022-0071。

也许“糟糕”这个词太温和了。开发后，这些是灾难性的漏洞。

## 新修复

幸运的是，Unit 42 和 AWS 联手用更新、更安全的补丁修复了这些补丁。到目前为止，还没有人在野外被这些洞袭击过。

如果你不想成为第一个——如果你关心你的公司或工作，这是一个你真的不想要的“第一”——你必须尽快安装修复版本。事实上，现在——是的，现在——禁用会很好。

您可以通过安装永久补丁或最新的热补丁来实现这一点。AWS 已经发布了每个热补丁解决方案的修复程序。一旦主机运行固定版本，容器转义或权限提升都不能用于您的系统。

## 要采取的步骤

对于热补丁，您需要采取以下步骤。

1.  log4j-CVE-2021-44228-hot patch[包](https://alas.aws.amazon.com/announcements/2021-001.html)的 1.1-16 版本，捆绑了热补丁服务。
2.  [Hotdog](https://github.com/bottlerocket-os/hotdog) 的 1.02 版本，基于开放容器倡议(OCI) hooks 的 Bottlerocket 主机热补丁解决方案。

然而，没有一种自动的方法来使用 kubernetes-log4j-CVE-2021-44228-node-agent[Daemonset](https://github.com/aws-samples/kubernetes-log4j-cve-2021-44228-node-agent)安装修复的热补丁。相反，你需要通过以下几道关卡:

1.  在独立主机上，您可以通过运行以下命令进行升级

$ yum 更新日志 4j-CVE-2021-44228-热补丁

对于基于 RPM 的发行版或使用 DEB 的发行版:

$ Sudo apt 安装-仅升级 log4j-CVE-2021-44228-热补丁

1.  更新:在通过 [hotpatch Daemonset](https://github.com/aws-samples/kubernetes-log4j-cve-2021-44228-node-agent) 为每个节点安装了热补丁的 Kubernetes 集群上，需要手动连接到每个节点，并通过 yum 或 apt 更新已安装的热补丁。请注意，仅删除热补丁 Daemonset 不会从节点中删除热补丁服务。
2.  热狗用户需要升级到[最新版本](https://github.com/bottlerocket-os/hotdog/releases)。

或者，如果您确定——我是说确定——您的环境针对 Log4Shell 安装了永久补丁，您可以通过运行以下命令在主机上禁用 Hotdog:

$ sudo touch/etc/log4j-CVE-2021-44228-hot patch . kill，

$ run API client set OCI-hooks . log4j-hot patch-enabled = false。

### 立即升级

Alta Vista 的 [Prisma Cloud](https://www.paloaltonetworks.com/cloud-security?utm_content=inline-mention) 客户可以在“漏洞”标签下识别受影响的主机。该平台检测热补丁包，并向运行易受攻击版本的虚拟机上的客户发出警报。

之所以这是一个首要问题，是因为 Log4Shell 是一个如此危险的 bug，用户经常大规模部署热补丁。运行不可信映像的多租户容器环境和集群尤其危险。

[我和 Palo Alto Networks](https://www.paloaltonetworks.com/cloud-security?utm_content=inline-mention) 鼓励您尽快升级到修复的热补丁版本。但是，如果您仍然在修补 Log4Shell，那么首先要优先考虑这项工作。是的，这很糟糕，但是 Log4Shell 可能更糟糕。所以，就像我之前说的，开始修补吧。它需要做。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>