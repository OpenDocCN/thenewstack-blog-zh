# Linux 发行版:一年回顾

> 原文：<https://thenewstack.io/linux-distros-year-in-review/>

2021 年对于云原生和开发者世界中的 Linux 发行版来说是非常激动人心的一年。两个 CentOS 替代者不仅发布了新的迭代，而且他们还达到了超过他们取代的平台的[的稳定性水平(](https://thenewstack.io/red-hat-deprecates-linux-centos-in-favor-of-a-streaming-edition/)[红帽](https://www.openshift.com/try?utm_content=inline-mention)在去年年底改变了 CentOS 的方向，使其更具实验性)。

虽然没有发布专门为云、容器和边缘用例构建的新发行版，但有大量针对其他操作系统的更新，增强了产品，使几乎每个 Linux 服务器发行版都对大多数企业和开发人员有广泛的吸引力。

因此，虽然表面上看起来好像只是另一年的“第二节与第一节相同”，但实际上远不止如此。多了多少？让我们进去看看。

## AlmaLinux

![](img/b2daafef051c6a72d4df188c21c6cbc1.png)

[AlmaLinux](https://almalinux.org/) 很快成为 [CentOS 的替代品，击败了](https://thenewstack.io/almalinux-captures-the-soul-of-centos/)。它不仅比其他任何产品都快，而且很快就迭代出新的版本，甚至通过 TuxCare 找到了享受商业支持的方法。回到 11 月，在 Red Hat 发布 Red Hat Enterprise Linux(RHEL)8.5 版本后不到 48 小时，开发人员发布了 alma Linux 8.5 版本。

8.5 中的新功能反映了 RHEL 8.5 中的新功能，包括对开发运维团队管理容器化工作负载的方式的改进、更新的编程语言(如 GCC 11、LLVM 12.0.1、Rust 1.54.0、Go 1.16.7、PHP 7.4.19、Ruby 3.0、Node.js 16)和组件(如 Squid 4.15、Mutt 2.0.7 和 Nginx 1.20A)、新的 SCAP 安全配置文件以及互联网安全中心的重组(如这个新配置文件现在包括工作站级别 1、工作站级别 2、服务器级别 1 和服务器级别 2。此外，安全技术实施指南(STIG)安全配置文件现在的版本是 V1R3。

还有很多其他的添加和改进，但可能最重要的是，2021 年证明了 AlmaLinux 已经成为 CentOS 最可靠的替代品之一。该发行版不仅是 RHEL 的 1:1 二进制替代品，而且社区也在蓬勃发展，支持也很容易获得。

## 洛基 Linux

![](img/a9aa82421a651cc386b9d1fe2f25bd0f.png)

[Rocky Linux](https://rockylinux.org/) 由 CentOS 的创始人[创建，它显示](https://thenewstack.io/centos-creator-gregory-kurtzer-discusses-his-new-distro-rocky-linux/)。如果你不知道任何更好的，没有品牌的地方，你会发誓这是 CentOS。并且在 2021 年 4 月 30 日，Rocky Linux 的第一个发布候选版本面世。差不多两个月后，第一个普遍可用的版本发布了(2021 年 6 月 21 日)。

那个版本是 8.4，基于(你猜对了)RHEL 8.4。因此，2021 年 11 月 16 日，开发人员发布了 8.5 版本，这也就不足为奇了，该版本与 RHEL 8.5 版本一致(并且包含了与 AlmaLinux 8.5 类似的一系列功能和改进)。8.5 的一些新增功能包括 GCC 11、LLVM 12.0.1、Rust 1.54.0、Go 1.16.7 和 OpenJDK 17。

Rocky Linux 8.5 增加的一个非常重要的特性是支持安全引导。这意味着 Rocky Linux 可以在任何需要安全引导认证密钥的硬件上运行。

像 AlmaLinux 一样，用户和开发人员现在可以从 Docker Hub 将 Rocky Linux 部署为容器映像，或者将其托管在第三方云服务上，如 AWS 或 Azure。

## Ubuntu 服务器

![](img/fb97635eb5b1b94e6861332272fec3f9.png)2021 年 10 月 14 日[Ubuntu Server 21.10](https://ubuntu.com/blog/ubuntu-server-21-10)(Impish Indri)发布。尽管不是一个长期的候选版本，21.10 对于原生云、容器和开发者来说有很多非常棒的特性。这个最新的迭代还扩展了 edge 用例，在 Ubuntu Server Live 安装程序中包含了一个最小系统安装选项。这个最小的安装只占用 100MB 的磁盘空间。

一个真正有趣的补充是 21.10 默认启用了`needrestart`。这个新特性在应用库更新后自动重启守护进程。`Needrestart`检查在库更新后哪些守护进程需要重新启动，并自动处理该任务。

对于那些依赖 GPU 设备处理重要工作负载的人，Ubuntu 21.10 为 Ubuntu KVM 上的 NVIDIA vGPU 软件 13.1 引入了认证驱动程序，主机和来宾驱动程序都可用于 Ubuntu 20.04 LTS 和 18.04 LTS。

## Fedora Linux

![](img/2b9dfb5447cc72d848ee654794c74d95.png)

[Fedora Server 35](https://getfedora.org/en/server/) 于 2021 年 11 月 2 日发布，包含一个面向众多用例(如服务器、云和物联网)的版本。除了对 Fedora Linux 桌面版的所有改进之外，针对云和服务器用例的发行版还增加了两个非常重要的内容。

首先，Fedora 35 云映像具有混合 BIOS+UEFI 引导支持，UEFI 和传统 BIOS 都支持作为后备。

下一个主要变化是切换到 Btrfs 文件系统，这是工作站和云版本的默认设置。通过这一更改，用户可以使用透明压缩(以节省存储空间)、快照、回滚等功能。

## 亚马逊 Linux 3

接近年底的时候，[亚马逊网络服务](https://aws.amazon.com/?utm_content=inline-mention)宣布将完全采用 Fedora Linux 作为他们基于云的[亚马逊 Linux](https://aws.amazon.com/linux/amazon-linux-2022) 的基础，这是一个更大的宣布。这个名为 AL2022 的新发行版使用 Fedora 作为其上游，因此它与 RHEL 保持一致。更好的是，AL2022 针对亚马逊 EC2 进行了优化，并集成了所有最新的 AWS 功能和工具。

AL2022 的一个非常独特的特性是，用户可以将其锁定到特定版本的亚马逊 Linux 包存储库。通过这样做，您可以坚持平台的一个特定迭代，并控制何时从一个版本转移到下一个版本。

AL2022 立即在所有商业地区提供免费预览版，可以从 AWS 管理控制台、AWS 命令行界面、AWS Tools for Windows PowerShell、RunInstances 或 AWS CloudFormation 模板启动。

## 红帽企业版 Linux

![](img/30857ce88e5dbff128a5a83e3bb09c03.png) 2021 年对于[红帽企业 Linux](https://www.redhat.com/en/technologies/linux-platforms/enterprise-linux) 来说是个好年景。即使竞争越来越激烈，它仍然能够作为企业业务的领先 Linux 发行版保持距离。最激动人心的消息之一是年底 RHEL 9 beta 版的全面上市。开发人员将大量精力集中在简化的自动化和管理上(通过大大增强的 web 控制台和更好的数据导出)，通过 web 控制台进行内核实时修补，从单个构建节点构建 RHE 8 和 9 映像的能力，大量安全性和合规性增强(如附加的安全性配置文件、详细的 SSSD 日志记录、OpenSSL 3 集成和默认禁用的 SSH root 登录)。

对于云原生和容器开发者来说，RHEL 9 附带了 cgroup2 和最新发布的 [Podman](https://thenewstack.io/deploy-a-pod-on-centos-with-podman/) 。

## 结论

对于服务器、云以及依赖于可靠、安全和灵活的操作系统的任何地方的 Linux 来说，这是一个好年景。如果您还没有迁移到 Linux，我强烈建议您看看这些发行版中的任何一个，以满足您的云、容器、边缘和物联网需求。虽然看起来它们中的许多只不过是一个主题的变体，但是您可能会发现其中一个比其他的更适合您的需求。请务必阅读更多关于每个发行版的信息，这样您就可以确定您使用的是最适合您业务的产品。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>