# ActiveState:为什么没有容器编排的 Docker 是不够的

> 原文：<https://thenewstack.io/activestate-docker-without-container-orchestration-not-enough/>

当通过平台即服务(PaaS)部署应用时，Docker 本身是不够的。当用户可以应用编排 Docker 容器部署的方法时，真正的价值就来了，正如我最近与 [ActiveState 的](http://www.activestate.com/) [John Wetherill](http://www.activestate.com/blog/authors/johnw) 讨论的那样。

[https://www.youtube.com/embed/dYW769B79K4?feature=oembed](https://www.youtube.com/embed/dYW769B79K4?feature=oembed)

视频

随着越来越多的用户考虑如何使用 Docker，容器编排是一个适时的话题。然而，当在企业运营的环境中考虑 Docker 时，用户通常会发现管理 Docker 要复杂得多。

[![johnwetherill](img/37dc34471f191f23aca3e20c0eab8783.png)](https://thenewstack.io/wp-content/uploads/2015/02/johnwetherill.png)

John Wetherill 是平台即服务 Stackato 的开发者 ActiveState 的技术布道者。

Wetherill 使用该演示来讨论容器编排如何在 ActiveState 的 [Stackato](https://www8.hp.com/us/en/solutions/business-solutions.html) 环境中构建、管理和自动伸缩容器。Stackato 是基于 Cloud Foundry、Docker 等开源组件的私有 PaaS 软件。它可以安装在您的内部基础架构或公共云上。

首先，Wetherill 展示了如何[将 ActiveState 微云](https://www.activestate.com/blog/activestates-stackato-cloud-foundry-docker-based-paas-acquired-hp/)下载到虚拟机，然后在 VMware 中启动它。根据 ActiveState 的说法，微云是 Stackato 系统的独立实例，运行在单个高达 4gb 内存的虚拟机中。它允许您将您的应用程序推到一个与完整的 Stackato PaaS 集群功能相同的环境中。

通过虚拟机，Wetherill 访问了登录页面的链接，并登录到 web 控制台，以访问显示已部署的应用程序以及他可以选择部署的应用程序的应用程序商店。任何企业语言在 Stackato 上都有体现。然后，他导航到 OpenStack 上的一个路径，部署了一个 Python 应用程序，指定了一组属性。

部署后，Stackato 从 GitHub 上托管代码的地方提取应用程序的位。在这个过程中，它为应用程序创建 Docker 容器，为数据服务创建容器。他推出的三层货币转换器应用程序利用了 Redis。在 PaaS 中，Wetherill 对于如何使用容器有几种选择。例如，他可以扩展应用程序，通过用户界面中的滑动条增加实例的数量。

Wetherill 的例子展示了 Stackato 如何自动化容器编排。它说明了如果用户不能访问 Stackato 容器编排环境，他们将不得不手工缝合容器。

特色图片[通过](https://www.flickr.com/photos/time-to-look/15298114215/in/photolist-iuZJCa-bLFHn4-6EWEaD-4tqp7Q-piQQnV-jtzgQm-fd8cES-bzDEbs-6fZZUv-aZQA6n-cp4Fvm-ee9x3C-bLFGoM-bE7KPV-bj9f4F-asFVfF-bELWYN-cEjVMJ-o23HQH-pyh2vz-b88Fng-ee9x5U-pRCD46-aSQpMV-fwVKE3-bVYo4M-8XbbWZ-e8u2HB-c8TxVd-hH4aTb-8CTHwn-5iyCua-8D5Sjj-gsG89i-97gM6q-ceyGSj-5FHLwD-drWn5b-drWuYb-o9jtJw-2hvny-dsayc3-8XxXb1-eaH2mS-hXev2r-fJYrjR-fKfUKQ-8x8Nfm-7jVafW-4zywCy) Flickr 知识共享。

ActiveState 是新堆栈的发起人。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>