# Google Next 将 Kubernetes、无服务器和类似虚拟机的隔离带到了云中

> 原文：<https://thenewstack.io/google-next-brings-kubernetes-serverless-and-vm-like-isolation-to-the-cloud/>

今天，谷歌在三藩市召开了一年一度的云大会， [Google Next](https://cloud.withgoogle.com/next18/sf/) 。该活动包括教程、讲座和主题演讲，详细介绍了该公司云产品的复杂性，同时还展示了谷歌提供的最新最棒的服务。包括在所有会议活动中的主题演讲详细介绍了谷歌围绕 Kubernetes 所做的努力，以及其在服务器内部更安全地隔离应用程序的工作。

[谷歌云](https://www.linkedin.com/in/teich/)[的产品管理总监柳文欢·泰奇](https://cloud.google.com)首先发布了用于[谷歌应用引擎](https://cloud.google.com/appengine/)的新 [Gvisor](https://github.com/google/gvisor) 。AppEngine 是该公司的第一个云服务托管产品，自发布以来已经有了很大的发展。去年，该公司扩大了可以在 App Engine 上运行的应用程序的范围，修复了多年来给许多用户带来痛苦的一个主要平台缺陷。Gvisor 允许应用程序彼此完全隔离，就像虚拟化应用程序一样。

现在，Google AppEngine 功能更强，可以运行更高效地连接外部资源的应用程序，Google 通过添加自己的类似 VM 的功能，将目光转向了整个平台的安全性。“Gvisor 是一种新的虚拟化技术，可为您提供虚拟机的安全性和容器的性能。几个月前，我们将它作为 Kubernetes 的一部分进行了开源。我们已经在 AppEngine 和云函数的生产中使用它很长时间了。从历史上看，App Engine 有很多限制。有了新的基于 Gvisor 的运行时，我们可以用基于 Gvisor 的新一代 PHP 7、Node 8 和其他运行时来绕过它。它速度更快，不是专有的，而且完全符合习惯。

谷歌一直在做的另一件事是可移植性。该公司与 IBM、T2、SAP、T4、思科和其他公司联手，将无服务器功能扩展到更多的无服务器平台。这个项目被称为 [Knative](https://github.com/knative) ，它专注于构建必要的基础，以便在 [Kubernetes](https://kubernetes.io/) 上运行无服务器应用程序。由于项目的每个参与者对无服务器都有自己的看法，这项工作的重点是确保这些应用程序可以在 Kubernetes 的安装之间移植。

“Knative 是一个开源项目，引入了无服务器概念——特别是三源构建、服务和事件绑定——并将它们作为自定义 CRD 引入 Kubernetes。这是一个常见的建立在 Kubernetes 顶部的基础。这允许工作负载的可移植性。无服务器不仅仅是一种操作模式，也是一种编程模式。您最终会编写特定于该无服务器平台的代码。这就把它拿走了。”泰克说。

“这也使我们能够提供自己的产品，”泰奇说。“这被称为谷歌 Kubernetes 引擎无服务器插件。这将 Knative 包装成一个我们可以使用的产品。现在，在谷歌云存储容器的支持下，谷歌计算引擎将所有这些整合在一起；您可以运行容器，将它部署到 GCE，几分钟后改变主意，将它部署到 Google Kubernetes 引擎集群或其他纯开源的地方。它给你带来了便携性。”

谷歌 Kubernetes 引擎的使用也不再局限于该公司的云。随着 Google Kubernetes On-Premises 的发布，Google 在此次 Google Next 上完全接受了混合云的理念。这个 Kubernetes 的现场版本为企业提供了一种在谷歌云和他们自己的数据中心之间建立桥梁的快捷方式。有了统一版本的 Kubernetes，管理员将能够远程访问 Google Kubernetes 引擎，并在那里创建服务器，或者在内部旋转它们，并在准备就绪时将它们移动到外部。

Istio 1.0 将在平滑内部和外部 Kubernetes 之间的路径方面发挥重要作用，谷歌正计划将另一个 CNCF 项目大量集成到其产品中。谷歌云首席执行官黛安·格林(Diane Greene)表示，今年的谷歌 Next“比往年要大得多。我们有超过 20，000 人参加，超过 250 名客户参与讨论，能够真正看到这一切走到一起，对我们来说很有趣。”

Google Next 将持续到本周的剩余时间。

谷歌是新堆栈的赞助商。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>