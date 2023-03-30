# 本周编程:关于编写优雅的代码

> 原文：<https://thenewstack.io/this-week-in-programming-on-writing-elegant-code/>

有代码，然后有漂亮的代码，阿米利特？

但是是什么让代码变得美丽呢？是优雅简单，还是实现了之前设定的目标？是“有利可图”吗？

[肯特·贝克](https://twitter.com/KentBeck),[极限编程](https://en.wikipedia.org/wiki/Extreme_programming)的程序员和创造者，在 Twitter 上提供了一个[想象的(尽管非常真实)场景](https://twitter.com/KentBeck/status/1190052930843336704)，提出了漂亮与功能性代码的概念，这让一些人开始谈论这个话题。

当然，这里的想法是，完成工作的代码没有什么可羞愧的，但是有几个人提出了异议，反对这种代码引入了技术债务，随着时间的推移，会减少利润。一个人[观察到](https://twitter.com/bi_linguist/status/1190064071795605504)“以后偿还技术债务的成本可能会比利润更高——特别是如果最初的开发者已经离开，新的开发者必须维护它的话。然而，其他人注意到[“代码腐烂”的产生](https://twitter.com/christianhujer/status/1190132678890315776)为长期维护合同创造了条件。

https://twitter.com/bi_linguist/status/1190064071795605504

然而，其他人仍然发现“盈利能力”的概念与开发人员的职责范围没有直接联系，尽管敏捷的整个概念可能会不一致。

然而，Beck 对你的代码是否漂亮、格式是否正确、是否优雅等等的另一个方面提出了异议——羞耻的概念。

作为开发人员，你应该为编写完成工作的代码感到羞耻吗？贝克，为了他的钱，似乎认为结果证明手段。与此同时，黑客新闻上的另一个帖子本周越过了我们的订阅源，相反，它看起来是在庆祝[你所读过的最美丽的代码片段](https://news.ycombinator.com/item?id=21373852)——“一个优雅的片段，而不是一个完整的(精心设计的)代码库”。在这个线程中，我们选择了用这么少的资源做这么多的事情的代码——这可能是我们所有人都渴望的，但事实上，对于完成工作来说完全没有必要。

一个例子是一个程序[，它由一行简单的基本指令](https://youtube.com/watch?v=m9joBLOZVEo)组成，据说可以创建一个迷宫(尽管即使这样也有争议)。

[https://www.youtube.com/embed/m9joBLOZVEo?feature=oembed](https://www.youtube.com/embed/m9joBLOZVEo?feature=oembed)

视频

或者 Lisp 中简单到像“(loop(print(eval(read)))”的单行 [read-eval-print 循环](https://en.wikipedia.org/wiki/Read%E2%80%93eval%E2%80%93print_loop)怎么样？然后是完整的 Lisp 解释器，只用… 13 行 Lisp 语言编写。

[https://www.youtube.com/embed/OyfBQmvr2Hc?feature=oembed](https://www.youtube.com/embed/OyfBQmvr2Hc?feature=oembed)

视频

无论如何，也许我们今天早上在这里的目的是庆祝代码的简单和优雅，同时不要为我们所能做的只是编写不那么漂亮的代码来完成工作而感到羞愧。现在，关于*真正的*问题与[的对话](https://twitter.com/JFThatsABug/status/1190206351689048064) …

## 本周的节目中

*   **Rust 想要你的博客:**也就是说，Rust 团队已经在[发出了一个博客](https://blog.rust-lang.org/2019/10/29/A-call-for-blogs-2020.html)的号召，具体是关于你希望 Rust 在 2020 年的发展是什么样子的，以便为即将到来的路线图众包想法。基本上，你写博客，核心团队阅读它们，然后他们写一个“路线图 RFC”，这个“路线图 RFC”被审查、评论、修改，最后被接受，指导他们在接下来的一年里将注意力集中在 Rust 语言的开发上。截止日期是 12 月 1 日，所以如果你对 Rust 的发展方向有什么看法，或者应该如何发展，写下来贴在网上。他们写道，他们正在寻找关于“几乎任何与 Rust 有关的东西:语言特性、工具需求、社区项目、生态系统需求……如果它与 Rust 有关，我们希望听到它。”去年，Rust 团队[采取了同样的方法](https://blog.rust-lang.org/2019/04/23/roadmap.html)，看了 [73 篇博文](https://readrust.net/rust-2019/)，产生了 [2019 路线图 RFC](https://github.com/rust-lang/rfcs/blob/master/text/2657-roadmap-2019.md) ，所以如果你正在寻找灵感，你已经有了。

https://twitter.com/davecheney/status/1189441717872680961

*   **本周在…遥测？**在过去的一周里，遥测技术似乎已经成为了一个集体思考的话题，因为 Linux 基金会抓住了这个话题，并围绕数据收集、存储和使用制定了一项政策。有道理，当然，GDPR 什么的。与此同时，Gitlab 也在考虑遥测技术，但不是在它的一些产品中实现选择退出遥测技术——这个月早些时候推出的想法遇到了很多阻力，然后[在本周给所有用户的电子邮件中取消了](https://gitlab.com/gitlab-org/growth/product/issues/164)。在电子邮件中，他们写道“主要的错误是，我们没有通过让我们的用户、贡献者和客户参与战略讨论来实现我们自己的核心协作价值”，并且“我们不应该感到惊讶，你对选择加入/选择退出决策、第一方与第三方跟踪、数据保护、安全性、部署灵活性和许多其他主题有强烈的感受，我们应该首先听取意见。”你觉得呢？
*   **微软要回馈 OpenJDK:** 上周是[亚马逊承诺加入 Java 社区进程(JCP)](https://aws.amazon.com/blogs/opensource/amazon-joins-the-java-community-process-jcp/) 。本周，JAXEnter 写道[微软已经准备好为 OpenJDK](https://jaxenter.com/microsoft-ready-contribute-openjdk-163550.html) 做出贡献，并引用了来自 [Bruno Borges](https://www.linkedin.com/in/brunocborges/?originalSubdomain=ca) 的[消息，Bruno Borges](https://mail.openjdk.java.net/pipermail/discuss/2019-October/005173.html) 是微软 Java 的主要开发者倡导者，他向 OpenJDK 社区传达了这一消息。他在信中写道，“微软及其子公司在许多方面都严重依赖 Java”，并且该公司“认识到 Oracle 对 OpenJDK 项目的成功和有效管理为 Java 和更广泛的软件生态系统带来了巨大的价值，我们期待着尽自己的一份力量做出贡献。”怎么会？主要是错误修复和反向移植，直到团队更好地学习“如何成为 OpenJDK 中的好公民”

*   **想为 TensorFlow 买单？**在《我赢了一周》的标题中，DEVClass 嘲弄地问你是否[渴望在机器学习上砸钱](https://devclass.com/2019/10/31/itching-to-hurl-cash-at-machine-learning-google-unveils-tensorflow-enterprise/)——因为如果你是，那么谷歌[新推出的](https://cloud.google.com/blog/products/ai-machine-learning/introducing-tensorflow-enterprise-supported-scalable-and-seamless-tensorflow-in-the-cloud) TensorFlow Enterprise 就是为你准备的，它“为那些愿意付费的人提供支持、更好的性能和托管服务。”当然，谷歌反而将其服务描述为提供企业级支持、云级性能和托管服务，并以“因为谷歌创建并开源了 TensorFlow，所以谷歌云具有独特的定位，可以直接从 TensorFlow 团队本身提供支持和见解”来销售企业产品。这就是你要的——tensor flow，虽然成本很高，但作为一家涉足人工智能的大企业，你可能会想要所有这些好东西。这应该有助于销售它的阶梯，对不对？
*   这种感觉是相互的:争论已经持续了好几年，但是 Perl 5 和 Perl 6 之间的分歧终于在几周前有了结论，决定将 Perl 6 重新命名为樱庭落。这种区别已经延伸到了互联网的另一个角落，一位 Perl 博客作者写道，将樱庭落与 [/r/Perl](https://www.reddit.com/r/perl/) 分开，成为[自己的子编辑](https://www.reddit.com/r/rakulang/)的决定是“两种语言向前迈出的明智的一步”主持人写道，今后，/r/Perl 将用于“对 Perl 5(我猜，还有更早的版本)的讨论”，而不是樱庭落，后者将被视为跑题。
*   **Atlassian for VS Code 2.0:** 对于 Atlassian Bitbucket 和吉拉用户来说，最后一点生产力特性新闻，Atlassian for VS Code 的最新版本现在允许您[预览您的拉取请求和更多内容](https://bitbucket.org/blog/preview-your-pull-requests-and-more-with-atlassian-for-vs-code-2-0)。该扩展是今年早些时候[发布的](https://bitbucket.org/blog/atlassian-for-vscode-bitbucketcloud-and-jirasoftware-extension-for-visual-studio-code)，允许用户从 VS 代码中查看和创建问题、拉请求和管道，但是它缺少一个重要的东西——在你创建它们之前预览拉请求差异的能力，以便你可以捕捉任何最后的修复。现在你可以这么做了！Atlassian for VS Code 2.0 还增加了对 Bitbucket 和吉拉的服务器和数据中心部署的支持，以及对所有问题的单一视图。如果这一切听起来令人兴奋，那么现在就开始[安装扩展吧](https://marketplace.visualstudio.com/items?itemName=Atlassian.atlascode)！

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>