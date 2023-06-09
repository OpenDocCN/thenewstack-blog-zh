# 为什么性能在时间序列数据中很重要

> 原文：<https://thenewstack.io/why-performance-matters-in-time-series-data/>

[](https://www.linkedin.com/in/nicolas-hourcard-cfa-b7349b37)

[Nicolas hour card](https://www.linkedin.com/in/nicolas-hourcard-cfa-b7349b37)

[Nicolas 是一个终生的技术爱好者，也是 QuestDB 的联合创始人。他以前为罗斯柴尔德和纳斯达克等公司利用时间序列数据。他把时间分配在伦敦和旧金山之间，喜欢网球、滑雪和每年攀登新的山峰。](https://www.linkedin.com/in/nicolas-hourcard-cfa-b7349b37)

[](https://www.linkedin.com/in/nicolas-hourcard-cfa-b7349b37)[](https://www.linkedin.com/in/nicolas-hourcard-cfa-b7349b37)

过去的好数据有助于我们现在做出更好的决策。

今天存在的大部分数据都是在过去十年内创建的，人类数据输出只会从那时开始迅猛增长。国际数据公司预测，到 2025 年，人类数据的总收集量将达到 175 兆字节。一个 zettabyte 当然是十亿太字节，或者一万亿吉字节，这取决于你更喜欢哪种令人费解的测量方法。

虽然我们在存储和收集这些数据方面没有问题，但真正的问题在于我们如何处理这些数据。Forrester data 表示，企业内多达 73%的数据没有用于分析，这是一个巨大的错失机会，无法有效地捕获和处理数据。这就是为什么许多团队正在开发有竞争力的产品，以使数据更有用。

[QuestDB](https://questdb.io/) 特别关注捕获时间序列数据，这让我们能够表示和理解随时间的变化。时间序列数据可能与天气的变化、机器性能的变化，甚至是你自身体重的变化有关。但与每天称一次体重并将这些独立状态存储在数据库中不同，时间序列数据要求捕捉体重的每一个微小波动，无论是上升还是下降，无论何时出汗、生病、吃饭或上厕所。

处理这类数据需要一个高性能的系统，能够快速处理大量单独的数据点，将这些数据转化为决策辅助工具。性能对于时间序列数据来说非常重要，原因如下。

## 时间序列数据是爆炸性的

它是互联设备、物联网、自动驾驶汽车、金融服务甚至服务器场监控的核心。时间序列数据不是捕捉单个数据点，而是捕捉成千上万个数据点。但它甚至不止于此——不仅时间序列数据不断增长，永不停止，而且它可以爆发式增长，在短时间内产生大量读数。

一个气象站捕获关于风速的时间序列数据可能会在很长一段时间内记录为零。但是一旦刮风，你会每秒得到数千个测量值，因为测量值变化很大。需要高性能的系统来有效地捕捉和记录它。

时间序列数据在现代技术专家看来无处不在，有效管理它的工具有点专业化。否则，对处理能力的爆炸性需求和同时减少的可用性将成为一个供需问题。

## 摩尔定律的末日就在眼前

当数据继续呈指数增长时，处理器能力的提高将会放缓。在我们寻求处理和分析所有这些数据的过程中，我们面临着一个大问题，投入更多改进的 CPU 服务器机架来解决这个问题将不再奏效。硬件方面缺乏性能改进，加上公司成本激增，也于事无补。硬件已耗尽。

这就是为什么是时候关注这个等式的另一面了:软件。解决方案是编写更精简的代码，更有效地利用硬件，并通过如此有效地调整软件来提高性能。这种软件较少依赖硬件方面的能力，为利用数据开辟了新的可能性，并实时运行，没有任何滞后。

摩尔定律正在接近其物理极限，因为集成电路中只能容纳这么多晶体管——数据的大部分性能来自硬件，间接允许开发人员编写懒惰、臃肿的代码。但如今优化硬件的空间少了很多。芯片制造商正在接近这样一个时刻，他们需要一种新的物理学来改进今天的现代处理器。这意味着是时候专注于改进软件了。

## 它减少了您的云账单

无论您今天存储和处理了多少数据，明天您只会拥有更多数据。如果您想要在相同的时间内处理增加的信息量，那么您需要更多的计算资源，随着需求的增加，从一台到两台或更多的服务器。但是，您不仅要为此向您的云服务支付更多费用，还要向您的数据库提供商支付额外的软件许可证。

问题变成了:你实际上从每台机器中获得了多少价值？如果一台机器可以处理 10 亿个数据点，那么你知道每增加 10 亿就需要一台新机器。但是，如果你可以通过使用更高性能的软件为每台新机器获得 1000 亿个数据点，那么你就可以真正降低每台机器的成本。此外，你最终需要他们更少。

时间序列数据的性能是帮助您尽可能有效地做出最佳决策。这就是为什么 QuestDB 很高兴能够构建比竞争对手快得多的高性能时序数据解决方案。

通过 Pixabay 的特征图像。

目前，新堆栈不允许直接在该网站上发表评论。我们邀请所有希望讨论某个故事的读者通过推特(Twitter)或脸书(T2)与我们联系。我们也欢迎您通过电子邮件发送新闻提示和反馈:[反馈@thenewstack.io](mailto:feedback@thenewstack.io) 。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>