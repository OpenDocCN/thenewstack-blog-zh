# 如何选择合适的 Kubernetes 监控工具

> 原文：<https://thenewstack.io/how-to-choose-the-right-kubernetes-monitoring-tool/>

[](https://www.linkedin.com/in/kylehunter)

 [凯尔·亨特

凯尔是拉法系统公司的产品营销主管。他在信息传递和定位、竞争差异化、走向市场战略和思想领导力方面有着出色的表现。](https://www.linkedin.com/in/kylehunter) [](https://www.linkedin.com/in/kylehunter)

使用 Kubernetes 进行应用程序现代化的[的最大好处之一是，它能够通过在一个集群内的多个节点上操作来提供灵活性和可伸缩性。这样做允许应用程序跨集群甚至云环境分布。虽然 Kubernetes 的这一功能的好处远远超过了它的挑战，但它确实给跟踪应用程序和基础设施的整体健康状况造成了很大的障碍。](https://thenewstack.io/do-i-really-need-kubernetes/)

在本文中，我们讨论了一些当今的最佳实践及其相应的解决方案，用于监控 Kubernetes，以确保您进行优化以获得最大效率。

## **什么是 Kubernetes 监控？**

首先，让我们从 Kubernetes 监控的定义开始。在这种情况下，Kubernetes 监控意味着从您的集群中收集指标和事件，以确保您的代码、技术堆栈和所有应用程序正常运行。有效的监控还需要将所有这些数据集中在一个位置，让多个利益相关方能够获得可操作的见解。

由于运行 Kubernetes 和容器化应用程序通常会带来许多复杂的层，因此监控、集中和分析这些数据的过程可能会很麻烦。然而，Kubernetes 受欢迎程度的增长与支持它的工具和服务的激增相对应，包括各种开源和商业工具和平台，可以帮助实现有效的 Kubernetes 监控。

让我们从一些最流行和最广泛使用的 Kubernetes 监控和日志记录工具开始。有许多工具可供选择——坦率地说，最适合您的工具很大程度上取决于组织的需求——但此列表将提供一些适合许多 it 团队需求的常用工具的见解。

## **行业工具**

### **普罗米修斯**

Prometheus 因其开箱即用的事件监控功能而赢得了 Kubernetes 粉丝的喜爱。作为一个开源工具，Prometheus 为用户提供了许多商业解决方案所不具备的灵活性和可定制性。它是市场上较为成熟的事件监控和警报工具之一，早在 2016 年就加入了云计算原生计算基金会(CNCF)，成为继 Kubernetes 之后的第二个托管项目。

### **格拉法纳**

Grafana 是另一个开源平台，它为 Kubernetes 监控提供了许多优秀的特性。Grafana 作为度量分析和事件监控以及可视化的工具而蓬勃发展。该工具与 Prometheus 等监控软件携手合作，形成监控和可视化的组合拳。通过部署这两种工具，您可以深入了解 Kubernetes 实例。

### **灭霸**

我正努力避免任何复仇者联盟的双关语，但是灭霸的设计是为了让集中你的基于普罗米修斯的监控系统变得轻而易举(抱歉！).虽然普罗米修斯确实是一个受欢迎的和有能力的选择，监测库伯内特，规模普罗米修斯可以具有挑战性。灭霸是另一个开源工具，可以帮助您将现有的 Prometheus 部署转变为统一的监控系统。还记得我们说过的集中数据吗？这很有帮助。

### **弹性搜索**

Elasticsearch 是一个名副其实的搜索和分析引擎，它的灵活性和规模使其成为 Kubernetes 的最佳选择。

### **日志存储**

当谈到集中数据时，Logstash 可能是一个强大的选项。另一个开源工具，这是一个服务器站点数据处理管道，它从各种来源获取数据，对其进行转换并记录。

### **基巴纳**

如果数据不具有可操作性，它还有什么用？Kibana 是一个数据可视化工具，用于日志和时间序列分析，以及监控和智能。

## **选择合适的工具**

那么，面对所有这些选择，您如何着手为您的组织选择合适的工具呢？如上所述，最终的选择取决于您组织的需求。在做出这些决定时，重要的是不仅要看你当前的环境，还要看你的 Kubernetes 将来会是什么样子。选择一种能够随着公司的发展而扩展的监控方法，对于保持简化的运营并充分利用您的监控和分析至关重要。

考虑到这一点，Prometheus 和 Grafana 的组合是事件和应用监控的最受欢迎的选择之一。Prometheus 是从软件和硬件来源收集时间序列数据的最常用工具之一。Grafana 是一个强大的工具，可以将数据可视化为可操作的东西。

> 如今，有一些解决方案可以采用集中的方法进行监控，使组织在未来不再局限于一种或几种工具。

然而，如上所述，随着组织的发展，跨许多集群扩展 Prometheus 可能会成为一项挑战，因为在应用部署、管理配置要求和漂移方面存在障碍。如果您的组织目前或最终将在多集群环境中运行，这就是灭霸成为强大选择的地方。灭霸允许你聚合数据并提供长期存储，这使得普罗米修斯和格拉法纳的结合更加灵活。

另一个很好的选择，尤其是在大规模的情况下，是将 Elasticsearch 与 Kibana 和 Logstash 结合起来——通常被称为 ELK stack 或 Elastic Stack。这为收集、组织、搜索和可视化您的数据提供了一种很好的方式，从而为您的 Kubernetes 集群提供端到端的监控和可见性。

## 复杂性需要平台方法吗？

使用 Kubernetes 的 IT 组织在监控方面面临的最大挑战之一是预测未来的需求，并构建一个解决方案来提供现在和未来的稳定性和性能指标。事实上，许多组织面临着组合工具以创建满足其需求的监控堆栈的复杂性，他们决定采用商业解决方案，如 Datadog、New Relic 或 Cloudwatch。这些解决方案提供了强大的监控和可视化功能，但每种解决方案都有自己的优缺点。那么，当您的组织成长时，您如何知道选择哪个选项来为其服务呢？

对于许多公司来说，答案是采用平台方法。如今，有一些解决方案可以采用集中的方法进行监控，使组织在未来不再局限于一种或几种工具。您的组织可以为不同的节点或集群部署不同的工具，以满足您的应用程序的特定需求，同时仍然将您的可见性集中在单一控制台中，以进行跨组织的应用程序和基础架构运行状况监控。此外，通过采用基于角色的访问控制，您可以确保每个利益相关方获得最相关的数据和信息，从而将复杂性转化为控制力。

## **把所有的放在一起**

无论您决定采用单点方式还是平台方式来满足您的 Kubernetes 监控需求，可供您选择的选项和工具非常多，而且它们的功能非常强大。最重要的事情是努力获得对您的应用程序和系统的广泛可见性。这样做，您可以充分利用 Kubernetes，并为持续成功做好准备。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>