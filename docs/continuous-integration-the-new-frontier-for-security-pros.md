# 持续集成:安全专家的新领域

> 原文：<https://thenewstack.io/continuous-integration-the-new-frontier-for-security-pros/>

[GitLab](https://about.gitlab.com/) 赞助本帖。

 [辛迪·布莱克

Cindy 是 GitLab 的高级安全宣传员。](https://www.linkedin.com/in/cblake2000/) 

1960 年，约翰·肯尼迪总统提出了著名的“新边疆”作为他的政治口号和立法计划，暗示了一个变革的新时代和对二战后美国现状的颠覆。应用程序开发世界正面临着一个类似的，尽管不那么引人注目的新领域，因为它拥抱了 DevOps 的[左移](https://thenewstack.io/the-great-shift-left-what-changes-for-developers-and-security-teams/)。

采用 DevOps 的企业了解更早和协作地将安全性纳入考虑范围的需要——他们认识到需要向左转，以使他们的开发人员能够在 DevOps 生命周期中更快地发现和修复安全缺陷。这些组织中的许多已经通过使用 API 和插件以及 CI [脚本](https://www.blazemeter.com/blog/how-to-integrate-your-github-repository-to-your-jenkins-project)的[将他们的安全扫描器集成到他们的 CI 管道中，以在流行的 CI 工具(如 Jenkins 和 Circle CI)中向开发人员提供扫描结果。但是，他们可能选择了一条挑战换挑战的道路。](https://blog.probely.com/how-to-configure-jenkins-to-integrate-security-into-ci-cd-2b340728de56)

有两种途径可供选择，其中一种不太为安全专业人士所知。常见的方法是将安全团队最喜欢的安全扫描器拼凑在一起，将结果输入 CI 管道供开发人员查看，并期望开发人员能够适应。另一条路是 DevOps 专业人员和软件工程师更熟悉的，那就是选择一个嵌入现成安全扫描的 CI——调整安全性以适应开发人员流程，而不牺牲效率或风险。

选择将单个安全扫描器集成到其管道中的组织不可避免地会面临至少一个或多个这样的挑战。

## **维持脆弱的整合**

首先，集成很难实现和维护。[DevSecOps Realities and Opportunities](https://www.synopsys.com/software-integrity/resources/analyst-reports/examining-devops.html)白皮书基于 451 Research(由安全公司 Synopsys 委托)进行的研究，显示受访者 CI/CD 工作流中固有的最大应用安全测试挑战是缺乏自动化的集成安全工具(61%)。Synopsys 在[的博客文章](https://www.synopsys.com/blogs/software-security/security-challenges-cicd-workflows/)中指出，虽然大多数应用安全工具都有一个命令行界面(CLI)来将工具集成到 CI/CD 管道中，但您必须考虑这些应用安全工具运行的管道中的多个定义的检查点。

为了说明这一点，Synopsys 解释道:

*“…提交前检查完成后，管道启动，并运行增量静态应用程序安全测试(SAST)。一旦测试完成，管道应该无缝地进入下一个阶段:软件组成分析(SCA)和更深入、更彻底的 SAST 评估。”*

它显示了 Web IDE 中的预提交 SAST、代码提交时的增量 SAST 以及构建时的另一次 SAST 扫描。它还显示了 DAST，IAST 和 fuzzing 在生命周期的后期测试。每一点都需要在您的 CI/CD 管道中精心编写脚本，如果您对源代码管理、CI 和 CD 使用不同的工具，可能需要使用多种工具。

每个集成都有自己独特的需求和发布时间表，这就更加复杂了。例如，一个扫描仪可能以 PDF 和 XML 格式报告结果，而另一个工具可能以 JASON 或 HTML 格式生成报告。不幸的是，当涉及到为缺陷跟踪、更新度量仪表板和中断构建等常见活动定制插件时，这可能是一个巨大的挑战。您一直处于维护脆弱的工具链的状态。

安全专家应该考虑开发专家已经知道的东西。将安全性集成到 CI/CD 中的单一平台[不仅可以消除这一维护难题，而且实际上还能提供更高的效率和更低的风险。通过使用 CI 功能中已经包含的](https://about.gitlab.com/blog/2020/12/08/security-features-in-ultimate/)[审查应用](https://docs.gitlab.com/ee/ci/review_apps/)，利用 SAST、DAST 和 fuzzing 的洞察力，可以从根源上消除漏洞。

## **为开发人员提供可行的发现**

对于您希望集成的每个扫描仪，UI 体验可能会有所不同。一个可以提供操作，另一个只能提供评论。例如，仅注释仍然需要将信息复制到另一个工具来创建工作单(或问题)。它可能没有像代码行这样的信息，而这些信息对负责修复工作的人来说是有帮助的。即使是可操作的结果也可能不会自动与吉拉等其他工具集成，因此可能需要另一个集成点来维护。

## **实施所需的扫描和策略**

众所周知，开发团队的工作速度比安全团队快，可能是因为开发人员总是比安全专家多。安全团队必须依靠自动化来应用反映其组织独特风险偏好的安全策略。如果您有一个复杂的工具链，那么在任何需要的地方应用适当的安全设置都是一个挑战。每个扫描器通常都有自己的设置，但是您必须设置 CI 管道来应用可接受(或不可接受)的内容，以传递到部署中。通常，这些设置必须在项目之间重复。

## **跨工具可见性**

根据 SmartDraw 的 [2019 DevOps 可见性报告](https://www.smartdraw.com/about/press/devops-survey.htm)，84%的组织表示 DevOps 可见性对他们很重要。在任何现有渠道中实施整个安全工具链都是一项挑战。你能看到，在 DevOps 工具中，谁改变了什么，在哪里，什么时候，为什么？如果有人授予例外并批准 CI 中的合并请求/拉取请求，您的安全仪表板能看到是谁做的吗？为什么？如果在整个开发生命周期中没有[端到端的可见性](https://docs.gitlab.com/ee/user/admin_area/settings/visibility_and_access_controls.html)，团队在面对审计和法规遵从性时就会面临挑战。

## **能够跨数百个项目进行扩展**

如果你已经为一个项目建立了 DIY CI 渠道，那么恭喜你。现在，假设您想要将该技术应用到使用不同编程语言的项目中。你需要一条新的管道。这是又一条需要维护的管道。就像电子表格或幻灯片的版本一样，您如何确保它们保持同步？您真正需要的是一个 CI 模板，它能自动识别所用编程语言的正确扫描器。组织越大，项目越复杂。

## **不可预测的成本**

如果您是按扫描或应用程序(或者更糟，按扫描的大小)来支付安全扫描仪的费用，那么在收到账单之前很难预测成本。迭代 DevOps 扫描和更分散的扫描环境的复杂性因素，其中成本由开发人员的行为决定。现在层在一个多年的预测。当 DevOps 实践在您的组织中更全面地部署时，您的扫描还需要多少扫描、应用程序或 GB？你需要一个按座位收费的解决方案，一个更加稳定和可预测的变量。如果您对 CI 和安全性采取更全面的方法，您就可以实现这一目标。

那么，如何避免这些挑战，或者至少尽量减少它们的发生呢？

## **新领域:在 CI 中实现安全自动化**

成功实施可扩展的 DevSecOps 的关键是嵌入到您的 CI 中的[安全自动化](https://about.gitlab.com/blog/2020/07/08/devsecops-security-automation/)。这不仅有助于消除安全瓶颈，而且还增强了开发人员的能力，使他们能够将精力和精力集中在更大的问题上。

### **首先，考虑一个单一的集成平台**

如果您的开发人员已经在使用包含安全性的 CI 平台，请接受它。看看它能为你做什么。如果有缺点，通过 Dev 和 Sec 的共同努力，它们可能很容易被克服。如果他们没有使用已经包含安全性的配置项，您也许能够说服他们做出改变。许多领先的独立 CI 工具需要复杂而脆弱的 CI 脚本，许多工程公司已经做好了改变的准备。如果他们觉得受现有产品的束缚，他们仍然可以使用现有的 CI 工具作为记录的 CI，但只需在集成了 CI 和安全性的平台之间进行一次集成，如 GitLab 及其现有 CI。这种单个配置项到配置项的集成比多个安全工具集成到传统配置项要容易维护得多。

单个平台不仅可以让您免去集成的麻烦，还可以在整个软件开发生命周期中提供审计的可见性。此外，通过使用单一的真实来源来记录变更、管理基于角色的访问和捕获漏洞，您可以提高共享工具的透明度，并在开发人员和安全团队之间建立信任。

### **接下来，利用 CI 来应用安全策略**

一旦您确定了您的策略，只需配置它们。需要考虑的事项包括:

*   您将启用哪些扫描仪？
*   您*需要哪些扫描仪*？
*   您是否需要批准(哪些人/团体？)对于严重或高严重性的漏洞？

一些供应商在没有编程知识的情况下，通过复选框 UI 轻松配置管道，以打开/关闭常用的 [DevOps 工具](https://docs.gitlab.com/ee/topics/autodevops/)和[安全策略](https://docs.gitlab.com/ee/user/application_security/configuration/)。这些通常就足够了，除非您有独特的需求。如果这样做，可以很容易地在 CI.yml 文件中编写 CI 管道脚本。 [Markdown 语言](https://about.gitlab.com/blog/2018/08/17/gitlab-markdown-tutorial/)非常简单，不比简单的电子表格宏更难学。这种方式和 DIY 方式的主要区别在于，在这里，您只需为各种语言和所有扫描仪(SAST、DAST、依赖、容器、模糊化等)定制一次管道。

大多数商店希望确保开发人员确实使用了所需的扫描和策略设置。最简单的方法是模板化您的 CI 设置。管理员可以设置配置项模板，并要求每个项目或特定项目组使用这些模板。借助端到端可见性，如果授权内部人员更改了模板，甚至更改了特定工作的策略，都会被捕获。寻找像 GitLab 这样的 [CI 解决方案，它已经包含了您可能需要的所有](https://docs.gitlab.com/ee/ci/)[模板](https://docs.gitlab.com/ee/development/cicd/templates.html)，而且还允许定制以匹配任何需要的策略。通过使用模板，您可以通过内置参数来简化管道流程，并确保一致性。

定期评估现有政策的有效性也是一个好主意。它们被覆盖的频率是多少？现在可能是使用 CI 解决方案的时候了，它允许您根据需要定制模板和权限。寻找[工具](https://docs.gitlab.com/ee/user/application_security/sast/index.html#configure-sast-in-the-ui),帮助您的安全团队设置防护栏，而无需了解如何编写 CI yml 文件，但也要确保让您的开发人员参与工具选择或介绍不会影响他们的工作流和首选工具集的左移方法。

虽然 DevSecOps 的这一新领域和左移可能感觉像是未知的领域，但通过从开发人员工作流开始，考虑将 Dev 和 Sec 结合起来的单一工具，并利用 CI，您可以提高所有相关人员的效率，同时仍然降低风险。

[*在 GitLab*](https://about.gitlab.com/solutions/dev-sec-ops/?utm_source=vmblog&utm_medium=pressrelease&utm_content=gitlab2021predictions) *了解更多关于 DevSecOps 的信息。*

Synopsys 和 CircleCI 是新堆栈的赞助商。

通过 Pixabay 的特征图像。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>