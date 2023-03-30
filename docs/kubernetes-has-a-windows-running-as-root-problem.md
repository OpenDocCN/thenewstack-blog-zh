# Kubernetes 有一个“Windows 以 Root 用户身份运行”的问题

> 原文：<https://thenewstack.io/kubernetes-has-a-windows-running-as-root-problem/>

在明确禁止的情况下，Windows 工作负载以 Kubernetes 容器管理员的身份运行？那是意想不到的。

我们都知道你能做的最愚蠢的事情之一就是用 root 权限运行容器。这并不能阻止人们这样做，但至少他们通常知道自己是在自找麻烦。现在， [Kubernetes 安全响应委员会](https://github.com/kubernetes/committee-security-response)报告了一个安全漏洞， [CVE-2021-25749](https://seclists.org/oss-sec/2022/q3/206) ，该漏洞使 Windows 工作负载能够在它们的容器中作为 Kubernetes 容器管理员运行，即使 runAsNonRoot 选项设置为 true。

哎呦！

## 问题是

具体来说，问题是在 Kubernetes 中发现了一个“安全问题”，该问题可能允许 [Windows 工作负载作为容器管理员](https://github.com/kubernetes/kubernetes/issues/112192)运行，即使这些工作负载将 runAsNonRoot 选项设置为 true。您可以通过检查 Kubernetes 审计日志中拼写错误的用户名来发现是否有人试图利用这一点。这些可能是有人试图绕过用户舱限制的证据。如果您发现此类攻击的证据，请联系 [security@kubernetes.io](https://mail.google.com/mail/?view=cm&fs=1&tf=1&to=security@kubernetes.io) 。

虽然问题没有那么糟糕——它的[通用漏洞评分系统(CVSS)](https://thenewstack.io/cvss-struggles-to-remain-viable-in-the-era-of-cloud-native-computing/) 评分很低，只有 3.4 分——但仍然令人担忧。[红帽](https://www.openshift.com/try?utm_content=inline-mention)认为比那更难听一点，CVSS 评分 3.8。不过，Red Hat 的安全团队指出，它的攻击复杂性和完成攻击所需的权限都很高。

不幸的是，没有办法减轻它。它会影响后面的 [Kubelet](https://kubernetes.io/docs/concepts/overview/components/) 版本。

*   库伯莱 1.20 版–1.21 版
*   库伯莱 1.22.0 版–1 . 22 . 13 版
*   库伯莱 1.23.0 版–1 . 23 . 10 版
*   库伯莱 1.24.0 版–1 . 24 . 4 版

## 修复

但是有一个简单的解决方法。升级到下一个版本就好了。这些是:

*   库伯莱 1.22.14 版
*   库伯莱 1.23.11 版
*   库伯莱 1.23.5 版
*   库伯莱 1.25.0 版

为了实现这一点，您需要遵循关于如何升级 Kubernetes 集群的说明。

做完这些后，你可以把这种担心放在一边，回到你和 Kubernetes clusters 的常规战斗中去。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>