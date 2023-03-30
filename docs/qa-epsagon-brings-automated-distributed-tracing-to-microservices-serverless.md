# 问与答:Epsagon 将自动分布式跟踪引入微服务，无需服务器

> 原文：<https://thenewstack.io/qa-epsagon-brings-automated-distributed-tracing-to-microservices-serverless/>

随着向分布式微服务软件架构的迁移，需要考虑的事情可能会比您最初意识到的更多。例如，您已经习惯使用的日志记录和应用程序性能管理(APM)工具可能不再适用。对于单块应用程序，传统日志可以帮助进行故障排除，但分布式架构和无数的 ethereal 微服务可能意味着您有无数的日志要仔细查看，以找出应用程序中的问题。此外，采用无服务器功能会带来成倍的复杂性，传统的日志记录工具和 APM 可能再也无法提供任何洞察力。

相反，分布式架构可能需要新的方法，如[分布式跟踪](https://opentracing.io/docs/overview/what-is-tracing/)，它可以洞察由许多相互作用的部分组成的软件中发生的事情，而不是单一的整体。我们采访了为云微服务提供自动跟踪的公司 [Epsagon](https://epsagon.com/) 的联合创始人兼首席执行官[尼赞·沙皮拉](https://il.linkedin.com/in/nitzan-shapira-521291108)，谈论现代应用程序开发和故障排除的状态，从 monoliths 到微服务的转变，并了解 Epsagon 如何让现代开发人员更加轻松。

**最近你听到的一切都是关于从整体服务到微服务的转变——组织是如何转变的？**

通常情况下，不是一步到位的。它分为两个部分 **—** 构建新的微服务应用和迁移现有应用。当然，编写新的应用程序要容易得多。在很多情况下，他们只是决定从现在开始在云上做微服务。例如，他们经常从 AWS 解决方案架构师那里获得帮助，或者从系统集成人员那里获得帮助，他们参与并完成大量实现工作。至于迁移，真的没有简单的方法将遗留应用迁移到微服务——这更像是从头开始编写，并将其连接到现有的遗留应用。工作量很大。

**公司从单片系统转向微服务和分布式架构时面临哪些挑战？**

很多。第一个挑战是开发本身，因为他们现有的软件不一定是为微服务、容器或无服务器构建的。可能是用不同的编程语言，有些已经过时了，所以要从头开始写很多东西。例如，他们过去可能使用 Java，现在他们想使用 Node.js 或 Go 之类的东西。他们可能不得不从头开始学习。然后，部署和 CI/CD 管道通常比它们现有的方法更先进。

我们看到的最大挑战是可见性——监控和故障排除，尤其是在生产中。他们中的大多数人使用混合工具，通常是 APM 或基础架构监控工具和日志聚合工具，这些工具对于单一应用程序来说很好，但突然之间，当他们进入微服务时，来自这些工具的数据无法讲述分布式系统的故事。在微服务环境中，这些解决方案不能很好地理解生产中正在发生的事情。日志并不是理解分布式系统的正确工具，因为它们之间没有关联。有时组织只有在生产后才意识到这一点，这是在生产中采用微服务架构的一个障碍。监控和故障排除是我们看到的首要问题。

谁将转向微服务？我们总是听到前沿技术公司的例子，但你是否看到更多的传统公司进行这种转变，如果是，如何进行？

是的，实际上，我们看到许多传统公司。它可以是零售或保险或任何类似的东西，突然他们明白他们必须更加数字化。例如，在电子商务领域，每个人都在走向数字化和在线，然后他们希望使用适当的技术来实现这一点。在这些情况下，这实际上更有趣，因为他们从云提供商那里获得了很多帮助。结果实际上是一个非常复杂的应用程序，非常现代——有时比你在科技公司看到的还要多，因为他们从第一天就这样做了。他们可以从零开始，在云中使用全新的架构。这些应用程序设计良好，但对于不习惯在这种环境中工作的企业来说，也非常复杂。

**说到从整体式迁移到微服务，组织传统上是如何监控和故障排除的，当您迁移到微服务时会有什么变化？**

我们今天看到的是，首先，IT 运营、开发人员和开发人员之间不再分离。开发人员必须更多地参与进来，因为每个问题都比以往更加复杂。将日志和跟踪分开实际上是没有意义的，因为在工具之间和部门之间有很多来回的事情发生。这是一个巨大的低效率。日志本身不足以理解系统，因为当您的架构包含几十或几百个节点时，数据流是很难理解的。你必须把它联系起来。组织很快意识到这一点，这就是为什么像分布式跟踪这样的技术开始出现。它们旨在克服一切都不相关的事实，而是在服务之间创建一个跟踪。

然而，现在，如果您查看跟踪解决方案，它们通常与度量和日志解决方案分开，这仍然会产生一个问题，因为它们必须在不同的工具之间来回切换。例如，在 [Epsagon](https://epsagon.com/) ，我们通过采用分布式跟踪是分布式应用的基础的方法来克服这个问题。我们的方法不是使用日志作为主要的事实来源，而是简单地提供对现有日志的访问。我们已经建立了我们称之为“有效载荷可见性”的东西，它捕获服务之间的数据，存储并索引它。它允许非常快速的故障排除。通常，使用 Epsagon 的人不再依赖他们的日志聚合服务。

**所以当我们谈论微服务时，我们通常会想到容器和 Kubernetes。无服务器在这一切中处于什么位置？**

无服务器是一种可以作为微服务故事一部分的技术。这是最前沿的。它仍然被认为是非常先进的，显然，它还没有普及。如果一家公司决定转向云，那么在很多情况下，他们会选择尽可能尝试无服务器，因为这样更有意义。他们不需要管理基础设施，而且非常便宜。最终，无论何时需要，它都将是无服务器、容器和传统虚拟机的混合，因为不可能从头开始编写所有内容。无服务器需要大量的设计和思考。

**无服务器给日志记录和跟踪带来了什么挑战，你们是如何用 Epsagon 克服这些挑战的？**

第一个挑战是，一切都变得更加分散，至少多一个数量级，因为每个功能都小得多，而你有更多的功能。架构要复杂得多。如果你用圆木，你可能会很快迷路。这就是分布式跟踪更为关键的地方。如果你看看我们的一些案例研究，你可以看到直观的地图，它显示了复杂性，以及如果没有它们，理解正在发生的事情是多么困难。另一个问题是没有地方安装代理。传统的 APM 依赖于代理，但是您需要将它们安装在某个地方。代理做不同的事情，这些事情不能在无服务器功能中完成。为了进行跟踪，你需要进行插装，你需要在代码内部，在没有代理的情况下进行。这是一个技术挑战。

例如，在 Epsagon，从第一天起，我们就不得不用代理来构建一切，只使用一个代码库，它可以是任何服务的一部分。这是一个优势，因为今天我们可以为无服务器、容器和传统虚拟机提供相同的体验。

这是开发人员在构建应用程序时需要考虑的事情吗，或者他们可以追溯应用它吗？

我们假设我们的客户已经在生产中运行，可能有数千个微服务。我们做的一切都是自动化的。如果你有一个现有的应用程序，Epsagon 可以自动注入到你现有的服务中。然后，所有的跟踪和检测都完全自动进行，包括连接到您的云帐户或 Kubernetes 集群，以生成一系列指标和见解作为第一步。我们所做的一切都是基于这样的假设，即应用程序已经以非常高的规模在生产中运行。所以，答案是否定的，在使用 Epsagon 之前，你不必提前做决定。

**除了对语言和架构的考虑之外，从整体服务到微服务的转变是否需要组织上的改变？让这一切更好的工作？**

是的。我认为必须发生的主要变化是开发人员和运营人员不再分离。这实际上是一个很大的变化，因为这就是今天的工作方式。这意味着开发人员更多地参与到代码部署后发生的事情中。已经不是运营团队的问题了。应用程序的所有者变成了开发者，而不一定是运营者。这是大多数组织仍在努力解决的问题。如果您考虑托管服务和无服务器之类的东西，运营团队有时甚至不知道新服务现在已经投入生产。必须有人知道这件事——如果不是运营部门，那就必须是开发人员。

**以前，Epsagon 专注于成本监控，将其作为一项差异化优势，但现在不那么关注了。我们想知道，您认为现在您在监控领域的竞争优势是什么？**

我们一直拥有的相同区别是，我们可以进行自动化的分布式跟踪，这已经非常困难了。目前还没有针对我们所做的这类应用程序进行自动分布式跟踪的解决方案。如果您现在有一个基于云的容器应用程序，您没有解决方案可以自动为您提供这种跟踪，除非您想花几周或几个月的时间自己实现 OpenTracing 之类的东西，我们在幕后使用它，但我们会为您实现。这是一个很大的区别。

与众不同的是，我们整合了许多工具，为快速故障排除提供了高效的体验。有效负载可见性意味着您可以在任何给定时间访问您的数据，无需采样。这对于故障排除来说是超级强大的。我们的客户通常从混合工具开始，当他们迁移到 Epsagon 后，他们不再使用混合工具，而只使用 Epsagon。我们让他们有机会就发生的事情提出非常复杂的问题，并立即找到解决方案，这样他们就可以在几分钟内解决问题，而不是几小时或几天。这一直是差异所在。

我们做的一些很酷的事情是引入对特殊服务的支持，如 AWS App Sync，这是 AWS 中非常受欢迎的服务，目前没有故障排除解决方案。Epsagon 是目前唯一能做到这一点的供应商。目前还没有解决方案从根本上基于分布式跟踪，并像我们这样自动完成。

**爱普生是如何做到这一点的？它如何自动发现现有架构中的所有这些服务？**

这一切都是基于自动化代码工具。我们的代码库自动进入现有的应用程序。这可以通过注入、CI/CD 插件或者仅仅在顶部添加几行代码来实现。只需按照说明操作，一旦有了库，代码就会被自动检测。我们已经支持五大编程语言。一旦对代码进行了检测，运行时就会将提取的事件发送回我们的 SaaS 平台。这就是我们能够将所有这些事件连接在一起的引擎，以创建跨非常多种框架和技术的分布式跟踪。它可以是一个向 Kafka 发布消息的容器，用 Java 编写，转到 express Node.js 容器，然后触发 Lambda 函数——所有这些东西都将自动从头到尾连接起来。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>