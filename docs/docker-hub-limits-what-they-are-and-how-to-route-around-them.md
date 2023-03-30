# 码头枢纽限制:它们是什么以及如何绕过它们

> 原文：<https://thenewstack.io/docker-hub-limits-what-they-are-and-how-to-route-around-them/>

今年早些时候，Docker 宣布将对 Docker Hub 容器映像库的使用实施新的限制。该公司声称，此举对于管理超出其愿意继续作为免费服务提供的范围的外围用例是必要的。

当时，这些限制涉及图像的[存储](https://www.docker.com/blog/scaling-dockers-business-to-serve-millions-more-developers-storage/)长时间闲置，以及图像的[速率限制](https://www.docker.com/blog/scaling-docker-to-serve-millions-more-developers-network-egress/)，两者都将在 11 月 2 日颁布。虽然关于闲置存储库的限制被推迟了，但是拉取速率限制在本月早些时候生效，分别限制匿名和自由层用户每 6 小时 100 和 200 次图像拉取。然而，付费用户可以享受无限的图片吸引。

“我们现在有超过 1200 万开发人员，但我们发现只有极少数人在大量使用这个中心。因此，作为其中的一部分，我们看到了这一点，我们说，我们必须确保这是可持续的，真的，对双方都是如此。“它只影响了很小的一部分，大约 1.5%或更少的用户，所以有很多噪音，但我认为重要的是要强调，我们正在谈论的是超过 98%的用户没有看到任何影响，并保持原样，愉快地使用 Docker Hub。”

根据 Berkholz 的说法，该公司发现这一小部分用户实际上负责 Docker Hub 30%的流量。

“你不可能永远为所有人提供无限量的自助餐。你必须弄清楚如何让人们获得适量的食物。当我们解决这一问题时，我们希望确保绝大多数开发人员永远看不到这一点，永远不会遇到这种情况，”伯克霍尔茨解释道。“对于使用量非常大的一小部分用户，我们希望确保能够为他们提供价值，并确保我们能够让他们了解他们的使用情形，我们能够提供这些使用情形。”

尽管如此，一些公司已经通过博客帖子解决了这些变化，为开发者提供了他们自己的解决方案，OpenFaas 创始人 T2 表示，这个问题是许多用户，特别是那些运行 Kubernetes 的用户，现在需要准备的。

“我认为很多人对此有些自满，或者他们还没有触及他们将要触及的问题。当你想到 CI 产品时，它们对这些节点上的所有活动都使用共享 IP 地址，”Ellis 说。

在一篇详述[如何为 Docker Hub 速率限制](https://inlets.dev/blog/2020/10/29/preparing-docker-hub-rate-limits.html)做准备的博客文章中，Ellis 写道“Kubernetes 用户将受到最大影响，因为在开发过程中，随着容器的每次修订，多次推送和拉取图像是非常常见的。甚至引导一个有 10 个节点的集群，每个节点仅控制平面就需要 10 个容器，甚至在您开始实际工作之前就可能耗尽未认证的限制。”

> “付钱不是问题。这是一个问题，因为那些速率限制，就像如果它是每六小时 1000 到 5000，我们可能都会过得非常好，支付他们，并在我们需要的地方获得我们的注册机密。”亚历克斯·埃利斯

当然，正是在这些情况下，许多用户使用同一个 IP 地址，或者某个特定的工作流导致大量图像超过当前的速率限制，Docker 敦促用户获得付费帐户。对于个人用户，订阅费为每月 5 美元，而团队订阅费为每月 5 个用户，起价为 25 美元。然而，埃利斯认为，即使是付费用户，新的限制也会给 Kubernetes 的新手用户带来不必要的负担。

“对于 Kubernetes 的学习者来说，无论你选择哪种解决方案(包括支付 Docker Hub 账户)，这都将是一个额外的步骤，”埃利斯写道。“学习曲线已经够陡了，但现在需要在每个新集群上部署合适的解决方案，而不是安装 Kubernetes 并继续工作。”

对于那些希望绕过新限制的用户，Ellis 提供了许多解决方案，包括托管 Docker Hub 的本地镜像，使用 Docker Hub 的公共镜像，将自己的图像发布到另一个注册表，如果仍在使用 Docker Hub，则配置图像拉取秘密以通过 Docker 认证，并接收提升的 200 个速率限制或付费帐户的无限拉取。

为此，Ellis 创建了 [registry-creds](https://github.com/alexellis/registry-creds/) ，这是一个开源操作符，可用于将单个 ImagePullSecret 传播到集群中的所有名称空间，这样就可以通过身份验证提取图像，并使 Kubernetes 的用户更容易从 Docker Hub 消费图像。虽然该工具旨在“缓解开发人员和 Kubernetes 新手的日常生活”，但他也建议使用 Argo、Flux 或 Terraform 等工具来管理生产中跨名称空间的秘密。

就替代方案而言，有几种，尽管每一种都应根据其自身的条件和限制来考虑。目前，GitHub 在其 [GitHub 容器注册处](https://github.com/features/packages)提供无限量的公共图像，谷歌在其自己的镜像上提供[缓存的 Docker Hub 图像](https://cloud.google.com/container-registry/docs/pulling-cached-images)，AWS 为镜像提供私人托管，[表示计划“在几周内”推出](https://aws.amazon.com/blogs/containers/advice-for-customers-dealing-with-docker-hub-rate-limits-and-a-coming-soon-announcement/)公共容器注册处与此同时，[认为](https://tanzu.vmware.com/content/blog/harbor-to-the-rescue-operating-a-secure-registry-without-restrictive-pull-policies)Harbor“可以通过复制功能和代理缓存功能来帮助您减轻即将到来的 DockerHub 限制的影响”，GitLab 已经向[用户提供了关于如何“减少从 CI/CD 基础架构调用 Docker Hub 的次数”的指南](https://about.gitlab.com/blog/2020/10/30/mitigating-the-impact-of-docker-hub-pull-requests-limits/)，以及[开源其依赖代理](https://about.gitlab.com/blog/2020/10/30/minor-breaking-change-dependency-proxy/)，GitLab 核心用户可以免费“代理和缓存来自 Docker Hub 的图像或来自任何受支持的公共存储库的包”

一些用户可能会最强烈地感受到这些速率限制变化的影响，他们是开源项目，这些项目通常已经受到资金和时间的限制，Docker 已经为那些符合条件的项目提供了无限制的图像拉取。要求包括发行商 Docker 名称空间内的所有回购必须符合开放源代码倡议(OSI) [对“开放源代码”的定义，](https://opensource.org/docs/osd)根据 OSI 批准的[开放源代码许可证](https://opensource.org/licenses/alphabetical)分发图像，并且是“公共和非商业性的”项目必须每年[提交一份申请](https://www.docker.com/community/open-source/application)，对于那些获得批准的项目，有一份他们必须承诺参与的“联合推广项目”清单，包括“博客、网络研讨会、解决方案简介和其他宣传材料”

伯克霍尔茨认为这些要求是合理的，对所有参与者来说都是等价交换。

伯克霍尔茨说:“希望这不是一个过分的要求，因为我们代表我们免费向他们提供东西，因为我们关心社区的维持，我们能够让这些东西对每个人都有意义，而不是要求人们到这里来写 70 篇博客文章，每周做一次网络研讨会或其他什么。”“我们能够利用我们试图提供的各种东西来帮助开源社区，并从中获得一点好处，使其成为一种公平的价值交易，因为这将使我们这边的计划能够持续下去。”

对于埃利斯来说，开源的要求，就像速率限制本身一样，显得有点过于激进，他担心最终的结果不会是 Docker 得到报酬——他鼓励所有人都这样做——而是整个事件将以支离破碎而告终。

“最终的结果将是许多支离破碎的解决方案。就像我们在 CNCF 有 20 个无服务器项目，然后有几个消失了，我们会得到同样的东西；每个人都将建立公共集装箱注册，每个人都将试图解决这个问题，并获得这些客户的一部分，”埃利斯说。“真正会影响人们的是开发者体验。如果你是一名试图学习 Kubernetes 的新开发人员，这会给你带来摩擦。”

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>