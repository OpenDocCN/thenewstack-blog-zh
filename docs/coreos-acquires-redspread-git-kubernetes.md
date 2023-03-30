# CoreOS 收购 Redspread，这是一个“为 Kubernetes 提供的 Git”

> 原文：<https://thenewstack.io/coreos-acquires-redspread-git-kubernetes/>

在周一宣布的一项收购交易中，Kubernetes 集群版本控制开源工具的开发人员发现自己受雇于 CoreOS，并从中获利。Redspread 去年 8 月刚刚发布了 spread 客户端本地存储系统的 1.0 版本，并吹捧 Docker“推动了集装箱化运动”，现在它发现自己是制作 **rkt** 集装箱格式的公司的一部分。

CoreOS 的首席执行官 [Alex Polvi](https://twitter.com/polvi) 在接受《新堆栈》采访时宣称，Spread“是一项伟大的技术”。“您如何对集群进行修改和备份？这是任何在生产中从事这项工作的公司都需要做的基本操作。Spread 几乎和 git 一样，但是对于 Kubernetes 来说。它允许你修改和存储你的集群在特定时间的样子。这是后 Kubernetes 时代所需系统的一个例子——您需要能够批量备份您的集群。”

Polvi 接着证实，Spread 功能确实将被整合到 CoreOS 的 Kubernetes 商业实现中。

## 彻底简化部署

在去年八月的一篇 Redspread 博客文章中，首席执行官[麦肯齐·伯内特](https://twitter.com/ciaomack)解释了“传播库”的目的

Burnett 写道:“Spread 和 Git 的关键区别在于我们的版本控制:部署的结构化数据。“与普通文本文件不同，结构化数据包括信息的*上下文*。这意味着我们知道哪些配置字段意味着什么，或者什么“类型”(字符串、布尔、整数等)。)那些领域期待。这使我们能够以编程方式‘备份’Kubernetes 集群，并在此上下文信息的基础上构建新功能，如字段或对象之间的链接。”

作为一家年轻的公司，CoreOS 的第一笔重大收购是 Quay，这已经是两年前的事了，Quay 是一家托管的私人码头注册公司，它是 curiotic today 的主要部分，并保留了它原来的名字。Polvi 在与我们的讨论中承认 Quay，表示无论 Spread 的功能将被整合到 constructive 中，其存储库概念和 Quay 的企业注册将共存。

![161014-mackenzee-burnett-dan-gillespie-redspread](img/e14259804a207bdb4f5536ba24405b0b.png)

就在去年，伯内特从马里兰大学帕克分校获得了国际关系学士学位。与商业伙伴兼首席技术官[丹·吉莱斯皮](https://www.linkedin.com/in/ethernetdan) [ *右* ]一起，在去年二月 Kubernetes 开发社区[的一次公开发布的会议](https://www.youtube.com/watch?v=j7EQfVJdf3A)期间，将 Redspread 引入了 Kubernetes 现场。在那里，他们展示了他们的计划，让 Spread 使用一个命令部署一个版本化的 Kubernetes 集群——据所有人说，去年 8 月他们成功完成了这个计划。

Spread 将给 Kubernetes 用户的日常实践带来的一个变化是通过引入 Burnett 所描述的*目录约定*——一种对容器部署所必需的对象进行归档的标准方式，比如 Dockerfile 和各种 Kubernetes 配置(“Kube 对象”)。在本惯例中，单个码头集装箱将被存储为 ***。ctr** 文件，鼓励一个容器版本更容易区分的系统。

对于多个部署通用的参数可以给定模板，这极大地简化了集群到各种平台的部署，例如 AWS。模板的名称用作 **spread deploy** 函数的参数。这样，开发人员也可以更容易地将测试集群部署到 Minikube 上，Minikube 是基于笔记本电脑的开源 Kubernetes staging 环境，顺便提一下，Burnett 和 Gillespie 也是该环境的贡献者。

Burnett 在去年 2 月的社区会议上说:“这是我们看到 Spread 未来的地方 Kubernetes 的 **git** 的想法，这是一个类似 UNIX 的、最小版本化的命令行容器工作流。

## 快速通道

我问 CoreOS 的 Polvi，如果 Redspread 继续增长，超越两个人的创业，他的公司是否还能与该公司合作。或者出于竞争原因，现在获得他们的服务是绝对必要的吗？

“Redspread 团队非常有才华，”他回应道，“我认为如果他们继续独立运作，他们会非常成功。我觉得非常幸运的是，我们能够让他们与我们合作，这样我们就可以一起加速生态系统的发展。他们是一个非常有才华的团队，我相信如果你是这个领域的投资者，你应该投资在这些平台上运行的产品，而不是与之竞争。找到下一个 ber 不要找到 iOS 或 Android 的下一个替代品。”

将 Spread 的服务整合到“大地构造”的具体细节还有待研究，尽管 Polvi 表示，这种整合实际上可能会加快他对该平台的一些未来计划。“他们的加入已经以一种有意义的方式加速了我们的构造路线图，”他说。

CoreOS 是新堆栈的赞助商。

特写:特大号被子，“当上帝让我生来就是美国佬的时候，他是个奶妈”，作者詹妮弗·富尔顿。詹妮弗的更多被子和她的制作方法在[询问缝纫师](http://www.inquiringquilter.com/)那里。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>