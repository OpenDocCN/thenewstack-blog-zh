# Boxfuse“可启动应用程序”封装了不可变的基础设施，以实现可移植性、安全性

> 原文：<https://thenewstack.io/boxfuse-bootable-app-packages-immutable-infrastructure-portability-security/>

当技术世界的许多人期待容器来解决一系列软件开发和部署问题时，总部位于慕尼黑的 [Boxfuse](https://boxfuse.com/) 专注于寻找一种更好的方法来使用虚拟机在亚马逊网络服务上部署 JVM、Node.js 和 Go 应用程序。

“我们觉得虚拟机受到了不公正的指责。这些天他们实际上提供了很多优势。Boxfuse 创始人兼首席执行官[阿克塞尔方丹](https://github.com/axelfontaine)说，在 AWS 上，虚拟机给你一个非常细粒度的构建块，例如，你可以从一个 [t2.nano](https://aws.amazon.com/blogs/aws/ec2-update-t2-nano-instances-now-available/) 开始，每小时只需几分之一美分，它们按秒计费，启动相对较快——与容器相比，它们只是减少了你环境中活动部件的数量。

该公司是在他之前的连续交付工作基础上发展起来的——对运营方面的复杂性感到沮丧。该公司声称，结果是一个基于不变基础设施的架构，它是可移植的、可靠的和可预测的。

这家德国公司还创建了数据库迁移工具 [Flyway](https://flywaydb.org/) 。

## 相同的基础设施

尽管在软件通过连续交付过程进入生产阶段的过程中努力保持环境的一致性，但是一系列的变化——补丁、升级、配置——可能会突然出现。

Boxfuse 创建了一个它称之为可启动的应用程序——整个机器被打包成一个不可变的单元，在每次更改后由持续集成服务器重新生成。然后，整个机器映像可以在不同环境之间不变地升级。同样的可启动 app 可以部署在 [VirtualBox](https://www.neowin.net/news/virtualbox-524) 和 AWS [EC2](https://aws.amazon.com/ec2/) 上。

Boxfuse 首先分析应用程序，动态生成包括基于 Linux 的操作系统在内的最小虚拟机映像。该映像包括一个引导加载程序、一个内核、一个 JVM 或 Node.js 运行时和您的应用程序。第二部分是编排和供应组件。

它将图像上传到 AWS，将其转换为 AMI，并自动提供应用程序需要的所有资源。它还提供了一个名为 Boxfuse Vault 的图像存储库。

Boxfuse 原生运行在 Windows、Mac 和 Linux 上，并针对流行的工具和框架进行了特殊优化，如 Spring Boot、Dropwizard、Grails、Play、可执行 Jars、Tomcat、TomEE 和 Node.js

除了[命令行客户端](https://boxfuse.com/docs/commandline)，它还提供了 [Maven](https://boxfuse.com/docs/maven) 和 [Gradle](https://boxfuse.com/docs/gradle) 插件。

[https://www.youtube.com/embed/Z5Yxq-0xJq0?feature=oembed](https://www.youtube.com/embed/Z5Yxq-0xJq0?feature=oembed)

视频

其演示中的可启动应用程序刚刚超过 48MB。他说，较小的图像相当于较小的攻击面，同时提高了安全性。

“我们能够拥有非常紧凑的东西，提供与容器相同的能力来真正冻结环境并移动它，但不需要容器的运行时间和复杂性。我们可以将它直接部署到虚拟硬件上，”Fontaine 说。

它与亚马逊 RDS 集成，自动提供关系数据库。

“我们可以提供负载平衡器…利用负载平衡器进行零停机升级，我们可以提供 https、域名和日志记录—所有类型的资源都可以通过这一个命令获得，因此这实际上是非常强大的，”Fontaine 说，并解释说命令 **boxfuse run** 是用户所需要的。

“仅仅您的标准容器解决方案是不够的。你需要有某种注册表，在某个地方推送你的容器，你需要一个 orchestrator，它有合适的插件或者与你的基础平台集成。[Boxfuse 是]端到端集成的，所以如果您不想，就不必担心所有这些部分。”

方丹指出了三个主要竞争对手:

*   **AWS 豆茎 。这项服务提供了一个标准的 AMI，你可以创建[自定义映像](https://docs.aws.amazon.com/elasticbeanstalk/latest/dg/using-features.customenv.html)，但是 Fontaine 坚持认为，不能保证你在一个集群中运行的两个实例 100%相同。**
*   **Docker/ECS/Kubernetes 生态系统**。他说，虽然它享有很高的知名度，但根据公司的规模，可能会带来一些客户不需要的复杂性。
*   [Heroku](https://www.heroku.com/) 。方丹认为 Heroku 在“完成任务方面”名列前茅。你确实以相对较高的价格部署在他们有围墙的花园里。我认为这种便利是市场上最好的，但价格非常高，”他说。

对于 2018 年，该公司将增加与 Docker 的集成，以满足那些喜欢 Docker 工具，但不一定想要运行容器的复杂性的客户。他说，他们将能够在本地测试应用程序，并将它们部署到 AWS，而不需要任何代理或 Kubernetes 或任何其他东西。

通过 Pixabay 的特征图像。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>