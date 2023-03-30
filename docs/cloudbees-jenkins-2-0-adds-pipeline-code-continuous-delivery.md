# Jenkins 2.0 增加了持续交付的管道代码

> 原文：<https://thenewstack.io/cloudbees-jenkins-2-0-adds-pipeline-code-continuous-delivery/>

我们倾向于谈论“CI/CD”(持续集成/持续交付)，就好像它是一件事情，并且在它们之间没有斜线。甚至当 [Jez Humble 和 David Farley 出版了一本关于后者](http://martinfowler.com/delivery.html)的书，将它作为自己的一个目标时，[这本书的介绍将它](http://martinfowler.com/delivery.html)描述为建立在 CI 的“基础”上，或者[是 CI](https://www.thoughtworks.com/continuous-delivery) 的“自然延伸”。你不用看得太远，就能发现 CD 是 CI 的[的“逻辑演变”。微软不止一次地将 CD 描述为](http://www.methodsandtools.com/archive/archive.php?id=121)[当你完成 CI](https://www.asp.net/aspnet/overview/developing-apps-with-windows-azure/building-real-world-cloud-apps-with-windows-azure/continuous-integration-and-continuous-delivery) 时按下的魔法按钮。最后和/或最不重要的一点是， [IBM 将 CD 表示为 CI，只是带有一个“d”。](https://www.ibm.com/developerworks/library/d-continuous-delivery-framework-jenkins/d-continuous-delivery-framework-jenkins-pdf.pdf)

当[正确解释](https://www.atlassian.com/continuous-delivery/nuts-and-bolts-continuous-integration)时，连续交付根本不是将软件推出“出口”滑槽的快速重复过程。它实际上是一个复杂的事件链，确保将经过适当测试的工作代码发布到产品中，然后管理其生命周期。在一个高度连续的环境中，旧代码会很快消亡，但与其说是产品*消亡，不如说是产品*蜕掉了旧皮。

令人难以置信的是，正是在这里，我们开始意识到 Jenkins，组织中 CI/CD 原则最明显的代言人——与这个主题同义，以至于我听到不止一个 CIO 称 CI/CD 本身为“你知道，有管家的那个”——并没有正式维护一个自动化连续交付管道的首选流程。尽管 Martin Fowler 被认为是 CI 的创始人，[将 CD 定义为需要一个“部署管道”，但是](http://www.methodsandtools.com/archive/archive.php?id=121)与 Jenkins 一起实现这样一个管道需要遵循一个或多个过多的方法。

“詹金斯近乎无限的可扩展性的好处在于，人们实际上已经在用詹金斯实现连续的交付管道，”詹金斯项目的资深贡献者、詹金斯与 Puppet 的共同实施者泰勒·克罗伊(r . Tyler Schmidt)在接受 New Stack 采访时说他们把已经存在的东西拼凑在一起。"

## 一次送货，不是十二次

周二，商业 Jenkins 的管理者 CloudBees 宣布 Jenkins 2.0 在社区中正式发布。随着这一版本的发布，出现了第一个官方支持的特定领域语言(DSL)的实现，用于对连续交付的管道进行编码，即“管道即代码”

换句话说，这个名字已经成为持续交付概念的同义词，现在正在真正实现它。

克罗伊说:“现在詹金斯懂得并能说一种与生俱来的交付管道语言，而不是像以前那样必须拼凑这些不同的部分。以前没有。”

在 Jenkins 中，克罗伊本人是许多知识渊博的输送管道原则的演示者之一(不要像许多人经常做的那样与“部署管道”混淆)。但是这个原则已经用各种脚本语言演示过了:CloudBees 展示了带有 Groovy 的[CD；其他人](http://www.slideshare.net/cloudbees/pimp-your-continuous-delivery-pipeline-with-jenkins-workflow-wjax-14)[建议使用构建工具 Ant](http://www.methodsandtools.com/archive/archive.php?id=121) (基于 XML 的构建文件)；其他人用构建工具 Gradle 演示了 [Jenkins。其中一些构建工具和脚本语言依赖于](https://www.youtube.com/watch?v=V0FpbDkKYtA) [Jenkins 的构建插件](https://wiki.jenkins-ci.org/display/JENKINS/Build+Pipeline+Plugin)，而其他的依赖于完全不同的 [Jenkins 的交付管道插件](https://wiki.jenkins-ci.org/display/JENKINS/Delivery+Pipeline+Plugin)。

所以这是连续交付，从这个意义上说，很多人交付了大量的方法来完成几乎相同的事情。

“作为一名实施者，作为一名 Jenkins 持续交付的实践者，这一点很好，”克罗伊说，“[*就是*，它还允许我采用以前的软件交付方式的隐式模型，并在源代码中非常明确地定义它，我可以签入，我可以跟踪，我可以审计，就像我可以[T2]我的软件的每一个其他部分一样。”

## 过程的价值

克罗伊在 Jenkins 社区的突出地位证明了他对流程和最佳实践的熟悉，该社区的成员一定与他分享了这些流程和最佳实践。他告诉我们，根据他的计算，在没有使用 Jenkins 的管道比喻的情况下，大约有四五个*事实上的*最佳实践可以说明连续交付流程是如何被链接在一起的。这些是独立于那些使用 Jenkins 1.x 的组织的小组，并且附加了一个插件和一个脚本语言，但是仍然省略了管道隐喻。这两个类都清楚地认识到持续交付比持续集成更重要，除了这次是真的。

但是克罗伊说，他相信这些组织可能已经采用了最适合他们目的的模型。事实上，当我问他这些组织是否会保护甚至觊觎这些过程作为他们的知识产权时，克罗伊说，在某些情况下，是的。

他说，网飞已经证明了交付过程可以成为公司的附加值，即使是非常公开地这样做。但是这种价值是可以量化的。

“从一个地方到另一个地方需要付出很多努力，”他说，“每个交付过程都会有所不同，这取决于你的产品，你的软件是如何构建的，它是如何组合在一起的。这并不是说有人会效仿网飞的做法，突然成为网飞的竞争对手。但与五年或十年前不同的是，交付管道和流程被视为只有运营人员或开发人员才关心的事情，网飞已经表明，它实际上可以通过允许他们越来越快地移动来显著改变企业的地位和位置，这是一个明确的竞争优势。”

这使得流水线操作(以及迄今为止取代它的流程)越来越像*业务流程管理*——一种不仅编码业务中如何完成事情，而且像保护秘密信息一样保护它的方式。克罗伊承认，詹金斯 2.0 不会推动这些企业遵守一些单一的，自我声明的标准来定义这些过程。相反，采用 Jenkins 2.0 新的声明性 DSL 可能会迫使这些企业重新考虑他们的方法，并很可能简化它们。

“这就是，对我个人来说，为什么获得持续交付到詹金斯是如此重要，”克罗伊说。“它确实改变了你交付软件的方式，以及你对它的看法，变得更好。”

但是我也和克罗伊分享了该领域从业者的观点，他们公开宣称“交付”是开发过程的最后阶段，或者许多人称之为“开发完成”虽然支持者认为 CD 的标志是保持一种永久准备就绪的状态，但怀疑者认为如果软件总是准备就绪，那么[就永远不会真正*就绪*](http://programmers.stackexchange.com/questions/124193/how-can-continuous-delivery-work-in-practice) 。

“‘软件准备好了吗？’对你的个人贡献者，你的项目经理，你的产品经理，你的质量保证经理，和你的运营团队来说，意味着非常不同的事情，”泰勒·克罗伊解释到软件的就绪状态对于生产线上每个将要接触并参与交付软件的人来说有着非常不同的意义。将它引入一个更明确的模型，比如 Jenkins 2.0 中的 pipeline-as-code，为您提供以前不存在的协作点。"

这些协作点是项目准备从一个环境过渡到另一个环境的地方:例如，从开发人员转移到可能需要运行冒烟测试的 QA 工程师。那么从 QA 的角度来看，软件可能是“准备好了”，但是仅仅是在移动到下一个阶段的范围内。最终，产品经理可能会宣布产品“准备好”出现在客户面前。即使这样，在 CD 的背景下，软件可能永远不会“完成”——只是准备进化到下一个阶段。

“管道让你可以表达所有这些，这是你现在在很多工具中没有的东西，”克罗伊说。“但随着你开始加快软件业务的发展，掌握‘准备好’的含义变得更加重要。”

来自 Pixabay 的公共域中的特征图像。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>