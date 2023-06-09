# 关于僵尸的一切，一个掩盖元数据的开源努力

> 原文：<https://thenewstack.io/all-about-zombie-an-open-source-effort-to-mask-metadata/>

偏见是人性的一部分。这些偏见会威胁到代码的质量和安全性，并且会将产生代码的人排除在外。在参与和采用开源的规模上，这些偏见很容易被放大。

新堆栈之前写了关于[在最初考虑开源拉取请求期间屏蔽元数据](https://thenewstack.io/can-masking-metadata-boost-open-source-security-diversity/)如何帮助消除对寻求为开源项目做贡献的人的身份的偏见。现在我们写一个已经存在的技术解决方案来实现这一点。

开源解决方案处于无人维护的状态，是 Chrome 和 Mozilla 浏览器的[网络扩展](https://bugzilla.mozilla.org/show_bug.cgi?id=1366429)。[僵尸](https://github.com/zombie/blind-reviews/)编辑 GitHub 上代码评审请求的作者。

如果开源生态系统广泛采用类似的功能，维护人员可以更加专注于评估代码质量和防止技术债务，同时不会错过他们的宠物贡献者被黑客攻击和恶意注入正在悄悄通过他们的信号。

## 为什么要创造一个盲目的僵尸？

早在 2018 年，[时任 Mozilla 项目经理的 Emma Humphries](http://emmas.site) 就在寻找一种随机分配活跃贡献者的解决方案，以帮助对 bug 进行分类。大约在同一时间，他们还参加了与 Airbnb 合作举办的为期六周的研讨会，旨在改善开源的多样性。

与此同时，Mozilla 的同事 Don Marti 正在寻找提高项目可维护性和减少未来技术债务的方法。

现任 CafeMedia 生态系统创新副总裁的 Marti 告诉 New Stack 说:“有时候，对一个项目提出的改变实际上会起作用，它解决了提出它的人的问题。”“但这也意味着开源项目的发展会有一点额外的复杂性。”

马蒂说，这在小范围内可能没问题，但“当你积累了所有这些为一个人解决一个问题的小变化时，你会让项目变得越来越慢，以便能够为未来的问题做出改变。”

与 Mozilla 全球多样性和包容性负责人 Larissa Brown Shapiro 合作，三人组决定尝试双盲或屏蔽拉式请求，旨在支持开源质量和生产力，以及多样性、公平和包容性(DEI)工作。

“艾玛和我看到的是，开源质量出现的问题和大型组织中 DEI 讨论中出现的问题有很大的重叠，”Marti 说。“在很多开发团队中，我们都有一种‘看起来不错’的习惯。所以，你能用同样的方法解决质量问题和 DEI 问题吗？”

他认为这不仅仅是一个开源问题——这种[确认偏差](https://en.wikipedia.org/wiki/Confirmation_bias)存在于所有类型的软件开发团队中。

“我们有这种夸大的想法，认为软件开发人员是盒子里的精英头脑，但事实并非如此，”他说。“软件开发团队与任何灵长类社会群体(如猴群)有更多的共同点，而不是与开源质量和度量驱动的组织的一些理想化愿景有更多的共同点。”

他举了一个例子，当风险投资家保罗·格拉厄姆说他资助一家公司只是因为这位[的创始人看起来像脸书的马克·扎克伯格](https://www.businessinsider.com/yc-funds-mark-zuckerberg-look-alike-2013-5)。结果呢？一场灾难。

“这不仅仅是在评估创始人或高层人士的工作时，这种情况也发生在微观层面，一些人更容易经历不好的变化，而其他人则更容易经历好的变化，”马蒂说。

回到 2016 年，[加州理工大学和北卡罗来纳州立大学的研究人员进行的一项研究发现](https://peerj.com/preprints/1733/)女性身份贡献者的拉请求不太可能被接受。如果女性掩盖了自己的性别，她们的改变比男性更有可能被批准，而且总体上不太可能需要重构。

## 在正确的时间获得正确的信息

玛蒂把这些元数据——名字、照片和手柄——当作一种干扰。他提到一项医生评估疑似心脏病患者的研究。

“事实证明，查看最佳信息比查看大量信息要好，”他说。“平均而言，如果心脏病专家只得到重要的信息，他们可以从他们的心脏病专家那里得到更好的决定。”

他说，在第一次 PR 评审中隐藏元数据，同样有助于维护人员只关注最重要的信息，包括代码质量。通过屏蔽不必要的元数据，维护人员可以更加关注整个项目的后果和可操作性——而不是通过批准可能对项目寿命产生重大影响的小更改来增加技术债务。

“让人们根据代码的实际作用中立地思考这一点，而不是让他们大脑中的人识别电路过早启动，我认为这有积极的影响，”马蒂说。

## 投资新的项目维护者

僵尸 web 扩展最初是一直打开的，但是来自 Mozilla 内外用户的反馈是，一直打开并不太适合开源项目。

“我们有开发者指出这对他们很有用，我们也确实得到了一些关于如何平衡盲目代码审查和开源社会惯例的反馈，”Marti 说。

此类会议依赖于识别您的社区成员，以欢迎新的贡献者，并鼓励和激励他们重复参与。

“投资新维护者的道路是创建一个受欢迎的、多样化的、可持续的开源社区的支柱，” [Abby Cabunoc Mayes，](https://www.linkedin.com/in/abbycabs/)写道，她现在是 GitHub 的高级项目经理，以前在 Mozilla 工作。

Cabunoc Mayes 进一步引用了她从 [Mozilla Open Leaders 项目](https://foundation.mozilla.org/en/initiatives/mozilla-open-leaders/)中学到的其他经验，这些经验最终影响了这个屏蔽功能的一些变化。也就是说，一个可持续发展的社区需要两样东西:

1.  新来的人
2.  一种提升内在的方法

她写道，例如，如果你感谢开源贡献者，你更有可能获得他们的持续参与。开源社区的成功依赖于识别和最大化 [VM (Vicky) Brasseur](https://www.linkedin.com/in/vmbrasseur/) ，一位开源商业战略家，称之为[“得来速贡献”。](https://youtu.be/q3ie1duhpCg)

这种理解迫使 Marti 和 Humphries 的项目使评审者在完成初步评审后很容易关闭屏蔽功能。

## 社区规模重要吗？

“双盲代码审查不会是灵丹妙药，”Humphries 告诉新堆栈。然而，“将会有一个他们将会有效的领域。”

他们不认为元数据屏蔽将适用于他们目前大约一百名 Bandcamp 贡献者的团队。

“它不适用于小组织、少数贡献者或者你很容易就能看出贡献者的代码的地方。汉弗莱斯说:“这太容易让人想到‘哦，不，这是丽贝卡的准则。(“代码手”是开发人员认知签名的另一个名称——从评论中的表情符号一直到提交，开发人员的个性经常闪耀。)

Humphries 说:“它必须在你有一个非常大的项目的地方工作，比如有一个非常大的代码库的 [Mozilla 项目](https://github.com/mozilla/)，并且它将为较小的拉请求工作。”。“对于更大的拉取请求，这是行不通的，”他们说，这需要对话。

“当你进入那些更大的拉取请求时，我不确定你是否能保持匿名。”

然而，Sonatype 的开源开发者倡导者[萨尔·金米奇](https://www.linkedin.com/in/salkimmich/)认为，这种屏蔽甚至对六人项目也很有价值，因为它有助于防止恶意代码注入——这是一种高度的网络安全威胁，会接管社区中公认的个人账户。

他们告诉新的堆栈，这些定期的贡献者或维护者更容易被合并，因为维护者更可能看到公认的名称，而不是总是严格地评估代码的质量。更老练的黑客采用了频繁的项目贡献者的认知签名和风格，从而很容易忽略恶意代码。

这不是一个可以忽略的威胁。根据 [Sonatype 的“2021 年软件供应链状况”](https://www.sonatype.com/resources/state-of-the-software-supply-chain-2021)报告，在过去的两年里，这类代码增长了 650%。“他们会将恶意代码放入包装在看起来像典型贡献的东西中，”Kimmich 说

“许多维护人员没有接受过安全培训，甚至没有真正接受过最佳实践培训，”他们继续说道，他们只注意到了有价值的贡献，而没有注意到它隐藏的风险。

通过屏蔽元数据，您消除了[光环效应](https://en.wikipedia.org/wiki/Halo_effect)，并在担心是谁写的代码之前，根据质量来验证代码。

在任何掩饰生效之前，确保社区基础设施如心理安全到位是至关重要的。Humphries 警告说，像掩盖最初的代码审查这样的过程变化不能强加给一个非多样化的文化。这包括[行为准则](https://thenewstack.io/open-source-communities-need-more-safe-spaces-and-codes-of-conducts-now/)，它概述了攻击性或虐待行为的后果，以及返回社区的潜在途径。

## 数据伪装寻求维护者

最终，僵尸项目注定只能成为一个最低限度的可行产品，输给了 Mozilla 上的其他竞争对手。它在 GitHub 上是开源的，但目前没有维护。

“我们没有机会对现有的代码进行全面的定性研究，”Marti 说，因为其他功能变得更加重要。这个项目是在维护人员的日常工作之外建立的，一直持续到 2020 年初 Mozilla 的[第一次大裁员。](https://techcrunch.com/2020/01/15/mozilla-lays-off-70-as-it-waits-for-subscription-products-to-generate-revenue/)

“我们真的没有时间去探索它的全部，”汉弗莱斯说。但是这个项目确实提供了一些经验。

首先，他们意识到这种功能不应该作为 web 扩展来构建——它必须构建到项目本身中，最好是在 GitHub 中构建一个可以打开和关闭的功能。

Humphries 还希望看到内置的某种代码预处理，如整理器或格式化器，以“净化代码”的质量，并从第一个视图中删除更多的认知签名，如注释——攻击者可以利用这些签名来模仿熟悉的项目贡献者的风格。

在维护者考虑拉取请求之前，Humphries 说将这个杀毒软件与安全、单元和集成测试一起运行会很有趣。他们说，这将为维护者节省大量时间，因为“很多时候，当人们收到一个拉请求时，就像是”“‘好吧，这看起来不错，但是你对它进行过测试吗？"

Humphries 指出，在较大的项目中，核心团队倾向于从特性编写转向基础设施、规范和社区管理。他们说，如果你能根据规范自动测试，那就简化了负担过重的维护者的项目/产品经理的角色。

Kimmich 说，所有这些都可以整合到一个知识库中的 GitHub Actions 工作流自动化中。

他们说，开源世界上最大的项目往往都有测试，所以这些项目并不总是这类攻击的目标。

“他们会选择中型的，”金米奇说。“因此，他们正在寻找大约 3 到 500 个处于上升趋势的贡献者社区，他们正在看是否有新的贡献者加入其中。这是他们找到那些小甜点并进入的地方。”

他们补充说，这些攻击者通常会通过这些中型项目更深入地进入供应链，“他们知道他们会攻击每一个大型企业。”

数据屏蔽并不是完美的解决方案。这是一个复杂难题中的一个技术部分，必须解决代码和社区中日益增加的偏见和安全问题。开源所固有的社会和结构因素充其量仍然是脆弱的。

“[开源的模式还是有缺陷的](https://blog.container-solutions.com/wtf-is-wrong-with-open-source-communities)。你还在要求人们为你免费劳动，”汉弗莱斯说。

这次对话集中在可能导致糟糕代码的认知因素上，但这只是为了促进[开源可持续性](https://thenewstack.io/how-to-build-open-source-sustainability/)而必须解决的一部分。

正如汉弗莱斯所说，“你要求人们做大量的工作，却不给他们报酬。”

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>