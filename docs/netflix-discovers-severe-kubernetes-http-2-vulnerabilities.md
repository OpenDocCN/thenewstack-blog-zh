# 网飞发现了严重的 Kubernetes HTTP/2 漏洞

> 原文：<https://thenewstack.io/netflix-discovers-severe-kubernetes-http-2-vulnerabilities/>

看看互联网的 HTTP/2 协议是如何工作的，网飞的工程师在 Kubernetes 的 T3 中发现了 T2 的一系列漏洞。主要问题是在 Go 语言的 net/https 库中发现的。因为它是在这个特定的库中找到的，所以 Kubernetes 的每个版本和每个组件都会受到影响。Kubernetes 产品安全委员会将这两个问题的基本得分定为 7.5 分(严重程度很高)。这两个漏洞是:

*   **T5【CVE】2019-9512 平洪水。**这使得攻击者能够向 HTTP/2 对等方发送连续的 ping 请求，导致对等方创建内部响应队列。发生这种情况时，服务器的 CPU 和内存会被消耗，从而导致拒绝服务。
*   **[CVE-2019-9514](http://web.nvd.nist.gov/view/vuln/detail?vulnId=CVE-2019-9514) 重置洪水。**这使得攻击者能够打开多个流，这些流用于发送无效请求，以从对等方请求 RS_STREAM 帧。如果对等体不正确地对 RST 流帧进行排队，服务器的 CPU 和内存就会被消耗，从而导致拒绝服务。

所有八个漏洞都会影响 Kubernetes。虽然这些仍在等待 NIST 的分析，但 Kubernetes 已经发布了补丁，这些补丁出现在以下版本中:

*   kubernetes v 1 . 15 . 3–go 1 . 12 . 9
*   kubernetes v 1 . 14 . 6–go 1 . 12 . 9
*   kubernetes v 1 . 13 . 10–go 1 . 11 . 13

用户将 Kubernetes(通常缩写为“K8s”)的每个实例升级到上述迭代之一是至关重要的，否则，他们将容易受到攻击。当然，如何升级 Kubernetes 实例将取决于它们是如何部署的(在数据中心服务器上，通过 Google Cloud、AWS 等。).请务必查阅 Kubernetes 官方文档，了解您的部署的升级过程。

## 这些漏洞是如何工作的

每个 Kubernetes 漏洞都是通过以下步骤发挥作用的:

*   恶意客户端请求易受攻击的服务器执行 X 操作，从而生成响应。
*   客户端拒绝阅读响应。
*   拒绝操作服务器的队列管理代码。
*   如果服务器处理队列的方式很差，那么在处理请求时，客户机会迫使服务器消耗过多的 CPU 周期和内存。

上述步骤会造成拒绝服务，从而导致服务器停机。

值得注意的是，漏洞(如网飞所述)不允许攻击者修改或泄露敏感信息。相反，发现的缺陷允许在易受攻击的服务器上实施拒绝服务(DoS)。

## K8s 复杂性

Linux 发行商 Canonical 的产品总监 Stephan Fabel 对 Kubernetes 的漏洞有这样的评价。“对于最近 K8s 的拒绝服务攻击，有趣的是注意到这不是 K8s 独有的缺陷。但它确实强调了 K8s 是一个复杂的应用程序，它建立在重视安全性的技术基础之上。这些软件包在整个生态系统中被修补或正在被修补，”他说。

Fabel 继续提醒管理员 Kubernetes 不是一个孤岛:“Kubernetes 不是独立的，它的安全性也不是。通过保护从操作系统到应用程序和网络的整个部署，Kubernetes 可以保持安全。系统更新(无人值守升级)、基于角色的访问控制、本地防火墙(ufw)和网络分段等工具对此有所帮助。这不是 K8s 特有的，所有系统都需要分层的安全方法，”他说。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>