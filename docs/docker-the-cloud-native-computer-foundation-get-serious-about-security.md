# Docker，云本地计算机基金会认真对待安全问题

> 原文：<https://thenewstack.io/docker-the-cloud-native-computer-foundation-get-serious-about-security/>

云本地计算基金会(CNCF) 赞助了这篇文章。

[【CNCF】，码头工人说他们(甚至更)重视安全](https://thenewstack.simplecast.com/episodes/cncf-docker-say-they-are-even-more-serious-about-security)

显而易见，随着云原生漏洞和容器漏洞越来越受欢迎，它们正成为攻击者更具吸引力的目标。但最近，这两个平台上的一些安全漏洞引发了更大的担忧。

也就是说，最近披露了一个安全漏洞——在本文发布时还缺乏一个可靠的修补程序——详细说明了攻击者如何获得 Docker 容器主机的根访问权限。该漏洞在范围上类似于[符号链接竞争攻击](https://news.ycombinator.com/item?id=20031403)，SUSE 安全研究员揭示了当前漏洞如何适用于与 Docker 引擎相关联的任何主机。

今年早些时候，一个 [Docker 运行时漏洞](https://www.zdnet.com/article/doomsday-docker-security-hole-uncovered/)被揭露，暴露了 Docker、Kubernetes 和 Docker 的 [runC](https://blog.docker.com/2015/06/runc/) 中的漏洞。

很容易断定 Docker 和 cloud 存在尚未公开披露的其他本机漏洞。而且，不用说，大多数攻击者无论如何都在寻找更容易打开的门——或者更准确地说，是为他们打开的门——通过运行非常容易运行的密码漏洞。

[云原生计算基金会(CNCF)](https://www.cncf.io/) 和 [Docker](https://www.docker.com/) 表示，他们正在采取更积极的措施来锁定容器和云原生部署，但并没有批评他们在这方面的有效性。更重要的是，他们提供了更多的流程，披露了更多关于组织如何利用他们提供的资源来帮助自己的信息。

在最近于巴塞罗纳举办的 [KubeCon + CloudNativeCon](https://events.linuxfoundation.org/events/kubecon-cloudnativecon-europe-2019/) 活动中，[CNCF 首席技术官兼 CNFC 首席运营官 Chris Aniszczyk](https://www.linkedin.com/in/caniszczyk) 和[Docker 安全工程师贾斯汀·科马克](https://uk.linkedin.com/in/justincormack)探讨了两家公司如何以新的方式帮助组织更好地掌控其安全命运。他们在会议上的“新堆栈制造商”播客中与总编辑 Joab Jackson 进行了交谈。

总体而言，CNCF 一直向其成员提供安全工具和信息，安全审计已成为成员项目的关键流程。它通过与第三方安全公司签订合同来做到这一点。Aniszczyk 说:“你让某个人从外部查看你的代码，做一些潜在威胁建模、pen 测试等等，然后把这些结果交给项目，同时确保他们的安全披露过程是可行的。”。“项目本身能够解决他们的任何问题，因为我们项目的毕业要求是，他们必须能够有一个安全披露流程，并且能够通过事件安全审计。”

Aniszczyk 说，到目前为止，CNCF 项目已经完成了十几项审计。“还有一点很酷，”Aniszczyk 说，就是这些报告是如何开源的，如何“与世界共享”

科马克称赞 CNCF 倡议如何管理沙盒项目和早期项目的审计，以及“不只是在毕业时”Cormac 说，这“真的很好，因为有很多新项目可以从审计中学习安全性”。

Aniszczyk 说，在 CNCF 审计期间或在 Kubernetes 平台中发现的漏洞，只有在找到修复程序后才会公布。“Kubernetes 现在实际上正在经历这一过程。Aniszczyk 说:“审计工作即将完成，所以报告正在编写中，所有问题都在向上游推进，任何相关的 CD 都将被创建。”“所以，我们希望能在几个月后公布(这些报告)。”

[https://www.youtube.com/embed/KJG7dJdu5U8?feature=oembed](https://www.youtube.com/embed/KJG7dJdu5U8?feature=oembed)

视频

### 在这个版本中:

[1:40:](https://thenewstack.simplecast.com/episodes/cncf-docker-say-they-are-even-more-serious-about-security?t=1:40) 探索 CNCF 项目安全审计流程
[7:00:](https://thenewstack.simplecast.com/episodes/cncf-docker-say-they-are-even-more-serious-about-security?t=7:00) 对于审计公司来说，云原生计算组件听起来也是一种挑战。
[11:47:](https://thenewstack.simplecast.com/episodes/cncf-docker-say-they-are-even-more-serious-about-security?t=11:47)CNCF 的安保相关项目。
[12:30:](https://thenewstack.simplecast.com/episodes/cncf-docker-say-they-are-even-more-serious-about-security?t=12:30) 看起来目标的一部分是让项目考虑相同的安全最佳实践。
[19:58:](https://thenewstack.simplecast.com/episodes/cncf-docker-say-they-are-even-more-serious-about-security?t=19:58) Justin，你能提供 Docker Hub 安全漏洞的最新情况吗？
[25:40:](https://thenewstack.simplecast.com/episodes/cncf-docker-say-they-are-even-more-serious-about-security?t=25:40) 零信任模型是云原生计算用户需要牢记的好方法吗？

云计算原生计算基金会是新堆栈的赞助商。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>