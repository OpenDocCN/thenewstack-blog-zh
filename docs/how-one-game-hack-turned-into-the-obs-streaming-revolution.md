# 一个游戏黑客如何演变成 OBS 流媒体革命

> 原文：<https://thenewstack.io/how-one-game-hack-turned-into-the-obs-streaming-revolution/>

这是关于开放源码构建者系列的一部分。要获得本系列的其他文章列表，请查看

[the introductory post](https://thenewstack.io/open-source-builders-an-inside-look/)

.

[](https://www.linkedin.com/in/mjasay/)

 [马特阿萨伊

马特是 AWS 的一名负责人，一直参与开源及其支持的所有领域(云、机器学习、数据基础设施、移动等。)近二十年来，为各种开源公司工作，并定期为 InfoWorld 和 TechRepublic 撰写文章。你可以在推特上关注他(@mjasay)。](https://www.linkedin.com/in/mjasay/) [](https://www.linkedin.com/in/mjasay/)

你渴望成为下一个 YouTube 或 Twitch 明星吗？如果是这样的话，你很有可能想要[开放式广播软件](https://obsproject.com/) (OBS)来捕捉视频和直播你的反恐精英。

在这一点上，你与 OBS 的创始人休“吉姆”贝利没有太大的不同。但就贝利而言，他没有成为 YouTube 明星的野心。尽管他喜欢玩电子游戏，但他创建 OBS 的灵感并不是名气。相反，他只需要在星际争霸上捕捉游戏屏幕的一部分，以便在显示敌人活动的小地图上获得更大的视野。Bailey 说，几百行代码和一个发布到 [StarCraft subreddit](https://www.reddit.com/r/starcraft/) 的帖子，“它就像螺旋上升到这个疯狂的、超级受欢迎的程序中”。

在最近的一次采访中，Bailey 声称这一切的动力是他很无聊，没有免费的工具选项，但他很谦虚。他的经历可以告诉我们很多关于最成功的开源项目是如何运作的。

## 归咎于星际争霸

Bailey 从八岁开始就是一名程序员，没有接受过软件开发方面的正规培训——没有上过大学，除了 18 岁时(1999 年)的一段短暂经历外，没有任何工作经验。

“我一生中从未真正有过一份真正的工作，”他说。不是说他没兴趣，包括 Twitch。“事实表明，我以前从未与任何人合作过，我在那次面试中非常失败，”他说。至少有一个七位数的报价，他拒绝了，因为他觉得这对 OBS 用户没有好处。

贝利形容自己出道前的生活是一个彻头彻尾的流浪汉，和父亲住在一起。他碰巧也是一名出色的开发人员，以开发游戏引擎为乐，尤其需要在星际争霸中“作弊”。他说，那时人们在互联网上流式传输他们的游戏——特别是星际争霸。

“当我玩星际争霸的时候，我尝试了捕捉技术，因为——这听起来很愚蠢——在星际争霸中你有一个叫做小地图的小东西，它会告诉你你的敌人在哪里，”他解释道。“我制作了这个程序，它可以捕捉小地图，并使它在我的左屏幕上变得非常大，因为我希望能够发现是否有人进来，使游戏变得更容易一些。”

最初的捕获程序只有几百行代码，融合了他所学的图形、视频捕获等知识。他本可以使用专有的 XSplit 软件来录制和播放游戏，但他说他很无聊，而且没有免费的工具。他有机会成为第一个，所以他在接下来的几个月里迅速建立了一个原型——“一个程序的非常基本的外壳”——在 Reddit 上提到了它，它占据了他的生活。但不仅仅是他的。

正如 Bailey 所说，“我让它开源，因为它需要社区的努力才能成为最佳技术。”索罗，他可以做一些很酷的东西。有了一个社区，他就能创造出令人惊叹的东西。

## 通过开源更好地在一起

明确地说，贝利是一位杰出的工程师。他说，在早期，他做了别人没有做过的事情。例如，微软有一项技术，允许他在两个进程之间共享纹理，而无需将其从图形处理器中移出，这创造了一种从未有人做过的闪电般快速的视频捕捉方法。

“它就是从那里爆炸的，”他说，“太疯狂了。我以前很难跟上，现在仍然很难跟上。”

幸运的是，他没有囤积。从第一条 Reddit 帖子开始，投稿纷至沓来——包括由[沃尚 7](https://twitter.com/Warchamp7?ref_src=twsrc%5Egoogle%7Ctwcamp%5Eserp%7Ctwgr%5Eauthor) 创建的 OBS 网站，他已经成为贝利的好朋友和 OBS 的忠实投稿人。事实上，许多早期的贡献者今天仍然留在 OBS。

Bailey 建立了早期的基础设施来引导社区，几乎立即将代码从 SourceForge 转移到 GitHub。此外，他还建立了一个 IRC 频道，供社区成员交流。

“那是我学习的地方，”贝利说。“我必须学习很多东西，因为我一开始不知道如何正确同步视频和音频，以及其他类似的东西。”

这个社区在继续发展，也在继续教育贝利，所以他建立了一个论坛，人们可以在那里提问。

“我回复了两三年的每一个帖子，”贝利说，但最终对他来说太多了。当他专注于编码的时候，他把这个问题留给了他成长中的社区来回答。

“在 OBS 之前，我基本上是为自己编程，”他说。他承认他从来没有和其他人一起工作过，这导致了一些他自己也承认是糟糕的编码实践。

“OBS 对我来说是一次巨大的学习经历，我狼吞虎咽。我喜欢它。能够遇到这么多教了我这么多东西的人真是太好了。没有所有人的参与，OBS 就不会有今天。有这么多眼睛盯着某样东西，有助于把它提升到一个你从未想过的水平。”

尽管 OBS 在很大程度上是一个社区的努力，Bailey 仍然做了大量的编码工作——在他看来太多了。

“我不应该编码，”他说。“在开源项目中，有一点维护者不应该再编码了。我已经通过了。”

到目前为止，他还不能从编码工作中解脱出来，因为他需要为 OBS 赞助商提供功能。但这让他疲惫不堪。

“我有很多次感到筋疲力尽，我只需要休息一两周，”他说，“这种事情发生得太多了。”

他不想编码，而是想支付他目前未完成的 115 个拉请求。然而，在接受了帮助支持 OBS 开发的客户的资助后，他必须继续致力于那些功能需求…这将我们带回了社区。

## 对其他项目的建议

当被要求向其他潜在的项目负责人提供建议时，贝利直言不讳:“不要做一个混蛋。你的社区反映了你是谁，”他说。"你带进社区的人是你的一个很大的反映."

毫不奇怪，贝利努力让人们在 OBS 社区感到受欢迎。

然而，这并不总是容易的，因为[开源本来就是自私的](https://blog.p2pfoundation.net/open-source-is-about-self-interest/2006/06/29)。它总是与自身利益有关，这在公司选择资助开源项目以推进其收入目标的方式中显而易见。在 OBS 的世界里，生活没有什么不同。

“我期望开源像彩虹和蝴蝶一样，每个人都和谐地一起工作，就像‘哦，这就是开源。我有很棒的代码。“给你，”贝利说，“但不是那样的。人们只贡献对他们有用的东西，几乎是唯一的。他们通常不会贡献对每个人都有用的代码，尽管有时候他们会。”他说，有时人们试图改进项目，但大多数时候——可能 80%的时候——每当他看到对某件事的拉请求或合并代码的请求时，几乎总是为了狭隘的私利。

更糟糕的是，偶尔的贡献者的代码通常不是特别好。

“审查人们的代码可能非常困难，因为你希望项目中的一切都是一致的，”Bailey 解释道。定期贡献者知道什么是期望。但是随机的、零星的贡献者更难管理。

Bailey 就是 Bailey，他试图理解这些贡献背后的动机，并与他们一起改进代码，使其可以被包含。如果代码很差，但想法很好，他会指导他们如何改进代码。或者他可能自己修改代码，他承认，这不是让人们学习变得更好的最有效的方法。

所以这不全是和平、爱和开源，但是 Bailey 说他不会为任何事放弃它。他承认，这并不总是很有趣，但这仍然是他所要求的最好的工作，他希望能与一些最优秀的人一起工作。这就够了。

在 AWS，我们喜欢支持任何类型的建设者，无论是设计师还是开发者(或其他类型的建设者)。如果你或你认识的人在不同的开源项目上需要帮助，请访问 [AWS 开源](https://aws.amazon.com/opensource)网站，了解开源项目如何[申请 AWS 推广积分](https://aws.amazon.com/blogs/opensource/aws-promotional-credits-open-source-projects/)。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>