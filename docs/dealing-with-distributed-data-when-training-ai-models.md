# 训练人工智能模型时处理分布式数据

> 原文：<https://thenewstack.io/dealing-with-distributed-data-when-training-ai-models/>

联合学习是一个工具，让你的手机自动更正你的拼写，而不用上传你的整个文本。它还可以应用于在数据源训练人工智能，而不必将其集中在一个位置。

这种方法可能会在医疗保健和金融等受监管行业(法律问题可能意味着数据不能跨辖区移动)以及数据本质上是分散的物联网领域带来突破。

人工智能公司 [integrate.ai](https://www.integrate.ai/) 的创始人兼首席执行官 [Steve Irvine](https://www.linkedin.com/in/steveirvine/?originalSubdomain=ca) 说:“一些你和我都希望能够进入这个世界的最有意义的用例，以及开发人员想要带入这个世界的用例，因为数据不能移动而被阻止了。“数据不是必须到达一个中心位置来训练机器学习模型，而是模型的版本被发送到数据所在的位置。”

新的 Stack 与 Irvine 进行了交谈，以了解 integrate.ai 如何部署联合学习来[在不汇集数据的情况下训练 ai 模型](https://thenewstack.io/transparent-ai-explainable-and-trainable-artificial-intelligence/)。

## 它是如何工作的

Integrate.ai 提供了一个软件开发工具包，它创建了一个预置的 [Docker 容器](https://thenewstack.io/how-to-share-data-between-docker-containers/)，其中包含了在本地训练模型所需的库和其他工具。开发人员或数据保管人可以决定在容器中包含或不包含什么数据。integrate.ai 然后获取模型并联合它，让它在选定的数据节点上训练。

“如果你要建立一个全新的网络，这就像几行代码一样简单，”欧文说。“基本上，它会在您的环境中创建一个容器，无论它在哪里，然后您可以决定将哪些数据放入其中，并决定该数据适合参与哪些任务。”

数据本身不会移动。该模型在本地环境中运行，然后跨所有节点进行通信和协调，以优化该模型，就好像它已经对同一本地存储库中的所有数据进行了训练一样。他解释说，然后它将参数更新回全球模型。

“它在后端创造了一个无缝的体验——研究人员永远不会知道其中的区别，除非他们不上飞机，等一年才能运行一个模型，而他们可以在几分钟内完成，”欧文说。

所有这些幕后操作——设置网络、训练模型、平均模型，以及确保所有这些都以隐私安全的方式完成——都可以通过 API 进行控制，这些 API 通过 SDK 进行安装和使用。

训练结束后，Docker 容器被拆除。这个工具很大程度上是基于 Python 的，但是它支持 Irvine 所说的“定制模型”

“大多数数据科学家会使用类似于 [Jupyter 笔记本](https://thenewstack.io/configure-a-kubeflow-jupyter-notebook-server-for-data-preparation/)的东西，这是他们实际构建模型的地方。我们只是在 Jupyter 笔记本中显示命令，”他说。“因此，您可以在构建模型的同一个地方联合您的模型；你可以在同样的环境中训练他们。”

他声称，这为开发人员和数据科学家带来了无缝体验。

## 开源选项

有一些开源工具可以用于联合学习。 [Nvidia 提供 Nvidia Flare](https://thenewstack.io/nvidia-shaves-up-to-30-off-large-language-model-training-times/) ，一个进行联合学习的开源框架，而 [Google Federate](https://thenewstack.io/federated-learning-lets-data-stay-distributed/) 允许构建联合模型，他说。阿里巴巴今年也推出了一个联合框架。

“有很多大型开源方法来做实验，但它们通常专注于让数据科学家能够进行实验和模拟，”Irvine 说。“如果你是一名开发人员，负责在你的产品中加入这一功能，这就是目前市场上存在的差距，因为这些开源系统要求你能够基本上拥有并管理它。”

Irvine 认为这就是 integrate.ai 与众不同的地方，就像行业的[Stripe](https://thenewstack.io/stripe-for-developer-payments-with-new-3scale-service/)一样，简化了集成工作。

## 联合学习的用例

他说:[联合学习](https://thenewstack.io/federated-learning-lets-data-stay-distributed/)为受监管的行业带来了很多机会，比如医疗保健和金融服务。一个用例是一个跨国组织，由于法规原因，它可能无法将数据移动到一个位置。Irvine 说，其他用例可能包括组织之间的合作，在这种情况下移动数据可能不可行或效率不高，例如扫描来自不同国家不同医院的乳腺癌 x 光片。

“现在，你不能集中数据；他说:“有很多规定不允许你跨辖区移动任何数据。“您的应用程序无法正常工作，尽管所有这些客户都很乐意合作，因为他们只是希望检测更好，更准确。”

欧文说，其他潜在的用例包括使用驻留在边缘或[物联网设备](https://thenewstack.io/foundries-io-a-platform-for-iot-development-and-deployment/)上的[数据来训练模型。他补充说，这也是有意义的，因为它降低了成本，隐私和安全问题。](https://thenewstack.io/new_tools_moves_ai_from_backend_to_edge/)

“当世界上的一切都是一台计算机、一个数据采集和决策设备时，我们就必须有不同的网络基础设施来支持构建网络。”

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>