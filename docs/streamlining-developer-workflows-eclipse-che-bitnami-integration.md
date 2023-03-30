# 教程星期五:用 Eclipse Che 和 Bitnami 栈简化开发人员的工作流程

> 原文：<https://thenewstack.io/streamlining-developer-workflows-eclipse-che-bitnami-integration/>

在新堆栈教程星期五的这一集中，我们将探索 [Bitnami](https://bitnami.com/) 和 [Codenvy](https://codenvy.com/) 如何通过提供集成的工作空间和预打包的软件堆栈来简化持续集成和部署。

Bitnami 营销副总裁[大卫·丹尼斯](https://www.linkedin.com/in/davidpdennis)和 Bitnami 工程副总裁[里克·斯潘塞](https://www.linkedin.com/in/rickspencer3)与 Codenvy 首席执行官和 [Eclipse Che](http://www.eclipse.org/che/) 项目负责人[泰勒·朱厄尔](https://www.linkedin.com/in/tylerjewell)一起进行了一个简短的演示，演示了如何使用 Eclipse Che 和 Jenkins 以及 Bitnami 的开发人员容器，这些容器经过预先配置，可以让开发人员快速启动并运行。

[https://www.youtube.com/embed/-eQklVIUfk8?feature=oembed](https://www.youtube.com/embed/-eQklVIUfk8?feature=oembed)

视频
这些[开发者容器](http://bitnami.com/docker)，运行 [Bitnami](https://bitnami.com/) 所称的“按需工作空间”然后，斯潘塞通过导航到 Bitnami 的 Docker Express 的 GitHub 库开始了演练，然后开始了一个 T21 的 Eclipse Che 开发者工作区。这样做之后，工作区运行时开始自动设置。这导致了一个现成的快递网站，托管在 [Codenvy](https://codenvy.com/) 上。

在参加 Dockercon 2016 期间，Dennis 看到许多 Bitnami 展台的参观者解释说，他们平均需要两天时间才能将所有东西都放好。“这又回到了那个问题，‘在他的机器上行得通，但在我的机器上行不通。’开发人员经历的过程是:‘嘿，我得给自己弄个运行时。等一下，我必须得到正确的框架。我有那个框架的正确版本吗？它的设置方式正确吗？然后，我必须启动我的 IDE，这只是为了开始编写代码。"

“这个过程是持续的和可重复的，我们只是专注于用 Che 来自动化这个过程，”斯潘塞说。

开发人员还可以在其选择的云提供商中运行按需工作区。Bitnami 提供了各种现成的堆栈供选择，仪表盘显示 Java 的选项。NET、Android 和空白工作区。然后，斯潘塞导航到第二个工作区选项卡，即工作区库。

接下来，斯潘塞强调了一些对开始自己的持续集成和交付管道感兴趣的开发人员的关键功能，他们已经预配置了一个包含 Eclipse Che、Bitnami、Gitlab 和 Jenkins 在内的资源的 [Microsoft Azure](https://azure.microsoft.com/en-us/) 堆栈。

斯潘塞提到，对于大多数开发人员来说，[詹金斯](https://jenkins.io/)代表着他们 CI/CD 工作流程的基石，斯潘塞幽默地解释说，这也是出了名的难以建立。“你看到星期五晚上人们在酒吧里，这些可怜的破碎的灵魂。你问他们怎么了，他们会说‘我花了一周的时间试图把詹金斯安顿好。’"

当搜索哪个詹金斯实例在 Azure 中运行时，斯潘塞解释说，用户可能会注意到除了标准的詹金斯选项外，还有一个名为“生产詹金斯”的实例。通过选择“Production Jenkins”，将为用户创建所有父/子关系。通过输入应用程序名、密码，并选择要启动的子机数量，斯潘塞很快创建了一个运行 Express 样板代码的 CI/CD 管道。如果需要，Eclipse Che 还为用户提供了一个 URL 来查看他们的示例应用程序。

虽然开始使用 DevOps 可能看起来很有挑战性，但 Dennis 恳求 Bitnami 和 Codenvy 的目标是让这个过程对所有人来说都更容易。“很多人想开始做 DevOps，或者想做得更好，但我认为因为工具不太容易设置，所以他们一直止步不前。任何人都会想，“嘿，我真的想做敏捷软件开发，或者我想做 DevOps，但是我从来没有得到所有的链接和链条。或者，如果它看起来太难，是一个巨大的任务，我们将从头到尾使它变得容易得多。"

[Bitnami](https://bitnami.com/) 和 [Codenvy](https://codenvy.com/) 是新堆栈的赞助商。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>