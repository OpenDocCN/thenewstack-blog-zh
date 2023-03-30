# 本周编程:澄清围绕 Kubernetes 操作符的任何困惑

> 原文：<https://thenewstack.io/this-week-in-programming-clearing-up-any-confusion-around-kubernetes-operators/>

本月初，由[运营商 SDK](https://github.com/operator-framework/operator-sdk) 和[运营商生命周期管理器(OLM)](https://github.com/operator-framework/operator-lifecycle-manager) 组成的红帽[运营商框架](http://operatorframework.io/)，成为[云原生计算基金会](https://landscape.cncf.io/) (CNCF)的孵化项目。虽然你可以找到很多 CNCF 成员讨论基金会如何接受竞争项目的例子，而且[不参与“国王制定”业务](https://twitter.com/ChrisWahl/status/1021509158472835072)，但加入 CNCF 肯定会突出项目，并给它们带来一点公关提升。对于一些人来说，这甚至可能给人这样的印象，即这些项目是值得选择的，因为他们作为加入基金会的一部分所经历的审查过程确保他们符合关于治理、采用、安全等方面的某些标准。

尽管如此，当然仍然有很多分歧的空间，本周牧场主首席技术官达伦·谢泼德在推特上表达了他对运营商框架在运营商讨论中的主导地位的特殊异议，或者可以说是“强烈的负面反应”。(Rancher 本身也提供 Kubernetes 发行版，即将被 SUSE 收购。

在此之前，我们需要一些基本的定义。根据 Kubernetes 文档, [Operators](https://kubernetes.io/docs/concepts/extend-kubernetes/operator/) 是“Kubernetes 的软件扩展，它利用定制资源来管理应用程序及其组件”,这正是 Shepherd 对 Operator Framework 项目反感的一个关键点。

他进一步写道:“当客户理解了运营商这个概念的价值时，他们立即认为他们需要运营商框架，”他指出，甚至“关于‘运营商与掌舵人图表’的讨论[显示]每个人都有多么困惑。”在这一点上，就连我们本月早些时候采访过的红帽公司的人也强调了舵图和操作符之间的区别，这可能是这一领域混乱的另一个例子。

除了将操作符的概念与操作符框架的使用混为一谈(他正确地指出这在构建 Kubernetes 操作符时完全没有必要)，Shepherd 还提出了进一步的问题，即作为一个由 Red Hat 主导的项目，操作符框架“显然与 Red Hat 分发软件的方式一致。”他说，这并不是一个问题，“但令人恼火的是，运营商的概念与一个根本不需要的红帽子联系得如此紧密。”

Shepherd 并不是唯一有这种想法的人，其他人也指出了各种各样的工具，包括即将推出的 CNCF 沙盒项目、KUDO 和 Kubebuilder，运营商框架就是建立在这些工具之上的。

## 本周的节目中

*   **使用 Gather VS Code Extension 清理笔记本:**微软[推出了一种新的清理笔记本的方法](https://devblogs.microsoft.com/python/gather-a-new-way-to-clean-notebooks/)，发布了实验性扩展 [Gather](https://marketplace.visualstudio.com/items?itemName=ms-python.gather) ，这是一种“笔记本清理工具，它分析并确定笔记本中必要的代码依赖关系，并执行代码清理，自动完成这项困难、烦人且耗时的任务。”基本上，它帮助您只提取重新创建特定单元输出所需的相关代码段，并通过在您执行单元时持续分析和跟踪您的笔记本执行来工作。Gather 分析笔记本中需要哪些代码行来生成输出以及这些代码行的运行顺序，然后仅使用该代码创建一个新的笔记本或 Python 文件。目前，Gather 完全支持 matplotlib、NumPy、pandas、random 和 sklearn 包，以及一组内置的 Python 函数/关键字。

*   **使用 VS 代码扩展在 ACI 中运行容器:**本周，Visual Studio 代码领域的另一个新成员是微软最新发布的[VS 代码 Docker 扩展](https://cloudblogs.microsoft.com/opensource/2020/07/22/vs-code-docker-extension-azure-containers-instances/)的，它允许你在 Azure 容器实例(ACI)中运行容器。1.4 版允许您构建、管理和部署容器化的应用程序，现在您可以直接从 VS 代码中查看和排查部署在 ACI 中的容器。
*   **Rust 选择 GitHub Actions 而不是 Azure Pipelines:**Rust 团队已经评估 GitHub Actions 或 Azure Pipelines 是否最适合他们[近一年了](https://blog.rust-lang.org/inside-rust/2019/11/14/evaluating-github-actions.html)，本周最终决定[将 Rust 的 CI 转移到 GitHub Actions](https://blog.rust-lang.org/inside-rust/2020/07/23/rust-ci-is-moving-to-github-actions.html) 。整个过程实际上是在微软和 GitHub 的要求下进行的，Rust 团队表示此举将“极大地改善编译器贡献者的体验。”该团队指出，等待拉请求(PRs)被合并是主要的棘手问题之一，这一点，加上其广泛的持续集成(CI)系统，意味着 PRs 在被测试之前可能要在队列中等待数天。他们写道，GitHub Actions“提供了我们喜欢的 Azure Pipelines 的大部分功能，同时集成了 GitHub 的权限和 UI，这使得切换更加富有成效。”在我们结束 Rust 的话题之前，GitLab 本周通过 GitLab 战略安全部门的高级安全工程师 Antony Saba 的演讲[深入了解 Rust 编程语言](https://about.gitlab.com/company/team/#asaba)。请继续阅读，获取简短的总结或浏览整个演讲:

[https://www.youtube.com/embed/INT_rGJr6JQ?feature=oembed](https://www.youtube.com/embed/INT_rGJr6JQ?feature=oembed)

视频

*   **GitLab 13.2 解决在家工作的问题:**git lab 13.2 的最新[版本](https://aka.ms/VSCodeDocker)一如既往地引入了许多新功能，其中一些专门解决了当您的员工突然完全远程工作时您可能会遇到的问题。这些更新旨在帮助团队通过里程碑迭代简化项目规划，通过 wiki 页面的不同更改提供更好的协作，并通过负载性能测试提高整体性能/效率。
*   **采访维护者:**对于那些对开源感兴趣的人来说，开发者和博客作者 Shawn Wildermuth 发布了一系列新的视频，我们认为应该重点介绍一下。名为[维护者](http://wildermuth.com/2020/07/21/A-New-Video-Series-The-Maintainers)的视频系列是“关于你每天使用的开源项目”，其中 Wildermuth 采访了那些开源项目的维护者，谈论为什么开源对他们很重要。旁注——如果你去看看博客，是的，那张怀尔德穆斯的照片在闪烁，非常轻微地移动。这不是你的想象。

[https://www.youtube.com/embed/dZ_ZVZS-FNc?feature=oembed](https://www.youtube.com/embed/dZ_ZVZS-FNc?feature=oembed)

视频

*   **Kotlin/Native 探索新的内存管理:** Kotlin/Native，用于与特定于本机平台的环境集成的 Kotlin 解决方案，正在展望其[内存管理路线图](https://blog.jetbrains.com/kotlin/2020/07/kotlin-native-memory-management-roadmap/)，注意到其当前的实现在并发性方面存在局限性。因此，他们正在寻找替代品，JetBrains 在一篇博客文章中提供了对该问题历史的深入分析，以及正在考虑的解决方案。他们写道，Kotlin/Native 希望成为“C 兼容语言，就像 Kotlin/JVM 对于 JVM 语言一样——一种实用、简洁、安全、工具友好的编写代码的语言。”这是问题的根源，因为 Objective-C 中的内存管理是如何工作的，Kotlin/Native 的目标是与 Objective-C 互操作。不幸的是，目前的方法“有许多不足之处，阻碍了 Kotlin/Native 的更广泛采用，”他们写道，因此该团队已经开始致力于“Kotlin/Native 的替代内存管理器，它将允许我们取消对 Kotlin/Native 中对象共享的限制，自动跟踪和回收所有未使用的 Kotlin 内存，提高性能，并提供完全无泄漏的安全并发编程原语，不需要开发人员进行任何特殊管理或注释。”

云计算原生计算基金会、GitLab 和 Red Hat 是新堆栈的赞助商。

来自德国 Pixabay 的 Bruno 特写图片

目前，新堆栈不允许直接在该网站上发表评论。我们邀请所有希望讨论一个故事的读者通过 [Twitter](https://twitter.com/thenewstack) 或[脸书](https://www.facebook.com/thenewstack/)访问我们。我们也欢迎您通过电子邮件发送新闻提示和反馈: [feedback@thenewstack.io](mailto:feedback@thenewstack.io) 。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>