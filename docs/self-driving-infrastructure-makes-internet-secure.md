# 自动驾驶基础设施让互联网更安全

> 原文：<https://thenewstack.io/self-driving-infrastructure-makes-internet-secure/>

CoreOS 的成立有一个使命:保护互联网。这个有点大胆的目标驱动着我们所做的一切。自三年前成立公司以来，我们一直处于行业变革的中心，这是一场向动态调度、容器化应用程序的云原生世界转变的运动。随着组织对其应用基础设施进行现代化改造，这是一个独特的机会，可以在整个软件体系中实施和采用新的措施来保护企业和客户所依赖的服务。

事实证明，机器可以比人类更好地部署软件。为什么？因为软件部署是一组可以由声明性语言驱动的机械过程。这是一个为系统方法做好准备的过程，并且是可重复的。当补丁和安全补丁被应用到软件中时，这一点尤其重要——这是一种应该是可重复的、无缝的仪式。

## 自动更新=自动驾驶基础设施

大多数影响软件部署的安全问题都可以通过及时应用随时可用的更新来缓解。不幸的是，在高压下有机构建的一代基础设施被认为是如此脆弱，以至于许多运营团队养成了“让它运行起来，不要碰它”的口头禅这不仅不利于安全，也不利于业务，因为它阻碍了公司交付自己的软件的能力，而不仅仅是他们应用安全更新的能力。

这里有一个例子:作为这种现状的安全影响的关键说明，我们已经看到了两个需要立即关注的主要漏洞:“脏牛”Linux 权限提升( [CVE-2016-5195](https://cve.mitre.org/cgi-bin/cvename.cgi?name=CVE-2016-5195) )和 Kubernetes 远程访问漏洞。这两个安全缺陷在同一天被披露，是关键漏洞“起火”的主要例子，运营团队不得不放弃他们正在做的任何事情来更新他们的软件。

另一方面，使用自动驾驶基础设施，安全更新会自动应用到所有使用 Container Linux(以前称为 CoreOS Linux)和 core OS structure 软件的运行系统。在所谓的“脏牛”漏洞出现的 24 小时内，大多数客户的 CoreOS Linux 系统在没有任何用户干预的情况下得到更新。自从我们开始 CoreOS 以来，我们就在 CoreOS Container Linux 中提供了这种自驱动方法，现在我们正在将这种关键功能引入 Kubernetes 集群。更新软件是安全的关键，轻松自动更新软件的能力是提高服务器安全性最有效的方法。

自动驾驶基础设施允许运营团队将他们的注意力从追逐安全更新和灭火上转移开来，使工程师能够在更高价值的领域进行创新。就像汽车中的自动驾驶系统减少人类驾驶员的认知负荷一样，自动驾驶基础设施可以解决困扰当今管理服务器的运营团队的看似不断的火灾和问题。

## 追求平台的开放组件

为了让自动驾驶基础设施成为现实，我们在过去的三年半时间里一直在引领一种新的基于软件容器和分布式系统的开源软件。在不停机或不影响运行服务的情况下自动化基础架构软件更新和管理是一个非常困难的问题，这就是为什么我们在基础组件上花费如此多的精力来使其全部工作:像 [CoreOS Container Linux](https://coreos.com/why/) 、 [etcd](https://coreos.com/etcd) 和 [Kubernetes](http://kubernetes.io) 这样的软件。我们将这些部分视为构建可靠的自动驾驶基础设施的要求，这些基础设施让我们对未来感到兴奋。

## 当今无人驾驶基础设施

这不仅仅是对遥远未来的憧憬。我们目前每月通过 CoreOS 的 Container Linux 向 100 万个实例提供自动软件和安全更新。在 11 月的 KubeCon 大会上，我们引入了 Operators，它们是 Kubernetes 代理，封装了应用领域的专业知识，已经可以用来帮助管理[您的监控系统](https://coreos.com/blog/the-prometheus-operator.html)，或者自动化[etcd 分布式键值存储的部署和恢复](https://coreos.com/blog/introducing-the-etcd-operator.html)。

运营商是 Kubernetes 生态系统发展的一个重要里程碑。它们描绘了 CoreOS 对基础设施未来的愿景，并提供了一种自动化安全措施的机制，这对于我们保护互联网的使命至关重要。

最近，在本周举行的构造峰会(Kubernetes 的主要企业活动)上，我们宣布 core OS structure 是第一个自动驾驶的 Kubernetes 平台，它采用了我们的容器 Linux 理念，并将其应用于 core OS structure。那些使用 core OS structural 的用户将获得适用于 Kubernetes 的最新版本和安全更新。这是一个激动人心的时刻，因为这仅仅是我们共同努力保护互联网并使我们数字世界的主干变得更加强大和安全的开始。

[英特尔的尼克·韦弗讨论编排](https://thenewstack.simplecast.com/episodes/intels-nick-weaver-discusses-orchestration)

CoreOS 和英特尔是新堆栈的赞助商。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>