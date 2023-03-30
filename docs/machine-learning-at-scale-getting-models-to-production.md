# 大规模机器学习:将模型投入生产

> 原文：<https://thenewstack.io/machine-learning-at-scale-getting-models-to-production/>

[](https://www.linkedin.com/in/sanghamitra-goswami-b6174753/)

[Mitra Goswami](https://www.linkedin.com/in/sanghamitra-goswami-b6174753/)

[Mitra 是 PagerDuty 的高级主管，是一名机器学习专家，在天体物理学、媒体、营销技术和金融服务领域为 ML 产品提供支持。她的专业知识和兴趣在于建立可扩展的以数据为中心的团队，创建经济高效的数据工程解决方案，并引领推动商业价值的 ML 创新。](https://www.linkedin.com/in/sanghamitra-goswami-b6174753/)

[](https://www.linkedin.com/in/sanghamitra-goswami-b6174753/)[](https://www.linkedin.com/in/sanghamitra-goswami-b6174753/)

对于组织来说，将机器学习(ML)模型投入生产并送到客户手中一直是一个重大挑战。根据 [Venturebeat](https://venturebeat.com/2019/07/19/why-do-87-of-data-science-projects-never-make-it-into-production/) 和 [redapt](https://www.redapt.com/blog/why-90-of-machine-learning-models-never-make-it-to-production#:~:text=During%20a%20panel%20at%20last,actually%20make%20it%20into%20production.) 的报道，数据科学家构建的几乎 90%的模型从未成功投入生产。

这是非常不幸的，因为机器学习计划应该解决现实世界的问题。如果机器学习模型无法大规模接触客户，它就无法:

*   尝试解决它想要解决的问题。
*   获得关于解决方案准确性的反馈，从而随着时间的推移而改进(ML 的本质)。

将模型投入生产是一项具有挑战性的任务，原因有几个。下面我将重点阐述四个最重要的问题。

## **问题 1:背景和培训**

数据科学是一个不断发展的领域，迎来了来自不同背景的候选人。用于在新兵训练营和学术界培训数据科学家来构建模型的工具通常不适合生产使用。通常由个人来学习具体的工具，如容器化(如 Docker)或 API 创建(如 Flask)。虽然这些工具在数据科学家的环境中显示出前景，但有时他们不清楚如何部署到生产中。此外，并行化或其他类型的性能效率编码需要复杂的系统架构，数据科学家在加入行业角色之前不一定要学习这些技能。

组织试图通过两种方式解决这个问题:1)雇佣一个全栈数据科学家*、*或者 2)创建一个将数据科学家与软件工程师配对的团队。全栈数据科学家是独角兽，他们可以将数据驱动的概念从识别/构思带到原型构建和执行。他们还负责衡量其数据科学功能的影响，并随着时间的推移不断改进，重点是解决生产环境中的挑战。这些高级数据科学家经历了这一旅程，并随着时间的推移提高了他们的技能，学习了新的工具，并在不同的组织中遇到了生产挑战。

> “如果你担心可伸缩性，任何迫使你运行协议的算法最终都会成为你的瓶颈。把这当成理所当然。”
> <text class="quote-attribution">—亚马逊首席技术官沃纳·威格尔</text>

在数据科学团队中，如果全栈工程师很少，并且数据科学家和具有软件工程技能的数据工程师组合在一起，混合方法似乎最有效。即使雇佣一名全栈工程师也是一个相当大的挑战。另一个选择可能是提高拥有云平台(架构师)认证的数据科学家的技能，并让团队专注于交付。尽管不是每个数据科学家都喜欢软件开发驱动的学习，但它正日益成为一项必要的技能，特别是如果数据科学家希望让他们的模型在生产中运行，而不必依赖他人。

## **第 2 期:两个不同世界的合作**

将模型投入生产需要数据科学家和工程团队的合作。数据科学家希望解决具有创新性和挑战性的业务问题。一旦他们建立了一个原型，他们通常希望软件工程师来负责接下来的步骤。另一方面，软件工程师是构建前端、将模型连接到生产代码、处理持续部署问题和打包的专家。作为最佳实践，高级数据科学家和工程师(有时是 SRE 团队)有责任建立正确的框架来帮助数据科学家成功部署到生产中。他们不需要每次都从头开始发明整个过程。然而，数据科学家和软件工程师必须在这个过渡期合作，以交换感知的有效载荷信息、模型调整、精度测量和其他参数。

因此，自动化起着至关重要的作用。了解部署流程的哪些部分是通用的、可以自动化的，以及哪些组件是特定于特定数据科学功能的，这一点至关重要。例如，在 AWS 中，创建 API 握手点的 Sagemaker 环境是一个通用框架，但是定义有效负载是特定于项目的。我们围绕这些通用接触点构建了加速器或自动化，确保只有定制的操作才需要团队协作。

## **问题 3:实时性能和准确性可能会偏离**

实时性能和准确性可能会大大偏离离线测试。当数据科学家创建模型时，他们用历史数据训练模型。他们还在训练数据的子集上检查模型的准确性。因此，当组织向新的*、*实时客户数据发布模型时，即使是向少数客户发布，模型结果也不总是如预期的那样，并且需要仔细监控实验以确保训练的模型是有效的和准确的。为了在此阶段将不确定性降至最低，数据科学家需要:

*   创建增量敏捷的产品(可以逐步改进)，并在产品发布之前创建度量标准来衡量性能。
*   使用基于百分比的展示或分阶段(alpha、beta 等)发布数据科学产品。，以受控的增量方式移动。

例如，在我们的 AIOps 数据科学功能智能警报分组中，它是[page duty 的事件智能](https://www.pagerduty.com/platform/event-intelligence-and-automation/)(智能事件管理)产品的一部分，后端算法构建为观察实际警报数据和事件历史，并在看到新警报时进行调整。该模型基于强化学习(自动学习)，因此成功率取决于客户数据的规模和细微差别。尽管基于历史数据构建原型很容易，但一旦我们将算法发布给第一批早期用户，调整算法就相当复杂了。在数据科学产品开发的这一阶段，我们需要数据科学家来研究和了解如何调整可用的模型参数，以便准确性不会改变，除非底层数据发生重大变化。只有这样，ML 模型才能随着时间的推移而改进，这样客户就可以在没有数据科学家不断干预的情况下实现 ML 的好处。

## **问题 4:不断变化的数据需求和解决方案**

大数据和机器学习的格局在不断变化。在大数据革命之初，主要是数据量至关重要，而现在也是速度和多样性，因此数据科学家在生产中使用的工具必须适应。例如，几十年来，关系数据库作为数据存储和数据操作的商业解决方案一直占据着主导地位。然而，今天我们需要实时数据流、持久数据存储和快速访问数据存储来处理结构化和非结构化数据。

为了解决这个问题，组织需要为不同类别的数据(事务性、非事务性等)编写访问模式。)并投资于多种类型的适用数据存储，而不是一刀切的选择。

## **总结**

对机器学习和人工智能驱动的决策的追求有时会让商业领袖不切实际，他们认为机器学习和人工智能可以在没有足够投资的情况下瞬间或在短时间内改变他们的业务。数据科学家、工程师和企业领导人需要就以下问题展开健康的讨论:

*   什么是可能的，需要多长时间以及相关的风险。
*   需要哪些必要的投资，以便数据科学家和工程师可以将模型大规模部署到生产中。

机器学习/人工智能技术的成功部署在本质上是跨职能的。必须鼓励拥有不同技能组合的团队进行协作，自动化一般工作，并承担精心计算的实时风险，以推动机器学习模型的结果。这样做还会暴露出不同团队(不仅仅是数据科学团队)必须适应的特定于组织的细微差别。我们希望您能够从我们成功地将机器学习模型投入大规模生产的经验中学到一些东西。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>