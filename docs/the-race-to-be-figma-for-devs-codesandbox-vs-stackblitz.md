# 开发者的 Figma 竞赛:CodeSandbox vs. StackBlitz

> 原文：<https://thenewstack.io/the-race-to-be-figma-for-devs-codesandbox-vs-stackblitz/>

自从 9 月份 Figma 以 200 亿美元收购了 T1，人们对 T2 的云 IDE 市场越来越感兴趣。人们的想法是，如果连设计工具都可以变成网络本地的，那么开发人员肯定是时候转向完全基于网络的工具了。毕竟，即使是 Photoshop——曾经被认为无法转移到网络上——[现在也有了浏览器版本](https://thenewstack.io/top-5-internet-technology-stories-of-2021/)。但奇怪的是，开发工具似乎是最后一类转移到 web 上的构建产品。开发者忠诚地坚持他们的本地主机。

我最近[对 StackBlitz](https://thenewstack.io/stackblitz-launches-codeflow-and-announces-figma-investment/) 进行了描述，它将自己标榜为“Figma 为设计所做的开发类比”那篇文章发表后，StackBlitz 竞争对手的一位创始人在 Twitter 上给我发了邮件，对其中的一些引用提出了质疑。CodeSandbox 的联合创始人和创建者 Ives van Hoorne 告诉我，他的产品也可以在浏览器中运行桌面版本的 VS 代码，也可以运行 VS 代码扩展。言下之意是，StackBlitz 并不独占这项功能。

出于对 CodeSandbox 与 StackBlitz 相比如何的好奇，以及对云 IDE 市场的更多专家意见，我邀请 van Hoorne 进行了一次采访。幸运的是，他接受了。

CodeSandbox 的起源故事可以追溯到 2016 年，当时 van Hoorne 是他的祖国荷兰的一个拍卖网站的网络开发人员。那年度假时，他发现了没有在线开发环境的挫折。

“我的同事对一些代码有疑问，”他回忆道。“我没有带笔记本电脑，仅仅从 Slack 上获取这些文本片段就相当令人沮丧，我不得不在无法运行代码的情况下破译正在发生的事情。因为我刚刚在手机上看了这个问题。所以当时我觉得，如果能让你的开发环境随处可用，那一定很有意思。”

后来，他联系了他的联合创始人 Bas Buursma，两人于 2017 年 4 月发布了 CodeSandbox 的第一个版本，作为一个开源项目。他们在 2019 年进行了一轮种子轮(当时的投资者之一是 Figma 创始人 Dylan Field，他的公司也是 StackBlitz 的战略投资者)和 2020 年的 A 轮风险投资。

该产品的当前版本被定位为“快速 web 开发的协作沙箱”，这与 StackBlitz 的“即时开发体验”描述相似。这两种产品还提供免费层和高级层。StackBlitz 的定价目前为每月 8.25 美元(针对单个用户)，而 CodeSandbox 为 9 美元。不过，van Hoorne 指出，它才刚刚开始建立其业务的收入方面。

## 微虚拟机是关键的区别

我问 van hoor ne code sandbox 的方法与 StackBlitz 的方法有何不同？他回答说，这两种产品的年龄差不多，在最初的 3-4 年里，“我们(双方)采取了非常相似的方法。”但他说，这种情况在几年前开始出现分歧。

“他们决定全力以赴在浏览器中运行一切，我们决定进入微虚拟机——在微虚拟机上运行东西，”他说。一个[微型虚拟机](https://www.techtarget.com/searchsecurity/definition/micro-VM-micro-virtual-machine)(微型虚拟机)是一个程序，它将操作与计算机的主机操作系统隔离开来。

“StackBlitz 在浏览器中运行一切，”van Hoorne 继续说道，“这给了他们非常快速的体验。他们可以完全控制环境，但不能掌控一切。因此，如果你想运行 Docker 之类的东西，或者你想运行 Postgres 之类的数据库，那是不可能的。”

他说，有了 CodeSandbox，他们选择专注于服务器技术。这促使他们寻找“让服务器上的代码运行得非常快”的方法

“最初，我们认为这是不可能的，”他说。但是微型虚拟机允许他们“非常快速地启动虚拟机，大约 600 毫秒。但最重要的是，它还允许你对它的记忆进行快照——这对我们来说是一个突破。”

他将快照过程比作在 MacBook 上从 localdev 工作。

“你合上 MacBook，一天后再打开，你的整个(开发者)环境仍在运行。你不必等待一切开始，因为在后台 MacBook 序列化了所有这些内存；然后当你打开[计算机]时，它将再次从内存中加载，并继续运行——我们现在在 CodeSandbox 中有相同的概念。”

他补充说，你打开的 CodeSandbox 中的每个分支都会发生这种情况。

## CodeSandbox 项目

今年 3 月，CodeSandbox 推出了名为 CodeSandbox Projects 的新版本产品，该公司称这是“从头开始重写 CodeSandbox”它增加了与 git 和 VS 代码的紧密集成，但项目的关键方面是它使开发人员能够从事更大的项目。

van Hoorne 澄清说，这是引入了微型虚拟机的 CodeSandbox 版本；事实上，他说现在他们应该把它叫做 CodeSandbox 的第二版，而不是给它起一个“项目”的绰号。

“它将取代今天的 CodeSandbox，”他在谈到项目时说，“但我们不想放弃旧的 CodeSandbox，因为我们有 4000 万个项目，我们不想突然把所有项目都转移过来，因为有可能会破坏这些项目。”

根据发布帖的说法，项目的一个关键特征是“每个分支都有自己的开发环境，由唯一的 URL 支持。”这使得团队中的其他开发人员“总是能够看到一个正在运行的分支，即使您离线。”

## 从本地主机迁移

关于云 ide，值得关注的是它们是否成功地让开发人员摆脱了对本地主机的依赖。Van Hoorne 说，现在的趋势很明显，开发者正在转向在线环境。

“现在打包一个开发环境(在线)非常容易，而且正在开发一些标准，以拥有一个可重复的开发环境[……]与此同时，对于许多人来说，网络连接变得越来越稳定。”

他补充说，CodeSandbox 使开发人员能够同步本地和云，以便它们具有相同的配置——这允许开发人员轻松地在两者之间切换。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>