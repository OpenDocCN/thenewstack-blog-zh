# StackRox KubeLinter 为 Kubernetes 带来安全林挺

> 原文：<https://thenewstack.io/stackrox-kubelinter-brings-security-linting-to-kubernetes/>

在 20 世纪 70 年代末，著名的开发人员 Stephen C. Johnson 提出了一个静态代码分析工具 [lint](https://www.embedded.com/introduction-to-lint/) ，它可以标记编程错误、bug 和不正确的结构。你可以说 lint 在让 C 和 Unix 如此流行的过程中起了很大的作用。今天， [Kubernetes 已经非常流行](https://www.zdnet.com/article/kubernetes-jumps-in-popularity/)，但男孩很容易犯错误，引入逻辑错误，并建立错误的结构。所以，很明显，是时候使用 [StackRox](https://www.stackrox.com/) 的新 [KubeLinter](https://github.com/stackrox/kube-linter) 工具了。

就像鼎盛时期的 lint back 一样，KubeLinter 满足了真正的需求。

正如 StackRox 软件工程师 [Viswajith Venugopal](https://www.stackrox.com/authors/vvenugopal/) 解释的那样，“KubeLinter 诞生于一个我们在 StackRox 非常了解的痛点，既来自于我们的内部集群，也来自于对我们的[客户](https://www.stackrox.com/customers/)的倾听:配置 Kubernetes 应用程序非常困难！有许多旋钮和转盘，光是让你的豆荚上来并相互交谈就可能让人不知所措。但是，即使实现了这一点，也并不意味着您已经准备好在生产中进行部署 Kubernetes 配置中的默认设置通常不适合安全性和生产就绪性。”

不，不，他们不是。Kubernetes 是非常强大的，但它是一个安全的熊。仅举几个问题，协调[基于角色的访问控制(RBAC)](https://kubernetes.io/docs/reference/access-authn-authz/rbac/) 与传统的 Linux 安全性绝非易事。然后，还有保护 Kubernetes 机密的重要工作，这些机密存储在 Kubernetes 默认的分布式键值存储中。到目前为止，一切顺利，但是，默认情况下 etcd 数据没有加密，因此，你的秘密也没有加密。

我可以继续说下去，但你应该明白。为了保护 Kubernetes，你需要所有你能得到的帮助。这就是 KubeLinter 的用武之地。

KubeLinter [分析](https://www.stackrox.com/post/2020/10/introducing-kubelinter-an-open-source-linter-for-kubernetes/) Kubernetes YAML 文件和舵图，并对照各种最佳实践进行检查。它的重点是清除他们的安全错误。一个[样品运行](https://github.com/stackrox/kube-linter) :

```
pod.yaml:  (object:  &lt;no namespace&gt;/security-context-demo  /v1,  Kind=Pod)  container  "sec-ctx-demo"  does not have  a  read-only root file system  (check:  no-read-only-root-fs,  remediation:  Set readOnlyRootFilesystem to true in your container's securityContext.)

pod.yaml: (object: &lt;no namespace&gt;/security-context-demo /v1, Kind=Pod) container    "sec-ctx-demo" has cpu limit 0 (check: unset-cpu-requirements, remediation: Set    your container's  CPU requests and limits depending on its requirements.  See    https://kubernetes.io/docs/concepts/configuration/manage-resources-containers/   #requests-and-limits for more details.)

pod.yaml:  (object:  &lt;no namespace&gt;/security-context-demo  /v1,  Kind=Pod)  container    "sec-ctx-demo"  has memory limit  0  (check:  unset-memory-requirements,  remediation:    Set your container's  memory requests and limits depending on its requirements.    See https://kubernetes.io/docs/concepts/configuration/manage-resources-containers/   #requests-and-limits for more details.)

Error:  found  3  lint errors

```

其中一些是非常简单的错误，但同样危险。例如，在开箱即用时，KubeLinter 会检查以确保您作为非根用户运行容器，强制执行最小特权，并且只在机密中存储敏感信息。

您可以配置 KubeLinter，以便启用和禁用检查，并创建您自己的自定义检查。正如 Venugopal 所写的，“我们已经设计了 KubeLinter，以确保编写自定义检查只需要用户做最少的工作，并且具有非常小的学习曲线。”

KubeLinter 是用 Go 编写的，打包成一个静态的、自包含的二进制文件，所以它可以在几秒钟内安装完毕。一旦你指向你的舵图和 YAML 文件，它会立即给你结果。

您还可以将 KubeLinter 内嵌到您的[持续集成(CI)](https://thenewstack.io/a-primer-continuous-integration-and-continuous-delivery-ci-cd/) 工具中，已经支持将其与 GitHub Action、Jenkins、Travis CI 一起使用。或者 CircleCI。这使得 KubeLinter 更有价值，因为您的开发人员可以自动处理生产流程中的问题。

如果这听起来很棒，那么它应该。KubeLinter 展示了成为真正有用的 Kubernetes 开发工具的前景。也就是说，请记住，在游戏的这个阶段，它只是一个 alpha 程序。将来会对命令用法、标志和配置文件格式进行重大更改。然而，StackRox 希望你开始在测试中使用它，如果你能[做错误报告并为 KubeLinter 的开源 Apache 2 许可代码](https://github.com/stackrox/kube-linter/blob/main/CONTRIBUTING.md)做贡献，他会很高兴的。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>