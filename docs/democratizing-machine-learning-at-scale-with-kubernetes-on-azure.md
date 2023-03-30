# 通过 Azure 上的 Kubernetes 大规模民主化机器学习

> 原文：<https://thenewstack.io/democratizing-machine-learning-at-scale-with-kubernetes-on-azure/>

[微软](https://azure.microsoft.com/en-us/?v=17.14)赞助了这篇文章，是新栈写的。

容器和 Kubernetes orchestrator 正在成为交付分布式培训的核心技术，其规模足以让有效的机器学习在生产用例中保持可靠。

大量带标签的数据集和处理它们的工具推动了机器学习从模糊的研究技术到主流技术的发展。多年来对算法的逐步改进已经被捆绑到 TensorFlow 和 PyTorch 等框架中，使用 GPU 的大规模并行性加快了训练这些算法的过程。容器有自己的权衡，但通过正确的工具和云规模，它们在支持分布式机器学习环境的横向扩展架构中显示出真正的前景。

“容器是打包和分发机器学习模型的好方法，Kubernetes 是协调和扩展这些模型的训练和服务的好方法，”来自微软 Azure 容器团队的[拉克伦·艾文森](https://github.com/lachie83)指出。“Kubernetes 使商用 NVidia GPUs 成为可调度的资源；你可以说‘我想要这么多这种类型 GPU’，然后在 Kubernetes 上安排。”

对于数据科学家来说，Kubernetes 原语可能不是特别直观，但像 [Kubeflow](https://github.com/kubeflow/Kubeflow) 这样的开源工具使他们更容易利用 Kubernetes 来训练、扩展和服务数据模型，而无需成为基础设施专家。

但是，在您自己的基础设施上，使用 GPU 节点将 Kubernetes 扩展到大规模集群可能会非常昂贵。即使使用 Kubeflow 来简化数据科学家的工作，使 Kubernetes 大规模高效仍然非常复杂，需要您组织中某个地方的基础架构专业知识。除非你有深厚的专业知识或正在获取它来运行其他微服务工作负载，否则带有 GPU 节点的云容器服务，如 [Azure Kubernetes Service](https://docs.microsoft.com/azure/aks/gpu-cluster) 是合乎逻辑的下一步。

## 攀登 Kubernetes 需要专家

OpenAI 选择 Kubernetes 进行深度学习研究，因为它允许快速迭代周期，并且可以扩展到该组织最大模型的规模——他们最大的集群超过 2500 个节点。但是，即使是由硅谷知名人士资助的拥有自己的数据中心的研究基金会，也没有资源来扩展其基础设施以支持这样的大型模型。相反，集群在 Azure 上，那里的资源可以有效地运行集群。

让 Kubernetes 达到这样的规模，即使是在 Azure 上，也需要 OpenAI 在管理 orchestrator 方面发展深厚的专业知识。当他们的[第一个集群超过 500 个节点](https://blog.openai.com/scaling-kubernetes-to-2500-nodes/)时，OpenAI 必须将 Kube 主机的 etcd 集群存储状态切换到使用直接连接的 SSD，以避免延迟问题；一旦超过 1，000 个节点，他们就必须重新配置其日志记录和监控，增加 etcd 集群上的存储，并将 Docker 根目录移动到 SSD，微调 KubeDNS，积极管理 Docker 映像拉取管道，并重新配置网络。

对于大型数据集，训练需要很长时间，让数据科学家坐以待毙。“他们无法在自己的数据中心获得足够的基础设施来保持所有数据科学家的高效工作，因此他们将 Kubernetes 集群扩展到云，”Evenson 解释道。但是仅仅转移到云并不能自动给你提供高效的分布式培训。如果没有一些额外的工作，加倍可用的资源不会导致线性扩展，因为许多机器学习模型不是为分布式训练设计的。你可能需要考虑一些不太熟悉的工具，比如 [Horovod](https://github.com/uber/horovod) ，这是一个在优步开发的框架，可以插入 TensorFlow、PyTorch 或 Keras。Horovod 在像 Kubernetes 这样的分布式系统上提高了模型的可伸缩性，与使用参数服务器相比，对模型的更改更少。

随着机器学习模型在其训练中经历每一批步骤，模型的参数得到调整；对于分布式培训中的多个工作人员，参数服务器会收集更新的参数并将其分发给所有工作人员，但是批处理和分发这些更改是非常网络和 CPU 密集型的，并且会随着您添加更多的 GPU 和工作人员而停止性能扩展。Horovod 使用英伟达的 NCCL 协议在 GPU 之间直接通信，而不需要参数服务器，这意味着工人可以随着时间的推移分发对模型的更改，而不会成为瓶颈。

分布式训练一般需要大量的网络带宽；使用 RDMA 和 [FreeFlow CNI 插件](https://github.com/Microsoft/Freeflow)改进容器覆盖网络通信，而不是让操作系统内核批量处理和传输数据，这降低了延迟，提高了网络吞吐量，而不增加 CPU 使用率，这也有助于提高可扩展性。

## 在 Azure 上经济高效地扩展分布式学习

Kubeflow、Horovod 和 Freeflow 都使用 [Nvidia VMs](https://aka.ms/kubeflow-labs) 与 Azure Kubernetes 服务配合使用，可以显著提高 ResNet、VGG-16 和 Inception v3 等常见深度学习模型的可扩展性。“我们的目标是让数据科学家更容易进入开源平台，开发他们的机器学习模型，所以你需要非常轻量级、可扩展的基础设施，你需要模型和基础设施线性扩展，这样他们就不必支付更多的费用来完成更多的工作。”

但是使用像 AKS 这样基于虚拟机的 Kubernetes 服务并不能解决云中大规模机器学习训练的所有问题。“当我开始一项培训工作时，我需要很多资源，当我完成时，我不需要这些，”Evenson 解释道。“尽管 Kubernetes 中的自动扩展很棒，但您仍然需要等待虚拟机加速和减速，以及与之相关的成本。在虚拟机模型中，您要么过度配置并让昂贵的 GPU 集群闲置，要么承受扩展的打击，因此当您在集群上删除一个作业时，每个虚拟机可能需要几分钟才能启动并准备好为负载提供服务。”

Azure Container Instances 通过交付按需容器来避免这种延迟，并且它将很快开始添加 GPU 支持。“ACI 将使工作负载快速增加；因为您不受虚拟机启动和停止时间的限制，所以您可以利用群集在更短的时间内启动大量节点，并加快交付速度。”Evenson 指出，除了让模型准备好更快地训练，这还会给你带来更大的可扩展性。

“因为 GPU 节点非常昂贵，人们只希望在处理数据时使用它们，他们想知道它们的运行效率如何。我是在填充 GPU，还是它们只发挥了一半的能力，这样我就可以运行一半的舰队了？ACI 可以快速扩展以交付批量工作负载，然后在工作负载完成后缩减规模。”ACI 还提供按秒计费，而不是按分钟计费。而且因为你使用[虚拟 Kubernetes kubelets](https://github.com/virtual-kubelet/virtual-kubelet)插入 ACI，行为就像标准的 Kubernetes Kubelets，不需要任何代码更改，Evenson 说，“但是后端运行在无节点的 Kubernetes 中，而不是绑定到虚拟机上。”

机器学习框架已经使构建深度学习模型的工具民主化，一个工具生态系统正在将 Kubernetes 变成一种有效的方式来实现这一点，而不需要数据科学家成为基础设施专家。Kubernetes 在云中的服务正在形成所需的规模，以便高效地处理每个人都可以使用的最大数据集。

特征图片:Horovod 比传统的分布式 TensorFlow(在 AKS 上进行基准测试)更好地扩展到分布式学习模型。图片由微软提供。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>