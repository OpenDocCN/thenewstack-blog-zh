# Sysdig 为 Kubernetes 带来零信任网络安全

> 原文：<https://thenewstack.io/sysdig-brings-zero-trust-network-security-to-kubernetes/>

本周在 kube con+CloudNativeCon North America 大会上，集装箱安全公司 [Sysdig](https://sysdig.com/) 为 Kubernetes 带来了其零信任安全方法，推出了针对 Kubernetes 的零信任网络安全。该方法通过使用 Kubernetes 的本地策略添加网络可见性和自动规则创建，扩展了该公司通常的容器扫描和运行时安全性方法。

由 Forrester Research 定义并由 Google 推广的[零信任](https://thenewstack.io/beyondcorp-google-ditched-virtual-private-networking-internal-applications/)安全模型与传统安全方法的不同之处在于，默认情况下没有任何东西是可信的，无论它可能位于何处，而传统方法可能允许您的网络或应用程序中的任何东西与同一边界内的任何其他东西自由交互。在云本地术语中，这可能意味着一个微服务与另一个微服务对话，只要它位于同一个 Kubernetes 节点上。

Sysdig 的新方法允许其用户利用 Kubernetes 的本地策略，通过更容易地设置策略，然后查看这些策略的效果，来实施零信任安全状态。虽然这听起来很简单，但 Sysdig 产品副总裁 Knox Anderson 解释说，设置 Kubernetes 网络策略通常是一个难点。

“我们可以把实施时间从几周缩短到几个小时，”安德森说。“通过 Sysdig 提供深入的可见性，我们确实使公司采用 Kubernetes 网络政策的过程变得更加容易。客户将能够轻松地查看我们的拓扑图，了解服务到服务的通信，决定他们希望允许什么，然后我们将据此自动创建 Kubernetes 网络策略，然后应用到他们的集群。"

[https://www.youtube.com/embed/lgIB4EItah4?feature=oembed](https://www.youtube.com/embed/lgIB4EItah4?feature=oembed)

视频

提到的拓扑图是此版本中的另一个新功能，它允许用户可视化进出特定 pod、服务和应用程序的所有通信。安德森说，通过地图和自动规则创建的结合，这解决了行业中的一个特殊差距。

“我们从客户那里看到的主要挑战是，应用团队有应用 A 到应用 B 的上下文，但他们不知道 Kubernetes 网络策略是如何工作的。然后，运营团队知道如何编写 Kubernetes 策略，但不知道在应用程序级别，哪些应用程序应该相互通信。因此，我们真的在帮助弥合开发商和运营商之间的鸿沟，”安德森说。

他提到，Kubernetes 网络策略的使用也是区别于其他人解决问题的方式，而不是使用中间人类型的方法，后者可能会覆盖二进制文件或覆盖 runC 或修改 IP 表。这些方法虽然有效，但也可能引入延迟，而使用 Kubernetes 网络策略不会出现这种延迟。Sysdig 首席营销官珍妮特·松田隼说，这也让事情变得简单，在处理安全问题时，这总是一个好主意。

“我们继续增加围绕零信任的功能，以确保即使 Kubernetes 在默认情况下是开放的，我们也能让开发人员和安全团队更容易地合作，以实施这些零信任控制。我们采用的方法是使用 Kubernetes 的原生控件，坚持开源控件，而不是添加另一个难题，”松田隼说。“Kubernetes 网络已经够复杂了。你不希望有一个安全工具做一些与 Kubernetes 预期的宇宙状态相冲突的事情。”

Sysdig 方法的最后一个部分是 Sysdig Audit Tap，它使 DevOps 团队能够识别和监控由一个进程建立的每个连接，即使连接不成功。松田隼解释说，有了这个，Sysdig 用户可以验证他们的网络策略没有引起任何问题，而是提供了他们想要的零信任环境。

松田隼说:“在网络安全方面，这种审计选项卡功能比零信任更广泛，但它是一个重要的组成部分，因为一旦你制定了这些政策，你就会说，‘这些是被阻止的网络连接，这些是正在发生的网络连接’，并真正验证你是否正确实施了这些政策。”。“这可以帮助您了解，可能有人试图攻击您的环境，也可能是您制定了错误的策略。“预先计划，实施，然后检查发生了什么”的回路实际上是零信任情况下你需要的闭环。”

新的功能将作为 Sysdig 企业级的一部分免费提供。

由[杰森·登特](https://unsplash.com/@jdent?utm_source=unsplash&utm_medium=referral&utm_content=creditCopyText)在 [Unsplash](https://unsplash.com/s/photos/enforcement?utm_source=unsplash&utm_medium=referral&utm_content=creditCopyText) 上拍摄的特写图片。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>