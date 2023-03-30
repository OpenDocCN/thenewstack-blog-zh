# 本周的编程:AWS re:Invent for Developers

> 原文：<https://thenewstack.io/this-week-in-programming-aws-reinvent-for-developers/>

2019-12-07 06:00:34

本周的编程:AWS re:Invent for Developers

本周节目中，

# 本周的编程:AWS re:Invent for Developers

《本周编程》让我们来看看本周来自亚马逊网络服务年度用户大会的新闻。

Dec 7th, 2019 6:00am by [Mike Melanson](https://thenewstack.io/author/mike-melanson/ "Posts by Mike Melanson")![Featued image for: This Week in Programming: AWS re:Invent for Developers](img/07b469780d91f0a3ea312c4e43b6c49f.png)

又是一周，又是一场大型会议，几十个公告一个接一个地堆积在一起。本周，亚马逊接管了拉斯维加斯，举办了 AWS re:Invent 大会，新闻层出不穷。当然，并不是所有的都适用于你，开发者，所以我们认为我们应该尝试，至少，收集一些你可能想看的新闻。所以，这就是我们本周要开始的地方，在我们看一看编程世界中的其他一些新闻之前，有几篇文章就写在这个新的堆栈中。

## 本周 AWS 关于:发明

*   **量子计算即服务:** AWS 加入微软，提供完全管理的[量子计算即服务](/amazon-web-services-launches-quantum-computing-as-a-service/)，它的名字是 [Braket](https://aws.amazon.com/braket/) ，将作为三个不同的量子计算硬件供应商的市场。每个硬件提供商提供不同的架构，所有三个都在一个开发环境中得到支持，该环境使用 Jupyter 笔记本电脑并输出到亚马逊 S3。
*   **机器学习来到代码审查:**我以前说过，现在我再说一遍——如果你想看到代码做有趣的事情，就去找那些试图让自己的生活变得更简单的开发人员。亚马逊的新 [CodeGuru](https://aws.amazon.com/codeguru/) 机器学习服务可能就是这样，它提供自动化代码审查和应用程序性能建议，我们[写道](/amazon-web-services-codeguru-will-point-out-whats-wrong-with-your-code/)“它是首批基于 ML 的代码审查和分析工具之一。”该工具源于亚马逊自己的内部代码审查流程，并从 GitHub 上的 10，000 多个开源项目中获取数据，使其能够“查明资源泄漏、原子性违规、潜在的并发竞争情况、未统计的输入、浪费的 CPU 周期以及难以查明的线程安全类等问题。”

*   **专门用于机器学习的 IDE:**亚马逊跟进了其两年前在[发布的](https://thenewstack.io/amazon-sagemaker-automates-artificial-intelligence-development-pipeline/) [Sagemaker 平台](https://aws.amazon.com/sagemaker/)，推出了 [Sagemaker Studio](https://aws.amazon.com/blogs/aws/amazon-sagemaker-studio-the-first-fully-integrated-development-environment-for-machine-learning/) ，这是一个 [IDE，用于管理我们编写的整个机器学习生命周期](/amazon-web-services-launches-an-ide-to-manage-the-full-machine-learning-lifecycle/)“包括许多附加功能，包括调试、监控甚至自动创建 ML 模型。”Sagemaker Studio 提供了“单一窗口”体验，开发人员可以在其中构建、培训、调整和部署他们的 ML 模型。AWS 不仅仅是推出了一个 IDE，还发布了几个工具，包括 [SageMaker 实验](https://aws.amazon.com/blogs/aws/amazon-sagemaker-experiments-organize-track-and-compare-your-machine-learning-trainings/)、 [SageMaker 处理](https://aws.amazon.com/blogs/aws/amazon-sagemaker-processing-fully-managed-data-processing-and-model-evaluation/)、一个新的[调试器](https://aws.amazon.com/blogs/aws/amazon-sagemaker-debugger-debug-your-machine-learning-models/)、 [SageMaker 模型监视器](https://aws.amazon.com/blogs/aws/amazon-sagemaker-model-monitor-fully-managed-automatic-monitoring-for-your-machine-learning-models/)和 [SageMaker 自动驾驶仪](https://aws.amazon.com/blogs/aws/amazon-sagemaker-autopilot-fully-managed-automatic-machine-learning/)——所以请确保查看我们所有 ML-good 细节的完整故事。
*   **Java 的深度学习:**当我们谈论学习时，AWS 还[推出了](https://towardsdatascience.com/introducing-deep-java-library-djl-9de98de8c6ca)一个开源库，使用高级 API 开发、训练和运行 Java 的深度学习模型，称为[深度 Java 库(DJL)](https://djl.ai/) 。他们写道，DJL“将简化你训练和运行预测的方式”，他们提供了“如何在几分钟内用预训练的深度学习模型运行预测”的演练至于他们为什么要做 DJL，他们说 Python 资源匮乏，Java 资源匮乏……因此有了 DJL。

https://twitter.com/spimescape/status/1201630250104426497

*   **音乐创作的机器学习:**继之前的 ML 学习工具之后，如 [AWS DeepLens](https://aws.amazon.com/deeplens/) 和 [AWS DeepRacer](https://aws.amazon.com/deepracer/) ，这一次亚马逊[发布了 AWS DeepComposer](https://aws.amazon.com/blogs/aws/aws-deepcomposer-compose-music-with-generative-machine-learning-models/) ，它让你可以用生成式机器学习模型创作音乐。 [AWS DeepComposer](https://aws.amazon.com/deepcomposer/) 是“一个 32 键、2 个八度音阶的键盘，专为开发人员设计，可以使用预训练的模型或你自己的模型来接触生成式人工智能，”他们说这是“世界上第一个支持机器学习的音乐键盘。”
*   **Java 和。AWS CDK 中的. NET 支持:**亚马逊的 [AWS 云开发套件](https://aws.amazon.com/cdk/) (CDK) [现在提供对 Java 和. NET 的支持](https://aws.amazon.com/blogs/aws/aws-cloud-development-kit-cdk-java-and-net-are-now-generally-available/)，之前 [AWS CDK](https://aws.amazon.com/cdk/) 支持 [TypeScript 和 Python](https://aws.amazon.com/blogs/aws/aws-cloud-development-kit-cdk-typescript-and-python-are-now-generally-available/) 通过 [AWS CloudFormation](https://aws.amazon.com/cloudformation/) 对你的云应用资源进行建模和供应。
*   **面向移动开发人员的 AWS 框架:**最后，亚马逊推出了 [Amplify iOS](https://aws-amplify.github.io/docs/ios/start) 和 [Amplify Android](https://aws-amplify.github.io/docs/android/start) ，这两个开源库可以帮助开发人员“构建可扩展和安全的移动应用程序”，并“轻松地为您的移动和网络应用程序添加分析、AI/ML、API (GraphQL 和 REST)、数据存储和存储功能。”

## 本周的节目中

*   两种 Rust IDE 支持的故事:在支持 Rust 方面，IDE 目前有两种选择——Rust 语言服务器(RLS)和 Rust 分析器。虽然他们主要在性能上有所不同，但 Rust IDE 团队认为他们各自为政的开发有点令人遗憾，[写道](https://blog.rust-lang.org/inside-rust/2019/12/04/ide-future.html)“我们希望改变这种情况，并找出如何统一这些努力。”在分析目前的状况时，他们说 rust-analyzer 提供了更好的性能和“更丰富的功能集”,而 RLS 提供了“精确度”。当然, [Inside Rust 博客文章](https://blog.rust-lang.org/inside-rust/2019/12/04/ide-future.html)更深入一点，但长话短说，他们提出“有可能在不加倍工程努力的情况下集成这两种方法”以及“如果这种方法有效，我们将考虑冻结 RLS 并完全专注于 rust-analyzer。”
*   **倾听铁锈:**如果你对这种香肠制作感兴趣，或者即使不感兴趣，但你对铁锈的未来有看法，那么就去参加 [2019 年铁锈调查](https://docs.google.com/forms/d/1iGnf8Mmf4JRggOJ3E7iZlBLsgeLxIYzaI1caiFHQ6OQ/)，让他们知道你的想法。Rust 团队希望“了解其优势和劣势，并为未来建立开发优先级”，这是您参与的机会。该调查将持续大约 10-15 分钟，可以选择匿名，并开放到 12 月 16 日。密切关注一个月后的结果。

*   微软“类似 Rust”的编程语言:当我们谈到 Rust 这个话题时，你听说过微软的新语言吗，它目前被命名为“Project Verona”？根据 ZDNet 上的一篇文章，Project Verona 是[一种新的基于 Rust 的安全编码编程语言](https://www.zdnet.com/article/microsoft-were-creating-a-new-rust-based-programming-language-for-secure-coding/)，它来自于该公司的愿望，即“通过集成 Mozilla 开发的 Rust，使 Windows 10 中旧的低级组件更加安全”不久前，一名微软员工[制造了一些新闻](https://thenewstack.io/this-week-in-programming-blame-the-language-or-the-programmer/)，他透露“最近发现的绝大多数[错误都是内存安全缺陷](https://www.zdnet.com/article/microsoft-70-percent-of-all-security-bugs-are-memory-safety-issues/)”现在，该公司正在寻求用 Rust 解决这个问题，Rust 采用了“内存安全”技术，微软研究员 Matthew Parkinson 就该公司最近的方法做了一次演讲。“维罗纳计划”是微软试图重写一些特定的 Rust 组件，以更好地处理这些内存安全问题，同时保持性能，帕金森表示，它将“很快”开源，请密切关注。
*   **JetBrains 向太空发射:**当 AWS re:Invent 在拉斯维加斯举行的时候，Kotlin 也在举行自己的会议，会上 [JetBrains 推出了名为](https://blog.jetbrains.com/blog/2019/12/05/welcome-to-space/) [Space](https://jetbrains.com/space) 的新开发人员协作工具，它提供了基于 git 的版本控制、代码审查、基于 Kotlin 脚本的自动化(CI/CD)、包存储库、规划工具、问题跟踪器等等。空间目前在[早期访问](https://www.jetbrains.com/space/?_ga=2.154117819.244252904.1575650336-56983907.1573757115#request-eap-invite)中可用，并将作为服务或自托管提供。

[https://www.youtube.com/embed/t1vMUV9jYRs?feature=oembed](https://www.youtube.com/embed/t1vMUV9jYRs?feature=oembed)

视频

专题图片:AWS 首席执行官安迪·贾西

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>

TNS 所有者 Insight Partners 是新堆栈的投资者。

新堆栈更新一份时事通讯摘要，对本周最重要的新闻进行分析&。

新的堆栈不会出售您的信息，也不会与无关的第三方共享。如果继续，您同意我们的

[Terms of Use](/terms-of-use/)

和

[Privacy Policy](/privacy-policy/)

.