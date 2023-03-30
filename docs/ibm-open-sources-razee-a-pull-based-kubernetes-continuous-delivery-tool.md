# IBM 开源 Razee，一个基于拉的 Kubernetes 连续交付工具

> 原文：<https://thenewstack.io/ibm-open-sources-razee-a-pull-based-kubernetes-continuous-delivery-tool/>

几年前，当 IBM 着手建立其 IBM Kubernetes 服务(IKS)时，它发现它缺少一个主要的组成部分——一个持续的交付系统，可以提供它所做的事情所需的规模、速度和可见性。正如 IBM Cloud 和 Istio 的杰出工程师 [Daniel Berg](https://www.linkedin.com/in/daniel-berg-18b2bb3/) 在接受新堆栈采访时解释的那样，该团队发现自己陷入了一个难题，只有通过构建自己的连续交付(CD)软件才能解决。上个月在巴塞罗纳举行的 KubeCon + CloudNativeCon 大会上，IBM[开源了这个项目，现在叫做](https://www.ibm.com/cloud/blog/announcing-razee)[raze](https://razee.io/)。

“如果你愿意的话，我们掉进了构建一套微服务的陷阱，我们最终以整体交付。我们掉进了那个陷阱，”伯格说。“每个团队都会构建他们自己的微服务，并每天进行开发，但当我们进行持续集成和持续交付流程时，我们会尝试对所有协同工作的组件进行大量测试，然后将其作为测试单元部署到我们的环境中。使用我们传统的自动化系统变得极其困难、容易出错且复杂。”

Berg 说，他们开始构建 Razee 时，将速度、可见性和可伸缩性作为核心原则。Razee 的一个主要区别是，它的操作与其他 CD 系统不同，因为它是基于拉的，而不是推的，因此提供了自我更新的 Kubernetes 集群。这是通过在每个集群中插入一个代理来实现的，该代理可以检查规则更新，然后根据需要使用 Kubectl 和 Kubernetes API 进行更新。与此同时，该代理提供了对运行内容和运行位置的可见性，只要它向中央系统检查是否有更新。Berg 解释说，这是通过他们的引导过程实现的，通过使用功能标志，可以一次配置大量集群。

“使用 Razee，规则引擎是完全可插拔的。因此，你可以有一个非常简单的规则引擎，它是使用 YAML 终结符静态定义的，或者你可以有一些更复杂的东西，如与 launch crystally 集成，为你提供功能标记和动态规则评估，”Berg 说。

[https://www.youtube.com/embed/HXF0QzxUBTw?feature=oembed](https://www.youtube.com/embed/HXF0QzxUBTw?feature=oembed)

视频

Razee 的起源可能解释了它不像其他 CD 系统那样运行的事实。相反，Berg 描述了一种与 Kubernetes 紧密耦合的工具，他说这种工具可以与各种可用的托管和引导的 Kubernetes 系统一起工作。

“我们明确地将 CI(持续集成)从 CD 中分离出来。Razee 是一个分配系统。你可以称之为一个连续的输送系统，但最终它是一个 Kubernetes 资源分配系统，”伯格说。“它列出了分布在这些集群中的内容。因此，您可以看到它被推送到这些集群中的内容，这是一种推动资源分布到集群中的机制，这意味着它可以管理 Kubernetes 集群中的任何资源，包括 CRD，包括控制器，包括角色、角色绑定、部署、服务等等。如果是 Kubernetes 中的资源，Razee 可以管理它。”

更深入一点，Berg 说，虽然基于拉动的模型并不完全是 Razee 独有的，但内置的智能却是。

“还有其他基于拉取的工具，但它们是通用的自动化工具，您必须围绕它们构建智能。Razee 是专门为 Kubernetes 调整的。这不是一个通用的分配系统。举例来说，它不会将代码分发到虚拟机。它不是为此而设计的，”伯格说。“这是为 Kubernetes 设计的。它不会为混合云中的人们解决所有部署和分发问题，因为它不是为此而设计的。”

事实上，该项目的 [GitHub 存储库](https://github.com/razee-io/Razee)用特定的术语将该工具描述为“一个由 IBM 开发的开源项目，用于自动化和管理跨集群、环境和云提供商的 Kubernetes 资源的部署，并可视化您的资源的部署信息，以便您可以监控部署过程并更快地发现部署问题。”

尽管如此，Berg 说公司现在已经发布了它，希望发现是否有其他用例可能被它忽略了。

“我们为自己内部构建了这段代码。我们想，让我们打开它，这样我们就可以开始讨论了。我们将它用于一个非常特殊的用例。可能还有其他人。为了了解其他用例，人们需要访问它，”伯格说。“所以这就是我们把它开源的原因，这样我们就可以公开谈论它并获得反馈。如果有兴趣通过 SIG[特别兴趣小组]或可能的 CNCF[云计算原生计算基金会]将其贡献给 Kubernetes，我们愿意进行对话，但这不是我们推出它的主要前提。这是为了让它到达最终用户手中，获得一些反馈，也许会使它朝着最初没有打算的方向发展。”

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>