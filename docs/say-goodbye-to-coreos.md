# 向 CoreOS 说再见

> 原文：<https://thenewstack.io/say-goodbye-to-coreos/>

编者按:TNS 执行主编

[Joab Jackson](https://thenewstack.io/author/joab/)

促成了这篇文章。

对于任何喜欢使用 CoreOS Container Linux 的人来说，请在你的日历上标记 2020 年 5 月 26 日，因为这一天 Linux 发行版将到达其生命的尽头，并且不再接收更新。CoreOS 的开发者强烈建议用户立即开始将工作负载迁移到另一个平台。

[在 2018 年收购了 CoreOS](https://thenewstack.io/docker-acquiring-coreos-red-hat-aims-kubernetes-company/) 背后的公司红帽，将在 2020 年 9 月 1 日删除所有 CoreOS 图像。这意味着即使你想下载 CoreOS(没有支持的更新)，你也不能。

AWS Marketplace 中的 CoreOS Container Linux 列表已经为新用户移除。这一举措不会影响 AWS 上 Container Linux 的现有订户，也不会影响通过 CoreOS 下载页面上列出的 AMI IDs 启动 Container Linux

“我们要向多年来为 CoreOS 和 Container Linux 的成功做出贡献的用户、贡献者、合作伙伴和倡导者表示感谢，”Red Hat 在一份声明中断言，并感谢 Rackspace、DigitalOcean 和 Azure 早期对 CoreOS 的支持，以及 Geoff Levand 对 ARM64 port 的贡献。

CoreOS Linux(重命名为 CoreOS Container Linux)是一个开源的轻量级 Linux 操作系统，专门用于为集群部署提供必要的基础设施。它在 Linux 发行版中是独一无二的，因为它关注自动化、应用程序部署的简易性、安全性、可靠性和稳定性。它最初是在 2013 年 10 月发布的[。](https://thenewstack.io/its-beta-time-for-coreos-the-linux-distro-for-massive-server-deployments/)

当被问及 CoreOS 当时新颖的 CoreOS 自我更新方面时，CoreOS 创始人 Alex Polvi [在 2014 年告诉新堆栈](https://thenewstack.io/the-coreos-operating-system-as-a-service-is-new-and-thats-the-biggest-challenge/)“服务器没有这样的东西。如果你能在服务器上提供这样的补丁系统，这将是一件大事。它将提供大量的价值、安全性和性能。”

收购完成后，红帽将 CoreOS Container Linux 代码库集成到 OpenShift 中，命名为[红帽企业版 Linux](https://access.redhat.com/documentation/en-us/openshift_container_platform/4.1/html/architecture/architecture-rhcos) (RHCOS)

## 用户要做什么？

对于任何依赖 CoreOS 的人来说，还有其他选择吗？奇怪的是，CoreOS 的终结是在你猜对了， [Fedora CoreOS](https://getfedora.org/coreos/) 发布后不久宣布的。Fedora CoreOS 是 CoreOS 容器 Linux 的正式继任者。“Fedora CoreOS 是一个自动更新的最小操作系统，用于安全和大规模地运行容器化的工作负载，”根据官方描述。

Fedora CoreOS 将 CoreOS 的供应工具和自动更新模型与 Atomic Host 中的打包工具、OCI 支持和 SELinux 安全性结合在一起。

尽管 Fedora CoreOS 是 CoreOS 的官方替代产品，但仍有一些用例是它无法替代的，例如:

*   没有对 Azure、Digital Ocean、GCE、vagger 或 Container Linux 社区支持的平台的本机支持。
*   最初由 CoreOS 开发的 [rkt 容器运行时](https://thenewstack.io/coreoss-rkt-blazes-secure-trail-appc-containers/)不见了。

还应注意的是，尽管 Fedora CoreOS 确实提供了最佳稳定性，但它可能包含会破坏某些用例和/或工作负载的回归。

对于那些寻找非红帽替代品的人来说，应该看看[的 Flatcar Linux 项目](/flatcar-linux-the-coreos-operating-system-lives-on-beyond-red-hat/)，这是 CoreOS Container Linux 的一个[分支。](https://www.flatcar-linux.org/releases/)

有关从 CoreOS 切换到 Fedora CoreOS 的更多信息，请务必阅读[官方迁移说明](https://docs.fedoraproject.org/en-US/fedora-coreos/migrate-cl/)。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>