# CNCF 将托管 CoreDNS，通过服务发现提升其云原生产品组合

> 原文：<https://thenewstack.io/cncf-host-coredns-boosting-big-tent-service-discovery/>

就在本周的第二次签约中，[云原生计算基金会](https://www.cncf.io/)周四上午正式宣布，它将接管 [CoreDNS](https://coredns.io/) 的管理工作，这个项目诞生于一年前，其想法是挖出一个名为 [Caddy](https://caddyserver.com/) 的网络服务器的内部，并使其对服务发现的复杂请求做出响应。

“有许多不同的 DNS 服务器，甚至还有其他基于 DNS 的服务发现解决方案，”网络可见性服务提供商 [Infoblox](https://www.infoblox.com/) 的杰出架构师、CoreDNS 的主要贡献者 [John Belamaric](https://twitter.com/johnbelamaric) 说道。“但 CoreDNS 的一大优点是它具有极强的可扩展性和灵活性。这使得它很容易适应云原生环境中频繁变化的动态世界。”

[Miek gie Ben](https://www.miek.nl/)—[sky DNS](https://github.com/skynetservices/skydns)的原作者，他在几天内创建了 CoreDNS 征用了 Caddy 的底盘，因为它有一个有趣的扩展性模型。在解析查询时，它通过一系列插件函数传递标准，Gieben 称之为“中间件”(把 JBoss 和 WebSphere 放在脑后，把它想象成事物中间的一个软件链。)使用用 Go 编写的函数向 CoreDNS 注册这样的函数。以一种完全不复杂的方式，标准从函数链的前端传递到后端，直到有人能够解决它。

通过这种方式，可以非常容易地为服务发现的目的定制 DNS 的功能，这对于[微服务](/category/microservices/)来说更加频繁。

在周三的一篇博客文章中，Belamaric 透露 CoreDNS 团队已经成功地扩展了他们服务器的功能，不仅服务于 **A** ，还服务于 **SRV** 、 **PTR** 和 **TXT** 记录，其方式基本上与用于 Kubernetes 的 [Kube-DNS 插件兼容。](https://github.com/kubernetes/kubernetes/tree/master/cluster/addons/dns)

“该架构的灵活性使我们能够轻松调整 CoreDNS，以适应云原生环境中的不同用例，”Belamaric 告诉新堆栈。他说，类似于他的团队为 Kubernetes 实现后端服务发现而插入的“中间件”，拥有一个链接到 [**etcd**](https://github.com/coreos/etcd) 键值存储的链式函数链接将非常容易，为任何其他编排器提供类似的功能。

“像 [BIND](https://www.isc.org/downloads/bind/) 这样的传统 DNS 工具真的不是为那种你从 **etcd** 或 Kubernetes 中获得的动态交互水平而构建的，”他继续说道。他提醒我们，BIND 将其数据存储在文件中，绑定使得系统很难被修改以呈现略有不同的数据。

他说，BIND“是一个代码库，具有令人难以置信的大量特性。当然，正如我们在我们的行业中所知道的，随着一些东西的成长和增长，随着时间的推移而老化，并积累特性，修改变得越来越困难，尤其是在不破坏那些特性的情况下。因此，从开发的角度来看，尝试将后端数据存储换成 BIND，从那些定期重新加载、记录上有相对较长[*生存时间*]的文件中换出，并增加序列号，以处理类似于**etcd**的东西，将是相当具有挑战性的。”

服务发现——正如[周三 CNCF 接受 gRPC 所提醒我们的那样,](https://thenewstack.io/cncf-adds-googles-grpc-remote-call-project-big-tent/) —是过去庞大、集中的面向服务模型和今天敏捷、轻量级系统之间的关键区别。对于微服务来说，在每次对话中互相重新介绍自己似乎是违反直觉的(就像 Ellen DeGeneres 描绘的鱼一样)，但它避免了使用集中、庞大、序列化数据库的代价。至少，这是目标，只要服务发现不被绑定到 BIND 的最小数据库引擎，这对于现代数据服务就像一个上紧发条的音乐盒对于爱乐乐团一样。

Belamaric 指出:“大多数现有的 DNS 服务发现解决方案都绑定到单独的编排环境，或者它们建立在不太灵活的架构上。“它的设计不涉及任何级别的并发性；BIND 是一个单线程环境，而 CoreDNS 是多线程的。还有其他服务器，如 [Unbound](https://calomel.org/unbound_dns.html) 也是多线程的，但它们也有许多功能不一定适用于云原生世界。”

Belamaric 告诉 New Stack，CoreDNS 的贡献者希望获得更广泛的开发社区的更多可见性，以及来自 CNCF 众多用户成员的洞察力。

“我们将能够利用对集群的访问来推动可扩展性测试，”他补充道。“就功能而言，我们确实希望将[*CoreDNS*]扩展到其他管弦乐队，而不仅仅是[CNCF 的][T2 的]Kubernetes。我们希望围绕服务注册建立更多的结构，并可能有一个服务注册和发现解决方案组合。”

随着管理员和首席信息官期待集装箱化开发商解决其技术上悬而未决的安全问题，Belamaric 预见到通过应用选择性政策来扩展 CoreDNS 的可能性。具体来说，他看到 DNS 服务器可以根据规则批准或拒绝请求，这可能是由一个开源策略框架来执行的，如[开放策略代理](https://github.com/open-policy-agent/opa)。

这样，可能来自未经身份验证的来源或网络状态可能处于转换中的情况下的潜在危险查询可以被冷阻止，从而在潜在入侵或数据泄露开始之前就将其消除。Belamaric 承认，这样的系统需要实现访问控制列表(ACL ),并且会导致性能损失。尽管如此，他认为，这些损失不会超过从一开始就转移到现代的多线程数据引擎所带来的净效率收益。

无论 CNCF 是否会选择云原生平台托管，你都不能否认基金会正在将它们提升到一些非常高的基座上。

特征图片:[阿拉斯加理查森埃尔门多夫联合基地的电话总机](https://commons.wikimedia.org/wiki/File:JBER_telephone_operators_connect_calls,_people_120124-A-ZY202-001.jpg)，大约 1950 年，公共领域。

云计算原生计算基金会是新堆栈的赞助商。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>