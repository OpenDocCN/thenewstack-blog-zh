# 大卫·弗拉纳根在修复库伯内特星团时学到了什么

> 原文：<https://thenewstack.io/what-david-flanagan-learned-fixing-kubernetes-clusters/>

人们是卑鄙的。这是[大卫·弗拉纳根](https://www.linkedin.com/in/rawkode/?originalSubdomain=uk)通过在他的 YouTube 系列节目《 [Klustered](https://www.youtube.com/@RawkodeAcademy/videos) 》中修复 50 多个故意损坏的 Kubernetes 集群而学到的第一件事

在一个案例中，提交者用 unicode 二重奏替换了一个“c”字符——它看起来与终端输出中的 c 相同——从而导致了一个错误，导致弗拉纳根怀疑自己和自己修复集群的能力。

“我真的很讨厌那个家伙，”弗拉纳根上周在坦帕举行的 Civo Navigate 会议上坦言。“这是一个很长的插曲，我们花了近两个小时试图解决这个问题。我喜欢这个片段——因为我向你保证，我很聪明，而且我很擅长处理[Kubernetes](https://thenewstack.io/key-concepts/kubernetes/)——但是它让我怀疑我知道不是错误的事情。事实上，我认为一个六位数会在 64 位系统上引起任何形式的溢出——当然不会。但是调试很难。”

在那场演出之后，Klustered 采取了一项没有 Unicode 中断的政策。

弗拉纳根说:“只有当事情出错时，你才会学到东西。”。“这就是为什么我真的喜欢做 Klustered。如果你只有一个能正常工作的集群，你永远不会真正学会如何在超过一定规模的情况下操作它。Klustered 为我们带来了一种情况，我们可以让人们从自己的公司、自己的组织、自己的团队中带来他们的失败，我们在直播格式上复制这些问题，但它也允许我们看到个人如何调试它。”

## Linux 问题

他说，调试是困难的，即使你有一个来自红帽的团队在解决问题，他在另一集讲述红帽和塔罗斯的团队时学到了这一点。在这种情况下，Red Hat 从重要的二进制文件中删除了可执行位，如 kubectl、kubeadm，甚至 Perl——它有能力在一台机器上执行大多数 Sys 调用；限制了塔罗斯修复故障的能力。

“从这一集我们学到的是，你实际上可以在 Linux 上执行动态链接器。我们有了 ld-linux，所以你可以在一台机器上执行任何二进制代码，通过链接器代理它。所以你可以像这样 bin.chmod，这是一个非常酷的技巧。”
`/lib/ld-linux.so  /bin.chmod +x /bin/chmod`

人们还修改了 Linux 文件系统的属性。

"有人知道 Linux 文件系统有什么属性吗？"他问。“不，当然不是。你凭什么？”

但是这些属性允许您获得真正低级的文件系统。他展示了他们如何将一个文件标记为不可变的。

“所以你可以打包一个你知道的文件， [kubectl](https://thenewstack.io/kubecost-monitor-kubernetes-costs-with-kubectl/) 或 Kubernetes 必须写入并标记为不可变的，你马上就破坏了系统，”他说。“您不能通过运行常规的 LS 命令来检测这种中断，您实际上需要对文件进行 lsattr，并在您列出这些晦涩的引用时理解它们的含义。所以，再说一次，Klustered 只是给了我们一个环境，让我们能够从那些做过我们以前没有做过的事情的人那里提取所有这些知识。”

在另一集里，他有[克里斯·诺瓦](https://github.com/krisnova)，一个在安全和 Kubernetes 工作的内核黑客，还有[托马斯·斯特罗姆贝里](https://stromberg.org/t/)，一个 minikube 而 [Google](https://thenewstack.io/run-a-google-kubernetes-engine-cluster-for-under-25-month/) 的前维护者，他也从事入侵的法庭分析。斯特罗姆贝里不得不由 Nova(一个安全行业精英)来修复这个破碎的集群。

“托马斯过来指挥 FLS，”他说。“这是一个非常老的工具包，写于 90 年代末，叫做 [Sleuth Kit](http://www.sleuthkit.org/sleuthkit/man/fls.html) ，它对 Linux 文件系统进行取证分析。”

通过运行这个命令，他获得了对 Linux 文件系统的每一次修改的时间顺序变更。在过去的 48 小时里，他想回答的每个问题都有了答案…所以我很高兴我们有这些机会与大家分享知识，”他补充道。

## 网络中断常见

网络中断在那个节目中经常出现。Kubernetes 制定了核心网络政策来防止这种情况发生……但它还是发生了。

“然而，我们现在看到了分裂，因为其他 CNI 供应商带来了自己的适应网络政策，”弗拉纳根转述。“仅仅检查网络策略或群集网络策略是不够的。…你需要知道如何从网络层面成功运营 Kubernetes 集群，它会继续发展，变得非常麻烦、可怕、复杂，但也更容易。”

弗拉纳根对 Kubernetes 最大的不满是默认的 DNS 政策。

“谁认为 Kubernetes 中的默认 DNS 策略是默认 DNS 策略？现在我们有了这个叫做默认的 DNS 政策，”他说。“但这不是默认。默认情况下是集群优先，这意味着它将尝试在集群内解析 DNS 名称。默认策略实际上会解析为主机上的默认路由。”

弗拉纳根说，他一直在与 Tom Hockin 和 Kubernetes 的其他评论者讨论社区如何消除一些异常现象，这些异常现象实际上是在绊倒那些以前没有遇到过这些问题的人。

## Ebpf 改变景观

他说， [eBPF](https://ebpf.io/) 也正在改变这一景观。而不是进入一台 Linux 机器，运行 IP tables -l，他注意到这在过去的 20 年中已经根深蒂固地存在于开发人员的头脑中。现在开发人员应该监听所有 eBPF 探测和流量策略。本质上，您需要其他 eBPF 工具来理解现有的 eBPF 工具。

他建议去哈勃看看旧网络政策的可视化展示——特别是 Kubernetes 和 Cilium，他补充道。哈勃也配备了 CLI。

“我们拥有了解集群内网络的工具。如果你足够幸运，正在使用纤毛，如果你正在使用其他 CNI，你将不得不寻找其他工具，但它们也确实存在，”他说。

他还推荐了[纤毛编辑器](https://editors.cilium.io)。

弗拉纳根说:“你可以通过拖动框、改变标签和改变端口号来建立 Kubernetes 网络策略或 Cilium 网络策略。”"所以你实际上不再需要学习如何浏览这些深奥的 YAML 文件了."

他说，Ciluim 编辑器将允许你使用拖放操作来建立一个 Kubernetes 网络策略。

## 其他学习

当然，还有其他方法来打破 Kubernetes 集群。他指出，你可以攻击容器运行时。人们已经回滚了多达 25 个版本的 kubectl 二进制文件；25 版本实际上破坏了向后兼容性，因此它不能与 API 服务器通信。他补充说，存储是你自己的 CSI 提供商的另一个考虑因素。

他还推荐了三个资源:
[布伦丹·格雷格的](https://www.linkedin.com/in/brendangregg/?originalSubdomain=au) [书；](http://Brendangregg.com/bpf-performance-tools-book.html)T11[密件抄送](https://github.com/iovisor/bcc)；
[Ebpfkit；](https://github.com/Gui774ume/ebpfkit)

他想让工程师们承认他们不知道的事情并分享知识。

他说:“我给人们的一条规则是，请不要静静地坐在那里，用谷歌搜索相机来得到答案，然后说，哦，我知道如何解决这个问题。”“我希望让高级工程师为我们行业的新来者设定更好的标准，并消除我们在过去 30 年里建立的英雄文化。”

Civo 支付了 Loraine Lawson 参加会议的差旅费和住宿费。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>