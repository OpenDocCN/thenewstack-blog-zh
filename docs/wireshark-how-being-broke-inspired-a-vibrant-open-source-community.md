# Wireshark:破产如何激发了一个充满活力的开源社区

> 原文：<https://thenewstack.io/wireshark-how-being-broke-inspired-a-vibrant-open-source-community/>

这是关于开放源码构建者系列的一部分。要获得本系列的其他文章列表，请查看

[the introductory post](https://thenewstack.io/open-source-builders-an-inside-look/)

.

[](https://www.linkedin.com/in/mjasay/)

 [马特阿萨伊

马特是 AWS 的一名负责人，一直参与开源及其支持的所有领域(云、机器学习、数据基础设施、移动等。)近二十年来，为各种开源公司工作，并定期为 InfoWorld 和 TechRepublic 撰写文章。你可以在推特上关注他(@mjasay)。](https://www.linkedin.com/in/mjasay/) [](https://www.linkedin.com/in/mjasay/)

杰拉尔德·库姆斯在 1997 年没有 8 万美元可花，这是件好事。当时，作为一名为 ISP 工作的研究生，库姆斯需要一个网络数据包分析器来跟踪公司网络上的问题。但是他和 ISP 都负担不起花费 80，000 美元购买像 Network General 的 Sniffer 这样的商业产品，开源替代产品也不能满足他的需求。所以他做了“有意义”的事情，创造了 Wireshark(当时叫 Ethereal)这个已经成为世界上最流行的网络协议分析器。

与大多数其他开源项目不同，Wireshark 立即吸引了外部的贡献。如今 Wireshark 有 600 多名贡献者，但早在 1997 年，Combs 只是想完成他的工作。在这个过程中，他可能创造了“完美的开源项目”，正如库姆斯的朋友和前同事洛里斯·德吉奥安尼所说。

我们来看看为什么。

## 开发商的，开发商的，开发商的

受低预算价格(免费)高质量软件承诺的诱惑，许多开源项目吸引了大量用户。然而，这些相同的项目通常很难找到愿意贡献代码的开发人员。Wireshark 有相反的问题。

正如库姆斯在最近的一次采访中所说，“早期，我们有足够数量的开发人员。”有多快？在软件发布的一两天内，开发人员开始为 Wireshark 做贡献，库姆斯说，从那以后，它一直是一个稳定的流。正如他所描述的那样，这种直接的兴趣源于 Wireshark 满足了一种基本需求，即查看计算机之间在说什么，而 Wireshark 恰好比早期的选项更好地满足了这种需求。

“我真的没有做任何有意识的营销或推广或任何事情，”库姆斯说。相反，开发者在 [Freshmeat](http://freshmeat.sourceforge.net/) 上发现了 Wireshark，在 Slashdot 或其他地方听说了它[，并蜂拥到这个项目中。那些](https://slashdot.org/story/06/06/09/1935202/rip-ethereal-long-live-wireshark)[的早期用户](https://www.wireshark.org/docs/wsug_html_chunked/ChIntroHistory.html)，比如 Gilbert Ramirez、Guy Harris 和 Richard Sharpe，开始贡献底层的[解析器](https://www.wireshark.org/docs/wsdg_html_chunked/ChDissectAdd.html)(协议解析器)和其他缺失的功能。当这个项目在 2000 年左右增加了对 Windows 的支持后，dam 很快被用户采用。

纵观全局，Wireshark 社区成功的关键之一是早期用户不仅可以轻松使用该软件，还可以对其进行改进。Degioanni 指出，Wireshark 特别适合社区成功，因为用户社区是由开发人员组成的。“如果你真的熟悉协议的来龙去脉，那可能是因为你是某种开发人员，”Degioanni 说。此外，这些开发人员可以并行处理他们的软件领域。

因此，Combs 说，用户/开发人员可以很容易地利用他们关于协议的知识，然后为 Wireshark 编写一个剖析器，这有助于 Wireshark 在分析不同协议方面的能力广度的增长。

“每一个新的剖析器都使 Wireshark 变得越来越有用，并使我们的社区增长了一点，这意味着对长期开发者来说更有用的反馈，”Combs 说。今天，这些贡献加起来有 250 万和 350 万行代码，这取决于你如何计算。

Wireshark 的社区成功还有另一个秘密，它与项目的名字有些不一致:善良。

## 你会遇到的最好的鲨鱼群

“我热爱我们的社区。库姆斯说:“这是一个非常有建设性的社区，人们喜欢互相帮助。”。“我很早就意识到语气很重要。无论你作为一个项目的领导者设定了什么样的基调，就社区的行为和运作而言，这都是非常重要的。”

Wireshark 以一种非正式的治理模式运行，对贡献的回报是“赞赏的”,而不是要求的。相反，社区[建议贡献以下列方式使贡献者受益](https://www.wireshark.org/docs/wsug_html_chunked/ChIntroMaintenance.html):

1.  其他发现您的贡献有用的人会感激他们，并且您会知道您以 Wireshark 开发人员帮助您的同样方式帮助了人们。
2.  Wireshark 的开发人员可以进一步改进您的更改或在您的代码上实现额外的功能，这也可能对您有益。
3.  Wireshark 的维护人员和开发人员将维护您的代码，在 API 发生变化或其他变化时修复它，并通常使它与 Wireshark 发生的事情保持一致。因此，当 Wireshark 更新时(这是经常发生的)，您可以从网站上获得新的 Wireshark 版本，并且您的更改已经包括在内，无需您做任何额外的工作。

这个社区的一个重要组成部分是 [Riverbed](https://www.riverbed.com/) ，这是一家帮助组织提高网络和应用程序性能的公司。虽然 Riverbed 并不控制这个社区，但自从 2010 年[收购了库姆斯的雇主](https://en.wikipedia.org/wiki/Wireshark#History)，CACE 之后，它就雇佣了库姆斯，并允许库姆斯投入大量时间来帮助指导这个项目。Riverbed 还帮助投资 Wireshark 构建软件的基础设施。该项目尚未在 GitHub 或 GitLab 上运行，但 Combs 和其他开发人员正在积极致力于此，以更新基础设施。

## 开源是有意义的

库姆斯从未打算制造世界上最流行的协议分析器。“当你创建一个开源项目并向全世界发布时，得到认可是好事，但我不知道会有多大，”库姆斯说。"最初我需要挠痒痒——我需要解决工作中的一个问题。"他说，他希望人们会发现 Wireshark 很有用，但他不知道它会成为他的工作——事实上，是他的全职工作——很长一段时间。

他也没有想到创建 Wireshark 会带来一个友好的、充满活力的社区。“和他们一起工作很开心，”他说。

这一切的核心是开源。这一点毋庸置疑。当我问库姆斯为什么不创建一个个人项目并关闭它时，他回答说，“我从使用开源软件中获得了如此多的好处，至少对我来说，我只想回报。这很有意义。”

Wireshark 是在 GNU 通用公共许可证版本 2 下发布的。访问 [Wireshark 网站](https://www.wireshark.org/develop.html)，了解如何参与其社区。

*如果你或你认识的人在不同的开源项目上需要帮助，请访问 [AWS 开源](https://aws.amazon.com/opensource)网站，了解开源项目如何[申请 AWS 推广积分](https://aws.amazon.com/blogs/opensource/aws-promotional-credits-open-source-projects/)。*

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>