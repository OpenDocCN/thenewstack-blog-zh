# 本周编程:Knative 采用选举产生的指导委员会，切断谷歌的控制

> 原文：<https://thenewstack.io/this-week-in-programming-knative-adopts-elected-steering-committee-severing-google-control/>

Google first [于 2015 年](https://techcrunch.com/2015/07/21/as-kubernetes-hits-1-0-google-donates-technology-to-newly-formed-cloud-native-computing-foundation-with-ibm-intel-twitter-and-others/)向全世界发布了 Kubernetes，并由此开启了我们今天所知的云原生运动。随着 [1.0 版本](https://kuberneteslaunch.com/)的发布，谷歌放弃了对该项目的控制，并将其移交给新成立的[云原生计算基金会(CNCF)](https://www.cncf.io/) ，这一举动[被一些人认为是公司内部遗憾的原因](https://thenewstack.io/op-ed-kubernetes-may-be-googles-last-great-open-project/)，并继续玷污其其他云原生追求的方法。不管这种说法是否正确，它往往会影响云原生社区中许多人对该公司其他云原生项目意图的看法，如 Istio service mesh 和在 Kubernetes 上运行无服务器工作负载的 Knative 平台。

例如，在 Istio 的案例中，谷歌避免了采取与 Kubernetes 相同的路线，而是创建了开放使用共用来处理商标问题，将 [Istio 作为创始项目之一](https://thenewstack.io/googles-management-of-the-istio-service-mesh-raises-questions-in-the-cloud-native-community/)，此后不久[重组了指导委员会](https://thenewstack.io/this-week-in-programming-istio-restructures-steering-committee-to-avoid-single-vendor-majority/)以避免单一供应商控制。本质上，Istio 项目致力于表明它摆脱了谷歌的单一控制，没有将自己拱手让给 CNCF，尽管[早些时候承诺](https://developer.ibm.com/components/istio/blogs/istio-google-open-usage-commons/)这样做。

今年早些时候，我们看到了 Knative 的类似情况，其中谷歌澄清了其对该项目的立场，指出其“决定在可预见的未来不向任何基金会捐赠 Knative。”这一宣布遭到了一些人的反对，他们担心谷歌对该项目的多数控制权会抑制其采用和发展势头，但指导委员会当时表示，它将寻找不同的方式来开放对该项目的控制，并提供开放的治理，而不依赖于将控制权移交给一个单独的基金会，如 CNCF。

本周，来自 Protocol 的报道表明，Knative 正走在与 Istio 相似的道路上，谷歌[放弃了对项目](https://www.protocol.com/google-gives-up-direct-control-knative-open-source-project)的直接控制。Protocol 的 [Tom Krazit](https://twitter.com/tomkrazit) 写道，谷歌计划“宣布对项目的治理结构进行彻底的改变”，这将以“一个指导委员会结构的形式出现，在这个结构中，任何一家供应商都不能在一个五人委员会中拥有两个以上的席位。”此外，这一变化将指导委员会的席位从与公司明确相关改为与个人相关，未来可能会扩大成员数量，届时也将包括最终用户。

Knative project 实际上[几周前在 Twitter 上宣布了](https://twitter.com/KnativeProject/status/1309249954368688128)这些变化，指导委员会成员 Brenda Chen 指出，这种变化的势头始于 2019 年底第一次面对面的指导委员会会议。

随着这篇文章强调了这一变化，围绕 Knative 未来的讨论有了一些新的活力，尽管一些人仍然质疑将该项目移交给 CNCF 有什么犹豫，该项目被视为这种云原生开源项目的事实上的家园

虽然谷歌将暂时保留对 Knative 的商标控制权，但指导委员会的一名成员指出，即使在这方面，该公司也已经放弃了主导地位，向其他相关方提供了否决权。虽然这一举措可能不会安抚那些将 CNCF 视为成功的云原生开源项目的唯一途径的人，但它肯定是朝着正确方向迈出的一步，[指导委员会的另一名成员 Evan Anderson 认为](https://twitter.com/e_k_anderson/status/1314414948865302529)。

## 本周的节目中

*   **展望 Kotlin 的未来:**Kotlin 编程语言的粉丝们对未来一年有很多期待，因为该团队已经[公布了](https://blog.jetbrains.com/kotlin/2020/10/kotlin-public-roadmap-through-spring-2021/)一份[公开路线图](http://kotl.in/roadmap)，详细说明了 kot Lin 团队在未来六个月中最大的项目。路线图每三个月更新一次，当然，这是一项正在进行的工作和协作，这意味着你可以在[链接的 YouTrack ticket](https://youtrack.jetbrains.com/issues/KT?q=%23%7BRoadmap%20Item%7D%20) 或 [#kotlin-roadmap](https://kotlinlang.slack.com/archives/C01AAJSG3V4) Slack 频道([邀请此处](https://surveys.jetbrains.com/s3/kotlin-slack-sign-up))中提问。一些值得期待的关键特性包括加快变更-测试-调试周期，重写 Kotlin 编译器，重点优化速度、并行性和统一性(随后提供可插拔性)，提高 Kotlin IDE 的稳定性和性能，扩展对服务器端 JVM 的支持，甚至是 Kotlin-to-WebAssembly 编译器后端。
*   **Python 3.9.0 来了:**Python 开发社区已经[宣布了](https://feedproxy.google.com/~r/PythonInsider/~3/x_KphpL1EaI/python-390-is-now-available-and-you-can.html) [Python 3.9.0](https://www.python.org/downloads/release/python-390/) 的可用性，引入了一些新的字符串解析方法，更新和合并字典的新操作符，内置泛型类型的类型提示，以及一个新的解析器。但是不要相信我们的话，去看看 Python 3.9 的新特性吧。此外，不要对接近 Python 4 过于兴奋，因为下一个版本实际上是 Python 3.10，它实际上已经准备好了 alpha 版本。另一方面，对于那些落后的人来说， [Python 3.5 不再受支持](https://pythoninsider.blogspot.com/2020/10/python-35-is-no-longer-supported.html)，3.5 系列将不再有错误修复或安全补丁，而 [Python 3.5.10](https://www.python.org/downloads/release/python-3510/) 是最后一个版本。

*   **GitHub 借助第三方工具增强代码扫描:**一周多以前，GitHub [发布了原生代码扫描](https://github.blog/2020-09-30-code-scanning-is-now-available/)，现在该公司又发布了两个关于第三方代码扫描工具的公告。这些第三方工具扩展了 GitHub 的本机代码扫描，它由自己的 [CodeQL](https://securitylab.github.com/tools/codeql) 静态扫描引擎提供支持。这些工具通过 GitHub 动作或 GitHub 应用程序启动，基于 GitHub 中的事件，如 pull 请求，GitHub 的代码扫描 API 端点使用开放标准静态分析结果交换格式(SARIF)接收结果。首先公布的 10 个[静态分析和开发者安全培训](https://github.blog/2020-10-05-announcing-third-party-code-scanning-tools-static-analysis-and-developer-security-training/)包括 Checkmarx、Codacy、CodeScan、DefenseCode ThunderScan、Fortify on Demand、Muse、Secure Code Warrior、Synopsys 智能安全扫描、Veracode 静态分析和 Xanitizer，而作为代码和容器扫描的 7 个[基础设施](https://github.blog/2020-10-07-announcing-third-party-code-scanning-tools-infrastructure-as-code-and-container-scanning/)包括 42Crunch、Accurics、Bridgecrew、Snyk、Trivy by Aqua Security、Anchor 和 Snyk Container。要查看它们，请访问 GitHub 市场。
*   **GitHub 开源其文档:**因为一切都是更好的开源，GitHub 本周宣布其 [GitHub 文档现已开源](https://github.blog/2020-10-07-github-docs-are-now-open-source/)。于 7 月首次推出的 [GitHub Docs](https://docs.github.com/en) 是您获取 GitHub 文档的一站式商店，现在您可以开始评论它们，并为您的内容做出贡献。他们写道:“每个使用 GitHub 的人对什么有效都有不同的看法。”“我们希望 GitHub Docs 的文章能为所有来自不同背景的开发者所用。这就是我们以多种不同方式接受捐赠的原因。”对于感兴趣的人，你可以[直接在网站上发表](https://github.com/github/docs/blob/main/CONTRIBUTING.md)文章，或者你可以加入[讨论](https://github.com/github/docs/discussions)，发表一个问题，或者发表一个关于你想做的事情的请求。

*   **使用 GitPod 进行云原生编码:**今年早些时候，当云原生 IDE [开源](https://thenewstack.io/gitpod-open-sources-a-holistic-ide/)时，我们首次向读者介绍了 GitPod，现在该公司正在吹嘘一个[原生 GitLab 集成](https://www.gitpod.io/blog/gitlab-integration/)，它完成了 GitHub、GitLab 和 Bitbucket 的标准三连胜。GitPod 可以简单地通过在存储库 URL 前面加上 gitpod.io/#来自动启动开发环境，现在，通过 GitLab 的 UI 中的[原生 Gitpod 集成](https://gitlab.com/gitlab-org/gitlab/-/merge_requests/37985)，使用 GitLab 的 100，000 多个组织都可以使用该功能。GitPod 的开发环境超越了代码 IDE/编辑器，包括了编译器、构建工具、代码生成器、数据库和应用服务器。如果你在想“这听起来很像 GitHub Codespaces”，那么，你没有错——下面是两者的比较。

### 其他资源

*目前无法从新的堆栈站点访问这些站点。请将 URL 粘贴到您的浏览器窗口:*

静态分析结果交换格式:https://docs . oasis-open . org/sarif/sarif/v 2.0/sarif-v 2.0 . html

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>