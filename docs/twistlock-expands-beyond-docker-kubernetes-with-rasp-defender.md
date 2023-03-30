# Twistlock 扩展到 Docker 之外，Kubernetes 拥有 RASP Defender

> 原文：<https://thenewstack.io/twistlock-expands-beyond-docker-kubernetes-with-rasp-defender/>

一年一度的 RSA 安全大会将于本周召开，正如您所料，保护容器和微服务是一个反复出现的主题。与此同时，虚拟机也重新成为安全焦点，正如云原生安全提供商 [Twistlock](https://www.twistlock.com/) 本周[发布的](https://www.twistlock.com/2019/03/05/twistlock-19-03-release-notes/)公告所示，其最新版本将把虚拟机(VM)纳入当前包含云原生容器部署的同一安全产品中。

以前，Twistlock 已经扩展到容器和无服务器部署，但他们发现客户也要求包括虚拟机。

[twist lock](https://www.twistlock.com/about-us/team/john-morello/)的首席技术官约翰·莫雷罗写道:“虽然许多安全提供商已经提供了可以在虚拟机中运行的产品，但它们往往只是重复了传统的端点保护，并且没有针对定义云原生的自动化和无状态进行优化。“在 Twistlock 19.03 中，我们自豪地宣布推出世界上第一个真正全面的云原生安全平台—在单一产品中跨主机、容器和无服务器提供保护，云原生和 API 支持自身，涵盖您的所有工作负载，无论底层计算技术支持何种工作负载。”

New Stack 创始人兼总编辑 Alex Williams 在发布会上采访了 Morello，了解新产品的演示情况:

[https://www.youtube.com/embed/VGu0OzPOmSw?feature=oembed](https://www.youtube.com/embed/VGu0OzPOmSw?feature=oembed)

视频

然而，这并不是本周来自 Twistlock 的唯一消息。除了扩展到包括虚拟机之外，Twistlock 19.03 还引入了其他几个新特性，这些特性对那些使用容器和无服务器技术的人来说很有意义。例如，增加原生的 [Helm](https://helm.sh/) 支持，允许 Twistlock 用户现在“直接从 twistcli 为控制台和 Defender 生成准备运行的图表”。其他值得注意的功能包括[带有 Kubernetes 审计日志记录的自定义运行时规则](https://www.twistlock.com/2019/03/05/custom-runtime-rule-language-integrated-k8s-audit-logging/)，它现在将“为容器和主机提供对离散运行时行为的更多控制”，以及[扩展的云发现和合规性](https://www.twistlock.com/2019/03/05/automated-cloud-discovery-compliance/)，它已经扩展到“覆盖 Azure 和谷歌云平台上的所有云原生服务，并直接在控制台 web UI 中显示关于每个服务的丰富元数据。”

Twistlock 19.03 还引入了[运行时应用程序自我保护(RASP)防御程序](https://www.twistlock.com/2019/03/05/runtime-application-self-protection-protecting-apps-wherever-they-run)，Morello 解释说这是一种嵌入式安全形式，而不是由外部工具提供的安全，这解决了容器和无服务器带来的问题。

“随着 Docker 已经成为一个近乎通用的应用程序包标准，我们已经看到了服务的激增，尽管它们运行 Docker 映像，但实际上并不使用 Docker 或 OCI 运行时。例如，Pivotal Cloud Foundry PAS 可以运行 Docker 映像，但使用非 Docker 和 OCI 运行时，”Morello 写道。“其他服务，如 AWS Fargate 和 Azure Container 实例，使用 Docker 运行时，但在高度受限的环境中，Defender 无法以所需的提升访问权限运行。为了解决这两种情况，我们推出了新的 RASP Defender。”

RASP Defender 通过作为“简单的二进制文件”运行来解决这个问题，它“在受保护的应用程序之前启动，然后立即调用它，赋予它对应用程序本身的半管理能力，而不管底层运行时如何，也不需要主机操作系统内的特权。”

RASP Defender 适用于标准 Kubernetes 和 Docker 部署之外的所有场景。

“Docker 和 Kubernetes 是革命性的…但它们不是运行云工作负载的唯一方式，”Twistlock 解决方案架构师 [Neil Carpenter](https://www.twistlock.com/author/neil-carpenter/) 在博客文章[中解释该技术时写道。](https://www.twistlock.com/2019/03/05/runtime-application-self-protection-protecting-apps-wherever-they-run/)“您可能希望利用 Azure Container 实例或 AWS Fargate 等服务的强大功能来运行容器，而无需管理服务器。您可能希望在 AWS Lambda、Google Functions 上运行函数，甚至是自托管的功能即服务替代方案。您可能拥有不能在容器运行时接口平台上运行的遗留或专用环境。然而，在所有这些场景中，您都希望能够监控和保护您的应用程序和数据。借助 Twistlock 的 19.03 版本，您可以将保护扩展到所有这些场景。”

Twistlock 是新堆栈的赞助商。

由[凯尔·格伦](https://unsplash.com/photos/-f8ssjFhD1k?utm_source=unsplash&utm_medium=referral&utm_content=creditCopyText)在 [Unsplash](https://unsplash.com/search/photos/expand?utm_source=unsplash&utm_medium=referral&utm_content=creditCopyText) 上拍摄的特写图片。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>