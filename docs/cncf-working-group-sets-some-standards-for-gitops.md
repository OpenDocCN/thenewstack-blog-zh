# CNCF 工作组为“GitOps”制定了一些标准

> 原文：<https://thenewstack.io/cncf-working-group-sets-some-standards-for-gitops/>

来自 GitHub、微软、CodeFresh、 [Weaveworks](https://www.weave.works/?utm_content=inline-mention) 、[红帽](https://www.openshift.com/try?utm_content=inline-mention)和其他熟悉云的公司的工程师们已经联合起来，为 [GitOps](https://thenewstack.io/what-is-gitops-and-why-it-might-be-the-next-big-thing-for-devops/) 制定了一套定义和一致性规范。

这些工作都是通过[云本地计算基金会](https://cncf.io/?utm_content=inline-mention)的应用交付技术顾问小组完成的。上个月，团队[发布了](https://opengitops.dev/blog/1.0-announcement)[规范](https://github.com/open-gitops/documents/releases/tag/v1.0.0)的 1.0 版本。

“很多人认为他们在做 GitOps，因为他们在使用 git，他们在做拉请求，把改变推出去，”GitOps 工作组的联合主席 Leonardo Murillo 说。“我们希望社区开始看到 GitOps 不仅仅是包含 git 的 CI/CD。还有很多。”

他们从定义 GitOps 的核心原则开始，然后供应商可以解释这些原则，他们可以按照自己的方式自由地解释它们。

![Leonardo Murillo, a co-chair of the CNCF GitOps working group, sits down with TNS to discuss the OpenGitOps specification](img/e0b4e3779c1c7ae0809bd1a3efb4878b.png)

莱昂纳多·穆里略

根据该组织的说法，GitOps 必须满足这四个要求:

1.  ***声明性:**由 GitOps 管理的[系统](https://github.com/open-gitops/documents/blob/v1.0.0/GLOSSARY.md#software-system)必须以声明方式[表达其期望的状态](https://github.com/open-gitops/documents/blob/v1.0.0/GLOSSARY.md#declarative-description)。“*你不再给出指令，你在描述状态，”穆里略描述道。
2.  ***版本化和不可变:**期望的状态以一种实施不变性、版本化和保留完整版本历史的方式[存储](https://github.com/open-gitops/documents/blob/v1.0.0/GLOSSARY.md#state-store)。穆里略补充道:“你在你的系统中引入改变的唯一方法就是创造一个你想要的状态的新版本。”。*
3.  ***自动拉出:**软件代理自动从源代码中拉出所需的状态声明。*系统内的代理从存储库中提取所需的状态。
4.  ***持续协调:**软件代理[持续](https://github.com/open-gitops/documents/blob/v1.0.0/GLOSSARY.md#continuous)观察实际系统状态[尝试应用](https://github.com/open-gitops/documents/blob/v1.0.0/GLOSSARY.md#reconciliation)期望状态。Murillo 说:“(系统或软件的)理想状态是不断协调的。*

GitOps 不同于标准的连续交付(CD)系统，因为 CD 管道是强制性定义的。用户必须提供系统达到期望状态所需的所有动作的集合，之后不能保证系统保持在该状态，或者不知道采取什么动作来修复出故障的系统。

使用 GitOps，系统内部的代理总是在检查以确保系统处于期望的状态，如果系统中存在“漂移”,“协调循环”将通过从存储库中提取原始工件来自动将其返回到期望的状态。

Murillo 说:“你不是在编写管道，那里有 if-then 操作等等，你是在委派责任，将所有的复杂性封装到操作者的决策逻辑中。”

这种方法为用户提供了完全的可追溯性，每一个变化都会产生一个新的系统版本，如果需要的话，可以很容易地回滚到一个更早的版本。这种方法的另一个优点是:开发人员不需要访问他们的应用程序正在使用的集群。

GitOps 方法不仅限于应用程序维护。它还可以用于维护系统本身，支持[基础设施即服务](https://thenewstack.io/infrastructure-as-code-evolution-and-practice/) (IaaC)。有了 Kubernetes，它可以仅用于管理配置或服务。但是它也可以用于管理遗留应用程序。

该指南与供应商和实现无关。由系统集成人员决定使用哪些工具，并保持所需的状态。即使是构建 GitOps 名称的 [git](https://thenewstack.io/git-for-managing-small-projects/) 存储库也不是必需的依赖项。

## 把宠物变成牛

GitOps 模型可能影响深远，从应用程序管理扩展到集群甚至整个操作环境的统一管理。

Murillo 说，GitOps 模型可以“扩展到你的架构和环境的所有领域，这些领域是你最初不会考虑的”。

Murillo 说，GitOps 具有高价值的一个领域是车队管理，其中需要管理数百甚至数千个集群。与让所有这些集群自主更新相比，建立一个管道来将配置和软件更新推送到所有这些集群需要更多的工作。

云原生社区喜欢将容器视为“[牛而不是宠物](https://thenewstack.io/how-to-treat-your-kubernetes-clusters-like-cattle-not-pets/)”，因为它们应该被整体管理，而不是逐案管理。然而，Murillo 说，操作环境本身仍然被当作宠物。

“我认为我们仍然把环境当作宠物。我们给它们起了名字，“生产”和“登台”。“它们仍然是我们的宠物，”他说。GitOps 模型可以使组织朝着这些环境的一致性和可扩展性的方向发展。

“我认为你可以开始考虑短暂的环境——只是繁殖、创造和破坏环境，”穆里略说。

## 当事情出错时

现在 1.0 版本已经完成，该小组正在考虑扩展标准以定义更多的功能。例如:在 GitOps 环境中如何处理事件管理。安全管理、凭证管理、车队管理也是如此。

“如果您的群集出现故障…如果您的应用程序出现故障，在 GitOps 中应该遵循什么程序？”

例如，对于可编程基础设施，如果管理员只是通过 SSH 连接到路由器并进行简单的更改，例如修复错误的 IP 号码，这是不可取的。这是一个简单但长期坚持的实践，尽管如此，配置管理的理想并不赞成这种实践，因为它将部署抛出其“期望的状态”(并且可能是一个安全隐患)。

因此，该小组正在寻找处理简单事故管理活动的适当机制。在这种情况下，您会暂停持续对账吗？你如何处理补丁？

穆里略说，该组织希望回答“在 GitOps 环境中什么是正确的原则”的问题。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>