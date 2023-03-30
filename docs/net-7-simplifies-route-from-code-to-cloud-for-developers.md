# 。NET 7 简化了开发人员从代码到云的过程

> 原文：<https://thenewstack.io/net-7-simplifies-route-from-code-to-cloud-for-developers/>

微软发布了。NET 7，这是其流行的开发平台的最新版本，带来了许多新的特性和功能，包括[增强的性能](https://devblogs.microsoft.com/dotnet/performance_improvements_in_net_7/)和用于 [C# 11](https://devblogs.microsoft.com/dotnet/welcome-to-csharp-11) / [F# 7](https://devblogs.microsoft.com/dotnet/announcing-fsharp-7/) 、[的新特性。NET MAUI](https://devblogs.microsoft.com/dotnet/dotnet-maui-dotnet-7/) 、[ASP.NET Core/Blazor](https://devblogs.microsoft.com/dotnet/announcing-asp-net-core-in-dotnet-7)、Web APIs、 [WinForms](https://devblogs.microsoft.com/dotnet/winforms-enhancements-in-dotnet-7) 、 [WPF](https://devblogs.microsoft.com/dotnet/wpf-on-dotnet-7) ，以及对于云原生集，轻松容器化的能力。NET 应用程序。

简而言之。NET 7 对几乎所有类型的开发人员都有一些帮助。微软宣布。网 7 在其[。NET Conf 2022](https://www.dotnetconf.net/) 。

## 适用于各种应用的一个堆栈

“我们是唯一一个可以构建控制台、web、云、移动、桌面等等的堆栈，”微软 Azure 开发者体验产品副总裁 Scott Hunter 告诉新堆栈。“关于一件事。NET 的优势在于，大多数堆栈都非常擅长构建服务器应用程序或客户端应用程序，而我们可以构建每一种应用程序。”

而且，随着。微软已经消除了带来的摩擦。NET 支持无停靠站流程的云原生工作负载。

## 集装箱化

微软开发者平台和语言产品负责人 [Gaurav Seth](https://www.linkedin.com/in/gauravseth/) 告诉新堆栈:“容器正在成为云上部署的货币，我们通过. NET. 7 使你的应用部署到云中变得更加简单，不需要在你的机器上启用或安装 [Docker Desktop](https://thenewstack.io/docker-delivers-docker-extensions-docker-desktop-for-linux/) 。现在，只需一个简单的 CLI 命令，您就可以自定义容器、部署自定义容器等。，并且这种支持可以与任何容器运行时一起工作:Docker、 [Podman](https://podman.io/) 、 [Containerd](https://containerd.io/) 等。

这不仅可以从命令行界面(CLI)获得，而且微软已经为此目的在其 Visual Studio IDE 中引入了支持。

“Visual Studio 不仅可以无缝开发你的应用程序，还可以部署和提供各种 Azure PaaS 服务，如 [Azure 应用服务](https://thenewstack.io/azure-app-service-embraces-containers-now-runs-linux/)、[容器应用](https://thenewstack.io/microsoft-delivers-azure-container-apps-developer-cli/)等等，”Seth 说。

此外，随着。微软已经让开发者通过简单的右键点击 [GitHub Actions](https://thenewstack.io/simple-load-testing-with-github-actions/) 来设置 CI/CD 变得很容易。

“我最喜欢的功能[的。NET 7]是 Docker-less 或 Docker-Desktop-less 支持，主要是因为作为在 Azure 中构建容器服务的人，我们有一项工作，我们称之为“代码到云”,我们可以让开发人员编写或修改他们的一些代码以将其放到云中有多容易？任何时候我都可以去掉一层又一层，这让它变得更快，”亨特说。

对于构建客户端应用程序，开发人员通常喜欢有选择，他们选择正确的堆栈来构建客户端应用程序。归根结底，他们必须做出选择，这是在影响力和权力之间的选择。这是一个滑动比例。

“根据应用需求，您可以选择您所知道的正确组合，完全 web 化以实现最大范围，完全本机化以实现与操作系统、设备等的集成能力或深度。，”斯科特说。“如果有些人两者都需要，总会有混合客户端应用。现在。NET 支持这整个范围。”

关于可观察性特征。NET 7 与 Azure App Insights 集成，并支持 OpenTelemetry 框架。NET 7 云原生应用的可靠性和性能。

## Linux 支持

此外，。NET 7 是继微软宣布与 Canonical 合作之后的第一个重要版本。NET 7 可与[凿刻的 Ubuntu 容器](https://devblogs.microsoft.com/dotnet/dotnet-6-is-now-in-ubuntu-2204/)一起使用。

微软最近宣布。从 Ubuntu 22.04 LTS 发布版开始，现在可以在默认的软件包提要中使用. NET。公司一直在努力确保。NET 作为一个平台在 Linux 上运行良好。

“当我们在 2016 年开始这段旅程时，谁会想到红帽会来要求我们进入盒子？或者 Fedora 会希望我们在盒子里，”亨特说。“他们想要。NET 和 Java，Node，Python，Go 放在一起。我认为这与我们 2002 年封闭源码时代的. NET 相比是一个惊人的变化。”

## 其他功能

。NET 7 是与其他几个产品、库和平台一起发布的，包括[ASP.NET 核心 7](https://devblogs.microsoft.com/dotnet/announcing-asp-net-core-in-dotnet-7) 、[实体框架核心 7](https://devblogs.microsoft.com/dotnet/announcing-ef7) 。NET 毛伊岛，Windows 窗体，WPF 和[奥尔良 7](https://devblogs.microsoft.com/dotnet/whats-new-in-orleans-7/) 。还有。NET 7 自带对 ARM 64 的原生支持。

Orleans 是一个微软跨平台软件框架。NET 是为云编写分布式应用程序的关键平台。“我们正在让奥尔良成为。净家庭，”塞思说。“Orleans 使构建分布式应用程序变得更加容易。像 Halo、Mesh 和 Azure 这样的几个微软服务实际上已经在使用这项技术了。”

另外，“。NET 曾经是一种非常冗长的语言，如果你构建一个 API，你必须写很多代码，而我们一直在减少你必须写的代码量，”亨特说。“这是我们从 Node.js 和 Python 等工具中学到的东西，并将这些功能提供给我们的。净客户。”

## 群体意见

。NET 每月有超过 570 万的开发者在使用。它也继续成为开发人员最喜爱的框架之一——在 2019 年、2020 年和 2021 年的堆栈溢出调查中连续三年排名第一。

开源社区可以宣称对新版本中的几个增强负责。。Seth 说，NET 7 有来自 10，000 多个社区成员的超过 28，000 个贡献。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>