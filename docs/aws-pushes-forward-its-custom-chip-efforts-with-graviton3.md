# AWS 通过 Graviton3 推进其定制芯片的努力

> 原文：<https://thenewstack.io/aws-pushes-forward-its-custom-chip-efforts-with-graviton3/>

[亚马逊网络服务](https://aws.amazon.com/?utm_content=inline-mention)上个月扩大了其在[芯片方面的努力](https://thenewstack.io/amazon-web-services-takes-the-silicon-wars-to-the-cloud/)，其亮点是引入了这家大型云提供商的第三代基于 Arm 的 [Graviton 处理器](https://thenewstack.io/aws-graviton-marks-the-emergence-of-arm-for-cloud-native-workloads/)，该处理器将为新的云实例提供动力，旨在处理高性能计算(HPC)、科学建模、分析和基于 CPU 的机器学习推理等计算密集型工作负载。

在 AWS 的 re:Invent 会议上，该公司发布了 Graviton3 处理器，目前正在预览中，以及将在其上运行的 EC2 C7g 实例。与此同时，AWS 首席执行官[亚当·塞利普斯基](https://www.linkedin.com/in/adamselipsky/)还宣布了在该公司一年前的 Trainium 芯片上运行的新 Trn1 实例，旨在处理机器学习训练工作负载，并吹嘘了 2019 年推出的 Inf1 实例的性价比能力，并利用 Inferentia 芯片执行机器学习推理任务。

该公司甚至宣布了基于其 Nitro 固态硬盘(SSD)的存储优化 EC2 实例-Im4gn/is 4gen/I4i，以提高 AWS 云中 I/O 密集型工作负载的存储性能。

## **AWS 专注于芯片**

最新处理器和 EC2 实例的推出是 AWS 多年来努力构建自己的处理器以在其云实例和前哨基础设施中运行的最新证明，这些云实例和前哨基础设施旨在在企业采用混合云模式快速增长的时候向内部数据中心提供 AWS 服务和连接。

这一切都发生在 AWS 于 2016 年收购以色列初创公司 Annapurna Labs 五年后，使其成为其芯片制造工作的基础。

Moor Insights and Strategy 的首席分析师 Patrick Moorhead 告诉 New Stack 说:“AWS 已经在自己的芯片上投入了…年，从 Nitro 开始，扩展到通用 Graviton、用于推理的 Inferentia，现在是用于训练的 Trainium。”。“AWS 可以挑选它想要的每个功能和它不需要的每个功能，以利用自己的软件。它还可以针对特定的网络和存储优化其 I/O。在规模上，这应该允许 it 以更低的成本提供计算，并在某些情况下提供更高的性能。”

穆尔黑德说，英特尔、AMD 和英伟达服务于众多环境中的更广阔市场，一些客户并不使用每一项功能。AWS 正在使用自主开发的计算来区分其实例。

## **性价比是关键**

在他的主题演讲中，Selipsky 强调了企业在利用 AWS 芯片而不是英特尔和 AMD 的 x86 CPUs 或这些供应商和英伟达的 GPU 的实例上运行人工智能、机器学习和分析等工作负载时将获得的性价比优势。

首席执行官表示:“通过 Trainium 和 Inferentia，客户可以获得机器学习的最佳性价比，从扩展训练工作负载到用高性能推理加速生产中的深度学习工作负载，让所有客户都能利用机器学习的全部功能。”“这是我们长期以来的目标，降低训练和推理的成本是这一旅程中的重要一步。”

AWS 没有透露关于 Graviton3 的许多细节。他说，在运行通用计算工作负载时，使用新芯片的实例将比使用 Graviton2 的实例快 25%，在运行一些专用工作负载时甚至会更好。例如，对于科学工作负载和加密作业，它的浮点性能提高了一倍。它运行机器学习应用程序的速度也快了三倍。

## **功效系数**

Graviton3 在实现相同性能的同时，能耗将减少多达 60%，这在一定程度上得益于 DDR5 内存的使用，DDR 5 内存的功耗低于 DDR4，但带宽却增加了 50%。该处理器将运行多达 64 个内核，拥有 500 亿个晶体管，时钟速度为 2.6GHz。

基于 Graviton3 的 C7g 云实例将有各种尺寸，包括裸机模型，[AWS 副总裁兼首席传道者杰夫巴尔](https://www.linkedin.com/in/jeffbarr/)在[博客帖子](https://aws.amazon.com/blogs/aws/join-the-preview-amazon-ec2-c7g-instances-powered-by-new-aws-graviton3-processors/)中写道。

基于推理和训练的实例也是为了降低运行特定工作负载的成本。Selipsky 说，Inf1 实例的每次推理成本比类似的基于 GPU 的 ECs 实例低 70%。与此同时，以 Trainium 为动力的 Trn1 实例旨在从事自然语言处理和图像识别等工作，将提供两倍于基于 GPU 的实例的带宽——高达 800 Gb/s 的 EFA 网络吞吐量。

企业还将能够在 EC2 超级集群中部署 Trn1 实例，EC2 超级集群可以扩展到数万个 Trainium 芯片，并达到 Pb 级。这些超星系团将比之前的 EC2 超星系团大 2.5 倍。

穆尔黑德说:“推理和训练都是为了节省进行生产级推理和核心训练的资金。”。“AWS 一直坚持节约成本的立场，因此，在我看到 Trainium 的结果之前，我非常有信心在某些工作负载上，您将看到显著的节约。”

## **定制芯片趋势**

Graviton、Inferentia 和 Trainium 是行业中向专用处理器发展的更广泛趋势的一部分。在本周[的一篇博文](https://www.arm.com/company/news/2021/12/specialized-processing-driving-era-of-arm-based-cloud-computing)中，[Arm 高级副总裁兼基础设施业务总经理 Chris Bergey](https://www.linkedin.com/in/chrisbergey/) 写道，他的公司设计芯片并将这些设计授权给其他公司，正在通过其节能设计帮助推动这一趋势。

“数据中心工作负载和互联网流量几乎每两年翻一倍，因此性能功耗比的优势对于防止计算增加碳足迹至关重要，”Bergey 写道，并补充说，Arm 在云领域的发展“为开发人员提供了一个选择，通过在每个内核的基础上提供一致的性能和可扩展性，继续进行可持续创新，实现可扩展性能和效率的结合，以提供行业领先的总拥有成本。”

AWS 不是唯一一家寻求设计自己芯片的超大规模公司，因为他们寻求更高的性能和效率。据报道，微软去年决定开发基于 Arm 的芯片，用于 Azure 服务器和谷歌，谷歌拥有张量处理单元和 OpenTitan 安全芯片等定制芯片。脸书也在制造自己的数据中心芯片。

## **构建自己的处理器的挑战**

Enderle Group 的首席分析师 Rob Enderle 告诉 New Stack，他不确定事情会如何发展。

“当公司达到一定规模时，他们倾向于相信他们内部的规模经济将允许他们有效地与专注的提供商竞争，”Enderle 说。“这一最新趋势在很大程度上是由于英特尔错过了许多重要的里程碑……迫使云行业的大多数人考虑这条道路。”

然而，[在首席执行官帕特·基尔辛格](https://thenewstack.io/what-intels-fab-for-hire-plan-could-offer-hyperscale-cloud-platforms/)的领导下，[英特尔的执行力正在提升](https://thenewstack.io/intel-eyes-a-future-of-exaflops-and-zettabytes/)。与此同时，AMD 继续以其 Epyc CPUs 和 GPU 给人留下深刻印象，这表明对定制芯片的需求可能正在减少，他说。

“在供应短缺时期，通过 AMD 和英特尔这样的公司工作可能比单干更容易，因为这些公司不仅应该有更好的供应冗余，而且如果短缺超出了他们的控制范围，也能更好地转移内部决策者的指责，”Enderle 说。“成本仍然是单干的潜在优势，但前提是你忽略了各公司知识产权保护和数十年经验的价值，这些通常会提供抵消性的可靠性、一致性和性能优势。"

此外，随着时间的推移，成本增加，内部努力可能变得无利可图和不可持续。这位分析师表示，部分原因是因为很难找到并留住所需的人才，在熟练员工严重短缺的情况下，这是一个特别的挑战。

“虽然过去并不总是预测未来，AWS 这种规模的公司可以成功地做一些即使是最大的企业也做不到的事情，但自从 IBM 在 20 世纪 90 年代濒临倒闭以来，计算行业(苹果显然是个例外)在很大程度上一再远离垂直整合，”恩德勒说，并补充说，“只要专业化公司能够执行，它们的基本优势仍然有效。"

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>