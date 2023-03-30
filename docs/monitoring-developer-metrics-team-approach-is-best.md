# 监控开发人员度量:团队方法是最好的

> 原文：<https://thenewstack.io/monitoring-developer-metrics-team-approach-is-best/>

Software.com 的首席技术官 Mason McLead 知道开发团队反对监控软件是什么感觉。

McLead 在他之前的公司部署了一个监控解决方案，当时他有一个员工，在某种程度上，他已经知道这个员工不适合他。

“它告诉我我已经知道的事情，就像没有必要一样。我个人对此没有安全感，”麦克里德承认道。“当我终于和这个人聊得很开心时，他们感到很欣慰，因为我们终于有了这次聊天，我收集的所有数据都是无用的。”

他补充说，这确实激怒了他团队中的表演成员。

“我告诉我的团队我有这个工具，我正在试用它；一个月后，他们说，不，你得扔掉它。我们都在超努力地工作。“你会看着这些数据并以这种方式跟踪我们，这太荒谬了，”他说。所以我们一个月后就把它驱逐了。"

这就是为什么他非常清楚 Software.com 的 DevOps 度量工具不是用来报告单个开发人员的，而是用来汇总关于团队工作的数据。

“我们绝对不是间谍软件，这一点很重要，”他说。“我还是代码。我是开发人员，我们的产品人员是开发人员。我们牢记在心。”

相反，他建议 CTO 和其他 DevOps 领导者将那些生产力[度量提供给开发人员](https://thenewstack.io/the-magic-of-metrics-and-how-it-can-burn-you/)，无论是团队还是个人。

## 创造流动

对于个人开发人员，Software.com 提供了一个“流模式”，它使用个人的度量来确定开发人员何时处于“流状态”，这是开发人员完全投入并深入编码的工作的圣杯，不要与[开发流](https://thenewstack.io/flow-measurements-can-eliminate-bottlenecks-in-development/)混淆。流模式工具安装在开发人员的代码编辑器中，如 [VS Code](https://thenewstack.io/this-week-in-programming-visual-studio-code-arrives-on-the-web/) 或 Sublime Text，专门为开发人员跟踪数据——只有个人开发人员才能访问这些数据。该工具利用机器学习来检测开发人员何时处于宝贵的流动状态，然后该工具可以自动关闭干扰，以帮助开发人员更长时间地保持这种状态。

“我们有一个自动化平台，我用它来关闭[空闲](https://thenewstack.io/qa-julia-grace-slacks-head-of-infrastructure-engineering/)通知，它将我的状态设置为离开，并放一个紫色的小点，让人们知道我在心流中，并在我的日历中预订时间，所以没有人可以，”麦克里德说。"它会播放我最喜欢的 [Spotify](https://thenewstack.io/spotify-reboots-ospo-earmarks-109000-for-open-source-projects/) 播放列表."

## 更大利益的衡量标准

但是，这些单独的指标不会发送给管理层。

相反，Software.com 从公司的 [CI/CD 渠道](https://thenewstack.io/three-ways-ci-cd-adoption-can-benefit-your-devops-team/)和 [PR 评论](https://thenewstack.io/welcome-to-the-prty-the-all-inclusive-pull-request/)和 [GitHub](https://thenewstack.io/github-copilot-and-open-source-a-love-story-that-wont-end-well/) 上的部署中提取事件级指标。这些数据都是单独匿名的，并集中于整个团队的努力。他补充说，事件级数据由 JSON 模式验证。

他说:“我们的数据管道中实际上内置了身份验证，所以你不能发送一堆假事件，然后指望这会扰乱下游的指标。”

数据通过一种叫做雪犁的工具流入，然后进入亚马逊 Kinesis [数据流](https://thenewstack.io/aws-aerospike-team-up-for-more-efficient-data-streaming/)。事件在进入亚马逊 S3 时被提取出来，并被放入文件中。该数据然后被拉入[雪花数据仓库](https://thenewstack.io/bob-muglia-takes-the-wraps-off-snowflake-data-warehouse-service/)。

“我们能够从一个事件发生到我们能够平均在大约 20 秒内分析它，”他说。“这就是我们对管道中事件的响应速度。”

他解释说，在 DBT(它的数据转换工具)上运行着更大的批处理作业，告诉雪花做什么，并补充说所有的 SQL 代码都在 GitHub 中。Software.com 使用“拉”请求，数据被推送到一系列报告表中，这些报告表被缓存，然后通过一个 [API](https://thenewstack.io/state-of-the-api-lack-of-api-design-skills-a-key-problem/) 提供给前端，用于制作图表、定制仪表板和导出。

“我们追求的是我们能够监控流经实际交付管道的部分，并向您显示哪些地方可行，哪些地方不可行。同时也要强调目前什么是重要的，什么是不重要的，”他说。

Software.com 使用自己的解决方案来加快其数据团队的速度。它让一名工程师检查数据，并找到自动化和消除手动流程的地方。该供应商能够将新数据投入生产的交付周期从平均六天缩短到三天。

“我没有像首席技术官说的那样，‘你需要去那样做，’”麦克莱德说。“他们能够看到数据，他们知道内部的痛苦，所以他们去解决它。”

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>