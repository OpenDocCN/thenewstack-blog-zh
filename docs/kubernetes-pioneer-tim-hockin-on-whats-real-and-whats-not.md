# Kubernetes 先驱蒂姆·霍金谈什么是真实的，什么不是

> 原文：<https://thenewstack.io/kubernetes-pioneer-tim-hockin-on-whats-real-and-whats-not/>

[旗语](https://semaphoreci.com/)赞助本帖。

[Tim Hockin](https://twitter.com/thockin) ，Kubernetes 的创始人之一，是一名由艺术家转行的工程师。[Semaphore 的客户营销经理 Wojtek cichoú](https://twitter.com/wojtekidd)与 Hockin 谈论了 Kubernetes 在 2018 年的状态，该项目的过去和未来以及围绕它的嗡嗡声。

在你的主页上，你将自己描述为“一名系统软件工程师，他编写大多数人看不到的软件”。当看到 Kubernetes 的成功及其曝光率时，很难相信这一点。哪里出了问题？怎么会有那么多人看到“你的项目？”它成功的关键是什么？

 [沃伊泰克·奇乔

沃伊泰克正在 Semaphore 把营销和客户关系联系起来。在职业上，他喜欢与现代技术的创造者和动摇者密切合作。在业余时间，他写并表演口语诗。](https://semaphoreci.com/) 

我认为它成功的关键在于它解决了真实的人所面临的真实问题。有很多项目试图改变人们的工作方式或思考方式。Kubernetes 直接来自于我们在 Google 创建 Borg 的真实经历。我们已经用了 14 年，效果非常好。我突然意识到“有一天我会离开谷歌，当我离开时，我会做什么？没有这些工具，我将如何生存？”

Kubernetes 成功的原因是因为人们看着它，直到他们看到它做事情，他们才明白为什么需要它。然后他们说“哦，我的上帝，我需要它！”我不知道我在持怀疑态度的观众面前做了多少演讲和展示，他们不明白这是为了什么。仅仅通过显示像“让我们做一个滚动更新”这样简短的特性，我就能看到发生了什么。我中途停下来，然后倒回去，他们说“这就是我用手做的。这比你刚才做的要耗费我一吨多的精力。”所以我认为它抓住了人们真正想要的东西。

我还要补充一点，从大的方面来看，Kubernetes 真的没有被很多人看到。它不会也永远不会像安卓、Chrome 或谷歌地图那样显而易见。它仍然是“大多数人看不到的软件”

**您提到了博格，我想知道博格和库伯内特斯之间有什么关联。我怀疑它是 1 比 1。**

它来源于相同的思想和相同的模式，但是 Borg 是数百万行非常谷歌特有的代码。它有成千上万的功能，除了谷歌没人会用。

在 Kubernetes 变得如此流行之前，就有一场名为“人人共享谷歌基础设施”的运动。你认为你在 Google 基础设施中使用的一些工具可以开源并添加到现代 DevOps 工具中吗？

我希望如此。我们在提高开发人员生产力的工具、编译器工具、分布式构建和自动测试方面进行了大量投资。已经有一些关于 Forge 如何工作的博客文章和论文，这是我们的分布式构建系统。我们有一些你可能想不到的小事情，比如测试日志收集。每次我通过我们的测试系统运行测试时，日志都会被捕获并存储在某个地方。然后我回去，看着他们，意识到他们是巨人。

我们有一些非常棒的代码审查工具，它们集成了静态分析。谷歌员工可以添加插件，说明“我想在我的代码库上做这类事情的分析。”你把这些东西放进去，当有人给你发送代码变更时，它会根据他们的变更运行你的分析器。很棒的东西。

我们已经有了这些实时调试工具，它们可以在测试运行中捕捉踪迹。如果测试失败了，你实际上可以返回并单步执行测试，找出发生了什么和为什么。所有这些都是自动发生的。你不必说“我所有的测试都失败了。让我在调试器中运行它。”您只是自动捕获了它，因为保存数据的成本要低得多。

因此，这是我认为谷歌基础设施可以继续帮助影响世界的一个领域。我们还有很多其他的东西——内部存储系统和其他一些东西。Bigtable 和 Spanner 都是 Google 云产品。这些都是非常棒的工具，它们真正改变了我们内部的工作方式。我认为我们越来越擅长发布我们所做的事情。

**你提到 Kubernetes 实际上是在帮助人们做他们所做的事情，但这并不神秘，它有一个陡峭的学习曲线。它很复杂，跨越了软件开发和维护领域的各种主题。在一次采访中，你提到了该项目的最初使命是“提供多元生态系统的枢纽”K8s 最初是为了最大限度地减少运行和扩展的人力，但与此同时，项目本身也增加了复杂性。你能详细说明一下吗？它给生命带来的新生态系统有尽头吗？**

我希望这些“后续生态系统”都是可选的，如果它实际上没有带来任何好处，就不应该强迫任何人采用。Istio 就是一个很好的例子——Kubernetes 是一个应用管理平台，它出于需要进行联网，因为应用是联网的。但是 Kubernetes 试图成为终极网络抽象是没有意义的。它不可能是完美的服务发现，因为没有完美这样的东西。有上百种服务发现应用程序。它不可能是完美的负载平衡器，也不可能是完美的流量路由器，等等。

这些事情是复杂的服务，我们一直试图保持 Kubernetes 相对简单的核心。在这个过程的早期，我们创建了这个文档“什么是 Kubernetes”我们在那里定义了我们认为是什么，我们的泳道是什么，我们在做什么，我们不打算做什么。我们已经定义了 Kubernetes 盒子有多大，以及它之外的其他东西是怎样的。

网络在盒子里，但只有一点点。我们需要保持足够的量以保证工作正常进行。然后你看看人们真正需要的是什么。对于像第 7 层 HTTP 负载平衡器这样的东西，去阅读 Nginx 或 Envoy 或 HAProxy 的规范。他们有成百上千的特定于他们的实现的特性，并且他们彼此都不相同。

Kubernetes 不可能实现所有这些东西——我们将永远处于竞争之中。这不是我们想要的，我们不想与这些公司和项目竞争。我们不想对这些东西进行抽象，因为抽象会丢失信息、细节和对底层系统的访问。我们决定，我们的泳道是我们能够帮助基本用户做基本事情的最低限度。我们唯一拥有的是入口 API。这是一个非常简单的 HTTP API，简单到令人不满意的程度。几乎每个使用 Ingress 的人最终都会对他们的 Ingress 实现做一些事情，因为他们需要额外的特性。

这里，Istio 走过来说“我们要解决网络的问题！”它们不是容器管理系统。他们使用集装箱管理系统。他们和 Kubernetes 一起工作。它们是一个网络应用程序，像 Kubernetes 有 100 个集装箱管理功能，Istio 有 100 个交通管理功能。如果你不想用 Istio，如果它没有给你带来任何价值，你可以不用它。但对很多人来说，它确实带来了增值。您可以从一个简单的 API 开始，然后进入一个更详细、更健壮和更高级的 API。它带来了伴随价值而来的复杂性。复杂性需要证明自己，因为复杂性本身就是癌症。

我有点难过 Kubernetes 现在有多复杂。从某种意义上说，Kubernetes 不是为最终用户服务的，而是为建立集群的人服务的，而集群是为最终用户服务的。在 Google，我们总是将集群管理中涉及的角色分成两个非常具体的角色:集群操作员和应用程序操作员。

集群操作员了解 Borg 的一切，他们对运行在 Borg 上的每个应用程序都有所了解，但不是细节。他们能够保持 Borg 集群正常运行，并有相关的 SLA 等等。应用团队(如谷歌搜索或 Gmail)进来后说“我知道如何使用 Borg，但我不知道 Borg 如何运行，我也不需要。”他们进来，在 Borg 上运行他们的应用程序，这种分离给了人们一种非常好的专注能力。Kubernetes 真正针对的是那些集群运营商。

事实是，今天许多公司和组织都是集这两种角色于一身。很难找到合适的资源，所以他们有这种复杂性。不幸的是，网络和安全是很难的，它们是 Kubernetes 复杂性的一大来源。这些是在 Kubernetes 建立公司最困难的部分，因为它们仍然是我们整个行业中最困难的部分。

作为发起人之一，你对 Kubernetes 的发展方向和面临的最大问题有一个大致的了解。能否给我们一个关于 2018 年库伯内特斯状态的“开国元勋总结”？

因此，2018 年即将结束，我认为我们实际上已经做了一件体面的工作，回应了一些关于很难在 Kubernetes 建立某些东西的投诉。它大大简化了集群设置(不容易，但是更容易)。在那里我们还可以做更多的事情。

我认为 Kubernetes 开始进入一个稍微稳定一点的地方。我们再也看不到太多的主要特性了。这个系统的开发越来越多地转向插件和核心之外的东西。即使您查看 GitHub kubernetes/kubernetes repo 的提交数量图表，您也可以看到这一点。这是一件好事，因为越来越多的项目正在脱离核心回购。总的来说，这很好。

与此同时，社区在成长，Slack 在成长，参与和客户的数量也在大幅增长。这些对我来说是非常健康的信号。

我们仍然有太多的错误和太多的 PRs 打开。开发者体验过程仍在进行中。代码审查过程和设计过程仍在迭代中。今年真的很成功。回顾一年之初，1.8 版本感觉很原始。我们正在关闭越来越多的愿望列表，并进一步降低重要功能的列表。

**你认为理想的状态(如果软件世界有这种东西)是项目保持稳定吗？也就是说，没有大的变化发生，它只是工作，唯一要做的就是添加插件？**

是的，那太好了。它是软件，所以没有什么是真正永恒的。我们会不断更新安全之类的东西，总会有一些新功能和新东西出现。但是事情的变化速度(特别是那些对用户有影响的事情，比如 API 变化或者功能变化)肯定会慢下来，为了这个项目，他们不得不慢下来。

越来越多的东西要在后续的生态系统里。我不想做大量新的面向 HTTP 的工作。我希望它能登陆其他系统，如 Istio 和其他服务网络，如 Conduit。他们比我更擅长交际。我们把各种扩展机制放在一起，让人们做越来越多的非二等的事情。

**Kubernetes 的使命是减轻开发人员和 DevOps 专业人员在升级和维护软件方面的痛苦——这一切都与可靠性和正常运行时间有关。持续集成和部署也涉及相同的主题，但是在更接近源代码和测试的层次上。K8s 和 CI/CD 之间有没有共同的空间需要未来解决？**

所以这是我认为 Kubernetes 本身不应该去的地方之一。我认为 CI/CD 是人们希望使用 Kubernetes 这样的系统的最重要的事情，但我不认为 Kubernetes 应该试图成为一个 CI/CD 系统。有商业产品，有开源产品，有以云为中心的产品，我认为这些专家应该专注于如何做 CI/CD。

有趣的问题是，Kubernetes 可以做些什么来使其更容易从 CI/CD 中消费。无论是更多触发器、更多基于推送的解决方案还是 GitOps 工作流流程，这些问题都很有趣。如果有人提交了一个补丁来添加 CI/CD 到 Kubernetes API，我会尽我所能关闭它。我觉得这说不通。但我当然希望 Kubernetes 在这方面有用。我们从人们那里听到的第一件事是“这看起来很酷，我可以用它运行我的构建吗？”。我们可以做得更好，让这变得容易和可能。我认为我们在这方面做了很多改进。一个很好的例子就是在没有 Docker 的情况下构建 Docker 的能力。这种事情很重要。

**在一次采访中，你说过“人们不想在一匹新马身上下注”，我猜这是 Kubernetes 早期的做法。为了说服决策者和高级开发人员使用这个项目，并使它成为 GitHub 上最繁忙的社区之一，已经付出了很多努力。你认为真正促使人们采用 K8s 的原因是什么，尽管它很复杂，很独特？**

Kubernetes 最受我们的关注，它向人们展示了如何做古老的事情。我们尽量不拘泥于学术。我们试着不去理论化该做什么和想什么。例如，我们展示了如何对应用程序进行滚动更新，并在更新过程中出现问题时回滚。这是 DevOps 人员每天都在做的事情，而且并不总是自动化的。有了 Kubernetes，你可以让一切变得更简单。您可以围绕一致的 API 和一致的工具实现自动化，因此您可以更有信心地更频繁地这样做。这正是我们从许多人那里听到的问题，这就是为什么他们现在谈论 Kubernetes 的采用。他们说“我从一天一条推变成了 20 条推”，我认为这些是最受关注的事情。

第一个 KubeCon 不到 1000 人，现在我们看到 6500 人。但重要的是，我们将始终放入演示。我早期的很多演示都只是演示，比如“让我向你展示我可以用 Kubernetes 做的 10 件事”。这些都是吸引人们注意力的东西。我记得我在 USENIX 丽萨为系统管理员做过一次演讲，演讲结束后，人们走过来说，“这是我的工作，你刚刚自动化了我的工作。”我对此感到有点遗憾，但同时我希望这能让他们腾出时间去做其他事情和工作。

Kubernetes 的所作所为不言而喻。它允许人们快速获取和部署代码，无论你是首席执行官还是开发人员，你都会看到其中的巨大价值。

Kubernetes 现在是一个前沿技术关键词。它主导着所谓的“DevOps 行业”。事实上，这个项目太酷了，当我看到[非代码贡献者指南](https://kubernetes.io/blog/2018/10/04/introducing-the-non-code-contributors-guide/)时，我很兴奋，我可能会有所帮助(甚至在就这个主题进行适当的自我教育之前)。我甚至看到了一篇在社区中引起一些共鸣的文章，标题是[“你可能不需要 Kubernetes。](https://blog.jessfraz.com/post/you-might-not-need-k8s/)围绕这个项目的大肆宣传有什么好处吗？还是它制造了太多的噪音，转移了项目最初的关注点？

有很多噪音，任何时候有一件成功的事情，涉及到金钱，就有很多人试图将信息转移回他们自己，他们的产品或如何在这件事情上赚钱。当我们回顾 KubeCon 的谈判时，我们被告知的一件事是确保谈判不是供应商的推销。我们不希望人们推销他们的产品。我最终拒绝提案的一个主要原因是，“这只是一个推销，一家公司在向我展示他们的产品”，这不是人们在这样的会议上想看到的。我不认为噪音本身是不好的。我们的意识越强，项目就越顺利。

显然，我非常关心 Kubernetes 的成功和长寿。我看到，当人们现在进来时，他们带着更高的期望进来。随着门槛越来越高，人们开始接受你可以自动做某些事情，他们正在寻找下一步。现在有了 Kubernetes，也有半打其他系统可以用同样的方式做事情。当然，他们做出不同的权衡。人们带着不同层次的期望而来，但我不认为这降低了社区的价值。

《非代码贡献者指南》之所以在那里，是因为我们有很多在使用 Kubernetes 的公司工作的人，或者对该技术感兴趣的人，他们说“我不是真正的开发人员，但这是有趣和令人信服的东西。有什么可以帮你的吗？”非编码人员可以做上百件事情来做出贡献。

**我看到你和你的同事将在西雅图即将举行的 KubeCon 上发表主题演讲，题目是[“你从未听说过的关于 Kubernetes 起源的故事”](https://sched.co/GswX)你能为这次采访分享一个有趣的事实吗，这会鼓励读者在 12 月来到西雅图？**

我不想透露太多我们将要谈论的内容，但是已经发生了很多事情，特别是在早期，这些事情令人惊讶，并且使项目朝着与我预期不同的方向发展。

我们最早的客户会议之一是与来自雅虎、Box 和易贝等不同公司的一群代表举行的，他们来与我们交谈。他们想看看库伯内特到底是怎么回事。他们来到我们的谷歌办公室，我们给了他们一个演示，向他们展示了我们的产品。我认为每个人都很怀疑。特别是有几个人，对我们提出了非常非常难的问题。他们显然已经做了功课。我们没有很好的答案来回答所有的问题，因为时间还早。

在这一轮提问之后，Box 的 Sam Ghods(创始人之一，系统专家)说“我喜欢。我加入。”对我来说，这是一个很大的肯定。这是一个建立了一个成功的公司来解决系统难题的人，他看到了我们正在做的事情并加入进来。Sam 重写了我们的命令行工具，并对项目产生了真正有意义的影响。我们从未预料到这一点，但正是这一点让这个项目获得了成功。

我们有大量这些非常有趣和独特的个人贡献者故事，这些故事非常鼓舞人心。希望我们能够在 KubeCon 的主题演讲中触及其中的一些。

我是个细心的读者，我在你的主页上注意到你辅修美术！你是业余画家，画大尺寸方向盘吗？

当我高中毕业的时候，我得到了我的第一台电脑。在那之前，我是一名画家，整个高中我都在学习绘画和雕塑。我上大学想成为一名画家，我的父母试图说服我不要这样做。我的父亲是一名工程师，我的哥哥是一名机电工程师，我的妈妈一直告诉我“你为什么不去当一名工程师，你可以兼职画画。”我说“不，我想成为一名艺术家和老师(我在高中有一个非常有影响力的艺术老师)。”于是我就在美术专业读了美术与教育双学位。然后我得到了一台电脑作为毕业礼物。我开始玩它，并意识到它是多么有趣。我的一个朋友上了 C 编程课，所以我也上了，很容易。它刚刚和我说话了。我全都明白了。我意识到我真的很喜欢这样做，我想做更多这样的事情。我上了更多的课，最终从艺术专业转到了计算机专业。

下班后我不怎么画画，因为这需要更多的时间和空间，很难满足。雕塑更是如此。但是我确实画了很多，而且我现在在我们的办公室以在便利贴上涂鸦而出名，尤其是在开会的时候。就像我大脑的屏保一样。甚至有一个流传甚广的笑话说，如果蒂姆在画画，那就意味着他在专心听讲。

涂鸦不完全等同于绘画，但它是一种创造性的发泄方式。事实是，写代码满足了绘画一样的渴望——创造性表达的需要。我现在写的代码不像几年前那么多了，但是当我写的时候，我会因为自己做了一些有创造性的事情而感到同样的自豪。

*本次采访由 Semaphore 为您带来，这是一个 CI/CD 平台，刚刚在产品搜索上推出了全新的 [Semaphore 2.0。](https://www.producthunt.com/posts/semaphore-2-0)*

通过 Pixabay 的特征图像。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>