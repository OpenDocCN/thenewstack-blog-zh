# 英特尔更深入地研究软件开发

> 原文：<https://thenewstack.io/intel-takes-a-deeper-look-at-software-development/>

当帕特·基尔辛格在阔别十多年后于今年 2 月重返英特尔时，他很快就将精力和投资投入到支撑该公司著名的制造业务上，这一业务近年来一直受到生产延迟和错过最后期限的困扰，并使这家全球领先的芯片制造商突然看起来很脆弱。

它包括承诺花费 200 亿美元建造两个新的芯片工厂——或“晶圆厂”——启动一个正式的[芯片代工业务](https://thenewstack.io/what-intels-fab-for-hire-plan-could-offer-hyperscale-cloud-platforms/)来制造其他人的处理器，促进更多的芯片在美国制造的努力，然后在上个月宣布它将再投资 950 亿美元在欧洲建造更多的晶圆厂。

这些举措不仅宣布[英特尔](https://thenewstack.io/intel-unveils-next-generation-neuromorphic-computing-chip/)致力于保持主要芯片制造商的地位，而且也是对 AMD、 [Arm](https://thenewstack.io/arm-looks-to-supercharge-iot-software-development/) 和 [Nvidia](https://thenewstack.io/tutorial-deploy-the-nvidia-gpu-operator-on-kubernetes-based-on-containerd-runtime/) 等竞争对手不断增强的实力以及越来越多为人工智能(AI)和[机器学习](https://thenewstack.io/category/machine-learning/)等特定工作负载优化芯片的较小公司的一种回击。

## **VMware 的软件影响力**

然而，Gelsinger——在之前的八年多时间里，他一直担任 VMware 的首席执行官——也带着“软件第一”的坚定信念回到了英特尔。在一个数据是硬币的 IT 世界中，混合云是新兴的运营模式，[优势正在增长](https://thenewstack.io/tutorial-accelerate-ai-at-edge-with-onnx-runtime-and-intel-neural-compute-stick-2/)人工智能、机器学习和分析等现代工作负载正在脱颖而出，软件成为中心焦点，底层硬件(包括半导体)是其推动者。

这种对软件和开发人员的关注将成为本周英特尔首届[英特尔创新](https://www.intel.com/content/www/us/en/events/on-event-series.html)活动的中心舞台，这实质上是该公司大型英特尔开发者论坛的重启，该论坛于 2016 年举行。将会有一系列针对硬件和芯片的公告，但英特尔官员将会继续努力，把重点放在软件、开发者和开源社区上。

英特尔公司首席技术官兼高级副总裁兼英特尔新成立的[软件和先进技术事业部](https://www.intel.com/content/www/us/en/newsroom/news/intel-makes-changes-strengthen-execution-innovation-critical-business-areas.html#gs.erfq1z)总经理 [Greg Lavender](https://www.linkedin.com/in/greglavender/) 在新闻发布会上说:“我们的观点是，给市场选择，给开发者选择，我们希望成为值得信赖的合作伙伴，提供大量的开源技术，我们已经这样做了，但在过去几年里我们没有过多地谈论它。”。“我们将讨论我们现有资源的广度和深度及其可用性。”

## **将零件组装在一起**

Lavender 于 6 月份来到英特尔，主要是为了在英特尔内部创建一个软件团队，将分散在整个公司的不同部分整合在一起。他和 Gelsinger 相识几十年，并在 VMware 共事了四年。他说，Gelsinger 在 2009 年离开之前在英特尔工作了 30 年，对英特尔硬件历史有着深刻的理解，但在 VMware 工作后，软件优先的方法“现在是他 DNA 的一部分。”

在此次活动中，英特尔重新推出了其[开发人员专区](https://www.intel.com/content/www/us/en/developer/overview.html)，使这些开发人员的资产参考设计和工具包可通过单一门户获得。组件开发人员将可以访问从客户端和数据中心硬件到人工智能、云和边缘以及游戏的所有内容。开发人员专区还将包括一个整合的英特尔开发人员软件产品目录和一个改进的 DevCloud 开发环境，用于在 CPU、[GPU](https://thenewstack.io/nvidia-gpus-nudge-hpe-supercomputer-into-the-exascale/)、现场可编程门阵列(FPGAs)、加速器和软件工具等英特尔组件上测试和运行工作负载。

公司官员还表示，公司已经准备好为 oneAPI 提供最新的工具包，oneAPI 是去年推出的一种编程模型，旨在简化英特尔 CPU 和加速器(如 GPU 和 FPGAs)的软件开发。OneAPI 2022 将包括 900 项新功能，包括通过新的统一 C++/SYCL/Fortran 编译器和数据并行 Python(用于 Python 开发)为 CPU 和 GPU 开发软件的能力。新的工具包还扩展了 Advisor 加速器性能建模，将 VTune Flame Graph 纳入其中，并扩展了与 Microsoft Visual Studio 代码的集成以及对 Microsoft WSL 2 的支持。

此外，英特尔 oneAPI 卓越中心的新合作伙伴，包括橡树岭国家实验室、田纳西大学和加州大学伯克利分校，正在提供战略代码端口、更多硬件支持、课程开发以及旨在加速 oneAPI 采用的新技术和服务。

## **与开源社区合作**

这家芯片制造商还强调了它正在与开源社区合作开发一些最新的芯片，包括下一代至强可扩展处理器——代号为“[蓝宝石急流](https://www.intel.com/content/www/us/en/newsroom/opinion/updates-next-gen-data-center-platform-sapphire-rapids.html)”——和 Ponte Vecchio GPU。英特尔正在与芯片制造商 SiPearl 合作，通过添加 Ponte Vecchio 作为加速器，设计一款基于 Arm 的处理器，用于欧洲的亿亿次超级计算机。此外，SiPearl 正在利用 oneAPI 作为开放软件规范来提高开发人员的工作效率和工作负载性能。

Lavender 指出，英特尔的编译器技术属于他的职权范围，对 Sapphire Rapids 和其他芯片至关重要，因为它优化了开源代码以及来自 ISV 的代码。

在可编程网络方面，英特尔推出了一款基于 ASIC 的智能处理单元(IPU)，代号为“ [Mount Evans](https://www.intel.com/content/www/us/en/products/platforms/details/mount-evans.html) ”，与谷歌云联合开发，包括对行业标准编程语言开源基础设施程序员开发套件的支持，以方便开发人员访问谷歌云数据中心的技术。英特尔的结构处理器 Tofino 3 利用 P4 可编程性和人工智能工作负载加速为交换带来智能。

## **获取信息**

Lavender 说，英特尔多年来一直拥有强大的软件开发团队和与开源社区的关系，但过去一直没有对此发表足够的意见。对于芯片制造商来说，关键是确保使用英特尔平台的最广泛的开发人员能够获得和使用其软件。

他说，例如，用于人工智能和机器学习工作负载的最新版本 [TensorFlow](https://thenewstack.io/train-a-tensorflow-model-with-a-kubeflow-jupyter-notebook-server/) 库——8 月发布的 2.6 版——包括英特尔的加速器，已被下载超过 800 万次。

拉文德说:“我们努力做到相对无缝。”。“如果您想在至强处理器或英特尔酷睿处理器上运行 TensorFlow，无论您在哪里运行推理技术，您都有优势。我们的 OpenVINO 技术(用于深度学习和人工智能推理工作负载)得到了广泛应用，开发人员可以将其视为一个完整的平台和生态系统，而不必了解底层硬件，特别是为了获得将他们的模型[部署到边缘](https://thenewstack.io/where-service-mesh-and-smartnics-meet/)并在边缘对数据进行推理的价值。”

他说，关键是英特尔“必须在开发者所在的地方与他们见面。”

“我们希望让人们对我们的技术感兴趣，并免费引进顾问和咨询人员，帮助他们发展自己的公司，”拉文德说。“无论他们是在 Azure 云，还是在[亚马逊网络服务](https://aws.amazon.com/?utm_content=inline-mention)，无论他们是在谷歌云，无论他们是在[阿里巴巴](https://thenewstack.io/alibaba-github-repos-most-active-in-china/)云，还是在 IBM 云，无论他们是通过他们在 Red Hat、SUSE 或任何其他发行版上的数据中心在他们自己的私有云上运行，我们的软件技术都将在那里，我们认为 oneAPI 工具包将在今天的所有环境中运行。我们需要在所有这些环境中工作。”

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>