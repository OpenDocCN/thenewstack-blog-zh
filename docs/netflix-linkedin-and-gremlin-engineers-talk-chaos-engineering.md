# 网飞、LinkedIn 和 Gremlin 工程师谈论混沌工程

> 原文：<https://thenewstack.io/netflix-linkedin-and-gremlin-engineers-talk-chaos-engineering/>

[](https://launchdarkly.com/)

 [安德里亚·埃奇斯滕坎普

安德里亚·埃奇斯滕坎普是 LaunchDarkly 的营销总监，也是生产会议测试的组织者。她对社区和生态系统营销、以开发者为中心的公司、生物发光海洋生物和学习新事物感兴趣。](https://launchdarkly.com/) [](https://launchdarkly.com/)

[launch darky](https://launchdarkly.com/)赞助了这篇帖子。

在[launch darky](https://launchdarkly.com/)上，我们在湾区举办每月一次的生产测试会议，要求团队展示他们如何进行生产测试，并分享安全测试的经验和最佳实践。我们最近与来自网飞、LinkedIn 和 Gremlin 的工程师坐下来谈论混沌工程。

honeycomb CEO[Charity Majors](https://thenewstack.io/serverless-testing-in-production/)是生产测试的最大支持者之一。她将其描述为:“当我说‘在生产中测试’时，我并不是说不首先进行最佳实践。我的意思是，有未知的未知，应该通过构建具有弹性的系统来测试。”

我们六月的聚会聚焦于混沌工程。嘉宾以他们的团队如何看待混沌工程开始了讨论。网飞的高级软件工程师诺拉·琼斯谈到了网飞为自己的团队开发的混沌工程工具。[LinkedIn](https://launchdarkly.com/blog/request-disruption-at-linkedin/)的高级网站可靠性工程师(SRE)Ted Strzalkowski 讨论了他的团队如何专注于提供全面、自动化和可衡量的弹性反馈回路。Gremlin 的 UI 工程师 Pat Higgins 做了一个关于弹性工程和从整体上思考失败的演讲。最后，Twitch 的高级软件工程师 Shantanu Joshi 与我们的嘉宾进行了一次小组讨论。

以下是希金斯对混沌工程如何成为安全最佳实践中一个非常合适的工具的总结:

“混沌工程显然是安静的。它还是新生的。对于主流来说，这仍然是一个相当新的概念。所以对我们来说，还有一个教学问题需要考虑。因此，在我们思考如何在我们的平台上运行攻击时，我们也希望这种体验具有指导性。我们希望用户有最好的体验。本质上，我们也希望这些交互简单、安全、可靠。因此，我们也试图围绕这些价值观开发用户体验。”

观看下面的视频，了解这些组织如何让他们的工程师进行混沌实验，并获得他们实际可以使用的宝贵反馈。

[https://www.youtube.com/embed/YJVXtkE63c4?start=5&feature=oembed](https://www.youtube.com/embed/YJVXtkE63c4?start=5&feature=oembed)

视频

*以下是我们对话的文字记录:*

**Shantanu:** 在观看(小组讨论前的)会谈时，令我印象深刻的是秩序和混乱的重要性，有了工具、监控和仪表板，你就可以有很多安全保障。想到这一点，我看到你开始的地方之间有两大鸿沟…本质上，当你在一家公司开始混沌工程时，你可能更多地与顾问而不是团队合作。然后 Linkedin 和网飞使用非常自助。人们如何弥合这一鸿沟？你如何在这个漫长的过程中获得认同？

我想这是整个小组的问题。

诺拉:是的，我可以开始了。所以这是一个非常有趣的问题。我发现，作为一个集中型团队的成员，无论是混乱工程团队、站点可靠性工程团队还是开发团队，你有时都必须戴上咨询帽，有时还必须坐下来戴上耳机和代码帽。是的，我们现在正在让这些工具变得非常自助，但我们也希望深入了解人们是如何使用它们的，以及是什么激励他们从这些工具中采取行动。

我有几周时间完全与团队协商，也有几周时间完全编码。但我认为，在你公司所处的流程的任何阶段，一个集中化的团队要做的非常重要的事情是与你的内部客户、同事交谈，并找出什么样的事情让他们晚上睡不着觉——他们害怕他们会被寻呼到什么。他们如何使用这些工具？是什么让他们在黑色星期五或节假日等关键时期更有信心？

**Ted:** 同样，我们也做了大量的咨询工作。我想说这是我们目前 50%的时间。

我们明确地将内部客户视为我们构建这些工具的对象。当我们与他们坐下来，第一部分不是关于他们如何使用我们的工具。我们不想强行把它作为一个解决方案，因为它可能不是正确的解决方案。因此，我们从客户洞察访谈开始。他们有什么问题？他们希望在问题氛围中减少什么？并且明白了这一点。我们试图将这些提炼为用户故事，这样我们就可以从中判断这些是否是特性。当我们开始从一个团队到下一个团队看到共同的主题时，这些就是我们需要开发的特性。

然后，一旦我们得到这些信息，不带偏见地介绍我们的产品，然后我们向他们介绍我们的产品。如果他们没用过，我们就现场演示。然后我们问他们，“你如何看待自己使用这些东西？你认为这些能解决你刚才提到的哪些问题？”有时，这让他们有一个“啊哈”的时刻，他们说，“好吧，实际上，这将解决另一个问题，我忘了我们有。”

然后同样的事情。再次提出用户故事，以验证您构建的功能，这样我们就可以谈论我们的客户参与是如何在内部进行的。

Patrick: 显然，从我们的角度来看，弥合这一差距显然是一项商业利益。我同意诺拉和泰德所说的一切。就像 Ted 说的，我们确实关注客户与我们产品的互动。从产品的角度来看，这确实影响了我们的一些决策。特别是当我们问他们希望呈现什么样的数据时，因为他们正在运行攻击，并且实际上看到了这些攻击的结果。

还有另外一个因素，混沌工程显然是安静的。它还是新生的。对于主流来说，这仍然是一个相当新的概念。所以对我们来说，还有一个教学问题需要考虑。因此，在我们思考如何在我们的平台上运行攻击时，我们也希望这种体验具有指导性。我们希望用户有最好的体验。本质上，我们还希望这些交互简单、安全、可靠。因此，我们也试图围绕这些价值观开发用户体验。

**山塔努:**谢谢，伙计们。我猜是一些后续问题。Patrick，我发现你的演讲很有趣，因为我不会将前端与混沌工程联系在一起，所以这真的令人大开眼界。

我有一个关于比赛日的问题要问你。

派屈克:是的。

给定……我假设这是你们整个公司在周五进行的混沌实验。你如何防止一大群混乱的实验接管并降低生产？

Patrick: 所以我们不需要在生产中也进行实验。显然测试和生产…本质上这是混沌工程的最终目标。

当谈到 UI 时，失败不一定要发生在那个级别，我才能看到我需要修复的东西。有时确实如此。这真的取决于…关于混沌工程，我认为现实世界的视角，现实世界的体验是非常重要的一部分。我想答案是我不会在周五的三点钟停止生产。这类实验发生的时间和地点，对做实验的人和必须解决这些问题的人来说都是舒适的。

从本质上来说，我们寻找主动故障缓解的目标是确保我们在舒适的时间处理故障，而不是在凌晨 3:00。所以，我想总结一下，我的答案是，“我们不这样做。”

打开之前的最后一个问题。Ted，从谈话中可以看出，当前的失败是在 RPC 客户端层注入的。你会考虑在服务器层注入它们吗？有点嘲笑失败的意味。

**Ted:** 我们从用户那里收到了很多这样的请求。我们今天对实现它有点担心，因为在请求层实现它会给我们一个自动爆炸半径限制。为了安全起见，我们还没有。我们认为，一旦我们开始更好地了解正在发生的事情，以及我们可以在哪里解决问题以及如何解决问题，我们就会向这个方向发展。我们开始解决一些更关键的端点，然后我们会更舒服。因为事实证明，向我们提出服务器端中断请求的客户正是那些为我们的员工提供最关键服务的客户。因此，在这一点上，我们不这样做的唯一原因纯粹是基于恐惧。

**山塔努:**听起来不错。所以我们现在要打开它。

我们有大约一年半，也许两年的时间，我们会和一些人坐在一个房间里，花三个小时想出一个好的实验。然后，我们将它放在 Spinnaker 管道中，它将在部署上运行，但我们不会再查看该配置。用户不会再看到那个配置。我们的团队有四个人，所以我们没有足够的带宽来做所有这些咨询工作。所以我认为，从一开始就搞清楚什么是一个好的实验，什么是真正好的优先事项，并搞清楚这一点，将是很好的信息。

我们启动了 ChAP(网飞的混沌自动化平台),因为我们事先已经建立了另一个名为 Fit 的服务，它不限制爆炸半径。所以如果我回到过去，我会从限制爆炸半径开始，从一开始就把安全放在心上。你知道，实际上很容易建立这个工具并引起混乱。困难的部分是实际上限制爆炸半径，并监控在这些情况下需要监控的内容。

我不知道我是否会改变事情，但我可能会稍微改变一下焦点。

当我使用“脆弱性”这个词时，我的意思是，“一个问题还没有变得广泛。”因此，我们认为这是一个问题，但它要么只影响了一小部分客户，要么确实造成了问题，但客户没有注意到。它让工程师们有时间真正坐在自己的办公桌前，而不是受到寻呼机或 Twitter 上人们的攻击，“网飞下台了，我的生活结束了。”他们确实这样做了。我们已经讨论过实施“去外面玩”的信息…当它确实失败的时候。

这就是我所说的脆弱。事实上，我们正试图找出一种方法，轻松地为团队提供漏洞服务。你看到我装的单片屏幕了。我可以调出某些团队的单片眼镜，看到大约 50 个漏洞。但是如果你给一个团队 50 个漏洞，他们可能不会修复任何一个。懂我意思吧?所以你必须想办法优先处理这些…想办法向他们展示，“嘿，这实际上是一个你想解决的非常重要的事情，因为它可能会成为一个中断，并最终在 Twitter 上结束，这只是时间问题。”

**Patrick:** 我想这是为了让他们在比赛日呆在房间里。这就是我所提倡的。这是一种完全包容的体验，产品经理们都在这里。房间里确实有设计师。很明显，如果人们没有太多的技术背景，他们可能无法理解正在发生的一切。但是这是一个进行这些实验的教学机会。不仅仅是理解故障的运行方式，而是更普遍地理解堆栈。

**Patrick:** 关于混沌工程的一件有趣的事情，或者说重要的事情是，它是一种实践。它是连续的。做一次并不是真正有效的机制。所以它需要定期练习。也许像健身房会员或乐器。你不可能只吹 36 个小时的小号就真的吹得很好。这实际上是关于…我试图鼓励的是从组织的角度思考失败的想法，并围绕它创造一种文化。定期做这些事情并保持这种合作。

Ted: 我们正在做的一些事情..我们称之为“关键路径”我们正在查看默认响应，以便您至少可以模拟一些数据，向用户显示它可能不是正确的数据。其他事情是完全隐藏数据。就像 Patrick 之前在 Twitter 上展示的那样，这张卡片通常被认为是非常重要的信息，但它就是不见了。有时用户甚至会注意到这一点。

诺拉:按照这些思路，你应该始终确保自己有退路。

在网飞，当你登录你的网飞时，你会看到，“这是诺拉的推荐信。”有时那一行会失败。如果这一行失败了，我们不会把整个网飞都搞垮，我们只会给你看大多数人喜欢的东西。这就是那里发生的事情。

所以我认为，如果你在尝试这些东西，确保你有某种退路是很重要的。我们在关键路径中也有这些服务，我们从来没有对它们进行失败实验，因为我们知道它们实际上会失败，这对用户来说不会是一个好的体验。我们确实对它们进行了潜伏期实验。因此，我们将在这些调用之间增加时间，看看它是否仍然正常工作，并且在这种情况下实际上没有打开回退路径。

诺拉:是的，这就是我们大量自动化的原因。我们发现我们的用户，我们的内部客户，在这些领域没有足够的经验来做一个好的实验。他们实际上会在很多时候把我们拉进房间，这是我们从一开始就没有预料到的。我们想，“他们是这个服务的所有者，他们知道在这里测试什么，”但事实并非总是如此。这实际上是用户想出的大量信息，是什么使它成为这样的。

我们创建测试用例的初始配置页面非常复杂。它可能阻止了一些人使用它。因此，我认为自动化，填写信息，自动运行信息，并将其转变为选择退出模式是好的。这真的很有帮助。我认为大多数团队最终会相信混沌工程团队或工具是专家，在那种情况下，他们会被需要的。让他们参与进来肯定是好的，但我发现他们希望那个领域简单，这样他们就可以信任它，而不用花太多心思去创建那些实验。

**Patrick:** 就 Nora 的观点而言，正如你所说，我认为这是阻止我们“使这种配置比产品本身更难”的原因本质上，我们试图激励这些实践。如果我们把它做得太难，人们就不会去做了。

**Ted:** 这就是我们开发 Chrome 扩展的原因，将这种发现阶段推到用户的浏览器上。他们已经知道，他们的爆炸半径仅限于他们的浏览器会话，所以他们不怕测试任何东西。我们从 Chrome 扩展的用户监控中看到，大多数人一开始都失败了。就像，“那当然会爆炸。”然后他们开始“取消检查”东西。但很高兴看到这一点，因为这表明他们在那个水平上参与，他们没有任何恐惧。从 Chrome-extension 中，他们提出了实际的 sane 故障计划，然后我们为他们添加了将该计划导出到自动化框架的能力。

所以，同样的想法。很多用户来问我们，“我们该怎么做？”现在我们可以说，“这是你要学习的工具，”因为我们只有三个人。

Ted: 我先回答第二部分。对于新员工，我们有一个新的训练营，在那里我们可以搭载新的工程师。我们向他们介绍训练营里的工具。所以在 LinkedIn 的第三天，他们已经接触到了这些工具。所以他们看到我们有这些给他们。这是最小的爆炸半径，也是一种“明天就去玩”的想法。一旦他们进入堆栈并开始实际编写代码，一旦发生中断，我们就与他们同步，一旦他们说他们已经解决了问题，不会再发生中断，我们就尝试重放中断。这将他们重新引入工具集，这样他们就可以说，“哦，是的，我确实修复了这个问题，现在我可以检查未来的回归了。”

**诺拉:**我在配置方面经历了很多。我们发现人们的超时时间太高或太低。很容易进入一个文件，将超时时间从 400 改为 500，然后关闭吉拉门票。但你这么做是有原因的。

在很多情况下，我最终发现……在网飞，我们也扮演了混乱工程师的角色来探究“为什么”。比如，“为什么会这样？”我发现的一件有趣的事情是，工程师们不想花太多时间来设置他们的新应用程序。因此，我会看到人们从一个看起来与他们正在构建的服务相似的服务中获取一个配置文件，然后复制并粘贴整个文件，并将其放入他们的文件中。因为他们只想完成那部分。这真是有趣的学习。他们可以很容易地不断改变…或者我们甚至可以从 ChAP 提交池请求来改变他们的超时，但这是一个有趣的学习。

我认为其中的一部分是挖掘团队的“为什么”,实际上，如果你看到跨事物的模式，就采访他们。我们实际上已经在我们的工具中内置了，“好的，这是我们看到的某些类型的模式。”现在，我们可以在事后向团队提出特定类型的问题，以帮助他们从事件中学习，并从事件中了解我们自己以及事件发生的确切原因。

Patrick: 只是从一个……也许只是从理论的角度来看。因为我实际上不能像与来自一个组织的用户打交道的人那样谈论一般情况，但混沌工程本质上具有周期性，我们有一个实验和我们发现失败的点…我们经历一个补救和验证的过程。因此，从 Gremlin 的角度来看，尝试灌输这些补救和验证规范是这个过程中非常重要的一部分，因为我们希望企业从本质上看到混沌工程对他们也有商业价值。

**诺拉:**在网飞之前，我在一家初创公司工作。大概从 2011 年开始，网飞一直在做混沌工程。我在一家初创公司开始了它，它每天都很混乱。我最初没有在我的很多工具中设置安全，并且因为发现了一个漏洞，我结束了整整一周的测试环境。它不应该关闭测试环境；这是一个合理的漏洞，但之后对我来说就很难说服了。这是第一个使用案例。因此，我与产品经理交谈，最终我让一群业务人员参与进来，我不得不与他们坐下来，像这样，“看，我们应该限制这些实验的后果，”但这个过程实际上发现了一个合法的问题，幸运的是在生产中没有发生。

它确实需要一些实施它的人的宣传，但我认为如果你牢记安全，并且如果你传播，“如果我们不这样做，如果我们不积极主动，这将会发生什么。”

我有时会遇到一些公司向我求助，他们会说，“我们是一家银行公司，我们不可能做这样的事情，”但我认为他们应该比网飞这样的公司做得更多。他们应该知道会发生什么。他们应该真正知道当某件事失败时会发生什么。这不是一个“如果失败了会怎样”的问题，而是“如果失败了会怎样？”如果你不能回答这个问题，我会很害怕。

**Ted:** 对我们 LinkedIn 的人来说，第一步是展示有一个问题需要解决。所以被测量的东西就固定了。第一件事是查看随叫随到的数据，并看到我们整晚都在叫醒人们，因为一些实际上不会对成员造成任何影响的事情。所以我们说，“会员优先”，我们正在为此唤醒人们。

这是第一件事。然后我们说混沌工程是我们可以用来解决这些问题的工具之一。出现的第一个问题是，“如果你破坏网站的程度比我们已经在做的还要糟糕，那该怎么办？”这就是安全性的来源。展示我们所有的工具，第一个问题是，“安全在哪里？安全在哪里？”我之前也是这么说的。这都是为了限制爆炸半径。这种情况会推动买入。

然后是找到真正想要改变的顾客。这也很简单，一旦你有了随叫随到的数据——就是谁睡得最多。他们会非常积极地帮助你实现混沌工程。

诺拉:这并不难……我所做的是，我最终找到了一个对此非常感兴趣的团队。我的团队有些担心，但我也有团队喜欢，“是的，我们想做这个。这听起来是个好主意。”

我从他们开始。我从拥有最强适应能力的团队开始，并从那里获得了成功案例。然后它就进化了。之后，其他团队也想加入进来。

**Patrick:** 从我们的角度来看，我认为真正有益的事情是混沌实验刚刚开始，并表明…我认为对我们所有人来说，安全是一个巨大的问题。就商业案例而言，我认为…从我们的角度来看，这确实需要在我们的客户内部进行，但这显然是我们希望发起的事情，我们希望鼓励企业考虑停机时间对他们的成本和影响，以及…这对特定公司的客户信任意味着什么。

从我们的角度来看，我认为这在很大程度上是关于提出那些问题和提问。

**诺拉:**我也建议开始测试。不要从生产开始。

请和我一起再次感谢演讲者。

通过 Pixabay 的特征图像。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>