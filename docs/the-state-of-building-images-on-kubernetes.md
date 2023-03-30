# Kubernetes 上的建筑图像状态

> 原文：<https://thenewstack.io/the-state-of-building-images-on-kubernetes/>

[库伯内斯上的国家建筑图像](https://thenewstack.simplecast.com/episodes/the-state-of-building-images-on-kubernetes)

5 月份在哥本哈根举行的 KubeCon+CloudNativeCon 大会上，许多讨论都集中在使用容器构建持续集成和持续部署(CI/CD)管道所需的工作上。容器世界中仍然存在的一个主要问题是 CI/CD 管道的最后一点:构建、存储和保护为内部软件项目构建的容器。

[Steve Speicher](https://www.linkedin.com/in/stevespeicher/),[Red Hat open shift](https://www.openshift.com/)团队的主要产品经理，在 KubeCon 花了大量时间研究解决方案以及在更传统的敏捷开发环境中围绕动态构建和管理容器存在的剩余痛点。“很多人希望利用 Kubernetes 来构建管道本身，所以这是我们在这里讨论的事情之一，并了解更多关于人们对利用该平台做更多 CI/CD 感兴趣的事情，”Speicher 说。

Red Hat 首席工程师 Ben Parees 补充道:“有些人已经建立了 CI/CD 农场和基础设施，然后是他们的部署平台。“有了 Kubernetes 和 OpenShift，您就有机会将所有功能集于一身，因此您的集群既是您的构建平台，也是您的测试平台和部署平台。很容易扩展多个实例，对它们进行测试，在那里运行你的构建。

“Kubernetes 是一个运行图像的平台，但你必须自己制作这些图像，”Parees 说，他强调了许多希望采用 Kubernetes 的企业在工作流程中仍然存在的差距。“现在我们开始看到人们对‘我如何安全、可重复地构建这些图像，以及我能使用这个平台吗？ [Docker Build](https://docs.docker.com/engine/reference/commandline/build/) 需要很多权限，你可能不想给每个人都制作你的图像。在您的工作站上这样做是可以的，但在共享集群上可能就不行了。因此，现在我们开始看到一些额外的工具出现，如 [S2I](https://github.com/openshift/source-to-image) 工具、 [Kaniko](https://github.com/GoogleContainerTools/kaniko) 工具，以及其他一些围绕构建图像的工具，这些工具提供了更多的灵活性，并在平台上以安全的方式进行，”帕里斯说。

Speicher 说，再现性对于构建容器图像非常重要。他说，像红帽开发的那些系统的价值之一是围绕修补程序。“你需要以一种安全的方式推广它，”斯派克说。“当你这样做时，你需要确保这是一个可重复的过程。通过这种方式，我们有一个集中的注册表，您可以在其中保存内容，然后您可以有一个图像更改触发器，以便它可以在这些图像更改时通知构建。因此，当这种情况发生时，它将会以相当大的规模发生，并且将会发生在大量的应用程序中，您需要确保系统能够自动构建这些东西，然后以一致的方式再现最终的可部署映像。”

[https://www.youtube.com/embed/zhp4kMclk3U?feature=oembed](https://www.youtube.com/embed/zhp4kMclk3U?feature=oembed)

视频

### 在这个版本中:

[2:01:](https://thenewstack.simplecast.com/episodes/the-state-of-building-images-on-kubernetes?t=2:01)CI/CD 中有哪些摩擦仍然在阻碍着开发者？
[3:37:](https://thenewstack.simplecast.com/episodes/the-state-of-building-images-on-kubernetes?t=3:37) 现在如何为 Kubernetes 构建容器图像？
[7:16:](https://thenewstack.simplecast.com/episodes/the-state-of-building-images-on-kubernetes?t=7:16) 当开发人员开始走出去自己构建容器时，现在的开发人员体验在哪里，当它进展到 Kubernetes 发行版时有什么指导？
[10:10:](https://thenewstack.simplecast.com/episodes/the-state-of-building-images-on-kubernetes?t=10:10)[S2I](https://access.redhat.com/documentation/en-us/openshift_enterprise/3.0/html-single/architecture/#source-build)生产什么？
[15:14:](https://thenewstack.simplecast.com/episodes/the-state-of-building-images-on-kubernetes?t=15:14)Red Hat 为这些更具声明性的环境构建了什么基础设施？
[19:20:](https://thenewstack.simplecast.com/episodes/the-state-of-building-images-on-kubernetes?t=19:20) 利用 S2I 解决构建单图像层应用程序的速度问题。

[红帽](https://www.openshift.com/)赞助了这篇文章。

通过 Pixabay 的特征图像。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>