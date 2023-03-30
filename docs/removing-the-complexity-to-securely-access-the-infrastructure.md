# 消除安全访问基础架构的复杂性

> 原文：<https://thenewstack.io/removing-the-complexity-to-securely-access-the-infrastructure/>

随着技术堆栈的增长，必须在云计算环境中配置的技术列表呈指数级增长，并增加了 IT 基础架构的复杂性。虽然堆栈的每一层都有自己的加密连接、客户端身份验证、授权和审计实施，但开发人员和 DevOps 团队在正确设置对硬件的安全访问方面面临的挑战是，整个组织中的软件将继续增长，从而使 it 环境变得越来越脆弱。

在这一集的 New Stack Makers 播客中，Teleport 的开发人员关系经理 Ben Arent 讨论了如何通过使用 Teleport 9.0 和该公司首次发布的 Teleport Machine ID 等工具来解决来自云的硬件、软件和 peopleware 复杂性。 [Alex Williams](/author/alex/) ，New Stack 的创始人和发行人，主持了这个播客。

[消除复杂性，安全访问基础设施](https://thenewstack.simplecast.com/episodes/removing-the-complexity-to-securely-access-the-infrastructure)

随着 IT 堆栈转向云，混合基础架构环境中的共享责任模式增加了复杂性，“Teleport 所做的是帮助团队提供对所有基础架构的轻松安全的访问，从服务器、Kubernetes、集群到 AWS 管理控制台，”Arent 说。他说:一切都是基于你那天获得的背景证书。

该公司最近发布了 Teleport Machine ID，它“提供了对短期证书的相同访问，但用于机器对机器的通信，”Arent 说。Arent 说，有了 Teleport Machine ID，使用 tbots 每 20 分钟发布一次访问证书，这是一种自动检索证书的服务。“如果有一个妥协，凭证可以很容易地被锁定，并有一个完整的审计日志，在这些运行期间发生了什么，”他补充说。

Arent 说，由于数据库存储着一些最敏感的信息，保护对这一层的访问至关重要。他补充说，团队成员经常使用共享登录，然后离开公司，但使用 Teleport 9.0 用户可以识别团队中的哪个人访问了特定的数据库，从而提供了那层可见性。

[https://www.youtube.com/embed/1k9TXCkxrRI](https://www.youtube.com/embed/1k9TXCkxrRI)

视频

但是对于许多开发者来说，Teleport 是“关于合规性审计的”。许多人认为它是一本日记。如果您正在访问您的家庭实验室，确切地知道您做了什么会很有帮助，并且您可以返回查看您在特定机器上做了什么。”

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>