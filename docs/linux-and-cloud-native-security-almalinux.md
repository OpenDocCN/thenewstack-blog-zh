# Linux 和云本地安全性:AlmaLinux

> 原文：<https://thenewstack.io/linux-and-cloud-native-security-almalinux/>

本周，新的 Stack 发布了一系列文章，研究 Linux 发行商如何保护他们的发行版，以实现云原生操作。今天，我们来看看 AlmaLinux。

继续我的关于 Linux 的云原生安全性的系列问答，我联系了 AlmaLinux 的创建者，讨论它如何支持 Linux 上的安全云原生操作。

在[红帽](https://www.openshift.com/try?utm_content=inline-mention)的 CentOS 从标准版本转向滚动版本之后，AlmaLinux 发布了，这一事件引起了企业 Linux 社区的重大转变。这个行业的宠儿之一消失了，取而代之的是许多替代品。

AlmaLinux 是第一批这样的替代品之一，它很快上升到了顶端。我联系了 AlmaLinux，聊了聊云原生安全性的问题，AlmaLinux 撰稿人兼云/容器工程师 [Bala Raman](https://github.com/srbala) 回复了我。

**云原生开发者面临的最大安全问题是什么？**

![](img/dcb8997cc1b7c48fb80fb4261f84e617.png)

Bala Raman，AlmaLinux 贡献者和云和容器开发者

洋葱的层次。云原生开发增加了多维层的复杂性，例如云节点操作系统、云软件、应用容器操作系统，然后是应用平台和应用本身。每一层都有自己的安全问题和缓解措施。由云原生开发者处理所有这些是最大的挑战。

**如果您能给希望尽可能安全地部署容器的企业一条建议，那会是什么？**

使用平台即服务(PaaS)、软件即服务(SaaS)和功能即服务(FaaS)来帮助将管理安全性的负担转移给服务提供商，开发人员可以专注于他们的应用程序开发和使用。

**alma Linux 在云/容器安全方面与其他服务器操作系统有何不同？**

AlmaLinux 云映像和容器的构建更加频繁，包括增强和安全更新。此外，还在不断努力实现自动化的云映像和容器发布，例如，当高 CVE 安全修补程序可用时，它们会自动构建并发布。

**云原生开发的未来是什么样子的？**

将会有更多的基于浏览器的 Web IDEs 用于开发。GitOps 将在未来的云原生开发中扮演重要角色。GitHub/GitLab 行动将成为这些发展的综合驱动因素。应用程序开发周期会更短，但更容易出错。

**管理员应该对服务器操作系统做的第一件事是什么？**

首先是基本的，比如更改任何默认密码(云映像中的 root 用户)。应用操作系统更新、补丁包和安全补丁。移除未使用的、不需要的包装。尽可能利用 sudoers 并锁定 root。保持操作系统防火墙锁定，只打开必要的防火墙规则。在 AlmaLinux 上，可以通过在安装时应用安全配置文件来实现这种自动化，例如遵循我们的[互联网安全基准中心](https://www.cisecurity.org/cis-benchmarks/)。

**中小型企业如何获得企业中的安全级别？**

使用开源安全工具进行扫描和监控非常有帮助。将这些步骤整合到 CI/CD 流程中，如代码扫描和集装箱安全分析等。与 PaaS、SaaS 或 FaaS 的混合和搭配大有裨益。

**容器开发者能做的最好的事情是什么，以确保他们建立一个坚实安全的基础？**

遵循 Docker/container 的最佳实践，比如保持容器映像最少，仅够运行需要的应用程序。这也是我们发布[[Red Hat Universal Base Images](https://almalinux.org/blog/almalinux-container-images-update-full-rhel-ubi-compatibility/)]等价容器集的部分原因。在这种情况下，使用 AlmaLinux 微型和最小图像会很方便。使用 Docker 多级构建和像 [buildah](https://buildah.io/) 这样的构建工具来获得更好的优化和安全性。

**从你的角度来看，供应链安全问题的答案是什么？**

一个潜在的解决方案是从代码合并一直到最终构建的可验证的构建管道。我们正在考虑为我们的构建过程做这样的事情，以便与 ImmuDB(一个不可变的数据库)集成。它在供应链流程管理中提供了区块链式的完整性，并能极大地提高安全性。

**在未来几个月或几年内，AlmaLinux 最酷的 cloudnative 技术是什么？**

AlmaLinux 已经有了亚马逊网络服务、谷歌云、Azure、流浪者、LXC/LXD 和 OpenNebula 的云图像。AlmaLinux 容器图片可在 Docker Hub、Quay.io 和亚马逊 ECR 公共图库中获得。我们针对 Raspberry Pi 的新 AlmaLinux 操作系统更新现在也可以使用了。

这些都为 AlmaLinux 在物联网设备中的应用提供了更多的可能性。

我们还在计划基于 AlmaLinux 的软件和针对 Go、Node.js 和 Java 的特定应用 Docker 容器，它们将很快推出。这些容器映像对于从开发到部署的一切都是很好的补充。

**企业应该努力实现完全自动化，还是应该在开发运维流程中保留一层人工干预？**

选择二。AI/ML 驱动的自动化与 GitOps 将是一个很好的契合点:采用自动化，并对确认、验证和批准进行检查和平衡。总会有人在开发自动化，所以我们也不要忽视这一点。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>