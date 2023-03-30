# 码头工人餐叉:现在，关于分手的讨论已经摆上了桌面

> 原文：<https://thenewstack.io/docker-fork-talk-split-now-table/>

几个 Docker 生态系统供应商和最终用户正在讨论从 Docker 中分离出来。这些公司的技术专家对 Docker 对 Docker 引擎的管理表示失望，他们正在探索解决支持企业 Docker 部署的各种问题的方法。

几个选项正在考虑中，包括完全分叉开源 Docker 引擎的可能性。据一些接近最近讨论的消息人士称，代表们来自红帽、谷歌、CoreOS、华为等公司和两家大型终端用户客户。

Red Hat 和 CoreOS 的发言人否认了任何与 Docker 相关的谈话。Docker 拒绝公开置评。谷歌和华为尚未回复置评请求。

对于[容器生态系统](https://thenewstack.io/ebookseries/)来说，这是一个开创性的时刻。这些公司的技术专家都不想分叉，但他们也表达了对 Docker 代码库缺乏稳定性的担忧，这在构建附加服务和支持生产中依赖 Docker 的客户时可能会有问题。

话说回来，许多参与谈判的公司也在使用容器来构建大规模分布式系统，并可能将 Docker 最近推出的内置编排功能视为对他们自己的编排产品的威胁，这些产品几乎都基于 Google 的 Kubernetes。

黑客新闻[的一位观察者指出](https://news.ycombinator.com/item?id=12366065)“现在发生的事情，如果我们不小心的话，将会分裂容器生态系统，并且使得单个容器不可能针对多个运行时。

## 企业问题？

我们从 Docker 生态系统中听到的一个担忧是，Docker 激进的发布时间表如何使第三方系统提供商与其自己的客户群发生冲突。

“Docker 一贯破坏后端兼容性，”[罗伯·希施菲尔德](https://twitter.com/zehicle)—[RackN](https://rackn.com/)的首席执行官，Kubernetes 社区领袖(和[偶尔的 TNS 贡献者](https://thenewstack.io/author/rob_hirschfeld/))说，他没有参与会谈。RackN 的应用生命周期管理平台使用并供应 Docker 组件，因此对后端的更改会对支持客户产生业务影响。

希施菲尔德指责道:“Docker 把它的 Docker 引擎作为一种产品，而不是一个社区用来构建自己服务的组件。”。这种基于产品的方法意味着，当 Docker 推出新的创新或将 Swarm 等组件合并到 Docker 引擎中时，运营商被迫修复后端兼容性。

“虽然我们使用这些功能，但这些变化会导致稳定性、版本、迁移和后端兼容性方面的问题，”希施菲尔德说。

直到上周，关于对 Docker 不满的谈话基本上都是私下进行的。但现在，这种讨论正在进入公共论坛，谷歌宣传 Kubernetes 的负责人 Craig McLuckie 的推文就是例证:

随着 Docker 公司的[最近将 Docker Swarm 的](https://thenewstack.io/docker-engine-1-12-will-come-built-orchestration-capabilities/)包含在 Docker 1.12 中，长期酝酿的挫折感达到了顶点。通过 Swarm，Docker Engine 允许用户管理复杂的容器化应用程序，而无需额外的软件，使用与开发人员熟悉的 Docker 容器相同的命令行结构和语法。Docker 编排功能是可选的；它们[必须由用户激活](https://blog.docker.com/2016/06/docker-1-12-built-in-orchestration/)。尽管不选择可能会导致向后兼容问题。

以前，这些编排功能，正如他们所知，只通过第三方工具提供，如 Kubernetes，Google 开源的编排平台。

虽然谷歌不直接销售企业容器编排软件，但它的开源编排器确实为容器提供了一个到谷歌云平台的简单入口。其他公司，如 CoreOS 和 Apprenda，也提供商业支持版本的 Kubernetes。华为还推出了基于 Kubernetes 的容器引擎。

因此，毫不奇怪，所有这些方面都渴望将对话从容器转移到容器编排。

领导该公司 Kubernetes 项目的三星 SDS 云工程师 Bob Wise 也呼吁 Docker 放缓容器创新的步伐。三星电子[正在收购](https://www.joyent.com/blog/samsung-acquires-joyent-a-ctos-perspective) Joyent，后者提供基于云的容器支持服务。

“如果你的团队在 Kubernetes、Mesos 或 Cloud Foundry 中深入工作，你需要一个稳定、简单、乏味的容器实现，具有最少的基本特征，以及围绕图像创建、命名和发布的社区协议，”Wise [在上周的一篇博客文章中写道。“你需要使用其他人都在使用的同样简单、乏味的容器实现。作为一个社区，我们需要减缓基本构件的变化速度。稳定性将允许构建在其上的系统蓬勃发展。”](https://medium.com/@bob_48171/an-ode-to-boring-creating-open-and-stable-container-world-4a7a39971443#.gux8c0bx2)

同样，Apcera 技术产品经理菲利普·特里布尔[在个人博客文章](http://www.linux-toys.com/?p=684)中以尽可能外交的方式表示 Docker 不要将新推出的功能宣传为企业就绪的成品。特里布尔写道:“在互联网和会议上大肆宣传令人兴奋的新功能，但这些功能并不像展示的那样有效，这是不明智的。”

Apcera 的商业模式部分基于其对 T4 码头集装箱公司的支持。

特里布尔的帖子激励其他人在黑客新闻上表达他们自己对 Docker 的体验，包括一些对新发布的 bug 的哀叹。一位读者谈到，每天生产 70，000 到 90，000 个集装箱，由于“各种各样的码头工人错误”，其中约有 9%遇到了麻烦在最近一次更新后，这一数字已降至 4%。

但其他人则称赞该软件的稳定性。“我们在生产中使用 Docker 已经有 3 年了，没有遇到任何大问题，”另一位读者评论道。"它是一些很酷的 Linux 内核特性的简洁包装."

事实上，Docker 确实有一大批支持者，他们认为 Docker 的软件是稳定的。Docker 的工程师也很快夸耀公司的坚实基础。

无论如何，Docker 似乎无意为了其潜在的竞争对手而扼杀自己的创新，正如最近 Google Kubernetes 布道者 [Kelsey Hightower](https://twitter.com/kelseyhightower) 和 Docker 首席技术官 [Solomon Hykes](https://twitter.com/solomonstre) 之间关于开放容器倡议(OCI)的映像和运行时标准在基于 Docker 的容器栈标准化中应该扮演的角色的 Twitter 争端[所示。](https://thenewstack.io/container-format-dispute-twitter-shows-disparities-docker-community/)

OCI 的成立正是为了提供像怀斯这样的人所呼吁的:无聊的标准化容器技术。

然而，Hykes 对 OCI 对第三方提供商的有用程度表示怀疑。Hykes 指出，那些声称在没有 Docker 守护进程的情况下(大概是通过 [runC](https://thenewstack.io/ready-docker-containers-runc-runtime-riddler/) 运行时引擎)提供 Docker 容器完全支持的提供商实际上只提供了大约 90%的 Docker 特性的“伪支持”。

“我只知道 Docker 动作很快，结果声称‘Docker 支持’的产品都在撒谎，”Hykes 写道。在另一条推文中，Hykes 甚至将 OCI 图像格式斥为“假标准”

Docker 公司对 Docker 商标的持有进一步加剧了这一问题。该商标意味着，如果公司使用未经 Docker 社区批准的补丁、代码或软件包，他们可能会面临责任。在这种情况下，一家公司可能无法支持自己的客户，因为补丁没有得到 Docker 的批准或上游到项目中。

结果是:第三方供应商被迫接受 Docker 做出的关于开源项目的任何决定，并在出现问题时等待 Docker 的补丁。最好的结果是与 Docker 达成某种协议，以保证稳定发布。

争论的焦点还在于哪些特性应该由 Docker 实现，哪些应该由底层操作系统或堆栈中的另一个组件来处理。

另一家依赖 Docker，但也与 Docker 竞争的公司是 Red Hat。在今年的一些会议上，包括 LinuxCon North America 2016，Red Hat 工程师 [Dan Walsh](https://twitter.com/rhatdan) 将 Red Hat 描述为被困在其客户越来越多地使用 [systemd](https://www.freedesktop.org/wiki/Software/systemd/) 来初始化 Linux 系统，而 Docker 的[似乎不愿意](https://lwn.net/Articles/676938/)与 systemd 合作，而是依赖其自己的 Docker 守护进程来提供关于初始化、服务激活、安全性和容器日志的功能。

“在过去的三年里，我们一直试图在 systemd 和 Docker 之间实现良好的整合，我发现这两项工作的两位领导人都非常固执己见，”沃尔什说，他指的是 Hykes 和 systemd 的创造者——也是目前的红帽员工——Lennart poet ering。

"那么，当我打开机器时，谁打开系统服务，systemd 还是 Docker？"沃尔什问道。一个实现糟糕的系统可能会让 systemd 和 Docker 守护进程互相争斗。

对于它的客户，Red Hat [维护着](http://www.projectatomic.io/blog/2016/08/docker-patches/)它自己的 Docker 分叉版本，其中包括 Docker 可能有一天会包含或者可能永远不会选择包含的补丁。

## 桌面上的选项

时间会证明这些非正式会谈是否会带来更协调的努力。有可能适合各方的选择。例如，可能存在通过 OCI 管理的 Docker 图像格式和运行时的稳定版本。这将允许生态系统合作伙伴拥有稳定的组件，并允许 Docker 继续使用自己的 Docker 引擎。在这种情况下，OCI 运行时将是 Docker 的一个分支。

但如果生态系统公司希望与 Docker 彻底决裂，那么这将意味着一个名称不同的完整分支，需要一个新的团队来管理这一切。例如，[的 CoreOS 提供了一种替代的“无后台”容器技术](https://thenewstack.io/coreos-container-runtime-rkt-reaches-1-0/)，称为 rkt，尽管它还没有明显的市场吸引力，至少没有达到 Docker 的成功水平。

这是一个全新的领域，标志着市场成熟的速度和赌注。从政治和经济的角度探索容器生态系统对于帮助更好地理解社区的技术方向是很重要的。面对 Docker 和容器生态系统之间的深刻分歧，以及正在进行的关于分叉 Docker 的积极讨论，或者，如果没有其他事情，创建一个稳定的替代方案，允许建立一个标准核心，并确保最终用户的稳定性，这无疑是正确的。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>