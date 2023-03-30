# LogDNA 转向基于 Rust 的代理以加快日志记录

> 原文：<https://thenewstack.io/logdna-moves-to-rust-based-agents-for-speedier-logging/>

当我们在 2016 年第一次与日志管理公司 [LogDNA](https://logdna.com/) 交谈时，该公司刚刚从电子商务转向日志，重点是[通过机器学习](https://thenewstack.io/logdna-aims-make-logging-predictive-machine-learning/)使日志更具预测性。如今，LogDNA 已经将目光转向了针对“任何基础设施、任何架构、任何语言”的 Kubernetes 日志。为了加快进度，该公司本周推出了一系列性能和可用性更新，最引人注目的是用 Rust 编写代理，而不是使用 Node.js/JavaScript 方法。该公司在一份声明中表示，新功能集有助于开发人员更容易地查询、过滤和了解他们的日志数据，并更快地排除故障和修复问题。

[LogDNA 产品管理副总裁 Peter Cho](https://www.linkedin.com/in/petercho/) 解释说，机器学习根本不是需要解决的核心问题。相反，为 Kubernetes 提供大规模伐木是一个更为紧迫的问题。

“我们意识到，我们的客户当时看到的问题更多的是可扩展性。许多客户来找我们，使用其他工具，基本上说我们的东西正在爬行停止。如果我们从发送 100 兆字节到 100 千兆字节或 1 兆兆字节，速度真的会慢下来。“我们最终放弃了机器学习——这并不是说我们未来不会进入这一领域，但我们肯定更关注可扩展性和打造良好的 Kubernetes 用例及体验。”

除了 Kubernetes，Cho 还表示，LogDNA 还为其他大规模系统提供日志记录，例如当使用物联网(IOT)设备和边缘设备时。在解决大规模日志问题的努力中，LogDNA 意识到使用一种更系统级的语言可能会有所帮助，这个最新版本提供了一个用 Rust 编写的新的、更小的、性能更好的代理版本。除了在 Rust 中被重写，该公司表示，新代理“利用 Linux 内核来监控日志文件和目录的变化，释放 CPU 利用率，提高稳定性和准确性，并删除符号链接日志文件的重复行。”

“从基于 Node.js 的代理转移到基于 [Rust](https://www.rust-lang.org/) 的代理，CPU 消耗、RAM 消耗和总体占用空间都大大减少了。Cho 说:“我们遇到了一个问题，对于像 IBM 和其他公司这样具有一定规模的客户，如果代理使用了太多的系统资源，它将会错过一些东西。“我们最终意识到，我们必须使用一种更系统级的语言，如 Rust，这样它才能更具性能，保持在快速旋转的日志之上，以及高产量 Kubernetes 用例带来的其他怪癖，这就是我们从头重写它的原因。”

除了其新的、更高性能的代理之外，LogDNA 现在还提供每小时存档，使用户更容易获得他们需要的数据，而不是一整天的数据，以及提取和聚合字段的能力，Cho 解释说，这允许用户“查看日志行的当前保留窗口，建立模式，然后聚合这些字段，以完成您需要做的任何类型的数据工作。”

最后，LogDNA 还增加了定制的 [webhooks](https://thenewstack.io/webhooks-the-building-blocks-of-an-event-driven-architecture/) ，让用户能够更容易地与不支持的第三方服务集成，例如 JIRA 或微软团队，例如，他们可能会自动触发任务或发送消息。

至于 LogDNA 的下一步，Cho 表示，该公司正在将重点放在开发人员的体验上，他解释说，对于今天的初创公司来说，复杂性来得很快，即使是小型初创公司也要处理比 25 年前思科这样的巨头更多的数据。

“我不会说我们不会走机器学习之类的其他道路，但我会说，至少在近期和中期，我们真的专注于客户体验。我认为人们今天所面临的问题，他们并没有真正关注智力或新时代的事物。他们专注于处理遗留系统的混乱，同时引入 Kubernetes 这样的东西，”Cho 说。

LogDNA 是新堆栈的赞助商。

在 [Unsplash](https://unsplash.com/s/photos/logging?utm_source=unsplash&utm_medium=referral&utm_content=creditCopyText) 上由[稍微有用的](https://unsplash.com/@usefulcollective?utm_source=unsplash&utm_medium=referral&utm_content=creditCopyText)拍摄的特征图像。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>