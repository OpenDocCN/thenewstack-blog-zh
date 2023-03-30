# 本周编程:是什么阻止了生锈和老化？

> 原文：<https://thenewstack.io/this-week-in-programming-whats-holding-back-rust-and-go/>

在过去的一周里，我们看到 [Rust](https://www.rust-lang.org/) 和 [Go](https://golang.org/) 团队发布了他们过去一年的年度调查结果，强调了语言的各种用例及模式，他们在此期间采取的积极措施，以及使用这些语言的开发人员仍然看到的障碍。当然，选择[是否使用一个而不是另一个](https://thenewstack.io/this-week-in-programming-rust-versus-go-why-not-both/)在很大程度上取决于开发者和手头的任务，调查显示这也可能是你工作的公司或你使用的公共云环境的问题。

简单来说受欢迎程度，Go 在三个常用语言指数中领先 Rust，分别是 [PYPL 编程语言受欢迎程度指数](http://pypl.github.io/PYPL.html)、 [TIOBE 指数](https://www.tiobe.com/tiobe-index/)和 [Redmonk 语言排名](https://redmonk.com/sogrady/2020/02/28/language-rankings-1-20/)。如果我们寻找一个简单的原因，它可能会在 InfoWorld 强调的 Rust 调查的一个方面找到，事实上,[开发人员列举了 Rust 语言采用的障碍](https://www.infoworld.com/article/3539309/developers-cite-barriers-to-rust-language-adoption.html),这不仅包括对更好的文档的需求(该团队近年来一直致力于此[,还包括该语言呈现的陡峭的学习曲线。他们注意到，只有 37%的用户在不到一个月的时间里感到富有成效，而大多数受访者用了近一年的时间才感到使用这种语言富有成效。与此同时，dev class](https://blog.rust-lang.org/inside-rust/2020/03/27/goodbye-docs-team.html)[评论道](https://devclass.com/2020/04/21/language-survey-you-know-what-were-a-bit-rust-y-on-getting-companies-on-board/)Rust 继续受到开发人员的喜爱[但是，正如我们注意到的，其受欢迎程度落后，部分原因是公司没有像 Go 那样采用这种语言，并且“学习资源、更好的 IDE 集成和 GUI 将有助于说服人们更多地使用 Rust。”Rust 团队写道:“当我们问为什么有人停止使用 Rust 时，最常见的回答是‘我的公司不使用 Rust’。”](https://stackoverflow.blog/2020/01/20/what-is-rust-and-why-is-it-so-popular/)

至于 Go 调查，JAXEnter [关注](https://jaxenter.com/golang-dev-survey-171243.html)调查的一个特殊结果，这个结果一直是开发者的症结所在——缺乏泛型——79%的人说这个特性是必要的。为了保持对事物负面的关注，SDTimes 调查了[为什么这种语言没有被更多地使用](https://sdtimes.com/softwaredev/go-developer-survey-reveals-why-the-language-isnt-used-more-often/)，写道“开发人员不能更多地使用 Go 的原因是因为他们正在用另一种语言进行项目(56%)，在一个喜欢另一种语言的团队中工作(37%)，以及缺少 Go 中的一个关键特性(25%)，“指出”泛型、更好的错误处理、函数式编程特性、更强的类型系统、枚举/求和类型/空安全、增加的表达能力以及改进的性能和运行时控制“是缺少的特性与此同时，New Stack 的 Lawrence Hecht 从调查结果中收集了另一个见解——微软 Azure 有一个 Go 问题，事实证明，“去年只有 49%的人至少对在 Azure 上使用 Go 感到满意”，而“73%和 71%的人分别对他们在亚马逊网络服务(AWS)和谷歌云平台(GCP)上的 Go 体验有同样的感觉。”

无论你在争论是使用 Rust 还是 Go，现在至少你有了各种不使用它们的理由。

## 本周的节目中

*   **TorchServe，PyTorch 的开源服务器模型:**脸书和 AWS 已经[开源了一个名为](https://aws.amazon.com/blogs/aws/announcing-torchserve-an-open-source-model-server-for-pytorch/) [TorchServe](https://github.com/pytorch/serve) 的新模型服务器，这使得部署和管理用流行的 [PyTorch](http://aws.amazon.com/pytorch) 开源库构建的深度学习模型变得更加容易。TorchServe 模型服务器自动创建由可伸缩 web 服务器支持的预测 API，对预测请求运行预处理和后处理代码，并提供日志记录、监控和安全性等功能。简而言之，AWS 写道，它“使大规模部署训练有素的 PyTorch 模型变得容易，而不必编写定制代码”，并支持“任何机器学习环境，包括[亚马逊 SageMaker](https://aws.amazon.com/sagemaker/) ，容器服务和[亚马逊弹性计算云(EC2)](https://aws.amazon.com/ec2/) 。”与此相关的是， [PyTorch 1.5 刚刚发布了](https://pytorch.org/blog/pytorch-1-dot-5-released-with-new-and-updated-apis/)新的和更新的 API，包括它所谓的“对 C++前端的重大更新”——在[发布说明](https://github.com/pytorch/pytorch/releases)中可以找到完整的细节。

https://twitter.com/catalinmpit/status/1252922899805155328

*   gRPC 忙于 Kotlin，JavaScript:gRPC 团队在过去的一周里一直很忙，发布了 [Kotlin 支持](https://grpc.io/blog/kotlin-meet-grpc/)和 [gRPC-JS 1.0](https://www.npmjs.com/package/@grpc/grpc-js) for JavaScript，这是“原始[节点 gRPC 库 grpc](https://www.npmjs.com/package/grpc) 的纯类型脚本重新实现”gRPC 是谷歌建立的开源项目，提供了执行远程过程调用(RPC)的能力，既用于移动和网络上的最后一英里计算，也作为连接微服务的一种方式。以流行的基于 JVM 的编程语言 [Kotlin](https://kotlinlang.org/) 为例，开发者现在可以使用新开源的 [gRPC Kotlin](https://github.com/grpc/grpc-kotlin) 构建从移动应用到云微服务的一切，并在[云运行](https://cloud.run/)上部署 gRPC Kotlin 服务。至于 [gRPC-JS (@grpc/grpc-js)](https://www.npmjs.com/package/@grpc/grpc-js) ，它提供了他们所说的“应该覆盖大部分用例”的特性，并打算替换原来的节点 gRPC 库( [grpc](https://www.npmjs.com/package/grpc) )，该库设置为年内弃用。
*   **亚马逊 AppFlow 简化了 SaaS 集成:**亚马逊[宣布推出亚马逊 AppFlow](https://aws.amazon.com/blogs/aws/new-announcing-amazon-appflow/) ，这是一项自动化 AWS 服务与 Salesforce 和 Zendesk 等外部 SaaS 应用程序之间数据流的新服务。基本上，亚马逊不会要求开发人员在这些服务之间构建定制的集成来安全地传输数据，而是会根据预定时间、手动触发或事件等标准自动为您完成这项工作。TechCrunch [评论](https://techcrunch.com/2020/04/22/aws-launches-amazon-appflow-its-new-saas-integration-service/)称“然而，与一些竞争对手不同的是，AWS 将这项服务更多地定位为数据传输服务，而不是自动化工作流的一种方式，尽管数据流可以是双向的，但 AWS 的声明主要集中在将数据从 SaaS 应用程序移动到其他 AWS 服务进行进一步分析。为此，AppFlow 还包括许多工具，用于在数据通过服务时对其进行转换。”

[https://www.youtube.com/embed/USzaWjjjOJI?feature=oembed](https://www.youtube.com/embed/USzaWjjjOJI?feature=oembed)

视频

*   **Python 2 . x 的终结:**CPython 核心开发者发布了 [Python 2.7.18，Python 2 的最后一个版本](https://pythoninsider.blogspot.com/2020/04/python-2718-last-release-of-python-2.html)——不，这是[Python 2 . x 的最后一个版本](https://thenewstack.io/frustration-mounts-over-python-3-migrations/)，一个[在未来很多年的移动](https://thenewstack.io/this-week-in-programming-goodnight-sweet-python-2-x/)。“是时候让 CPython 社区对 Python 2 说一声深情而坚定的再见了，”他们写道。“自 11 年前 Python 2.6 发布以来，Python 2.7 一直处于积极的开发阶段。这些年来，CPython 的核心开发人员和贡献者不辞辛苦地将错误修复应用到 2.7 分支，这不是一个小任务，因为 Python 2 和 3 分支出现了分歧。”
*   **GitHub Actions 增长，获得组织范围内的跑步者:** GitHub 正在[吹捧 GitHub Actions 的“社区势头”](https://github.blog/2020-04-22-github-actions-community-momentum-enterprise-capabilities-and-developer-improvements/)，指出 GitHub Marketplace 现在有超过 3200 个 Actions，它说“在不到 6 个月的时间里增长了 500%。”除了这些数字，它还宣布，组织现在可以在该组织的多个存储库中共享自托管的 runners，同时还有一些一般性的改进，包括目录默认设置、允许下游数据传递的作业输出以及其他定制功能。在另一份声明中，GitHub 还表示[预定提醒现在正式退出测试](https://github.blog/2020-04-21-stay-on-top-of-your-code-reviews-with-scheduled-reminders/)并可以使用。

https://twitter.com/KeziyahL/status/1252625942679298050

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>