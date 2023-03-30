# 加入码头工人的行列

> 原文：<https://thenewstack.io/joining-the-docker-ship-and-go/>

GopherCon 如火如荼。围棋和基础设施新世界是紧密相连的。像 Docker 这样的公司反映了这种联系，并展示了为什么 Go 成为容器生态系统中“管道工”的最爱。

Go 编程语言和 Docker 都是开源项目，有着很深的联系。Docker 是用 Go 写的。它的执行和开发速度、强大的标准库、完整的开发环境等等，对 Docker 技术的发展和成长至关重要。

## 正在设置

像所有开源项目一样，您需要设置并学习使用正确的工具，然后才能做出贡献。以 Docker 为例，先决条件是 Git、Github 和 Docker 本身。如果您没有免费的 Github 帐户，[去注册一个](https://github.com/join)，然后继续阅读本指南。如果你是开源新手，我发现 [GitHub 的开源指南](https://guides.github.com/activities/contributing-to-open-source/index.html)是一个有价值的资源。

由于 Docker 使用 Docker 来创建 Docker，安装 Docker 自然是您在投稿前要做的第一步。 [Docker 安装文档](http://docs.docker.com/installation/)是在 OS X、Windows 和 Linux 上设置 Docker 的优秀指南。

下一步是获取 Docker 贡献容器。这是 Docker 团队用来开发 Docker 的一个特殊容器。它包含了所有的依赖项和工具，包括 Go 编译器，这些都是你需要贡献的。

此时，您应该已经涵盖了所有的依赖项，并准备好继续下一步。(没错，你不需要一个工作的 Go 安装来贡献。)

## 寻找工作的内容

你的下一个任务是找到可以贡献的东西。这可能是任何开源项目中最难的步骤之一，如果您碰巧是一个全新的贡献者，这将尤其困难。GitHub 上 Docker 项目的优势之一是我们的发行组织。我们使用一系列的标签来给贡献者一种任何给定问题的类型(“种类”)和难度(“经验”)级别的感觉，这使得项目新手相对容易找到适合初学者的任务。

对于标有[经验/新手](https://github.com/docker/docker/labels/exp%2Fbeginner)或者[经验/新手](https://github.com/docker/docker/labels/exp%2Fnovice)的任务，看一下 GitHub 上的[发布日志。您可以根据问题的类型进一步筛选该列表，以找到您专业领域内的问题。例如，如果写作是你的强项，那么你可以寻找带有“](https://github.com/docker/docker/issues)[类/写作](https://github.com/docker/docker/labels/kind%2Fwriting)”标签的问题。

虽然查找现有标签始终是一个好方法，但有些人更喜欢为他们想要处理的问题或功能创建标签，并满足他们已经有的需求。如果你走这条路，记得遵循 Docker 的投稿指南，给你的作品最好的被合并的机会。

认识到代码并不是对 Docker 或任何开源项目做出贡献的唯一方式也很重要。您可以撰写文档、报告问题、加入我们社区的讨论、撰写博客文章或进行可用性测试。你甚至可以提出自己的贡献类型！在最近的 Docker 开源马拉松中，核心团队成员教授和指导对项目感兴趣的人，我们对贡献者的创造力印象深刻，他们做了从编写教程到录制屏幕广播的一切事情。

## **提升您的围棋技能(与围棋同行)**

Docker 代码库是用 Go 开发的，所以您应该熟悉这种语言，以便为项目贡献代码。幸运的是，如果你已经有编程经验，你会发现 go 是一种非常平易近人的语言。有一些独特的特性(想到了多个返回值和通道)，但总的来说，该语言以一种非常简单的方式读写，并且编译非常快。

现在有很多学习围棋的资源。围棋官方网站有一些适合初学者的好资源，包括互动教程[围棋之旅](https://tour.golang.org/welcome/1)，以及围棋团队的围棋文档[有效围棋](https://golang.org/doc/effective_go.html)。在我自己学习围棋的过程中，我发现[GoingGo.net](http://www.goinggo.net/)是一个很棒的资源，可以链接到社区中的许多其他资源。最后，我自己的博客“[黑客管理](http://spf13.com/)”有很多围棋相关的资源，包括非常流行的[入门围棋](http://spf13.com/presentation/first-go-app/)工作坊。

学习 Go 并更加熟悉 Docker 代码库的最好方法之一是尝试将内联文档添加到文件中。这提供了三个显著的好处:

1.  这将极大地帮助您之后的其他开发人员更好地理解代码库。
2.  这将为您提供一个完成投稿工作流程的机会。
3.  它会做出一定不会破坏任何东西的贡献。

## 最后一英里

一旦您的贡献准备好了，您应该将它提交到您的本地 fork，并向 Docker 项目发送一个 pull 请求(PR)。维护人员和项目的其他成员将审查 PR 并提供反馈。如果投稿被退回，请不要生气，因为它需要更多的工作。我认为这实际上是开源过程中最伟大的部分之一。正是通过这个过程，我们获得了有价值的反馈，并学会了如何写出更好的代码。

我经常听到人们表示，他们对为开源做贡献感到不舒服，因为他们觉得自己不是足够好的开发人员，或者他们的贡献不受欢迎。虽然我不能代表所有的项目，但 Docker 已经付出了相当大的努力来克服这些耻辱，并欢迎任何水平的贡献者。

## 获得帮助

如果您有任何关于设置的问题，或者如果您不确定如何解决代码或文档的问题，我们可以随时提供帮助。对于刚接触开源的人来说， [gitter 聊天室](https://gitter.im/docker/docker)很容易通过 web 浏览器访问，并提供了一个简单的 GitHub 认证。

如果您正在处理一个项目问题，您可以在 GitHub 中寻求帮助，只需在问题上添加包含`+status/help-wanted`或`+status/docs-help`的评论。这将创建一个其他人可以筛选的标签。

如果你熟悉 IRC，可以随时访问 Freenode 上的#docker 或#docker-dev 频道。几乎总有 Docker 维护者或社区老手在身边帮你一把。

史蒂夫·法兰克王国是码头工程的首席操作员。Docker 是新堆栈的赞助商。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>