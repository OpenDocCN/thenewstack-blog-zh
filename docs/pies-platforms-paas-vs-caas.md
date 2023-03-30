# pie 和平台:平台即服务与容器即服务

> 原文：<https://thenewstack.io/pies-platforms-paas-vs-caas/>

[](https://www.cloudfoundry.org/)

[Childers](https://www.cloudfoundry.org/)

[Childers 在大规模计算和开源软件方面已经花费了超过 18 年的时间。2015 年，他成为云铸造基金会的联合创始人，担任技术参谋长。他是 Apache Cloudstack 的第一任副总裁，在 SunGard 领导企业云服务时，他帮助推动了该平台的发展，后来又在 Cumulogic 担任产品战略副总裁。在 SunGard 之前，他领导了包括 IRS.gov、USMint.gov、美林和 SEI Investments 在内的组织的任务关键型应用程序的重建工作。Chip 是 OSCON、LinuxCon North America、LC Japan、LC EU、ApacheCon、O ' Reilly Software Architecture Conference 等活动的资深演讲者。在空闲时间，奇普喜欢带着他的黑色实验室徒步旅行，驾驶双体船和太阳鱼，并试图跟上他年轻的女儿。](https://www.cloudfoundry.org/)

[](https://www.cloudfoundry.org/)[](https://www.cloudfoundry.org/)

我经常被问到使用平台即服务(PaaS)和容器即服务(CaaS)方法开发云应用程序的区别。什么时候选择一个或另一个是有意义的？描述这种差异以及它如何影响您的开发时间和资源的一种方法是，将它视为烘烤馅饼的过程。

你必须有一个好的外壳才能有一个好的馅饼——但是真正区别馅饼的是它的馅料。不过，你可能喜欢做馅饼皮，更喜欢自己动手做。如果你有时间，你会爆发出你的“烹饪的乐趣”，混合面团，擀开，然后切成合适的大小。这只是冒险中的馅饼皮部分——你甚至还没吃到馅料呢！

现在想象一下，你承诺带十个馅饼去参加一个聚会。突然间，较慢的手工制作方法看起来没那么有吸引力了。即使你经常自制面团，并以做得好而自豪，其他人也能熟练地从头开始制作面团。当然，还有一些人在准备馅饼皮方面做得非常好，他们在当地超市的冷冻食品区按打出售。

## 用 CaaS 和 PaaS 烤馅饼

使用 CaaS 平台制作馅饼的方法，您不仅可以搅拌自己的馅料，还可以从头开始制作包含馅料的饼皮。在加入自制馅料之前，你必须经历混合面团、擀开面皮、切割成适合平底锅的形状的过程。

借助像 [Cloud Foundry](https://www.cloudfoundry.org/) 这样的云计算应用平台方法，您可以跳过自制面团，将精力集中在馅料上——真正让您的馅饼与众不同的内容。

冷冻馅饼皮实际上是非常好的，一个好的面团制造商以提供一致的、高质量的馅饼皮而自豪。跳过这个耗时的步骤可以帮助你更快地烤好你的馅饼。

## 馅饼和平台

让我们更具体地了解一下使用 CaaS 平台和 Cloud Foundry 这样的平台编写应用程序的区别。

假设你正在用你最喜欢的语言——比如 Java、Python 或 Ruby——编写一个基于网络的应用程序。作为使用 CaaS 的开发人员，您需要采取额外的步骤来创建一个新的空容器映像，使用一个基本文件系统，并将代码移动到本地容器中。您可能会运行编译步骤，然后在编译过程中下载许多依赖项，然后创建 Docker 容器映像。一旦有了容器映像，就可以将其推送到 CaaS 平台。

像 Cloud Foundry 这样的平台为你做的就是照顾外壳。它不需要你打包你的软件。它会为你做的。

Cloud Foundry 使用 Linux 容器技术，通过一个简单的 CF Push 命令，平台就会为你创建容器。有了 Cloud Foundry，您可以在平台创建容器的同时专注于编写代码。

这个故事还有另一部分。除了处理像创建容器这样的细节之外，一个好的 PaaS 还做了很多事情来使你的软件在发布后更容易操作。

有很多方法可以使用容器平台并实现日志聚合。但有了像 Cloud Foundry 这样的系统，事情就简单得令人难以置信了——只需打印到控制台，平台就会捕获你的文本，并自动将其拉进一个共享的日志记录系统，在那里你可以看到你的应用程序的所有实例中的日志是什么样的，甚至可以跨多个应用程序。

PaaS 框架旨在使开发人员能够专注于编写代码或业务逻辑，而它负责诸如管道之类的细节。您不必担心创建容器或如何进行日志聚合。一旦软件进入环境，Cloud Foundry 可以简化软件的设置和管理。

一些企业开发人员想要弄清楚如何完成他们的应用程序的管道部分。我理解这样做的价值和兴趣。然而，一些开发人员宁愿专注于解决业务问题，或为初创公司编写新的应用程序。很多基础设施都没有应用程序中真正接触到客户的部分重要。

选择 CaaS 而不是 PaaS 平台，您是在用速度换取控制权。无论采用哪种方法，您都可以开发出优秀的应用程序。CaaS 方法只是需要更多的工作——就像从零开始混合 10 个馅饼皮比购买 10 个美味的现成皮要多得多，所以你可以专注于馅料。

*编者按:请听我们对 Chip Childers 的采访，了解他对 PaaS 与 CaaS 的更多见解:*

[PaaS vs CaaS:对应用开发者的实际意义](https://thenewstack.simplecast.com/episodes/paas-vs-caas-what-it-actually-means-for-application-developers)

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>