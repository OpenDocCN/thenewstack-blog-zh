# 什么是 Siloscape，您的团队如何防范它？

> 原文：<https://thenewstack.io/what-is-siloscape-and-how-can-your-team-defend-against-it/>

在容器中部署应用程序的企业通常对该技术的安全风险知之甚少。这对网络罪犯来说是个好消息。

[根据](https://info.aquasec.com/aqua-runtime-survey)[Aqua Security](https://www.aquasec.com/)7 月发布的对 150 名云原生安全从业者的调查，只有 3%的受访者理解容器本身不是安全边界，不到四分之一的人拥有在运行时保护容器的工具。

这就是为什么帕洛阿尔托网络 ['](https://www.paloaltonetworks.com/prisma/cloud) 网络安全研究小组 [Unit 42](https://unit42.paloaltonetworks.com) 的 [Siloscape 报告](https://unit42.paloaltonetworks.com/siloscape/)来自 [Prisma Cloud 如此令人不安。](https://www.paloaltonetworks.com/cloud-security?utm_content=inline-mention)

六月，[帕洛阿尔托的高级安全研究员丹尼尔·普里兹曼特](https://www.linkedin.com/in/prizmant/)[报告发现了第一个针对 Windows 容器的已知恶意软件](https://unit42.paloaltonetworks.com/siloscape/)。

他告诉新堆栈，恶意软件利用了 Windows 内核中一个未记录的函数的漏洞。

“这个函数可以建立一个符号链接——一个对象指向另一个对象——全局的，这实际上在容器和主机之间建立了一个开放的链接，”他说。

他补充说，实际上，这为攻击者提供了大量的可能性。“这种恶意软件可能会被用于各种攻击，包括供应链攻击，”他说。

例如，一家软件公司的软件可能会被入侵，这样该软件的所有用户都会感染恶意软件，正如最近利用[网络安全管理软件产品](https://thenewstack.io/solarwinds-the-worlds-biggest-security-failure-and-open-sources-better-answer/)和[卡塞亚](https://thenewstack.io/kaseya-sera-whatever-will-be-will-be/) IT 管理软件的攻击所发生的那样。

Prizmant 说，或者攻击者可以感染一个网络服务器集群，把它变成一个巨大的钓鱼网站。

这种类型的恶意软件也可以用于加密劫持，攻击者使用被劫持的服务器来挖掘比特币和其他加密货币。

“他们通过窃取处理能力来轻松赚钱，”他说。

## Windows 容器易受攻击

攻击者已经在利用这一漏洞，任何将 Kubernetes 集群与 Windows 容器结合使用的人都有可能受到攻击。今年 6 月，Pirzmant 确认了 23 名积极参与攻击的受害者，攻击已经持续了一年多。

“总的来说，这令人深感不安，”总部设在华盛顿的网络安全公司[格林](https://www.grimm-co.com/)的高级安全顾问摩西·弗罗斯特说。

他说:“这表明，不仅环境中存在 Windows 工作负载，而且它们没有通过打补丁来解决，它们的权限可能过于宽松。”。

他说，这些公司可能将工作负载从 Windows 内部转移到了 Kubernetes，并且可能没有充分考虑到作为这种方法的早期采用者可能会面临的所有挑战。

“[微软](https://azure.microsoft.com/) Windows 没有 Linux 所有的必要限制，即使在 Linux 中，我们仍然可以找到容器突破，”他补充道。

## 如何防御 Siloscape

为了防御 Siloscape，公司应该确保 Windows 容器只拥有运行所需的权限，而不是更多权限，并审查其群集和云环境的安全配置。

弗罗斯特说，公司还应该部署能够扫描攻击的容器感知终端安全工具。

“容器更多的是应用打包解决方案，而不是像虚拟机那样的安全边界，”他说。“我们对这一点了解得越多，我们就能更好地模拟风险。”

微软自己也建议公司不要使用 Windows 容器作为安全特性，而是对任何依赖容器化作为安全边界的事情使用 Hyper-V 容器。

然而，微软最近增加了额外的安全检查。例如，现在有一个对 Siloscape 攻击中使用的关键函数的检查，该函数允许恶意软件从容器中逃逸。如果从容器内部调用该函数，它将被阻塞。

网络安全公司 [Threat Stack](https://www.threatstack.com/) 的安全专家 Nathan Paulhus 说，最重要的是，公司需要确保所有的系统都打了补丁并且是最新的。

“所有观察到的感染都是通过运行易受攻击软件的 Windows 容器，”Paulhus 说。“如果没有这些漏洞，最初的立足点就不会存在。”

为了首先将 Siloscape 恶意软件放入 Windows 容器，攻击者必须找到一个入口点。

“有一堆软件人们运行着，可能是因为技术债务，他们无法更新，”他说。"或者他们缺乏资源."

Siloscape 恶意软件还使用 Tor 代理和洋葱域与其命令和控制服务器进行通信。

“如果你的公司不使用或不需要访问 Tor，你可能想停止那些 DNS 请求的解析，”Paulhus 说。

## 防范未来的攻击

Palo Alto 的 Prizmant 说，由于 Siloscape 利用的特定漏洞已经被微软修补，我们可能不会看到许多使用这种特定载体的攻击。

“然而，我确实希望看到其他恶意软件试图通过逃离容器来滥用 Kubernetes 的处理能力，”他说。

他说，为了保护自己，公司应该遵循云环境配置的最佳实践。例如，不允许节点完全访问。不要运行特权容器。”

网络安全公司 [Deep Instinct](http://www.deepinstinct.com/) 的现场首席技术官 [Robert Boudreaux](https://www.linkedin.com/in/robertboudreaux/) 说，预防是网络安全的最佳策略。

但是公司也应该培训他们的安全团队和员工来识别系统何时被入侵。

“随着技术的进步，攻击的表面和不同妥协的可能性也在增加，”他说。

他说，这要求公司不断审查其安全政策，着眼于不断变化的威胁形势。

对于容器来说尤其如此。[根据](https://www.redhat.com/en/resources/kubernetes-adoption-security-market-trends-2021-overview) [Red Hat](https://www.redhat.com/en/technologies/cloud-computing/openshift/try-it?utm_content=logo-sponsorpage&utm_source=thenewstack&utm_medium=website&utm_campaign=platform) 在 7 月发布的一份报告，94%接受调查的公司在过去一年中在其 Kubernetes 环境中至少经历过一次安全事件。

超过一半的人报告说由于安全问题而推迟了 Kubernetes 应用程序的部署。

为了提供帮助，[国家安全局](https://www.nsa.gov/)与[网络安全和基础设施安全局](https://www.cisa.gov/)、[合作发布了一份报告](https://media.defense.gov/2021/Aug/03/2002820425/-1/-1/1/CTR_KUBERNETES%20HARDENING%20GUIDANCE.PDF)，提供了提高 Kubernetes 集装箱安全性的指导。

威胁堆栈的保罗胡斯说，该指南非常详细，非常有价值。“尤其是对 Kubernetes 的采用者来说。加强集群有很多好处。”

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>