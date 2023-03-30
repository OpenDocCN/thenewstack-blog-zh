# CNCF 网络研讨会:最近发现的五个 Kubernetes 安全漏洞

> 原文：<https://thenewstack.io/cncf-webinar-five-recently-unearthed-kubernetes-security-vulnerabilities/>

随着 Kubernetes 越来越受欢迎，它吸引了更多安全研究人员的注意，他们调查该软件寻找弱点。像任何软件一样，肯定会发现大量的错误，其中一些攻击者可以用来渗透甚至控制一个集群。在最近一次来自[云本地计算基金会](https://www.cncf.io/)的网络研讨会中，Kubernetes 安全提供商 [Alcide](https://www.alcide.io/company/) 的创始人 [Gadi Naor](https://www.linkedin.com/in/gadinaor/?originalSubdomain=il) 总结了 Kubernetes 最近的五个漏洞——其中一个是 CNCF 花了六个多月时间提醒 K8s 用户的。

通用漏洞和暴露(CVE)数据库，[识别并评估](https://thenewstack.io/cvss-struggles-to-remain-viable-in-the-era-of-cloud-native-computing/)最近披露的软件漏洞。Naor 说，它们为最终用户提供了有用的信息，最终用户应该对他们环境中的每个漏洞或弱点相关的“风险或爆炸半径”有很好的了解。

最近的两个漏洞涉及 Kubernetes 控制平面:

*   (https://cve.mitre.org/cgi-bin/cvename.cgi CVE 2020-8555 号？名字= CVE-2020-8555):Kubernetes**kube-controller-manager**可以通过服务器端请求伪造(SSRF)的方式进行攻击。Kubernetes kube-controller-manager 实现了对负载平衡、存储等服务的特定于云的调用。该攻击通过 HTTP 重定向到攻击者选择的资源来欺骗控制管理中心，例如，提供从元数据 API 服务器或元素提取信息的能力。
*   (https://cve.mitre.org/cgi-bin/cvename.cgi CVE 2020-8559？name=CVE-2020-8559):该漏洞提供了一种将权限从一个节点提升到整个集群的方法，即通过向 **kube-apiserver** 发送未经验证的重定向，这将允许攻击者将权限从一个节点危害提升到整个集群。

其他三个涉及存在于节点层的漏洞:

*   (https://cve.mitre.org/cgi-bin/cvename.cgi CVE 2020-8557 号？name=CVE-2020-8557):这个漏洞可以在一个 pod 内完成，它可以通过拒绝服务(DOS)攻击来关闭整个节点。原因:Kubernetes kubelet 不考虑写入其自己的 */etc/hosts* 文件的 pod 的磁盘使用情况，允许该 pod 用数据填充磁盘。
*   (https://cve.mitre.org/cgi-bin/cvename.cgi CVE 2020-8558 号？name=CVE-2020-8558):这是一种“中间人”(MitM)攻击，可以在 0.8.6 版之前的所有版本的*容器网络/插件*中使用。恶意容器可以向主机或其他容器发送恶意 IPv6 路由器广告，将流量重定向到恶意容器。此漏洞绕过了本地主机信任边界。Naor 说:“本质上，攻击者可以从相邻的 pod，甚至从主机本身向本地主机地址 127.0.0.1 发送流量。
*   (https://cve.mitre.org/cgi-bin/cvename.cgi CVE 2020-10749？name=CVE-2020-10749):另一种 MitM 攻击，它使用 IPv6 路由器广告来欺骗转发代理，如 Calico 或容器网络接口(CNI)，将原始流量发送到主机。即使不使用 IPv6，攻击者也可以在 Linux 中获得工作堆栈。实际上，他们可以通过操纵底层转发平面来劫持流向附近 pod 的流量。

现在，更多的漏洞正在被引入，Kubernetes 产品安全委员会正在努力跟上。Naor 报道说，微软在 12 月提交了 CVE-2020-8555 的错误报告，但直到 6 月 K8s 用户才被告知此事。通常，安全委员会在漏洞公开之前会要求一段时间，以便在攻击者发现之前修复它。在这种情况下，禁运时间因 COVID 疫情号的中断而延长。Naor 说，结果是 K8s 系统“在很多很多个月里都很脆弱”。

[https://www.youtube.com/embed/Dp1RCYCpyJk?start=1647&feature=oembed](https://www.youtube.com/embed/Dp1RCYCpyJk?start=1647&feature=oembed)

视频

云计算原生计算基金会是新堆栈的赞助商。

来自 Pixabay 的 Alexander Antropov 的专题图片。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>