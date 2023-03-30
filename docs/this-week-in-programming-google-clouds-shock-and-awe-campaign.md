# 本周编程:谷歌云的震撼和敬畏运动

> 原文：<https://thenewstack.io/this-week-in-programming-google-clouds-shock-and-awe-campaign/>

在本周讨论科技新闻的节奏时,“震惊和敬畏”这个词出现了，并一直伴随着我。也许将谷歌本周在 2019 年云下一次会议上的声明与美国旨在恐吓反对派屈服的军事行动相比较是一个麻木不仁的隐喻，但这可能有点像对老年人注意力范围的攻击，以及对这么多声明同时出现的能力的打击。

与此同时，许多人很快指出谷歌在企业云方面的弱势地位，亚马逊 AWS 和微软 Azure 处于领先地位，因此这种类比似乎是…恰当的。当竞争对手领先时，你需要用你永远不会期望得到回报的单方面集成震惊所有人，并用平台灵活性让他们敬畏，说“我们甚至会与竞争对手合作，让你站在我们这边。”在 TechCrunch 上，罗恩·米勒提出了这一观点，他写道，[谷歌云平台(GCP)正在采取一些强有力的措施，通过“将自己推销为可以帮助你实现数字化转型的混合云公司”，使自己与 AWS 和微软](https://techcrunch.com/2019/04/11/google-cloud-makes-some-strong-moves-to-differentiate-itself-from-aws-and-microsoft/)区分开来

这似乎也是谷歌正在做的事情，它发布了大量公告，但无畏的开发者不要害怕，因为我们希望强调一些你感兴趣的主要公告，从向谷歌云添加开源数据管理和分析服务到其最新的无服务器产品到其最新的云原生编码工具。事不宜迟…

## 面向开发人员的云计算 2019 年

*   **GCP 获得数据服务集成:**首先，谷歌宣布将为谷歌云客户带来[最好的开源软件，在数据管理和分析领域有七个合作伙伴，包括](https://cloud.google.com/blog/products/open-source/bringing-the-best-of-open-source-to-google-cloud-customers)[融合](https://www.confluent.io/)、[数据税](https://www.datastax.com/)、[弹性](https://www.elastic.co/)、[流入数据](https://www.influxdata.com/)、 [MongoDB](https://www.mongodb.com/) 、 [Neo4j](https://neo4j.com/) 和 [Redis 实验室](https://redis.com/)[通过这些合作伙伴关系，谷歌将提供紧密集成到谷歌云平台(GCP)的托管服务，提供单一用户界面和统一计费以及支持。在一份独立但类似的公告中，谷歌还](https://redis.com/)[宣布了三个新的企业数据库](https://cloud.google.com/blog/products/databases/enterprise-databases-managed-for-you):微软 SQL Server 的[云 SQL 预览版、](https://cloud.google.com/sql-server/)[支持 11 版本的 PostgreSQL 的](https://cloud.google.com/sql/)云 SQL，以及[云 Bigtable 的多区域复制](https://cloud.google.com/bigtable/)。
*   **谷歌云服务平台正式上市 Anthos:** 自从谷歌[几个月前推出谷歌云服务平台](https://thenewstack.io/googles-cloud-services-platform-brings-managed-kubernetes-to-hybrid-cloud/)以来，我把它的名字和 GCP 搞混了，所以我很高兴该公司把这项服务更名为“Anthos”抛开更名不谈，[推出 Anthos](https://cloud.google.com/blog/topics/hybrid-cloud/new-platform-for-managing-applications-in-todays-multi-cloud-world) 也意味着谷歌混合 Kubernetes 平台的全面上市，以及管理运行在 AWS 和 Azure 等第三方云上的工作负载的能力。TechCrunch 的 Frederic Lardinois 写道，这种对其他第三方云竞争对手的整合仍然“非常不寻常”，他指出，他不“认为我们会看到 AWS 和 Azure 用类似的工具做出反应，但如果他们这样做，这对他们的客户来说是一件好事。”除此之外，Anthos 还将包括“30 多个硬件、软件和系统集成合作伙伴的扩展生态系统，包括思科、戴尔、EMC、HPE、VMware、英特尔、戴尔、联想、ATOS 和德勤。”

*   **Google Cloud Run:** 现在，我们开始讨论本周公告的核心内容，Google 的无服务器计算堆栈的最新成员 [Cloud Run，它表示它旨在提供“无服务器带来的便捷性和速度，或者容器带来的灵活性和便携性。”Cloud Run 处于测试阶段，它让开发人员专注于编写代码，而无需担心底层基础设施。基于 Knative，一个开放的 API 和运行时环境，让您可以在您选择的任何地方运行您的无服务器工作负载，云可以在“您选择的任何地方运行无服务器工作负载”，并“负责所有基础架构管理，包括供应、配置、扩展和管理服务器。”云运行可在 GCP、GKE 集群或本地 Kubernetes 上完全管理，并可在两者之间移动。此外，谷歌还宣布了对云功能和 App Engine 中第二代运行时的新投资，包括新的语言运行时支持，如通用版本中的 Node.js 8、Python 3.7 和 Go 1.11，测试版中的 Node.js 10alpha 中的 Java 8 和 Go 1.12。](https://cloud.google.com/blog/products/serverless/announcing-cloud-run-the-newest-member-of-our-serverless-compute-stack)

[https://www.youtube.com/embed/gx8VTa1c8DA?feature=oembed](https://www.youtube.com/embed/gx8VTa1c8DA?feature=oembed)

视频

*   **云代码和云构建 FTW:** 通读[关于黑客新闻](https://news.ycombinator.com/item?id=19626940)的评论，你会看到许多关于试图锁定供应商的评论，并关注谷歌[为开源微软 IDE](https://news.ycombinator.com/item?id=19618649) 发布闭源插件的事实。尽管如此，[谷歌的云代码](https://cloud.google.com/blog/products/devops-sre/announcing-cloud-code-accelerating-cloud-native-application-development)对于开发云原生应用的开发者来说，听起来是一个有趣的工具。该工具是微软 Visual Studio 代码和 JetBeans IntelliJ IDEs 的一个插件，它“在开发人员构建项目时为他们的项目提供本地、持续的反馈，扩展这个本地编辑-编译-调试循环，以在他们的本地工作站或云中创建云原生的 Kubernetes 环境”，在幕后使用[ska fold](https://github.com/GoogleContainerTools/skaffold)、 [Jib](https://github.com/GoogleContainerTools/jib) 和 [Kubectl](https://kubernetes.io/docs/reference/kubectl/overview/) 。云代码还可以轻松集成到众多的 Google APIs(存在锁定)和 DevOps 工具和服务，例如[云构建](https://cloud.google.com/cloud-build/)和 [Stackdriver](https://cloud.google.com/stackdriver/) 。“例如，”公告写道，“一旦您的代码准备好部署，只需执行一个拉请求或提交，这将触发云构建自动构建、测试和部署您的应用程序。”另一个工具是 IntelliJ 的集成库管理器，它自动添加所需的依赖项，启用 API，并管理所需的机密。除此之外，云代码和云构建可以协同工作来编辑、审查、测试和更改 Kubernetes yaml 文件，内置模板、林挺和错误突出显示，以及从您的 IDE 查看应用程序日志的能力。最后，您可以“定义不同的部署目标，比如本地开发、共享开发、测试或生产，这样您就可以在您的工作站或云中轻松地进行测试和调试。”

[https://www.youtube.com/embed/Ns0fHKuv7_Y?feature=oembed](https://www.youtube.com/embed/Ns0fHKuv7_Y?feature=oembed)

视频

*   **当然还有……人工智能和机器学习:**如果没有必备的人工智能和人工智能新闻，这些天还会有什么好消息发布呢？虽然一些新工具是专门针对整个企业的，但谷歌写道，它正在[扩展其平台，使开发者更容易构建和部署人工智能](https://cloud.google.com/blog/products/ai-machine-learning/expanding-google-cloud-ai-to-make-it-easier-for-developers-to-build-and-deploy-ai)。第一个公告是测试版的[人工智能平台](https://cloud.google.com/ai-platform/)，这是一个“全面的端到端开发平台，通过相同的共享界面帮助团队准备、构建、运行和管理 ML 项目”，模型共享、培训和工作负载扩展都是从云控制台管理的——当然，像其他工具一样，它旨在在混合环境中工作，而不仅仅是在公共云中。谷歌还宣布了对[云 AutoML](https://cloud.google.com/automl/) 的一些更新，包括 AutoML 表格、AutoML 视觉和 AutoML 视频，以使企业更容易构建和部署他们自己的定制 ML 模型。
*   **让我们用手机说出来:**谷歌新闻的最后一点，尽管我甚至不确定这是否是 Next 的一部分，因为该公司宣布 [ML Kit 扩展到具有语言识别和智能回复的 NLP](http://android-developers.googleblog.com/2019/04/ml-kit-expands-into-nlp-with-language.html)。我已经在想，有多少我的短信对话实际上是两个人工智能设备在互相做动作，现在，我们将通过[语言识别](https://firebase.google.com/docs/ml-kit/identify-languages)和[智能回复](https://firebase.google.com/docs/ml-kit/generate-smart-replies)在我们所有的短信应用中向这一现实迈进一步。基本上，这些工具能够确定你在用什么语言写作，然后向任何应用程序提供“智能回复”，而不仅仅是谷歌的应用程序。新的智能回复 API 是一种无状态 API，运行在设备上，并根据对话中的最后 10 条消息提供建议的回复，尽管如果只有一条先前的消息可用，它仍然可以工作。谷歌确实指出，至少它试图保持适当，因为它“增加了一个检测敏感话题的模型，以便我们避免在回应亵渎或个人悲剧/困难的情况下提出建议。”目前，“ML Kit 可以识别 110 种不同语言的文本，通常只需要几个词就可以做出准确的判断。”

亚历克斯·威廉姆斯的特写图片。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>