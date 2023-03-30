# 分布式跟踪很麻烦，原因如下

> 原文：<https://thenewstack.io/distributed-tracing-is-a-hassle-heres-why/>

为什么分布式跟踪如此麻烦？几周前，Twitter 上出现了这个问题。从那以后，对话一直在继续。

在这个异构的软件世界中，分布式跟踪并不被广泛接受。它[可以拿下生产](https://twitter.com/KirbySaysHi/status/1405960481848844289)。哦，什叶派。

但似乎每个人都在努力。分布式寻人[火爆](https://twitter.com/Liran_Last/status/1407938830443892736)！

有些人希望未来来得更快。换句话说，在这个世界中，分布式跟踪只是工作流的一部分，可以轻松使用。但是我们知道事情还没这么简单。

因此，当我本周在 [Rookout](https://www.rookout.com/?utm_content=inline-mention) 与团队交谈时，我询问了开发人员对分布式跟踪的体验。他们提醒我，事实上他们有一点关于这个主题的新闻，这似乎与我对开发者体验到底意味着什么的兴趣有关，无论如何是在堆栈的上上下下。

Rookout [将分布式跟踪](https://www.rookout.com/blog/getting-by-with-a-little-help-from-my-visual-tracing)分解为一个问题，这个问题的根源在于如何调试云原生微服务。云原生方法通常会引导开发人员使用更传统的基于日志的方法。但是事情很快就变得复杂了。Rookout 产品经理 [Oded Keret](https://www.linkedin.com/in/oded-keret-49786229/?originalSubdomain=il) 认为，逐步调试不适合分布式的大规模架构。日志记录成本增加，性能受到影响。Rookout 团队认为，基于日志的调试意味着必须添加一行日志代码，等待新的发布，在延迟问题解决的同时浪费更多宝贵的开发时间。

一句话就能统治所有人——很难。Kubernetes 的学生将会看到这个选项，并会感到困惑。这是一个动态的世界。有容器和豆荚——一个调试工具不能统治我们所有人。该学生想知道，也没有服务器——这就像一个飞行马戏团，分散的表演者，现在在这里，下一个就不见了。

调试出来的是要多看。因此，这些年来，我们看到了应用性能监控(APM)的兴起。但是在去分布式马戏团的路上发生了一件有趣的事情。这些工具只是通向更复杂事物的窗口。监控提供的信息往往只会让事情变得更加混乱。观看飞行马戏的开发人员可能无法监控一切。开发者可能会问，隐形的飞象发生了什么？就像大象可以在短暂的空间里飞翔和腾跃一样，完全和全面的监控并不现实，这也于事无补。更好的办法是想象它们，并把它们带回现实——所有那些粉红色的宠儿。

但是，等等——这时候学生可能会说——分布式跟踪可以帮助我更好地跟踪那些在机器中运行的自由精神。

Keret 和 Rookout 团队认为跟踪是对日志记录和监控的补充。真正的需求是实时查看应用程序的内部状态。他的观点将对话带入了可观测性的世界，这可以说是过去几年大规模计算领域最重要的发展之一。由蜂巢的好人开创的可观察性现在成了人们谈论的话题。Rookout、 [New Relic](http://newrelic.com/?utm_content=inline-mention) 、 [Grafana](https://thenewstack.io/grafana-8-0-rethinks-alerts-and-visualizations/) 以及像 [Akita](https://www.akitasoftware.com/) 这样的年轻公司都在这场游戏中，还有许多其他公司，如 [Lightstep](https://lightstep.com/?utm_content=inline-mention) 、 [CA](https://thenewstack.io/monitoring-and-observability-whats-the-difference-and-why-does-it-matter/) 和[桑德拉](https://www.thundra.io/?utm_content=inline-mention)。

(我忘了吗，有人吗？那就是同意了。[为我们写一篇文章，告诉我们你在那里](https://thenewstack.io/contributions/)。请让它具有可读性和相关性。编辑团队会踢我的屁股，如果我们得到一堆宣传，我也一样，故事。挑战我们的读者，让他们参与进来——请解释。)

开源项目有助于那些试图跟踪大象的开发人员。Keret 说,[开放遥测项目](https://thenewstack.io/opentracing-opencensus-merge-into-a-single-new-project-opentelemetry/)是整个[云本地计算基金会](https://cncf.io/?utm_content=inline-mention)最受欢迎的项目之一，仅次于 Kubernetes。

Rookout 对可观测性的看法在很多方面都与测量时间有关，秋田公司的创始人 Jean Yang 在一篇文章中也提到了这一主题。在 Rookout，他们已经通过新的跟踪时间线将分布式跟踪引入到调试会话中。它为开放遥测项目用户提供了一种查看不同基于云的微服务之间的内部关系的方式。这是一种故障诊断的方式，是为可能使用 Jaeger、Zipkin 或 Lightstep 等跟踪工具的开发人员准备的。

Rookout 团队认为，这个故事的下一个维度是关于可理解性。将跟踪信息与代码级、特定于上下文的调试数据相结合的能力，使开发人员能够洞察应用程序的行为。大象怎么会出现在托皮卡呢？也许他们去那里是为了食物？在[季风印度烧烤店](http://www.monsoonindiangrill.com/)，食物看起来又香又辣。

然而，我们如何以及为什么理解大象是如何飞到堪萨斯州的，这是一个值得在奥兹国思考的问题。

秋田软件创始人 Jean Yang [在秋田博客](https://www.akitasoftware.com/blog-posts/developer-experience-stuck-between-abstraction-and-a-hard-place)上写道，写时间的软件已经变成了操作时间的软件。现在大部分时间都花在了“预测监控图”上

危险的是对快速解决方案的需求，杨在她的文章中讨论的对银弹的追求。

最后，更多的是我的朋友泰勒·朱厄尔会怎么说。正如他所说，这显然是关于工具如何适应气流，适应滑流。这才是最重要的。然后就是你想做的事情了。

你在寻找允许抽象的工具吗？或者你正在寻找揭示复杂性的工具？

最后，只有时间能告诉我们分布式跟踪如何适应开发人员的需求。在那之前，季风烧烤餐厅现在绝对是我遗愿清单上的一家餐厅。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>