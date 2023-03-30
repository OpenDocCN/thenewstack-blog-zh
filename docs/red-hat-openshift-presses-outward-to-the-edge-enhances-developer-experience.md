# Red Hat OpenShift 向外压到边缘，增强开发人员体验

> 原文：<https://thenewstack.io/red-hat-openshift-presses-outward-to-the-edge-enhances-developer-experience/>

[蜂巢](https://www.honeycomb.io/)赞助了新栈对 KubeCon+CloudNativeCon 北美 2020 的报道。

虽然 Red Hat 在 10 月下旬正式[推出了](https://www.openshift.com/blog/red-hat-openshift-4.6-is-now-available) OpenShift 4.6，但该公司在本周的[kube con+CloudNativeCon North America](https://events.linuxfoundation.org/kubecon-cloudnativecon-north-america/)发布会上推出了许多围绕其托管 Kubernetes 产品的新功能，包括围绕无服务器的更新、其 [Quarkus](https://quarkus.io/) Kubernetes 原生 Java 堆栈、长期支持以及在不需要 Kubernetes 的情况下运行远程工作负载的能力。

除此之外，Red Hat 的产品战略高级主管 Brian Gracely 解释说，该公司已经扩大了用户可以运行 OpenShift 的地方和硬件。

“我们总是说 OpenShift 是一个可以在任何地方运行的平台，私有云、公共云，但即使在这两个领域中也有许多子领域，”Gracely 说，并解释说 OpenShift 现在也支持 IBM Power 和 Z 平台，以及 AWS 和 Azure 政府云。

Red Hat 还将为 OpenShift 引入延长的生命周期支持，将范围从 9 个月延长到 18 个月，帮助那些难以跟上 Kubernetes 发布周期的公司减缓步伐，Kubernetes 每三个月发布一个新版本。“我们已经听到越来越多的客户说，‘我们感谢所有的创新，但跟上它有时具有挑战性，’”格雷斯利说。

在无服务器方面，随着 Apache Camel-K 的加入，用户现在可以从 100 多个事件源中进行选择，这带来了新的事件源，如 AWS SQS、AWS Kinesis、Salesforce、Slack、Telegram 等。

Red Hat 还让所有 OpenShift 客户都可以使用 Quarkus，并优雅地表示，这个框架已经推出一年多了，现在已经开始有回报了。

“Java 的问题是它往往相当重量级。Java EE 之类的东西和某种程度上的 Spring Boot 之间总是有一点点不匹配:把它放在一个容器中，你往往会有非常重的容器。Quarkus 的真正目标是减少内存占用、启动速度等等，并试图让 Java 应用程序看起来更像你的其他容器应用程序，”Gracely 说。“他们看到内存使用量大大减少，启动时间几乎是即时的。我会说，这相当于当人们第一次开始使用服务器虚拟化时，他们会说，“哦，现在我明白了这是做什么的，我马上就能省下一大笔钱。”这和我们看到的差不多。"

与此同时，红帽将继续把重点放在运营处于边缘的 Kubernetes 上，并超越 Kubernetes，寻找潜在的更简单的替代方案。格雷斯利说，在该公司推出在边缘运行三节点 OpenShift 的能力后，客户开始询问是否可以将这种能力进一步缩小到一个节点，他说他们正在研究这种可能性。然而，除此之外，OpenShift 4.6 还包括启动远程工作节点的能力，这将处理能力扩展到空间受限的环境，并使远程扩展成为可能，同时保持集中式操作和管理。

“通常使用 Kubernetes，您会在同一位置部署控制平面、主节点和工作节点。我们开始看到一些使用案例，在这些案例中，人们要么说部署这两者的成本太高，要么说‘我在那里的可用空间有限，我可以让员工在远程位置工作吗？’因此，我们允许人们扩展这些边缘，只成为工作节点，只成为应用节点，”Gracely 解释道。

本质上，这允许 OpenShift Kubernetes 将远程节点视为同一个集群的一部分，Gracely 说这是一个调整问题，以确保当响应时间比本地资源预期的正常敏感响应时间长时，Kubernetes 不会取消对远程资源的调度。

最后，Gracely 表示，该公司[最近提出了](https://www.redhat.com/en/blog/whats-new-red-hat-enterprise-linux-83)根据 edge 用例的应用需求，结合 Red Hat OpenShift 或 Red Hat Enterprise Linux 和 Podman 在 edge 上运行容器化工作负载的想法。

“你打算在那里用掉多少集装箱？你真的需要 Kubernetes 吗？出现这种对话的原因是，你开始问一些问题，比如“你打算多久去触摸一次那个边缘设备？”Kubernetes 的更新频率非常快，比你可能习惯的要快。这真的是你想处理的事情吗？”优雅地说如果只有本机操作系统(本质上是 RHEL)可以实现您想要的功能，它是以安全方式本机构建的，并且它更适合单节点甚至双节点环境，那会怎么样？"

格雷斯利说，展望未来，OpenShift 将继续扩张，既向云领域扩张，也向抽象 Kubernetes 领域扩张，改善开发者体验。

“我认为在这一点上，我们已经触及了 OpenShift 可以运行的每一个可能的云，尽管我们可能会在未来扩展到阿里巴巴和其他一些公司，但未来你将看到的是继续让在 Openshift 上构建应用程序变得越来越简单。少谈 Kubernetes 的特性，多谈隐藏 YAML，让定义微服务更简单，让运行不同语言更容易，等等。这就是下一个重大转变的地方:加倍努力为更广泛的应用程序简化开发人员的体验，”格雷斯利说。

KubeCon+CloudNativeCon 和 Red Hat 是新堆栈的赞助商。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>