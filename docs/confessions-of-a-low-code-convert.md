# 一个低代码转换者的自白

> 原文：<https://thenewstack.io/confessions-of-a-low-code-convert/>

我是一名程序员。我写代码。我娱乐性地用 C++编程。在工作中，我喜欢低代码平台。我想你一定想知道像我这样的人是如何成为一个低代码爱好者的。下面是我的故事…

 [杰森·麦基

Jason 是 ServiceNow 的开发者福音总监。他是一名计算机科学极客，花了 20 年时间在政府和金融等部门开发应用程序和自动化业务流程。他身兼多职，从一线开发人员到领导和经理，以及内部和外部顾问的企业架构师。作为一名开发主管，他指导过许多开发团队完成技术堆栈的过渡，例如从 VB 到 Java 和从 Java 到 ServiceNow。作为一名狂热的制造商，Jason 打印、构建和编码了一些物联网设备，如由 ServiceNow 驱动的酒保机器人 LiquorBot。](https://www.linkedin.com/in/jason-mckee-056957104/) 

在过去的 27 年里，我一直从事业务应用程序开发，构建会计系统和许多其他内部工作流程和业务应用程序。我经历了你能想到的所有迭代:微软基础类、Visual Basic、ASP、JSP、servlets。我是 90 年代 1.0 天的 Java 程序员。换句话说，如果说出“代码低”这个词，我就是那种会深深叹息的人。

我喜欢低代码工具。

“Java 是新的 COBOL”的笑话不是没有根据的。在不破坏任何东西的情况下实现业务目标在 Java 中越来越难了。只是太超重了。Java EE、对象关系映射框架、UI 框架、依赖注入框架来管理所有其他框架——无论出现了什么库和框架来管理这种令人崩溃的复杂性，我们仍然发现自己处于一个非常乏味和耗时的映射和配置过程中，基本上要做数百行 XML 才能获得相当于“Hello，World！”

作为一名商业应用程序开发人员，我开始拓展业务，寻找更轻量级的框架，如 Python、Node、AWS 空间——除了依赖内部系统，我还能在那里托管什么呢？但是，即使是这样，它们也正在变得像 Java 一样复杂和笨重，然后你会发现自己仍然不得不选择和连接构建应用程序所需的所有不同的库。它比 Java 好，但只是逐渐好起来。

## 灯泡力矩

当我开始使用 ServiceNow 时，我是一名应用开发经理，有 6 名开发人员支持 54 个应用。非 Java 应用程序是任务关键型 Excel、Access、Fox Pro、VB“classic”和 PowerBuilder 以及你能想到的所有其他东西的大杂烩(我们甚至有一个 JCL 脚本来提取我们必须维护的会计代码)，这是 IT 部门多年来试图找到加速应用程序开发的银弹而积累的。我们从来没有带宽来用 Java 或任何其他现代工具替换或更新它们，所以我们总是在创可贴模式下勉强维护一切。我们只是不够敏捷，技术债务继续堆积。

一天，我的一位客户与我预约了一个小时的会议，讨论他在共享 Outlook 收件箱中运行的公共许可查询流程。他想将其搭载在我们的 it 服务管理安装之上。在几分钟内，很明显这是一个可怕的想法，但他需要的是一个适合 ServiceNow 应用程序的扣篮。

我在会议室里打开开发环境，在我们谈话的时候开始构建应用程序。我们在第 37 分钟结束了会议，因为我构建应用程序的速度比他想象未来状态的速度要快。他带着可以展示给他的团队的最小可行产品(MVP)离开了，而我带着同样的内啡肽冲动离开了，这种冲动通常来自于编写一段聪明的代码来解决棘手的问题。

这不是我在 ServiceNow 上开发的第一个应用，但这是我在[发现低代码工具有多么强大的时刻。使用传统工具，这可能需要六个月的时间——而且我不得不告诉他，除非是核心系统的故障修复，否则我无论如何也帮不了他。](https://www.servicenow.com/workflow/it-transformation/low-code-software-development-demand-reality-check/?campid=84354&cid=sc:brand:all:tns:q122:confessions_lowcode_convert_wwsn_article_link_1:22228:phdus:discov&utm_medium=sponsoredcontent&utm_source=tns)

## 处理样板文件

许多程序员听到“低代码工具”就会变得焦躁不安。但是事实是，特别是如果你正在构建过程而不是工具，低代码的解决方案并不会妨碍我的创造力和效率；他们使之成为可能。它们处理单调乏味、劳动密集型的样板文件，让我有时间编写我真正需要用来表达业务问题的 JavaScript 代码。而且还有很多地方你需要去(并且要去！)编写一些巧妙的代码来实现一个独特的业务需求。

修复或重构一个由业务线中的低代码[公民开发者](https://www.servicenow.com/workflow/employee-engagement/the-rise-of-citizen-developers/?campid=78942&cid=sc:brand:all:forbes:q122:enterprise_ux_heart_wwsn_article_link_2:22225:phdus:discov&utm_medium=sponsoredcontent&utm_source=forbes)编写的应用要比破译他们在庞大的任务关键型 Excel 电子表格中拼凑的任何疯狂东西容易得多。我发现低代码平台非常明智。它们减少了系统中的噪音，并消除了我工作中许多公认的乏味因素。

技术领域已经发生了巨大的变化。云的采用引入了一个无服务器容器化的世界。据 [Gartner](https://www.gartner.com/en/documents/4003532/how-to-navigate-the-application-platforms-market-including-cloud-native-low-code-and-saas) 称，目前使用的最高端应用平台是 Java EE 应用服务器平台，其中 40%计划在 2022 年 7 月之前被替换。这些替代将归结为基于云的容器化或低代码。

如果你需要高度的弹性和可伸缩性来面对客户，容器化是有意义的——例如，如果你正在构建下一个网飞，或者一个购物车，或者一个多人在线游戏。内部业务系统一般不会受益于容器化，也不需要 AWS 等云平台提供的资源弹性。自动化工作流是[低代码的理想用例](https://www.servicenow.com/workflow/crash-courses/how-to-get-started-with-low-code-development/?campid=78942&cid=sc:brand:all:forbes:q122:enterprise_ux_heart_wwsn_article_link_3:22226:phdus:discov&utm_medium=sponsoredcontent&utm_source=forbes)。随着公司对远程工作灵活性的需求不断增长，不必从头开始创建高代码工作流变得越来越重要。既费时又费钱。

最后，如果你从业务的角度来看这个等式，你会想用你的高价值程序员来完成高价值的任务。如果您是开发人员，您不希望陷入敷衍的、重复的项目中，这些项目使您无法实现您想要的独特的、富有表现力的问题解决方案。因此，我建议让业务分析师去处理表单上的字段顺序，因为几乎可以肯定，您还有更有趣的问题要解决。

这是两全其美的事情:您不必为简单的数据管理构建一个完整的 Java 应用程序，尽管您没有试图使用您的低代码工具来进行科学计算，但您肯定可以使用它来从电子表格和收件箱中获取流程，以实现高效、轻松的管理。流程自动化是一种定义非常明确的应用模式。为相同类型的用例从头开始一遍又一遍地构建没有太多意义，而且很快就会变得令人厌烦。低代码工具让业务工作流程应用的自动化变得异常迅速。

## 提高生产力

低代码并不意味着“没有代码”，这种区别很重要。有很多非代码工具，它们在一开始还不错，直到你碰到“不能从这里到达那里”的那堵墙，因为你试图解决的问题只是稍微超出了它们的预期用例。当您这样做时，没有迁移路径；你要么用别的东西代替它们，重新实现所有没有文档记录或设计良好的东西——要么你只能尽力让它运行。

专业开发人员使用低代码可以提高工作效率。他们甚至可以扩展到自己不擅长的领域。例如，如果您正在用 Java 构建业务应用程序，您通常也不进行移动应用程序开发，这导致创建和维护移动 ui 的过程非常繁琐，或者更糟的是，与另一个团队协作构建原生移动界面。

ServiceNow 的[原生移动功能](https://www.servicenow.com/solutions/build-and-automate/low-code-app-development.html?campid=84354&cid=sc:brand:all:tns:q122:confessions_lowcode_convert_wwsn_article_link_4:22231:phdus:discov&utm_medium=sponsoredcontent&utm_source=tns)使得向业务应用添加移动元素变得容易，开销更低，维护也更简单。如果他们有大量的工作要做，并且他们没有足够的时间从头开始构建所有的东西，为什么他们不把一些额外的任务交给业务分析师呢？低代码非常适合这一点。

不过说真的，我仍然写了相当多的代码——不出所料，主要是系统间的数据集成工作。只是我还没有做 Java 中必须做的那些样板文件。我就是这样学会不再担心，热爱低代码的。如果你正在寻找摆脱世俗，专注于有趣的事情的方法，你可能想试试。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>