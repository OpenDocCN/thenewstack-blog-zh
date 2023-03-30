# 发现并修复了 Kubernetes 网络错误

> 原文：<https://thenewstack.io/kubernetes-networking-bug-uncovered-and-fixed/>

坏消息是，你可以安装更新版本的 Kubernetes。—您不能与您的工作节点联网。好消息是一位 Mirantis 工程师找到了一些修复方法并正在分享。

没有什么比建立一个全新的 [Kubernetes](https://kubernetes.io/) 集群，部署它，以及——管它呢！—您的工作节点失去网络连接。你不能嘘他们。你不能 ping 他们。他们“走了”

## 发现问题

当然，它们实际上并没有消失；你就是无法接近他们。在九月中旬发现[问题后，开始寻找问题。](https://github.com/kubernetes/kubernetes/issues/112477)

原来问题是默认的 Linux 防火墙程序 iptables 与你安装的 iptables kube-router 1.25 版本有冲突。

问题的核心是 [iptables 1.8.8 在一些规则上破坏了与旧版本的兼容性](https://bugzilla.netfilter.org/show_bug.cgi?id=1632)。在 iptables 1.8.8 中创建新的"-m mark "规则时，旧版本的 iptables 无法正确读取它:这实际上是一个预期的结果。根本原因是较新的 iptables-nft 使用原生的 [nftables](https://netfilter.org/projects/nftables/) 表达式来匹配包标记，而较旧的 iptables-NFT 使用内核中的 [xtables 扩展](https://www.netfilter.org/projects/xtables-addons/index.html)。netfilter 的开发者并不希望用户运行两个不同版本的 iptables。当然，对于容器，这种情况经常发生。

哎呦！

正如 [Mirantis](https://www.mirantis.com/) 软件工程师 [Jussi Nummelin](https://www.linkedin.com/in/jnummelin/?originalSubdomain=fi) 解释**，**“如果主机正在使用 iptables 1.8.8，当像 kube-router CNI 这样的组件开始用旧版本的 iptables 编写自己的网络策略和规则时——kube-router 附带 iptables 1 . 8 . 7——事情会变得很棒！因为 kubelet 通过主机提供的 iptables 1.8.8 写道:

-A KUBE 防火墙-m 注释-注释“kubernetes 防火墙丢弃标记的数据包”-m 标记-标记 0x8000/0x8000 -j 丢弃

然后，kube-router 使用 kube-proxy 提供的早期版本的 iptables，执行正常的 iptables-save；修改/添加规则；iptables-restore，但是对旧版本执行此操作会导致读取并重新插入规则，如下所示:

-KUBE 防火墙-m 注释-注释“kubernetes 防火墙丢弃标记的数据包”-j DROP

明白了吗？作为一个古代的网络管理员，我来解释一下会发生什么。因为该规则已“损坏”，所以它会阻止主机上的所有网络流量。或者，正如 Nummelin 所说的，**当你甚至不能再 ping 本地主机时，你就知道你有麻烦了。**

 **阿门。

此外，Nummelin 解释说:“虽然在这个特定的案例中，我们使用 kube-router，但所有这些实际上都可能发生在任何其他在 pod/containers 中使用 iptables 的网络组件上:

为什么是的，网络在 Kubernetes 非常脆弱。

解决方法是“确保每个网络组件实际上都使用与主机相同版本的 iptables，并且所有这些组件都使用相同的后端(传统与 nftables)。”

那么为什么我们需要相同的版本呢？“库伯内特公司就不能赔偿吗？不，不，它不能。Nummelin 说，这是因为“netfilter 团队真的没有任何版本兼容性的保证。(具体来说，iptables 团队不能保证向后兼容，因为它是一个前容器时代的工具，它是建立在主机上永远不会有多个 iptables 版本的假设之上的。"

这是公平的。Netfilter 和 IPTable 毕竟要追溯到 1999 年。而且，如果你认为他们不好，你从来没有使用他们的前身，ipchains。

## 解决方法

那么你能做什么呢？

在 [k0s](https://k0sproject.io/) 、 [Mirantis](https://thenewstack.io/mirantis-builds-a-data-center-as-a-service-on-kubernetes-with-flow/) 的 Kubernetes 发行版中，他们通过以下方式缓解了这个问题:

*   使用 [iptables-wrappers](https://github.com/kubernetes-sigs/iptables-wrappers) 脚本检测 iptables 模式:这给了我们以相同模式工作的最大可能性。
*   将 iptables 二进制文件与 k0s 一起发布:这样，操作系统升级就不会出问题，因为 k0s 从不依赖操作系统提供的版本。
*   将 iptables 1.8.7 与 k0s 一起发布:这样，我们与其他组件保持同步，并且我们实际上测试了这些组合。

如果您没有使用 k0s，您还有几个其他选项:

*   将主机上的 iptables 降级到 1.8.7 以消除不兼容性。
*   用[–feature-gates = IPTablesOwnershipCleanup = true](https://github.com/kubernetes/enhancements/issues/3178)运行 kubelet，这将导致它不创建有问题的“-j DROP”规则。正如[丹·温希普](https://github.com/danwinship),@丹·温希普在 Github 上指出的，“当然，[这是一个 alpha 特性](https://github.com/kubernetes/kubernetes/issues/112477#issuecomment-1274589824)，你可能会遇到一些组件的问题，假设 kubelet 仍然创建那些规则，但是如果你这样做了，那么你可以报告它们并帮助 KEP 向前发展。”

我通读了 GitHub 对 Kubernetes 和 IPTables 的评论。一言以蔽之，“乱七八糟”，而且我看不到一个能让 Kubernetes 用户满意的修复方案会很快出台。所以，就目前而言，我认为将主机 iptables 降级到 1.8.7 是你最好的选择。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>**