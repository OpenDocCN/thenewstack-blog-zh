# 港口采纳 OCI 协议，申办 CNCF 毕业

> 原文：<https://thenewstack.io/harbor-adopts-oci-compliance-makes-bid-to-graduate-cncf/>

本月[发布的 Harbor 2.0](https://goharbor.io/blog/harbor-2.0/) 增加了对所有[开放容器倡议](https://www.opencontainers.org/) (OCI)工件的支持，使其成为第一个符合 OCI 标准的开源注册表，“能够存储大量的云原生工件，包括容器图像、舵图、OPAs、奇点等”，[项目博客帖子](https://goharbor.io/blog/harbor-2.0/)称。OCI 提供了一个关于云原生工件的格式、运行时和分发的标准，随着 OCI 对 Harbor 的支持，注册表确保了与任何符合标准的工件的兼容性，但 VMware 和 Harbor maintainer 的产品管理总监 [Michael Michael](https://www.linkedin.com/in/mimichael/) 表示，存储工件只是一个开始。

“社区正在扩大。云原生工件的种类越来越多。随着越来越多的工件由开发人员制作，你可以在 Harbor 托管它们，但这并不完全是将工件推入或拉入 Harbor，”Michael 说。“这基本上是注册管理机构需要做的最起码的工作。Harbor 真正的优势来自于策略引擎，它能够扫描映像中的漏洞，能够设置配额，能够定义 webhooks，这样您就可以将 Harbor 与您的 CI/CD 或其他自动化需求相集成，甚至可以获得报告和警报。”

在其博客文章中，Harbor 团队称现有用户“不必担心；Harbor 所有熟悉的操作和主要优势都很好地移植到了 OCI。”用户可以执行他们以前能够执行的所有操作—推送、拉入、删除、重新标记、复制、扫描和签署索引，以及漏洞扫描和执行策略实施—等等，例如新添加的删除图像标记而不删除底层清单和所有其他相关图像标记的功能。该项目还指出，由于符合 OCI 标准，它现在也“完全有能力处理 OCI[索引](https://github.com/opencontainers/image-spec/blob/master/image-index.md)，这是一种更高级别的清单，代表图像清单的捆绑，是多架构场景的理想选择。”

Harbor 于 2014 年在 VMware 首次创建，[于 2018 年 7 月将](https://thenewstack.io/cncf-cloud-native-stack-gets-a-private-container-registry-from-vmware/)捐赠给了[云计算原生计算基金会(CNCF)](https://www.cncf.io/) ，在那里，它在 2018 年 11 月从沙盒级别快速进入孵化级别。现在，该项目正处于今年晚些时候成为该基金会毕业的第 11 个项目的最后阶段，投票将于本月晚些时候举行。虽然该项目面临着围绕一些安全问题和不同贡献者组成的一些审查，但 Michael 说，它已经通过大量的安全测试和增加新的维护者和贡献者解决了这些问题。在一个例子中，Michael 指出了许多已经成为维护者的贡献者，例如[的 Daniel Pacak](https://www.linkedin.com/in/pacakdaniel/?originalSubdomain=pl) ，Aqua Security 的 OSS 工程师，以及腾讯和 OVHcloud 的员工。

“我们与他们的目标一致，这就是为什么我们有来自这三家公司的维护人员来推动 Harbor 的愿景和方向。他们希望将注册中心作为服务功能提供给最终用户。与港口外存在的没有任何匹配。他们真的很喜欢 Harbor，他们的用户也喜欢 Harbor。所以他们来和我们合作，”迈克尔说。“他们在港湾有股份，他们有席位。这一切之所以成为可能，是因为他们愿意来我们的社区做贡献。所以我们从不拒绝任何人。如果有人想进来帮助我们并做出贡献，我们非常欢迎。”

至于 Aqua Security，Harbor 2.0 的另一个功能是用 Aqua Security 的 Trivy 代替 Clair 作为默认的图像扫描仪，尽管 Michael 说这不是因为 Pacak 的参与，而是因为这是“正确的选择”。迈克尔说，在 Harbor 1.1 中，引入了可插拔扫描框架，从那时起，众多安全公司，包括 Aqua Security、Sysdig 和其他公司，但 Aqua Security 的 Trivy 脱颖而出。

“Trivy 与我们在 Harbor 的目标最为一致。它速度快，灵活，有很多功能，维护得很好，经常更新，更重要的是，它从操作系统和应用程序打包的角度进行全面扫描，以符合我们的愿景，”Michael 说。

Harbor 2.0 还附带了对核心 Harbor 功能的 SSL 支持，以及可以单独触发并附带 Slack 集成的 webhooks，更不用说黑暗模式了。为了更多地了解 Harbor，该项目将于 5 月 28 日上午 10 点(太平洋标准时间)举办一场关于 Harbor v2.0 的 CNCF 项目网络研讨会。

云计算原生计算基金会和 VMware 是新体系的赞助商。

照片由来自 Pixabay 的 Gordon Johnson 拍摄。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>