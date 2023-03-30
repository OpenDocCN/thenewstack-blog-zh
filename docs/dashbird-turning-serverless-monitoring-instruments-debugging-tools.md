# Dashbird:将无服务器监控仪器变成调试工具

> 原文：<https://thenewstack.io/dashbird-turning-serverless-monitoring-instruments-debugging-tools/>

无服务器技术发展很快，但对于更主流的采用，需要一套监控工具来允许开发人员跟踪他们的应用程序和工作流的实际情况。[无服务器](/category/serverless/)需要不同类型的监控(例如，专注于单个功能性能和复杂工作流的健壮性)，一波新工具渴望提供解决方案:[斯塔克里](https://thenewstack.io/emerging-ops-tooling-serverless-reveals-two-adoption-paths/)、 [IOpipe](https://thenewstack.io/iopipe-launches-lambda-monitoring-tool-aws-summit/) ，现在 [Dashbird](https://dashbird.io/) 都已进入舞台。

Dashbird 的联合创始人[Taavi rehemgi](https://github.com/taavirehemagi)和 [Mikk Kirstein](https://github.com/kirstein) 认为他们的监控方法是最有洞察力和最准确的，不会降低性能，因为监控直接来自 [CloudWatch](https://aws.amazon.com/cloudwatch/) 日志，而不是注入在函数之间运行的新代码。但几乎作为副产品，Dashbird 发现他们的监控解决方案有了新用途:作为一种调试工具，可以帮助开发人员在执行无服务器工作流时获得反馈。

目前，Dashbird 专注于 AWS 中的监控，因为 95%的市场都在 AWS Lambda 上，首席执行官兼联合创始人 rehemgi 说。“我们连接到一个 AWS 账户，查看 CloudWatch 日志。我们的服务绝对不会对代码执行速度产生任何影响，也不会增加包的大小或任何其他开销。我们的直接好处是设置速度和帐户范围的可见性，”他说。

rehemgi 说，传统的应用程序性能监控方法通常通过远程 API 发送数据来收集日志，然后使用这些日志来创建仪表板和基于所摄取数据的警报。这种方法不适合无服务器，他解释道:“你有很多功能，一切都发生在瞬间，所以收集引擎缓存更有意义。此外，可能不会报告超时，因为调用在那里停止。为了避免这种情况，我们为函数退休设置了一个标志，以显示它是重试还是第一次调用。”

rehemgi 说，他在用户中看到的主要错误类型包括:

*   ***超时:*** 这些是主要的错误类型，尤其是在无服务器工作流中，一个功能可能需要超过六秒钟
*   ***无声故障:*** 雷海姆吉说，这是一个大问题，因为用户没有将报告附加到一些他们认为不会失败的功能上。“500 个函数中有 10 到 20 个函数可能会出现你认为不会出现的问题。这是 Docker 或传统编程方法所没有的问题。”
*   ***配置错误:*** 当用户忘记附加依赖项或库时会出现这些错误，这意味着事件处理程序没有被触发，所以问题甚至没有被报告。

所有这三种类型的错误都可以通过 Dashbird 进行分析和解决，dash bird 目前有仪表板视图来提供无服务器架构性能的概述，并且可以与 Slack 集成来根据需要提供关键报告。该团队的下一步是开始分析一段时间内的内存使用情况，以便用户可以在无服务器架构达到某个阈值或面临内存限制的风险时获得主动警报。

## 使用监控工具进行调试

但是 Dashbird 的一个意想不到的用例可能是它被用作调试工具。无服务器的挑战之一是没有开发阶段，因此开发人员必须执行他们的功能，看看他们在现实世界中是如何运行的，然后找出如果它没有按预期执行会发生什么。关于代码发生了什么的反馈循环要长得多:采用者需要构建和部署他们的无服务器工作流，然后才能看到发生了什么。

与无服务器框架一起使用的开源 [无服务器离线插件](https://github.com/dherault/serverless-offline) 可以模拟 Lambda 操作和 API 网关，以允许开发者创建开发阶段环境。有了无服务器离线，“至少现在我可以在把代码推给 AWS 之前，在本地测试我所有的代码。克罗地亚在线学习平台 [Bookvar](https://bookvar.co/all) 的联合创始人兼开发者 Adnan Rahic 写道:“这真是松了一口气。

但是对于那些不需要完全独立环境的人来说，Dashbird 的监控本身或许可以充当调试工具。“由于我们将所有的调用和日志分开，你可以在开发时使用它，这样你就可以在发生时获得上下文，”rehemgi 说。“所以你可以在代码执行时看到它。这不仅是关于捕捉错误，也是关于建立系统。”

rehemgi 说，他看到许多 Dashbird 用户每天都会在他们的监控工具上停留几个小时，这表明它是用于调试的。虽然他认为 Dashbird 确实能够缩短反馈回路，但他不太愿意称之为实时——“延迟大约是一分钟”——但他希望这个例子能够鼓励其他无服务器产品的创造者开始构建解决方案。

与此同时，Dashbird 现已正式发布，其使用量已经比私人测试阶段翻了一番。正如其他无服务器工具制造商发现的那样，早期采用者通常来自营销和在线广告公司，但即使在这一领域，也存在很大的差异。在迄今为止使用 Dashbird 的公司中，大约 10%的公司每月的调用次数达到 1 亿次。中型公司开始在一个特定的用例中采用无服务器，其余的公司则在尝试可行的方案。“但是有一半是 Lambda 的忠实用户，”rehemgi 估计。

专题图片:由 [Unsplash 上的](https://unsplash.com/photos/kuJkUTxR0z4)rid ham Nagralawala 拍摄。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>