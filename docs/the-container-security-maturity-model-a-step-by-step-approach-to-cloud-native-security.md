# 容器安全性成熟度模型，一种逐步实现云原生安全性的方法

> 原文：<https://thenewstack.io/the-container-security-maturity-model-a-step-by-step-approach-to-cloud-native-security/>

[](https://www.stackrox.com/)

 [米歇尔·麦克林

作为 StackRox 的产品营销副总裁，米歇尔负责监督公司所有的产品营销战略和计划。她拥有 20 多年的市场定位、GTM 和需求挖掘经验。在加入 StackRox 之前，她是 ScaleArc 的营销副总裁，负责监督所有的对外营销活动，此前她曾在 Silver Spring Networks、ConSentry Networks、Peribit Networks 和 Trapeze Networks 担任产品营销总监。她曾在研究公司 META Group 担任项目总监，为全球 2000 强企业客户提供技术和战略指导。她以一名科技记者开始了她的职业生涯。米歇尔在加州大学伯克利分校获得英语学士学位。](https://www.stackrox.com/) [](https://www.stackrox.com/)

传统基础设施附带了一套强大的安全工具和最佳实践。从服务器和虚拟机到使用容器和 Kubernetes 的云原生环境的过渡并没有结束攻击的威胁或影响，也没有将责任转移到云提供商。相反，它带来了一系列新的不同的[安全挑战](https://www.stackrox.com/post/2020/05/kubernetes-security-101/#kubernetes-security-risks-and-challenges)，并使传统工具过时。了解基于云的容器化操作中的安全挑战及其所需的有效缓解策略，对于保护您的业务至关重要。

我们已经意识到，随着组织对云技术的使用的增加，他们需要的安全实践的类型和范围可以沿着一条曲线绘制。该曲线定义了一个组织从一个初级初学者到一个高度成熟的容器化应用程序开发者的旅程中所经历的各个阶段。我们将这条曲线称为[容器安全成熟度模型](https://security.stackrox.com/rs/219-UEH-533/images/container-security-maturity-model-final.pdf)。随着集装箱旅程的进行，安全要求会急剧上升。以此为指导，了解您所处的阶段，评估您当前的安全状况，并准备进入下一阶段。

**第一阶段:了解集装箱。**在这里，个人使用自己的机器学习容器的基本知识。它通常是作为一个附带项目开始的，而不是一个官方认可的项目。由于这项工作不是为生产部署而设计的，所以在安全性方面没有太多问题，所以您不太需要专用的安全工具。

**第二阶段:正式批准项目。**在这一阶段，某人的第一阶段学习练习转变为——或者一个全新的努力变成了——一个注定要投入生产的正式项目。这是第一阶段的一大步，第一阶段通常只涉及一个人。第二阶段通常有一个完整的团队来完成这个项目。在这里，私有图像注册中心对于执行有关图像扫描和图像访问的策略非常有用。包含多个容器的 pod 在这里发挥了作用，Kubernetes 也是如此，它编排了这些 pod。Kubernetes 带来了自己的漏洞，需要自己独特的工具包。至于这个阶段的安全性，您将需要修改和编纂安全策略，以适应容器化应用程序的需要。控制配置的自动化工具在这个阶段也是一大优势。Kubernetes-native 安全工具已经被证明是有用的，尽管以容器为中心的安全工具在一段时间内已经足够了。

第 3 阶段:在生产中部署单个应用程序。现在，您有了一个面向互联网的应用程序，为您的组织创造了真实的曝光率。在这里，Kubernetes 真正发挥了作用，提供了容器调度、负载平衡、健康检查、自动修复、故障转移等等。您的团队将处于学习曲线上，以跟上这些协调互动的复杂性。为了安全，您需要用更多的限制来强化环境，了解遵从标准，扩展您的配置管理以跨越容器和 Kubernetes，提供初始或扩展的网络分段，并添加运行时安全性。在这个阶段，如果没有 Kubernetes-native security，您的团队将无法跟上，它利用 Kubernetes 的上下文和控件来实现内置的安全性，而不是附加的安全性。

**第四阶段:扩张。**在这一阶段，组织要么将多个应用程序容器化，要么扩展初始应用程序。基础设施和安全性方面的复杂性都增加了。现在，针对法规遵从性、事件响应和更广泛协作的安全要求占据了中心位置。在这个阶段，具有大量安全防护的组织治理策略对于确保标准的工作流至关重要。自动化在这里至关重要，因为您要处理多个集群，手动流程根本不够。Kubernetes——本机安全性仍然是应对复杂性的基础，因为所有策略都驻留在基础设施中，并且继承了 Kubernetes 在自动化、可伸缩性和可移植性方面的优势。

**阶段 5:在组织范围内采用容器。**这一阶段代表了组织在容器使用方面的发展高潮。在这一点上，容器基本上占据了所有新的开发，通常旧的应用程序正在迁移到容器中。通过服务网格，您的基础设施可能呈现出一种新形式的复杂性，这可以提供超越 Kubernetes 所能提供的编排。以额外技术层为特征的完全自动化，有时包括安全性代码，也可以作为组织在此阶段的特征。当您到达容器的广泛使用阶段时，您的 Kubernetes-native 安全能力将会与您一起成长。

没有一个组织能达到完美的安全。但是，您必须在发展基础设施知识的同时，增强您的安全能力。安全性应该与集装箱运输过程中的基础设施紧密相关。和往常一样，良好的安全性不仅仅局限于工具，还需要组织结构和协作实践，将 DevOps 和安全性结合起来，实现成功的容器之旅。

通过 Pixabay 的特征图像。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>