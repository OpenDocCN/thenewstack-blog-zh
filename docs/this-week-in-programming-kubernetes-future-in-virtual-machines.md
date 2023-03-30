# 本周编程:Kubernetes 在虚拟机中的未来

> 原文：<https://thenewstack.io/this-week-in-programming-kubernetes-future-in-virtual-machines/>

上个月，在亚马逊的年度 AWS re:Invent 会议上，该公司公布了一项新技术，从表面上看，这项技术似乎是幽默的完美素材:微型虚拟机。当然，这个场景中的幽默来自于这样一个事实，虚拟机从 20 世纪 60 年代就以这样或那样的形式出现了。

https://twitter.com/wattersjames/status/1067309229541744640

Pivotal 产品高级副总裁 James Watters 在他的推特上完美地总结了这一点——我们拥有当今风靡一时的技术，而要颠覆它的技术是我们已经使用了几十年的技术。这条推文可能看起来像是在开玩笑，但看起来可能不是这样，因为本周围绕容器和 Kubernetes 的真正前进方向实际上是…虚拟机的想法爆发了一阵讨论。有趣的是，这个想法，就像它所谈到的技术一样，也不是全新的。(注意下面这条推文中的 2015 年时间戳。)

[Paul Czarkowski](https://www.linkedin.com/in/paul-czarkowski-2670a545) ，Docker 早期的容器爱好者，Pivotal 的同事，本周写了一篇文章，并广为流传，他大胆地宣称[Kubernetes 的未来是虚拟机](https://tech.paulcz.net/blog/future-of-kubernetes-is-virtual-machines/)——人们对此没有哄笑回应，而是表示同意，而且相当激烈。

“我是容器的忠实粉丝，我不会试图暗示[容器已死](https://chrisshort.net/docker-inc-is-dead/)。Docker 在 2013 年带给我们的是一个围绕 Linux 容器的包装器。他们向我们展示了构建、打包、共享和部署应用程序的惊人的新方法，”Czarkowski 写道。“还有一个棘手的问题有待解决，我相信这将成为容器的败笔……多租户。Linux 容器并不是被构建成安全的隔离沙箱(像 Solaris Zones 或 FreeBSD Jails)。相反，它们建立在共享内核模型的基础上，利用内核特性来提供基本的进程隔离。”

现在，如果你不同意虚拟机是未来发展方向的观点，也许可以看看 GitHub 工程师、前 Docker 核心维护者、自称“容器的 Keyser sze”[Jessie Frazelle](https://blog.jessfraz.com/)的 Twitter 帖子，他写道“Kubernetes 并没有考虑到安全性。这是事后的想法，因此，除非你在设计中构建自己的硬多租户，否则你将继续成为车轮中的仓鼠，汗流浃背。”

https://twitter.com/jessfraz/status/1078057723231641600

Frazelle 去年五月更深入地探讨了这个话题，她在 Kubernetes 的[博客上讨论了硬多租户。这种硬多租户理念背后的基本思想——以及 Czarkowski 和其他人认为 Kubernetes 缺乏的特性——是“租户不信任彼此，被认为是恶意的和不可信任的。硬多租户意味着同一集群中的多个租户不能访问其他租户的任何内容。在这个模型中，目标是让安全边界成为 Kubernetes 名称空间对象。这是一个有待解决的问题，这让我们回到了当前的建议，即虚拟机或其某种形式实际上可能是前进的方向…尽管事实上它们一直都在这里。](https://blog.jessfraz.com/post/hard-multi-tenancy-in-kubernetes/)

当然，如果你对所有血淋淋的技术细节感兴趣，请务必通读这两篇博文。可以说，Czarkowski 说，这并不新鲜。

“云提供商已经在朝着这个未来努力。通过观察开源社区中发生的事情，您可以看到这种情况的形成。(可以说亚马逊已经用 Fargate 不透明地做到了这一点)，”Czarkowski 总结道。“结合对 Kubernetes 硬租赁模式的正确改进，您将获得 Kubernetes 的圣杯。Kubernetes 工作负载的完全隔离和在 Kubernetes 上运行工作负载的纯每 Pod 消耗成本模型。”

因此，作为一名关注世界各地 Kubernetes 并宣布 2018 年为“Kubernetes 年”的开发人员，你可能会对自己说，“2019 年，我将解决整个 Kubernetes 的事情。”或者也许你只是对自己说，好像很多人都这么认为，“Kubernetes 实在是太他妈复杂了。”无论哪种方式，你都可能是幸运的——无论如何，你最终都可能坚持使用虚拟机！

对于其他人来说，仅仅是考虑在未来一年进行 web 开发，这里有一个很好的小视频，它提供了一个你需要做什么的快速指南:

[https://www.youtube.com/embed/UnTQVlqmDQ0?feature=oembed](https://www.youtube.com/embed/UnTQVlqmDQ0?feature=oembed)

视频

就本周的新闻而言，嗯，正如你可能想象的那样，真的没有任何新闻。但是，还是有一些我们认为值得分享的链接。所以我们开始吧。

## 本周的节目中

*   **GitLab ChatOps 开源:**git lab 背后的团队表示将会[在 GitLab 11.8 中](https://about.gitlab.com/2018/12/24/gitlab-chatops-will-become-available-to-everyone/)让每个人都可以使用 GitLab ChatOps。如果你不熟悉的话， [GitLab ChatOps](https://docs.gitlab.com/ee/ci/chatops/) 可以让你在一个频道中运行 chat 命令，让每个人都知道发生了什么。不幸的是，ChatOps 似乎从未像一些人希望的那样真正起飞，但 GitLab 现在正在开源该功能，“希望开源该功能将鼓励更多人使用 ChatOps 并为其做出更多贡献。”
*   **2018 年的 API:**本周，ProgrammableWeb 在一系列博客文章中总结了其点击、分享和谈论最多的 API。尽管 2018 年“对于 API 提供商或开发者来说并不是一帆风顺的一年[…] [API 设计](https://www.programmableweb.com/category/all/news?keyword=%22API%20Design%22&page=1)继续发展，这对 API 经济来说是一个好兆头。”他们写道，尽管在过去的一年中存在任何问题，但数字说明了一切。“如果添加到 ProgrammableWeb 目录中的 API、SDK 和示例源代码概要的数量能够表明 API 经济的健康状况，那么我们没有什么可担心的。2018 年的总数包括今年添加到我们目录中的 [1，776 个 API](https://www.programmableweb.com/category/all/apis?order=created&sort=desc)、 [3，381 个 SDK](https://www.programmableweb.com/category/all/sdk?order=created&sort=desc)和 [3，028 个示例源代码](https://www.programmableweb.com/category/all/sample-source-code?order=created&sort=desc)概要文件。”如果你对哪些特定类别领先感兴趣，请确保点击进入。
*   **开源的持续发展:**上周，我们看了一下围绕开源许可发展的热烈讨论。如果这个话题引起了你的兴趣，那么一定要读一读 Redmonk 创始人斯蒂芬·奥格雷迪的[开源循环理论](https://redmonk.com/sogrady/2018/12/21/cycles-oss/)。O'Grady 着眼于混合许可证的问题，他写道，它们并没有像之前预测的那样消失，而是似乎在翻倍。O'Grady 写道:“开源作为一种开发模式无疑会持续下去，因为它是所有其他已尝试过的模式中最不糟糕的模式，而且开发者授权的现象不太可能逆转。”。“但是，在一个对开源软件的商业需求受到专有云产品威胁的世界里，如果公共模式让位于私有模式，行业需求和对开源的支持肯定会放缓。”

Pivotal 是新堆栈的赞助商。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>