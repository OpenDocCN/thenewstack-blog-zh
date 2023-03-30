# 为什么我们创建了普罗米修斯一致性计划

> 原文：<https://thenewstack.io/why-we-created-the-prometheus-conformance-program/>

[](https://www.linkedin.com/in/%F0%9F%93%88-richard-hartmann-b71800107/)

 [理查德哈特曼

理查德“里奇”是 Grafana 实验室的社区主任，普罗米修斯团队成员，OpenMetrics 创始人和 CNCF SIG 观察主席。他还组织各种会议，包括 FOSDEM、DENOG、DebConf 和混沌通信大会。过去，他让大型机数据库工作，让 ISP 骨干网运行，并从零开始建立了一个数据中心。](https://www.linkedin.com/in/%F0%9F%93%88-richard-hartmann-b71800107/) [](https://www.linkedin.com/in/%F0%9F%93%88-richard-hartmann-b71800107/)

继 Kubernetes 之后，Prometheus 是第二个加入云计算原生计算基金会(CNCF)的项目。Prometheus 也是继 Kubernetes 之后第二个在 CNCF 毕业的项目。从那以后,“普罗米修斯”一直是第二个被广泛采用的 CNCF 项目，仅次于“库伯内特”。现在，普罗米修斯是第二个推出官方合规计划的项目，就在…你懂了。；)

为什么这是个大新闻？因为它将使您，最终用户，更有信心地从 Prometheus 的各种兼容(和“兼容”)实现和产品中进行选择。

普罗米修斯是自身成功的受害者。我们是如何实现基于度量的可观察性的云原生标准。谈论自己的产品如何与普罗米修斯兼容的经济动机是巨大的。这些年来，我们在 Prometheus 团队中已经看到一些项目和供应商在适当的兼容性方面投入了巨大的努力，而其他人在营销部门投入了更多。

为了减少这种混乱，普罗米修斯团队[在 CNCF 的保护下创建了普罗米修斯一致性项目](https://prometheus.io/blog/2021/05/03/introducing-prometheus-conformance-program/)。任何想要获得 Prometheus 兼容性认证的人都可以运行我们不断增加的测试套件，例如[远程写入测试](https://prometheus.io/blog/2021/05/04/prometheus-conformance-remote-write-compliance/)，并向我们提交结果。在与 CNCF 签署文件(确保诚信测试和公平竞争环境)并提交成功结果后，这些项目和供应商可以展示“普罗米修斯兼容”标志。如果有人声称与 Prometheus 兼容，但在接下来的几周或几个月内没有那个标志，也许值得问问他们为什么——以及他们打算如何解决这个问题。

所有这些令人惊叹的事情是测试套件是完全开源的。一些供应商已经或准备为此做出贡献。这意味着每个人都可以改进他们自己的实现，我们保持彼此诚实，并且作为最终用户，您可以依赖一个实际上与云本机可观测性及其他标准无缝工作的解决方案:Prometheus。

我将于 10 月 14 日在 kube con+CloudNativeCon North America 谈论一致性计划[。请收听以了解有关其设计、可用测试套件、当前测试结果以及如何申请 Prometheus 兼容性官方标志的更多信息。](https://sched.co/lV2v)

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>