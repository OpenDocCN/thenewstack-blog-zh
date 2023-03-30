# 英伟达为人工智能提供托管的大规模处理

> 原文：<https://thenewstack.io/nvidia-offers-hosted-large-scale-processing-for-ai/>

芯片制造商英伟达(Nvidia)正在兑现承诺，通过更方便地使用该公司强大的超级计算产品，让主流企业开发人员和数据科学家更容易获得人工智能(AI)技术。

这家 GPU 制造商本周正在向北美公司普遍提供其基本命令平台。该平台是一个托管的人工智能开发产品，基于英伟达的 DGX 超级计算机，是其更大的 [LaunchPad](https://www.nvidia.com/en-us/data-center/ai-launchpad/) 计划的一部分，旨在通过托管平台提供其人工智能和机器学习基础设施。

在过去的几个月里，NVIDIA[一直在为此做准备。官员们在四月份的 GTC](https://thenewstack.io/tutorial-deploy-the-nvidia-gpu-operator-on-kubernetes-based-on-containerd-runtime/)[活动上展示了](https://www.nvidia.com/en-us/gtc/) [DGX 超级计算机](https://www.nvidia.com/en-us/data-center/resources/nvidia-dgx-superpod-reference-architecture/)，称其为云原生的多租户人工智能超级计算机。5 月下旬，该公司推出了 Base Command，一个月后推出了 LaunchPad 计划和 [Fleet Command](https://www.nvidia.com/en-us/data-center/products/fleet-command/) ，这是另一个托管平台，旨在使组织能够部署和管理高度分布式的人工智能工作负载。

根据 Base Command Platform 产品管理高级总监 Stephan Fabel 的说法，该供应商正在寻求将人工智能和机器学习能力扩展到研究机构、[高性能计算(HPC)](https://thenewstack.io/high-performance-computing-on-a-cloud-native-stack/) 中心和政府机构以外的领域，并扩展到主流企业，如[自然语言处理](https://thenewstack.io/the-promising-duo-five-use-cases-for-natural-language-processing-in-fintech/)和视频分析。

购买一台 DGX SuperPod 并将其带到现场可能会有很高的价格，因为配备英伟达 Bluefield 数据处理单元(DPUs)的超级计算机从 20 个节点开始，以 20 个节点为增量扩展，并配有网络和存储工具。Fabel 告诉 New Stack，运行和管理 SuperPod 所需的成本和工作可能会使许多企业望尘莫及。

此外，组织可能在很长一段时间内不需要所有的计算能力。他们真正需要的是在运行人工智能工作负载时更好的性能。

“这个概念在一个我们通常不会用 DGX 超级市场来应对的细分市场中，与一大批其他公司产生了很好的共鸣，”他说。“在我们推动人工智能民主化和进入更广泛的企业市场的过程中，现在这个托管环境中的[Base Command Platform]是我们向比传统目标更大的市场领域扩展的第一步。”

[Base Command Platform](https://www.nvidia.com/en-us/data-center/base-command-platform/) 使组织能够租赁他们需要的计算机电源。DGX 超级电脑由数据中心提供商 [Equinix](https://www.equinix.com/) 运营的设施托管。此外，英伟达正在与 [NetApp](https://www.netapp.com/) 合作开发集成数据管理解决方案，该解决方案提供高性能存储，可以处理加速的人工智能计算。

> 购买 NGX SuperPod 并将其带到现场可能会有很高的价格，因为配备 Nvidia blue field 数据处理单元(DPUs)的超级计算机从 20 个节点开始，以 20 个节点为增量扩展，并配有网络和存储工具。

另一个合作伙伴是[Weights and bias](https://wandb.ai/site)，一家机器学习开发工具的提供商，它将把 [MLOps](https://thenewstack.io/what-is-mlops/) 软件带到基地指挥平台。该软件将使企业能够跟踪实验以及数据版本和模型可视化。开发人员和数据科学家也能够利用英伟达的 [NGC](https://www.nvidia.com/en-us/gpu-cloud/) 系列 GPU 优化软件，用于 HCP、人工智能和机器学习。

虽然基地司令部将减轻企业的大量成本负担，从资本转移到运营支出，但它并不便宜。用户需要为 DGX SuperPod access 支付至少三个月的月租，租金为 9 万美元。他们可以在需要时延长租期或扩大规模。企业还可以以类似的订阅方式从 NetApp 获得专用的全闪存存储文件。尽管如此，法贝尔说，OpEx 模式和租赁选项意味着开发人员和数据科学家可以在高性能基础设施上追求人工智能项目，否则他们可能会跳过这些项目，因为这些项目过于昂贵，将比其他硬件运行得更快

他还指出，基地指挥和舰队指挥平台的结合为企业提供了一个完整的人工智能解决方案，基地指挥用于人工智能培训，并利用云原生容器创建人工智能模型。

他说:“有了我们的姐妹项目舰队司令部，他们现在可以在生产中部署这种设备了。”“这是一个创建、培训和研究模型的一站式商店，提供越来越好的模型来运行他们的推理，并结合一个平台来实际部署这些模型，这就完成了这个故事，并使公司和企业不必自己实施所有的软件管理……。让数据科学家能够立即访问，然后能够将他们的工作成果立即部署到生产中，这就是价值所在。”

DGX SuperPod 是一台人工智能超级计算机，可以从 20 个扩展到 140 个 DGX A100 系统，具有 [Bluefield DPUs](https://www.nvidia.com/en-us/networking/products/data-processing-unit/) ，可以从 1 扩展到 10 Pb 的存储，提供高达 200 Gb/s 的网络结构，以及英伟达的 [DGX](https://www.nvidia.com/en-us/data-center/dgx-systems/?ncid=van-dgx-systems) 和 [CUDA-X](https://developer.nvidia.com/gpu-accelerated-libraries) 软件堆栈。它提供 100 到 700 PFOPS 的性能。

Nvidia 是越来越多的老牌硬件制造商之一，包括惠普企业、戴尔技术、思科系统和联想，它们正在迅速转向为基于云的环境提供更多的产品组合即服务。通过这些“即服务”的努力，供应商使组织能够为其内部环境创建类似云的基础架构，例如拥有灵活的消费模式，以及可以通过公共云访问的产品。

Fabel 说，目标和模式是相似的，但 Nvidia 的 Base Command 平台更像是一个租赁产品——有租赁规则、基线时间表和月费——而不是一个服务项目。

“这真的是一个专门的集群，”他说。“所有的高速 InfiniBand 网络都遵循直接参考体系结构，然后基本上利用一个平台作为消费它的切入点。如果你想扩大规模，那么你必须通知我们，你会得到第四个节点或第五个节点，等等。”

[https://www.youtube.com/embed/prsrply1GUA?feature=oembed](https://www.youtube.com/embed/prsrply1GUA?feature=oembed)

视频

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>