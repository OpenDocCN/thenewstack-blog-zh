# 特性标记如何转变团队并支持开发运维

> 原文：<https://thenewstack.io/how-feature-flagging-transforms-teams-and-supports-devops/>

[launch darly](https://launchdarkly.com/)赞助了这篇帖子。

 [金·哈里森

金是 LaunchDarkly 的内容经理。她与开发人员和其他以 flag 为特色的团队紧密合作。金已经在硅谷的软件公司工作了五年多。她喜欢帮助团队将他们的故事融入世界，这样他们就可以分享他们的经验和最佳实践。Kim 拥有加州大学伯克利分校的社会学学士学位。](https://learn.launchdarkly.com/demo/) 

动作要快，不要弄坏东西。取悦顾客。满足将停机时间限制在绝对最小值的 SLA。跟上客户期望和当今竞争的步伐是一项艰巨的任务。更多、更快地发布是有风险的，并且会将不适当的负担从开发转移到运营，甚至组织内的业务团队。为了应对这些压力，许多软件开发团队已经采用了新的方法和工具来帮助他们优雅地完成这项工作。

一种被证明是成功的方法是促进跨职能部门的沟通。特别是 Atlassian，通过创建由工程主管、设计主管和产品经理组成的[三人组](https://www.atlassian.com/company/events/summit-us/watch-sessions/2017/team-culture/triad-magic-how-product-design-and-engineering-work-better-together)——开发团队，使这一实践正式化。有了这三个领域的领导，项目一定会从这三个重要视角的指导中受益。所有三个领导都负责制定战略并确保实现目标。他们的组合团队在整个开发周期中协作，构建技术上正确的特性，向客户交付价值。Atlassian 发现，通过将这样的领导集合在一起并让他们承担同等的责任，最终的工作不仅会顺利进行，还会让客户高兴并改善他们的体验。

还有许多其他组织也发现了促进跨职能协作的价值。像 Atlassian 一样，大多数人都同意这是一个帮助团队更快行动的好方法，而不会损害客户的价值。但许多采用这种方法的人也会同意，这种文化转变极大地受益于有助于保持良好沟通和可见性的工具。吉拉、Slack、GitHub、Bitbucket 和 Confluence 都是我们听说过的工具，即使我们还没有机会使用它们。

## 开始跑步

在所有这些工具中，特性管理是最突出的。(惊喜？)我们知道许多团队都有特征标志，但是我们注意到当团队将集中的特征管理系统整合到他们的过程中时，他们是如何转变的。当团队[开始标记](http://featureflags.io/feature-flag-introduction/)时，他们已经在考虑管理他们的发布过程。因此，当然，当他们开始围绕特性标记集中可见性和功能时，好处会超出工程范围。

最近，我们与来自 Atlassian 和 BrandVerge 的产品经理坐下来，讨论了标记在支持这种协作方面的[影响，以及它如何改变了他们组织内的开发周期。](https://launchdarkly.com/webinars/better-team-coordination/)[Atlassian 的高级产品经理 Taylor Pechacek](https://twitter.com/tpechacek) 和 BrandVerge 的产品总监 Marc Devens 与 LaunchDarkly 的产品和平台副总裁[Adam zimmen](https://www.linkedin.com/in/adamzimman/)分享了他们的经验。

Taylor 和 Marc 都指出，当特性标记是开发新特性的策略的一部分时，在工作开始之前，他们就已经在考虑把标记放在哪里以及如何检测它们。这意味着他们的团队需要了解他们正在构建什么，谁应该看到它，以及成功的标准是什么。它是面向一小部分用户的 VIP 功能吗？它会是一个所有用户都应该访问的核心特性吗？或者这是一个测试和验证新想法的机会？

在最高水平上，在构建之前考虑这些元素是足够有益的。就项目规范达成一致有助于所有相关人员理解并认同正在构建的内容和期望。但更重要的是，当工程、产品和设计在这些重要方面达成一致时，开发周期会更快，运行效率也会更高。

马克·埃文斯还指出，除了保持一致之外，从长远来看，将功能标志放在适当的位置这一本质为他的团队提供了灵活性。“我们真正受益的事情之一是在以后改变事情的能力，”他说。让每个人都在同一页上开始工作并有明确的方向感是很好的，但如果需要，让埃文斯的团队有能力快速转向也很有价值。当他们得到反馈，需要迭代的时候，他们可以保持快速前进。

## 现在你看到了

在更深的层次上，这些团队发现了可见性，并且沟通在他们的开发周期中得到了改善。是的，让每个人都在同一个页面上开始是很好的，但是一旦工作开始，这些团队现在有一个中心平台，每个人都可以看到正在构建的新功能。他们可以保持一致。

> “这真的改变了我对规划的所有看法……你实际上进入了这种模式，在这种模式中，更多的是关于整个‘构建、测量、学习’的咒语和这些反馈循环。你如何管理这些反馈循环，你如何回应客户，你如何迭代，你如何发展。”Atlassian 高级产品经理 Taylor Pechacek

在使用像 LaunchDarkly 这样的特性管理平台之前，只有开发团队知道代码库中有什么。在一些更大的组织中，不同的开发团队可能甚至没有一个好的方法在他们之间共享这些知识，信息是孤立的。特性管理系统为其他团队带来了包装在标志中的特性的可见性。他们可以看到存在什么，谁拥有它，它是如何被检测的，他们现在有办法积极参与测试或发布。

提高可见性意味着如果你是帮助构建、发布和推广一个特性的大团队中的一员，你会对它的状态以及你的角色如何发展有更好的认识。即使你没有直接参与功能的构建或营销，你仍然可以对它有所了解。从营销和销售到客户成功，整个组织的团队都将从中受益。构建其他特性的其他开发团队可以更好地理解他们自己的项目如何受到依赖关系的影响，并做出适当的计划。

> “作为产品经理，我要确保每个需要了解即将推出的功能的人都知道它的所有细节，我们已经有了支持文档，该版本所需的一切都在任何人看到之前完成了。”–brand verge 产品总监 Marc Devens

Taylor 和 Marc 都指出，当可见性提高时，跨职能团队的团队成员会有更强的主人翁意识和更清晰的授权路径。即使您正在标记功能，如果没有中央系统来管理您的标记，也很难了解功能和标记的存在和状态。当团队共享可见性并对谁在做什么有更强的意识时，对特性及其相关标志的所有权就成为可能。您可以将个人或小组分配到开发过程中的实际功能、标志或时刻。

> “对我们来说，所有权的关键在于可见性。因此，我们需要知道谁拥有该功能标志，或者至少谁知道它，以及它实际上如何与其他功能标志交互”Atlassian 高级产品经理 Taylor Pechacek

更进一步，集中的视图允许委托。有了可见性、所有权和允许任何人控制代码库中的特性的平台，团队可以共享与测试、发布和管理特性相关的任务。现在，开发人员可以专注于构建，并将发布控制权交给产品、营销或任何其他团队。这消除了工程团队的压力，并允许其他团队更积极地参与发布过程——无论是实验和反馈循环，还是向用户推出产品。

> BrandVerge 产品总监 Marc Devens 表示:“客户成功团队成员可能正在与询问此事的客户通话，他们可以在与客户通话的同时直接将钱存入客户账户。”

有了特性管理，团队对他们正在构建的东西有了更强的所有权，从概念，到发布和控制，最后在发布完成时清理，是时候移除标志了。要了解更多关于功能管理如何支持跨职能协作的对话，请查看 Pechacek、Devens 和 Zimman 参加的[录制的网络研讨会](https://launchdarkly.com/webinars/better-team-coordination/)。

专题图片:[利亚姆·德西奇](https://unsplash.com/photos/acKSt3THWKA?utm_source=unsplash&utm_medium=referral&utm_content=creditCopyText)上 [Unsplash](https://unsplash.com/search/photos/flags?utm_source=unsplash&utm_medium=referral&utm_content=creditCopyText) 。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>