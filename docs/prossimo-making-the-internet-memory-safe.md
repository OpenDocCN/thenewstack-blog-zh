# 普罗西莫:让互联网存储安全

> 原文：<https://thenewstack.io/prossimo-making-the-internet-memory-safe/>

互联网安全研究小组(ISRG) 以其[让我们加密](https://letsencrypt.org/)认证机构而闻名，但它也致力于修复内存问题。它通过谷歌赞助了一名 Linux 内核开发人员——so[Miguel oje da](https://ojeda.dev/)全职研究 Linux 中的 Rust，在很大程度上修复其内置的 C 内存问题。此外，它还有一个专门致力于内存安全编程的部门[prosimo](https://www.memorysafety.org/about/)。它的其他项目是用于 Apache web 服务器的内存安全 TLS 模块，内存安全 curl 数据传输实用程序和内存安全 Rustls，一个更安全的 OpenSSL 替代方案。让我们看看这些项目。

首先，ISRG 正在这样做，如果你做过很多互联网编程或网络管理工作，你就会知道，因为内存问题困扰着许多互联网的基础程序。这些安全漏洞通常源于 C 和 C++代码内存安全问题。因此，ISRG 想把这些程序转移到[内存安全的](https://www.memorysafety.org/docs/memory-safety/)代码中。

内存安全程序是用避免常见的[越界读写](https://cwe.mitre.org/data/definitions/125.html)和[释放后使用](https://cwe.mitre.org/data/definitions/416.html)问题的语言编写的。C、C++和汇编，尽管速度很快，却很容易犯这种错误。而 Rust、Go、C#等语言，则接近内存防错。

那么这个问题到底有多严重呢？[2019 年对零日](https://twitter.com/LazyFishBarrel/status/1129000965741404160)在野外被利用的分析发现，超过 80%被利用的漏洞是内存安全问题。微软估计，在过去十年中，他们产品中 70%的漏洞都是内存安全问题。而[谷歌估计](https://security.googleblog.com/2019/05/queue-hardening-enhancements.html)90%的安卓漏洞都是内存安全问题。所以，是的，很糟糕。

你可以用[模糊化](https://thenewstack.io/developers-are-buzzing-on-fuzzing/)和[静态分析](https://thenewstack.io/checking-linuxs-code-with-static-analysis-tools/)之类的技术来降低流行的不安全语言中的风险，但这需要大量的工作，而且他们并没有找到所有可能的内存漏洞。Prossimo 的答案是用内存安全语言编写的程序替换我们现有的网络程序，这将消除所有这类问题。

那可不容易。互联网上有很多 C 和 C++代码。但是，正如它指出的，“互联网将会存在很长一段时间。雄心勃勃的努力有回报的时候了。通过明智地进行初始投资，专注于最关键的组件，我们可以在 1-2 年内看到可观的回报。”

当然，在我们的有生之年，Linux 中数千万行 C 代码不会生锈。但是， [Linus Torvalds，Linux 的创造者，可以看到 Rust 在驱动程序](https://www.zdnet.com/article/linus-torvalds-on-where-rust-will-fit-into-linux/)和其他半独立的 Linux 程序中扮演着重要的角色。

短期内更可行的是其他 Prossimo 项目。

对于 curl，这个一直很受欢迎也很危险的数据传输程序，Prossimo 正在和 curl 的维护者 Daniel Stenberg 合作。计划是用内存安全的 HTTP 和 TLS 库构建 curl。对于 HTTP，那是 [Hyper](https://github.com/hyperium/hyper) 库；对于 TLS 来说，就是 [Rustls](https://github.com/ctz/rustls) 库。Stenberg 正在进行 Hyper library 的集成，而 ISRG 的工程师 Jacob Hoffman-Andrews 则负责 Rustls 的集成。

反过来，Rustls 也是无处不在的 OpenSSL 的替代者。如果你关注网络安全，你就会知道这些年来 OpenSSL 是多么容易出现安全问题。我只需要提一下 [Heartbleed](https://www.zdnet.com/article/heartbleed-serious-openssl-zero-day-vulnerability-revealed/) ，你就知道我们说的是大麻烦。

著名的 Rust 开发者 Dirkjan Ochtman 正在改进 Rustls 库的代码。一个针对 Rustls 的 C API 已经开发出来，所以你可以用 Rustls 替换 OpenSSL。

最后， [Greenbytes](https://greenbytes.is/) 的 [Stefan Eissing](https://eissing.org/) 正在为 [Apache web 服务器](https://httpd.apache.org/)编写 [mod_tls](https://github.com/abetterinternet/mod_tls) ，一个新的传输层安全(tls)模块。这个流行的 web 服务器也是用 c 写的，一旦完成，他们希望 mod_tls 能取代现有的 mod_ssl。正如您可能猜到的，它将使用最安全的内存 Rustls TLS 库，而不是 OpenSSL。

最终，ISRG 想要给[网络时间协议(NTP)](http://www.ntp.org/) 内存安全的待遇。然而，目前这个国家结核控制计划项目缺乏资金。想帮忙吗？一旦有了钱，他们就准备工作了。

除此之外，ISRG 希望从根本上改变互联网的工作方式和我们对内存安全的看法。正如他们所说，“今天，在网络边缘部署用非内存安全语言(如 C 和 C++)编写的软件被认为是完全正常和可以接受的，尽管有大量证据表明这是多么危险。我们的希望是，我们可以让人们充分认识到风险，并将内存安全视为对安全敏感角色的软件的一项要求。”

这是一个很难达到的目标，但他们确实有道理。我们现在一切都依赖互联网。我们让它越安全越好。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>