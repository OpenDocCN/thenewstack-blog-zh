# Argo CD 和 OpenShift 如何为开发人员启用 GitOps

> 原文：<https://thenewstack.io/how-argo-cd-and-openshift-enable-gitops-for-developers/>

[](https://www.linkedin.com/in/alhandy/)

 [亚历克斯·汉迪

亚历克斯是红帽公司的技术营销经理。在他之前的生活中，他报道了第一台 iMac 的发布，然后开始了 20 多年的科技记者生涯。](https://www.linkedin.com/in/alhandy/) [](https://www.linkedin.com/in/alhandy/)

Kubernetes 和 Red Hat OpenShift 为管理员和操作人员打开了一个可能性的世界，但是让开发人员进入这样一个平台需要时间和精力。对许多人来说，这意味着彻底改变开发者的工作流程，加入新的工具、平台和中介。这就是为什么 GitOps 已经成为基础设施管理的时尚:Git 使生成文本资产(无论是代码、配置还是数据)的分布式工作流变得有意义。

对于 Kubernetes 用户，管理员可以使用 [Argo CD](https://argoproj.github.io/argo-cd/) 将他们基于 git 的意愿强加到他们的集群上。但是对开发人员来说，做同样的事情有点棘手。OpenShift 消除了这种复杂性，并向开发人员扩展了 Argo CD 的功能，这些功能受到名称空间的限制。

那么 Argo CD 到底是什么？用最简单的话来说，它是运行在集群内部的一段代码，并保持它锁定在 git 上描述的任何配置中。因此，如果有人登录到您的集群并更改了配置，Argo CD 会自动将所有内容恢复到与集群相关联的 git 存储库中的配置文件的任何版本。

当然，Argo CD 做的不止这些，但是从集群管理的角度来看，它是配置更改的看门人，强制这些更改在 git 上发生，在那里它们将被记录和跟踪。

然而，Argo CD 不仅仅是为那些希望为开发人员启用集群的管理员提供连续部署。Argo CD 也可以部署给开发人员使用。通过在 OpenShift GitOps 中进行正确的配置，Argo CD 可以被限制为仅在名称空间中工作，从而允许个人开发人员在个人应用程序中使用它。

这是 Argo CD 可以实现的一组重要的限制。对于管理员来说，Argo CD 几乎是一个安全工具，尽管只是执行最后一英里的连续部署。对于开发人员来说，Argo CD 几乎就像一个机器人系统管理员，完全绑定到开发人员指定的配置文件。

开发人员可以使用 Argo CD 以最小的努力保持他们的部署环境在线。一旦正确配置并集成到适当的 CI/CD 管道中，Argo CD 就可以成为开发人员一键部署操作的一部分，甚至可以避开开发人员已经在使用的 git 工作流，保持不可见。考虑到开发人员已经熟悉 git 及其工作方式，扩展该工作流以覆盖实际的测试环境和生产部署只能通过消除额外的步骤来加快整体开发速度。

## 企业中的 Argo 光盘

这是 Argo CD 对企业用户吸引力的一部分。在兼容商业软件的世界里，公司经常必须证明某些应用程序正在运行并保持跟踪。他们还必须严格跟踪对该软件所做的更改，以防出现问题，并且出于法律原因需要验证合规性。

通过 Argo CD 将所有的软件变更引入 git，也有助于将这些变更整合到一个 git 位置，允许对这些变更进行验证、跟踪并与用户关联。几乎不可能对 git 存储库中的代码进行秘密更改，因此简单地围绕这个平台构建一个流程可以增强安全性和记录保存。

这就是为什么 Red Hat OpenShift 在其整个平台上采用了 GitOps 方法和工具。OpenShift GitOps 使用 Argo CD 将更改推送到集群，并防止未跟踪的更改被实现。OpenShift 还包括将开发人员对 Argo CD 的使用限制在其名称空间的能力，允许他们获得所有好处，而不需要集群上的每个人都使用它。

这就是企业需要从他们的软件中得到的:遵从性和可追溯性。对于开发人员来说，当部署例程要求他们遵循 80 页的指南并填写大量表格来验证他们构建的软件的完整性时，这可能会成为一种负担。

由于人容易犯错，将他们从部署管道中完全移除有助于提高流程的可预测性，并将故障排除整合到单一的线性行为轨迹中，而不是某种无法追踪的瀑布方法。

Argo CD 甚至具有发出警报的能力，因此它也可以连接到警报系统中。如果您的管理员想知道每次部署一个新版本的应用程序，Argo CD 可以给出警告。如果这些管理员想知道 Argo CD 何时因为集群内部发生了变化而重新部署某些东西，它也可以为此发出警报。

所有这些都与企业更快、更安全地部署更多应用程序和创新功能的需求紧密相关。作为大多数收入流的中心，业务应用程序直接驱动着利润，服务中断也是如此。安全问题使整个事件复杂化，增加了每次部署的风险。

但是，当这些部署被大量跟踪和监控，并且来自存储在基本上是一个可靠的软件存储介质中的代码时，git 使用文件的哈希作为其内部标识符。因此，如果文件以任何方式更改，ID 也会更改。使用 git 的行为以数学上可证明的多种方式增强了安全性。例如，获取一个软件并对其进行修改，然后试图让它生成与该软件的前一版本相同的散列，本质上比实际利用该软件本身更困难。

事实上，git 在基础级别内置了许多安全特性:这是 Linus Torvalds 编写的一个好处。Argo CD 利用了这些内置的安全功能和特性，并在整个软件生命周期中扩展它们。Argo CD 没有引入专门关注安全性的其他层，而是简单地将现有的保护扩展到部署过程。

通过将其绑定到名称空间，它可以将这些保护扩展到开发过程——以及整个开发团队。GitOps 如今是一个常见的流行词，但在未来，它可能会变得像创可贴或面巾纸一样通用。它不再是运行 CI/CD 的规定方法，而是我们开发和部署软件的简单方式。这是一个太引人注目和太强大的工作流，不能不成为默认的，就像 git 已经成为默认的分布式源代码库一样。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>