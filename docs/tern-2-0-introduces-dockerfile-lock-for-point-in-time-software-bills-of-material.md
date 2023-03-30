# Tern 2.0 为时间点软件物料清单引入了 Dockerfile 锁

> 原文：<https://thenewstack.io/tern-2-0-introduces-dockerfile-lock-for-point-in-time-software-bills-of-material/>

从本质上来说，容器化消除了开发人员多年来使用的“它在我的机器上工作”的借口。通过将应用程序的代码/二进制文件与所需的配置文件、库和依赖项打包在一起，容器解决了代码在不同机器上以不同方式运行的问题。

但是和任何解决方案一样，新的问题出现了。对于运行容器化应用程序的公司来说，一个这样的问题是与容器中包含的众多依赖项相关的安全性和合规性。开源集装箱检查工具项目 [Tern](https://github.com/vmware/tern) 最近[发布了 Tern 2.0](https://automatecompliance.org/news/2020/04/23/tern-2-0-0-now-available/) ，继续努力通过向用户提供“软件材料清单”来解决这个问题

“人们没有意识到的是，当他们安装软件包时，他们也在安装软件包的依赖项。通常，他们带来的包比他们知道的要多，所以 Tern 的目标是提供一个完整的包列表，Docker 文件可以使用 Docker build 安装在容器映像中，”Tern 维护者[妮莎·库马尔](https://www.linkedin.com/in/nisha-kumar-mayernik-57642b7/)在一次采访中解释道容器的问题在于，你实际上是在运送一个完整的操作系统。这是操作系统供应商非常了解的事情，并且在历史上已经做了尽职调查，但是因为容器不仅包含基本操作系统，还包含来自各种生态系统的大量其他包，所以实际上获得应用程序依赖关系的绝对列表变得越来越困难。"

Kumar 解释说，有了这个列表，用户可以更容易地评估安全状况，并确保各种软件包的相关许可证符合任何相关法规和公司对该软件的使用。

虽然这听起来相对简单，但这里还有另一个复杂之处——docker files，它自动创建容器映像，并不明确列出包及其版本。相反，他们可能会说使用特定包的“最新版本”,这取决于容器映像的构建时间，可能会引用该包的不同版本。

为了解决这个问题，Tern 2.0 引入了“Dockerfile lock”功能，其中 Tern“创建一个锁定的 Dockerfile，其中基本映像被固定到一个摘要，为每个后续层安装的软件包被固定到它们的版本，如果它们是已知的话。”本质上，Tern 创建了一个 Dockerfile，它在某个时间点被锁定，在这里它将这些动态变量转换成静态值，包括 ARG 和 ENV 变量。Kumar 说，这不仅可以获得准确的材料清单，还可以从 Docker 文件中创建更多可复制的 Docker 映像，以便在稍后的时间点重建构建。

Kumar 说:“Dockerfile 文件通常是以一种非常命令式的方式编写的，所以很难使用相同的 Dockerfile 文件重建一个月前构建的相同的容器映像。“锁特性允许您做的是能够重现您的容器构建。它的行为方式与 [pip 冻结](https://pip.pypa.io/en/stable/reference/pip_freeze/)或 gem 日志相同，其中您可以获得用于构建您的第一个容器映像的精确映像摘要，并且您还可以获得绑定到其版本的包。”

Tern 构建软件材料清单的主要方式是通过与包管理器交互来确定包含哪些依赖项，但第二种方式是使用扩展，它允许外部文件扫描器扫描容器映像。Kumar 解释说，随着这个版本的发布，Tern 现在可以将 [Scancode-toolkit](https://github.com/nexB/scancode-toolkit) 文件扫描仪的输出映射到它的数据模型。

Kumar 说:“您可以将 Tern 和 Scancode 结合使用，基本上对容器映像进行精细的分析，然后 Tern 将生成不同格式的报告，”他解释说，它支持的软件材料清单格式就像是容器映像的鸟瞰图，可以在 YAML 的 JSON 和 [SPDX](https://spdx.org/) 中找到，SPDX 是由 Linux 基金会创建的一种开放标准，用于交流软件材料清单信息，包括组件、许可证、版权和安全参考。

虽然 Tern 已经发布了 Tern 2.0，但 Kumar 指出，该项目使用语义版本，并且仍处于 alpha 测试阶段，还没有全面推出。展望未来，Kumar 表示，该项目将专注于在 Mac 和 Windows 环境下运行，以及添加对语言包管理器的支持和添加对多级 Docker 构建的支持。

Linux 基金会和 VMware 是新堆栈的赞助商。

由[丹尼米勒](https://unsplash.com/@redaquamedia?utm_source=unsplash&utm_medium=referral&utm_content=creditCopyText)在 [Unsplash](https://unsplash.com/s/photos/inventory?utm_source=unsplash&utm_medium=referral&utm_content=creditCopyText) 上拍摄的特写图片。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>