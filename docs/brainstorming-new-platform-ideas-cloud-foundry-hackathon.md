# 一个黑客马拉松团队可能已经发现了“无服务器的正确做法”

> 原文：<https://thenewstack.io/brainstorming-new-platform-ideas-cloud-foundry-hackathon/>

[](https://www.cloudfoundry.org/)

[Childers](https://www.cloudfoundry.org/)

[Childers 在大规模计算和开源软件方面已经花费了超过 18 年的时间。2015 年，他成为云铸造基金会的联合创始人，担任技术参谋长。他是 Apache Cloudstack 的第一任副总裁，在 SunGard 领导企业云服务时，他帮助推动了该平台的发展，后来又在 Cumulogic 担任产品战略副总裁。在 SunGard 之前，他领导了包括 IRS.gov、USMint.gov、美林和 SEI Investments 在内的组织的任务关键型应用程序的重建工作。Chip 是 OSCON、LinuxCon North America、LC Japan、LC EU、ApacheCon、O ' Reilly Software Architecture Conference 等活动的资深演讲者。在空闲时间，奇普喜欢带着他的黑色实验室徒步旅行，驾驶双体船和太阳鱼，并试图跟上他年轻的女儿。](https://www.cloudfoundry.org/)

[](https://www.cloudfoundry.org/)[](https://www.cloudfoundry.org/)

平台开发人员的一天通常包括倾听用户的需求和客户的问题，然后编写代码和解决问题。假设这些开发人员有空闲时间去探索一些超越当前优先事项的新想法？

在我们的上一次 Cloud Foundry 峰会上，培训如期进行，用户聚集在社区日，从事 Cloud Foundry 平台及其相关工作的开发人员参加了一整天的黑客马拉松比赛。他们在自我选择的团队中一起工作，探索新的想法或花时间发明工具，使他们的生活更轻松。

对于我们在 [Cloud Foundry Foundation](https://www.cloudfoundry.org/) 的人来说，这是第一次冒险。

团队有 24 小时的时间来设计、制作原型和分享项目。最后，五个团队提交了项目。获胜者是一个由 Pivotal 和 IBM 开发人员组成的团队，他们自称为“热门话题”，他们想出了一种使用 Cloud Foundry 来托管“功能”(想想:无服务器)的方法，这些功能与传统上在系统中托管的长期运行的应用程序具有相同的功能。他们称他们的提交“CF 无服务器做得好。”

“PaaS 只是推动代码。“无服务器只是推动功能，”埃德·金在[对项目](https://teddyking.github.io/hottopic-release/)的评论中写道。正如 King 所解释的，这两个概念都是关于抽象的，让开发人员编写无状态的代码，平台可以使用这些代码来管理、扩展和编排。

但也有关键的区别:“应用程序只是由路线触发的无状态容器，并由 CF scale 扩展，”他写道。函数是一样的，但是由共享消息队列中的事件触发，并根据消息队列长度自动缩放。Hot Topic 是一个概念证明，它使用 CF **map-event** 命令，类似于 CF **map-route** 来使 FaaS 和 PaaS 以一种非常好、简单和正交的方式一起工作。

“就 **cf 推**。如果您想要一个网络应用程序，请使用 **cf 地图路线**。使用 **cf 地图事件**功能。相同的日志流、打包、编排、工作流，相同的服务绑定方式，所有这些都完全集成、简单且一致。”

获奖作品是一个事件驱动编程模型的优秀原型，融入了 Cloud Foundry 运行时。项目团队的另一名成员 Julz Friedman 在活动中做了一个很棒(也很有趣)的演讲，表达了他对团队核心项目主题的看法。

[https://www.youtube.com/embed/akwINZwftC0?feature=oembed](https://www.youtube.com/embed/akwINZwftC0?feature=oembed)

视频

当然，还有其他事件驱动的编程模型可以与 Cloud Foundry 协同工作或与之比肩。热门话题团队从深度整合的方法开始。然后，它建立在云铸造平台的基本抽象之上。最后，它让用户可以访问平台的整个语言、框架和支持服务的生态系统。该团队添加的唯一额外抽象是支持将“主题”绑定到已部署的应用程序。在后端，该项目使用自动缩放和消息队列，根据队列中的消息数量按需旋转应用实例。

## Cloud Foundry 采用无服务器技术

“无服务器”是[在](/category/serverless/)之前你已经在新的堆栈中看到的一个术语，在这个上下文中有一些额外的解释。在我们的领域中，无服务器的一个更好的术语可能是“事件驱动函数”与一个不断循环的 web 应用程序不同，它监听 HTTP 请求，为无服务器模型编写的代码只在有事件要处理时运行。无论是向上还是向下缩放，都会神奇地为您处理。

这是对微服务的不同看法，为应用程序开发人员提供了一种更简单地考虑事件驱动应用程序的方式。开发人员不必担心伸缩性，而是将注意力集中在编写应用程序上，这样她就可以将消息放入队列中进行处理。她不必实现一堆逻辑或者担心管道或交付。很简单，她编写了无服务器代码，只接受消息并管理它们的传递。

如果没有事件驱动的方法，就有更多的管道要担心。开发人员需要更加了解事件驱动的消息传递是如何工作的，并自己编写代码。它们直接与系统的消息队列进行交互，并编写逻辑在消息出现时提取消息。这是一种更复杂的方法，需要您自己进行扩展。

Hot Topic 的成功方法是实现事件驱动部署模型的一种很好的方式，但更好的是，你仍然只是 **cf push** 你的应用。

## 更多平台创新

黑客马拉松的第二名和第三名获胜者都创造了让[的波什](https://bosh.io/)作者工作更容易的工具。排名第二的是来自 [Engineer Better](http://www.engineerbetter.com/) 和 Pivotal 的 BCRaaS 团队，他们设计了一个省时的服务，在 AWS S3 桶中预编译 BOSH 版本。通常，BOSH 平台的编译过程需要花费大量的时间和精力。Team BCRaaS 的条目使人们更容易使用预编译的 BOSH 版本，而不是自己动手。

创作一个 BOSH 发行版需要一些努力，尤其是如果您试图重新打包其他已经打包用于 Linux 发行版的开源软件。第三，由 Pivotal 员工组成的团队 Debr 想出了一个方法来自动创建来自 Debian 包的 BOSH 版本。它使用了一些魔法来爬行依赖树，并将每个包的内容从一种格式映射到另一种格式。

黑客马拉松非常精彩，所有参与的团队似乎都玩得很开心。更好的是，伟大的想法被公之于众，甚至可以作为原型快速启动。我们期待着下一次黑客马拉松。

[Cloud Foundry](https://www.cloudfoundry.org/) 是新堆栈的赞助商。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>