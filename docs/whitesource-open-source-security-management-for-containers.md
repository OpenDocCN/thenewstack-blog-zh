# WhiteSource:容器的开源安全管理

> 原文：<https://thenewstack.io/whitesource-open-source-security-management-for-containers/>

很有可能，你正在使用一个开源库。最近的一项调查报告称，92%的应用程序至少使用一个开源库。另一项[调查](https://www.blackducksoftware.com/open-source-security-risk-analysis-2017)显示这个数字甚至更高，达到 96%。重点是，开源无处不在。当然，这样做有很好的理由——使用开源库可以节省你重新发明轮子的时间和金钱。不幸的是，它也可能使您的应用程序暴露于安全漏洞，这些安全漏洞要么继承自您选择的库，要么继承自那些库引入的[传递依赖](https://en.wikipedia.org/wiki/Transitive_dependency)。

[WhiteSource](https://www.whitesourcesoftware.com/) 是一款持续开源的安全和许可证合规性管理工具，它于七年前创建，旨在解决这一问题。本周，它将持续监控功能引入容器化的应用程序和组成这些应用程序的映像。

“WhiteSource 提供了所有开源组件及其所有依赖项的图片，并提供了警报和仪表板，为用户提供了许可、合规性和安全性图片，以利用他们的 CI/CD 渠道，并在涉及开源使用风险时设置一些关卡，”WhiteSource 的产品副总裁 David Habusha 总结道。“从构建容器的最开始到生产，集成到 CI/CD 管道的各个部分非常重要。你必须采取全面的方法。”

[https://www.youtube.com/embed/NPNiZhqpirI?feature=oembed](https://www.youtube.com/embed/NPNiZhqpirI?feature=oembed)

视频

根据一份声明，该公司表示，在其最新发布的版本中，它现在通过 Kubernetes 的支持，在软件开发生命周期(SDLC)中提供“用于检测和修复容器映像和容器内开源漏洞的端到端解决方案”。它通过“Kubernetes 代理在后台作为生产集群中的 pod 静默运行，自动扫描新 pod 中部署到生产的任何映像”，同时监控 Docker Hub、Amazon ECR、Azure Container Registry 和 JFrog Artifactory 中存储的容器映像。

“我们最近增加了支持静态扫描 Docker 图像的功能。当存储一个容器图像时，我们有一个触发器来自动扫描这些图像，如果它们违反了策略，就取消它们的顺序。这是一个无缝集成——它们直接连接到平台上，”哈布沙说。“这完全取决于客户将安全性和合规性关口放在哪里，以及架构和 CI/CD 渠道的成熟度。”

Habusha 解释说:使用微服务的公司将在容器中提供这些服务，并希望确保从构建阶段到容器编排平台的这些映像的安全性和合规性。“这就是容器白源的全部内容。”

WhiteSource 表示，它将继续监控部署后的应用程序，而不仅仅是那些正在开发的应用程序，因为漏洞可能会在几年后出现。此外，WhiteSource 还将容器编排环境本身纳入其监控范围。

该公司表示，作为 WhiteSource for Containers 的一部分，该工具扫描整个平台，包括编排引擎，以发现开源漏洞。在最近的 runc 漏洞的情况下，该漏洞在发布时已经被检测到，并在多个客户帐户上发出警报，包括建议的补救措施。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>