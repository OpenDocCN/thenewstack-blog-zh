# SolveSpace 如何重组其 3D CAD 开源社区

> 原文：<https://thenewstack.io/how-solvespace-is-retooling-its-3d-cad-open-source-community/>

这是关于开放源码构建者系列的一部分。要获得本系列的其他文章列表，请查看

[the introductory post](https://thenewstack.io/open-source-builders-an-inside-look/)

.

亚马逊网络服务(AWS) 赞助了这篇文章。

 [马特·阿萨伊

Matt 是 AWS 的负责人，参与了开源及其支持的所有领域(云、机器学习、数据基础设施、移动等。)近二十年来，为各种开源公司工作，并定期为 InfoWorld 和 TechRepublic 撰写文章。你可以在推特上关注他(@mjasay)。](https://www.linkedin.com/in/mjasay/) 

在开源构建者中，有些人将这个概念发挥到了极致。[怀特夸克](https://whitequark.org/)，例如， [SolveSpace](http://solvespace.com/index.pl) 参数化 CAD(计算机辅助设计)软件项目的首席维护者，有一个简单的愿望:她想制造“非常无聊”的技术零件，比如法兰，因为“制造实物很酷”，用她自己的话说。然而，对于她想要制造的东西，她的[数控铣床](https://www.thomasnet.com/articles/custom-manufacturing-fabricating/understanding-cnc-milling/)不够用；她需要在一家机械商店工作，这意味着她需要某种 3D CAD 软件。

这个软件不需要开源。她不是纯粹主义者。*重要的是*软件在 Linux 上运行良好，价格便宜，并且支持[参数化建模](https://www.engineering.com/DesignSoftware/DesignSoftwareArticles/ArticleID/16587/Whats-the-Difference-Between-Parametric-and-Direct-Modeling.aspx)和 [NURBS 布尔运算](https://knowledge.autodesk.com/support/maya/learn-explore/caas/CloudHelp/cloudhelp/2018/ENU/Maya-Modeling/files/GUID-3B3826A9-72B0-4270-A5E2-026E0685FDAB-htm.html)。这大大缩小了范围。

在尝试了 FreeCAD 和 HeeksCAD 之后，Whitequark 发现了 SolveSpace，这是一个由 Jonathan Westhues 发起的开源项目。很好，对吧？不完全是。是的，SolveSpace 满足了 Whitequark 的一些核心需求，但她表示，该软件是一个遗留的代码库，对于不是其原作者的任何人来说，使用它都极具挑战性。这可能会让大多数潜在的开源贡献者望而却步。

但对于像 Whitequark 这样的建造者来说，这是一个(重新)建造数字工具的绝佳机会，反过来，她可以用来建造物理工具。

## 查找撤消按钮

并不是说 Whitequark 曾计划为 SolveSpace 或任何其他开源 CAD 软件做出贡献。她热衷于建造实物。软件只是达到目的的一种手段。

Whitequark 很快庆祝了开源先锋在 3D CAD 领域所做的伟大工作。如果不是因为一个大罪:数据丢失，她会很乐意追随他们中的一个。HeeksCAD 是“开创性的”,但缺乏撤销功能。这证明了一个问题，因为她发现它有点古怪和不可靠。Whitequark 认为 FreeCAD 可能与她的需求更直接相关，但她说，“我从未设法在 FreeCAD 中建模过哪怕一个零件，因为它崩溃得太厉害了，每次都破坏我的工作。如果我没记错的话， *undo* 在那里也不好用。”

离开了 SolveSpace。

“SolveSpace 在很多方面都很完美，”怀特夸克说。“它简单易用。它完美地——我是说完美地——运行了*撤销*。它从来没有——我是说从来没有——让我崩溃，至少在我开始改进它之前是这样，”她自嘲地继续说道。但是它也有一些不太完美的地方，包括它是用受限的类似 C++的方言为 Windows 编写的。没有测试。大量没有抽象的定制数据结构和大量隐藏的不变量。不是特别便携。仅支持 ASCII。诸如此类。

“它所做的事情，绝对是 T4 超越 T5 的，”怀特夸克说。“但这是一个遗留的代码库，对于不是它的原作者的任何人来说，这是一个极具挑战性的工作，因为我很快意识到，我早期的许多明显的变化实际上是不正确的。”

所以她开始工作，逐渐地——小心翼翼地——改进代码。据她估计，她花了两年时间才适应修改代码。相比之下，Westhues 对 Whitequark 的参与非常满意，并把维护者的帽子递给了她。

## 集结军队

无论一个项目领导有多好，他们自己很少是足够的——对于需要接触不同用户群的最雄心勃勃的项目来说更是如此。即使 Whitequark 增加了可用性改进，如改进的 [GTK2](https://www.gtk.org/) 端口和本机 macOS 支持，她也意识到该项目需要一名计算机图形专家，因为几何运算需要工作，OpenGL 2 即时模式渲染器非常慢，并且没有办法导出带有隐藏线的 2D 投影。“我和计算机图形专家正好相反，”她承认道。“我做跨平台系统编程，但我几乎不会两个矩阵相乘。”

伟大的领导者利用他们的优势，同时认识到他们的弱点，用别人的优势来弥补这些弱点。在怀特夸克的案例中，她找到了阿列克谢·叶戈罗夫(Aleksey Egorov)，这位才华横溢的工程师对计算机图形学有着必要的了解，并精通 C++。然而，叶戈罗夫不能免费工作，所以怀特夸克接受了合同工作，这样她就可以资助他的工作。最近，为了帮助分担负载，她聘请瑞安·帕夫里克和保罗·卡勒成为共同维护者。

即便如此，Whitequark 的经历对任何潜在的开源贡献者来说都是一个教训。因为 SolveSpace 代码库非常复杂，临时贡献者很难参与其中。“问题不是没有足够多的人愿意写代码，而是很难写出既可靠又不会引入兼容性风险的代码，”Whitequark 强调说。这意味着开发的大部分负担都落在了她身上，特别是因为 SolveSpace 社区中的许多人往往是机械工程师，而不是软件开发人员。

## 建设和维护

随着时间的推移，Whitequark 在 SolveSpace 上的工作性质已经发生了变化，尽管它教会了她慢慢改进代码以保持向后兼容性的重要性。“我过去做的系统编程工作比维护工作多得多，但很快就变成了相反的工作，”她说。“尽管如此，我仍然有一些改进 SolveSpace 的宏伟计划。作为一个花了数年时间详细学习这个代码库的人，我处在一个完美的位置，可以确保没有人需要花同样长的时间在我之后。我的原则可以概括为‘做了比完美更好，但坏了的明天比根本没做更糟。’缓慢的开发可能会让用户感到沮丧——并疏远直言不讳的少数人——但 SolveSpace 会一直存在，我会让它比我发现它时更好，即使这意味着改进的速度会更慢。"

这对任何希望领导开源项目的人来说都是至关重要的。“随着时间的推移，社会决策变得比技术决策重要得多，”怀特夸克说。

当然，代码很重要，但它最终会过时。通过创建一个友好的社区，像 Whitequark 这样的项目维护者能够利用其他人的集体能量来确保代码被刷新以满足新的需求。

这就是为什么开源需要更多像 Whitequark 这样的建设者。SolveSpace 没有一个庞大的社区，相对于 Linux 的规模，它的用户数量总是很少。只是没有多少人使用 3D CAD 软件来建造实物。然而，这并没有降低它对那些构建这种东西的人的重要性，Whitequark 对提高 SolveSpace 的功能和可靠性的关注为开源领导者提供了重要的线索。

Whitequark 和其他人努力确保 SolveSpace 是一个受欢迎的社区。想参与进来吗？进入 [SolveSpace 论坛](http://solvespace.com/forum.pl)。还没准备好吗？也许花点时间看一下[的 SolveSpace 教程](http://solvespace.com/tutorial.pl)，然后[下载应用程序](http://solvespace.com/download.pl)并尝试构建一些东西。准备好贡献了吗？SolveSpace 让你第一次投稿的开始变得[简单。](https://github.com/solvespace/solvespace/contribute)

*如果您或您认识的人在不同的开源项目上需要帮助，请访问 [AWS 开源](https://aws.amazon.com/opensource)网站，了解开源项目如何[申请 AWS 推广积分](https://aws.amazon.com/blogs/opensource/aws-promotional-credits-open-source-projects/)。*

通过 Pixabay 的特征图像。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>