# GitOps 的问题——以及如何解决它们

> 原文：<https://thenewstack.io/the-problems-with-gitops-and-how-to-fix-them/>

[Codefresh](https://codefresh.io/) 赞助本帖。

 [维克多·法西奇

Viktor Farcic 是 Codefresh 的首席 DevOps 架构师，Google 开发者专家和 Docker Captains 组的成员，也是一名出版作家。](https://www.linkedin.com/in/viktorfarcic/) 

GitOps 是一种管理系统实际状态的方法，通过存储在 Git 中的期望状态的定义。你可能已经知道 GitOps 是什么，以及它的所有好处。如果你不知道，请观看[什么是 GitOps，我们为什么想要它？](https://youtu.be/qwyRJlmG5ew)。在这篇文章中，我们将忽略好的一面，关注坏的和丑陋的一面。

在接下来的文章中，我会说 GitOps 作为一个想法是很棒的，但是我们甚至还没有接近让这个想法在实际意义上有用。我甚至会说，有许多工作要做，我们需要按下重置按钮。现在，让我集中讨论我们在 GitOps 中面临的问题。

让我给你总结一下这些问题:

*   GitOps 被误解了。
*   GitOps 不仅仅是关于 Kubernetes。
*   GitOps 工具并没有推广 GitOps 原则。
*   我们甚至经常无法在 GitOps 工具中应用 GitOps 原则。
*   我们没有工具来反映 Git 中集群内部发生的变化。
*   可观察性不成熟。
*   没有既定的模式。
*   持续交付和 GitOps 之间的联系还没有很好地建立起来。
*   大规模运行 GitOps 极具挑战性。
*   管理秘密是一个大问题。

现在让我们进入兔子洞，看看我们在采用 GitOps 时所面临的痛苦。

## **吉托普斯被误解了**

对什么是 GitOps 有一个误解。像许多其他受欢迎的浪潮一样，软件公司也乘着这股浪潮，将“GitOps”标签贴在他们的产品上。正如今天每个工具都是 DevOps 工具一样，无论该工具做什么，甚至是 DevOps 是什么，今天许多工具都被(重新)标记为 GitOps 工具。公司试图向我们推销这样一种理念，即无论他们的工具在做什么，GitOps 就是这样。因此，我们在争论它是什么，不是什么，而实际上它是一个基于一些易于解释的原则的简单概念。

一切都被定义为代码；代码存储在 git 中；git 包含所需的状态；机器正在把实际的东西汇聚成理想的状态。就是这样。这就是全部了。好不容易到了那里，却直截了当的说明了是什么；如果这个解释被接受，那么区分那些帮助我们实现 GitOps 的工具和那些没有帮助我们实现 GitOps 的工具就更加容易了。

## **GitOps 不仅仅是关于 Kubernetes**

我对 GitOps 背后的一些想法的发起人更失望。例如，“GitOps 是一种进行 Kubernetes 集群管理和应用交付的方式”的定义是误导性的。GitOps 不仅仅是一种进行“Kubernetes 集群管理”的方式 Kubernetes 被大量采用的事实并不意味着它是每个人唯一关心的事情。GitOps 是关于别的东西的，而且这个东西比 Kubernetes 要宽泛得多。即使是那些完全拥护 Kubernetes 的人也不会声称一切都是 Kubernetes。有要管理的节点。有人脉。还有第三方服务。无服务器应用越来越广泛。诸如此类。

事实上，有人有一个专注于 Kubernetes 的解决方案并不意味着 GitOps 只是关于 Kubernetes 集群内部的状态。这是工作的方式。这是一种定义事物状态的方法，不管它是什么。即使你百分之百依赖 Kubernetes，它也不会凭空出现，也不会自己管理。GitOps 应该对此有所帮助，而不是局限于非常狭窄的范围。

前两期可以归为不好，现在越来越难看了。

## **GitOps 工具没有推广 GitOps 原则**

GitOps 工具，即使是那些代表业界闪亮灯塔的工具，也不是真正在推广 GitOps。让我重复一遍。GitOps 工具并没有推广 GitOps 原则。即使他们这样做了，许多人不知何故认为它适用于其他人，他们是例外。为了证明这一点，我们可以看看安装两个最流行的 GitOps 工具的“默认”说明: [Flux](https://www.weave.works/oss/flux/) 和 [Argo CD](https://argoproj.github.io/argo-cd/) 。

在我们继续之前，让我强调一下，我认为这两个工具都非常优秀。这并不是试图“击败”他们，而是表明我们仍然处于采用 GitOps 的非常早期的阶段，它还没有铭刻在我们的脑海中。

首先，Flux 最初没有试图为安装提供任何声明性定义，至少没有从初始安装页面提供。没有人试图引导我们在应用到集群之前将某些东西定义为代码并存储在 git 中。

随着 Flux v2 的推出，这一切都改变了。该工具改变了安装过程，现在它创建一个 git repo，推送 Flux 清单，然后才安装 Flux。从那时起，对 Flux 的任何更改都可以通过对相关的存储库进行更改来完成。干得好 Flux！

使用 Argo CD，我们可以获取 install.yaml 清单，将其存储在 git 中，然后将其应用于实际状态。我们可以很容易地将它与任何 CD 工具挂钩，并创建一个 webhook，在定义发生变化时通知它。

第一眼看上去，Argo CD 至少给了我们一个 YAML 文件，我们可以在应用它之前将它存储在 git 存储库中，从而给了我们一个遵循 GitOps 原则的假象。但是，它选择以可以存储在 git 中的声明性 YAML 格式来定义，这似乎更像是一个幸运的意外。事实是，当我们向下滚动同一页时，我们会发现如下的例子。

```
```bash
kubectl patch svc argocd-server  \
-n  argocd  \
-p  '{"spec": {"type": "LoadBalancer"}}'
```

```

如果我们继续向下滚动，我们可以找到类似下面的命令，将一个集群添加到它的注册表中。

```
argocd cluster add docker-for-desktop

```

现在，我将跳过使用这些工具是否真的是 GitOps 的讨论。在这种情况下，Argo CD 从一开始就没有遵守“以声明方式描述整个系统”的原则。它并没有试图“推动”用户接受期望的状态应该存储在 git 中的想法。第一次接触 Argo CD，以及直到最近接触 Flux，tools 告诉我们，“我们是例外；那些规则适用于其他人，但不适用于我们。”

说实话，市场上的大多数工具也是如此，包括那些自称为 GitOps 的工具。我挑以上两个，多半是因为他们优秀，受欢迎，而不是因为他们比别人差。

在本文中，我们探讨了我的候选列表中的前三个 GitOps 问题。我将在后续的两篇文章中讨论其余的内容。

通过 Pixabay 的特征图像。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>