# 使用云原生构建包轻松创建容器映像

> 原文：<https://thenewstack.io/container-images-the-easy-way-with-cloud-native-buildpacks/>

[](https://www.linkedin.com/in/danielmikusa/)

 [丹尼尔·米库萨

丹尼尔是 VMware Java build pack 的开发人员，是 Paketo 项目的维护者，也是 build pack 的长期支持者。](https://www.linkedin.com/in/danielmikusa/) [](https://www.linkedin.com/in/danielmikusa/)

当我在小学的时候，我的数学老师捉弄了我。她解释了长除法的概念，然后让我和我的同学在黑板上、作业上、考试上做长除法，我们总是要展示我们的作业。我不知道我们在长除法上花了多少时间，但我知道自从我有了计算器后，我在长除法上花了多少时间，那是零。

然而，学习一个过程并不是浪费时间。以艰难的方式学习事情可以让你更好地理解你的任务，更好地欣赏你的工具。与此同时，会计师不会用长除法来平衡公司的账目；他们将使用计算机来确保数学是正确的。

这是我最近使用 Dockerfiles 的经验。我很高兴我了解了他们；我很高兴我对他们有些经验；我很高兴我明白它们是如何运作的。然而，在一天结束的时候，这不是我想花时间的地方。这听起来可能像是你在汽车保险杠贴纸上看到的东西，但我宁愿编码。尽管如此，我还是绝对需要将我的软件打包到一个容器映像中，以便易于分发和使用。我只想用最少的努力来做这件事。

我现在可以告诉你最简单的方法，但是，就像我的小学数学老师一样，我要先告诉你最难的方法。

## 艰难的道路

如果你是一名编写 docker 文件的应用程序开发人员，无论你是否意识到，你都在艰难地做着。

Dockerfiles 有什么难的？细微差别。下面举个例子来说明这一点:

```
  FROM openjdk:8-jdk-alpine
  VOLUME  /tmp
  COPY target/*.jar app.jar
  ENTRYPOINT  ["java","-jar","/app.jar"]

```

看似简单，对吧？是的，而且在某种程度上，它有助于完成任务。不过，这种方法也有一些问题:

1.  **安全性**:您的安全团队会对使用这个 docker 文件生成的图像有问题，因为它们将以 root 用户身份运行。
2.  **灵活性**:您的操作团队可能想要使用图像，但是要使用它，他们需要向入口点命令传递不同的参数。您不能这样做，至少不能在不重建您的映像或完全覆盖命令的情况下这样做。
3.  速度:你可能想要更快的构建时间。谁没有呢？这意味着你需要更智能的分层、缓存，甚至可能是多阶段构建。
4.  **附加软件**:如果你需要 Tomcat 来运行你的应用程序怎么办？
5.  **未知的**:你确定你遵循了所有的[最佳实践](https://www.docker.com/blog/intro-guide-to-dockerfile-best-practices/)？

当然，你可以用 Dockerfiles 解决所有这些问题，但这就是复杂性的来源。这就是你被迫投入时间开发和维护 docker 文件的地方。这就是事情变得困难的地方。

在我职业生涯的大部分时间里，我都是 Linux 用户。任何运行过 Linux 桌面或服务器的人都应该熟悉运行包更新。偶尔，你会到你的平台上，看看有什么新的东西并应用更新。完成后，你重新启动，当你的机器重新装载它闪亮的新内核时，你反思你是如何保护你的计算机在接下来的一周免受互联网的祸害的。

如果您有几台服务器，很容易让它们都保持最新。我想说这甚至很有趣，但这可能只是我。但是，如果您有 100 或 1000 台服务器，那就不好玩了。手动更新它们是一种艰难的方式。

Dockerfiles 也是如此。如果你正在做一个项目，管理它的 done 文件不会太麻烦。也许你甚至乐在其中。但是，如果你从事的项目不止一个，那很快就会成为一种负担。您有多个 docker 文件，跨多个存储库，其中一些可能有独特的、特定于项目的需求，并且所有这些都需要维护。

这也是一种艰难的方式。

## 简单的方法

对年轻的我来说，是计算器把我从长除法中解放出来。对今天的我来说，是[构建包](https://buildpacks.io)和驱动它们的工具 [pack CLI，](https://github.com/buildpacks/pack/releases)把我的项目从 docker 文件中解放出来。

简单的方法是什么？一个单独的命令:*打包构建我的-酷-应用-图像*。

想打包你的 Java，。NET Core，Python，Ruby，PHP，Node.js，Go 还是 Rust app？都是一样的命令。等等。那不可能。这是如何工作的？什么样的魔法正在进行？很高兴你问了。

构建包可以非常简单地解释。插入一些源代码并接收一个容器图像。中间发生的事情是由构建包动态决定的，并且是为您的应用程序定制的。Buildpacks 了解你的代码，构建它需要什么，运行软件需要什么，以及如何将所有这些组合成一个映像。它们将您放入 Dockerfiles 的所有细微差别和工作打包，并封装在代码中，因此您不必考虑它。您获得了所需的映像，并且可以继续开发您的软件。

还怀疑？以下是 buildpacks 如何帮助您生成高质量的图像。

1.  **没有更多的 Dockerfiles** :继续，从你的项目中*RM docker files*。很好玩。
2.  安全可信基础映像:当构建包执行时，它们在从基础构建映像派生的映像中执行。当您的应用程序执行时，它是在从基本运行时映像派生的映像中执行的。你可以选择你的基本映像，并且有一些安全的基本映像可以从受人尊敬和信任的组织获得，比如[云铸造基金会](https://www.cloudfoundry.org/)、Heroku 和 Google。此外，由于只有两个基本映像，这大大减少了您的安全团队需要审核的映像数量。
3.  **物料清单**:随着构建包的运行，它们为已经安装到映像中的东西生成一份物料清单。这可以在许多方面有所帮助，但最值得注意的是，它将帮助您回答审计人员和安全团队提出的问题。
4.  **可再现的图像构建**:给定相同的输入，您将获得相同的输出图像。如果您需要返回并重建图像或验证图像，这将非常方便。哈希应该匹配，因为映像构建是可重复的。
5.  **支持超快速构建的缓存**:构建包是智能的，可以主动缓存，因此应用程序的重建总是非常快速。这不需要额外的工作或思考；它从盒子里出来。
6.  **默认情况下包含最佳实践**:不用再担心层的顺序，减少层大小的技巧，缓存获取的资源的技巧，或者在多级构建中复制什么。Buildpacks 将始终如一地将最佳实践应用于您的所有映像。
7.  **与其他流行工具的集成**:虽然您可以使用 pack CLI，但也可以集成 Spring Boot、CircleCI、GitLab、Tekton、[VMware Tanzu Build Service](https://tanzu.vmware.com/build-service)和 Kubernetes 等。
8.  **闪电般的映像升级**:基础映像升级可以在不进行重建的情况下通过[过程进行，该过程被称为重新基础化](https://buildpacks.io/docs/concepts/operations/rebase/)。这使您可以升级整个映像群，所需时间只是重建时间的一小部分。

## 用组装包学习飞行

如果你还在阅读，你可能想知道下一步去哪里。别担心，我会掩护你的。以下部分包含一些建议的后续步骤。

### 入门指南

如果你是全新的，刚刚开始创建你的第一个容器图像，这是我推荐的路径。

1.  [Buildpacks 入门指南](https://buildpacks.io/docs/app-developer-guide/)应该是你的第一站。它将带你完成安装*包*和构建你的第一个应用程序。它还涵盖了基本的定制，如设置环境变量、选择构建包、挂载卷、定制启动过程和使用 project.toml，这是一种保存应用程序设置的便捷方式。如果你还不想安装任何东西，你可以看看 [Katacoda 教程](https://katacoda.com/buildpacks/scenarios/app-journey)。
2.  虽然 Buildpacks 项目提供了一个 buildpacks 规范，但它并没有提供一套完整的 buildpacks。Paketo 项目正是这样做的，它为所有您喜欢的语言提供了一套全面的构建包。下一步，我建议看一下 [Paketo 入门指南](https://paketo.io/docs/)。这里有更多的示例供您尝试，并提供了特定于您所选择的语言的信息。
3.  此时，您可能想要运行您的映像，所以请花些时间熟悉 Docker，它非常适合在本地运行映像，或者 [Kubernetes](https://tanzu.vmware.com/kubernetes-vs-docker) ，这是大多数应用程序映像在生产中运行的地方。这一步与构建包无关，但是理解这些工具很重要，因为构建包只构建映像。你需要别的东西来运行它们。

### 迁移到构建包

如果您是 Dockerfiles 的老手，您可能对如何从 docker files 迁移到 buildpacks 更感兴趣。虽然本文篇幅有限，无法提供全面的指南，但我可以给你一些提示，帮助你加速迁移。

1.  安装 pack CLI。它在大多数包管理器中，或者你可以从 [GitHub](https://github.com/buildpacks/pack/releases) 中获得。
2.  您感兴趣的主要 pack 命令是 [pack build](https://buildpacks.io/docs/tools/pack/cli/pack_build/) ，所以看看它的用法/docs。
3.  同样，Buildpacks 项目提供了 buildpacks 的规范，但没有提供一套完整的 buildpacks。有不同的实现可用。您可以运行 *pack builder suggest* 来获得这些实现的最新列表，buildpacks 规范称之为[构建器](https://buildpacks.io/docs/concepts/components/builder/)。我会推荐 Paketo 的 builder，因为它有很好的语言支持和友好的开源社区，但也有来自 Google 和 Heroku 的优质 builder。这个决定不要想多了。选择一个支持您需要的语言、有一个适合您的堆栈(构建和运行时基础映像)并且与您选择的部署平台配合良好的。
4.  简单地开始，对你的应用程序运行*包构建*，看看会发生什么。在许多情况下，这将只是工作。如果您需要进一步配置，本指南将介绍如何使用 project.toml 设置环境变量、挂载卷和持久化设置。如果您正在使用 Paketo 实现，您可以查看特定于语言的参考文档，例如 [Java](https://paketo.io/docs/howto/java/) 、[。NET](https://paketo.io/docs/reference/dotnet-core-reference/) 、 [Ruby](https://paketo.io/docs/reference/ruby-reference/) 、 [Go](https://paketo.io/docs/reference/go-reference/) 、 [Node.js](https://paketo.io/docs/reference/nodejs-reference/) 、 [PHP](https://paketo.io/docs/reference/php-reference/) ，解释了可以传递到 buildpacks 中的附加配置选项，比如选择语言运行时的特定版本，或者将附加参数传递给构建工具。另外， [Paketo Buildpacks 配置文档页面](https://paketo.io/docs/reference/configuration/)解释了更高级的主题，如 Procfiles、服务绑定、定制标签、离线/代理后工作以及添加定制 CA 证书。

## 加入社区

如果您有疑问或遇到无法解决的问题，欢迎社区随时提供帮助。这里有几个你可以寻求帮助的渠道。

1.  获得帮助最简单的方法就是[在 StackOverflow](https://stackoverflow.com/questions/tagged/buildpack) 上发布一个问题。使用标签 *buildpack* 向社区提出您的问题。如果你对 Paketo 项目或构建包有疑问，你也可以使用[pake to 标签](https://stackoverflow.com/questions/tagged/paketo)。
2.  如果您对 Slack 感兴趣，您可以向 [Buildpacks Slack 频道](https://slack.buildpacks.io/)或 [Paketo Slack 频道](https://slack.paketo.io/)提出问题。不要太在意你贴在哪里(不要双贴就好)。这些群体有重叠，友好的社区会给你指出正确的方向。
3.  你也可以在项目的 GitHub 组织上发布问题或报告你发现的 bug，无论是 [Buildpacks](https://github.com/buildpacks/) 还是 [Paketo](https://github.com/paketo-buildpacks/) 。组织下有很多不同的项目，所以再次强调，不要太担心你在哪里发布；社区成员可以帮助确保报告到达正确的团队。
4.  如果你想参与并回馈社区， [Buildpacks](https://buildpacks.io/community/) 和 [Paketo](https://paketo.io/community/) 都是开源的，欢迎所有的贡献。

上面提到的一切都是免费的(就像啤酒和自由一样)。这都是围绕 buildpacks 的开源社区的一部分。但是，如果您希望在您的专业工作中采用构建包，并且想要一组扩展的构建包、离线/air gap 兼容的构建包、基于 Kubernetes 的构建自动化和商业支持，这些功能可以通过 VMware [*Tanzu 构建服务*](https://tanzu.vmware.com/build-service) *获得。*

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>