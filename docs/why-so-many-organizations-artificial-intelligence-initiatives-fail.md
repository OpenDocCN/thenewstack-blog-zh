# 为什么这么多组织的人工智能计划失败了

> 原文：<https://thenewstack.io/why-so-many-organizations-artificial-intelligence-initiatives-fail/>

你正在你的 iPhone 上寻找你朋友的一张照片，这张照片是几年前拍的。有成千上万的图片可以搜索，但苹果照片应用程序会锁定正确的人，然后很快！几秒钟内你就能找到你要找的照片。

幕后有很多工作在实现这一点，包括面部识别和图像分析以及自动标记，通过推断什么是需要的或想要的来节省精力，然后实时根据这些推断采取行动。

像苹果这样的公司——以及谷歌、联邦快递、优步、网飞——已经花了数年时间来构建系统和架构，使用户体验变得更容易、更个性化、更直观。在某些情况下，人工智能能够几乎瞬间做出关键决策，或者实时做出预测，让企业能够立即改善结果。

这在更广泛的企业领域并没有被忽略:根据 [2022 年德勤调查](https://www2.deloitte.com/us/en/pages/consulting/articles/state-of-ai-2022.html)，94%的商业领袖表示人工智能对成功至关重要。

那么，为什么对于大多数组织来说，构建成功的人工智能应用程序是一个巨大的挑战呢？这可以归结为三大障碍:错误的数据在错误的时间出现在错误的基础设施中。

## 人工智能成功的障碍

[根据麦肯锡](https://www.mckinsey.com/~/media/McKinsey/Business%20Functions/McKinsey%20Analytics/Our%20Insights/Global%20survey%20The%20state%20of%20AI%20in%202021/Global-survey-The-state-of-AI-in-2021.pdf)的数据，56%的公司已经采用了人工智能，但正如埃森哲在一份[报告](https://www.accenture.com/us-en/insights/artificial-intelligence/ai-maturity-and-transformation)中指出的，只有 12%的公司成功实现了人工智能的卓越增长和业务转型。

许多绊脚石阻挡了将人工智能成功构建成实时应用程序的道路，但大多数都与一个核心元素有关:数据。

许多传统的 ML/AI 系统，以及它们产生的结果，依赖于[数据仓库](https://thenewstack.io/build-data-factories-not-data-warehouses/)和批处理。结果是:需要一系列复杂的技术、数据移动和转换来将这些历史数据“带到”机器学习系统。

输入到 ML 模型中的数据称为特征(可用于分析的可测量属性)，通常基于应用程序数据库中存储的数据或写入日志文件的数据。它们通常需要转换，例如基于先前记录的缩放值或计算(例如，记录生成时的移动平均值)。

这通常会减缓数据从输入到决策再到输出的流动，导致错失机会，从而导致客户流失，或者已识别的网络安全威胁模式未被检测到且未得到缓解。挑战可以归结为拥有不合适的数据集，由移动速度过慢的错位基础架构支持。

## 错误的数据

由于庞大的数据量(以及相关的成本)，为了便于传输和可用性，必须对数据进行汇总。简而言之，聚合或过度转换的数据会阻止组织轻松地实时确定适当的行动，并降低实现首选结果的可能性，无论是建议的产品、更新的包裹递送路线还是工厂机器上的调整设置。这降低了组织寻找新问题答案、预测结果或适应快速发展环境的能力。

数据科学家被迫使用粗粒度数据集，这将产生模糊的预测，进而不会产生预期的业务影响，特别是在像客户会议这样的离散环境中。当应用程序被重新配置或数据源发生变化时，他们也可能不知道，从而导致无法提供特性的重要事件。在选择模型时，这些缺失的数据会导致不明智的决策。这会导致预测性能不准确，或者更糟的是，使用错误数据的模型会导致错误的决策。

最后，聚合的重点是创建现有的特性。新的特征工程(处理选择和训练模型所需的数据)需要返回不同聚合的原始数据。这种额外的处理大大降低了数据科学家的工作速度，延长了实验过程。

## …在错误的基础架构中

第二个挑战与当前推动人工智能计划的 ML 基础设施有关，它们无法大规模处理数据集。模型的质量及其结果随着事件数据量的增加而提高。组织通常需要处理大量事件，传统基础架构无法应对。

为运行推理而服务的训练模型的序列变得复杂，尤其是当它需要在每个模型之间移动数据时。试图处理高质量预测所需的规模将传统架构推向了崩溃的边缘。它也非常慢，不可靠，成本高。所有这些都威胁着日益关键的应用程序的价值和影响。

## …在错误的时间

另一个绊脚石是处理数据太晚，无法产生任何重大影响。当前的架构需要通过多个系统处理数据以服务于一个模型，这引入了延迟，以各种方式影响人工智能计划:

*   模型的输出不能改变事态发展的进程。例如，当转换率下降时，它向客户提供优惠，而客户可能已经购买了其他东西。
*   为模型提供服务并获得结果所需的时间与数字体验或自动化流程的预期不符。有时，可能要过几天数据才能准备好进行处理。在竞争激烈的市场中，这么旧的数据往好里说是无关紧要的，往坏里说是危险的(想象一下一个拼车应用在危机或灾难期间应用激增定价)。
*   数据科学家无法获得最新数据。这可能会影响模型的结果，并可能需要数据科学家花费宝贵的时间来寻找额外的数据点或来源。

许多当前的 ML 基础设施不能为应用服务，因为它们太贵、太复杂、太慢。监管变化最终可能会要求组织提供更详细的解释，说明模型是如何训练的，以及它们为什么会做出特定的决定。由于所涉及的处理、聚合和各种工具，这种级别的可见性在当前的架构中是不可能的。

许多基础设施的问题在于数据必须经过人工智能驱动的应用程序的旅程。问题的答案，简单来说就是反其道而行之。

## 将人工智能引入数据

领导者，如本文开头提到的公司，通过聚集来自客户、设备、传感器或合作伙伴的大量实时数据，随着数据在应用程序中流动，从而取得成功。这些数据反过来用于训练和服务他们的模型。这些公司即时根据这些数据采取行动，为数百万客户提供实时服务。

领导者成功的另一个关键因素是，他们以最精细的方式收集所有数据——作为带有时间戳的事件。这意味着他们不仅有大量的数据；随着时间的推移，他们也能理解发生了什么以及什么时候发生的。

像网飞、联邦快递和优步这样的领先企业“将人工智能带到数据所在的地方”，因此他们可以在应用程序所在的地方提供推理。换句话说，他们将他们的 ML 模型嵌入到他们的应用程序中，通过流媒体服务实时聚合事件，并将这些数据暴露给 ML 模型。他们有一个数据库(在上面提到的三个领导者的例子中，是高通量、开源的 NoSQL 数据库 [Apache Cassandra](https://dtsx.io/3jhSOC8) )可以存储大量的事件数据。

借助正确的统一数据平台，ML 计划拥有正确的基础设施和正确的数据。数据工程师和数据科学家可以“打破他们的筒仓”，并调整他们的特征工程、模型实验、训练和推理过程，以支持预测。虽然这些过程仍然需要许多工具，但它们都在相同的数据基础上工作。

由海量事件数据驱动以服务于模型和应用，由人工智能驱动的最成功的应用通过不断改进它们提供给最终用户的体验来区分和领先。他们服务数百万客户的能力，以及他们变得越来越聪明的能力，使他们能够定义他们所处的市场。

[*了解 DataStax 如何启用实时 AI*](https://dtsx.io/3JqTekn) 。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>