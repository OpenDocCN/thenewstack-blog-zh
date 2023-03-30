# K8ssandra 是 Kubernetes 的开源 Cassandra

> 原文：<https://thenewstack.io/k8ssandra-is-open-source-cassandra-for-kubernetes/>

继今年早些时候[收购](https://techcrunch.com/2020/03/03/datastax-acquires-the-last-pickle/)Last Pickle、[发布 Kubernetes 运营商](https://thenewstack.io/datastax-open-sources-a-kubernetes-operator-to-ease-cassandra-management/)和[推出 Cassandra Astra](https://thenewstack.io/datastax-creates-a-pain-reliever-for-cassandra-management/) 、 [DataStax](https://www.datastax.com/) 继续对 Kubernetes 感兴趣，在本周的 [KubeCon + CloudNativeCon 北美](https://events.linuxfoundation.org/kubecon-cloudnativecon-north-america/)上推出 [K8ssandra](https://k8ssandra.io/) 。DataStax 首席战略官 Sam Ramji 解释说，K8ssandra 汇集了过去六个月来各种努力的元素，结合了该公司在使用 helm chart 安装的开源发行版 Apache Cassandra 的经验。

“在这段时间里，我们学到了很多关于如何调整 Cassandra 架构以及为了让 Cassandra 在 Kubernetes 的世界中良好运行还需要哪些其他组件的知识。你怎么和库伯内特控制平面通话？为了自动化在无人值守环境中需要自动化的事情，如备份、修复、运行状况检查、滚动重启响应等，您需要哪些工具？这是我们迈出的一大步。我们学会了如何做到这一点，并开源了运行 Astra 所需的所有不同项目，”Ramji 说。

K8ssandra 包括前面提到的由 DataStax 构建和开源的[Cass-operator](https://github.com/datastax/cass-operator)Kubernetes operator，预构建和预配置的与 [Prometheus](https://prometheus.io/) 和 [Grafana](https://grafana.com/) 的集成，以及作为上次 Pickle 收购的一部分来到 Cassandra 的两个工具: [Cassandra Reaper](http://cassandra-reaper.io/) ，一个反熵修复工具，和 [Cassandra Medusa](https://github.com/thelastpickle/cassandra-medusa) ，一个数据备份和恢复工具。

Helm chart 将所有这些部分结合在一起，自动完成下载正确的容器、在控制平面中设置它们以及启动所有必要的 cron 作业的过程。舵图也是可配置的，允许用户根据自己的喜好切换安装的不同部分。

DataStax 的开发者关系副总裁 Patrick McFadin 将所有这些描述为在 Kubernetes 上部署 Cassandra 时“社区聚集起来的必备工具”。

“当我们谈论部署 Cassandra 时，这些是部署的自然部分，”麦克法丁说。“有大量的人在使用 Kubernetes，如果他们想运行 Cassandra，为什么他们要重新发明轮子？”

除了简单地将必须拥有的部分打包在一起，麦克法丁还称这次发布是“SREs 的聚集地，在那里我们可以开始贡献我们关于如何在 Kubernetes 中部署像 Cassandra 这样的东西的知识，”他解释说，像 New Relic 和彭博这样的公司已经在协助这项工作。

Ramji 回应了这一想法，指出 Prometheus 中预先配置的指标和 Grafana 中预先设计的仪表板带来的“嵌入式智慧”,这些指标提供了“操作经验”,说明在 Kubernetes 上运行 Cassandra 时应该注意哪些内容应该打包在一起，哪些内容不应该打包在一起。其他可能在不久的将来加入的工具包括开源数据收集器 [Fluentd](https://www.fluentd.org/) 和开源的端到端分布式追踪工具 [Jaeger](https://www.jaegertracing.io/) 。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>