# Rustls 希望为 OpenSSL 提供一个内存安全的替代品

> 原文：<https://thenewstack.io/rustls-looks-to-provide-a-memory-safe-replacement-for-openssl/>

在谷歌的财政支持下，[互联网安全研究小组(ISRG)](https://www.abetterinternet.org/) 已经与 [Rustls](https://github.com/ctz/rustls) (发音为“russels”)传输层安全(tls)项目合作，[对开源项目实施了一系列的改变](https://www.abetterinternet.org/post/preparing-rustls-for-wider-adoption/)，希望提供 OpenSSL 的替代品，作为其内存安全计划的一部分。

与许多系统级应用程序一样，OpenSSL 主要是用 C 编写的，目前的一大问题是 C 和 C++等语言不是内存安全的，这可能导致安全漏洞。例如，2019 年，微软披露，其产品中近 70%的安全漏洞是由内存安全问题引起的。以 OpenSSL 为例，由于内存安全问题，出现了很多漏洞；Heartbleed bug 就是这样一个臭名昭著的漏洞。相比之下，Rustls 主要是用 Rust 编写的，这是一种内存安全的语言，ISRG 改进 Rustls 的努力旨在为该库的广泛采用做准备。

“新的是，我们现在有了一种语言，在我所谓的系统级别上给了我们一种内存安全的选择，”ISRG 执行董事乔希·奥斯解释说。“现在我们有机会看一看一些底层系统代码，然后想，‘好吧，我们可以做得更好。现在我们有了一个选择。内存安全的语言通常比 C 慢得多，所以过去如果你能用内存安全的语言写一些东西，你通常必须在安全性和性能之间做出选择。有了 Rust，我们就不必再做这样的权衡了。我们可以拥有安全和性能。"

Rust 最近成为一种流行的选择，因为它提供了一种内存安全的 C 语言替代品，这种语言发现自己被选择用于许多系统级重写。最近，谷歌宣布在安卓系统中采用 Rust，这种语言已经在 Linux 内核中使用，微软和 T4 也在探索用它来重写 Windows 的部分内容。在性能方面，具体来说，[最近比较 Rustls 和 OpenSSL](https://www.zdnet.com/article/a-rust-based-tls-library-outperformed-openssl-in-almost-every-category/) 的基准测试实际上发现，Rustls 比它的对手有更好的连接速度和更小的内存占用。

ISRG 的内存安全倡议旨在识别对互联网至关重要但用非内存安全语言编写的代码，然后将这些代码转换为内存安全语言，以消除所有类别的安全漏洞。Aas 解释说，Rust 是取代 C 的理想选择，不仅因为它的性能，还因为这种语言缺乏运行时，不像许多其他内存安全的语言，它允许你以增量方式重写用 C 编写的程序。Aas 说，不幸的是，OpenSSL 将无法被重写，因此他们正致力于准备 Rustls 来完全取代它。ISRG 已经在 Apache HTTP Server 和 Curl 中用 Rustls 取代了 OpenSSL，现在该组织正在努力推进这一运动。

Aas 说:“另一个大问题是 open SSL 使用的 API 非常复杂，所以使用 OpenSSL 的人往往会在他们的实现中出错，因为 OpenSSL API 非常混乱和复杂。”“Rustls 有一个更安全、更易于理解的 API，所以我们在这次转变中真正得到了两件事。我们将获得 Rustls 带来的内存安全性，以及更安全的 API。”

具体来说，ISRG 和谷歌正在与 Rustls 贡献者 [Dirkjan Ochtman](https://github.com/djc) 签约，对该项目进行几项改进，例如改进“T2 的 C API ，以便 Rustls 可以更容易地集成到现有的基于 C 的应用程序中”，并强制执行[一项无恐慌政策](https://github.com/ctz/rustls/issues/447)，以消除跨 C 语言边界使用 Rustls 时潜在的未定义行为 ISRG 在 Apache HTTP 服务器中替换 OpenSSL 的工作采取了类似的方式，使用 Google 提供的资金雇佣了一个 httpd 提交者来执行必要的更新。

“C 编程语言已经有 50 年的历史了，想想都觉得不可思议，所以现在是我们开始超越它的时候了。然而，有 50 年的 C 代码，我们必须在整个过程中进行互操作，否则，我们永远也到不了那里。谷歌的安全软件工程师丹·洛伦克说。“尽我们所能与现有的维护人员合作，是迄今为止最有效和最好的方式。像这样的开源项目的维护者工资很低，从一开始就没有得到足够的支持，所以依赖他们的大公司仅仅提出需求并不是一个好的策略。我们喜欢支持他们尽我们所能做出这些改进，而不仅仅是要求免费工作或自己重写东西。在我们力所能及的地方与社区合作会更好。”

Aas 表示，他们希望看到 Rustls 继续取代 OpenSSL 和其他不安全的 tls 库，并且随着每次集成，他们都会学到一些东西，使下一次集成更容易。

“你可以使用 OpenSSL 的任何地方，这些天来无处不在，从汽车到云服务到家庭网络服务器和设备，随着时间的推移，你应该可以使用 Rustls，”Aas 说，“所以这是一件影响很多人的大事。”

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>