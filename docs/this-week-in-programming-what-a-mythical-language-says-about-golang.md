# 本周编程:关于 Golang，一种神秘的语言是怎么说的

> 原文：<https://thenewstack.io/this-week-in-programming-what-a-mythical-language-says-about-golang/>

如果你关注了上周的专栏[，你可能会注意到一个明显的错误:Go++不是真正的编程语言。](https://thenewstack.io/this-week-in-programming-do-or-not-do-there-is-no-try/)

你看，当我忙着在 Twitter 和其他地方收集关于正在进行的 Go 编程语言开发的最新进展的意见时，我无意中走进了一堆由[特使代理创建者 Matt Klein](https://twitter.com/mattklein123) 进行的骚扰，他在他的 Twitter 简历上列出了“与 [@davecheney](https://twitter.com/davecheney?lang=en) 一起担任 Go++指导委员会联合主席”，以及他的其他实际资格，所以我们在帖子中提到了这个资格。好吧，本周我来找你，因为我对细节的疏忽而面红耳赤，但尽管如此，我还是想分享 Go++的奇迹，这种虚构的语言最常被用来模仿 Klein 可能认为是不断发展的 Go 语言的错误。

虽然 Go++可能并不存在，但它反映了克莱恩的一些真实想法，他曾将 Go 称为“一个巨大的信号”

或者，这只是一个诱饵，但即使是诱饵也能提供一些见解。在这一点上我们应该提到，Klein 用 C++编写了 Envoy

也许克莱因的钓鱼努力中最有趣的部分，超出了我自己的轻信，是克莱因过分的模仿如此接近地反映了其他人所支持的观点…但这难道不是最终有效的钓鱼吗？

因此，Go++确实飞速发展。现在，让我们来看看编程语言等领域的最新消息。

## 本周的节目中

*   **AWS 将 TypeScript 和 Python 引入基础设施即代码:**你以前听说过基础设施即代码的概念，对吗？这是你，开发人员，成为一个 DevOps 的人，并开始处理这项工作。嗯，亚马逊正试图让这项任务变得更容易一些，通过[AWS 云开发工具包(CDK)](https://aws.amazon.com/blogs/aws/aws-cloud-development-kit-cdk-typescript-and-python-are-now-generally-available/) 的全面上市，它现在支持 Python 和 TypeScript。 [AWS CDK](https://aws.amazon.com/cdk/) 是“一个可扩展的开源软件开发框架，使用熟悉的编程语言来建模和供应你的云基础设施”，并于本周在[亚马逊 AWS 峰会](https://aws.amazon.com/events/summits/new-york/)上发布。AWS CKD 使您能够在相同的 IDE 和相同的语言中构建您的应用程序和基础结构，并且可以免费使用。要开始，请查看[分步在线教程](https://cdkworkshop.com/)和 [CDK 示例项目库](https://github.com/aws-samples/aws-cdk-examples)。
*   **AWS Toolkit for Visual Studio Code:**同样在本周的 AWS 峰会上，亚马逊[也发布了](https://aws.amazon.com/blogs/developer/announcing-aws-toolkit-for-visual-studio-code)AWS Toolkit for Visual Studio Code[AWS Toolkit for Visual Studio Code](https://aws.amazon.com/visualstudiocode/)，这是一个流行的 IDE 的扩展，现在已经普遍可用，并使“开发社区使用该编辑器更容易构建无服务器项目”该扩展从去年 11 月开始出现，在 Apache 2.0 许可下可在 GitHub 上开源获得，并使开发人员能够“轻松开发无服务器应用程序，包括创建新项目、本地调试和部署您的项目——所有这些都可以在编辑器中方便地完成”，支持 Node.js、Python 和. NET。具体来说，该工具包使开发人员能够在类似 Lambda 的环境中通过分步调试在本地测试代码，部署到选择的 AWS 区域，在本地和远程调用 Lambda 函数，以及指定函数配置查看[博客文章](https://aws.amazon.com/blogs/developer/announcing-aws-toolkit-for-visual-studio-code)的完整演练。

https://twitter.com/parrudanet/status/1148247278802624513

*   **麻省理工学院为机器学习引入新的 PPL:**对于那些进入机器学习领域的人来说，有一个新的孩子即将到来——麻省理工学院为[引入了一种新的概率编程语言(PPL ),命名为 Gen](https://dl.acm.org/citation.cfm?id=3314221.3314642) ，这是[进入 block 首席技术官 Jesus Rodriguez](https://www.linkedin.com/in/jesusmrv) 在[博客文章](https://www.linkedin.com/pulse/introducing-gen-mits-new-language-wants-tensorflow-jesus-rodriguez/)中描述的。Rodriguez 表示，“新语言允许研究人员编写应用人工智能技术的多个领域的模型和算法，如计算机视觉、机器人和统计，而不必处理方程或手动编写高性能代码。”Gen“通过利用一种改进了一些传统 PPL 技术的新型架构”解决了这一领域的一些常见挑战，它基于 [Julia](https://julialang.org/) 。这种新颖的体系结构“不是以图灵完全建模语言中的程序代码来表示模型，而是以黑盒的形式来表示模型，这些黑盒通过一个公共接口来展示对推理有用的功能。”虽然 Gen 肯定不是镇上唯一的游戏，但 Rodriguez 写道，“像 Gen 这样的努力正试图以 TensorFlow 为深度学习所做的相同方式来民主化 ppl。”
*   **用 Docsy 做文档:**可能是我是作者，但我发现谷歌最近为开源软件做文档的努力值得称赞，现在该公司已经[发布了 Docsy](http://opensource.googleblog.com/2019/07/announcing-docsy-website-theme-for.html) ，这是一个技术文档的网站主题，已经被 [Kubeflow](https://www.kubeflow.org/) 、 [Knative](https://knative.dev/) 和 [Agones](https://agones.dev/) 使用。本质上， [Docsy](https://github.com/google/docsy) 提供了“一个带有文档模板和指南的文档网站，我们将它开源给公众使用并帮助改进工具”，因为，见鬼，你的专长是构建软件，而不是创建和组织可公开访问的文档，对吗？

*   Erlang 的十年:当我们都在忙于研究最新的语言时，有一些像 Erlang 这样的语言已经存在了 33 年，据 Erlang 的开发者 [Fred Hebert](https://twitter.com/mononcqc/) 说，它们“仍然深深地嵌在许多公司的基础设施中”。赫伯特本周在[的博客上发表了一篇关于他使用 Erlang 十年的长文](https://ferd.ca/ten-years-of-erlang.html)，其中他讨论了“宣传阶段以及这与 Erlang 的关系，语言中的思想阶梯以及这如何影响采用，我在这里的十年中发生了什么变化，以及[……]我认为 Erlang 仍然需要为整个编程社区带来什么。”
*   独角兽的语言:当然，独角兽指的是那些价值数十亿美元的公司。Coding Dojo [做了一个小调查](https://www.codingdojo.com/blog/unicorn-languages-report)，并提供了一些关于谁在使用什么的见解。如果你对编程语言排名的赛马感兴趣，看看结果吧。不出所料，Python、Java 和 Javascript 位列前三，剩下的是你能想到的其他熟悉语言的组合。然而，他们确实注意到“Kotlin 出奇的受欢迎，25 只独角兽中有 8 只使用了它”，这在该公司的分析中还是第一次。当我们在这里谈论语言赛马的时候，TIOBE 指数也出来了，指出 [Perl 达到了有史以来的最低受欢迎程度](https://jaxenter.com/perl-tiobe-july2019-159930.html)。尽管如此，New Stack 的 Dave Cassel 刚刚开始撰写一个关于[开始学习 Perl 6](/getting-started-at-long-last-on-perl-6/) 的新系列文章，所以如果 Perl 6 在你的学习清单上，请继续关注。

来自 Pixabay 的 Alexas_Fotos 的特写图片。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>