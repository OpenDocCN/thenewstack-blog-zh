# 3 技术债务的来源以及如何管理

> 原文：<https://thenewstack.io/3-sources-of-tech-debt-and-how-to-manage-it/>

[](https://www.linkedin.com/in/nick-moore-b704a870/)

 [尼克·摩尔

尼克是 Sourcegraph 的内容编辑。](https://www.linkedin.com/in/nick-moore-b704a870/) [](https://www.linkedin.com/in/nick-moore-b704a870/)

软件工程不是一个以魅力闻名的领域，但是如果有魅力的部分，那么技术债务肯定不在其中。

技术债务是一个有许多定义的术语，它们之间有许多分歧。对于本文，我们将依赖来自沃德·坎宁安的[原始定义](https://www.youtube.com/watch?v=pqeJFYwnkjE&t=14s)，该定义指出，技术债务产生于业务需求和实际编写的软件之间的不一致。他说，从这个基本的分歧开始，“我们将不断地跌倒……那会让我们慢下来，就像支付贷款利息一样。”

换句话说，技术债务是当业务作为一个整体和软件开发团队作为一个部分不一致时，以及当这种分歧导致软件开发团队随着时间的推移而变慢时。随着时间的推移，团队会进一步放慢速度，直到你能够偿还技术债务和/或重构代码库。

用这些话来说，科技债务听起来很糟糕。但不一定非要这样。

想象你梦想中的家。30 年后你可能买得起，但你今天就想要，所以你负债了。你今天得到了一个家的好处，代价是几十年后慢慢还清债务。这是世界上许多家庭做出的理性决定，也是软件开发团队做出的决定。

然而，关键是要确保当你决定借债时，你是有意识地这样做的，并且有一个还债的计划。如果你不这样做，你会有一个止赎的房子或一个腐烂的代码库。以下是你可能有意或无意利用的科技债务的三个来源，以及管理由此产生的科技债务的方法。

## 1.速度

速度的名声不好。在“快速行动，打破常规”从灵感变成嘲笑之后，有意快速行动的想法常常让人觉得是一种危险的行动。但是对于大多数创业公司来说，速度是现实，也是必须的。

以 Squarespace 为例。当公司规模达到 600 人左右时，开发团队开始着手电子邮件营销产品电子邮件活动。首要任务是电子邮件编辑器，但团队不想构建一个真正的电子邮件交付基础设施来支持它，因为他们真正想要的反馈只是编辑器。

相反，根据 Squarespace 的工程经理乔恩·桑顿(Jon Thornton)的说法，他们建造了“我们能做到的最简单、最花哨、最快捷的东西”——一个循环，它接受一系列电子邮件地址，并逐个循环，沿途发送电子邮件。

好吃吗？不，它应该是在顾客用它发送电子邮件活动的时候掉下来的。但这不是重点。Squarespace 用它来发送电子邮件已经足够好了，这意味着它足以让人们体验编辑器并提供反馈。

据桑顿说，他们在这个项目上花了大约一周时间，他毫不掩饰地称之为“一次性工作”。他说，如果有什么不同的话，团队会积极地期待删除代码。

速度是值得拥抱的，因为它导致的技术债务，只要你的团队在最终偿还债务和你所做投资的价值上是一致的。Squarespace 在需要构建基础设施之前需要反馈，因此他们优先考虑速度，同时确保他们有计划来偿还速度带来的债务。

## 2.时间

科技债务是不可避免的，因为时间的推移是不可避免的。然而，要是我们能跟上时间就好了。摩尔定律的涟漪效应，尤其是当它们与一个以风险资本为燃料的行业发生碰撞时，意味着技术总是在变化。

在 DevOps Days 的一次演讲中，谷歌云平台的开发者关系工程师戴夫·斯坦克宣称“所有的技术都是债务。”按照斯坦克的说法，技术从未停止前进:“一个新的框架，一种新的语言，一个新的这个，一个新的那个。真是莫名其妙。”科技债务不仅源于这种困惑，也源于科技的飞速发展。

“不管你设计的时候世界是什么样的，当你部署它的时候，那都是旧闻了，”Stanke 说。所有的技术都是技术债务，因为当它成为现实时，时间会让它成为债务。

因为斯坦克认为“你能建造的东西没有一件不是债务，”他认为“你唯一的希望就是尽快进入下一步。”这意味着投资于人和他们领域的专业知识，这是你拥有的最接近持久资产和防御护城河的东西。

如果科技债务是不可避免的，而且根据 Stanke 的说法，它就像时间一样不可避免，那么投资于你的团队是确保你避免破产的最佳方式。

## 3.争论

如果我们回到上面引用的 Cunningham 的原始定义，你会注意到速度和时间都没有被强调。相反，Cunningham 关注的是分歧，联想的 Luca Rossi 在[的这篇文章](https://refactoring.fm/p/the-true-meaning-of-technical-debt)中也提到了这一点。

这里的不一致是指业务需求和软件开发现实之间的差异。

以下三个分歧可能会刺激科技债务的积累:

1.  商业领袖正在寻找出路。如果公司高管专注于退出，特别是收购，他们可能希望通过科技债务来获得用户和收入，这样他们就可以吸引收购要约。他们可能会优先考虑增长而不是技术债务，并将付款计划留给收购后的努力。确保企业领导人和工程师保持一致，这样企业领导人就能学会长期优先考虑技术债务，或者工程师学会短期承担技术债务。
2.  **产品经理过于雄心勃勃**。产品经理，有时受到上级的激励，可能会制定一个产品路线图，无意中要求工程师走捷径来冲刺。随着工程师优先考虑功能的完成，而不是这些功能的可持续性和可维护性，技术债务将会累积。产品经理可以通过在他们和与他们一起工作的工程师之间建立一个更紧密的反馈回路来区分技术债务的优先级。在地面上的工程师是最好的地方知道一个功能是否会及时着陆，有没有牺牲。
3.  **项目经理没有时间偿还技术债务**。你的团队可能同意技术债务是值得解决的，但是如果你的项目时间表没有考虑到它，那么它可能永远不会完成。通过将科技债务与高影响力项目配对，对科技债务进行优先排序(见顾问 Gergely Orosz 对这种方法的论证[此处](https://blog.pragmaticengineer.com/tech-debt/))，将每个季度的最后几个周期用于科技债务(见 Dropbox 的 Leemay Nassery 对这种方法的论证[此处](https://increment.com/planning/reframing-tech-debt/))，或者在每次冲刺中指定一天来处理科技债务(见 Squarespace 的 Thornton 对这种方法的论证[此处](https://changelog.com/podcast/379))。

分歧可能是科技债务最难管理的来源。解决方案——实际上是多个解决方案，因为每个解决方案都必须适合每个环境——依赖于人，而不是技术。

## 科技债务是不可避免的，但你的付款计划不是

这篇文章的标题是有意选择的；科技债务不是你可以消除、遏制或逃避的，但它是你可以管理的。

速度是商业的必需品；时间是不可避免的，无法逃避的；分歧是不可避免的。那么，你的目标不是避免科技债务，而是找出它的来源(这个列表并不详尽！)并在每一类科技债务出现和累积时，仔细考虑管理它们的计划。

记住，科技债务不一定是负担。这是一个强大的杠杆，你可以选择拉，但你应该只拉，如果你有一个付款计划。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>