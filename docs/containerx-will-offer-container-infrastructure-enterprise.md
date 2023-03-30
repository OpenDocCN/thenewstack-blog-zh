# ContainerX 将为企业提供一个容器管理平台

> 原文：<https://thenewstack.io/containerx-will-offer-container-infrastructure-enterprise/>

初创公司 ContainerX 正积极致力于在 6 月初推出面向企业的容器管理平台。

这家总部位于圣何塞的公司于 11 月在巴塞罗那的 DockerCon 展会上亮相，此后每月发布一次测试版。

该公司的目标是通过两个 IP 在日益拥挤的集装箱管理细分市场中脱颖而出:弹性集群和集装箱池，这两个 IP 相结合，可以根据预定义的优先级和当前的资源利用模式为集装箱集群分配基础设施。

“如果人们认为我们是 vSphere for containers，我们会感到谦卑，”公司首席执行官 Kiran Kamity 说。“我们希望通过最少的培训，让任何虚拟机管理员都能成为容器管理员。因此，我们正在构建一个现成的、全包式的基础架构堆栈，它专为开发人员和运营人员能够自助服务的企业 IT 而设计。”

他说，这就是 vSphere 和 Hyper-V 在虚拟机领域所做的事情，但他补充说，“容器领域缺少这样的平台。”

该公司利用 VMware、微软和 Citrix 的领导经验，并从 General Catalyst Partners、Greylock 和 Caffeinated Capital 的前 VMware 首席技术官 Steve Herrod 那里筹集了 270 万美元的种子资金。

https://youtu.be/N_4WYd_9MKs

首席执行官基兰·卡米提的第一家公司 [RingCube](http://www.informationweek.com/mobile/citrix-buys-ringcube-for-personalized-virtual-desktop-capabilities/d/d-id/1099489?) 于 2006 年成立，建立了 Windows 容器，促使 ContainerX 专注于使 Windows 容器成为一流公民。思杰在 2011 年收购了这家公司。其他创始成员在 VMware 从事 vSphere 的[分布式资源调度(DRS)功能，该功能通过在底层基础架构中平均分配工作负载来提高可用资源的利用率。](http://www.forbes.com/sites/janakirammsv/2015/11/14/containerx-aims-to-become-the-vsphere-of-the-container-world/#6c73bf8e1069)

它正致力于满足企业市场的两种需求:开发者和公司高管的需求。

他说，开发人员可能会在一个容器中构建部门应用程序，然后去 IT 部门寻找运行它们的地方，但 IT 部门还没有能力提供这样的地方。

与此同时，“有远见的 IT 高管”意识到他可以通过减少虚拟机数量来降低维护成本，Kamity 说。

“每台虚拟机每年大约需要 16 个工时来修补、更新操作系统、防病毒等。这是针对合理自动化的基础设施。如果它们不是自动化的，可能需要更长的时间。再乘以您环境中的虚拟机数量，这就是一大笔 OPEX，”Kamity 说。

借助弹性集群和容器池，您可以将一个计算集群划分为多个逻辑池:财务获得 10%，CRM 获得 25%，以此类推。

他说，你可以超过 100%地过度使用这些资源，因为你知道在任何给定的时间点，数据中心资源都没有得到充分利用。

从安全和隔离的角度来看，这些池不仅有 CPU 隔离限制，它们还有自己的虚拟网络；他们有自己的 LDAP(轻量级目录访问协议)身份验证，这意味着特定团队或应用程序的开发人员身份验证是在池级别进行的。

他说，通过池，它可以创建一个多租户环境，可以在多个团队之间共享，同时更好地利用资源。

在同一个控制台中，您可以使用裸机、本地虚拟机或公共云来设置集群。

ContainerX 将在 1.0 版本中使用 [Docker Swarm](https://thenewstack.io/docker-swarm-wins-scaling-benchmark-dont-take-gospel/) 进行编排，但稍后会添加 [Mesos](https://thenewstack.io/mesos-simplifies-support-container-formats-unified-containerizer/) 。卡米提说他想在 3.0 版本中加入 [Kubernetes](https://thenewstack.io/kubernetes-cluster-ops-sig/) 。类似地，它使用 Docker 运行时，但是如果有需求，它会添加 CoreOS 的 rkt。卡米提说，Choice 是其平台的主要租户，但由于资源有限，该公司不得不在 1.0 版本中专注于 Docker。

## 它是如何工作的

每台主机上都有一个代理容器，代理具有计算、存储和网络功能。代理能够执行多租户，并将计算集群划分为多个池，等等。ContainerX 在池之间而不是在集群级别提供虚拟覆盖网络，对于存储，它可以与任何基于 NFV 的存储一起工作。它有自己的注册中心，并开放给其他第三方注册中心使用。

从网络角度来看，所有池都是隔离的，并且需要池级身份认证。如果你有一个流氓容器，占用了大量的 CPU 资源，它不能超过你为它设置的限制。这些资源是自动扩展的、有弹性的和孤立的。您可以随时向该群集中添加或删除计算机。

这一切都是为了与 VMware 和 Windows 紧密集成而设计的。

ContainerX 面临的最大挑战将是让自己与众不同，并赶上一系列竞争对手，451 Research 的云管理和容器研究经理杰伊·莱曼在最近的一份报告中写道。

他写道:“容器的增长，尤其是生产用途的增长，可能是一个好迹象，表明 ContainerX 对传统和 vSphere 容器部署经验和专业知识的关注将吸引企业。”

他说，它解决了使用容器的企业对开发和生产环境一致性的关键需求。容器池整合了开发、测试、试运行和生产，消除了流程中每个步骤、部门或开发团队对单独软件堆栈的需求。

但他强调了强劲的竞争，包括亚马逊的 EC2 容器服务，基于 Kubernetes 和 Joyent 的 Triton Elastic Container 服务的谷歌容器服务，CoreOS，Mesosphere，Cloud 66，Kismatic 和 Shippable，更不用说 PaaS 玩家 Apprenda，[最近宣布与 Kubernete](https://thenewstack.io/apprenda-extends-platform-services-kubernetes-integration/) s，Engine Yard，在其 Diego orchestration 软件中支持 Docker 的 Pivotal 以及 Red Hat，后者已将 Kubernetes 纳入其 OpenShift PaaS 并与谷歌合作。

Apprenda、CoreOS、Docker、Joyent、Pivotal、Red Hat 和 VMware 是新堆栈的赞助商。

特征图片:[路鉴](https://www.flickr.com/photos/roadconnoisseur/)[x](https://www.flickr.com/photos/roadconnoisseur/11331603325/in/photolist-igkqT8-dB65J4-DYpjdv-9Ju141-89aBpF-ahF6FQ-8VGFkq-evF6c1-9JrcAB-fZSrmx-ovnQsD-dBbwM9-fZSuN2-izjG2t-edTw6s-dB64Q8-bKjwgP-dBbwjW-9Ju3L1-7iNm9y-4enFGo-dkZNyR-Epvcce-9JrfEn-7XZiw3-8wCeQF-4MnNCY-7RHL9N-dBbwN9-dBMPLs-5GUJCC-dZT7xw-dB7C6G-eVRKZt-aDDe3K-DXjTc7-9CLRdE-DKTohS-etugMX-5V34md-6YEGy1-EtiqCT-CZnCt3-DQXzYB-7BmVJH-aZ6wZZ-iVmC6g-6hn8Xe-9ciaqf-dBbwt3)，授权 **[CC BY-SA 2.0](https://creativecommons.org/licenses/by/2.0/)** 。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>