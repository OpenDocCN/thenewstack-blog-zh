# 红帽招募黑鸭评估集装箱安全

> 原文：<https://thenewstack.io/red-hat-enlists-black-duck-fortify-container-security/>

红帽公司周二宣布与安全公司黑鸭(Black Duck)合作，这可能是迄今为止解决集装箱安全问题最雄心勃勃的举措。

我们的目标是提供一个容器内容的深度视图，以便未来的策略驱动系统可以根据可执行文件的源代码揭示的容器可以做什么来批准或拒绝容器的部署，尤其是在生产环境中。

“Black Duck 有许多非常有趣的工具，主要是在 Black Duck Hub 品牌下，允许开发人员实际签入或分析源代码或二进制文件，”Red Hat 集成解决方案总经理 Lars Herrmann 说。这些工具可以洞察源代码的来源，以及运行这样的软件会带来什么样的安全和许可问题。

## 少了一面墙

开源项目通常由从其他地方合法获得的开源代码组成。在开源系统开发的旧世界中，将组件打包在一个 tarball 或其他包中是相对容易的，库存系统可以检查它的内容。资产管理软件的出现有助于数据中心跟踪其大量开源许可证，现在许多组织需要它们来满足合规性和监管准则。

随着越来越多的组织，尤其是金融服务行业的组织，依赖独立的风险管理来确保其数据中心的完整性，容器化的支持者迄今为止还无法变出一种分析和确保容器内容的技术，一种像更成熟的服务交付系统一样自动化或可信的技术，如[VMware v realize Orchestrator](https://www.vmware.com/products/vrealize-orchestrator)。

如果 Red Hat 在 Black Duck 的帮助下能够实现其集装箱完整性管理的愿景，这种情况可能会改变。

您可能熟悉通过签名扫描已知恶意代码的安全软件。Black Duck Hub 以类似的方式扫描已知的开放源代码，目的是识别可能需要用更新、更安全的版本替换的代码。

Red Hat 的 Herrmann 说:“Black Duck Hub 能够追踪源代码的版本信息，还可以与应用流存储库进行比较。容器中的所有东西都会被检查——运行时组件、所有应用程序代码，或者开发人员选择使用的任何附加框架或库。Herrmann 说，由此产生的分析可以提供“关于容器图像可能有什么问题”的见解。

Herrmann 描绘了一幅未来的图画，很可能是联合品牌的服务，它可以提供对容器内代码完整性的一般风险分析。此外，Herrmann 认为一种策略驱动的管道可以集成到现有的编排系统(如 Kubernetes)中，使 DevOps 专业人员和管理员能够制定规则和策略，限制生产环境中高风险代码的执行。

这种系统(诚然，在这个阶段，理论上)可以消除组织在生产中部署容器环境的主要保留——调查继续显示，这种保留使当今生产中的大多数容器化环境被限制在有限的虚拟机内。

## 制约

Herrmann 告诉 New Stack，这种未来的系统，也是这种新的合作关系的目标，将促进新的和扩展的企业变更管理和库存系统。

他说:“我们的愿景是一个开放的架构，在这个架构中，你可以获得各种针对不同层次的 API。”“因此，您可以直接访问 Black Duck，查看哪些集装箱图像已经在您的注册表中，以及它们在任何时间点的风险评估。”

通过一个 Red Hat API，也许是通过 OpenShift，Black Duck 返回的库存数据可以关联到一个被 Herrmann 称为“当前暴露”的指数中。仪表板可以生成一个不同的列表，评估当前运行在生产环境中的代码相对于开发或测试中的代码的相对暴露程度。

然后，基于策略的决策可以确定容器中等待部署的新代码的好处是否远远超过风险因素。这种控制对于已经习惯于并且在很大程度上依赖于由 VM 监控系统提供的保证和风险指数的企业内集装箱化的批准可能是绝对必要的。

“我们看到现在在集装箱管理和集装箱安全领域有很多创新和创造性思维，”赫尔曼告诉《新堆栈》。“因此，我们希望能够解决采用集装箱化的一个关键障碍。我接触的每一个客户都在问我，‘我怎样才能让它变得安全呢？’？我怎么知道怎么回事？“我可以使用哪些工具，”所以我们可以给他们很多工具，也可以给他们所有的 API，这样其他工具就可以围绕它来构建。我们可以为企业围绕容器创建一个充满活力的开放生态系统。"

Red Hat 和 VMware 是新堆栈的赞助商。

特征图片:“[请进！](https://www.flickr.com/photos/joceykinghorn/10012135796/in/photolist-gfJP9Y-ajeQsN-abez57-ajeQ8E-nFXHBL-ajc222-oSTEKk-fi1RkW-nng7Ft-ajc1gi-uysK3M-5mHuiN-y8xVQ-uxNUJY-acZdbW-abbKjM-uvVruu-tBeq8b-fi1Bm1-uyofc2-ajeNz7-oezxxH-uxKvAj-oSQGEu-uxP1Lh-uyfkhP-ajc3fB-5NsbFp-5NwsbS-fSbyyG-ugCvoS-oQPTW5-p83HCR-ugFPc1-ugAsNY-pPGd6c-pxi2Xy-oaLf37-tBeuFj-ugNvpV-tBexwu-5NsbqZ-fhk2qV-5mDbRZ-nVj131-iBoCv1-oezwm4-ajeNmC-q4SfPf-dVQc5v)[乔斯林·金霍恩](https://www.flickr.com/photos/joceykinghorn/)的获得 [CC BY-SA 2.0](https://creativecommons.org/licenses/by-sa/2.0/) 的授权。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>