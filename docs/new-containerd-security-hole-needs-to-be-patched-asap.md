# 新集装箱的安全漏洞需要尽快修补

> 原文：<https://thenewstack.io/new-containerd-security-hole-needs-to-be-patched-asap/>

如今，我们大多数人都在使用 [containerd](https://containerd.io/) 运行时来管理容器的生命周期。毕竟，它是 [Docker](https://www.docker.com/) 和许多[常见 Kubernetes 配置](https://thenewstack.io/open-standards-and-the-role-of-containerd-in-kubernetes-orchestration/)的基础。当然，这意味着我们需要特别关注任何可能的容器安全问题。唉，英国安全公司 [NCC Group](https://www.nccgroup.com/us/) ，揭露了一个潜在的危险: [CVE-2020-15257](https://nvd.nist.gov/vuln/detail/CVE-2020-15257) ， [containerd-shim API 暴露给主机网络容器](https://research.nccgroup.com/2020/11/30/technical-advisory-containerd-containerd-shim-api-exposed-to-host-network-containers-cve-2020-15257/)。

containerd-shim 是由 containerd 生成的二进制文件。它充当容器的父容器。它实现了容器生命周期和重新连接逻辑。这反过来使用 containerd shim API 作为到 containerd 的网络连接。到目前为止，一切正常。

但是，这个连接进程的有效 UID 为 0——也就是 root——但是没有限制对其域套接字的访问。哎呦。由于这一点，具有主机网络的非用户命名空间容器可以访问此 API，并导致 containerd-shim 执行危险的操作和旋转任意特权容器，从而使容器溢出并升级到主机上的完全根权限。

我说哎哟了吗？我再说一遍:哎呦。

没有什么比安全漏洞更能让攻击者相对容易地获得 root 权限，从而引起人们的注意。

当然，最好的做法是使用减少的特权集、非零 UID 和隔离的名称空间来运行容器。事实上，containerd 的维护者强烈反对与主机共享名称空间。也就是说，我见过太多容器以 root 身份运行。如果您没有实践良好的安全性，您可能会受到攻击。

正如 [Red Hat](https://www.redhat.com/en) security 所说，即使 [OpenShift](https://www.openshift.com/) 使用 [cri-o](https://cri-o.io/) 容器运行时并因此免疫，“这可能[允许恶意容器在与 shim 相同的网络名称空间中运行，有效 UID 为 0](https://access.redhat.com/security/cve/cve-2020-15257) 但权限降低，从而导致新进程以提升的权限运行。该漏洞对数据机密性和完整性以及系统可用性的威胁最大。”

因此，红帽“授予”这个漏洞一个通用漏洞评分系统(CVSS)8.8 分。这很高。虽然它可能不在“立即修复”的关键评级中，但已经足够令人担忧了。

那么，你能做些什么呢？首先，它已经在 containerd 1.3.9 和 1.4.3 中得到修复。这些补丁是最近发布的。您应该尽快更新到这些版本。在修复之前，您还必须重新启动任何启动的容器。这是因为旧的运行容器即使在升级后也仍然容易受到攻击。

当你这样做的时候，停止在根网络名称空间中作为根运行容器。即使你现在打了补丁，躲过了这一劫，当下一个严重的容器安全漏洞出现时，你可能就没那么幸运了。

kiwikong de Pixabay 的特征图像。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>