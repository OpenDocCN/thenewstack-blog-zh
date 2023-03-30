# 本周编程:Python 的目标是速度提升 5 倍

> 原文：<https://thenewstack.io/this-week-in-programming-python-aims-for-a-5x-speed-boost/>

如果你关注编程语言流行的赛马，你就会知道 Python 是最受欢迎的语言之一，尤其是在机器学习和数据科学领域。这种语言的流行有很多原因，其中包括它的可读性、易用性和广泛的生态系统。然而，与其他一些语言相比，Python 落后的一点是它的速度，本周引起一些波澜的消息是，前仁慈的终身独裁者(BDFL) [吉多·范·罗苏姆](https://en.wikipedia.org/wiki/Guido_van_Rossum)正在努力让 Python 在速度方面有所提高。

本周早些时候，在 [Python 语言峰会](https://us.pycon.org/2021/summits/language/)上，van Rossum [泄露了他的秘密计划](https://mail.python.org/archives/list/python-dev@python.org/message/WVURDCWRH7F5UDLU5ZLT5P35ZO6TIBYA/)和他为他们争取的秘密资金来源:微软。

van Rossum 本周在 Python 邮件列表中写道:“我们在峰会之前一直处于秘密模式，但现在猫肯定已经出来了——微软通过资助加速 CPython 的工作来感谢 Python 社区，”并指出他和其他两人将在未来四年内领导使 CPython 速度提高五倍的努力。

另外两个加入范·罗森的人包括核心 Python 开发者和微软高级软件工程师[埃里克·斯诺、](https://www.linkedin.com/in/ericsnowcurrently/)和[马克·香农](https://www.linkedin.com/in/mark-shannon-bb459551/?originalSubdomain=uk)，他是范·罗森所谓的“[香农计划](https://github.com/markshannon/faster-cpython)的幕后人 Shannon 去年 10 月在 python-dev 邮件列表上发布了他的计划以寻求资金，van Rossum 将此归功于疫情的一点停工期，以及微软允许他选择一个项目进行工作，这个想法开始了，在本周早些时候他的演讲的幻灯片中，他将这一策略称为“微软回馈 python 的方式”。

如果你想知道为什么 Python 不如它的一些同行快，iprogramer 上的一篇[博客文章提供了一个简单的解释:部分易用性和可读性是以速度为代价的，因为编译器——在这种情况下是 CPython——负责解析剩余的复杂性。](https://www.i-programmer.info/news/216-python/14573-guido-and-microsoft-want-to-make-python-x2-faster.html)

现在，香农的计划得到了微软的资助，[目前的计划](https://twitter.com/ahultner/status/1393557689633067014)是让 Python 3.11 快两倍，最终目标是 5 倍，并且所有这些都是在开放环境中与核心 Python 开发者合作完成的。Van Rossum 在他的演示中解释说，即使是 2 倍的加速也是“远不确定的”，除此之外，他们将“必须在未来的机器代码生成方面有所创新”

## 本周的节目中

*   **谷歌推出以谷歌为中心的开发库:**上周，谷歌举行了其[谷歌 I/O 开发者大会](https://events.google.com/io/)，在会上推出了[一系列新功能和产品](https://adtmag.com/blogs/watersworks/2021/05/google-io-announcements.aspx)，大部分是针对 Android 开发者的。一个让我们印象深刻的公告是谷歌新的[开源内容库](https://developers.googleblog.com/2021/05/a-new-open-source-content-library-from-google.html)，即[开发者库](https://devlibrary.withgoogle.com/)，它突出了(据谷歌称)与其产品相关的最好的开源技术。目前，这些项目分为六个类别——机器学习、Flutter、Firebase、Angular、云和 Android——谷歌表示还会有更多项目。虽然有很多其他地方可以找到开源项目，但谷歌表示，这一努力的突出之处在于，“网站上的每一篇文章都由谷歌专家团队详细审查，以确保准确性和相关性，所以你知道当你查看网站上的内容时，它都有谷歌的批准。”如果你有兴趣加入收藏，你可以[提交你的项目进行评审](https://docs.google.com/forms/d/e/1FAIpQLScvcMrUQlp6YizvT0N18_0KLjDOz26apRpSabLKh64to4qxyA/viewform?usp=send_form)。
*   **AWS 推出 App Runner 以简化容器映像部署:**虽然容器提供了“速度、生产力和一致性”，但[亚马逊网络服务](https://aws.amazon.com/?utm_content=inline-mention)技术传道者马丁·毕比写道，“容器开发工作流程有一个方面我不喜欢:我第一次部署容器映像时经历的冗长例行程序。”从设置负载平衡器和 TLS 到创建 CI/CD 管道和配置域，这个过程仍然是一个漫长的过程，AWS 对此的回答是其[新发布的 AWS App Runner](https://aws.amazon.com/blogs/aws/app-runner-from-code-to-scalable-secure-web-apps/) ，据说它将在几分钟内带你从代码到可扩展的安全 web 应用。 [AWS App Runner](https://aws.amazon.com/apprunner) 提供自动伸缩，无冷启动，并提供内置的操作和安全最佳实践，将您的应用程序部署到您的源代码或容器注册表。AWS 与 MongoDB、Datadog 和 HashiCorp 合作提供该服务，并与 [Pulumi](https://www.pulumi.com/blog/deploy-applications-with-aws-app-runner/) 、 [Logz.io](http://logz.io/blog/aws-app-runner) 和 Sysdig 进行了集成。AWS App Runner 现已推出，成本[基于计算和内存使用情况](https://aws.amazon.com/apprunner/pricing)。有关更多信息，请参见 App Runner [定价页面](https://aws.amazon.com/apprunner/pricing)。

*   **GitHub 开源产品出口商，发布播客:**在本周的 GitHub 新闻中，该公司[发布了一款开源工具](https://github.blog/2021-05-18-github-artifact-exporter-open-source-release/)来帮助大型组织进行报告。 [GitHub 工件导出器](https://github.com/github/github-artifact-exporter)将帮助团队导出用于审计的粒度数据，提供一种比通过其 API 更简单的方式来访问数据，相反，允许开发人员简单地下载 CSV 和 JSON 格式的数据，而不是学习 GitHub API。工件浏览器提供了命令行界面和 GUI 来探索 GitHub 问题和评论，允许用户进行搜索和过滤。CLI 还支持导出提交、里程碑、项目、拉请求和发布，以及相关的问题和注释。当我们在这里谈论 GitHub 时，似乎值得一提的是其新推出的播客[和](https://github.blog/2021-05-17-introducing-readme-podcast/)[自述播客](https://github.com/readme/podcast)，该播客以三集开始，分别由 OctoPrint 的吉娜·海格、Vue 的尤雨溪以及 Das 博客的斯科特·汉森曼和马克·唐尼主演。似乎值得一听。
*   Windows 上的 Envoy 代理 GA: 显然，所有云原生开发人员都熟悉 Envoy 代理，但迄今为止，它只在 Linux 上可用。本周，该项目宣布其在 Windows 上的[全面可用，该项目称其自 2016](https://blog.envoyproxy.io/general-availability-of-envoy-on-windows-267e4544994a) 起就有了[的目标。继上周有消息称](https://github.com/envoyproxy/envoy/issues/129) [eBPF 也将进军 Windows](https://thenewstack.io/this-week-in-programming-ebpf-coming-to-a-windows-near-you/) 之后，对于开发者来说，在 Windows 上发布 Envoy 似乎是一个新兴且充满希望的趋势的一部分。Envoy-Windows-Development group 使 Envoy 的移植成为可能，该团队主要由 VMware 和微软的开发人员组成，他们去年发布了该项目的 alpha 版本。自该版本发布以来，该团队还添加了额外的功能，实现了持续集成，并提高了 Envoy 在 Windows 上的性能和可靠性，所有这些都在博客帖子中进行了详细介绍。尽管如此，他们说他们“仍然有很多工作要做，才能让特使在 Windows 上与 Linux 平起平坐”，目前正在努力提高性能和二进制分发，以及与服务网格集成，“就像即将发布的[Windows Server 2022](https://openservicemesh.io/)上的 [OSM](https://openservicemesh.io/)

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>