# 产生数千个技术问题的神经网络

> 原文：<https://thenewstack.io/the-neural-network-that-generated-thousands-of-questions-for-stack-overflow/>

一名开发人员最近向世界展示了另一个神经网络做人类所做事情的例子——或者至少,*模拟了*人类所做的事情。它通过[模仿由](https://stackroboflow.com/) [Stack Exchange](https://stackexchange.com/) 运营的热门社区 Q&Stack Overflow上的帖子，生成关于计算编程的人工问题。

结果是可笑的，怪异的，最终发人深省的——提出了一些关于人工智能在未来会做什么的真正问题…

## **学习学习**

“Stack Roboflow”是总部位于得梅因的开发人员布拉德·德怀尔(Brad Dwyer)的想法，他一直在参加 fast.ai 为开发人员开设的关于实用深度学习的在线课程。

“我倾向于在我自己的项目中学习得最好，”他在他的项目网站上解释道，“创建 Stack Roboflow 是将我的学习应用到一个新问题的一种方式。”

使用 fast.ai 的深度学习开源库，以及 Python 的开源机器学习库(PyTorch)，德怀尔开始教神经网络如何像程序员一样说话。他从 Salesforce 的 [AWD-LSTM 语言模型](https://github.com/salesforce/awd-lstm-lm)开始，该模型根据维基百科页面上的句子来确定英语句子中单词的概率。

但随后利用 Stack Overflow 的数百万个问题作为输入数据，他训练自己的神经网络说 geek。

一路上，Dwyer 必须克服一个人项目面临的所有技术挑战——有时，甚至考虑使用云计算。例如，Dwyer 在 Reddit 上解释说，使用 2080 Ti 显卡进行了大约 30 个小时的训练，尽管“我只能使用我可用数据的 1/16。”该项目的页面解释说，他只有 32GB 的系统内存，尽管他计算过需要 700GB 来容纳一切——然后再花几周时间用他的显卡训练一切。这个“100%‘无服务器’网站”使用了 AWS' [简单存储服务](https://aws.amazon.com/s3/) (S3)、AWS CloudFront 内容交付网络和 Lambda@Edge。"

“出于成本考虑，我最终放弃了云培训的想法，”他在自己的网站上解释道。尽管在 Reddit 上，他补充说他还没有放弃这个想法——如果他能让它实现的话。“我想在某个时候用更大内存的谷歌云实例进行训练，但我的可抢占实例不断被终止，不可抢占实例对我来说太昂贵了，以至于无法在这样的玩具项目上使用。”

## **虚拟编程题**

Dwyer [在 Twitter](https://twitter.com/braddwyer/status/1107084405481398272) 上报道说，他建立并运行了网站——问题是实时生成的，并根据需要上传到网站，几天内就有超过 40，000 名独立访客，并生成了超过 100，000 个问题。

这是一个非常逼真的模拟，提出了类似于“[我如何在 C#中获得当前时间？](https://stackroboflow.com/question/9603)“一度甚至产生了[一个关于 Fortran 的问题](https://stackroboflow.com/question/12187)。

在 Reddit 的编程论坛上的一次讨论中，Dwyer [证实了](https://www.reddit.com/r/programming/comments/b1hzvy/this_programming_question_does_not_exist_stack/eimefku/)Stack robo flow 甚至自发地开始生成一个真实帖子的泄密 tics 甚至包括在问题顶部以“EDIT:”开头的句子。

“它还学会了感谢像戴夫这样的陌生人，甚至有时会签上自己的名字……显然是字符集 o_O。”

在 Reddit 上，Dwyer 澄清说，他的[最终目标](https://www.reddit.com/r/programming/comments/b1hzvy/this_programming_question_does_not_exist_stack/eio9ao5/)一直是更好地预测问题的质量——然后利用它来训练人工智能*产生*更好的问题。“质量预测模型还会有其他有用的应用程序(例如，如果您要发布一个可能被否决的关于堆栈溢出的问题，Google Chrome 扩展会警告您)。”

Dwyer 在 Twitter 上分享了一些有趣的观察结果——包括[一个词云](https://twitter.com/braddwyer/status/1107735353039958021)比较两个网站上最流行的标签。

![](img/4b76a984c96dc6af095d48239d8fafab.png)

Dwyer 最终[希望](https://news.ycombinator.com/item?id=19393285)尝试用来自其他[Stack Exchange](https://stackexchange.com/)community Q&A 站点的数据来训练它。他的网站指出“一个在 philosophy.stackexchange.com 身上训练过的模型可能会‘发明’一些有趣的理论。”

与此同时，他现在提供预先训练好的词汇的免费下载，在知识共享许可下发布——但该页面有一个可选的按需付费捐赠按钮，以支持他的下一个梦想。

“我希望收集足够的钱来支付在完整数据集上进行训练所需的云计算时间(我也将提供下载)。”

此后，他添加了一个页面[，上面有一些更有趣的问题](https://stackroboflow.com/highlights/index.html)，外加该网站最近产生的 100 个问题的索引。该页面还包括一个用于搜索功能的 Elasticsearch 实例(如果你在某个特定主题上寻找人工智能生成的废话。)

## 开发者笑话

这家伙是谁？德怀尔是一家名为[孵化者](http://about.hatchlings.com/)的手机游戏公司的创始人。如果你把手机摄像头对准它，它的一个应用程序可以立即解决一个数独难题。

但是看到更大的开发人员社区对他们自己社区的这种模拟的反应是很有趣的。UI 设计师 Clayton Miller [在 Hacker News](https://news.ycombinator.com/item?id=19394351) 上发帖称:“最初似乎遵循某种内部逻辑的文本有些令人不安，但实际上并非如此。”他补充说，“一些结果读起来像是编程狂热的梦想。”

或者，正如一位名为罗瑟·施瓦茨[的用户发布的](https://news.ycombinator.com/item?id=19394103)，“这是文本合成的神秘之谷。”

一位声称在 Stack Overflow 上审查了 1600 个编辑的评论者指出，“一些自动生成的问题[比一般的 Stack Overflow 问题更容易理解。](https://news.ycombinator.com/item?id=19392508)

另一个人认为[是反乌托邦未来的先兆](https://news.ycombinator.com/item?id=19387131)。“我想知道我们目前在互联网上的讨论板能否经受住即将到来的这种内容的涌入以及随之而来的下一代信息技术的冲击。”

但是至少有一个评论者说问题[看起来奇怪地熟悉](https://news.ycombinator.com/item?id=19391352)。"这也是我初学编程时每个问题的样子."尽管一些反应包括他们自己对社交媒体状况的讽刺性评论。

一位 Reddit 用户——一位 PowerShell 和自动化爱好者——开玩笑说，该网站可以改编成一个来自地狱的技术采访。“从 Stack Overflow 中给某人一些真正的问题，然后插入其中的两三个，看看他们如何试图回答这些问题。”

## **下一步是什么？**

自从最初发布以来，Dwyer 似乎已经做了一些改进。问题现在有了标签(导致带有相同单词的问题的搜索结果)，所以你可以比较它关于特定主题的最后 100 个答案，比如 JavaScript 或 PHP。

但是他仍然有更多的想法，例如，回答问题的能力。"如果我能让它工作起来，它实际上会成为一个有用的工具，而不是一个有趣的玩具。"

他的项目网站分享了另一个未来发展目标——教它如何编码。“我很惊讶这个模型这么快就学会了各种不同的编码语法。它似乎知道 SQL、C#和 JavaScript 之间的区别，并且能够根据问题的内容切换上下文！

“我认为尝试在 GitHub 上训练一些代码，看看它是否可以开始编写实际运行的代码，这真的很棒。”

* * *

# WebReduce

来自 Pixabay 的 rottonara 的特写图像

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>