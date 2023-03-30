# 当今云世界中的无服务器、功能和挑战

> 原文：<https://thenewstack.io/serverless-functions-and-challenges-in-todays-cloud-native-world/>

甲骨文公司赞助了这次播客。

[无服务器、API 网关和挑战当今的云原生世界](https://thenewstack.simplecast.com/episodes/serverless-api-gateways-and-challenges-in-todays-cloud-native-world)

针对云原生部署的新服务和工具不断涌现，在已经非常复杂的选择网络中争夺一席之地。

在巴塞罗那 KubeCon + CloudNativeCon 由 New Stack 创始人兼主编 Alex Williams 主持的播客中，主要话题是 [Oracle](https://www.oracle.com/index.html) 和 [Autom8 的无服务器工具和目标。网络](https://gitlab.com/autom8.network)，提供分散的功能即服务(FaaS)。

播客嘉宾[甲骨文高级软件开发人员 Maddie Patrichi](https://www.linkedin.com/in/ioana-madalina-patrichi/?originalSubdomain=uk) 和 Autom8 联合创始人兼首席技术官 [Gregg Altschul](https://www.linkedin.com/in/gregg-altschul) 。网络，提供他们的想法和描述他们的项目。

Altschul 描述了 Autom8。Network 正在创建一个分散的 FaaS 平台，供开发人员部署他们的功能。“由于它是分散的，我们去寻找一个节点，无论它在哪里，它在那里运行并返回一个结果，如果开发者想从他们运行的功能中赚钱，你只需支付计算时间和少量版税，”Altschul 说。

从一开始，Altschul 就说 Autom8。网络试图避免被单一的云供应商或技术所束缚。“我们可以在 Lambda 上建立这样的东西，但那样我们就会成为 AWS Lambda，我们就会被束缚在那个生态系统中。或者我们可以选择任何其他类型的技术，如谷歌或其他类似的云提供的技术，但你仍然会被困在这些技术中，”Altschul 说。“还有其他技术可以让您构建自己的数据中心，如果您有自己的数据中心，您可以将这些东西放入其中并进行构建。”

帕特里奇说，对于帕特里奇的团队和他们的 API gateway 项目，他们试图使用 Kubernetes，但“放弃了”。帕特里奇描述了主要问题是如何牵涉到安全问题的。例如，客户可以访问 API 网关数据计划，“因此，如果我们有一个从控制平面到数据平面的漏洞，那么从数据平面基本上可以访问所有的客户租户，”Patrichi 说。

“所以，你并不是真的想要 Kubernetes(在这种情况下)。Kubernetes 非常成熟，社区在识别安全问题和为这些安全问题提供补丁方面做得非常好，但是……在我们特定的 API 网关案例中，它可能并不总是安全的。"这种类型的交流，你知道，来来回回，不是功能的最佳方式."

一天结束时，帕特里奇说她不相信“Kubernetes 更像一把瑞士刀。”“因此，我认为它更适合服务应用程序，但不一定适合提供商——我们是服务提供商，我们希望建立架构，我们希望负责架构，”Patrichi 说。“所以，这就是为什么我们有点信任问题，你知道我们正在处理非常敏感的信息。我们有庞大的客户，政府也是客户，所以我们非常非常有安全意识。”

[https://www.youtube.com/embed/TWR-YPDuGYg?feature=oembed](https://www.youtube.com/embed/TWR-YPDuGYg?feature=oembed)

视频

### 在这个版本中:

[1:33:](https://thenewstack.simplecast.com/episodes/serverless-api-gateways-and-challenges-in-todays-cloud-native-world?t=1:33) Maddie，您之前说过您正在与 Oracle 合作开发他们的 API 网关。你能告诉我们一点吗？
[3:03:](https://thenewstack.simplecast.com/episodes/serverless-api-gateways-and-challenges-in-todays-cloud-native-world?t=3:03) 请简单介绍一下您开始看到的无服务器架构，以及您为什么选择 Fn？我知道你有一个自己开发的点对点网络，你把 Fn 放在上面。造成这种情况的原因是什么？
[7:36:](https://thenewstack.simplecast.com/episodes/serverless-api-gateways-and-challenges-in-todays-cloud-native-world?t=7:36) Maddie，你的团队对函数的理念是什么，它们如何适应 API Gateway？
[14:53:](https://thenewstack.simplecast.com/episodes/serverless-api-gateways-and-challenges-in-todays-cloud-native-world?t=14:53)FaaS 在 API 网关中的角色，这为您提供了什么优势？这有什么独特的？
[18:22:](https://thenewstack.simplecast.com/episodes/serverless-api-gateways-and-challenges-in-todays-cloud-native-world?t=18:22) 当了解到软件供应链的存在时，你如何发展你的姿态？
[24:44:](https://thenewstack.simplecast.com/episodes/serverless-api-gateways-and-challenges-in-todays-cloud-native-world?t=24:44)Maddie，在您考虑 API 网关和功能集成时，您的团队在未来六个月内会优先考虑哪些方面？

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>