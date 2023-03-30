# 煎饼播客:卡珊德拉和 Kubernetes 数据平面

> 原文：<https://thenewstack.io/pancake-podcast-cassandra-and-the-kubernetes-data-plane/>

数据平面在 Kubernetes 生态系统中扮演什么角色？这是我们最新的(虚拟)煎饼早餐和小组讨论的主题，由开源 Cassandra 数据库的保管者 DataStax T1 赞助，在最新一集的[新堆栈分析师 T3 播客中捕捉到。](https://thenewstack.io/podcasts/analysts)

上个月，Datastax [发布了一个 Kubernetes 操作器](https://thenewstack.io/datastax-open-sources-a-kubernetes-operator-to-ease-cassandra-management/)，这样 NoSQL 的数据库可以更容易地在基于 Kubernetes 容器的基础设施中安装、管理和更新。

本次讨论的小组成员:

《新书库》的出版商亚历克斯·威廉姆斯在 TNS 执行主编约阿布·杰克逊的帮助下担任了这个小组的主持人。

[Pancake 播客:Cassandra 和对 Kubernetes 数据平面的需求](https://thenewstack.simplecast.com/episodes/pancake-podcast-cassandra-and-the-need-for-a-kubernetes-data-plane)

2015 年，拉姆奇在谷歌工作，监督其当时新开放的开源项目 Kubernetes 的业务发展，该项目基于其内部容器编制器 Borg。Borg 为谷歌提供了一个单一的控制面板，用于动态管理其所有许多容器化的工作负载，其横向扩展数据库 Spanner[为数据平面](https://www.nextplatform.com/2017/02/15/googles-spanner-database-wont-well-clone)提供了相同的功能。

“这两者的结合使得计算和数据变得如此普遍，如此容易访问，以至于你可以做任何你可以想象的事情，”Ramji 解释道。

虽然 Kubernetes 为其用户提供了类似 Borg 的通用控制平面，但等效的数据平面尚未普遍建立。但这是一个卡桑德拉可以轻松胜任的角色。

[https://www.youtube.com/embed/LwkS_WGzNg4?feature=oembed](https://www.youtube.com/embed/LwkS_WGzNg4?feature=oembed)

视频

“Cassandra 已经存在了十多年，它是久经考验的分布式数据库之一。许多客户将它用于结构化、非结构化数据。MSV 指出:“卡珊德拉的独特能力真的越来越大了。”。

正如 Ploetz 指出的，这种可伸缩性也非常非常重要。

“我记得以前，横向扩展群集意味着像提交请求一样提交请求，这样我们就可以从戴尔购买一台或多台服务器，而且还必须为这一决定辩护。大型企业在冰川规模上移动，”Poletz 说。“使用像 Kubernetes 这样的东西，你可以说，‘我还需要三个节点。’好吧，嘣，嘣，嘣。给你。正是这种敏捷性和快速扩展的能力带来了巨大的好处。"

根据 Erickson 的说法，这就是为什么操作符是拼图的最后一块，因为它为 Kubernetes 提供了一个指令集，用于根据其需求放大或缩小数据库。

“当你添加一个 Cassandra 节点时，它会寻找一个种子，并说我准备好加入 Kubernetes 上的集群了。你正在使用 DNS 名称。因此，当我们想要添加节点时，我们使用 Management sidecar 所做的就是解析主机名，即种子的 IP 地址，并确保我们以正确的顺序编排这些事情。因此，如果 IP 地址发生变化，我们不会有问题，我们只是在启动时进行快速检查，以确保我们知道这一点，”她说。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>