# AWS 中的远程调试:调试工具集中缺失的一环

> 原文：<https://thenewstack.io/remote-debugging-in-aws-the-missing-link-in-your-debugging-toolset/>

[桑德拉](https://www.thundra.io/)赞助了这篇文章。

 [埃姆拉·萨姆丹

艾姆拉是桑德拉公司的产品副总裁。他热衷于无服务器、可观测性和混沌工程。](https://www.linkedin.com/in/emrahsamdan/) 

虽然软件开发过程已经发展到包括一些确保缺陷在早期被发现的技术，但是预测系统何时以及如何失败是不可能的。问题不再是*是否会出现*缺陷，而是*何时*——以及*如何*快速找到并修复它们以限制它们的影响。

无论你有多熟练，bug 都是不可避免的。您可以遵循所有最佳软件开发实践，正确定义和调用所有函数，并编写测试。尽管如此，有些事情最终还是会出错，你需要找出原因。

在构建应用程序或从事软件项目时，您可以对奇特的算法、应用程序基础结构或用户界面设计进行创新。但是您必须彻底调试您的代码，以确保它按预期工作。在这篇文章中，您将了解为什么在本地环境中调试不足以解决问题，以及为什么应该将远程调试添加到您的工具集中。

## 在本地开发环境中调试

过去，开发人员在他们的本地开发环境中调试代码。本地调试在开发环境中是有效的，但是在解决云中的问题时就不够了——因为环境之间的差异。

调试对不同的人有不同的意义。对于开发人员来说，这是一种从代码中删除 bug 的方法。调试时，您正在检查代码的实际行为和预期行为之间出现偏差的原因。您可以通过检查代码、建立断点、评估应用程序的方法和变量来确定偏差的原因，从而做到这一点。调试在软件中很重要，因为它使您能够构建更好的应用程序，并减少可能影响最终用户的错误的发生。

因为调试与开发紧密相关，ide 和代码编辑器已经建立了各种机制，允许您编写代码并在本地调试。大多数编程语言也有与各种 ide 集成来完成相同任务的调试器。比如 Python 有[pdb](https://docs.python.org/3/library/pdb.html)Ruby 有 [Byebug](https://github.com/deivid-rodriguez/byebug) 和 [Pry](https://github.com/pry/pry) 。

随着现代应用程序变得越来越复杂，仅在本地环境中进行调试已经被证明是不够的。

## 为什么在本地环境中调试应用程序是不够的

当应用程序处于开发阶段时，测试场景是清晰的，环境是已知的。生产中的应用程序是另一回事。生产系统的不可预测性使得很难重现错误并模拟您需要的确切情况，以便在本地进行调查。因为开发人员环境不同于生产环境，所以您可能会发现捕捉导致 bug 的实际状态很有挑战性——包括变量值、特定线程和代码试图做的其他事情。

另外，有些 bug 只有推到云环境下才会发生。它们在开发环境中是不可复制的。这使得开发人员更难预测当代码被推送到 AWS 这样的云服务时可能发生的每个错误。

现代应用程序通常使用第三方 API，这些 API 在本地开发过程中要么被嘲笑，要么被跳过。像这样的 API 是整个应用程序作为一个整体运行所必需的。由于它们是在第三方的控制之下，所以它们面临着挑战——例如控制组成它们的逻辑的代码、托管它们的服务器，或者在应用程序和 API 之间传输的数据。

一句话:在本地调试应用程序是必要的，但不足以发现和解决所有问题。在微服务或无服务器架构中尤其如此，在这些架构中，多个服务运行并相互通信。为了大幅减少云原生应用程序中解决 bug 的时间，开发人员需要接受一种新的调试思维。

## 为什么在云中调试应用程序很难

在开发环境中调试代码要比在生产环境中容易得多。在开发环境中，您可以舒适地使用 IDE 和调试器。您还可以设置断点，单步执行您的代码，并提供修复。

但是当应用程序转到云端时，各种疯狂的事情都会发生。许多意想不到的因素——如高并发使用率、高可伸缩性、不可预测的系统行为和内存泄漏——会使您的代码不稳定。有些问题可能会间歇性地出现，而有些问题只有在重新启动应用程序时才会出现。这种不可预测的性质使得重现和调试云环境错误变得困难。

毫无疑问，调试是应用程序生命周期的重要部分；但是，因为现代应用程序的真实环境是不可预测的，并且难以重现，所以为问题做准备是一项挑战。每当最终用户报告生产系统没有按预期工作时，通常很难理解错误的根本原因。因为我们生活在一个错误不可避免且业务正常运行至关重要的世界，生产中的一个错误意味着金钱、时间的损失，或者(甚至更糟)关键服务的中断。据估计，一个小时的停机时间会造成 68，000 美元的收入损失。为了避免这种巨大的损失，您需要尽快解决生产缺陷并恢复正常的业务运营。开发人员经常发现很难在云中调试现代应用程序，因为与检测和修复此类应用程序中的错误相关的信息分布在多个来源之间，如日志文件。筛选这样的文件就像大海捞针一样乏味。

### 筛选日志的问题是

历史上，日志对于调试生产问题至关重要；而微服务架构的出现，让日志变得比以往更加关键。不可否认的是，微服务架构提供了许多好处——例如加速功能交付、采用不同的技术堆栈、向上和向下扩展、采用敏捷开发以及独立部署每个节点的能力。但是它们也给解决问题和理解应用程序的行为带来了新的挑战。

在微服务架构中，调试错误所需的信息可能分布在多个不同的来源中，如本地变量、调用堆栈、数据库查询、事件队列、日志文件等。因为每个微服务都实现了自己的事件记录方法，所以您最终会得到大量难以筛选的日志数据。

随着微服务数量的增长，日志变得越来越难以管理，存储成本也越来越高。如果您没有正确地组织和聚合来自每个服务实例的日志条目，您可能无法确定应用程序中发生了什么错误或为什么会发生错误。例如，您可以在日志中发现一个严重的事件，但是您如何知道日志是从哪里产生的以及哪个服务产生了该事件呢？如果没有适当的上下文，跟踪日志文件没有什么价值。

在微服务架构中，很多事情都可能出错。有这么多组件一起工作，重现一个 bug 并追踪其根本原因变得更加困难和不切实际——特别是当您需要跨多个日志或相互通信的系统跟踪一个操作时。总之，筛选日志不足以查明生产系统中的一些问题，因为它们可能缺少显示错误根本原因的相关上下文数据。

## 在云环境中调试应用程序的更好方法

虽然没有完美的工具可以神奇地指出代码中的错误，但是应用程序开发已经发展了。在 EKS、EC2、Fargate 或云中的其他地方，有一种更好的方法来调试 Lambda 函数或远程运行的代码。

远程调试是调试运行在本地环境之外的应用程序**。**这通常是通过使用支持远程调试的调试器(IDE 或编程语言)将远程应用连接到您的本地环境来完成的。

远程调试技术允许您直接检查在不同的服务器环境或远程机器上运行的应用程序的源代码，从而帮助您节省金钱和时间。它允许您有效地调试应用程序，尤其是在无法进行常规调试的情况下。远程调试还使您能够调试应用程序，而无需挖掘巨大的日志文件或在本地复制云环境。

使用远程调试，您不需要安装昂贵的硬件或飞到您的服务器位置来调试应用程序。你可以远程做任何事情，没有不必要的麻烦。

通过允许您在云上的应用程序中设置不间断断点，远程调试提供了日志记录的所有好处，同时消除了与日志记录方法相关的缺点。远程调试使您能够:

*   访问应用程序状态，包括完整的堆栈跟踪，以及需要调试的全局和局部变量。
*   远程快速修复云应用中的错误，无需重启或重新部署应用。
*   与团队成员实时协作，更快地解决问题。
*   从代码中获取数据并调试问题，而无需记录大量会降低或影响应用性能的数据。

如果您是开发人员、站点可靠性工程师或工程经理，您知道调试是必不可少的。更重要的是，您知道虽然本地调试是有用的，但是远程调试——如果操作正确——将会节省您的时间、金钱和麻烦。由于在本地开发环境中筛选许多日志的困难和调试生产缺陷的低效，没有比现在更好的时机来采用远程调试了。

桑德拉将很快通过不间断跟踪点支持调试生产应用程序。我们的方法将把远程调试与我们的强项分布式跟踪结合起来。今天就申请提前使用。

亚马逊网络服务是新堆栈的赞助商。

通过 Pixabay 的特征图像。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>