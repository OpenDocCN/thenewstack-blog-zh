# 人工智能系统中检测和校正偏差的实用方法

> 原文：<https://thenewstack.io/a-practical-approach-to-detecting-and-correcting-bias-in-ai-systems/>

[](https://www.hackerrank.com/)

[Sofus Mackássy](https://www.hackerrank.com/)

[Sofus Mackássy 是 HackerRank 的数据科学副总裁，他的使命是为每个开发人员找到合适的工作。在过去的 30 年里，他在机器学习、人工智能、数据科学和用户建模方面积累了丰富的专业知识。在 HackerRank 之前，他在 Branch Metrics 和脸书领导团队。他拥有机器学习的博士学位。](https://www.hackerrank.com/)

[](https://www.hackerrank.com/)[](https://www.hackerrank.com/)

随着公司寻求将人工智能纳入其业务的核心，要求提高人工智能算法透明度和对其决策问责的呼声越来越高。

这是有道理的:如果人们打算依靠人工智能做出对现实世界有影响的重要决定，他们需要信任它。但是信任有多种形式——这使得它很难确定。首先，人工智能需要解释为什么它会提出一个特别的建议。这会建立信任，因为人们理解其中的道理。更深层次的信任来自于知道一个系统是公平和公正的。展示这部分要难得多。

这让公司在利用人工智能时陷入了困境:他们要么盲目飞行，要么落后。2018 年，亚马逊——人工智能的明显领跑者——[在团队发现系统中存在偏见的重大问题后，关闭了其实验性人工智能招聘工具](https://www.reuters.com/article/us-amazon-com-jobs-automation-insight/amazon-scraps-secret-ai-recruiting-tool-that-showed-bias-against-women-idUSKCN1MK08G)。

需要的是一种更实际的方法。这是我在脸书和布兰奇等公司建立人工智能和机器学习模型的 15 年，以及现在的 [HackerRank](https://www.hackerrank.com/) 教会我如何检测和纠正人工智能系统中的偏差。

## 专注于你能控制的事情

围绕人工智能系统中的偏差检测和校正的问题集是巨大的。为了在提高人工智能系统的保真度方面取得真正的进展，你需要将偏差问题分解成更小的部分。

从弄清楚哪些方面是你可以实际控制的开始。例如，假设您希望使用人工智能来加速开发人员招聘流程，推动更好的招聘结果，并促进更大的多样性。在这种情况下，偏见会以多种方式悄悄进入流程——有些你可以控制，有些你不能。例如，虽然短期内你无法直接在广泛的社会层面上消除候选人渠道中的系统性偏见(例如，在早期 STEM 教育中扩大多样性)，但你可以采取一些措施来优化你自己的招聘渠道和流程，例如，检查职位描述中的隐性偏见，并在面试反馈过程中省略姓名和代词，以使其专注于相关事实。

> 亚马逊根据 10 年来提交的简历建立了数据模型，其中大部分来自男性。在没有更好的基线数据的情况下，算法产生了对男性候选人的强烈偏好。

关键是理解从你的人工智能系统中完全消除偏见是不可能的。我全心全意地相信人工智能研究人员有一天会到达那里。在此之前，最好专注于解决问题的更实际的方面——这实际上可能比你最初预期的要有效得多。

## 确定偏差可能渗入系统的领域

一般来说，找出什么在你的控制之下是一项分析输入和识别人为错误(即偏差)可以进入等式。虽然这是一个因系统而异的高度关联的过程，但有三个特别高风险的领域需要检查:

**基线数据:**如果你的 AI 运行的数据有偏差，那么 AI 本身也会有偏差。建立基线数据有两个关键步骤:(1)人群抽样——基于有限的数据点创建世界的精确模型；(2)数据转换——将数据点转换成人工智能系统需要学习的格式。两者都非常容易受到无意识偏见(无意中错误处理数据)、无知(不知道任何更好的东西)、懒惰(在清理数据时缺乏活力)和显性偏见(在做上述任何事情时无法将个人观点与客观性分开)的影响。

在亚马逊的案例中，该公司根据 10 年来提交的简历建立了数据模型，其中大部分来自男性。没有更好的(即。更准确和更有代表性)基线数据，算法产生了有利于男性候选人的强烈偏见。

**指令:**你分配给人工智能算法的任务越简单和具体，偏见扭曲结果的可能性就越小。一个相对简单的过程，例如确定一张图片是否包含一只猫，比复杂的任务更不容易受到偏见的影响，比如根据简历预测候选人是否适合某份工作。

随着复杂性的增加，有两种类型的偏见需要应对。第一个是“标签偏差”——为了训练一个人工智能算法来预测一份简历是否适合某个工作角色，需要给许多简历贴上标签，包括好的和坏的。在这里，如果标签是由在某种程度上无意识地有偏见的人创建的，或者如果整个招聘过程有偏见(即主要雇佣男性)。第二个是“相关性偏差”——收集的数据可能与标签不完全相关，从而产生偏差。例如，头发的颜色与某人是否被录用没有太大关系，但相关性可能仍然存在。换句话说，很难教会人工智能相关性不一定意味着因果关系

**行动:**如果人工智能提供的见解或预测被最终做出决策的人忽视，这些个人的偏见将不可避免地影响系统。这“最后一英里”可能是最有问题的。在这些情况下，很难发现和纠正偏差，因为决策是在系统之外做出的，无法精确测量。

## 应用人工智能

一旦你瞄准了你能控制的部分，并识别出它们容易受到人类偏见影响的地方，下一步就是采取行动。根据我的经验，创建第二层人工智能来监控第一层是一个非常实用的策略。

从本质上讲，你需要一套人工智能系统来监控每一个容易出现偏差的模型和过程，并标记异常，以便进行更仔细的检查。例如，如果你的目标是建立一个与一般人群性别多样性水平相似的团队，那么通过引入可信的第三方数据，建立一个跟踪一般人群和你的申请人之间差异的系统就相对容易了。如果两者之间存在差距，就存在偏见。然后，您可以使用统计和/或人工智能来纠正模型，确保性别的理想分布。不过要谨慎行事——一般人群中你可能不像你的候选人那样多样化，所以了解目标是什么以及你要标准化到什么是很重要的。

在某些情况下，例如在前面的示例中，系统可以快速自主地纠正问题。在其他情况下，让人类参与进来是有意义的。例如，假设你的系统跟踪(1)你的申请人群，(2)你最终雇佣的人，和(3)一般人群之间的差异，申请人群和一般人群之间的性别差异很小，但申请人和被雇佣的候选人之间的差异*很大。显然，偏见正在悄悄进入你的系统——但在哪里呢？由于这个过程包括许多步骤，人类可能会更快地弄明白。一旦他们这样做了，你可以将人工智能监督添加到问题区域，以监控未来的偏差。*

然而，重要的是要注意，虽然将人加入到循环中可以在某些方面改善结果，但它也为偏见进入系统带来了新的机会。为了帮助降低这种风险，可以考虑在上面增加额外的偏差监控层。

正如这些例子所说明的，使用当今可用的技术，有许多创造性的方法来检测和纠正人工智能系统中的偏差。没有完美的解决方案，并不意味着你必须袖手旁观。但要做好这件事，关键是要明白，人工智能的好坏取决于它运行的数据、你给它的指令，以及——或许最重要的——与它互动的人类。所以，勇往直前，开始建设吧——在前进的每一步都要坚持不懈地根除偏见。

通过 Pixabay 的特征图像。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>