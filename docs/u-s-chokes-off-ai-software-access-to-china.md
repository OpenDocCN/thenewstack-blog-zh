# 美国阻止人工智能软件进入中国

> 原文：<https://thenewstack.io/u-s-chokes-off-ai-software-access-to-china/>

最近几周，美国政府采取了积极措施，遏制中国在人工智能领域取得进展的努力，同时推动国内超级计算和人工智能的计算基础设施。

美国政府已经禁止向中国出口尖端芯片，包括 AMD 和 Nvidia 等公司的特定图形处理器。

该禁令切断了中国获得源自美国的人工智能芯片和软件的途径。美国政府希望该禁令将阻止中国在人工智能方面的快速进步，这是一项国家优先事项。

## Nvidia 上的 Nix

GPU 出口禁令还将限制中国实体通过英伟达 [CUDA](https://thenewstack.io/cuda-12-harnesses-a-nvidias-speedier-gpu-architecture/) 并行编程框架编写高级人工智能软件的能力。CUDA 允许程序员编写软件，利用 GPU 的进步来更快地处理人工智能程序。

[战略与国际研究中心](https://www.csis.org/)在最近发表的一份[研究报告](https://www.csis.org/analysis/choking-chinas-access-future-ai)中引用富邦证券投资服务公司的数据称，“CUDA 软件和英伟达硬件的组合优势在很大程度上解释了为什么英伟达占中国人工智能芯片销售额的 95%”。

美国政府还切断了对英伟达最新 GPU 的访问，这些 GPU 包括今年宣布的 Hopper 架构。

这项禁令一直在修改，也对出口支持硬件运行的软件进行了限制。这意味着 CUDA 本身可能会被禁止，尽管这还有待确定。英伟达的企业人工智能软件套件(Enterprise AI software suite)基于 CUDA，可以帮助组织为垂直行业编写人工智能应用程序。

Nvidia 预计将在未来几个月发布 CUDA 的下一个版本，即版本 12，该版本旨在利用 Hopper 的计算能力。中国公司将能够在基于 Ampere 的 A100 等旧 GPU 上使用 CUDA 12，但人工智能应用程序将运行较慢。

英伟达不会将其 A100 和 H100 芯片运往中国，这可能会减缓 CUDA 的采用。AMD 的开源并行编程框架，称为 [ROCm](https://thenewstack.io/amd-builds-out-a-software-strategy-after-acquisitions/) ，可能是一个受益者，因为它没有将人工智能软件锁定在其 GPU 上。

## 其他选择

中国实体也可以选择像 OpenCL 这样的并行框架，OpenCL 是开源的，由 Khronos Group 管理。像 [TensorFlow](https://thenewstack.io/look-inside-tensorflow-googles-open-source-deep-learning-framework/) 和 [Pytorch](https://thenewstack.io/pytorch-takes-ai-ml-back-to-its-research-open-source-roots/) 这样的 AI 工具都是开源的，可以免费使用。使用 SYCLomatic 等工具也可以轻松地从程序中剥离特定于 CUDA 的代码，SYCLomatic 可以迁移和自动化代码，以便在一系列 CPU、GPU 和 FPGAs 上执行。

从长远来看，中国的目标是减少对美国芯片和软件工具的依赖。中国的大学和公司正在放弃 x86，开发基于 [RISC-V](https://thenewstack.io/open-source-risc-v-serving-a-side-of-software-with-chips/) 架构的芯片，这是一种免费许可的开源指令集架构。

中国曾试图开发国产尖端芯片，但进展艰难，难以赶上英特尔和英伟达制造的芯片。在 8 月份的 Hot Chips 峰会上，一家名为 [Biren Technology](https://isesglobal.com/members/shanghai-biren-technology/) 的中国初创公司谈到了其使用 7 纳米工艺制造的最新 GPU，这表明该公司正在为人工智能应用开发加速器。

本月早些时候，来自美国实体名单上的[中国科学院](https://en.wikipedia.org/wiki/Chinese_Academy_of_Sciences)的研究人员分享了中国研究人员如何使用敏捷开发方法设计香山 RISC-V 芯片的方法。迭代方法类似于云原生公司如何使用 DevOps 来编写和部署代码。但是[论文](https://github.com/OpenXiangShan/XiangShan-doc/blob/main/publications/micro2022-xiangshan.pdf)显示了英特尔和 AMD 等公司对 FPGA 技术的严重依赖，这些公司可以在生产前制作 RISC-V 芯片的原型。

英伟达曾经认为中国是一个重要的市场，每年在中国举行 GTC 会议。该公司于 2009 年成立了中国科学院作为 CUDA 卓越中心。2011 年，中国教育部将 CUDA 列为技术教育[的一部分](https://nvidianews.nvidia.com/news/chinese-ministry-of-education-to-integrate-cuda-programming-curriculum-in-universities-nationwide-6622839)，此后，关于 CUDA 在中国各行业应用的研究论文不断发表。

## 切断通路

美国政府还切断了中国获得开发尖端芯片的最新软件工具的途径。EDA(电子设计自动化)工具在芯片制造的早期是必不可少的——该软件允许芯片设计师模拟和测试芯片的数字副本，然后帮助最终确定工厂生产的物理产品。

美国的目标是关闭对像 Synopsys 和 Cadence 这样占据市场主导地位的公司的工具的访问。

开源 EDA 工具如[谷歌的 OpenROAD](https://theopenroadproject.org/) 是可用的，但它们大多用于旧制造节点上的芯片设计。

这些限制是基于[外国直接产品规则](https://www.federalregister.gov/documents/2022/02/03/2022-02302/foreign-direct-product-rules-organization-clarification-and-correction)，在俄罗斯入侵乌克兰后，该规则也被用于禁止向俄罗斯出口技术产品。FPDR 以前被用来阻止美国公司与华为做生意，华为的产品被认为是对国家安全的威胁。

出口管制措施出台之际，美国政府正采取一系列措施来加强国内半导体生产、研究和供应链。美国总统乔·拜登(Joe Biden)最近签署了《美国为美国生产半导体(芯片)创造有益激励法案》，该法案开放了超过 500 亿美元的公共资金，以促进美国芯片基础设施的发展。

[芯片法案](https://thenewstack.io/chips-act-pushes-funding-to-exascale-app-dev-and-devsecops/)有两个部分专注于芯片制造和研发。芯片制造计划为包括英特尔、TSMC 和三星在内的几家公司提供了 2800 万美元的激励措施，以在美国建立先进的芯片工厂。英特尔和 TSMC 正在亚利桑那州凤凰城附近建立制造工厂，而三星正在得克萨斯州建立工厂。另外 100 亿美元的资金将用于像德州仪器这样的芯片制造公司在旧节点上建立工厂，生产用于日常电子产品和汽车的芯片。

其余约 110 亿美元的资金将用于制造、材料和芯片开发技术的研发。美国商务部下属的国家标准与技术研究所负责管理芯片法案项目。

NIST 的芯片项目办公室现在欢迎公众对制造和研发计划提出意见。这些投入与构建资金结构、减少芯片伪造以及通过确保激励措施不被用于股票回购等公司目的来保护纳税人有关，股票回购在科技公司中非常普遍。

NIST 也欢迎公众对建立美国制造研究所的投入，这是一项促进最新材料、芯片、计算和软件技术的公私合作的努力。政府还在建立研究所，作为 DARPA 等政府机构开发和测试最新芯片的机制，这些芯片可能用于战斗机等设备。

英特尔已经表示愿意推动芯片的学术研究。该公司宣布，它将为研究人员和学术机构开放工厂，以获得在 EDA 工具中设计的芯片的物理版本。英特尔正在提供工艺开发工具包，这将有助于学术界为英特尔的制造节点设计芯片，然后在工厂生产。

“我们的目的是创造一个合作和竞争的环境。把它想象成自动驾驶的 DARPA 挑战。这有点像硅挑战。英特尔代工服务客户解决方案工程部副总裁兼总经理 [Bob Brennan](https://www.linkedin.com/in/bobbrennan40/) 表示:“我们正努力鼓励大学中的所有教授共同合作进行研究，同时打造最好的知识产权。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>