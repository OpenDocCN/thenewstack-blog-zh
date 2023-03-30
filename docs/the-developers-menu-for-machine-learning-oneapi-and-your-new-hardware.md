# 机器学习的开发者菜单:oneAPI 和你的新硬件

> 原文：<https://thenewstack.io/the-developers-menu-for-machine-learning-oneapi-and-your-new-hardware/>

机器学习(ML)开始对应用程序的开发方式产生重大影响，因为数据科学家和 ML 工程师在 DevOps 中发挥着越来越重要的作用。运行应用程序的硬件和基础架构选择将与过去一样重要，同时改变未来数据中心的概念和管理。

由英特尔领导的行业范围的跨架构规范 [oneAPI](https://www.oneapi.com/) 正是基于这些新动态而创建的，旨在满足开发人员对以 ML 和数据科学为中心的 CI/CD 的编码和数据建模需求。随着 it 的发展，开发运维团队的技能组合及其与底层数据中心基础架构的关系也在不断发展。这些是新堆栈的直播系列“[机器学习日:oneAPI 和数据中心的未来](https://thenewstack.io/a-day-with-intel-on-hacking-and-scaling-machine-learning-with-open-source/)”的关键主题

英特尔首席工程师[米娜·阿鲁纳恰拉姆](https://www.linkedin.com/in/meena-arunachalam-b2812b2/)在直播中讨论了扩展人工智能应用程序和实现这一目标所需的硬件，她表示:“仅仅关注‘我想快速优化人工智能算法或技术’是不够的，而是要考虑整个生态系统，几乎就像一名数据工程师将[开发]任务交给一名数据科学家，后者将任务交给一名人工智能工程师。”。“我们过去常说，‘硬件-软件协同设计’，我现在要说[或重新表述]为‘硬件人工智能协同设计’:我要理解我的算法、我的数据、我的建模和所有这些[ML]技术……这样，最终，我可以为用户和开发人员创造最好、最愉快的应用体验，同时也是最高效和最有成效的。”

在本文中，我们将从开发人员的角度出发，介绍 oneAPI 在 API 发展中的位置，它在大规模 ML 应用开发中的用途，以及 DevOps 与硬件的交互以及数据中心的总体发展情况。

[https://www.youtube.com/embed/6Ol21vD1ag0?feature=oembed](https://www.youtube.com/embed/6Ol21vD1ag0?feature=oembed)

视频

## oneAPI 承诺

在过去的几十年中，API 已经成为开发人员和运营团队成员能够大规模构建和管理应用程序的不可或缺的角色。在 API 的发展过程中，oneAPI 规范充当了一个框架，开发人员使用它来构建库代码、文档和其他资源，以解决与开发加速器架构应用程序相关的挑战。作为一个包含编程语言和库的软件层，英特尔架构图形和软件部门的人工智能产品经理 Saumya Satish 将 oneAPI 描述为一个开放的行业规范，“其他供应商可以为他们的不同架构贡献和实现它。”

[英特尔 oneAPI](https://software.intel.com/content/www/us/en/develop/tools/oneapi.html) ，顾名思义，自 2018 年创建以来，一直是一个更加面向英特尔硬件的框架。Satish 表示，英特尔 oneAPI 产品“提供了 oneAPI 的实施，以利用我们多样化架构的最佳功能，同时英特尔也在多样化架构方面进行了大量投资，并提供了一系列不同的选项和选择。”

通过这种方式，英特尔 oneAPI 为创建 ML 系统/应用的开发人员和数据科学家提供了英特尔硬件优化框架和库，以在多个领域实现最佳性能，包括数学、分析、机器学习、深度神经网络、视频处理等。开发人员无需选择和混合不同的相关库和框架，而是可以通过简单易用的以领域为中心的工具包访问针对特定英特尔 XPUs 优化的资源。

对于人工智能和机器学习，oneAPI 提供了[英特尔人工智能分析工具包](https://software.intel.com/content/www/us/en/develop/tools/oneapi/ai-analytics-toolkit.html)，用于加速端到端数据科学和 ML 管道。该工具包包括流行的开源 DL 框架(Tensorflow、Pytorch)和 ML 库(scikit-learn、XGBoost)以及一个轻量级可扩展数据框架——Modin，所有这些都针对使用 oneAPI 库的英特尔 XPUs 进行了优化，并通过最少或无代码更改来提供嵌入式加速。

英特尔深度学习软件首席工程师 [AG Ramesh](https://www.linkedin.com/in/rameshbabukv) 表示:“oneAPI 是一种访问一些内部硬件的方式，能够利用它提供的指令集方面的一些功能来加速人工智能和机器学习。“可以为特定的硬件定制后端”，因此一个 DNN 内核可以在多个平台上工作。

[https://www.youtube.com/embed/BqzvUx_XFZ8?feature=oembed](https://www.youtube.com/embed/BqzvUx_XFZ8?feature=oembed)

视频

例如，借助[英特尔 oneAPI 深度神经网络库(oneDNN)](https://software.intel.com/content/www/us/en/develop/tools/oneapi/components/onednn.html) ，开发人员可以通过单个 API 访问 Nvidia 图形处理器单元(GPU)、英特尔中央处理器单元(CPU)、现场编程门阵列(FPGAs)和其他设备的代码，用于计算和硬件密集型 ML 应用。

如果没有必要的 API 框架，许多开发团队可能会举步维艰，特别是当他们缺乏内部技能和其他资源来创建 ML 应用程序，而没有单一的端到端框架来帮助完成任务时。

“当开发人员或数据科学家不知道如何在合理的时间和预算内创建所需的概念证明时，许多 ML 项目在早期阶段就夭折了。[企业管理协会(EMA)](https://www.enterprisemanagement.com/) 的分析师[托尔斯滕·沃尔克](https://www.linkedin.com/in/torstenvolk/)说:“他们经常拥有数据、算法、代码库，甚至是如何训练和验证模型的知识，但由于无法为他们的特定用例建立一切而失败。”。“英特尔 oneAPI 恰好解决了将[DL 和] ML 框架与底层处理硬件相连接的问题，因此开发人员只需对 oneAPI 编写一次代码，oneAPI 便可决定最佳性能模型训练或推断所需的硬件。”

作为一个案例研究的例子，谷歌依赖英特尔 oneAPI 使用 [TensorFlow](https://www.tensorflow.org/) 作为其 ML 应用开发需求的开源平台。Ramesh 说，谷歌使用英特尔 oneAPI 作为“整理 TensorFlow 使用的数据和特定平台的 oneDNN 之间的数据所必需的代码”。

Ramesh 说，谷歌和其他客户一样，受益于英特尔 oneAPI，以便实现“硬件的正确设置，并从底层硬件获得所有好处，而用户不必[完全]了解他们正在使用什么系统”。

[https://www.youtube.com/embed/RDYdThZ9X8Y?feature=oembed](https://www.youtube.com/embed/RDYdThZ9X8Y?feature=oembed)

视频

## 按钮和旋钮

随着应用开发继续向云环境转移，硬件设备选择将对 ML 应用性能产生直接影响。因此，开发人员和工程师必须在硬件选择过程中提供意见，就像他们为现场数据中心选择设备一样，无论是亚马逊网络服务、谷歌还是微软管理他们的基础设施。英特尔 oneAPI 特别适合这一硬件选择流程。

“开发人员本质上想要控制他们正在使用的机器。他们希望能够使用所有的杠杆和旋钮，所以我认为裸机正在成为他们正在寻找的解决方案之一:基于处理器或使用[英特尔加速器](https://www.intel.com/content/www/us/en/homepage.html)，[Equinix](https://www.linkedin.com/in/paulteich/)的产品管理-基础设施总监保罗·泰奇说。“但因为它在深度学习软件框架内，所以你希望获得你能获得的所有性能。”

一个开发团队可能会试验并创建一个应用程序以在无服务器环境中进行测试，但最终，一个雄心勃勃的 ML 应用程序开发项目将需要非常具体的库、文档和硬件，以便在部署后正常运行。

“由于英特尔 oneAPI 和(行业规范)oneAPI 以代码形式提供硬件加速，企业可以利用单个 API 功能的集中利用率数据来规划数据中心和云资源的未来投资，”Volk 说。“只要目标基础设施支持 oneAPI，相同的 AI/ML 模型应该可以在 AWS、Azure、Google Cloud 或其他任何地方运行。”

## 面向 ML 的端到端框架

ML 应用程序开发可能是出了名的困难，而不使用框架和库(如 oneAPI 提供的那些)的开发团队很容易发现自己陷入困境，如上所述。

O'Reilly Media 人工智能和数据副总裁 Rachel Roumeliotis[表示:“一些公司将足够大，以至于他们将建立自己的数据管道(用于人工智能应用开发)，但我也认为会有更多的公司寻求这些解决方案。”。“我认为他们仍然需要考虑这些框架，但是他们需要这些框架的帮助，”比如 oneAPI。](https://www.linkedin.com/in/rachelroumeliotis/)

Volk 说，让开发人员和数据科学家在 ML 应用程序上工作的供应商应该“击败任何从他们的硬件基础设施中榨取更多性能、密度或成本效率的供应商”。由于开发人员和数据科学家通常不是确定什么硬件特定的加速器功能或指令集可用于什么硬件组件的专家，因此“这些指令中的绝大多数并没有增加它的设计价值，”Volk 说。

“oneAPI 旨在通过统一的 API 平台提供这些特定于硬件的加速功能，从而节省开发人员的时间，同时提高应用速度和基础设施利用率——本质上是“ML-Acceleration as Code，”Volk 说。

[https://www.youtube.com/embed/fi6g5aKw0_Y?feature=oembed](https://www.youtube.com/embed/fi6g5aKw0_Y?feature=oembed)

视频

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>