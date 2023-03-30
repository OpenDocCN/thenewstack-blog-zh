# Kubernetes 上三角帆开发的新方法

> 原文：<https://thenewstack.io/a-new-approach-to-devops-with-spinnaker-on-kubernetes/>

[库伯内特](https://thenewstack.simplecast.com/episodes/a-new-approach-to-devops-with-spinnaker-on-kubernetes) 用三角帆开发新方法

随着组织将 DevOps 视为实现数字化转型的手段，他们意识到必须加快端到端软件交付流程，并使其更加安全。

“这看起来像是一个煮沸海洋类型的问题。这就很难弄清楚你将如何从它那里逐渐获取价值，”谷歌云平台 DevOps 部门的产品经理 Andrew Phillips 在本期《新堆栈制造商》中说道。

通过将开发人员反馈周期从展示过程中分离出来，组织可以找到一个易于管理的起点。Phillips 说，像 Spinnaker 这样的工具就是为了这个目的而构建的，“提供一个抽象，以便开发团队可以有一个简化的体验，同时仍然为运营团队提供以对组织最有意义的方式管理、调整和定义它的能力。”

人们经常讨论抽象来为如何管理应用程序架构提供背景。Kubernetes 引入了基础设施的新抽象。菲利普斯说, [Spinnaker](https://www.spinnaker.io/) 这样的技术允许在企业工作的人创建适合他们的抽象概念。

总的来说，软件交付并不完美。定义模式并不容易。归根到底是什么藏物被释放了。通常，遵循 DevOps 实践的 IT 人员发现他们自己是从模板的角度来思考的，这最终会成为管理复杂性的一项相当大的练习。

## Spinnaker 有谷歌的支持

公司必须为正在运行的候选人定义展示流程，并以一种能够识别 [Kubernetes](https://kubernetes.io/) 清单有效性的方式来管理该流程。清单必须是健康的。Kubernetes 允许团队创建一个“恢复流”,即所谓的保存状态和清单。如果您能够以健康的方式提交清单，那么它就可以作为您恢复和复制该状态的模板。但是你是怎么做到的呢？

它归结为给定一个团队或组织的上下文，什么实现是最合适的。它可以使用 Spinnaker 之类的工具，也可以使用 [GitOps 之类的拉请求方法。](https://thenewstack.io/gitops-git-push-all-the-things/)随着应用程序开发架构变得越来越复杂，并且需要一个环境来应对这种规模，Spinnaker 允许组织成长。谷歌已经将其开发工作放在 Spinnaker 之后，现在正在投资与 Kubernetes 的契合度。

Spinnaker 最初由网飞开发，它提供了一个明确的用户界面来了解应用程序是如何运行的。使用 Spinnaker，用户不必检查模板。清单更新后会在 Kubernetes 中自动运行。

现在的挑战是，当组织采用 Kubernetes 时，要为他们找到管理应用交付的正确方法。Kubernetes 的早期用户正在构建他们的平台。Spinnaker 是一种为应用程序部署软件的方法——用于发布候选工件和配置。
这说明了为什么谷歌投资支持 Kubernetes，以便应用程序可以在云本地、多云和混合场景中进行管理。

### 在这个版本中:

[5:00:](https://thenewstack.simplecast.com/episodes/a-new-approach-to-devops-with-spinnaker-on-kubernetes?t=5:00) 子单元的概念、开发反馈周期，以及在使用 Kubernetes
[9:54:](https://thenewstack.simplecast.com/episodes/a-new-approach-to-devops-with-spinnaker-on-kubernetes?t=9:54) 谷歌认为重要的工具生态系统中的桥梁的背景
[14:00:](https://thenewstack.simplecast.com/episodes/a-new-approach-to-devops-with-spinnaker-on-kubernetes?t=14:00) 当用户采用 Kubernetes 基础设施时，你开始看到哪些模式在演变？
[21:15:](https://thenewstack.simplecast.com/episodes/a-new-approach-to-devops-with-spinnaker-on-kubernetes?t=21:15) 当你看到 Spinnaker 这样的工具出现时，你在看什么，在围绕 Kubernetes 构建生态系统时，你应该考虑什么？
[30:59:](https://thenewstack.simplecast.com/episodes/a-new-approach-to-devops-with-spinnaker-on-kubernetes?t=30:59) 如何看待那个语境下的现代化身份，以及 Spinnaker 的建筑历史？
[34:11:](https://thenewstack.simplecast.com/episodes/a-new-approach-to-devops-with-spinnaker-on-kubernetes?t=34:11) 在 Kubernetes 景观中工作的其他工具和挑战

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>