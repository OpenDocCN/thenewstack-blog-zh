# 红帽为 Kubernetes 运营商推出一个中心

> 原文：<https://thenewstack.io/red-hat-launches-a-hub-for-kubernetes-operators/>

在 Kubernetes 运营商势头的基础上，Red Hat 建立了一个公共注册中心， [OperatorHub.io](https://www.operatorhub.io/) ，旨在使开发者和管理员更容易[为他们的应用找到预先测试的运营商](https://www.redhat.com/en/blog/introducing-operatorhubio-place-finding-kubernetes-native-services)。

红帽社区发展总监[黛安·米勒](https://www.linkedin.com/in/muellerdiane/)说:“运营商中心实际上是被设计成寻找和分享 Kubernetes 运营商和运营商支持的服务的公共注册中心。

亚马逊网络服务、谷歌云和微软也参与了该项目——这三家公司都提供商业 Kubernetes 服务。一个充斥着易于访问的运营商的中心可以让用户更容易地设置和部署应用程序。

CoreOS 在 2016 年引入了 Operator 模式，作为一种方式来加速在基于 Kubernetes 的集群上部署应用程序。本质上，operator 格式为软件开发人员提供了一个模板，告诉 Kubernetes 如何部署和维护应用程序，包括如何构建和部署该应用程序的详细说明。打包成独立容器的操作者将配置细节打包成 Kubernetes 可以理解的 YAML 定义的定制资源定义(CRD)。相关联的控制器确保所得到的集群由运营商规范来维护。

Red Hat [去年收购了](https://thenewstack.io/red-hat-will-acquire-coreos-greater-kubernetes-presence/) CoreOS，自那以后，它继续捍卫运营商的角色。该公司此后发布了[运营商框架](https://github.com/operator-framework)，这是一个开源工具包，提供 SDK、生命周期管理、计量和监控功能来支持运营商。

Mueller 说，除了提供打包格式将复杂的应用程序安装到集群上的初始用例之外，Operator 还用于简化“第二天的操作”。“除了初始安装之外的一切都是运营商框架起飞并获得如此广泛认知的原因。”

第二天的操作可能包括无缝升级应用程序、修补、备份和整体生命周期管理等任务。

红帽正在征求第三方运营商的提交。每位提交的操作员都将接受一系列基本操作测试。此外，打包必须符合[运营商框架的运营商生命周期管理](https://github.com/operator-framework/operator-lifecycle-manager)的标准。

最初，该中心预计将有大约 12 家运营商，但该公司预计，一旦消息传出，这一数字将迅速增加。现有的运营商包括 Couchbase Autonomous 运营商、etcd 运营商、Kubernetes 的 Jaeger 运营商、Kubernetes Federation 运营商、MongoDB Enterprise 运营商、Prometheus 运营商、Redis 运营商和 Apache Kafka 的 Strimzi 运营商。

*如果你在加州，想要获得更多关于运营商的信息，请参加 Kubernetes 运营商框架实践研讨会，这两个研讨会分别于 3 月 7 日在帕萨迪纳的 [ScaleX](https://www.socallinuxexpo.org/scale/17x/presentations/workshop-kubernetes-operator-framework) 和 3 月 11 日在圣克拉拉的 [OpenShift Commons 关于规模化运营的聚会](https://commons.openshift.org/gatherings/Santa_Clara_2019.html)。*

红帽是新堆栈的赞助商。

通过 Pixabay 的特征图像。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>