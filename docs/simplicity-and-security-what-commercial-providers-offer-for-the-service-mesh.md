# 简单性和安全性:商业提供商为服务网格提供了什么

> 原文：<https://thenewstack.io/simplicity-and-security-what-commercial-providers-offer-for-the-service-mesh/>

*The News Stack is running [a series of posts](https://thenewstack.io/service-mesh-adds-security-observability-and-traffic-control-to-kubernetes/) on the value that a service mesh brings to Kubernetes deployments. This week, we resume that series with this latest installment. Check back often [for more updates](https://thenewstack.io/category/service-mesh/).*

“开源就像小狗一样免费，”T2 阿斯彭网(Aspen Mesh)的首席技术官安德鲁·詹金斯说，他是 T4 Istio 服务网(Istio service mesh)企业版的提供商。无论我们谈论的是 Kubernetes、Spinnaker 还是服务网格，企业产品与纯开源软件的争论本质上是相同的。开源是免费的，但是通常没有公司需要的全部功能。在内部调整开源解决方案的成本加起来可能比购买一个已经自带这些特性的产品的成本还要高。

组织转向商业服务网格提供商的另一个原因是支持。在 Linkerd 的案例中，这是转向提供商业 Linkerd 支持的公司[buppy](https://buoyant.io/)的唯一原因。“我们不会隐瞒任何事情，”浮力公司的首席执行官威廉·摩根解释道。“这更多的是一种哲学立场。然而，如果你想与我们建立商业关系，我们将确保服务网络为你服务，提供服务和集成等所有东西。”

## **驯服复杂性**

服务网格是为非常复杂的架构设计的。它们只对大规模运营的公司有意义，但它们本身会增加基础架构的复杂性。Aspen Mesh 等公司的一个主要关注点是降低服务网格带来的复杂性。Jenkins 解释说:“我们在上面添加了我们自己的仪表板，并且我们将该用户界面用于我们的大量数据。这使得公司使用服务网格比使用普通 Istio 更容易。

在 [Consul](https://www.hashicorp.com/products/consul) 、 [HashiCorp](https://www.hashicorp.com/) 的服务网格中，组织可以使用服务网格将运行在 Kubernetes 中的服务与运行在其他环境中的传统应用连接起来，从而降低许多混合了云本地应用和传统应用的现实组织的整体复杂性。

HashiCorp 的 Consul 产品营销经理 Raymond Austin 解释说:“我们看到许多人开始为他们的云原生应用程序建立服务网络。“然后，他们意识到他们有一堆本地资源或虚拟机环境。例如，他们希望将 Kubernetes 连接到现有的数据中心环境。”

[服务网格服务和工具提供商](https://www.linkedin.com/in/iditlevine/) [Solo.io](http://solo.io) 的首席执行官艾迪特·莱文同意简单是与商业服务网格提供商合作的原因之一，尤其是当你处理多个集群和/或多个服务网格时。“能够用一个非常简单的 API 来管理这一切对我们的客户来说非常重要，”她说。

## **安全**

安全性是组织使用服务网格的三个主要原因之一，但它也可能在基础设施中引入安全漏洞。尽管组织完全有可能自己修补安全漏洞，但最终用户通常不像商业服务网格提供商那样技术复杂或了解最新的常见漏洞和暴露(CVE)。

“阿斯麦是安全早期披露名单的一部分，”詹金斯解释说。“像许多其他拥有开放核心产品的供应商一样，我们也在向客户发布产品之前测试和强化我们的产品，因此它往往更少错误，更安全。

对于需要其基础设施尽可能保持安全但没有内部资源或专业知识的组织来说，商业服务网格可以提供帮助。

## **技能差距**

设置 Istio 或者 Linkerd 之类的东西很难吗？是也不是，各种消息来源都同意。

“技能差距是绝对真实的，”詹金斯说。但这并不是真正的服务网格技能差距，而是容器/Kubernetes/云原生技能差距。“如果你已经非常流利地使用 Kubernetes，Istio 或 Linkerd 将非常容易掌握。如果你是容器和容器编排领域的新手，有很多东西需要学习。”

无论成熟度如何，商业产品的优势之一就是支持。从纯粹的开源服务网格中获取建议或故障排除并不容易。对于一些组织来说，这并不重要，但对于其他组织来说，在出现问题时有人可以打电话的知识是至关重要的，甚至可能被纳入公司治理政策。

Jenkins 说，在 Kubernetes 中使用 sidecar 代理服务网格的一个好处是，它允许一个较小的中央平台团队管理一个大型基础设施，并且它减少了应用程序开发人员管理与基础设施管理相关的任何事情的负担。

他说，使用商业服务网格提供商可以让组织进一步减少内部管理基础设施的需求。

奥斯汀同意，使服务网格成为“企业级”的因素之一是增加操作的简单性，使小型平台尽可能简单地管理大型应用程序套件。对于企业来说，这意味着能够将更多的工程资源用于功能开发和创造商业价值，而减少基础设施管理。

“安装服务网是容易的部分，”莱文说。“你必须配置它，操作它。”她说，Solo 致力于让配置和操作对最终用户来说尽可能简单。

## **复杂的生态系统**

也许对服务网格的一个误解是它们都是一样的。例如，Istio 向用户公开的配置选项比 Linkerd 多得多——而且是故意的。对于一些组织来说，这是一个优势。但 Linkerd 更固执己见的方法意味着它也更容易使用，这也是一个优势。其他选择，像领事、库马或灰质都有自己的好处。正确的选择取决于组织。

“Kubernetes 是容器编排的明显赢家，”Levine 说。“我认为服务网格是一个更加复杂的生态系统，不会只有一个明显的赢家。”

有没有一个明确的方法可以知道一个公司是否会从商业服务网格中受益？浮力银行的摩根提供了一个清晰的晴雨表。“如果你是一家过去在纯开源方面非常成功的公司，这可能意味着你在开源服务网格方面也会成功，”他说。“如果你是那种往往需要大量帮助的公司，这是一个信号，表明你也需要服务网格方面的帮助。”

Aspen Mash 和 HashiCorp 是新堆栈的赞助商。

来自 Pixabay 的 Alehandra13 特写图片。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>