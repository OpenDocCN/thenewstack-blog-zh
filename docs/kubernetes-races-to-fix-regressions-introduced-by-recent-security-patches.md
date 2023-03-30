# Kubernetes 竞相修复最近的安全补丁带来的倒退

> 原文：<https://thenewstack.io/kubernetes-races-to-fix-regressions-introduced-by-recent-security-patches/>

Kubernetes 最近收到了两个严重漏洞的补丁，这两个漏洞可能允许攻击者绕过安全屏障，从主机系统中读取、写入或删除文件。然而，这些补丁似乎导致了功能退化，迫使开发人员推出新的版本来解决其中的一些问题。

第一个漏洞[被跟踪为 CVE-2017-1002101](https://github.com/kubernetes/kubernetes/issues/60813) ，在某些配置中，可以用于获取对 pod 中指定的卷之外的任意文件的读写访问权限，包括主机文件系统上的文件。

“这可以通过任何卷类型来实现，包括 emptyDir，并且可以通过非特权 pod(受文件权限限制)来实现，”Kubernetes 开发人员在他们的建议中写道。

该漏洞位于子路径卷装载中，已在 3 月 12 日发布的 Kubernetes 版本 1.7.14、1.8.9 和 1.9.4 中修复。利用该漏洞需要“结合恶意容器行为的特制 pod 规范”

易受攻击的配置包括“允许不受信任的用户控制 pod 规范内容并使用 PodSecurityPolicy(或自定义准入插件)阻止通过主机路径卷(或其他卷类型)访问主机文件系统的群集”和“使用带有不受信任的容器或可能受到危害的容器的子路径卷装载的群集”

红帽[修补了其 OpenShift 容器平台中的漏洞](https://access.redhat.com/security/cve/cve-2017-1002101)，并在 CVSS 等级上给了它 7.2(高)的严重性分数。Twistlock 的安全研究人员将其描述为 Kubernetes 有史以来报道的最严重的安全漏洞之一，并在[发表了一篇博客文章](https://www.twistlock.com/2018/03/21/deep-dive-severe-kubernetes-vulnerability-date-cve-2017-1002101/)，解释了如何利用该漏洞。

第二个漏洞[被确定为 CVE-2017-1002102](https://github.com/kubernetes/kubernetes/issues/60814) ，也被红帽[评为高严重性](https://access.redhat.com/security/cve/cve-2017-1002102) (CVSS 7.1)，因为它允许使用 secret、configMap、projected 或 downwardAPI 卷的容器触发节点主机上任意文件和目录的删除。这个操作是由 Kubelet 进程执行的，它以 root 用户身份运行，因此任何文件都是公平的。

Twistlock 的研究人员 Nitsan Bin-Nun 说:“修复错误的最佳做法是升级集群，否则应该禁用 Secrets、configMap、downwardAPI 和 projected volumes。”"升级会以只读方式装载这些卷，并且会导致写调用失败。容器将需要相应地更新。”

修复缺陷，特别是 CVE-2017-1002101，需要改变设计，这产生了引入功能回归的影响，导致某些集装箱配置出现问题。Kubernetes 团队正在解决这些问题，并已经发布了两个新版本来修复最严重的问题(1.7.15、1.8.10、1.9.5 和 1.9.6)。在 GitHub 上的[这个伞票](https://github.com/kubernetes/kubernetes/issues/61563)中跟踪回归。

Twistlock 的 Bin-Nun 说:“如果升级不是一个选项，可以使用一个快速的方法:使用 PodSecurityPolicy 对象来限制容器创建权限，并完全禁用 hostPath 卷。”

红帽 OpenShift】有一篇关于升级的博客文章，谷歌也在它的 Kubernetes 引擎的[发布说明](https://cloud.google.com/kubernetes-engine/release-notes)中有说明。

[红帽](https://www.openshift.com/)和[扭锁](https://www.paloaltonetworks.com/prisma/cloud)是新堆栈的赞助商。

通过 Pixabay 的特征图像。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>