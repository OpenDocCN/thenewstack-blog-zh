# Bitnami Stacksmith 为 AWS、Azure 打包应用程序

> 原文：<https://thenewstack.io/bitnami-stacksmith-packages-apps-for-aws-azure/>

当 Bitnami 公司在三月份发布其应用打包产品 [Stacksmith](https://bitnami.com/stacksmith) 作为企业解决方案时，这是为了帮助公司——特别是那些几乎没有云经验的公司——将他们的定制和旧应用迁移到公共云或私有云。

Stacksmith 旨在[将遗留应用](/bitnamis-stacksmith-aims-make-moving-legacy-apps-cloud-effortless/)自动打包到云就绪映像中，将它们迁移到云中，并在之后持续监控它们的升级和补丁。

It [最近](https://blog.bitnami.com/2018/10/Stacksmith-Product-Family.html)让 Stacksmith 在公共层免费提供给部署应用程序的用户，这些应用程序使用公共存储库中的资产，这些资产部署在公共云上。它还增加了 Stacksmith Team，使组织的团队能够共享项目，使用私有或公共存储库中的资产，并部署在多个公共或私有云中。Stacksmith Enterprise 是 Stacksmith 的单租户部署。

“当我们推出 Stacksmith 时，我们关注的是人们已经拥有的东西。他们希望使用云，并利用托管服务，如数据库或消息队列。Bitnami 产品副总裁西蒙·贝内特(Simon Bennett)说:“我们发现 Stacksmith 在许多其他用例中也很有用。

“您可以使用它来提供 golden base 映像，作为他们每季度更新一次的静态映像的替代方案。特别是在过去的六个月里，Linux 安全补丁以相当快的速度出现，这是非常有用的。

“它还可以用于全新的功能——扩展现有系统或在开源基础上从头编写另一个应用程序。人们仍在迁移——这是 Stacksmith 可以帮助人们的一个重要部分——但我们正在更多地了解人们是如何使用它的，”他说。

Stacksmith 基于其内部使用的技术来打包和维护 Bitnami 发布到所有主要云市场的大约 120 个开源应用程序的[目录](https://bitnami.com/stacks)。

它旨在将传统应用程序自动打包到云就绪映像中，将它们迁移到云中，并在升级和修补后持续监控它们。

不需要任何代码修改，Stacksmith 模板带来了目标平台所需的所有组件以及最佳实践。之后，它会自动执行日常维护任务，包括监控更新和安全漏洞补丁。

如果它在 Kubernetes 环境中的容器中运行，Stacksmith 还会构建一个[舵图](https://docs.helm.sh/developing_charts/)来配合它，这样它就有了关于基础设施以及如何部署它的指令。

它最初是为了在亚马逊网络服务上运行而创建的，但该公司后来增加了对 Azure 的支持，并增加了将其绑定到现有基础设施的关键功能，包括 [GitHub](https://github.com/) 和 [Artifactory](https://jfrog.com/artifactory/) 。

去年 12 月，它发布了 Kubeapps，这是一个基于网络的 UI，用于在 Kubernetes 集群中部署和管理应用程序。它一直处于[无服务器](/serverless-101-how-to-get-serverless-started-in-the-enterprise/)运动的最前沿，引领着无库开源原生无服务器计算框架。

它还参与了与 WSO2、Google 和 Apache OpenWhisk group 一起开发的项目，以开发[芭蕾舞演员编程语言](/ballerina-a-programming-language-for-cloud-native-computing/)，试图创建一种用于消息代理、服务托管和事务协调的云原生编程语言。

“该公司一直致力于帮助人们在多个平台上部署应用。Stacksmith 就是其中的一部分，而 Kubeapps 就是让这些部分以自助的方式变得可消费。自助服务是我们看到的另一个主要趋势。人们希望得到他们需要的基础设施，他们希望在几分钟内看到这一点，”他说。

他说，Stacksmith 使该组织能够使用他们今天熟悉的技术进行部署，以期随着时间的推移过渡到集装箱化的世界。

随着越来越多的公司进入这个领域，Bitnami 的独特之处在于，它没有为了针对多个云而推广新的 DSL 或新的模板语言。他表示:这样做的好处是，你可以获得底层平台的全部功能。

“我们并不是要建立一个让人们不得不全盘接受的平台，”他说。“我们将像 Stacksmith 这样的项目与 Kubeapps 一起投放市场，我们使人们能够为他们的特定场景选择正确的产品，而不要求他们端到端地全押 Bitnami 解决方案。他们可以混合搭配多种 CI 工具、多种配置管理工具……现在，他们可以只拿自己需要的部分。”

WSO2 是新堆栈的赞助商。

通过 Pixabay 的特征图像。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>