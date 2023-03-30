# Optic 如何利用人工智能和机器学习检测 NFT 欺诈

> 原文：<https://thenewstack.io/how-optic-detects-nft-fraud-with-ai-and-machine-learning/>

NFT 空间一直存在欺诈问题，包括不良演员从一个项目中批发艺术作品，并在第二个项目中使用它——这一过程通常被称为“抄袭”它们是衍生项目，与原始项目有太多的相似之处，不能被认为是剽窃。虽然这些重复项目中的大多数相对于原始项目来说销量很小，但它们可能会损害潜在的品牌，导致对 NFT 空间的整体不信任，或欺骗不太精明的买家花钱买一些相当于街头小贩先令假冒劳力士手表的东西。

为了帮助打击这种欺诈，一些专门从事 NFTs 欺诈检测的公司正在兴起。他们倾向于利用区块链数据来帮助确定哪个项目先出现，并应用一些图像检测来找到元数据匹配。其中一个解决方案是 [Optic](https://optic.xyz/about) ，它使用人工智能和机器学习来分析与 NFT 相关的图像，这有助于 NFT 市场和铸造平台捕捉副本，并保护创作者和买家。

在最近的一份新闻稿中，Optic 表示，他们是为 OpenSea 提供 copymint 检测的合作伙伴，open sea 可以说是最知名的 NFT 市场，[在 2022 年 5 月推出了](https://opensea.io/blog/announcements/improving-authenticity-on-opensea-updates-to-verification-and-copymint-prevention/)这一功能。Optic 目前每天处理大约 2TB 的 NFT 元数据，来自数百万新生成的 NFT。他们分析精确拷贝和模糊匹配，包括翻转、旋转、调整大小和颜色变化。

## 人工智能和机器学习驱动的 API

光学背后的人工智能和机器学习利用了[英伟达 Triton](https://developer.nvidia.com/nvidia-triton-inference-server) 推理服务器、 [Milvus](https://milvus.io/docs) 、PyTorch 机器学习框架、 [MLflow](https://mlflow.org/docs/latest/index.html) 、[亚马逊 SageMaker](https://aws.amazon.com/sagemaker/) 、Lightning 以及通过 [DVC](https://dvc.org/) 的开源 ML 版本控制。

如果你有兴趣为自己的项目探索人工智能，新的堆栈有一个关于部署推理服务器的教程，以及一些关于 T2 的文章。考虑到使所有这些技术协同工作的潜在复杂性，如果您正在考虑分析 NFT 元数据的类似解决方案，实现 Optic 的 API 可能比尝试和培训内部解决方案更容易。

Optic 通过批处理 API 或实时 API 支持图像分析。我就这两者之间的区别询问了[光学公司的首席执行官兼创始人安德烈·多罗尼切夫](https://twitter.com/dobry)。他说:“在批处理模式下，市场使用一些数据存储(例如 S3 或雪花)向 Optic 提供他们的目录，Optic 定期读取新数据，检查每个集合，并将匹配结果返回给市场。在实时模式下，市场调用 Optic API，提供令牌元数据，Optic 返回匹配结果，以确定它是原创还是抄袭，以及哪个是原创，匹配分数是多少。”

在下面的截图中，您可以看到一个示例比较以及光学评分。

[![Optic comparison of duplicate NFT projects](img/11a0b687793ad1df8378484e207fa8ae.png)](https://cdn.thenewstack.io/media/2022/07/259c2f19-pivots.png)

我观察到复制经常出现问题的一个领域是，原始版本可能在以太坊上，而项目的副本在 Solana 或 Polygon 上启动。我问多罗尼切夫光学如何解决这个问题。“跨链复制是一个真正的问题，”他说，“这就是为什么我们目前正在匹配以太坊，多边形和索拉纳链的令牌。我们将根据 NFT 的使用情况，优先考虑接下来支持哪些连锁店。”

虽然 Optic API 目前是私有的，但他们计划在 2022 年底之前推出一个公共 API。与此同时，如果你正在为 NFTs 建立一个市场，或者只是想确保用户不会试图利用他人的知识产权，你可以联系 Optic 来[请求访问](https://optic.xyz/about#contact-us)他们的私有 API，或者[加入他们的纷争](https://discord.com/invite/bS2bNkzRAc)与团队合作。还有一份关于即将推出的光学协议的白皮书。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>