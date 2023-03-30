# Inkscape 如何为 Mac 和 Windows 用户建立一个开源社区

> 原文：<https://thenewstack.io/how-inkscape-built-an-open-source-community-with-mac-and-windows-users/>

这是关于开放源码构建者系列的一部分。要获得本系列的其他文章列表，请查看

[the introductory post](https://thenewstack.io/open-source-builders-an-inside-look/)

.

亚马逊网络服务(AWS) 赞助了这篇文章。

 [马特·阿萨伊

Matt 是 AWS 的负责人，参与了开源及其支持的所有领域(云、机器学习、数据基础设施、移动等。)近二十年来，为各种开源公司工作，并定期为 InfoWorld 和 TechRepublic 撰写文章。你可以在推特上关注他(@mjasay)。](https://www.linkedin.com/in/mjasay/) 

正如开源大师[布莱恩·贝伦多夫曾经断言的](https://asay.blogspot.com/2006/10/wither-right-to-fork.html)，分叉的自由很可能是开源的基本规则，但是分叉不是一个被轻视的行为。在某些方面，分叉表明开源正在发挥其应有的功能；在其他方面，这清楚地表明一个开源*项目*失败了。

以 Sodipodi 为例，这是一个开源矢量图形项目，Ted Gould 和其他人共同创建了 [Inkscape](https://inkscape.org/) 。Gould 在系统工程方面有很长的历史，但由于他在 Ubuntu 桌面上的开创性设计工作，他在开源界变得非常有名。正如古尔德在采访中所说，索迪波迪的问题不在于建筑，而在于社区，或者说，缺乏社区。Inkscape 的创建者不想分叉 Sodipodi，但他们想让任何人都可以贡献或参与这个项目。

结果是产生了一个非常受欢迎的社区，尽管这对于开源来说并不是一个典型的社区。为什么？因为 Inkscape 是为那些对创造完美的标志或美丽的艺术感兴趣的设计师们设计的，而开发它的工程师们可能没有同样的创造欲望。事实证明，这种明显的不和谐导致了一些有趣的动态。

但首先，让我们谈谈那把叉子。

## 一路向下分叉

Inkscape 来自福克斯的优良血统。如前所述，Inkscape 的联合创始人分叉了 Sodipodi，而 Sodipodi 又是 Gill 项目的分叉。即便如此，这也没有让叉 Sodipodi 的决定变得更容易。

据古尔德说，他和其他开发人员想为 Sodipodi 做贡献，但是做不到。例如，有人可能提交了一个补丁，当项目维护人员进行“完整的评审”时，他们被搁置了，这被证明更像是“重写”这减缓了发展并阻碍了贡献。古尔德和其他几个人最初试图通过 Sodipodi 的 [Hydra 分支](http://wiki.inkscape.org/wiki/index.php/SodipodiHydra)发送 pull 请求，希望给 Sodipodi 的维护者提供高度可用的修复，使他们更容易合并到 Sodipodi main 中。

这种方法行不通。事实上，古尔德说这最终导致了一些压力，Sodipodi 的维护者鼓励他们放弃他的项目。

叉它，他们做到了。这段历史对于理解 Inkscape 为什么以这种方式运行，以及为什么它的社区如此坚持要制作它以便任何人都可以贡献并参与到这个项目中来是至关重要的。古尔德说，这种对包容性的强调是 Inkscape 长期成功的真正原因。

## 一个不同类型的社区

不像其他流行的开源项目，如 Linux 或 Kubernetes，他们的开发者通过编写自由软件获得丰厚的报酬，实际上所有 Inkscape 的贡献者都是无偿的志愿者。古尔德说，Inkscape 的许多贡献者从事自由软件的专业工作，或者是顾问。“没有人把在 Inkscape 上工作作为他们的日常工作来获得报酬，”他说。古尔德解释说，随着使用 Inkscape 的设计公司变得越来越大，并从 Inkscape 中赚到足够的钱，这种情况可能会改变，使他们有能力做出贡献。

但是今天，如果你在 Inkscape 上写代码，你是在做一份爱的工作。

您也可能不是该工具的最终消费者。作为一个专注于技术含量较低的设计师的项目，Inkscape 缺乏潜在用户贡献者的基础，比如说， [Wireshark](https://thenewstack.io/wireshark-how-being-broke-inspired-a-vibrant-open-source-community/) 。“我们的典型用户是设计师，”古尔德说，他们倾向于运行 MacOS 或 Windows。然而，Inkscape 的代码贡献者大多更喜欢运行 Linux。“我们很难在 Windows 和 MacOS 上找到贡献者，”他承认道。看到潜在的摩擦了吗？

事实上，古尔德说，对于 Inkscape 的 Windows 用户来说，开源的概念可能是陌生的。“从 Windows 进入 Inkscape 的人是从免费软件的角度来看的，而不是从开源软件的角度，”他解释道。古尔德说，Inkscape 的 Windows 用户并不期望他们能够或者能够以任何方式为这个项目做出贡献。“如果你为了开源而对开源感兴趣，你可能没有用过 Windows，”他说。相比之下，Linux 用户“已经理解了开源这个东西以及它为什么重要。”

或许与此相关，Inkscape 主要的 Mac 和 Windows 用户群并不一定关心这个项目是开源的。“我们有大量的用户，如果 Inkscape 是专有的和免费的，他们不会真的关心，”他解释说。

事实上，正如古尔德所阐述的，“开源软件作为 MySQL 或 MongoDB 之类的工程服务往往非常成功，因为工程师天生重视能够获得代码并对其进行修补。”他说，相比之下，Inkscape 的设计师用户群并不重视源代码，因为这不是他们可以使用的东西。

对于自称为“开源狂热者”的古尔德来说，他希望“每个人都真正真正关心开源这件事。”但现实是他们没有。

“他们只是希望能够编辑图形，制作一个标志，或者设计他们的房子，或者其他任何东西，”他说。因此，Inkscape 社区中的贡献者总是比我们在基础设施项目中看到的要少。

古尔德对此没意见。但这并不意味着他和其他 Inkscape 代码社区不努力改进以吸引更多的贡献。

## 铺开迎宾席

如前所述，Inkscape 的分叉是为了确保以社区为中心的矢量图形方法。这种情况一直持续到今天。古尔德说，Inkscape 社区一直非常积极，强调鼓励而不是强迫贡献。

“如果你是一个新的投稿人，首先要说的是‘欢迎’，而不是‘你今天为什么不投稿？’”古尔德说或者，如果有人带来一个补丁，你不要说的第一句话是，“你错误格式化了第 35 行。”取而代之的是，‘嘿，太好了。我们已经有了这些格式规则，下面是如何应用它们。会很容易的。如果你做不到，我来帮你做。"

像任何项目一样，Inkscape 社区也有提交要求，并确保它们被记录在案，以便于参与和满足期望。“有一个简单的、欢迎的过程对围绕项目创造积极的态度大有帮助，”古尔德说。

除了积极的文化之外，Inkscape 还实现了一个扩展系统，使投稿变得容易，即使对于那些不是高级开发人员的人也是如此。在近 20 年的存在中，Inkscape 的代码库变得越来越复杂，但该项目的扩展系统允许开发人员插入 Python 脚本等。不利的一面是，像 [Ink/Stitch](https://inkstitch.org/) 这样的扩展，一个刺绣扩展，在主 Inkscape 社区之外炫耀他们自己的、独立的社区。

然而，有利的一面是 Inkscape 的持续增长和相关性，因为它致力于连接用户和开发者社区。对于一个即将离开青少年的项目来说，这并不坏。

如果你想[为 Inkscape](https://inkscape.org/contribute/) 做贡献，你不必是一名开发者。有大量的非代码选项——如测试、营销推广等等——以及各种更具技术性的贡献，从代码到网站设计。无论你选择什么，你的贡献都将受到欢迎。那是水墨风景的方式。

*在 AWS，我们喜欢支持任何类型的建设者，无论是设计师还是开发者(或者其他类型的建设者)。* *如果你或你认识的人需要帮助一个不同的开源项目，请访问* [*AWS 开源*](https://aws.amazon.com/opensource) *网站，了解开源项目如何能够* [*申请 AWS 推广积分*](https://aws.amazon.com/blogs/opensource/aws-promotional-credits-open-source-projects/) *。*

通过 Pixabay 的特征图像。

目前，新堆栈不允许直接在该网站上发表评论。我们邀请所有希望讨论某个故事的读者通过推特或脸书 T21 与我们联系。我们也欢迎您通过电子邮件发送新闻提示和反馈:[feedback @ thenewstack . io](mailto:feedback@thenewstack.io)。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>