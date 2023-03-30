# 本周编程:牧场主的 Docker 桌面替换

> 原文：<https://thenewstack.io/this-week-in-programming-ranchers-docker-desktop-replacement/>

又是一周的周末，我们再次讨论替换 Docker 桌面的想法，在 [SUSE 本周宣布了](https://finance.yahoo.com/news/suse-accelerates-pace-cloud-native-140000078.html) [Rancher Desktop](https://rancherdesktop.io/) 的最新版本之后，这个消息成为了[黑客新闻](https://news.ycombinator.com/item?id=28835690)的头条，标题为“Rancher Desktop，Docker 桌面的替代品”

如果你没有关注整个磨难，你可能会有至少一个黑客新闻评论者的相同反应，他[问](https://news.ycombinator.com/item?id=28836394)“Docker 的创始人踢了一群小狗还是什么？我是否忽略了一些原因，为什么我们应该对被要求为每个人都使用的东西付费感到愤怒，并从中获得很多价值？”

现在，我自己的观点是，如今我们都生活在一个互联网权利的世界里，我们期望所有的软件都是免费的——我并不声称可以免除这一点——即使 Docker [做出了改变](https://www.docker.com/blog/updating-product-subscriptions/),明确针对拥有 250 多名员工或年收入超过 1000 万美元的公司，我们仍然在寻找救生艇。顺便说一句，这也不是第一个救生船，因为在 Docker Desktop 新定价的消息传出后不久，我们就已经[考察了 Podman](https://thenewstack.io/this-week-in-programming-the-docker-dogpile-continues/) 的潜力。

所以，问题依然存在:Rancher 桌面能取代 Docker 桌面吗？

根据 SUSE 工程和创新总裁 [Sheng Liang](https://www.linkedin.com/in/shengliang) 的说法，Rancher Desktop 主要是作为 Kubernetes 的桌面开发环境而设计的，并以 Kubernetes 为中心。因此，首先，(正如黑客新闻评论中指出的)它不是 Docker 桌面的替代产品，因为它不支持 Docker Swarm。对于 Kubernetes 开发人员和“一些容器开发人员”，梁在一封电子邮件中写道，“使用 Rancher Desktop 作为 Docker Desktop 的替代品是可能的。”

“牧场主桌面和码头桌面的最初重点是不同的，”连写道。“为 Kubernetes 开发人员提供桌面应用程序导致 Rancher Desktop 与 Docker Desktop 的功能高度重叠。”

梁继续解释说，Kubernetes 开发人员使用 Rancher Desktop 的目标是“提供一个本地基础堆栈，他们可以在其中构建和运行他们的容器，并在 Kubernetes 中运行他们的应用程序”，并且“Rancher Desktop 允许开发人员选择他们想要使用的 Kubernetes 版本，并轻松地将环境恢复到默认设置。那些只对容器开发感兴趣的人或许也可以使用 Rancher Desktop。”

当然，所有这些都没有提到 Rancher Desktop 仍然只是 v0.5，还有许多发展要做，尽管梁说它有望在 2022 年全面上市，“几个主要功能将在 GA 之前推出。”

现在，如果你想对两者进行全面的比较，并判断 Rancher Desktop 是否真的可以作为 Docker Desktop 的替代品，当然不要依赖这些一般性的思考，而是看看 Upbound.io 开发人员 Viktor Farcic 的视频，他直接比较了这两种产品，并得出了明确的结论。

[https://www.youtube.com/embed/bYVfCp9dRTE?feature=oembed](https://www.youtube.com/embed/bYVfCp9dRTE?feature=oembed)

视频

## 本周的节目中

*   一个加速 Python 的提议:本周首先，Infoworld 报道了 [Python 可能会失去它的全局解释器锁(GIL)但是如果脸书开发者](https://www.infoworld.com/article/3637073/python-stands-to-lose-its-gil-and-gain-a-lot-of-speed.html#tk.rss_applicationdevelopment) [Sam Gross](https://mail.python.org/archives/list/python-dev@python.org/thread/ABR2L6BENNA6UPSPKV474HCS4LWT26GY/) 的[提议](https://mail.python.org/archives/list/python-dev@python.org/thread/ABR2L6BENNA6UPSPKV474HCS4LWT26GY/)被接受的话，速度会提高很多。提议的更改将涉及“对 CPython 的更改，以允许它在没有全局解释器锁的情况下运行”，这是 CPython 的核心组件，并将解决 Python 无法在多线程环境中伸缩的问题。根据 Infoworld 的说法，“多年来，人们已经做出了很多努力来消除它，但代价是损害单线程的性能——换句话说，就是让绝大多数现有的 Python 应用程序变得更慢。”与此同时，格罗斯写道，“概念验证是为了证明移除 GIL 是可行且值得的。”根据 Gross 的[设计概述](https://docs.google.com/document/d/18CXhDb1ygxg-YXNBJNzfzZsDFosB5e6BfnXLlejd9l0/edit)，该提案还旨在推销“权衡是可管理的，消除 GIL 的努力是值得的”这一理念，他通过提供基准来表明这种方法不会大大降低性能。

*   **Visual Studio 获得发布日期:**对于 Visual Studio 用户来说，本周有几个更新需要跟上。首先，虽然预览还没有完全完成(见下文)，但看起来 Visual Studio 2022 的正式发布指日可待，发布日期定在 11 月 8 日。事实上，随着发布日期的到来，Visual Studio 2022 也有一个[发布候选(RC)](https://aka.ms/vs2022release) 出来，旁边还有[预览 5](https://aka.ms/vs2022preview) ，它主要增加了 Xcode 支持并修复了一些 bug。Visual Studio 2022 将于 11 月 8 日上午 8 点 30 分[太平洋时间](https://www.timeanddate.com/worldclock/converter.html?iso=20211108T163000&p1=234&p2=179&p3=136&p4=166&p5=33&p6=240&p7=248)参加[虚拟发布活动，由 Scott Hanselman 做主题演讲，并将包括演讲嘉宾、与 Visual Studio 团队交流的能力以及“独家数字赠品”。](https://aka.ms/vs2022launch)
*   继上个月的[Visual Studio 2022 for Mac Preview 1](https://devblogs.microsoft.com/visualstudio/visual-studio-2022-for-mac-preview-1-is-now-available/)之后，**Visual Studio 2022 for Mac Preview 2**:除了前面提到的 [Preview 5](https://aka.ms/vs2022preview) ，本周还将发布[Visual Studio 2022 for Mac Preview 2](https://devblogs.microsoft.com/visualstudio/visual-studio-2022-for-mac-preview-2-is-now-available/)。预览版 2 主要介绍对新[的支持。NET 6 候选版本 2 (RC2)](https://devblogs.microsoft.com/dotnet/announcing-net-6-release-candidate-2/) 在基于英特尔的 MAC 电脑上发布，也于本周首次亮相。与所有其他预览版一样，这可以与 Visual Studio 2019 并行安装，Visual Studio 团队正在寻找[建议](https://aka.ms/vsmac-suggestion)和[问题报告](https://docs.microsoft.com/visualstudio/mac/report-a-problem)。要用。NET 6 RC2，你需要手动[安装它](https://dotnet.microsoft.com/download/dotnet/6.0)，但是要注意运行。目前不支持 M1 (ARM64)处理器架构上的 Visual Studio for Mac 中的. NET 6 RC2。请留意那件事。Visual Studio for Mac Preview 2 也继续了迁移到完全原生的 macOS UI 的工作，同时还添加了一些错误修复，详见[发行说明](https://docs.microsoft.com/en-us/visualstudio/releases/2022/mac-release-notes-preview)。
*   **Visual Studio 获得 VS 代码主题，扩展课程:**在 Visual Studio 的世界中，微软正在提供一个由九个视频组成的[新视频系列](https://www.youtube.com/watch?v=aMsyHiso4Vs&list=PLReL099Y5nRdz9jvxuy_LgHFKowkx8tS4&index=1)来帮助开发人员[学习编写 Visual Studio 扩展](https://devblogs.microsoft.com/visualstudio/learn-to-write-visual-studio-extensions/)，它从让你使用正确的工具和环境开始，然后带你一路构建扩展。除此之外，Visual Studio 2022 用户可以通过新发布的[主题转换器工具](https://aka.ms/themeconverter)将 Visual Studio 代码(VS 代码)主题[带到 Visual Studio 2022](https://devblogs.microsoft.com/visualstudio/vs-code-themes-in-vs/) 中，该工具可以将颜色令牌从 VS 代码主题转换并应用到 Visual Studio 中。团队已经[分享了使用这个工具](https://aka.ms/vsthemes)创建的新社区主题的集合，现在终端用户可以自己做了。他们指出，“转换后的主题在 C#和 C++ repos 中看起来最好”，并且与 Visual Studio 2022 Preview 3 及更高版本最兼容。

*   **GitLab 的 Kubernetes 操作员到来:**虽然 [GitLab](https://about.gitlab.com/?utm_content=inline-mention) 在[上市](https://www.bloomberg.com/news/articles/2021-10-14/gitlab-jumps-22-in-u-s-initial-public-offering?srnd=deals)的消息可能会占据所有的头条，但我们更感兴趣的是 [GitLab 的支持](https://about.gitlab.com/blog/2021/10/12/open-shift-ga/) [Red Hat](https://www.openshift.com/try?utm_content=inline-mention) OpenShift 的 Kubernetes 操作员现已全面上市的消息。GitLab 支持的 [GitLab Operator](https://docs.gitlab.com/charts/installation/operator.html) 提供了在 Kubernetes 平台上运行 GitLab 生产实例的能力，包括 Red Hat OpenShift，遵循[今年早些时候 GitLab Operator](https://cloud.redhat.com/blog/test-the-new-gitlab-operator-for-openshift) 的测试版。GitLab 表示，在过去的 6 个月里，它“与 Red Hat 密切合作，讨论技术细节并优化兼容性”，现在该运营商将帮助自动执行安装、配置和升级等任务。虽然 GitLab 运营商与[掌舵图](https://docs.gitlab.com/charts/)一起“串联”提供，但 GitLab 指出，该运营商“提供了超越云原生掌舵图的扩展功能”，不仅部署 GitLab，还保护部署免受不必要的更改，并随着组件版本更新保持最新。对于那些使用 Red Hat OpenShift 的人来说，认证“即将到来”。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>