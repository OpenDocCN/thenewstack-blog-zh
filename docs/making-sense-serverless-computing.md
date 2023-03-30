# 理解无服务器计算

> 原文：<https://thenewstack.io/making-sense-serverless-computing/>

这篇文章是我们将从演讲者那里收集的一系列介绍性文章中的第一篇

[To the Cloud and Beyond](http://cloudnativecomputing.softwarecircus.io/)

，这是一个为期三天的关于云计算的精彩会议

[Software Circus](https://twitter.com/softwarecircus)

集体研讨会，8 月 31 日至 9 月 2 日在阿姆斯特丹举行。

Michael Hausenblas 是 Mesosphere 的一名开发者支持者，他在 meso sphere 帮助 AppOps 构建和运营分布式服务。他的背景是大规模数据集成、Hadoop/NoSQL 和物联网，并且在宣传和标准化(W3C 和 IETF)方面经验丰富。Michael 为 DC/OS 项目等开源软件做出了贡献，并通过代码、博客文章和公开演讲分享了他在分布式系统和大规模数据处理方面的经验。

2016 年，我们将见证[无服务器模式](http://martinfowler.com/articles/serverless.html)成为主流。虽然这个名字本身是一个用词不当的名称——多次尝试 [将其重命名为更合理的名称都失败了——但其背后的基本思想似乎很有说服力:将计算单元变成一个单一的函数，有效地提供一个轻量级和动态可扩展的计算环境。](https://medium.com/@mhausenblas/pets-vs-cattle-vs-flock-of-birds-12f1da3abfc3)

> 有人提出，只有真正的无服务器计算[在公共云产品中才有意义](http://serverlesscalc.com/)；这个案子还没有定论。

随着容器的出现，我们已经看到了第一个转变:从管理整个(虚拟)机器到应用程序级的依赖性管理。然而，即使有了容器，人们仍然必须处理不同层次的抽象；例如，虽然 Docker 映像很好地打包了 NGINX 之类的 web 服务器，但是仍然需要确定放入的内容，并准备好 CI/CD 管道来生成这些映像。

从这个意义上说，无服务器更类似于 PaaS:不用担心底层组件，只需提供代码。其他的，经常[提到的](https://twitter.com/patrickdebois/status/734459440603275264)优势包括弹性和成本。大多数(如果不是全部的话)无服务器计算[产品](https://451research.com/report-short?entityId=89566)在幕后使用容器，但现在相关的挑战(如容器编排)是其他人的问题——您可以受益于隔离保证和(任意)代码的即时执行。

然而，以可伸缩的方式孤立地执行函数的能力是不够的:我们需要能够触发函数的执行。简而言之，这意味着与网关等其他服务和物联网等特定领域产品的集成越好，无服务器平台就越有价值和有用。无服务器领域的现任者 AWS Lambda 是一个很好的例子，它提供了与 S3、SNS 或 CloudWatch 等其他服务的广泛和深度集成。

有许多众所周知的[案例](https://www.linkedin.com/pulse/5-killer-use-cases-aws-lambda-karoly-sepsy)，其中[非常适合](https://speakerdeck.com/mhausenblas/microservices-are-so-2015-whats-next):主要围绕事件驱动架构中相当短时间运行的无状态作业，通常在移动应用程序(想想: [Pokemon Go](https://thenewstack.io/wild-week-augment-realitys-first-killer-app-pokemon-go/) )或物联网应用程序中发现，例如传感器阵列每天更新一次其值。无服务器在这种情况下如此有效的原因是，您必须在短时间内处理大量相对简单的操作，但是[与 PaaS](https://twitter.com/adrianco/status/736553530689998848) 相比，您的规模单位是单一功能。通常，在这种自动扩展的背景下，人们会提出这样的论点，即真正的无服务器计算在公共云产品中有意义。这个案子还没有定论。

现在让我们将注意力转向无服务器计算的[挑战](https://medium.com/@PaulDJohnston/when-not-to-use-serverless-jeff-6d054d0e7098)，这些挑战大致分为两类:用例阻抗不匹配和 [DevOps 相关主题](https://www.reddit.com/r/serverless/comments/4odiyv/researching_aws_lambda_what_are_the_challenges/):

*   有状态服务最好在无服务器功能之外完成(与其他平台服务(如数据库或存储)的集成对实现这一点极其重要)
*   长时间运行的工作(几分钟到几小时)不太合适，典型的期望值在秒的范围内。
*   日志记录和[监控](https://twitter.com/danielbryantuk/status/743092989321478145)是一个巨大的挑战:一方面，当前的产品对这些运营需求提供的支持很少，此外，由于生命周期短，期望与传统环境大相径庭。
*   本地开发可能具有挑战性:通常，开发人员需要在在线环境中进行开发和测试。
*   语言支持:大多数无服务器产品只支持少数几种编程语言。

强调一点:无服务器模式通过短反馈循环和操作方面加强了 DevOps 文化——尽管目前没有完全解决——当然，发挥了重要作用。

然而，无服务器计算将继续存在，而不是将其视为适用于各种使用案例和工作负载的银弹，最好将其理解为云原生工具箱中的另一个工具。

[中间层](https://d2iq.com/)是新堆栈的赞助商。

通过 Pixabay 的特征图像

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>