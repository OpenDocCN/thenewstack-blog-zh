# 镖蛙:前端语言移动到后端

> 原文：<https://thenewstack.io/dart-frog-a-frontend-language-moves-to-the-backend/>

Dart 最广为人知的是它在 Flutter 中的使用和在移动应用中的部署，但一个名为 Dart Frog 的新框架允许开发人员在后端利用 Dart。这是 Very Good Ventures 的创建，这是一家专门从事颤振应用的咨询公司。VGV 最出名的是汉密尔顿应用——是的，*音乐剧——这是谷歌之外第一个用 Flutter 构建的商业应用之一。*

 *最终，后端的问题会影响移动应用程序，所以开发者管理后端和前端是很重要的，VGV 前首席工程师[菲利克斯·安杰洛夫](https://www.linkedin.com/feed/update/urn:li:activity:7034932841398370304/)说(安杰洛夫最近离开去帮助创立 Shorebird Development)。

“如果你有一个非常慢的后端或一个没有很好记录的后端，开发者很难与后端接口，这确实会破坏用户体验，或者反映在你发布的最终产品中，”安杰洛夫告诉 New Stack。“Dart Frog 是我们探索的方式，我们是否可以使用与构建移动应用程序完全相同的编程语言和技术堆栈——在后端使用 Flutter。”

## 为什么用 Dart 做后端？

Dart 是一种通用语言，经过优化可以在任何平台上创建快速应用程序。安杰洛夫说，谷歌已经在后端使用了 Dart:它的包管理器 pub.dev 内置于 Dart 中，允许开发者上传可以被拉入项目的包。他说，在后端广泛使用的问题是工具“不在那里”。

“这并不是说语言没有能力。只是在所有底层组件之上没有足够的工具和抽象来使它对人们更有吸引力，”安杰洛夫说。

他补充说，Dart 可以在服务器上运行，生成本地可执行文件，或者编译成 JavaScript 和机器代码。

“Dart 真的很酷，因为它真的是一种灵活的语言，可以用于许多许多目标，我认为这是它的特别之处，”安杰洛夫说。

此外，随着 Flutter 越来越受欢迎，将有更多的开发者希望在后端使用 Dart，他说。

## 镖蛙:前端移动到后端

[镖蛙](https://dartfrog.vgv.dev/)还在襁褓中。尽管开源框架现在很稳定，但据安杰洛夫称，VGV 的团队正致力于在今年某个时候发布 1.0 版本，但目标是第三季度。VGV 有一个功能的[路线图，它希望作为 1.0 版本的一部分添加进来。安杰洛夫说，目标是让开发者的体验尽可能简单，并保持框架的轻量级。这就是他如何将 Dart Frog 与 ServerPod 等产品区分开来的，server pod 是一种开源、可扩展的应用服务器，可用于在 Dart 中构建 API。安杰洛夫说，ServerPod 整合了 Redis 用于缓存，Postgres 用于数据库，以及对“各种你可能需要或不需要的东西”的迁移支持。](https://dartfrog.vgv.dev/docs/roadmap)

“而我们对 Dart Frog 的理念是:这是一个非常简单的核心，一套每个人无论如何都需要的功能，然后我们为你可能想在以后添加的东西开发单独的模块，”他说。“Dark Frog 主要是，我如何使用 Dart 快速创建端点，然后为开发人员提供一些其他实用程序，使您的代码易于测试，让您可以热重装。”

[热重装是颤振](https://thenewstack.io/12-ways-flutter-streamlines-app-development/)最受欢迎的特性之一。它可以确保实时更新所做的任何更改。这对于在一个应用上合作的团队来说很重要。

安杰洛夫说，Dart Frog 还让开发人员可以轻松地在云端部署一个 API 来与前端应用程序对话。

“基本上，你可以在几分钟内，生成一个新的 Dart Frog 项目，定义前端应用程序可以与之通信的两个端点，然后部署它，”他告诉 New Stack。“我们有一些针对现有热门云提供商的部署指南，如[谷歌云](https://thenewstack.io/google-cloud-stops-monster-ddos-attack/)、 [AWS](https://thenewstack.io/aws-why-we-support-sustainable-open-source/) 或[数字海洋](https://thenewstack.io/digitalocean-app-platform-eases-kubernetes-deployments-for-developers/)。”

VGV 使用 Dart Frog 的一种方式是集成由客户公司开发和/或维护的遗留系统。这种方法允许公司逐步淘汰遗留系统，而不必打破前端，这可能是一个真正的问题。当安杰洛夫在宝马工作时，他们迁移到 Flutter，作为迁移的一部分，他们必须重做 API。

“如果我们使用像 Dart Frog 这样的东西，我们可以创建移动应用程序，然后我们可以为前端层创建后端，如中间件层，然后与遗留系统通信，然后我们可以做各种事情，如优化[和]缓存，”安杰洛夫说。“我们基本上完全控制了移动应用和后端之间的沟通渠道。前端不知道——就像藏在黑匣子后面一样——也不关心遗留 API 的实现细节。”

他说:“最终，Dart Frog 可以部署一个代理，比如“[中间件](https://thenewstack.io/case-containerizing-middleware/)，它对[数据](https://thenewstack.io/starbursts-ceo-decries-big-data-lies-touts-data-truths/)进行标准化和一些转换。他补充说，这样一个层还将支持许多其他优化。VGV 使用这种方法是因为客户通常不允许咨询公司更改遗留系统，这需要大规模的更改和高风险。

“通过这种模式，你把这个中间件放在客户端和遗留系统之间，它给了我们作为开发人员更多的控制，并允许我们在前端和后端之间共享大量代码，”他说。“这样，我们就不必每次对原有系统进行更改时都向应用商店推送新版本。我们可以在中间件中修改这些变化。客户并不真正关心一天结束时的情况，只要我们保持相同的合同，每个人都很高兴。”

“这真的是最大的好处之一，是允许我们的开发人员控制合同，”他补充说。

此外，Dart Frog 将生成一个 [Docker](https://thenewstack.io/docker-versus-kubernetes-start-here/) 文件，可以部署在任何支持容器的地方，他说。

## 即将来到镖蛙

有计划支持更多的云，特别是 Heroku 和 Vercel 的请求。正在讨论的一个选项是添加一个部署命令，以便更容易地部署到用户想要的任何云提供商。

“这是目前摩擦最大的一点。不是每个人都知道 Docker 是如何工作的，也不是每个人都知道如何将 Docker 容器上传到谷歌云，”他说。“因此，有很大的空间来优化部署流程，只需点击一下鼠标或一个命令就可以部署到一些云提供商。”

VGV 想做的事情之一是直接为 ide 提供工具，比如 Visual Studio 代码和 Android Studio。

“我们希望直接从您的 ide 提供工具，您可以在 Dart Frog 中创建新的端点，或者您可以直接从您的 IDE 附加调试器，或者您可以直接从您的 IDE 生成新的项目，”他说。"你不必打开一个新的终端，运行一些命令或什么的."

Dart Frog 获得了麻省理工学院的许可，安杰洛夫鼓励其他人在 1.0 版本发布前尝试一下。

“这是我们的目标:轻量级、快速和模块化，这样你就可以添加你需要的任何东西，”他说。“我们试图用 Dart Frog 为您处理尽可能多的复杂性，并尽可能为您提供与 Flutter 相似的开发人员体验。你从 Flutter 得到的所有好处——比如调试、开发工具，Flutter 提供的所有东西——我们试图用 Dart Frog 提供同样的东西。”

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>*