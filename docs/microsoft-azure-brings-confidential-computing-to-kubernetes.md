# 微软 Azure 为 Kubernetes 带来机密计算

> 原文：<https://thenewstack.io/microsoft-azure-brings-confidential-computing-to-kubernetes/>

有很多保护静态和动态数据的解决方案；在使用数据时保护数据并不常见。去年，微软推出了一个 Kubernetes [SGX 插件](https://azure.microsoft.com/en-us/blog/bringing-confidential-computing-to-kubernetes/)来支持“机密计算”——运行 NGINX、Redis Cache 和 MemCache 等工作负载，这些工作负载是为了使用可信执行环境而构建的，或者是用其开源 [Open Enclave SDK](https://openenclave.io/sdk/) 编写的应用，它在加密内存中支持英特尔 SGX 和 Arm TrustZone。

Azure Compute [主管 Gabe Monroy](https://github.com/gabrtv) 当时告诉新的堆栈:“通过这个设备驱动程序插件，我们将安全保证水平绑定到芯片级，这是基于软件的解决方案所无法获得的。”这一切都是为了让代码和数据得到有效的加密，不仅在操作系统中保护代码和数据，而且即使是云提供商也无法窥探。"

当时，这需要在支持 SGX 的虚拟机上(在 Azure 或您自己的硬件上)创建一个 Kubernetes 集群，并安装机密计算设备插件，该插件将加密的页面缓存 RAM 作为 Kubernetes 可以调度的资源。每个 CPU 上的 enclave 数量有限，因此需要 Kubernetes 调度程序插件来确保需要 enclave 的 pod 位于有 enclave 可用的节点上。

“我们需要做的事情之一是实际上告诉 Kubernetes 有多少飞地可用之类的事情，以便你可以适当地安排时间，它可以找到有飞地可用的地方，”Kubernetes 联合创始人兼微软公司副总裁 Brendan Burns 告诉新堆栈。

现在，保密计算[在 AKS](https://docs.microsoft.com/en-us/azure/confidential-computing/confidential-nodes-aks-overview) 中可用，在预览中，使用相同的 SGX 设备插件使 EPC 内存成为您指定的资源类型，以及 SGX 报价助手服务，该服务证明应用程序及其运行环境的身份和状态。您可以将基于 [DCsv2 系列虚拟机](https://docs.microsoft.com/en-us/azure/virtual-machines/dcv2-series)的机密计算节点添加到新的或现有的 AKS 集群以及标准节点池中。这些虚拟机在有限数量的 Azure 区域可用(预计到 2020 年底将有更广泛的可用性)；它们运行在 SGX 的英特尔至强 E-2288G 处理器上(每个虚拟机最多有 8 个 vCPUs 和 168MiB 加密内存)，并且不与其他租户或订阅共享。您至少需要六个 DSCv2 内核。

容器应用程序直接在 CPU 上执行，无需客户操作系统或虚拟机管理程序来交付和证明运行 enclave-aware 容器，并为具有可信代码(也称为 enclave)的应用程序提供流程级容器隔离，这些代码在加密内存中运行[。除了 Open Enclave SDK，还有几个商业和开源工具可以帮助开发人员开发应用程序来利用机密计算，如](https://docs.microsoft.com/en-us/azure/confidential-computing/enclave-aware-containers) [Fortanix](https://www.fortanix.com/products/runtime-encryption) 、 [SCONE](https://scontain.com/) 、 [Anjuna](https://www.anjuna.io/) 、 [Graphene](https://grapheneproject.io/) 和 [Occlum](https://occlum.io/) 。

目前 AKS 中的机密计算仅支持 Linux 容器和 Ubuntu 18.04 Gen 2 VM 工作节点，在预览期间，您必须使用 Azure CLI 进行部署，而不是 Azure portal。

## 让机密变得普通

机密计算尚未达到吸引主流云用户的阶段，但将它引入 Kubernetes 是一个迹象，表明该平台在其支持的工作负载方面正在成熟。“客户说我们最安全的工作负载，我们最有特权的工作负载正在转向 Kubernetes 和 containers 以及云原生计算，”Burns 说。

他建议说，机密计算目前适用于对多个组织拥有的数据进行大数据分析，适用于秘密和密钥管理，适用于区块链以及金融、卫生和政府等受监管行业的机密微服务。但是随着技术的成熟，它会变得更加广泛。

美国国防部的绝地合同无疑推动了微软为 Azure 增加更多的安全选项，但伯恩斯指出，人们对云能够提供的安全级别的期望不断提高。

“当我们开始 AKS 时，API 服务器在公共互联网上，但很明显，你必须将 API 服务器放在专用网络内，而且只能放在专用网络内，”他指出。(AKS 现在与 [Azure Private Link](https://docs.microsoft.com/en-gb/azure/aks/private-clusters) 合作)。

“过去，云总是说‘公共网络——处理好它，如果你不喜欢它，没关系，去做别的事情吧。’现在，我们提供私有网络和私有 API 端点，我认为机密计算是下一件我们会说‘我们将把我们的超级特权、我们的高价值知识产权放在特权容器中’的事情。但我认为，随着时间的推移，我们会发现它只是成为标准，每个人都在其中运行一切，因为这是他们认为需要的方式。"

他指出，要达到像现在常规加密静态存储那样加密使用中的内存，需要进一步的发展。“我们已经围绕 enclave 和 enclave 对容器的支持与英特尔开展了大量合作，但这实际上是机密计算和云原生计算发展的开始。”硬件需要进一步发展，例如让一个 CPU 支持多个飞地；英特尔也在考虑加密系统中更多甚至所有的内存。在它成为默认之前，Kubernetes 社区还有很多工作要做。

“我认为现在对机密计算有太多的选择；不够自动化。我不能只在我的容器旁边打勾，就让它完全保密。我必须实际启发我的代码，知道它运行在一个飞地。这对于人们现在需要的特定用例来说非常好。但我认为，我们将会达到这样一个境界:每个人都只想勾选复选框，并知道他们的整个容器都在安全地运行。”

这是将 Kubernetes 从硬件无关型转变为利用全系列硬件并成为默认的“云原生基础设施”的一部分

“在 Kubernetes 的最初草案中，我们实际上概括了 CPU 或内存等资源，我们实际上称之为逻辑计算。我们说过你不应该关心 CPU 或 GPU 或指令集。但是，有人来找我们，说‘我为这个特定指令编写了代码，这个指令属于这个级别的英特尔至强处理器，而且只属于这个级别的至强处理器，所以我需要知道节点上正在运行什么进程，并相应地进行调度。’有各种各样的硬件，其中有一些有趣的东西，如绑定的 GPU，其中有两个 GPU 具有像 InfiniBand 这样的真正快速的互连:Azure 有一整套 InfiniBand。更不用说 Arm:每个人都构建了他们的 Raspberry Pi Kubernetes 集群，然后突然我们不得不处理这样一个事实，即容器不能在某些硬件上运行。它变成了一个非常多维的调度问题。"

伯恩斯认为，从某种意义上说，Kubernetes 和 AKS 是“新的虚拟机”:“它不再是一些客户将要使用的专用产品；这是绝大多数新应用程序开发的方向，因此，它需要具备每一个特性。我们添加到虚拟机中的每一个功能都必须包含在 Kubernetes 服务中，并且必须对用户可用。如果有处理器家族，我们必须支持它。如果有 FPGA，我们必须支持它。”

Azure 是第一个为 Kubernetes 提供机密计算支持的公共云，但其他人也在采用该标准。谷歌也有机密计算虚拟机，但他们在 AMD 第二代 EPYC 处理器中使用安全加密虚拟化技术，而不是英特尔 SGX:当 GKE 1.18 发布时，机密的 [GKE 节点](https://thenewstack.io/google-launches-confidential-vms-gke-nodes-to-encrypt-data-in-use/)将在测试版中提供[(可能在 10 月)。](https://cloud.google.com/blog/products/identity-security/expanding-google-clouds-confidential-computing-portfolio)

## 政策和准入

AKS 的其他安全和策略改进将会非常有用。使用 Azure 的组织可能已经在使用 Azure AD 进行身份和访问管理(针对用户和服务)。现在，AKS 支持 Azure RBAC，包括在同一个门户中使用相同的角色分配管理对 Kubernetes 资源的访问:团队努力使 AKS 资源在主 Azure 门户中可见的一个原因。

这些角色管理谁可以访问集群和集群上已有的资源，但不管理他们可以在集群上创建什么资源。Burns 建议，AKS 可以在这方面利用微软在企业和策略管理方面的专业知识，并将其引入开源社区。Kubernetes 策略已经在 AKS 上实现，不仅仅是因为它基于[看门人](https://github.com/open-policy-agent/gatekeeper)，验证准入控制器 webhook，微软将它的实现捐赠给了云本地计算基金会的开放策略代理项目，还因为它需要帮助客户摆脱 [Pod 安全策略](https://kubernetes.io/docs/concepts/security/pod-security-standards/)。

这是一个罕见的 Kubernetes 功能的例子，不会从测试版进展。“人们开始在测试版中使用它，因为 Kubernetes 已经有了从测试版到 1.0 版的稳定记录，但人们决定 Pod 安全政策永远不会离开测试版，”Burns 说。“因为我们在 Azure Policy 中所做的工作，即社区选择的看门人项目，实际上比 Pod 安全策略更通用，他们正在放弃 Pod 安全策略，并将代之以开放策略代理驱动的策略。我们有一群依赖它的客户，因此我们需要将准入策略准入控制器发布到 GA，以便我们可以在其他服务被弃用之前让客户迁移到它。”

这种支持是使用云 Kubernetes 服务而不是运行自己的基础设施的主要原因之一。伯恩斯说:“说‘测试版’很好，但一旦客户开始依赖它，你就必须支持它。”

云计算原生计算基金会是新堆栈的赞助商。

PIRO4D 从 Pixabay 获得的特征图像。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>