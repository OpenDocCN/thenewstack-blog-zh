# 美国空军如何在 45 天内在 F-16 上部署 Kubernetes 和 Istio

> 原文：<https://thenewstack.io/how-the-u-s-air-force-deployed-kubernetes-and-istio-on-an-f-16-in-45-days/>

就混合云战略而言，美国军方无疑正在采取一种独特的方法。

根据美国空军首席软件官 Nicholas Chaillan 在圣地亚哥举行的 kube con 2019 上发表的演讲，就像几乎所有其他事情一样，军事组织越来越依赖软件，他们正在转向 Kubernetes 和 Istio 等一系列开源云工具来完成工作。这些工具必须部署在一些非常有趣的地方，从武器系统到甚至战斗机。是的，F-16 在这些喷气式飞机内置的传统硬件上运行 Kubernetes。

“团队的一个目标是证明这是可以做到的，”Chaillan 说。他要求空军及其合作伙伴在 45 天内让 Kubernetes 在喷气式飞机上运行，尽管这听起来很困难，但该团队实现了目标，F-16 现在正在运行三个并发的 Kubernetes 集群，他说。

自然接下来的问题是，为什么？在 KubeCon 开幕当天的主题演讲后，Chaillan 在他的拥挤的演讲中解释了美国空军——现在在他的指导下，国防部的其他部门——如何在集装箱、 [Istio 和 Kubernetes](https://thenewstack.io/why-do-you-need-istio-when-you-already-have-kubernetes/) 上下大赌注。对于整个军队的软件团队来说，这是一个灵活但通用的开发平台，并防止供应商锁定。

[https://www.youtube.com/embed/YjZ4AZ7hRM0?feature=oembed](https://www.youtube.com/embed/YjZ4AZ7hRM0?feature=oembed)

视频

Chaillan 说，在空军大约 18 个月前开始这个项目之前，大多数军事软件团队都是使用老式的瀑布过程来构建软件，新代码可能需要数年才能完全投入生产。即使在那时，更新、测试甚至安全审查都严重依赖人工来完成商业部门很久以前就决定应该自动化的任务。

当涉及到执行任务所需的技术时，军方真的不能落后主流太多。随着竞争对手投资于他们自己的软件能力，他们可以在战场上获得优势。更新一些军方最关键的应用程序所需的缓慢过程的安全影响是显而易见的。

“对我们来说，减少攻击面并能够减轻威胁非常重要，”Chaillan 说。

## 国防部企业发展局

Chaillan 和他的团队决定采用开源软件作为新开发平台的基础，他们称之为[国防部企业开发计划](https://software.af.mil/dsop/documents/)。该计划规定了 Kubernetes、Istio、knative 和内部开发的规范的组合，用于“强化”具有一组严格安全要求的容器，作为整个军队的默认软件开发平台。

Chaillan 说，不同分支或地区的软件团队在如何使用他们所掌握的工具方面有一定的自主权，但一切都必须建立在空军平台一号团队提供的层上，而且有几件事情是团队不允许改变的。有趣的是，考虑到围绕[国防部上个月授予微软的 10 年绝地云合同的所有喧嚣，整个堆栈被设计为运行在](https://www.nytimes.com/2019/10/25/technology/dod-jedi-contract.html)[亚马逊网络服务的 GovCloud 或微软 Azure](https://software.af.mil/team/cloud-one/) 上。

Chaillan 在他的演讲后由云计算原生计算基金会主办的新闻发布会上对此进行了详细说明，解释说“我们不想被任何一件事情所束缚。”为此，该团队选择使用 Kubernetes，其他项目如 Istio 为国防部堆栈的网络层提供安全性:“我们希望确保 Istio 在整个堆栈中持续运行，”Chaillan 说。

当然，一路上有很多挑战。Chaillan 说，Kubernetes 不是为军方必须在许多情况下使用的断开环境设计的，这些情况涉及不应该到达互联网的数据。他暗示，国防部在 Kubernetes 维护者处理项目的这一部分时，将对他们提出许多建议，这可能有助于为 Kubernetes 在其他敏感的操作环境中使用铺平道路。

“我们非常习惯于使用互联网进行更新，连接到互联网，直接从互联网上获取更新。他说，对我们来说，我们必须将整个堆栈带上飞机或武器系统，这些飞机或武器系统被设计成与互联网断开连接。

## 国防部规模的开源堆栈

国防部运作的规模不同于几乎所有的商业运作；Chaillan 不得不对 10 万人进行 DevSecOps 原理的培训，更不用说新工具了。“文化的转变很有趣，”他在新闻发布会上说，看起来有些克制。

这一规模反映了国防部将把这一新的开发平台用于许多普通和非机密的应用:超过 200 万人为军方工作，其中大多数人没有驾驶运行 Kubernetes 的 F-16。

“这架飞机很有趣，但它只是我们所做工作的一小部分。Chaillan 说:“我们有许多业务系统正在迁移到云原生环境，迁移到微服务，从一开始就在构建。

Chaillan 说，整个 DoD Enterprise DevSecOps Initiative 堆栈是开源的，任何人都可以查看。他说，军事机构在向开源社区发布更多工作方面“越来越好”，并指出“我们不会放弃(开源)软件。”

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>