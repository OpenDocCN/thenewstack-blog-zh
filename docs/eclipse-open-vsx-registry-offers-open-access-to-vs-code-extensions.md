# Eclipse 开放 VSX 注册中心提供了对 VS 代码扩展的开放访问

> 原文：<https://thenewstack.io/eclipse-open-vsx-registry-offers-open-access-to-vs-code-extensions/>

[开放 VSX 注册中心](https://open-vsx.org/)已经转移到 [Eclipse 基金会](https://www.eclipse.org/org/foundation/)，该基金会表示，它将为微软的 [Visual Studio Marketplace](https://marketplace.visualstudio.com/) 提供一个厂商中立的、公开托管的开源替代扩展出口。

最初由 TypeFox 使用 Eclipse 开放 VSX 项目创建，开放 VSX 注册中心遵循了与 Eclipse 忒伊亚相似的道路，同样由 TypeFox 和 Eclipse 基金会称之为“Visual Studio 代码的真正开源替代方案”的

遵循同样的思路，Eclipse Foundation 执行董事 Mike Milinkovich 指出，虽然 VS 代码及其扩展是开源的，但它们的使用条款最终却不够开放。

“虽然从某种意义上说，VS 代码是开源的，你可以获得几乎所有的源代码，但当你从微软下载 VS 代码时，它就是微软的产品。你正在接受一个非开源的最终用户许可协议，微软正在收集你使用 VS 代码的遥测数据。“围绕 VS 代码建立的扩展生态系统无疑是它的优势之一，微软为 VS 代码扩展运营一个注册表，但使用条款规定它只能用于访问微软产品的扩展。”

VS 代码扩展对用户的重要性很难被夸大。一份[分析](https://thenewstack.io/this-week-in-programming-all-hail-visual-studio-code/)去年提到 VS Code 的扩展是领先于竞争对手的代码编辑器的四个特性之一，而[最近在 Visual Studio Code 博客](https://code.visualstudio.com/blogs/2021/02/16/extension-bisect)上的一篇博客文章指出，在微软的 VS Code Marketplace 中有超过 28，000 个扩展，并且“用户安装 50 个或更多扩展并不罕见。”虽然可以在市场之外找到并安装这些扩展，但是开放 VSX 注册中心为 VS 代码的用户提供了一个单一的位置来搜索和下载扩展。

除了使用条款有效地限制了 VS 代码替代品的用户，如 [Eclipse Che](https://www.eclipse.org/che/) 、 [VSCodium](https://github.com/VSCodium/vscodium) 、 [GitPod](https://www.gitpod.io/) 和其他人通过市场访问 VS 代码扩展，Milinkovich 还指出市场本身并不是开源的。相比之下，Open VSX 是在 [Eclipse Public License v2.0](https://www.eclipse.org/legal/epl-2.0/) 下的开源软件，包括一个[主存储库](https://github.com/eclipse/openvsx)提供服务器、web UI 和 CLI，以及一个[二级存储库](https://github.com/EclipseFdn/open-vsx.org)为开放 VSX 注册中心网站本身提供所有代码。

Milinkovich 说:“现在，例如，如果你是一个企业，你有很多开发人员在使用 VS 代码扩展，你可能会担心他们是否有权访问整个 VS 代码扩展注册表，也许出于安全原因，你想拥有自己的注册表，以限制扩展的版本，甚至扩展的数量。”。“有很多很好的理由可以解释为什么企业希望在防火墙后维护他们自己的扩展注册中心，所以开放 VSX 作为一个开源项目，允许你这样做。”

Milinkovich 解释说，结合 Eclipse 忒伊亚，公司现在可以创建他们自己的白色标签 ide——ARM 和 Arduino 已经这样做了——并建立他们自己的内部注册表。不管怎样，那些白标的实现现在能够访问超过 900 个 VS 代码扩展，这些扩展现在在开放 VSX 注册中心对非微软产品可用。

希望将扩展添加到开放 VSX 注册中心的 VS 代码扩展作者需要在打包和上传扩展之前创建一个 Eclipse Foundation 帐户、一个访问令牌和一个名称空间。对于那些希望将开放 VSX 注册中心与他们的工具集成在一起的人，提供了一个 REST API，其中包括用于创建名称空间、发布、查询元数据和搜索的 REST 端点。

关于开放 VSX 注册中心的背景及其使用的更多细节可以在 Eclipse Foundation 网站上的白皮书中找到。

Milinkovich 说，他们将开放 VSX 注册中心转移到 Eclipse 基金会的部分原因是他们希望看到它在使用和用例方面都有所增长。

“我们非常希望看到开放 VSX 的下一步是人们试用它，并将其作为开源设施在内部运行，然后做出贡献。你知道，告诉我们他们的体验，提供关于我们如何改进可扩展性、特性功能等的拉式请求。我们希望能够围绕开放 VSX 项目建立一个开发者社区，”Milinkovich 说。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>