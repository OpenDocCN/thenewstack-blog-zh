# 解决运营无服务器和跨云兼容性问题

> 原文：<https://thenewstack.io/tackling-operational-serverless-and-cross-cloud-compatibility/>

[#163:解决运营无服务器和跨云兼容性](https://thenewstack.simplecast.com/episodes/163-tackling-operational-serverless-and-cross-cloud-compatibility)

无服务器计算听起来像天堂，但如果没有正确的思维模式，它可能是地狱。考虑到云提供商对无服务器环境的限制、应用程序激增和版本变化的可能性，以及构建无服务器环境所需的普遍思维转变，向云功能的转变不是一朝一夕的事情。

“无服务器平台的有趣之处在于，它们是一个受限的执行环境，这是一件好事。这意味着云供应商可以以完全可定制的成本的一小部分为客户提供功能…问题是，由于这些平台仍在不断成熟，它们必然会受到所允许的执行类型的限制。例如，他们中的大多数人不会让你跑步超过五分钟或十分钟…挑战是，如果你不能在统一的环境中跑步怎么办？这就是容器发挥作用的地方， [Pulumi](https://www.pulumi.com/) 的产品经理[唐娜·马拉耶里](https://www.linkedin.com/in/donnamalayeri/)博士说。

“好吧，我们要写一些函数，但是我们如何处理我们的数据呢？我们有 14pb 的数据，我们不能就这么异想天开地把它移到某个地方。因此，从这个角度引入更多的环境控制对我来说是一件大事。我不断遇到这些情况，很多时候这仍然是一个大问号。我们要做什么？我们开始在这种新的无服务器架构上构建，但我们仍然有巨大的数据问题。

“业务关注点是什么？”我向马拉耶里询问了经常阻碍公司发展的数据要求。“为什么数据放在一个云中不好？这是一个业务连续性问题吗？因为，如果是的话，这是一个非常有趣的考虑。如果 [AWS](https://aws.amazon.com/) 停机，我需要冗余，我需要在其他地方运行它，这是你试图解决的问题的一部分。”

“我看到的另一个更令人困惑的问题是对供应商锁定的担忧。10 年后亚马逊会提价，而我们会被套牢。有时候，公司会过早地解决这个问题。他们会说，‘让我们构建这个解决方案，让它完全通用，可以移植到任何云上。问题是你最终要为一个可能永远不会到来的未来付出具体的代价。

Malayeri 说，如果有明确的商业理由，公司最好把时间花在跨云兼容性上。例如，如果一家公司要求其数据中心冗余，或者如果一家公司专门使用亚马逊，但希望使用[谷歌云的机器学习](https://cloud.google.com/products/machine-learning/)工具。她说，这些场景提供了建立跨云兼容性的真正理由，而不是简单地专注于避免供应商锁定。

### 在这个版本中:

[4:42:](https://thenewstack.simplecast.com/episodes/163-tackling-operational-serverless-and-cross-cloud-compatibility?t=4:42) 我如何管理无服务器环境和应用？
[8:14:](https://thenewstack.simplecast.com/episodes/163-tackling-operational-serverless-and-cross-cloud-compatibility?t=8:14) 你如何处理那些数据和状态？
[10:30:](https://thenewstack.simplecast.com/episodes/163-tackling-operational-serverless-and-cross-cloud-compatibility?t=10:30) 低代码环境和抽象层是传播企业云使用的好方法吗？
[13:16:](https://thenewstack.simplecast.com/episodes/163-tackling-operational-serverless-and-cross-cloud-compatibility?t=13:16) 随着无服务器架构的发展，我们所看到的复杂性
[20:15:](https://thenewstack.simplecast.com/episodes/163-tackling-operational-serverless-and-cross-cloud-compatibility?t=20:15) 如今无服务器在企业中的使用情况如何？
[26:49:](https://thenewstack.simplecast.com/episodes/163-tackling-operational-serverless-and-cross-cloud-compatibility?t=26:49) 在监控和性能方面，您需要考虑哪些潜在问题？

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>