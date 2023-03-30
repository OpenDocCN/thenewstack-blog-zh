# Gorilla Toolkit 开源项目成为废弃软件

> 原文：<https://thenewstack.io/gorilla-toolkit-open-source-project-becomes-abandonware/>

嗯，真讨厌！

多年来， [Gorilla Web Toolkit](https://www.gorillatoolkit.org/) 一直是基于 Web 的应用程序的流行、开源 [Go](https://go.dev/) 工具包。它由一些包组成，这些包扩充了 Go 的基础库，增加了一些重要的特性，比如参数化路由和会话管理。特别是， [mux](https://github.com/gorilla/mux) ，它的 web 请求路由器，一直很受欢迎。有多受欢迎？Try mux 在超过 90，000 个存储库中使用[。它被召去执行一些顶级项目，如](https://github.com/gorilla/mux/network/dependents?dependent_type=REPOSITORY)[纤毛](https://github.com/cilium/cilium/blob/v1.12.4/go.mod#L48)、 [Istio](https://thenewstack.io/solo-io-istio-is-winning-the-service-mesh-war/) 和[开放政策代理](https://thenewstack.io/open-policy-agent-the-top-5-kubernetes-admission-control-policies/)。的确，Gorilla 的 WebSocket 库甚至用在了 [Kubernetes](https://thenewstack.io/primer-how-kubernetes-came-to-be-what-it-is-and-why-you-should-care/) 中。尽管如此，这个项目现在已经被放弃了。

如此重要的项目怎么会发生这种事？简单。项目维护人员呼唤新血，无人应答。

## 需要尸体

天哪，我们需要新的维护者。正如最后一个维护者 Matt Silverlock 所说，“[没有活跃的贡献者](https://github.com/gorilla)，甚至没有分类问题。对维护者的呼吁明确表示我们将帮助合并，并为任何想要开始贡献的人做最后的审查。取而代之的是，许多人举起了手(阅读:在帖子中评论),然后就再也看不到了。…我们似乎从来没有让任何人坚持下来。”

是的，他们不会随便带走任何人。“正如我们在最初的维护者呼吁中所说:‘没有维护者比敌对的维护者更好！’—仅仅是掌控一个每周有超过 1.3 万个独立克隆(mux)的软件包，我都不会感到舒服。这在其他项目中表现不佳。"

## 关于钱

像许多重要但不受重视的开源项目一样，Gorilla 是为了钱。什么都没有。这是一个充满激情的项目。西尔弗伯格补充道，“这并不是在挖苦那些确实想为自己的努力获得报酬的维护者，而是在提醒大家，并不是每个人都是为了钱而做事的。”此外，大猩猩从来没有任何现金。从来没有人试图将大猩猩货币化。

所以，在花了将近一年的时间试图找到一个能够负责任地接管图书馆的人之后。他们放弃了。

## 项目档案

剩下的支持者已经决定在 2022 年底将这个项目存档。这意味着[存储库进入“只读”模式。您仍然可以克隆它们，获得它们，并像往常一样用它们来构建项目。但是不会有未来的发展。哦，还有安全补丁？求你了。现实点吧。](https://docs.github.com/en/repositories/archiving-a-github-repository/archiving-repositories)

当然，您可以派生项目或它的库。所有的 Gorilla 库都获得了 MIT、BSD-3 和 Apache 2.0 许可。

但是，虽然分叉一个项目很容易，但是分叉一个项目并围绕它进行构建要困难得多。

正如软件供应链安全公司 [Chainguard](https://www.chainguard.dev/) 软件工程师[丹·卢林](https://www.linkedin.com/in/danluhring/)和[埃迪·赞斯基](https://www.linkedin.com/in/eddiezane/)所说，大猩猩的崩溃凸显了两个问题。首先是 Gorilla 无法找到值得信赖的维护人员。如果你让汤姆、迪克或哈利中的任何一个成为维护者，你可能会陷入像 Chrome 的“[伟大的吊杆”插件](https://www.darkreading.com/application-security/malicious-code-injected-via-google-chrome-extension-highlights-app-risks)那样的境地。在那里，这个合法的项目被卖给了一家利用该插件传播恶意软件的无良公司。没人想要那样的烂摊子。

另一个问题是，我们经常相信开源项目会神奇地不断改进和修复出现的安全漏洞。通常，他们会。但是没有保证，当然也没有魔法。

## 提供支持

为了保持开源软件正常工作，Chainguard 的工作人员说:“公司需要为他们的团队提供工作时间，以回报他们所依赖的项目。虽然这里没有提到钱的问题，但是我们应该在经济上支持和雇佣开源维护者。我们可以宣传他们所做的工作，我们可以强调开源维护者的工作让世界变得更加安全。”

确实如此。只有当社区中的每个人都在开发人员的时间和汗水方面给予真正的支持时，开源才能很好地工作。而且，钱也不伤人。

在这种特定情况下，Chainguard 建议您确定哪些项目依赖于 Gorilla Toolkit 库。当然，Gorilla 是经过战斗考验的，没有理由相信它会很快出问题。不过，最好不要长期依赖任何无人维护的软件。简直是自找麻烦。

你可能想考虑的另一个库是 [Gin](https://github.com/gin-gonic/gin) 。这是一个功能更全的 Go web 框架。

不幸的是，如果你需要 [gorilla/websocket](https://github.com/gorilla/websocket) 替换，你可能要找一阵子了。链甲还没找到。

嘿，如果 Gorilla 对你很重要，我有个想法:放弃代码。适当地照顾它，指派一两个程序员和一个维护人员给它，并意识到原始项目的命运，制定长期计划使项目在未来几年继续进行。

不过，我不认为这很容易。正如大猩猩团队发现的那样，人们常常会说正确的话，但不会做正确的事。成功的开源项目需要持续的努力来维护他们的代码。您可以无忧无虑地使用废弃软件代码的日子已经一去不复返了。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>