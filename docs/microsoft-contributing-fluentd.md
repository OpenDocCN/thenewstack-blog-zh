# 微软如何为开源 Fluentd 项目做出贡献

> 原文：<https://thenewstack.io/microsoft-contributing-fluentd/>

微软对开源项目的贡献不断增加，它已经远远超出了微软开源技术的范围。为其[运营管理套件](https://thenewstack.io/microsofts-jeremy-winter-qa-automation-new-visualization/)选择了 [Fluentd](https://thenewstack.io/fluentd-offers-comprehensive-log-collection-cloud-microservices-world/) 日志收集框架后，OMS 团队一直在添加其需要的功能，并将这些功能提交回 Fluentd 项目。

微软的[阿努拉格·古普塔](https://www.linkedin.com/in/anurag-gupta-9927b875)告诉新堆栈:“我们希望有一个强大的双向连胜，我们从 Fluentd 中受益，我们希望确保我们从中获得的所有好处也能惠及社区。”。

微软迄今为止做出的最大贡献是他所谓的“循环”缓冲区。Fluentd 内置的缓冲区是使其可靠而不需要外部缓存的关键部分，但如果你记录了大量数据，出于某种原因，Fluentd 无法将这些数据传递到最终目的地(如网络问题),这将被填满。

循环缓冲区将自动丢弃旧数据，为新信息腾出空间，并一直这样做，直到路由到输出的数据再次被接受。“我们可以以滚动的方式丢弃数据，这样就不会填满日志信息文件并开始发送错误信息，这可以确保您获得最相关的新数据，”他说。

你甚至可以为不同的任务设置不同的缓冲容量；您可能希望为您的安全日志保留更多的数据，以便您可以回去分析它们，但是您可能不需要那么多的性能数据(尤其是在停机时，这可能不具有代表性)。

“您可以说您希望保留 80Mb 的每个安全日志，但是为您的性能数据设置 20Mb 的循环数据缓冲区。这样，如果出现服务中断，您可以确保保留安全日志审计数据，但性能数据可以在必要时删除。那是短暂的；目前查看是有用的，但这不是你需要保证会被审计的东西，”古普塔解释说。

微软对 Fluentd 的另一个贡献是为其本机监控机制添加了一个“心跳”。“您可以查看实例上正在运行哪些 Fluentd 插件、通过它们的数据量以及配置等信息。他告诉我们说:“我们在上面添加了一些额外的部分，将一些信息作为心跳备份，这样代理就知道系统的状态是什么。

日志记录代理通常需要心跳，以便您知道代理何时出现故障，何时需要重新启动它，或者何时需要开始将输出路由到不同的日志记录主机，因为默认主机不可用。这对于监控一个集群或一组协调的微服务同样有用，因此 OMS 团队将其转化为一个拉请求。

“我们需要确保向 OMS 报告的 Fluentd 代理有心跳，但我们没有创建一个专有的 OMS 插件，而是修改了 Fluentd 的本地监控功能来添加心跳，”Gupta 说。

[英特尔的尼克·韦弗讨论编排](https://thenewstack.simplecast.com/episodes/intels-nick-weaver-discusses-orchestration)

该团队对 Fluentd 的下一个贡献可能是他们的 [Statsd](https://thenewstack.io/collecting-metrics-using-statsd-a-standard-for-real-time-monitoring/) metrics 服务器。这个聚合器的代码已经可以从 [OMS GitHub repo](https://github.com/Microsoft/OMS-Agent-for-Linux) 获得，但是他们正在考虑把它打包成一个 Fluentd 插件，这样更容易上手。

此外，OMS 回购也是最初获得 Fluentd 的另一种方式。如果你不想安装 Ruby 并获取 [Fluentd Ruby gem](https://rubygems.org/gems/fluentd/versions/0.12.22) ，你可以使用 [td-agent](https://github.com/Microsoft/OMS-Agent-for-Linux) ，一个来自创建 Fluentd 框架的[宝藏数据](https://www.treasuredata.com/)的分发包。这为您做了更多的工作，从 repo 中检索 Fluentd 包并使用 RedHat 或 Debian 包管理器安装它，或者根据您安装它的系统获取 OS X 版本；它预配置了一些设置，包括发送数据到宝藏数据。还有厨师食谱和木偶模块，将为您安装 td-agent 来开始这个过程。

但是对于 OMS 来说，微软希望能够将 Fluentd 代理作为一个可以运行的自解压 shell 脚本来分发——你不需要使用 OMS 来利用这一点。Gupta 说，在某些情况下，这是一种比使用 td-agent 稍微简单的安装 Fluentd 的方法。“我们知道，如果你运行的是 Ubuntu 或 RedHat，我们会链接正确的 OpenSSL 版本，我们会明确说明这是哪个 Fluentd 版本。”

如果那有用的话，可以直接从微软的回购中获得。“我们为 Fluentd 构建的任何东西都可以在我们的 GitHub repo 中开源，每个人都可以使用，”Gupta 说。“你可以把它叉在 Apache 2 许可下；你可以用它做任何你想做的事情。”

通过 Pixabay 的特征图像。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>