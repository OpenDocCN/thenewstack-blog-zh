# Loodse 自动化 Kubernetes 集群管理

> 原文：<https://thenewstack.io/loodse-automates-kubernetes-cluster-management/>

德国公司 Loodse 提倡使用 Kubernetes 本身来自托管多个 Kubernetes 集群。这家总部位于汉堡的公司成立于 2016 年，它的名字来自一个荷兰语单词，意思是领航，就像在船上一样——就其而言，是一艘集装箱船。

Loodse 在二月份发布了其自动化编排系统的测试版。此后不久，联合创始人 [Sebastian Scheele](https://www.linkedin.com/in/sebastian-scheele/) 在 TNS 的一篇文章中概述了其技术。

Kubermatic 是一个自动化的“主即服务”解决方案，使您能够轻松设置托管的 Kubernetes 集群。它提供完全托管的主组件和节点，以及针对节点和工作负载的水平扩展。

Kubermatic 与 DigitalOcean 和 Amazon Web Services 以及任何提供 Ubuntu 16.04 或更高版本的提供商直接集成。该公司还致力于支持更多的云提供商。

该公司的目标不是沿着像 [StackPoint Cloud](https://thenewstack.io/stackpointcloud-solidifies-pricing-managed-kubernetes-cloud-deployments/) 、 [TeleKube](https://thenewstack.io/telekube-offers-remotely-managed-private-saas-kubernetes/) 、 [Platform9](https://thenewstack.io/platform9-offers-developers-flexibility-todays-multi-cloud-world/) 或 [Stratoscale](http://www.stratoscale.com/products/kubernetes-as-a-service/) 这样的平台提供托管 Kubernetes 服务。根据 Scheele 的说法，相反，它希望帮助企业在自己的基础设施上建立自己的容器引擎，无论是与云提供商合作还是内部部署。

“我们想创建一个类似于谷歌容器引擎的东西，但在任何地方，并[使客户]轻松地运行容器集群，并有多个集群，”他说。

[集群联盟](https://coreos.com/blog/kubernetes-cluster-federation.html)——将多个集群汇集在一起——是谷歌的 [Kelsey Hightower](https://github.com/kelseyhightower) 最近在柏林举行的 KubeCon Europe 2017 上发表的主题之一，Scheele 和高级基础设施建筑师 [Jason Murray](https://github.com/chaosaffe) 也在该活动中做了发言。

“我们希望让客户能够像牛一样管理他们的集群，”舍勒在接受采访时说，他指的是常用的[宠物与牛的类比](https://thenewstack.io/container-orchestration-scheduling-herding-computational-cattle/)。“创建新群集、丢弃现有群集、保存数据、装载存储应该很容易……我们为应用程序开发人员设定的目标是让基础架构变得不可见。”

只需按一个按钮来创建一个集群，定义一个名称。您可以定义主服务器应该运行的位置、公共云或数据中心。在后台，它启动 Kubernetes 主组件:API 服务器、 [etcd](https://github.com/coreos/etcd) 键值存储、调度器和控制器。然后，它创建由主服务器管理的内部集群。

你可以在任何时间点运行任意多的集群，[默里](https://github.com/chaosaffe)在[在线聚会](https://www.youtube.com/watch?v=oN8cmtgAEDQ)上说。您可以根据需要动态添加和删除节点。该公司还致力于开发动态节点扩展功能。

Kubermatic 为高可用性运行两个主组件，并在后台对它们运行健康检查。

默里在会议上说，最大的问题是网络、负载平衡和存储。

“当你处理 Kubermatic 集群时，我们希望创建一个非常一致的平面，不管你在哪个提供商上运行你的节点，你每次都有相同的期望，并且你每次都可以以完全相同的方式跨所有这些提供商部署你的集群，”他说。所以他们必须抽象出很多东西，使之独立于主机和提供商。

他说，在不同的环境中运行 seed 集群——谷歌容器引擎(GKE)、AWS、裸机——每一种环境都带来了独特的数据挑战。

然而，Kubernetes 最近发布的[存储类](http://blog.kubernetes.io/2016/10/dynamic-provisioning-and-storage-in-kubernetes.html)使得在创建和销毁集群时动态供应卷变得更加容易，而不必为此进行编码，他说。

另一个问题是 Kubernetes 的假设，例如，如果您在 AWS 上运行主服务器，节点也会在那里运行。在 Loodse 模型中，主服务器可以在一个云中，但是节点可以在任何地方运行。

默里说，该公司做了一些改变，并将其发送到上游项目，以解决这些基本假设。

它是二月份宣布的云本地计算基金会的新成员之一。**

特征图片:*[**DSC 06396**](https://www.flickr.com/photos/pdenker/9962419204/in/photolist-gbm19m-3ajHa8-bWA2Lq-76ZDxh-oTcBpv-9fm4op-9nP3E2-nBNj56-cTniQA-o7wthm-6dqBLe-8wHrti-89iKCo-fDNKC7-cTBypu-nW3fzB-5xXAqZ-omV1cq-nUi6i7-2avu9m-8eFP6z-2dys9D-2Z6EXr-qh7Z6D-bUWhgF-6k3eo8-8kQSry-6cz6kS-jfkPGH-6cz5Z9-84M6wh-2fpU5P-517WE2-9fm2Xk-e6JYFa-6b3jk7-aDw7QC-baAETv-EvA8Br-TeUdSV-a4aKHx-J2x5US-a4e4jd-puCujr-dW1mco-syQiDu-mr8yrx-8Jko4t-8JkohZ-8Jko7g/)作者 [Patrick Denker](https://www.flickr.com/photos/pdenker/) ，授权于 [CC BY-SA 2.0](https://creativecommons.org/licenses/by/2.0/)*

 *云本地计算基金会是新堆栈的赞助商。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>*