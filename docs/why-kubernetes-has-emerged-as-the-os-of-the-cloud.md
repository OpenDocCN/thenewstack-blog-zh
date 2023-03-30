# 为什么 Kubernetes 成为了云的“操作系统”

> 原文：<https://thenewstack.io/why-kubernetes-has-emerged-as-the-os-of-the-cloud/>

自从计算机时代开始以来，它就被主导它们的操作系统(MS-DOS、Unix、Linux、Windows、macOS、Android、iOS)所定义。新的研究显示，2023 年的主要参与者和市场份额保持不变，但随着我们进入神秘的新 Web3 时代，也有一颗冉冉升起的新星即将出现。

出乎意料的是，这颗星就是库伯内特斯。[云本地计算基金会(CNCF)](https://thenewstack.io/how-a-project-graduates-from-the-cloud-native-computing-foundation/) [报告](https://www.cncf.io/reports/cncf-annual-survey-2022/)称，这种“操作系统”——嗯，实际上是现代 IT 堆栈中运营管理的基础层——已经成功实现了向云的主流飞跃，并在短短几年内看到其实例大幅增加。

71%的组织在 Kubernetes 上运行数据库和缓存，同比增长 48%。随着消息传递系统(36%的增长)，组织越来越多地使用数据库和缓存来保存应用程序工作负载状态。

## 库伯内特起源

Kubernetes 已经普遍使用了不到十年，它通过微服务来编排和部署容器以运行工作负载。CNCF 调查(包括 2063 名合格的专业人员)的 44%的受访者已经将容器用于几乎所有的应用程序和业务领域，另外 35%的人表示容器至少用于一些生产应用程序。这对于虚拟机等竞争技术来说是一个重大威胁，虚拟机已经在数据系统中嵌入了 20 多年，但在生产用例中正在迅速被取代。

Kubernetes 最初是由谷歌工程师 [Craig McLuckie](https://thenewstack.io/beda-burns-and-mcluckie-the-creators-of-kubernetes-look-back/) 、 [Joe Beda](https://thenewstack.io/kubernetes-just-has-to-get-easier-for-developers/) 和 [Brendan Burns](https://thenewstack.io/brendan-burns-everything-you-need-to-know-about-confidential-computing-and-containers/) 在 2013 年开发和设计的，已经迅速发展成为世界上最受欢迎的开源项目之一。然而，system orchestrator 的使用增加并不是在 IT 基础设施的所有角落都很明显。

“因此，Kubernetes 正在发生的事情是，我们越来越多地使用它，越来越多地使用越来越复杂的(云原生)应用程序，”新堆栈的分析师/研究员 Lawrence Hecht 说。“但如果你将 Kubernetes 用于企业，那(市场细分)根本不会增长。零。现有用户，是的，然后可能会有一些小公司的新实例。但增长都是在云原生应用上。”

企业正在尝试不同的方式在云中部署 Kubernetes，并取得了成功。Dynatrace 在其 2023 年的报告中指出，在典型的 Kubernetes 集群中，应用程序工作负载占了大多数(59%)。当时，所有非应用程序工作负载(系统和辅助工作负载)所占的比例相对较小。

然而，一年后，这种情况迅速逆转。2022 年，随着组织越来越多地采用先进的 Kubernetes 平台技术，如安全控制、服务网格、消息传递系统和可观察性工具，辅助工作负载超过了应用工作负载(63%比 37%)。与此同时，组织尝试将 Kubernetes 用于更广泛的用例，如构建数据管道、调度公用事业工作负载和其他任务。Kubernetes 成为运行几乎任何东西的平台，从而成为云原生应用的虚拟“操作系统”。多才多艺是它至高无上的荣耀。

## 容器是新常态，WebAssembly 是未来

CNCF 还发现，随着容器在 2022 年成为主流，无服务器架构的采用正在为 WebAssembly 奠定基础，这是本次调查中首次被问到的问题。总体而言，37%的组织报告有一些使用 WebAssembly 部署应用程序的经验。尽管许多人仍在亲自测试它们，但 WasmEdge 和 WAMR 是目前使用的顶级运行时。

“WebAssembly，或 Wasm，被证明是在 web 浏览器上运行代码的一种非常实用的方式，可以充当各种编译器，”[在新的堆栈中写道](https://thenewstack.io/yes-webassembly-can-replace-kubernetes/) [B .卡梅隆增益](https://thenewstack.io/author/bruce-gain/)。“它作为一种语言工作得非常好，[万维网联盟(W3C)](https://thenewstack.io/this-week-in-programming-the-time-has-come-to-pay-attention-to-webassembly/) 在 2019 年将其命名为网络标准，从而成为与 HTML、CSS 和 JavaScript 一起的第四个网络标准。”

WebAssembly 被视为容器的有效负载，是一种编程 sidecar 服务(如服务网格)的方式，也是一种向边缘设备交付和编排工作负载的替代方式。

## 2022 年，CNCF 项目的采用有所增加

报告的其他重点包括:

*   响应者报告的使用和部署集装箱的最大挑战是缺乏培训和安全。事实上，缺乏培训是阻碍采用的最大障碍；这是 44%尚未在生产中部署容器的人和 41%在有限的基础上使用容器的人提到的最大挑战。一旦容器被用于几乎所有的应用程序，那么安全性就成了最大的挑战。
*   CNCF 孵化和毕业项目的采用在 2022 年有所增加，其中 [OpenTelemetry](https://www.cncf.io/projects/opentelemetry/) 和 [Argo](https://www.cncf.io/projects/argo/) 的使用量增长最快。前者从 2020 年的 4%上升到 2022 年的 20%，后者从 10%上升到 28%。同时， [Containerd](https://www.cncf.io/projects/containerd/) (36%比 56%)和 [CoreDNS](https://www.cncf.io/projects/coredns/) (48%比 56%)是使用和评价增幅最大的毕业项目。
*   [持续集成](https://glossary.cncf.io/continuous-integration/)和[交付](https://glossary.cncf.io/continuous-delivery/) (CI/CD)技术同比增长 43%,表明组织正在投入更多的 Kubernetes 集群来运行软件构建、测试和部署管道。

**这项全球调查由 CNCF 和 Linux 基金会研究部于 2022 年 6 月 30 日至 9 月 27 日进行。通过社交媒体、CNCF 和 Linux 基金会及其各自的网站、CNCF 完全订阅者电子邮件、KubeWeekly 简讯和 Linux 基金会简讯进行了宣传。该调查有英文、中文和日文版本。第三方小组提供商也被用来获得 54%的受访者，他们提供了参与的象征性报酬。**

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>