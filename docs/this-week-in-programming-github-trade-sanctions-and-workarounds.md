# 本周节目:GitHub、贸易制裁和变通办法

> 原文：<https://thenewstack.io/this-week-in-programming-github-trade-sanctions-and-workarounds/>

当物理边界被强加在互联网上时，感觉是如此的…错误。对吗？

当然，这种现象[不是一个新现象](https://techcrunch.com/2018/12/22/slack-says-it-will-comply-with-sanctions/)，但本周出现了一个新实例，这一次是对开发者世界的限制，ZDNet 首先报道 [GitHub 已经开始阻止面临美国贸易制裁的国家的开发者](https://www.zdnet.com/article/github-starts-blocking-developers-in-countries-facing-us-trade-sanctions/)。新闻首先出现在居住在克里米亚的 21 岁俄罗斯公民 Anatoliy kashk in[报道](https://github.com/tkashkin/GameHub/issues/289)他无法创建新的私人资料库，并且他现有的私人资料库已被禁用。

克里米亚并不是这个名单上唯一的一个，GitHub 声明指出，目前对克里米亚、古巴、伊朗、朝鲜和叙利亚都有限制。[据 Techcrunch](https://techcrunch.com/2019/07/29/github-ban-sanctioned-countries/) 报道，GitHub 已经开始实施这些“新的限制，以防止受制裁国家的用户访问私人存储库和 GitHub Marketplace，以及维护私人付费组织账户”，尽管“GitHub 服务的选择，如访问公共存储库，仍将对所有人开放。”这些限制甚至适用于只是在这些国家旅行的人，尽管对一些人来说，困难更可怕一些。

一名伊朗 GitHub 用户创建了一个知识库，要求该公司不要禁止那里的用户，他写道:“GitHub 曾经是一个对所有人开放的免费平台，但它决定限制伊朗账户贡献和成为开源生态系统的一部分。虽然我们理解 GitHub 可能会在美国政府的压力下做出这一决定，但我们期待 GitHub 采取更加尊重的行动。”许多用户呼吁 GitHub 采取不同的行动，尽管该公司表示受到美国贸易法的束缚。类似地，许多人认为解决方案不是让 GitHub 改变路线，而是采用替代的、分散的 Git 解决方案( [git](https://git-scm.com/) 本身，毕竟，全球任何人都可以免费下载和使用)。

鉴于这一点，我们再次面临在互联网上强加物理边界的情况，有一些变通办法，一名伊朗开发者上个月在一篇关于[在伊朗做开发者是什么样的](https://shahinsorkh.ir/2019/07/20/how-is-it-like-to-be-a-dev-in-iran)的博客文章中预见到了这一点。选项范围很广，从虚拟专用网络(VPN)到代理，再到虚拟专用服务器(VPS)。作者写道，他们“已经配置了 [bind/named](https://bind9.net/) 来通过 [shecan](https://shecan.ir/) 和 [privoxy](https://privoxy.org/) 代理几个特定的域查询，通过 [FOD](https://github.com/freedomofdevelopers/fod) 到 FOD 隧道所有支持的域，通过 TOR 隧道其他的域。”

鉴于我们谈论的是对开发者的限制，当然会有很多解决方案。毕竟你就是干这个的，对吧？

## 本周的节目中

*   **GitHub 的 Slack 应用获得更新:**既然说到 GitHub，那就来说说 GitHub 吧。也就是说，GitHub 和 Slack 集成中有一些[新东西，比如增加了对创建部署、检查和拉取请求的支持。根据这篇博客文章，](https://github.blog/2019-07-29-whats-new-in-the-github-and-slack-integration/) [GitHub 和 Slack 应用程序](https://slack.github.com/)现在使用[部署 API](https://developer.github.com/v3/repos/deployments/) 从 Slack 通道列出和创建您的存储库中的部署，以及获取对拉请求的检查状态，并获得新的拉请求草案的通知。这些特性以简单的斜杠命令的形式出现，GitHub 组织所有者或存储库管理员必须通过接受更新的权限来允许这些特性。如果你没有，这里有 GitHub 和 Slack 应用程序。
*   **不使用 GitHub 的一个方法:**如果你正在寻找一个坏主意，看看韩国公司在 GitHub 上提供的[明星饮料宣传片就知道了，正如《The Register》的一篇报道中所述。韩国最大的无线通信公司 SK 电讯向任何愿意开始其梅塔特隆发现项目的人提供免费的星巴克饮料。至于为什么会发生这种情况，登记册总结了项目所有者所说的“一个开源项目很难在一个大公司内部生存，尽管有内部公司政治，实现高明星数将有助于证明其价值。”该帖子现在已经消失，取而代之的是一份道歉，该公司现在表示将重置知识库。](https://www.theregister.co.uk/2019/07/30/would_you_star_a_github_project_for_a_free_drink/)

*   根据 Go 首席工程师[伊恩·兰斯·泰勒](https://www.linkedin.com/in/ianlancetaylor/)题为[为什么是泛型？](https://blog.golang.org/why-generics)–具体来说，泰勒写道,“Go 于 2009 年 11 月 10 日发布。不到 24 小时后，我们看到了关于泛型的第一条评论。当然，如果你熟悉 Go，你会认识到这是一个已经激烈争论了很长时间的话题，现在随着该语言向 Go 2.0 的进军，它又回到了前沿。简而言之，“泛型编程支持以泛型形式表示函数和数据结构，而不考虑类型。”Taylor 举了一个反函数的例子，它在 Go 中需要两个不同的函数来处理字符串和整数，并指出“一些刚接触 Go 的人感到惊讶的是，没有办法编写一个简单的反函数来处理任何类型的切片。”虽然大多数其他静态类型语言提供了这种类型问题的泛型，但是 Go 没有，尽管接口类型提供了一种变通方法，Go 团队正在提出另一种方法，这在[一份为 Go 添加泛型的设计草案](https://github.com/golang/proposal/blob/master/design/go2draft-contracts.md)中有所阐述。关于这个话题的总结，请看泰勒的博客文章，这篇文章来自他上周在 GopherCon 的一次演讲。如果你有任何反馈，该团队表示他们当然期待听到，尽管“要明确的是，我们对语义的反馈比对语法的细节更感兴趣。”他写道，总体目标是“实现一种设计，使编写我今天讨论的通用代码成为可能，而不会使语言变得太复杂而无法使用，或者让人感觉不再像是 Go。”

*   **用 AWS Amplify Framework 添加一点 AI/ML:**亚马逊表示，它希望“将机器学习放在每个开发人员的手中”，它表示，随着最新的 [Amplify Framework 更新](https://aws.amazon.com/blogs/aws/amplify-framework-update-quickly-add-machine-learning-capabilities-to-your-web-and-mobile-apps/)，这变得更加容易，允许开发人员快速将机器学习功能添加到网络和移动应用程序中。此次最新更新为 [Amplify 框架](https://aws.amazon.com/amplify/framework/)添加了预测类别，使开发人员能够使用[亚马逊识别](https://aws.amazon.com/rekognition/)识别图像中的文本、实体和标签，使用[亚马逊翻译](https://aws.amazon.com/translate/)将文本转换为不同的语言，使用[亚马逊 Polly](https://aws.amazon.com/polly/) 将文本转换为语音，使用[亚马逊转录](https://aws.amazon.com/transcribe/)将语音转换为文本，并使用[亚马逊解释文本以找到主导语言、实体、关键短语、情感或非结构化文本的语法要开始，请查看](https://aws.amazon.com/comprehend/)[入门教程](https://aws-amplify.github.io/)。
*   由人工智能驱动的代码自动完成和简单的 Web 托管:让我们高兴地结束这个话题，为开发人员提供两个漂亮的工具。首先，The Verge 写了一个[人工智能支持的自动完成软件，它是“Gmail 的智能编码软件”](https://www.theverge.com/2019/7/24/20708542/coding-autocompleter-deep-tabnine-ai-deep-learning-smart-compose)。这款名为 Deep TabNine 的编码自动完成器“使用了一种名为 GPT-2 的深度学习文本生成算法，由研究实验室 OpenAI 设计，以提高其能力”，并且“正在对来自编码库 GitHub 的 200 万个文件进行训练。”与 Gmail 的智能撰写非常相似，Deep TabNine“在这些数据中找到模式，并使用它们来建议任何给定代码行中接下来可能出现的内容，无论是变量名还是函数”，目前支持 22 种语言。接下来，还有 [hostyoself](https://github.com/schollz/hostyoself) ，这让它变得超级简单，嗯，“从你的浏览器、你的手机、你的烤面包机上托管你自己”。“出于好奇，所有的代码都可以在[库](https://github.com/schollz/hostyoself)中找到，但是对于其他人来说，只要去[hostyoself.com](https://hostyoself.com/)，拖放你想要托管的内容，它就会为你提供一个 URL。只要浏览器选项卡处于打开状态，网站就会保持在线状态。

通过 Pixabay 的特征图像。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>