# 使用定制控制器解决 Kubernetes 配置难题

> 原文：<https://thenewstack.io/solving-kubernetes-configuration-woes-with-a-custom-controller/>

[](https://pusher.com/)

[Joel Speed](https://pusher.com/)

[Joel 是 Pusher 的云基础设施工程师，致力于构建他们的内部 Kubernetes 平台。他已经在 DevOps 工作了四年多。最近，他一直专注于扩展 Kubernetes 的项目，构建准入和定制资源控制器，以改善开发人员在该平台上的体验。Joel 热衷于自动伸缩、部署管道、认证和授权。他还为 Pusher 工程团队制造并维护了一个聊天机器人 Marvin。](https://pusher.com/)

[](https://pusher.com/)[](https://pusher.com/)

两年前， [推手](https://pusher.com) 开始搭建一个基于 Kubernetes 的内部平台。当我们从单一产品过渡到多产品公司时，我们希望帮助我们的产品团队花更少的时间来担心基础设施等共同的问题，并能够将更多的精力放在为我们的产品编写业务逻辑上。

在此期间，我们的平台团队已经解决了许多 Kubernetes 无法开箱即用解决的问题。直到最近，我们还没有解决配置的问题。不幸的是，在普通的 Kubernetes 集群中，与大多数资源不同，对配置(存储在 ConfigMaps 和 Secrets 中)的更改不会触发集群内运行的应用程序状态的任何更改。

在我们的平台上运行的许多应用程序，无论是第一方还是第三方，都不能动态地重新加载它们的配置。当它们的配置被更新时，尽管装载到容器中的文件可能被更新(如果它们来自配置图)，但是应用程序不观察变化，并且仅在过程被重启时加载新的配置，或者更典型地，新的 pod 被创建并且现有的 pod 被终止。

由于 Kubernetes 通常会为您协调所需的状态，所以一个典型的用户可能会认为更新配置映射或密码会使应用程序加载新的配置。因为情况并非如此，所以用户很容易更新配置图或密码，而不替换安装配置的 pod，从而使运行配置不同于更新的期望配置。

## 我们的配置问题是什么？

通常在 Kubernetes 中，当你更新你想要的状态时，会有一些控制循环来查看世界的状态，并调整状态使其符合你想要的变化。当您为部署中的 Pod 更新模板时，部署控制器将用新的 Pod 替换所有现有的 Pod，以匹配更新的规范。

Kubernetes 中的配置存储在配置映射和机密中。这些通过文件挂载或环境变量挂载到 pod 中，以允许容器进程读取数据。然而，这种方法有一个问题。配置映射和机密都没有版本，也没有控制循环。虽然更新配置映射会更新 Pod 内的已挂载文件，但更新机密不会触发集群内的任何更改。

推料器平台上的产品依赖于一个称为桥的关键部件。网桥是我们入口层的一部分，将流量路由到后端服务，并在此过程中处理大量推送协议逻辑。不幸的是，网桥不能动态地重新加载它的配置。

该组件对于我们在该平台上运行的所有产品(Chatkit、Beams、TextSync)的运行至关重要，当它关闭时，其他一切都会随之关闭。

在过去的两年里，我们在这个平台上没有发生太多的事件(诚然，我们才发布了几个月)，但是当我们遇到中断时，事后分析几乎总是会得出相同的结论。桥内运行的配置不是它装载的配置映射内的配置。

大多数事件都是由一个基础架构团队对 Kubernetes 集群进行更改而引发的。我们不变地运行我们所有的机器，因此，当我们想要做出改变时，我们替换集群中的每个节点，并且依次替换每个单元。新的 pod 将从此时存在的任何配置开始。

我们发现，尽管我们有适当的程序，但在配置更新时，我们组件的 pod 并不总是被替换，在某些情况下，pod 仅在应用了损坏的配置后大约两周才被替换。如果您曾经遇到过同样的情况，您将会理解不知道发生了什么变化，并且在没有版本控制的情况下，无法回滚是多么可怕的事情。

## 我们如何解决这个问题

我们目前正在使用我们的 GitOps 项目 [Faros](https://github.com/pusher/faros) 来自动化我们的部署管道。我们的平台服务团队有许多服务不能动态地重新加载配置，并提出了对项目的关注。为了能够在 git merge 上同步配置更新，他们需要保证配置更新将被实际部署，并且在配置被破坏的情况下，有人将被通知 git 恢复他们刚刚部署的更改。

这就是我们的新项目 [Wave](https://github.com/pusher/wave) ，一个使用 [Kubebuilder](https://github.com/kubernetes-sigs/kubebuilder) 构建的定制控制器的用武之地。Wave 的作用是确保当一个配置图或密码被更新时，任何安装了所述配置图或密码的部署替换其所有的 pod。Wave 有效地推动了 Kubernetes 内置的 [部署](https://kubernetes.io/docs/concepts/workloads/controllers/deployment/) 控制器，并让它执行滚动更新，删除运行旧配置的 pod，并使用更新的配置创建新的 pod。

## Wave 是如何工作的？

与其他 Kubernetes 控制器一样，Wave 从 Kubernetes API 为部署对象订阅事件。这意味着，每当在任何部署上执行操作(创建/读取/更新/删除)时，Wave 都可以处理部署，并查看是否需要进行任何更改。

Wave 做的第一件事是检查部署上是否有 [注释](https://kubernetes.io/docs/concepts/overview/working-with-objects/annotations/)(wave.pusher.com/update-on-config-change:为真)。如果注释不存在，Wave 会忽略部署。这使得 Wave 成为一个选择加入的控制器，为了从 Wave 中受益，用户必须手动指定他们的部署由 Wave 管理。因此，部署到现有的 Kubernetes 集群是安全的，不用担心它会突然开始干扰不需要其更新触发功能的已部署工作负载。

其次，Wave 解析部署，并查找对配置映射的引用和装载到部署创建的 pod 中的秘密。然后，它获取每个配置映射和装载的机密，并使用可再现的算法，创建当前配置的散列。哈希表示来自所有配置映射和已装载机密的配置，只有在添加新装载、取消装载或修改装载数据中的任何字段时才会发生变化。

然后将该散列作为注释放置在部署中的 [Pod 模板](https://kubernetes.io/docs/concepts/workloads/controllers/deployment/#pod-template) 上。这就是我们利用内置 Kubernetes 部署控制器的地方。通过修改 Pod 模板的元数据，部署控制器将此视为更新，并开始处理部署更新策略。

总之，每当 config 被更新时，Wave 计算的散列将改变，Wave 将更新部署的 Pod 模板上的散列，然后部署控制器将读取更新策略，并通过创建新的副本集和新的 Pod 来开始新配置的展示。

由于 Wave 还订阅配置图和机密的事件，它可以使用 [所有者引用](https://kubernetes.io/docs/concepts/workloads/controllers/garbage-collection/#owners-and-dependents) 来跟踪哪些部署正在安装哪些配置图和机密，并且每当其中一个发生更新时，协调父部署以更新其散列。然而，我们不使用所有者引用的垃圾收集部分。一旦部署被标记为删除，Wave 将删除所有所有者引用，否则部署拥有的配置映射和机密也将被删除。

## 下一步是什么？

波尚未完成！目前只支持部署。将来，我们计划为 Wave 添加一个触发更新 [Daemonsets](https://kubernetes.io/docs/concepts/workloads/controllers/daemonset/) 和[statefullsets](https://kubernetes.io/docs/concepts/workloads/controllers/statefulset/)的功能。

我们已经将 Wave 部署到我们的系统中，并在我们的团队和更广泛的组织中实现了许多部署。自从开始使用它以来，我们已经更快地捕捉到损坏的配置(不再有生产事故),并且已经能够减少许多手动部署程序(部署配置，缓慢重启 pod)。

这个项目解决了我们最长期的问题之一。我们现在部署时更有信心，并且知道对所需配置的更新将在应用后立即运行。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>