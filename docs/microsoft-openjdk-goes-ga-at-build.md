# Microsoft OpenJDK 在构建时正式发布

> 原文：<https://thenewstack.io/microsoft-openjdk-goes-ga-at-build/>

微软在其 [Build 2021](https://register.build.microsoft.com/) 虚拟会议上公开了 OpenJDK 的发行版，这样想在 Azure cloud 上使用 Java 的开发者就可以这样做了。

[OpenJDK](https://thenewstack.io/this-week-in-programming-microsoft-jumps-back-into-java-with-openjdk-build-preview/) 是 Java SE 平台的免费开源参考实现，包括 Java 开发工具包(JDK)。OpenJDK 的[微软版本的 GA 发布紧随该技术的](https://www.microsoft.com/openjdk)[4 月预览版](https://www.theserverside.com/news/252499069/Microsoft-previews-OpenJDK-distro-to-the-delight-of-devs)之后，这是一个长期支持发行版。它是免费的，由微软为拥有合格 Azure 支持计划的客户提供支持。它包括 x64 服务器上基于 OpenJDK 11.0.11 的 Java 11 二进制文件，以及 macOS、Linux 和 Windows 上的桌面环境。

微软 Java 项目经理乔治·亚当斯在一篇博客文章中说，微软也发布了 OpenJDK Docker 镜像和相应 Docker 文件的微软版本。

## 微软对 Java 开放

由于 Java 是世界上最受欢迎的编程语言之一，有超过 700 万开发人员使用，微软打算让更多的开发人员使用 Azure 云，微软开发部门的公司副总裁 Julia Liuson 在接受新堆栈采访时说。她说，虽然该公司是 Java 生态系统的后来者，但它知道自己赢得开发者芳心的方式是通过参与生态系统并与之合作。

而且，微软本身就是 Java 的用户大户。“我们的 OpenJDK 版本运行在微软内部成千上万的虚拟机上，”Liuson 说。

Java 驱动了微软的一些核心产品，如 LinkedIn、SQL Server、Azure、《我的世界》和 Yammer。此外，微软拥有的 GitHub 是开源 Java 项目的家园，拥有超过 360 万个托管的 Java 库，Liuson 说。她说，该公司一直在提供免费的云计算周期，以支持 GitHub repos 中的 CI/CD 和代码扫描功能，这有助于为 Eclipse Foundation、Apache、VMware 和 Red Hat 等组织的几个顶级 Java 项目提供支持。

“我们正在为我们的内部系统运行成千上万的生产 JVM(不包括任何客户工作负载)，仅 LinkedIn 就有成千上万的 Java 微服务在生产中，”Liuson 在一篇博客文章中说。“微软带来了在内部和外部运行企业 Java 工作负载的专业知识，以帮助我们的客户实现业务转型。”

此外，为了更好地支持具有 Java 工作负载的组织，微软已经与 VMware 等公司合作开发 [Azure Spring Cloud](https://searchapparchitecture.techtarget.com/news/252488508/Microsoft-VMware-make-Azure-Spring-Cloud-GA) 作为 Spring Boot 应用的托管目的地。微软[还在 2019 年收购了总部位于伦敦的 Java 性能监控软件提供商和咨询公司 JClarity](https://www.theserverside.com/news/252468926/Microsoft-gains-instant-Java-credibility-with-jClarity-buy) ，作为[微软 Java 工程集团](https://devblogs.microsoft.com/java/)的基础。

Liuson 在她的帖子中说:“我们现在通过与 Red Hat、Oracle 和 IBM 的合作伙伴关系和协议支持全系列的 Java EE 和 Jakarta EE 应用服务器，并在 Azure 虚拟机上新发布了 [Red Hat JBoss EAP](https://aka.ms/jbosseap-blog-build2021) 和 [IBM WebSphere](https://aka.ms/websphere-blog-build2021) 。

## 帮助社区

然而，尽管微软做了很多工作来招募 Java 用户迁移到 Azure cloud，但社区中的一些人希望他们也能为社区做更多的事情。

“微软最近宣布在 Azure 上改进对 Java 的支持，加强了 Java 在企业计算中的重要性。我真的很高兴看到微软战略的清晰愿景:将企业工作负载吸引到 Azure 意味着以一流的方式支持 Java，” [Eclipse Foundation](https://thenewstack.io/java-ee-move-to-eclipse-foundation-makes-way-for-cloud-native-java/) 的执行董事 [Mike Milinkovich](https://accounts.eclipse.org/users/mmilinkovich) 说。“然而，微软旅程的下一步将是全面参与构建 Java 未来的开发者社区。微软的合作伙伴 IBM、Oracle 和 Red Hat 正在 Jakarta EE 和 MicroProfile 社区中工作。他们的 WebSphere Liberty、WebLogic 和 JBoss EAP 产品支持 Jakarta EE 和 MicroProfile 规范。微软的知识和观点将受到这些社区的欢迎，因为他们正致力于为 Java 创建下一代云原生平台。”

正如 Liuson 提到的，微软正在为其内部系统运行超过 500，000 个 JVM，仅 LinkedIn 就有超过 1，800 个 Java 微服务在生产中。微软自己在 GitHub 上有超过 60 个 Java 开源项目。

微软与其生态系统合作伙伴合作，将现有的 Java 工作负载引入 Azure，并为 Kroger Swiss re 和 AIA Singapore 等客户扩展应用程序的功能。例如，[友邦保险新加坡](https://customers.microsoft.com/en-us/story/860509-aia-singapore-drives-performance-enhancements-after-moving-java-applications-to-azure)将几十个 Java 应用程序从 JBoss EAP 服务器迁移到 Azure 上的混合架构，该架构以 Apache Tomcat 和 Azure Kubernetes 服务为特色，Liuson 说。

“当 Java 社区获得了 PaaS 产品的另一种选择时，这总是一个伟大的日子，”德克萨斯州弗劳尔德隆 Genuitec 的技术副总裁 Todd Williams 说。“看来微软已经与合作伙伴网络一起为多种类型的 Java 工作负载构建了一个非常有吸引力和竞争力的产品，这应该能够确保一定程度的成功。”

与此同时，Liuson 表示，微软正在与 Java 社区密切合作，以确保 Java 针对云原生计算进行优化。

“这是一场我们积极参与的关于整个 OpenJDK 生态系统的对话，”她说。“在过去的几年里，我们一直在努力提高垃圾收集器的速度，改善容器的启动时间，让 Java 更适合构建微服务。但是我们正在与生态系统合作。有许多合作伙伴正在共同致力于这项特别的计划。”

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>