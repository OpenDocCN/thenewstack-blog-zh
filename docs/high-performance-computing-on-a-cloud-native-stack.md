# 基于云原生堆栈的高性能计算

> 原文：<https://thenewstack.io/high-performance-computing-on-a-cloud-native-stack/>

甲骨文公司赞助了这次播客。

[两个高性能计算项目如何在云原生上得到提升](https://thenewstack.simplecast.com/episodes/how-two-high-performance-computing-projects-got-a-boost-on-cloud-native)

建造一个模拟人类心脏的模型。汇集和处理来自世界各地的公共交通和其他来源的数据，以确定特定距离之间的旅行时间。这是两个项目[阿方索·圣地亚哥，](https://www.linkedin.com/in/alfonso-stg/?locale=en_US)巴塞罗纳超级计算中心的研究员和[查理·戴维斯](https://www.linkedin.com/in/charlie-davies-259b6b9/?originalSubdomain=uk)，联合创始人，技术和产品总监，[igeo Lise](https://www.traveltimeplatform.com/)；积极参与建设。它们的共同点是如何在云原生平台上获得巨大的高性能计算(HPC)工作负载。

Santiago 和 Davies 在巴塞罗那的 KubeCon + CloudNativeCon 期间，在由执行主编 [Joab Jackson](https://twitter.com/Joab_Jackson) 主持的 [The New Stack Makers](https://thenewstack.io/podcasts/makers) 播客中，分享了关于 HPC 如何帮助解决他们各自项目的许多困难的详细信息。在场的还有 [TJ Fontaine](https://www.linkedin.com/in/timothyjfontaine/) ，他是一名软件工程师，也是甲骨文公司技术人员的顾问，他提供了一些关于甲骨文在这些项目中的角色，以及总体上在云计算的高性能计算中的角色。

巴塞罗那超级计算中心模拟人类心脏的任务包括创建一个像真实人类心脏一样反应的模型。由此产生的模型在临床试验和医疗设备测试中有巨大的用途。圣地亚哥说，虽然这个概念很简单，但研究人员面临两个主要问题:组合模拟很难配置，因为实际上有数千个变量需要考虑；模拟的计算成本需要大约两个小时才能完成一次执行。

“不是每个人的办公室都有这种类型的资源，所以我们试图通过尝试民主化这种工具来解决 Oracle Cloud 的问题，并让没有这种工具的人也能使用它，”Santiago 说。

人类心脏模型通过巴塞罗那超级计算中心的前端 web 应用程序进行访问，在该应用程序中，执行以“非常临床友好的方式”进行配置，因此研究人员不必管理 HPC 考虑参数的数字复杂变量，只需输入他们想要测试的数据。

圣地亚哥说，在不久的将来，他的团队计划将该模型移植到 Kubernetes 平台上，以模拟多个心脏。“如果你需要运行 10，000 个不同的患者试验，你需要一个高效和智能的工作量管理器，”圣地亚哥说。

圣地亚哥说，由于不同容器的独立结构，Kubernetes 和容器结构也有助于为 HPC 驱动的人类心脏模拟增加冗余。例如，这种内置的冗余允许在单个节点故障的情况下执行数千个其他执行。

虽然戴维斯自嘲地说，他的项目“没有什么比复制人类心脏更令人着迷”，但他确实说，确定旅行者的旅行时间也需要 HPC 进行“一些相当繁重的计算和数据”。

戴维斯描述了 iGeolise 如何创建了一种按时间而不是按距离搜索地图数据和我们周围世界的方法。例如，在超过 35 个国家，用户可以使用该应用程序来确定他们可以在半小时内通过公共交通、驾驶、步行或骑自行车或所有这些方式的组合去哪里。这些数据集绝不是静态的，需要根据全球超过 35 个国家不同城市的不断变化的变量来计算行程时间。

考虑到 iGeolise 的人员非常短缺，Davies 表示，该公司的业务模式严重依赖于 HPC 提供的综合计算能力以及云和 Kubernetes 平台的多功能性。“在一个小本创业公司，我们不得不处理数据，并决定以这样一种方式刷新它，以便我们可以将它放回我们的运行时服务器，并让一切都可用，”戴维斯说。“我们(最初)运行的代码真的非常糟糕。”

戴维斯说，由于其基于 HPC 的应用程序运行在云上，iGeolise 平台现在可以在大约 8 小时内汇集和处理数据，现在一天可以处理几次，而不是等待两周以上。这实际上促成了商业模式。"

[https://www.youtube.com/embed/niuAVbESM4g?feature=oembed](https://www.youtube.com/embed/niuAVbESM4g?feature=oembed)

视频

### 在这个版本中:

[3:19:](https://thenewstack.simplecast.com/episodes/how-two-high-performance-computing-projects-got-a-boost-on-cloud-native?t=3:19) 过渡是什么样的，对 Oracle 云上的高性能计算有什么好处？
[5:26:](https://thenewstack.simplecast.com/episodes/how-two-high-performance-computing-projects-got-a-boost-on-cloud-native?t=5:26) 这是否涉及最初为 HPC 设计的软件？
[15:53:](https://thenewstack.simplecast.com/episodes/how-two-high-performance-computing-projects-got-a-boost-on-cloud-native?t=15:53)HPC 工作负载的民主化。
[20:55:](https://thenewstack.simplecast.com/episodes/how-two-high-performance-computing-projects-got-a-boost-on-cloud-native?t=20:55)HPC 风格作业的首选配置是什么？
[26:57:](https://thenewstack.simplecast.com/episodes/how-two-high-performance-computing-projects-got-a-boost-on-cloud-native?t=26:57) 让代码更高效，数据更高效，优化代码让内存更高效的平衡。
[31:27:](https://thenewstack.simplecast.com/episodes/how-two-high-performance-computing-projects-got-a-boost-on-cloud-native?t=31:27) 敏感数据的处理问题。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>