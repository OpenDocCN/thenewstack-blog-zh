# 量子开发者的早期，但无服务器时代即将到来

> 原文：<https://thenewstack.io/early-days-for-quantum-developers-but-serverless-coming/>

IBM 是[量子计算硬件](https://thenewstack.io/quantum-computing-use-cases/)的领先公司之一，其路线图的目标是到 2023 年底超过 1000 个量子比特。这就是所谓的“量子优势”水平，量子计算将在[的某些用例](https://thenewstack.io/quantum-computing-use-cases-how-viable-is-it-really/)中超越经典计算。因此，我们知道 IBM 正在硬件方面进行创新，但它在量子计算的软件方面也同样雄心勃勃吗？而在 IBM 的 quantum 平台上做开发者是什么样子的？

为了回答这些问题，我采访了 IBM Quantum 的量子平台负责人 [Blake Johnson](https://www.linkedin.com/in/blake-johnson-b8747417b/) ，以及 Qiskit 运行时团队的产品经理 [Tushar Mittal](https://www.linkedin.com/in/tushar-mittal/) 。

根据约翰逊的说法，执行量子代码不仅仅是加载代码并点击运行。“我们已经建立了允许我们在运行时和量子系统本身之间进行交互式执行的系统，”他说，并补充说，量子计算目前的一个问题是“应对和处理量子系统有噪音的事实。”他在这里指的是量子计算机的物理操作，它目前涉及许多[干扰](https://www.quintessencelabs.com/blog/current-quantum-computers-noisy%E2%80%8B/)——这反过来会引入误差。

“应对噪音需要专业知识，”他继续说道，“我们可以将这些知识打包成最佳实践，并为开发人员提供更易于使用的体验。”

## Qiskit 运行时在 IBM 平台中的作用

当涉及到对 IBM 的量子计算机进行编程时，默认平台是 [Qiskit](https://qiskit.org/) —一个用 Python 构建的开源软件开发工具包(SDK)。Qiskit 由 IBM 开发，[于 2017 年 3 月发布](https://medium.com/qiskit/qiskit-turns-one-looking-back-cbc2c48d7a95)。像许多同类领先的 SDK 一样，Qiskit 在电路层面上运行，这意味着它专注于构建和编译量子电路。

去年， [Qiskit Runtime](https://www.ibm.com/quantum/qiskit-runtime) 作为 Qiskit 之上的抽象层推出。它的[主要目标](https://research.ibm.com/blog/qiskit-runtime-for-useful-quantum-computing)是“将执行模型从执行电路的服务转变为执行程序的服务。”

Qiskit Runtime 的产品经理 Mittal 告诉我，他的任务是让开发人员更高效地构建工作负载并对其进行迭代。但他也澄清说，Qiskit Runtime 不一定是为开发应用程序而优化的——不像, [Classiq 的抽象层](https://thenewstack.io/classiq-brings-abstraction-layer-to-quantum-software-stack/)。Qiskit 运行时所做的是优化代码执行的效率和性能。

“需要发生这两个层次的分解，”Mittal 解释说，指的是将一个复杂的软件问题或系统分解成几个部分的过程。“一个是应用特定的；另一个是研究可用设备的限制，以及可以运行的协议类型。”Qiskit Runtime 则侧重于后者。

## 早期原始人

去年，IBM 发布了两个 Qiskit 运行时原语——第一个用于优化采样操作，第二个用于估计操作。例如，[采样器原语](https://qiskit.org/documentation/partners/qiskit_ibm_runtime/tutorials/how-to-getting-started-with-sampler.html)“将用户电路作为输入，并生成减少误差的准概率读数。”

这听起来有点吓人，所以我问这些原语是否可以被 Python 开发人员使用？“在目前的模式下，用户仍然需要了解如何构建一个他们想要利用的电路，”米塔尔回答说。然而，他补充说，“我们的目标是继续让它变得更容易。”

随着时间的推移，IBM 的目标是减轻开发人员优化量子计算机性能的负担。

Johnson 重申这是关于“拥有可以处理噪音的方法”，这是 Qiskit Runtime 的主要目标。他提到了 IBM 最近的一篇博文，内容是关于[错误缓解技术](https://research.ibm.com/blog/gammabar-for-quantum-advantage)如何降低量子噪声的影响。

“在今年剩下的时间里，我们将把这些先进的技术融合进来，这些技术仅仅在一年前还是研究的想法，”他说，“并让它们直接在 Qiskit 运行时原语中可用，希望通过接口使这变得容易和容易。”

## 用例

我问，开发人员使用 Qiskit 运行时和这些原语是为了什么样的用例？

“我认为受众的主要焦点是算法开发者，”米塔尔回答道。"所以很多用例都是围绕变分算法展开的."

他说，估计器原语“非常好地映射到像变分量子本征解算器这样的算法——可以用于化学和优化问题。”至于 sampler 原语，用例包括“使用量子支持向量机的分类问题”

这些听起来像是涉及量子电路知识的用例，所以我问 IBM 是否计划让普通开发人员更容易使用量子机器。例如，Python 开发者将他们的机器学习用例带到 Qiskit 运行时？

“我们的团队已经有了各种原型，”约翰逊说，“在更广泛的 Qiskit 生态系统中，所谓的 Qiskit 应用模块，如 [Qiskit Nature](https://qiskit.org/documentation/nature/) 和 [Qiskit Machine Learning](https://qiskit.org/documentation/machine-learning/) ，它们试图做到这一点。”

Qiskit 文档声称，Qiskit 机器学习应用模块“非常容易使用，允许用户在没有深入的量子计算知识的情况下快速原型化第一个模型。”用户还可以将他们的量子神经网络集成到 PyTorch 中，这是一个流行的开源 ML 库。

然而，约翰逊强调，在这个阶段，这些都是“纯粹的原型”，他们还有更多工作要做，“将那些需求，那些人们舒适工作的领域，与[量子]硬件的能力结合起来。”

## 量子无服务器

从开发人员的角度来看，Qiskit Runtime 显然非常专注于优化量子计算机的性能，因此在这一点上，它更适合理解量子电路的开发人员。

Qiskit 运行时的开发路线图将继续面向其高级用户，但是 IBM 也将为普通开发人员开发托管服务。

米塔尔说，IBM 计划扩展其运行时间，并找出“提供与弹性计算集成的方法——这就是我们所说的量子无服务器。”

他补充说，他们将更加关注“用户应该考虑构建应用程序的方式，因为他们将拥有这些[量子]能力[和]托管体验。”

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>