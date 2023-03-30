# Aqua 将容器安全平台扩展到 Kubernetes、云服务

> 原文：<https://thenewstack.io/aqua-extends-container-security-platform-kubernetes-cloud-services/>

Aqua Security 已经扩展了其容器安全平台，以涵盖 [Kubernetes](/category/kubernetes/) 开源容器编排工具，以及第三方容器即服务云平台，否则用户可能无法享受对其容器的完全安全控制。

Aqua 3.0 旨在管理开发和部署过程中的容器安全，利用了 Kubernetes 1.8 中引入的许多控制，包括管理映像保证、网络分段和基于角色的访问控制，[Aqua Security](https://www.linkedin.com/in/amirjerbi/)的联合创始人兼首席技术官 Amir Jerbi 说。

使用 Aqua 3.0，用户可以创建细粒度的用户访问控制角色和策略。对 kubectl 命令的访问可以指定给特定的用户，并由 Aqua 的可伸缩标签格式管理。Kubernetes 控件还提供了阻止未经批准的映像在整个集群中运行的能力，以及基于 Kubernetes 名称空间、集群或部署控制网络流量的能力。

除了安全特性，Aqua 3.0 还提供了一组扩展的基准和日志功能。它整合了该公司的 Kube-Bench，这是一套确保 Kubernetes 得到适当保护的检查。

“基准本身实际上只是一个文档。大多数组织只是做一个手动清单。Aqua 营销副总裁安迪·费特说:“这种整合使检查更加自动化。"当您的系统运行时，我们将标记所有超出基准的内容."

Aqua 的事件日志记录功能可以捕获 Kubernetes 特有的信息，如 pod 名称、类型、部署和命名空间数据，为合规性和取证提供了额外的可见性。

该公司还通过一套名为“MicroEnforcer”的运行时安全控制，扩展了对用户无法控制主机环境的保护，即容器即服务(CaaS)环境，如[微软的 Azure 容器实例](https://azure.microsoft.com/en-us/services/container-instances/) (ACI)和亚马逊网络服务的 [Fargate](https://aws.amazon.com/fargate/) 。

在映像构建期间，会向每个容器添加一个边车，用于监视和控制实例化的容器，防止任何未经授权的活动。“MicroEnforcer”识别第三方服务上的恶意活动，与该公司的“Aqua Enforcer”[识别自我管理服务](https://blog.aquasec.com/securing-container-deployments-on-bluemix-with-aqua-security)的方式非常相似。它还管理操作以确保操作安全，例如将机密注入容器中以便用于授权，并收集警报以便分发到安全信息和事件管理(SIEM)和分析工具。

使用托管服务，“没有边界，没有任何东西可以预先安装。因此，挑战在于如何将安全性嵌入到应用程序中，”Jerbi 指出。用户将微施力装置与应用程序一起嵌入容器中。“它基本上是你图像中的一个附加层。当您发送您的映像时，它将识别出它是在[第三方托管]环境中运行，它将开始自己运行，并开始保护容器。”

MicroEnforcer 将其日志记录信息发送回指挥中心，同时定期在内部部署 Aqua。这种集成的方法为操作员提供了自由，因为他们可以跨托管安全或非托管安全环境运行容器，而无需在两种环境之间移动容器时进行任何更改。

Aqua 3.0 [与 Kubernetes 1.8 或更新版本的实现兼容](https://blog.aquasec.com/aqua-3.0-kubernetes-security-deep-dive)。该平台支持 Linux 和 Windows 运行时环境，并且有一个针对 Pivotal Cloud Foundry 的[新测试版](https://blog.aquasec.com/using-aqua-to-secure-applications-on-pivotal-cloud-foundry)。

Aqua 和微软是新堆栈的赞助商。

通过 Pixabay 的特征图像。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>