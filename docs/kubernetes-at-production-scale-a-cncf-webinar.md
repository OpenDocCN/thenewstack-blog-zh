# 生产规模的 kubernetes:CNCF 网络研讨会

> 原文：<https://thenewstack.io/kubernetes-at-production-scale-a-cncf-webinar/>

[Fairwinds](https://www.fairwinds.com/) Kubernetes 咨询公司总裁 [Kendall Miller](https://www.linkedin.com/in/kendallamiller/) 在[最近举行的关于开源编排引擎最佳实践的](https://www.youtube.com/watch?v=8z9qsBsEtOQ&list=WL&index=2&t=2495s)[云本地计算基金会](https://www.cncf.io/)网络研讨会上，警告不要对在线 Kubernetes 专业知识妄加预言。

尽管如此，努力工作会有回报，因为 Kubernetes 将企业带到了[理想的发展状态](https://twitter.com/kelseyhightower/status/851935087532945409?s=20) —拥有一个行业支持的平台即服务(PaaS)，针对公司的特定工作负载需求进行个性化。

Kubernetes“本身不是一个 PaaS，因为它需要大量的配置，但通过正确的配置和正确的方式，它感觉像是为您的需求定制的 PaaS，”Miller 说。“这真的是让你达到目标的框架。”开发人员可以指定他们的应用程序所需的特定资源(内存和 CPU 限制等)，运营工程师可以获得一个 API 来控制基础架构。

Fairwinds 为运行稳健的 Kubernetes 部署提供了哪些指导？以下是一些例子:

**版本控制**:将所有东西都作为基础设施代码来实现，并在 git 存储库中捕获设置。现在应该是赌桌了。“这确保了很容易跟踪你的配置随时间的变化，”Fairwinds 开源主管 Robert Brennan 指出。代码就是文档。通过定期审计，像 Fairwinds 自己的 [Polaris](https://www.fairwinds.com/polaris) 这样的工具可以很容易地发现配置错误。

**仪表板**:并非所有东西都必须通过 CLI 或 API 调用来管理。有了基础设施即代码，仪表板就提供了调整设置的能力，并公开它们供以后检查。“你可以看到一个下拉列表，这真的很好，”米勒说。“其中一些工具实际上做得非常好，可以将您在仪表板中实施的内容应用到基础架构的代码中。”

**设置灾难恢复(DR)** :基础设施即代码的另一个优点是，如果集群由于某种原因消失了，您可以快速地重新创建它，只需运行一个 CI/CD 进程或应用一组 kubectl 命令。Kubernetes 不应该是完整的灾难恢复计划，但它是一个良好的开端。

**不要把你的数据库放在集群中**:与 Kubernetes 集群中的其他东西不同，数据库不是短暂的。如果集群出现故障，您需要保存数据。虽然 Kubernetes 确实提供了诸如[持久卷](https://thenewstack.io/strategies-running-stateful-applications-kubernetes-persistent-volumes-claims/)和[有状态集](https://thenewstack.io/different-approaches-for-building-stateful-kubernetes-applications/)之类的特性来存储持久数据，但该技术仍然容易出错，而且通常还没有准备好投入使用。“这个功能在 Kubernetes 中没有得到我们想要的支持，这是我们试图让人们远离的东西。我们宁愿看到他们使用亚马逊的 RDS 服务来运行他们的数据库，而不是把它放在集群中，”布伦纳说。

转动旋钮:满负荷运转一切都是浪费开支。使用最适合工作负荷的实例类型。工作负载是 CPU 重还是内存重？理想的情况是让花费与工作量相匹配。米勒说，调整你的实例以节省每月 5 美元可能不值得花时间，但是稍微关闭配置设置会花费数千美元。Fairwinds 在这里也提供了一个工具， [Goldilocks](https://github.com/FairwindsOps/goldilocks) ，它可以提供将工作负载与最佳资源相匹配的建议。

在演讲的问答部分也有更多好的信息。点击此处查看完整演示:

[https://www.youtube.com/embed/8z9qsBsEtOQ?start=2495&feature=oembed](https://www.youtube.com/embed/8z9qsBsEtOQ?start=2495&feature=oembed)

视频

亚马逊网络服务和云计算原生计算基金会是新堆栈的赞助商。

目前，新堆栈不允许直接在该网站上发表评论。我们邀请所有希望讨论某个故事的读者通过推特或脸书与我们联系。我们也欢迎您通过电子邮件发送新闻提示和反馈:[feedback @ thenewstack . io](mailto:feedback@thenewstack.io)。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>