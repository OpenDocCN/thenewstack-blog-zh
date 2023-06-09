# 我们所说的“功能标志”是什么意思

> 原文：<https://thenewstack.io/what-we-mean-by-feature-flags/>

[](https://www.split.io/)

 [戴夫·卡罗

戴夫在开发人员工具、开发人员社区和使软件交付更加可持续的宣传方法方面有三十年的经验。戴夫是在斯坦福大学的校外长大的，当时硅谷正从国防发展到芯片、软件，最后是互联网服务。戴夫坐在所有这些活动的前排，这让他对技术发展的漫长过程和重复主题有了独特的看法。作为 Split Software 的 CD 布道者，Dave 谈到了将渐进式交付(即新代码的逐步推出)与系统健康、用户体验和用户行为的可观察性结合起来。在 Split.io 之前，他在 BlazeMeter 民主化了 *shift-left* 性能测试。](https://www.split.io/) [](https://www.split.io/)

“你一直在用那个词。我不认为它意味着你认为它意味着什么。”——伊尼戈·蒙托亚，公主新娘。

稍微调整一下，1987 年经典电影中的那句著名的台词可以很容易地应用于术语“特色旗帜”

这是我在参加各种行业会议和会面活动时经常想到的一句话，在那里我经常问人们这样的问题:“你们使用功能标志了吗？”通常，我会得到很多人的肯定回答。有一段时间，我认为这意味着特性标志在开发人员中已经广为人知。但后来我开始追问后续问题，我意识到根本不是那么回事。这个术语仍然存在一些混淆。

事实证明，当许多人听到特性标志这个术语时，他们关注的是“标志”这个词，实际上他们想到的是更古老的东西——软件工程中的其他标志。它们指的是编译时标志或服务器配置标志，或者可能是服务器配置文件。虽然这些的确是旗帜，但它们的共同点是它们都是全球性的。我的意思是，它们会影响通过该软件的每个用户。

但是当我说*特性*标志时，有时称为特性切换或操作切换，我说的是一件非常不同的事情。我指的是在我的代码中做一个动态的决定——实时的。我正在决定我将向用户发送哪种方式，而不必推送新代码，也不必更改配置文件。它不是静态的，不像其他的旗帜。这是一个逐个用户、逐个会话的决定。

## 指挥交通

一个简单的方式来考虑一个功能标志是作为一个交通警察指挥用户。也许交通警察将 10%的人发送到一个新功能，其余的人被发送到该功能周围——换句话说，他们没有获得该功能。这就是你在基于用户百分比的逐步推广中所做的事情。您还可以向内部用户、beta 测试人员、自由层用户或选择获得早期更新的人推出特性——或者目标人群中的任何数量的其他属性。

在功能展示中，您将流量警察(功能标志)放入代码中。一旦你做到了这一点，你就可以使用外部编辑的规则动态地控制谁去哪里。部署的代码不一定是发布的代码。当代码发布时，无需回滚或新部署即可关闭。

这是特性标志的关键所在:它们允许您将部署与发布分开。这为您释放了巨大的能量，因为您能够逐步推出您的代码的各个部分，而无需“释放金丝雀”来分离服务器并将流量路由到它们。它还能让你进行实验。在这两种情况下，您只是简单地将一些用户路由到一种方式，而将一些用户路由到另一种方式，然后观察两组用户之间的差异。

## 更进一步

现在，我遇到的很多人确实在做我上面描述的那种特征标记。然而，许多人正在以有限的方式这样做。人们自然重视拥有控制权的想法，因为它允许他们在出现问题时快速解决问题。而特征标志提供了这种控制。但许多人缺少的是观察和衡量的能力，这种能力使他们能够做出更明智的决定。这就是指标所提供的。

当您将两者结合起来时——控制的特性标志和可观察性的度量标准，那么您就可以进行真正的实验，这比单独的特性标志要强大得多。这几乎类似于得到一个微弱的回声对一个生动的彩色图像。

尽管如此，在你能跑之前你必须先走，理解什么是特性标志以及它们是如何工作的是重要的第一步。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>