# Codenvy 便携式开发人员工作区之旅

> 原文：<https://thenewstack.io/developers-laptop-container-workspace-codenvy/>

今天的开发人员经常不得不同时处理多个项目，但在某些情况下是完全不同的编程语言。当考虑到开发人员必须创建一个新的工作空间来测试、调试或开始一个新项目的次数时，这甚至会成为一个更大的问题。

Codenvy 已经利用开源工具 [Eclipse Che](http://www.eclipse.org/che/) 的力量来帮助开发者解决这个痛点。

Codenvy 首席运营官 [Brad Micklea](https://twitter.com/bradmicklea) 最近与新 Stack 创始人 [Alex Williams](https://twitter.com/alexwilliams) 坐在一起，在一个简短的教程中展示了 Che 的一些功能。在整个[教程](https://thenewstack.io/podcasts/tutorials/)中，Micklea 在 Codenvy 中创建了一个新项目，调试了一个失败的构建，建立了可共享的工作流，并展示了 Codenvy 如何帮助开发人员保护他们的代码安全。

[https://www.youtube.com/embed/cL5Ka6_fPPU?feature=oembed](https://www.youtube.com/embed/cL5Ka6_fPPU?feature=oembed)

视频

Codenvy 的下一个关键特性是如何管理工作区。Micklea 指出，Codenvy 的所有工作空间都是通过网络或云来控制的。

Che 是“一个随需应变的容器化开发人员工作空间”。我们将您在开发人员笔记本电脑上所做的一切都放入一个可以协作、共享和集中管理的容器中。”

这种方法提供了一些好处，包括安全性和灵活性。

“通常，IT 部门都在努力寻找保护笔记本电脑的方法。在 Codenvy 托管环境中，IP 永远不会离开中央托管系统。这样更安全。其次，协作性更强。米克尔亚说:“工作空间一旦容器化，就可以很容易地复制和共享。从 Codenvy 仪表板上，用户能够通过工作区 tiles 选择一个 Eclipse Che 项目，然后请求一个为该特定项目定制的 JSON 文件。创建 Docker 容器后，Codenvy 会注入它的代理，这样它就可以控制容器的生命周期，这样开发人员就不必费心启动或停止它。

接下来，将基于 Eclipse Che 的基于浏览器的 IDE 推送到用户的浏览器。开发人员不仅可以在他们的 Codenvy 工作区中预览他们的代码，还可以预览应用程序本身。他们可以访问 git 命令、代码辅助工具(如语法突出显示和文本补全)以及允许 root 用户访问其容器内部的终端。

Micklea 随后建立了一个新工厂，Codenvy 称之为 Docker 容器 URL。通过快速导航到 Codenvy dash 的 Factory 部分，用户可以选择一个他们希望转变为工厂的工作区，与他人共享，并根据他们的规范配置堆栈和命令。任何访问工厂 URL 的人都将被提供一个隔离的 Docker 容器，其中有一个工厂工作区的副本，Micklea 提到这是进行代码审查或面试新开发人员候选人的理想选择。

“我们即将发布一个更新，给予 Codenvy 双光标支持，这样你就可以远程进行结对编程，”Micklea 说。

Codenvy 的另一个亮点是它为那些在调试容器时对提高生活质量感兴趣的人提供的特性。Micklea 随后解释说，开发者可以轻松地将他们的 Codenvy URLs 放入 JIRA 问题。Codenvy 工作区为 DevOps 团队成员提供了一种更快速的解决问题的方法，Micklea 随后通过显示失败的 CI 测试来展示这一点。

“我们可以响应配置项中的一个 webhook，然后查询它以说明问题发生在哪个项目、分支、提交 ID 和构建中？然后，我们创建一个定制的诊断工作区，该工作区已经与构建中断点同步，”Micklea 解释道。

他解释说:“如今，每当开发人员配置一个工作空间时，他们就会被削减 1000 个工作空间，这是他们必须经常做的事情。“用 Java 7 做一个项目，而用 Java 8 做另一个项目，这有点像噩梦。相对于点击一个链接，他们打开自己的浏览器标签，他们已经被隔离，干净的房间，开发者可以随意在它们之间切换。”

Codenvy 是新堆栈的赞助商。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>