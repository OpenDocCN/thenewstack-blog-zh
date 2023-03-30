# 初级读本:Kubeflow 利用 Kubernetes 简化机器学习

> 原文：<https://thenewstack.io/primer-kubeflow-streamlines-machine-learning-with-kubernetes/>

*本文是关于将持续集成和部署(CI/CD)实践引入机器学习的[系列](https://thenewstack.io/build-and-deploy-a-machine-learning-model-with-azure-ml-service/)中的一篇文章。查看新的堆栈，了解未来的部分。*

[Kubeflow](https://www.kubeflow.org/) 的创建是为了让开发、部署和管理机器学习应用变得更加容易。这是一个基于 Kubernetes 的可组合、可扩展、可移植的机器学习堆栈，最初是基于 Google 在 Kubernetes 上使用 Tensorflow 的方式。

Kubeflow 于 2017 年 12 月首次作为开源项目发布。它将 Tensorflow 和 Jupyter Notebooks 等常用的机器学习工具集成到一个平台中。Kubeflow 的创新正在为所有现有的机器学习工具创造一种更好的方式，以共同创建一个内聚的管道，并自动化更多的机器学习应用程序生命周期-包括数据物流和版本管理-比以前可能的。

Kubeflow 联合创始人之一、Kubernetes 早期项目经理 Azure 开源机器学习战略负责人 David Aronchick 表示，在听到数十名数据科学家描述他们拼凑起来完成工作的应用程序蜘蛛网后，他受到了创办 Kubeflow 的启发。这让他想起了 Kubernetes 之前的软件开发。

“Kubeflow 旨在解决整个机器学习应用程序开发生命周期，从模型开发到部署和修改，”谷歌高级工程师兼 Kubeflow 活跃贡献者 Michelle Casbon[表示。"这个过程从根本上不同于常见的网络或移动架构."](https://www.linkedin.com/in/michellecasbon/)

“Kubeflow 的建立有一个特定的目标，那就是简化机器学习的工作流程，”MapR 企业架构总监 Jim Scott 解释道。“如果你不是在做机器学习，就不要看 Kubeflow，它不是适合这项工作的工具。”

即使作为一个相对较新的工具，Kubeflow 的使用已经增加，包括在企业用户中。根据 Scott 的说法，这是因为根本没有任何其他管理 ML/AI 工作流的好方法。Casbon 同意这一点，并补充说，她见过的大多数机器学习部署要么使用高度定制的闭源平台，要么是一次性的实现。通过 Kubeflow，数据科学家可以访问软件工程师已经使用的类似级别的工作流自动化——cas bon 表示，希望它将有助于建立管理机器学习管道的行业标准最佳实践。

## 管理复杂性

在 Kubeflow 之前，许多数据科学家使用为软件工程设计的工作流工具，这让他们试图拼凑不适合的部分。典型的机器学习工作流程可能包括以下步骤:数据摄取、数据分析、数据转换、数据验证、模型构建、模型训练、模型验证、大规模训练、服务模型和监控。随着模型的调整和新数据的加入，经常会有几十或几百次的迭代。

“当涉及多个模型时，复杂性会快速增长，维护这种类型的系统很难操作，”Casbon 解释道。“识别和修复错误不像软件工程那样简单，而且模型很难跟踪。”

“机器学习或深度学习项目生命周期中的这些不同部分必须由人工完成，这是一个长期存在的问题，”机器学习顾问兼 Kubeflow 贡献者 [Karthic Rao](https://github.com/hackintoshrao) 解释道。“还没有一种方法可以端到端地自动化或链接这些流程。”

尤其是在企业机器学习应用的背景下，还有其他的挑战。在机器学习应用程序上与多个团队合作需要每个人都使用相同的库版本，如果没有管理更新的工具，这通常很难保证。另外，一旦你定义了你的机器学习栈，你可能需要更新它的一部分或者修改栈。

Canonical 人工智能/人工智能产品经理[卡明·里米](https://www.linkedin.com/in/carminerimi/)解释道:“在企业环境中，这可能非常具有挑战性。“你可以花更多的时间来更新你的堆栈，而不是做你的工作。”

许多数据科学家只是努力跟踪数据的版本和管理几十个模型迭代，当涉及更多的应用程序和功能时，这变得更加困难。

最后，数据管理和物流可能是一项挑战。大多数机器学习应用程序在训练和生产中都使用数万亿字节的数据，这些数据也在不断变化。

“Kubeflow 为解决这些问题提供了一个平台，”Casbon 说。Kubeflow 的可组合特性使得定义您的堆栈并在整个公司范围内实现标准化变得非常容易。Kubeflow 还可以自动管理更新，因此堆栈总是更新的，每个人都在使用相同的版本。

Kubeflow 还有助于管理超参数调整，为数据科学家提供了一个工具来跟踪他们开发、测试和训练模型所经历的迭代，以便他们知道哪组变量产生了最有用的结果。

也许最重要的是，Kubeflow 使用自动化将机器学习应用程序生命周期中的不同阶段缝合在一起，减少了必须手动完成的步骤。这既节省了时间，又降低了出错的几率。

## 为什么是 Kubernetes

Kubeflow 基于 Kubernetes，需要一个 Kubernetes 环境，尽管它可以是任何 Kubernetes 环境、普通的香草或 Google Kubernetes 引擎。这在机器学习环境中提供了几个优点。也许最明显的是，随着 Kubernetes 成为行业标准的容器编排平台，能够在与公司其他应用程序相同的环境中运行机器学习应用程序降低了 IT 复杂性。这也使得在将应用程序推向生产 Kubernetes 环境之前，使用笔记本电脑在本地开发模型变得更加容易。

Kubeflow 也有利用 Kubernetes 特性的特定方式。自动缩放对于机器学习模型极其重要，因为训练可能是非常资源密集型的，而服务于模型通常不是如此。Kubernetes 已经在管理自动缩放，Kubeflow 只是将该功能放入机器学习上下文中。Kubernetes 还管理机器学习应用程序中容器的部署和编排。

“如果没有 Kubernetes，Kubeflow 就不会存在，”斯科特说。"其他任意的工具也会被使用."

Kubeflow 只有一年的历史，它已经被用来管理企业级的机器学习项目。Google 在内部项目中使用 Kubeflow，MapR 在其机器学习产品和为客户构建的定制应用程序中使用 Kubeflow。“我希望看到 Kubeflow 变成今天的 Kubernetes，”阿龙奇克说。不过，最重要的是，他希望 Kubeflow 能够减少构建成功的机器学习应用程序的一些障碍，并扩展机器学习在商业、医疗保健和其他行业的实际应用。

有关 Kubeflow 的更多信息，请收听 TNS 对 Aronchick、Mesosphere 产品营销经理 Chris Gaun 和 Mesosphere 社区项目技术负责人 rg Schad 的采访。

[KubeFlow:用 Kubernetes](https://thenewstack.simplecast.com/episodes/kubeflow-manage-ai-workflows-with-kubernetes) 管理 AI 工作流

管理 Kubernetes 的云本地计算基金会是新堆栈的赞助商。

由[paweczerwiński](https://unsplash.com/photos/BmAOtpBZpMk?utm_source=unsplash&utm_medium=referral&utm_content=creditCopyText)在 [Unsplash](https://unsplash.com/?utm_source=unsplash&utm_medium=referral&utm_content=creditCopyText) 上拍摄的特写图片。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>