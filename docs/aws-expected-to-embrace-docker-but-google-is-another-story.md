# AWS 期望拥抱 Docker，但谷歌是另一个故事

> 原文：<https://thenewstack.io/aws-expected-to-embrace-docker-but-google-is-another-story/>

拉斯维加斯金沙会展中心的 AWS re:Invent 展厅需要步行 20 分钟。这是一年中最大的云事件，但是还有什么值得关注的呢？当然是码头工人。

与谷歌不同，AWS 预计将在本周的活动中拥抱 Docker。正如 GigaOm 的芭芭拉·律界英豪[所指出的](https://gigaom.com/2014/11/05/coming-from-amazon-web-services-better-but-unspecified-docker-support/?utm_content=bufferf2690&utm_medium=social&utm_source=twitter.com&utm_campaign=buffer)，正如杰夫·巴尔(Jeff Barr)上周在一条推文中所阐述的那样，已经有了支持 AWS 的迹象，他最出名的可能是他为 AWS 所做的宣传以及他在 AWS 博客上写的关于其最新产品新闻的数百篇帖子。

这意味着什么是任何人的猜测，但它确实表明了 AWS 如何看待 Docker 与谷歌的不同，谷歌已经竭尽全力解释自己的容器引擎技术和他们开发的管理系统 Kubernetes。

### 谷歌容器引擎

本周早些时候，谷歌云平台发布了新的见解，预计用户将如何利用谷歌容器引擎(GKE)，该引擎在上周的谷歌云平台直播秀上推出。谷歌容器引擎产品管理副总裁 Brian Stevens 表示，利用开源 Kubernetes 项目的 GKE 允许用户创建和启动可在集群中管理的便携式 Docker 容器。

周一，产品经理 Craig McLuckie [写了一篇博客文章，进一步澄清了](http://googlecloudplatform.blogspot.com.es/2014/11/open-source-hosted-containers-recipe.html "Google Container Engine in hybrid cloud environments")GKE 打算如何跨混合云和本地环境移植。事实上，谷歌表示，谷歌容器引擎发布背后的全部动机是帮助那些寻找提供高度移动性的应用程序开发解决方案的客户。为了确保便携性，GKE 尊重三个核心价值观，麦克卢奇写道:

*   **基于容器:** McLuckie 指出，将应用程序从操作系统和基础设施环境中分离出来是 Docker 成为如此受欢迎的容器框架的原因
*   模块化: McLuckie 坚持认为，使用 Kubernetes 作为 GKE 的主干意味着一切都是基于“严格和有原则的模块化”设计的，每个组件都可以被拔出和替换
*   **分离服务:** McLuckie 承认，开发人员需要创建混合云场景的能力，这种能力允许应用程序被编排为托管在各种多云和内部环境上的一系列微服务。

Stevens [在发布时的一篇博客文章](http://googlecloudplatform.blogspot.com.es/2014/11/google-cloud-platform-live-introducing-container-engine-cloud-networking-and-much-more.html "Google Container Engine")中写道:“它建立在开源项目 [Kubernetes 项目](https://thenewstack.io/about-etcd-the-distributed-key-value-store-used-for-kubernetes-googles-cluster-container-manager/ "Kubernetes and Etcd")的基础上，还提供了高水平的工作负载移动性，使应用程序可以在开发机器、内部系统和公共云提供商之间轻松移动。”。当然，希望是，虽然基于容器的应用程序可以在任何地方运行，“快速启动、高效的虚拟机主机和无缝虚拟化网络集成的结合使谷歌云平台成为运行它们的最佳场所，”史蒂文斯当时写道。McLuckie 在他今天的博客文章中强调了这一点，他提出了三种场景，其中谷歌云平台可以允许测试和运行应用程序的混合环境(例如在云中进行横向扩展测试，其中高吞吐量横向扩展测试可以按分钟收费，然后生产仍在本地进行)。

或许这个消息会给 Docker 生态系统的合作伙伴一些安慰，他们对 GKE 的发布相对平静。

持续集成工具是目前最大的 Docker 生态系统合作伙伴之一，据首席执行官 Avi Cavale 称，约有 20 至 25，000 个容器在生产中，并被认为是“现阶段正在生产中的最大的 Docker 平台”。上周，Shippable 宣布了 800 万美元的首轮融资，以帮助他们扩大工程团队，并比路线图计划提前 6 个月开发出他们的产品。

Cavale 说，当软件被构建时，它通常是在一台机器上构建的，那通常是开发者的笔记本电脑。“然后，它被推到一个模拟生产的环境中。真正的整合发生在这种环境中。它创建了开发人员依赖的标记，这就是真正的问题出现的时候:当在架构本身中尝试这样做的时候。”你怎么知道它是在谁的盒子上创建的呢？”他问道。分诊很痛苦。容器让我们可以在笔记本电脑上运行完整的测试。因此，我可以在您合并之前运行完整的部署，这样您就可以知道您要合并的任何内容都完全正常。"

卡瓦尔说，当旋转一个容器变得如此容易时，人们就会倾向于使用微服务。例如，开发人员不再进行大的包代码下降。所需的系统将演变成越来越小的部件，可以在集装箱内运行，然后可以装运。

“我们真正关注的是开发人员的工作流程，应用程序是如何构建和交付的。

“我们专注于应用生命周期管理:我们如何为集装箱建造航线，”Cavale 说。“企业有自己的东西，所以我们有很多事情要做，这就是我们接下来要关注的。”

“谷歌已经宣布了他们的云，实际上是由开发者决定使用他们想选择的任何东西。然后，我们创建一个标准的方法，在开发人员选择的环境中部署容器，”Cavale 说。

McLuckie 回应了 Cavale 对 ship able 部署环境的非意见性的看法，确认了 GKE 能够与这样的 Docker 生态系统合作伙伴友好相处:“ship able 是一个持续集成框架，让您可以构建和部署 Docker 容器。“Shippable 可以部署到单个非托管节点(native Docker)，也可以部署到智能托管集群(Kubernetes，或我们的托管版本谷歌容器引擎)，”麦克卢奇说。

但是 Docker 并不是在为 GKE 唱赞歌。事实上,《GKE 新闻》展示了谷歌是如何讲述一个容器故事的，这个故事很少强调 Docker，而是更强调一种通用的“容器”方法。甚至可以说谷歌混淆了 Docker 的故事。这在传递的信息中显而易见。谷歌正在推广“谷歌容器引擎”这个名字，它与 Docker 公司一直在营销的“Docker 引擎”惊人地相似。

它显示了两家公司在集装箱领域的竞争。过去一周的新闻表明，GKE 将自己定位为可以管理 Docker 容器的中间件，从而扰乱了 Docker 的势头。

### Docker 视图

Docker 的商业部门 Docker Inc .的营销副总裁大卫·梅西纳认为，GKE 是对 Docker 生态系统及其增长的进一步验证。但他对 GKE 制造的容器的可移植性持怀疑态度。

> “从我们的角度来看，最终目标仍然是便携性。谷歌容器引擎基于 Docker 容器，但它基本上是谷歌云平台的解决方案。”

对于 Messina 来说，更令人担忧的是，谷歌将他们的 alpha 版本产品称为容器引擎可能会引起混淆。

Messina 认为 Docker 开源项目的核心是可用于构建和运输容器的平台。这个平台就是 Docker 引擎。

> “因此，根据我与客户交谈的经验，谷歌的命名惯例已经令人困惑。这是一个谷歌云平台特定的解决方案，用于编排特定的 Docker 容器。它与建造、运输和运营 Docker 集装箱完全无关。”

也许这就是为什么迄今为止 Docker 社区对谷歌云平台公告的反应和评论如此之少的原因。甚至在整个 GCP 现场活动中展示的演示也没有向 Docker 的方向倾斜，之前关于谷歌容器引擎将如何作为更广泛的 Docker 生态系统的一部分工作的细节很少。通过本周的博客文章，谷歌正在寻求将自己定位为 Docker 容器的平台，可以在不限制开发者环境的情况下编排、管理和监控应用程序。

这和 Docker 的策略一致吗？不完全是。Docker 渴望成为自己的平台，并且正在开发自己的工具来管理云服务中的容器。

AWS 生态系统已经准备好接受它。这里有几家初创公司正在谈论 Docker 与 AWS 未来几天预计将发布的新闻的集成。AWS 社区得到了 Docker，他们很喜欢它。为什么？易用性、灵活性等。

码头工人在明亮灯光下的表现已经令人惊讶了。他们一直被质疑其商业模式。就其本身而言，Docker 被许多人视为一家对自己的工具比对 Docker 生态系统中的工具更感兴趣的公司。正如 Google 希望自己的编排环境来控制容器一样，Docker 也希望自己的技术被企业采用。

至于 AWS？它似乎很好地为 Docker 提供了构建自己平台所需的支持。从长远来看，这将如何发展，这是 re:Invent 的每个人都想回答的大问题。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>