# arrikto:Kubernetes 上的 ML 模型部署可以变得更好

> 原文：<https://thenewstack.io/arrikto-ml-model-deployments-on-kubernetes-can-get-better/>

数据科学家和工程师在创建[机器学习](https://thenewstack.io/category/machine-learning/) (ML)模型时，通常与 DevOps 生产流水线并行工作。通过所谓的 MLOps，这些团队构建的 ML 模型通常在准备好投入生产后集成到应用程序部署环境中。这些数据科学家或 MLOps 团队也可能依赖 GitOps 作为具有 Git 存储库的不可变应用程序结构，以便 ML 模型分布在不同的环境中，例如混合云。

为了方便在 [Kubernetes](https://thenewstack.io/category/kubernetes/) 上部署 ML 模型和应用程序，开源 [Kubeflow](https://github.com/kubeflow/kubeflow) 已经成为一个更有前途的开源工具来帮助这个过程。尽管如此，与在 Kubernetes 上部署 ML 模型和应用程序的 MLOps 团队相关的挑战——即使使用 Kubeflow 这样的工具——也充满了困难和复杂性。这是由于 ML 模型开发以数据科学为中心的本质，以及与管理 Kubernetes 环境相关的大量记录的复杂性。

ML 工具和平台提供商 Arrikto 最新发布的[Arrikto Enterprise kube flow(EKF)](https://www.arrikto.com/enterprise-kubeflow/)，以 Kubeflow 1.4 为特色，为数据科学家团队与开发运营团队和运营团队在 Kubernetes 上集成 ML 模型提供了改进。该公司表示，它有助于进一步推动软件提供商的使命，支持数据科学家更快、更有效、更安全地构建和部署 ML 模型的目标。

## 解决机器学习挑战

Arrikto 首席执行官兼创始人 Constantinos Venetsanopoulos[告诉 New Stack:“为了解决当今的[ML 模型开发]挑战，DevOps 必须将大量不同的工具拼凑在一起，创建部署自动化基础架构，然后在环境发生变化时重新完成大部分工作，而数据科学家的工作流程仍然不是无缝的。“这就是 Kubeflow 和 EKF 携手为整个组织提供单一平台和单一用户体验来解决这些挑战的地方。”](https://www.linkedin.com/in/cvenets)

Venetsanopoulos 告诉新堆栈:“这一版本使数据科学和运营团队能够更有效地合作，从根本上减少了将 ML 模型投入生产所需的时间。”Venetsanopoulos 传达的具体特征包括:

*   自动化:对于数据科学家来说，通过 [Kale](https://github.com/kubeflow-kale/kale) 实现从实验到建模的简化的端到端工作流，Kale 是 Kubeflow 的一个工作流工具，可以协调所有 Kubeflow 组件。
*   可再现性:对于数据科学家、SecOps、legal 和 DevOps 而言，使用 Kubeflow 的数据管理解决方案 [Rok](https://www.arrikto.com/rok-data-management-platform/) ，笔记本和管道功能的版本包括代码、库、数据和元数据。
*   安全性:对于 SecOps 和 DevOps，集成了机密管理以保护对外部服务的访问，集成了授权提供商，如 Google、Okta、PingID 等，同时为用户和团队提供了高级隔离。
*   可移植性:对于整个组织来说，基于 GitOps 的自动化工具可以在[亚马逊网络服务](https://aws.amazon.com/?utm_content=inline-mention) (AWS)、Azure 和谷歌云提供商环境以及本地基础设施上部署相同的平台。

该公司还传达了关于 EKF 如何通过 GitOps 支持从左到右 ML 模型开发周期的更多细节。这些 GitOps 功能包括如何创建 EKF 以支持自动化的“端到端”部署流程，并在部署之前提供一个显示基础设施详细信息的向导。EKF 还提供了一个部署自动化工具，可以生成 Kustomize 清单，帮助定制满足基础设施需求的应用程序配置。

如上所述，EKF 还用于将 ML 模型清单提交给 Git repo，以确保不变性和可再现性。清单还用于在 Kubernetes 上部署更新和配置更改。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>