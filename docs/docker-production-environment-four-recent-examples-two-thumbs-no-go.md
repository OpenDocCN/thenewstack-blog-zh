# 生产环境中的码头工人:成功、挫折和教训

> 原文：<https://thenewstack.io/docker-production-environment-four-recent-examples-two-thumbs-no-go/>

Docker 在 2014 年的快速增长以几个关键的 Docker peeps 宣布容器服务基础设施已经达到生产就绪状态而告终。今年，像 Gartner 这样的分析师已经指出了 Docker 在企业中部署分布式应用程序所面临的安全挑战，但对 Docker 的总体发展方向还是相当支持的。今年一个月以来，出现了不少例子，测试使用容器进行持续改进和持续部署的真正生产就绪性。

经验丰富，有相信分布式 web 应用可以使用 Docker 大规模部署的人，有已经将 Docker 集成到他们的生产环境中的人，有选择暂时不这么做的人，还有拒绝使用 Docker 的人，他们认为 Docker 对于现实生活中的用例来说太复杂或不稳定。

下面是今年的四个例子，展示了 Docker 是如何被考虑用于生产环境的:

## 战斗:发布新功能

软件工程师 Jaime Bueza 最近发表的一篇博客文章显示了初创公司 Battlefy 在电子竞技平台上发布新功能或修复错误时，如何使用 Docker 和 Jenkins 快速构建和推送 Docker 图像，然后将其部署到 AWS Elastic Beanstalk。在过去的五个月里，Battlefy 的访问量从 100 增长到了 400，000(T1)，这个行业[预计今年的全球收入将增长 24%](file:///Users/apple/Dropbox/epubs/SuperData%20Research%20eSports%20Brief.pdf)，其国际用户群已经超过 7000 万。

Battlefy 从 GitHub pull 请求一个特性或 bug 开始，链接到一张 JIRA 门票，然后利用测试工具 [Screener](https://screener.io/) 来检测每个构建的 DOM 变化和屏幕截图差异。结果被发送到团队的 Slack 频道，当审查团队成员给代码竖起两个大拇指的表情符号时，Jenkins 将新代码发送到 AWS S3，在那里 Docker 容器被用于构建预生产环境。在生产前的另一轮 Screener 前端测试之后，Jenkins 能够自动将拉动请求合并到主生产环境中。

由于担心在生产中遇到任何故障，Battlefy 使用了 AWS Elastic Beanstalk，因此如果构建、推送和部署的 Docker 映像有错误，Battlefy 可以快速回滚到之前的版本。

## Iron.io:在微服务环境中应用 Docker

iron . io(iron MQ 消息队列系统和异步任务处理工具 IronWorker 的制造商)自豪地将自己视为 Docker 的早期采用者，对他们来说，他们将微服务架构视为运行时环境的标准化模型是非常合理的。

在上周[的一篇博客文章中](https://blog.iron.io/2015/01/the-ephemeral-life-of-dockerized.html)，渠道和集成总监 Ivan Dwyer 解释说，对于 Iron.io，他们可以避免安全、发现和故障等严重的生产挑战，因为他们已经在容器级别将 Docker 集成到他们的系统中:

“…我们将每个任务容器视为短暂的计算资源。持久性、冗余性、可用性——我们在服务级别构建产品时非常关心的所有事情，并不一定适用于单个任务容器级别。我们在这方面的关注基本上仅限于确保运行时在应该的时候发生，让我们对今天大量使用 Docker 充满信心。”

IronWorker 在块存储中有超过 15 个 Docker 映像栈，为运行代码提供语言和库环境。IronWorker 客户然后只利用他们需要编写代码的库，将其上传到 Iron.io 的 S3 文件存储，在那里他们的消息队列服务将基本 Docker 图像与用户的代码包合并到一个新容器中，运行该进程，然后销毁该容器。

Iron.io 在微服务环境中工作，这对于许多遗留企业生产环境来说是不可用的，这些环境远没有 Iron.io 支持的可组合性好。但对于较新的应用程序开发环境，Iron.io 可以在生产环境中使用 Docker 来帮助他们的最终用户管理成本，并根据需要在其编排基础架构内扩展流程。

## Mikamai: Devshop 使用 Opsworks 寻找 Docker 部署

来自 devshop Mikamai 的开发人员 Giovanni Intini 总结了许多成熟开发人员围绕 Docker 分享的一些共同关注的问题:从表面上看，他们喜欢这个想法，他们喜欢它的潜力。但他们也经历过几次，并对过快采用新技术持谨慎态度，这可能会导致他们在部署生产时不得不通宵工作或放弃三天的周末。作为一个二十出头的新程序员，这可能很有趣，但随着他们三十多岁甚至更老，在生产就绪环境中采用新技术的风险是一个更重要的决定因素。

尽管如此，Intini 看到了 Docker 的潜力，由于基于云的 DevOps 生态系统还没有足够成熟，他已经建立了新的开源项目，以使用现有的服务(如亚马逊的 Opsworks，目前还不支持 Docker)来实现 dockered 容器服务的生产部署。

Intini 的应用程序架构需要负载平衡器、前端 web 服务器、haproxy 以避免任何停机时间、应用程序容器、Redis、PostgreSQL、cron 和异步处理。他希望将自己的应用程序构建成可伸缩的 dockerized 应用程序。问题是，由于他的应用程序运行在亚马逊网络服务云上，Docker 并不是一个真正的选项。在他上周的博客帖子中，Intini 分享了他用来创建生产就绪环境以扩展其应用程序的代码和过程，他现在声称该环境在部署中没有停机时间。

## XMLDirector:针对 Docker 的案例

Andreas Jung 是 XMLDirector 的项目负责人，XML director 是一个 XML 内容管理系统和工作流平台，旨在通过转换发布格式和管理文档集合的工具来支持企业 XML 环境。

两周前，他写了一篇关于如何在生产环境中使用 Docker 将特定的 XML 类型的数据库放入容器中，以便可以快速安装和管理它们的文章；将 Plone enterprise CMS 应用程序放入一个容器中，以便它可以用于 XML Director 的演示；并将各种特定于 XML 的数据库放入容器中，这样就可以用它们来测试 XML Director 的后端处理其他 XML 数据库后端的方式。

荣格并不以为然。他发现典型的构建比使用 shell 慢 5-10 倍，几个进程需要重新启动 Docker，而且——因为 Docker 创建了多个映像和容器——在测试后需要进行一些“摆弄”来删除系统上的副本。

在尝试使用 Docker 之后，Jung 承认 Docker 背后的理论和思想是伟大的(但是“它的架构和实现是一团乱麻”,同时又让自己回到了“旧式部署”。Docker 在生产中完全不可用。它是不可靠的，不可预测的，易变的。”)

## 生产就绪？这要看情况而定

随着金融机构、媒体和其他大型全球企业部门对集装箱化系统的采用，Docker 经历了巨大的增长和不断扩大的生态系统。虽然 Docker 的容器技术正迅速成为构建分布式应用的标准，但对于生产环境，早期采用者发现它最适合他们已经考虑过如何为其应用构建微服务架构的用例。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>