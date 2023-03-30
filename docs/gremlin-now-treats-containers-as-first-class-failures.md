# Gremlin 现在将容器视为一级故障

> 原文：<https://thenewstack.io/gremlin-now-treats-containers-as-first-class-failures/>

没有多少公司愿意失败。然而，我们的创业文化建立在从错误中学习的基础上。按照这种快速学习的习惯，如果我们可以通过不断注入失败来创造一种稳定感——在它击垮你(或你的银行)之前先击垮它？这就是[混沌工程](https://thenewstack.io/how-chaos-engineering-can-drive-kubernetes-reliability/)背后的想法，这是一个不断增长的网站可靠性工程，人们将虚拟化水槽扔向虚拟机，现在是容器。

[混沌工程](https://thenewstack.io/chaos-engineering-can-give-distributed-systems-stability/)是一种对你的系统进行安全破坏的好习惯，就像一只猴子对你的办公室进行破坏一样。多年前，以正常运行时间和狂欢闻名的流媒体服务网飞通过开源其[混沌猴子](https://github.com/netflix/simianarmy)软件，在分布式系统上自动执行定期停机，“以便建立对系统承受生产中动荡条件的能力的信心”，开创了这一现在正在出现的最佳实践

混沌工程是关于承认、解决和拥抱你的系统以及建造和使用它们的人的复杂性和不可预测性。通过首先关注关键的、面向客户的服务，这种有意的混乱有助于公司限制停机和事故对业务和财务的影响，进而限制服务级别协议的破坏和客户流失。

Gremlin 首席技术官兼联合创始人[Matthew fornacari](https://www.linkedin.com/in/mattforni/)说:“我们喜欢用疫苗来类比:注射少量的伤害可以建立主动避免灾难的免疫力。

我们已经写过 [Gremlin Chaos 作为服务平台](https://thenewstack.io/gremlins-tammy-butow-on-the-business-side-of-chaos-engineering/)。当混沌猴随机地一次终止一个系统的时候，小妖精会带来更多的同步混乱。

现在，作为服务平台的两年失败已经被更新，不仅在虚拟机级别而且在容器级别管理恶作剧。

“随着今天对 Gremlin 平台的更新，DevOps 团队将能够大幅提高 Docker 在生产中的可靠性，”Fornaciari 说。

谁可能从中受益？Gremlin 根据客户需求添加了这一功能，为使用或迁移到容器化基础设施的任何人提供服务，无论是通过 Kubernetes 还是其他 orchestrators 编排的。这通常用于已经建立了足够的产品或产品集的公司，他们至少有一个站点可靠性工程师，但它也可以用于任何在 orchestrator 中运行自己的容器服务的服务所有者或平台团队。

Gremlin 作为 Docker 服务的失败现在允许用户模拟丢弃主机，确保底层基础架构稳定。已经在像安德玛这样的选定客户中处于测试阶段，这一更新允许组织在 Gremlin 用户界面中自动发现 Docker 容器，然后在其上运行混沌工程实验。这已经是一种服务发现，在这种情况下，该工具会扩展您的网络，并找出服务所在的位置以及如何访问它们，但它现在也在容器级别上这样做。

“我们为基础设施故障提供一切，就像我们为容器提供的一样，”Fornaciari 说，并指出有一些开源软件解决方案专门针对 Kubernetes 或 Docker，但不是像 Gremlin 这样的所有软件。

通过 Gremlin 将容器视为一等公民，组织能够对 CPU 和内存过载等资源进行攻击，模拟延迟和 DNS 问题，甚至随机关闭容器。这都允许团队意识到当事情出错时他们的架构如何反应，以及如何修复任何不好的反应。

Fornaciari 告诉 New Stack，当团队开始迁移到容器化架构时，他们并不总是理解行为、功能和缺陷。混沌工程允许你提前测试容器级别的粒度。

“许多客户努力将容器视为主机。Gremlin 给了他们生产码头工人的信心，”他说。

Gremin 的新功能与自动修复功能并行工作，即属于同一组的虚拟机或容器集群进行健康检查。如果容器或虚拟机变得不健康并被 Gremlin 标记，它将进入自动修复并退出生产使用，并获取另一个实例。这种自动修复通常在 Amazon Web Services 中完成，要么将自己从负载平衡器中拉出，要么用一个健康的事件替换自己。

虽然 Gremlin 最初在裸机上执行虚拟化混乱，但现在它也在主机之上的基于容器的抽象级别上执行虚拟化混乱。它是同类产品中第一个像对待一等公民一样对待容器的，而不是在主机级别安装，然后在容器上运行。

Gremlin 的产品和公司价值观是简单、安全和可靠。Fornaciari 表示，第一个价值与这一工具更新密切相关，它允许用户只需点击四五次就可以点击并启动容器标签。

“容器发现的简单性在于我们为您填充潜在的目标。您不必记住标记和识别信息，只需点击几个简单的框，浏览用户界面，就可以了。”

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>