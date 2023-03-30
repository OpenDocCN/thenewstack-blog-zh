# Kube-hunter: Aqua 的新开源工具，用于搜索 Kubernetes 安全问题

> 原文：<https://thenewstack.io/kube-hunter-aquas-new-open-source-tool-for-hunting-kubernetes-security-issues/>

集装箱安全公司 [Aqua Security](https://www.aquasec.com/) 开源了一款名为 [Kube-hunter](https://kube-hunter.aquasec.com/) 的工具，帮助搜索 Kubernetes 集群中的安全问题。

在[的博客文章](https://blog.aquasec.com/kube-hunter-kubernetes-penetration-testing)中，技术传道者 [Liz Rice](https://twitter.com/lizrice?ref_src=twsrc%5Egoogle%7Ctwcamp%5Eserp%7Ctwgr%5Eauthor) 将 Kube-hunter 比作自动化渗透测试(pentesting)。还有一个[网站](http://kube-hunter.aquasec.com/)，在那里你可以注册获得一个令牌来在线查看和分享结果。该工具还提供了针对各种漏洞的补救建议。

用 Python 写的源代码可以在 [GitHub](https://github.com/aquasecurity/kube-hunter) 上获得。

Kube-hunter 可以作为容器在你的集群之外的任何机器上运行——该公司警告说，它只能在你自己的集群上运行。提供集群的域名或 IP 地址，kube-hunter 会在域或地址范围内搜索与 Kubernetes 相关的开放端口，并测试可能暴露给黑客的配置问题。与主机网络一起运行，它将能够仔细检查主机上的所有接口

它也可以在集群中的机器上运行。第三种选择是在集群中作为一个单元运行，如果其中一个应用单元受到威胁，它可以报告暴露风险。

它的默认状态仅用于被动搜索，并执行诸如搜索 SSL 证书的电子邮件和检查打开的端口、代理服务或仪表板等任务。在活动状态下，猎人可能会在集群上进行状态改变操作，这促使公司警告用户在使用它时要非常小心。在活动状态下，Kube-hunter 将利用它发现的漏洞来探索进一步的漏洞。

它提供了三个选项:远程扫描，内部扫描和网络扫描。用户将能够看到测试运行的列表，无论是被动还是主动模式，并设置他们想要看到的日志记录级别:调试、信息(默认)或警告。映射选项允许用户仅查看网络中节点的映射。

Kube-hunter 网页列出了漏洞、严重性、用户环境的详细信息以及用户可以与组织中的其他人共享的 URL。

Kube-hunter 增强了 Aqua 一直致力于的另一个开源项目:kube-bench 项目。这是一个 Go 应用程序，它检查 Kubernetes 的部署是否符合互联网安全中心[为 Kubernetes](https://www.cisecurity.org/benchmark/kubernetes/) 制定的基准中定义的最佳实践。

[https://www.youtube.com/embed/DYDoGYWk_rk?feature=oembed](https://www.youtube.com/embed/DYDoGYWk_rk?feature=oembed)

视频

赖斯和纽约大学坦登工程学院计算机科学与工程副教授贾斯汀·卡波斯最近在哥本哈根 KubeCon+CloudNativeCon 录制的一集关于 Kubernetes 安全性的讨论中加入了 TNS 创始人亚历克斯·威廉姆斯。

[安全为 Kubernetes](https://thenewstack.simplecast.com/episodes/security-for-kubernetes)

[Aqua Security](https://www.aquasec.com/) 是新堆栈的赞助商。

特征图片:[1897 年由 FrédérIC Christol(1850-1933)出版的赫尔蒙附近一个洞穴](https://www.flickr.com/photos/vintage_illustration/29087257497/in/photolist-LjkNgB-phxkF9-SJfVKM-29z8oh-Qg754h)里的古画。根据 CC BY-SA 2.0 获得许可。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>