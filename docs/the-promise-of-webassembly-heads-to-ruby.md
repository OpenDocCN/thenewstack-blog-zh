# WebAssembly 向 Ruby 承诺

> 原文：<https://thenewstack.io/the-promise-of-webassembly-heads-to-ruby/>

虽然 Ruby 在 2021 年 WebAssembly 状态调查中并没有排在最受欢迎语言的榜首(这一荣誉失去了，Go 和 C++紧随其后)，但这正是本周发生的事情。

更具体地说，Ruby 3.2.0 的[首个预览版](https://www.ruby-lang.org/en/news/2022/04/03/ruby-3-2-0-preview1-released/)提供了基于 [WebAssembly 系统接口(WASI)](https://github.com/WebAssembly/WASI) 的 [WebAssembly](https://webassembly.org/) 支持，这“使得 CRuby 二进制文件可以在 Web 浏览器、无服务器 Edge 环境和其他 WebAssembly/WASI 嵌入程序上使用。”

如果你不熟悉的话，WebAssembly 为浏览器(和其他地方)带来了 HTML、CSS 和 JavaScript 之外的语言，几年前，万维网联盟(W3C) 将[命名为“允许代码在浏览器中运行的第四种 Web 语言”](https://thenewstack.io/this-week-in-programming-the-time-has-come-to-pay-attention-to-webassembly/)

尽管实现还处于早期阶段，还缺少一些功能，但是 Ruby 社区还是给了我们一些惊喜。

Ruby committer [森英士·齐藤](https://www.linkedin.com/in/kateinoigakukun/)上个月发表了一篇博客文章，提供了 Ruby 对 WebAssembly/WASI 支持的[更新，齐藤在文章中解释了一些推理和背景故事。Saito 解释说，Ruby 已经在使用 Emscripten 的 WebAssembly 中得到支持，但是这种实现严重依赖于主机 JavaScript 环境。通过转移到 WASI，Ruby 现在不仅可以在浏览器中使用，还可以“在各种情况下使用，比如边缘计算、嵌入式环境和插件系统的接口。”](https://itnext.io/final-report-webassembly-wasi-support-in-ruby-4aface7d90c9)

Saito 解释说:“WASI 致力于为 WebAssembly 模块定义一套标准的系统调用，使 WebAssembly 模块不仅可以跨架构移植，还可以跨实现这套标准系统调用的环境移植。”。" WASI 完全不依赖 JavaScript . "

要了解完整的技术细节，请阅读 Saito 的博客文章，这篇文章深入探讨了这将如何实现以及目前的局限性。除此之外，如果你想试一试，读一下这个快速的[启动指南](https://www.wasm.builders/rjzak/ruby-webassembly-bcj)然后开始吧。

## 本周的节目中

*   **Lambda 获得内置 HTTPS 端点:**虽然使用[亚马逊 API 网关](http://aws.amazon.com/apigateway)为 AWS Lambda 函数创建 API 端点在技术上可能是可行的，但随着 AWS 的[新 Lambda 函数 URL](https://aws.amazon.com/blogs/aws/announcing-aws-lambda-function-urls-built-in-https-endpoints-for-single-function-microservices/)的推出，这项任务变得简单多了。现在，无需学习或使用任何其他服务，AWS Lambda 用户可以将 HTTPS 端点添加到任何 Lambda 函数中，如果他们愿意，还可以配置[跨来源资源共享(CORS)头](https://developer.mozilla.org/en-US/docs/Web/HTTP/CORS)，这允许您指示“[来源](https://developer.mozilla.org/en-US/docs/Glossary/Origin)(域、方案或端口)，而不是它自己的，浏览器应该允许从其中加载资源”。这一新特性的目的是使端点的启动和运行变得快速简单，但是如果您需要高级功能，比如验证或节流， [Amazon API Gateway](http://aws.amazon.com/apigateway) 可能是更好的选择。不过，不就是这样吗？这个新特性的另一个好处是，你不必再为 Amazon API Gateway 付费了。关于如何设置它们，何时使用它们，以及它们可能花费多少(成本包含在 Lambda 的请求和持续时间定价中)的完整细节，请前往并浏览一下[博客帖子](https://aws.amazon.com/blogs/aws/announcing-aws-lambda-function-urls-built-in-https-endpoints-for-single-function-microservices/)。
*   **梅塔继续它的 F8 暂停:**尽管最近会议似乎无处不在，但似乎梅塔已经决定继续它在 2022 年 F8 的[暂停。F8 是脸书的开发者大会，2020 年取消，实际上在 2021 年举行。该公司在宣布这一举措的一篇博文中写道:“与过去几年类似，我们正在短暂中断编程，不会在 2022 年举办 F8，而我们正在加快新的举措，这些举措都是为了互联网的下一个篇章，也是我们公司的下一个篇章:建设元宇宙。”。然而，如果 AR、VR 和元宇宙是你的东西，脸书表示，它准备在今年晚些时候的“连接”活动中继续前进。](https://developers.facebook.com/blog/post/2022/04/06/pausing-f8-in-2022/)

*   GitLab 收购 OpsTrace 的下一步是什么？在本周一篇关于[可观察性是云原生转变的关键](https://about.gitlab.com/blog/2022/04/05/observability-is-key-to-cloud-native-transitions-and-modern-application-development/)的博客文章中，这一线索似乎被埋没了。虽然一般性的讨论还不错，但 GitLab 也链接到了 OpsTrace 最近在[发表的一篇博客文章，OpsTrace](https://opstrace.com/blog/gitlabobsvervabilityui)是他们[在 2021](https://about.gitlab.com/press/releases/2021-12-14-gitlab-acquires-opstrace-to-expand-its-devops-platform-with-open-source-observability-solution.html) 年收购的一家公司，OpsTrace 在文章中分享了其整合到 GitLab 的最新进展。在这篇最初于上个月下旬撰写的博客文章中，OpsTrace 写道，它希望分享“两个关键的更新”，首先是它将“启动一个新的开源项目，以构建一个新的 observability 用户界面(UI)，GitLab Observability UI”基于 Grafana 的最后一个 Apache 许可的分支(7.5.x)的一个分支。在本次更新的常见问题中，OpsTrace 表示，这样做是因为“使用现有基础使我们能够快速行动，并立即专注于改进的 UX，同时与现有的各种普罗米修斯仪表板兼容。”由此产生的项目将在 Apache 2.0 下获得许可，以允许“将 UI 嵌入 GitLab 和其他公司的现有产品中”。与此同时，OpsTrace 还统一了“ClickHouse 上度量、日志和跟踪的后端”,并出于许可原因删除了 Loki，以便他们可以在 ClickHouse 上创建自己的 Apache 许可的日志后端。所有这些，抛开公司的警告不谈，很可能在不远的将来就来到你身边的 GitLab。

*   **GitHub 的新措施防止漏洞 Intro:** 虽然 GitHub 的 Dependabot 服务已经让您知道您的某个依赖项是否存在漏洞，但仍然有可能通过添加新的依赖项来引入漏洞。这就是为什么 GitHub 在[中增加了一个新的动作，防止已知的漏洞进入你的代码](https://github.blog/2022-04-06-prevent-introduction-known-vulnerabilities-into-your-code/)。本周推出的新的[依赖性审查行动](https://github.com/actions/dependency-review-action)通过扫描依赖性变化的拉请求，然后与 [GitHub 咨询数据库](https://github.com/advisories)比较这些依赖性中的现有漏洞，来“自动发现和阻止当前仅显示在拉请求的 [rich diff 中的漏洞”。新的动作出现在 GitHub Marketplace 上，尽管，购买者请注意，这都是公开测试，所以](https://github.blog/changelog/2021-01-25-dependency-review-beta/)[新的 API 端点](https://docs.github.com/en/rest/reference/dependency-graph)仍然是一个移动的目标。
*   **Rust 发布 2024 年路线图:**正如今年早些时候为 [Rust 编译器 2022 年](https://blog.rust-lang.org/inside-rust/2022/02/22/compiler-team-ambitions-2022.html)的雄心所做的一样，Rust 团队本周发布了其[Rust Lang 2024 年路线图](https://blog.rust-lang.org/inside-rust/2022/04/04/lang-roadmap-2024.html)，这是[生存路线图](https://lang-team.rust-lang.org/roadmaps/roadmap-2024.html)的快照，也是该团队为 Rust 2024 所做工作的总结。他们写道，路线图的共同主题是根据三个基本主题“让每个人都能构建可靠而高效的软件”。首先，他们计划[通过让 Rust 更容易学习和使用来拉平(学习)曲线](https://blog.rust-lang.org/inside-rust/2022/04/04/lang-roadmap-2024.html#Theme-Flatten-the-learning-curve)。接下来，[帮助 Rust 的用户互相帮助](https://blog.rust-lang.org/inside-rust/2022/04/04/lang-roadmap-2024.html#Theme-Help-users-help-each-other)让库作者和他们的用户的生活更轻松。最后，[帮助 Rust 项目本身扩展](https://blog.rust-lang.org/inside-rust/2022/04/04/lang-roadmap-2024.html#Theme-Help-the-Rust-project-scale)，通过开发过程来适应越来越多用户的需求和用例。然而，这份总结仅仅是个开始。这篇博文详细介绍了这三个领域背后的愿景、实现这些愿景的计划，以及你们 Rust 社区如何[参与其中](https://rust-lang.zulipchat.com/#narrow/stream/318377-t-lang.2Froadmap-2024)实现这些愿景，因此，如果你对其中任何一项感兴趣，请前往阅读。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>