# Kubernetes 分销还是香草 Kubernetes？

> 原文：<https://thenewstack.io/kubernetes-distribution-or-vanilla-kubernetes/>

[](https://www.linkedin.com/in/catherinepaganini/en/)

 [凯瑟琳·帕格尼尼

凯瑟琳·帕格尼尼在 Kublr 领导营销工作。从战略到战术，Catherine 帮助 Kublr 宣传云原生技术的无限力量，塑造品牌，并与增长保持同步。在加入这家科技初创公司之前，凯瑟琳在博思艾伦汉密尔顿和华盛顿邮报营销 B2B 服务。](https://www.linkedin.com/in/catherinepaganini/en/) [](https://www.linkedin.com/in/catherinepaganini/en/)

最近，我看到一篇文章，作者是一位备受尊敬的记者，他的结论是，组织使用香草 Kubernetes 比使用 Kubernetes 发行版更好。在阅读了这篇文章之后，很明显，即使是这位已经报道该领域多年的作者，仍然很难理解生产级 Kubernetes 部署到底需要什么。这里是我试图带来一些清晰度。

在他的文章中，作者指出 Kubernetes 只有十几个组件，其中一些甚至是可选的。从这个前提出发，作者认为掌握它们并不难。是的，Kubernetes 可能只有十几个组件，但是要在生产中实现 Kubernetes，您需要的不仅仅是 Kubernetes。虽然陈述的论点代表发展，但它并没有转化为生产——这才是真正重要的。

## Kubernetes，堆栈中仅有的一项技术

对于生产级部署，您将需要一个完整的堆栈:编排(又名 Kubernetes)、容器运行时和操作系统、附加组件和扩展(如覆盖网络、DNS 等)。监控、日志记录、基础设施自动化、策略管理、安全强化等。您还需要集成现有的系统，如 RBAC、PKI 和身份管理(有关企业级 Kubernetes 平台应该处理什么的更多详细信息，请查看这个 [No-BS Kubernetes 清单](https://thenewstack.io/a-no-bs-checklist-for-kubernetes/))。一旦你认真起来，事情就会越来越多。

那么，你能在内部做吗？是的。但是，有许多活动部件必须进行适当的配置和微调，以提供企业所需的可靠性和安全性级别。这确实需要专业知识。你不能这么快就建成。

但是假设你成功地建立了一个内部平台，你仍然需要维护它。这意味着每季度更新 Kubernetes，并对所有其他组件进行同样的操作。虽然有些企业可能想走这条路，但它肯定会超出其他企业的能力。

另一种方法是利用 Kubernetes 发行版。这时，一个供应商采用了 vanilla Kubernetes——未修改的上游开源组件(尽管有些确实派生了它)——并添加了一些或所有上述功能。发行版的存在是因为它们比维护一个本土平台并使其与技术和生态系统保持同步所需的专家团队花费更少。

Kubernetes 分布在生态系统中扮演着重要的角色。对于一些公司来说，这是快速采用云原生堆栈的唯一方法。其他人可以也愿意选择自主开发的平台——这取决于他们的人力和财力。

## Kubernetes 发行是否意味着锁定？

作者确实提出了一个伟大的观点。当选择一个锁定你的发行版时，你就放弃了市场需求所急需的灵活性。这就是为什么我们在[ku bler 建立了一个完全可定制的平台，](https://kublr.com/)使用普通的上游 Kubernetes 组件，并与任何 Kubernetes 兼容的工具包一起工作。T4 有可能以开源的精神创建一个发行版，这取决于团队的愿景。

这里有两个关键发行版锁定警告标志:

1.  分叉的 Kubernetes :在这种情况下，该平台包含与上游 Kubernetes 或其他供应商不兼容的专有特性。如果使用，应用程序会被锁定。

2.  **供应商提供的 Kubernetes 集群依赖于供应商平台**:如果没有特定于供应商的附加组件或有效许可证，Kubernetes 集群将无法“生存”和/或使用。

作者还正确地指出，Kubernetes 发行版可能会消亡，这正是为什么您需要选择一个不会锁定您的发行版。

总的来说，你不能把库伯内特公司的产品和香草库伯内特公司的产品相比较——那是苹果和橘子的比较。一个是整个堆栈，而另一个只是生产中需要运行的一项技术。也就是说，让读者了解不同供应商设计决策的含义是很重要的。

云原生堆栈为企业提供了采用或构建灵活的模块化系统的机会，使他们能够适应市场需求，这可能是当今快速发展的技术环境中最重要的能力。将自己锁定在另一个堆栈中，会从总体上否定 Kubernetes 和云原生堆栈的好处。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>