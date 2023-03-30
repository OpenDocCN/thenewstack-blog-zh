# VMware 开源了光子控制器

> 原文：<https://thenewstack.io/vmware-open-sources-photon-controller/>

正如承诺的那样，VMware 已经将其光子控制器的代码作为开源项目发布。

早在 8 月份，它就宣布了该项目的计划，当时它[推出了 Photon Platform](https://thenewstack.io/vmwares-photon-platform-and-how-it-treats-containers/) ，作为 vSphere 的替代产品，仅面向“云原生”容器和打算提供软件即服务(SaaS)的数据中心，vSphere 尚未建立，也不打算建立。该公司在本周于巴塞罗那举行的 Dockercon 欧盟会议上宣布了这一消息。

光子平台由 Photon Machine 组成，其中包括 VMware 所谓的基于 ESX 及其轻量级 [Photon OS](https://thenewstack.io/vmware-announces-cloud-native-tools/) 的“micro visor”；以及 Photon Controller，它的分布式、API 驱动的多租户控制平面。该平台是为可伸缩性、变动性和高可用性而构建的。

虽然 Photon 平台将是一项订阅服务，但对控制器的访问将是免费的——它可以在 GitHub 上获得。VMware 还提供与 Pivotal Cloud Foundry 的捆绑服务。

“我们真的想围绕基于容器和微服务的框架构建一个平台。它将 Mesos、Kubernetes 和 Cloud Foundry 等容器调度器视为一流的实体，”VMware 云原生应用部门的首席技术专家 Jared Rosoff 说。

“我们可以要求它为我们创建一个 Docker Swarm 集群、一个 Kubernetes 集群或一个 Mesos 集群。它具有这些框架的内在知识；它可以像处理磁盘、虚拟机或其他框架一样处理这些逻辑集群实体。它简化了下一代工作负载的配置和管理。”

他毫不犹豫地试图通过开发商来吸引业务。

“软件开发人员正在做出许多技术选择。他们选择像 Kubernetes，Docker 和 Swarm 这样的技术。他们选择的技术主要是开源的，并且支持这种无摩擦的采用模式。我们希望使用这种开发人员驱动的采用策略来最大限度地减少采用的所有障碍，使开发人员能够真正轻松地将其拆除，并开始在其上构建应用程序，而不是派一名销售代表来试图向您的首席信息官推销它。”

Photon Controller 有许多通过 Apache Zookeeper 管理的松散耦合的组件或服务:

*   **根调度器**与叶调度器一起工作，提供一个设计成可伸缩和快速的双层调度器；
*   **API 前端**，API 接口，外部 API 使用 [Dropwizard](http://dropwizard.github.io/dropwizard/) 框架作为 REST/JSON 接口提供；
*   **部署者**实施控制计划，但也处理升级和更新；管家，确保控制平面与数据中心的节点保持同步；
*   **光波**身份和访问管理解决方案于 4 月开源； **Zookeeper** 用于故障转移和集群协调；
*   CloudStore 是一个可查询的横向扩展数据库，它使用了一个新的开源框架，名为 Xenon。CloudStore 充当所有对象(容器、集群、虚拟机、磁盘、网络、物理主机等)的单一真实来源。)由光子管理。
*   **健康管理器**评估组件的健康和修复情况；
*   **集群管理器**处理 Kubernetes、Mesos 等框架。

至于 VMware 对开源项目的预期，Rosoff 指出了对在这个平台上合作感兴趣的客户和合作伙伴，Pivotal 就是一个例子。

“Pivotal 发现，许多客户在尝试启动和运行 OpenStack 部署时遇到了阻碍。我们发现光子的启动和运行要简单得多，所以这创造了一个非常有趣的联合束，”罗素夫说。

“我们也有存储供应商希望创建一个更简单的模型，通过 Photon API 集映射他们的基础架构；我们希望与社区合作，使其他虚拟机管理程序和裸机操作系统能够在这里工作，它可以是在裸机 Linux 主机上的 Hyper-v 或 KVM 之上工作的控制器；我们看到许多客户对可扩展控制平面的概念感兴趣，也许他们有自己想要使用的应用服务基础设施或平台即服务框架，”Rosoff 说。“通过让它开源，我们设计系统的方式，你可以实现云的一些内置功能，而不是让它们成为基于云的插件。”

然而，AVOA 首席信息官战略顾问、分析师蒂姆·克劳福德对此表示怀疑。

“老实说，我对这个解决方案有点矛盾，”他说。“这实际上只适用于新的应用程序开发，而且有许多与之竞争的解决方案。我不认为 Photon 会在整个企业范围内被广泛采用。”

VMware 是新体系的赞助商。

专题图片: [E. Alejandro O](https://www.flickr.com/photos/u_nite/) 制作的[我们获得了](https://www.flickr.com/photos/u_nite/4156079184/in/photolist-7kfZxE-4PpVm5-pfSkz4-9Wte1P-z4xqud-58tgeq-d39pA-33DnBh-ZKcE6-9JcZak-jQULeF-oHeDu-fV4AFa-yZNUcz-d39sd-84SMP4-5RkzVR-pfcVmb-bUKoP5-9cfPvh-5G1zhW-8Jvx9k-5B5sh8-y51qc-5mQJBN-4wuWLQ-pfhsW-rAKzYt-bqo1mw-boMYB-eRhJh5-6NVoGc-c97N3L-4f3sT9-7QaWH7-o37Hcf-6yFtEQ-yhNZgN-fV4AzZ-boNd9-abaaM4-9JfNxy-43vgj-tN8Wn-rbrYeD-csLtm5-e24YNB-cRJUtJ-9VSN3F-dpTg2p)的控制权，并获得了 **CC BY-SA 2.0** 的许可。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>