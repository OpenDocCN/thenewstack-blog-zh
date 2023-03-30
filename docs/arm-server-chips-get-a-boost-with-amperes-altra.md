# ARM 服务器芯片因 Ampere 的 Altra 而获得提升

> 原文：<https://thenewstack.io/arm-server-chips-get-a-boost-with-amperes-altra/>

Ampere Computing 正在给基于 ARM 的芯片带来一种服务器突破，这种突破在过去十年里一直困扰着其他芯片公司。

该公司的芯片上个月被谷歌云和 HPE 采用，他们的支持为整个 ARM 服务器生态系统提供了巨大的推动力。

Ampere 由前英特尔总裁 [Renee James](https://www.linkedin.com/in/renee-j-james-64182424/) 创立，她在 2016 年管理层重组后离开了英特尔。她之前负责英特尔的数据中心业务，并在意识到英特尔的 x86 芯片不适合网络应用程序等以云为中心的工作负载后成立了 Ampere。

“我们认为行业的增长将来自软件、工作负载……您需要弹性地提供线性扩展性能。詹姆斯在上个月的一次新闻发布会上说:“这就是今天开发的软件如何消耗 CPU 的性能，从而提高能效。”。

Ampere 最快的 Altra 芯片有 128 个内核，基于该公司定制的 ARM 架构。这是高端 AMD x86 服务器芯片内核数的两倍，是英特尔 x86 服务器芯片内核数的三倍多，后者有 40 个内核。

## 专注于服务器

用于服务器的 ARM 和 x86 芯片有着根本的不同，有着截然不同的起源。ARM 架构强调能源效率，根源在于智能手机，而 x86 服务器芯片旨在提高性能，是 AMD 和英特尔最初为数据库和 ERP 等应用程序设计的高功耗芯片的后代。

“[Altra]是一种通用微处理器。它运行 Windows，它运行 Linux，它什么都做。它不是专门为传统应用程序设计的，”James 说，后来补充道，“我在构建 x86 服务器方面有很多经验。”

采用 Ampere 芯片的供应商指出，与 x86 芯片相比，Altra 内核提供了更高的性能，同时消耗了更少的功率，从而节省了更多成本。

谷歌云上周宣布将在[陶 T2A](https://cloud.google.com/blog/products/compute/tau-t2a-is-first-compute-engine-vm-on-an-arm-chip) 虚拟机实例中使用安培的处理器，这些虚拟机实例是为视频、数据库和人工智能设计的。根据谷歌的说法，采用 Ampere 芯片的 T2A 比其 x86 对手多提供 31%的马力，同时在价格和性能上节省高达 65%。

HPE 上个月推出了采用 Ampere Altra 芯片的下一代 Proliant Gen11 服务器系列。几十年来，HPE 推出了基于 x86 芯片的新一代单路或双路服务器，但决定通过新的 Proliant RL300 服务器走 ARM 路线，这也标志着 HPE 对云服务器的思考方式发生了巨大变化。在高端计算方面，HPE 已经在其 Apollo 80 中使用了基于 ARM 的富士通 A64FX 处理器，该处理器针对的是在 2U 尺寸中具有八个单插槽的高性能系统。

“这实际上是在一个可扩展的环境中运行代码，无论是什么形式——开源、现代云原生软件、层，还是在……Linux 的容器化环境中内部开发的平台和工作负载,[执行副总裁兼 HPE 计算业务总经理 Neil MacDonald](https://www.hpe.com/us/en/leadership-bios/neil-macdonald.html) 在新闻发布会上说。

## 过去的尝试

十年前，HPE 的 ARM 芯片实验，一项名为 Moonshot 的努力，失败了。当时，许多创业公司试图将智能手机中的 ARM 芯片引入服务器，重点是 LAMP (Linux，Apache，MySQL，Perl/PHP/Python)堆栈。

服务器制造商对 ARM 设计缺乏兴趣导致了一些公司的关闭，如 [Calxeda](https://en.wikipedia.org/wiki/Calxeda) ，而 Cavium 等公司的其他努力也因软件生态系统不成熟而被放弃。当时的 ARM 软件开发大多集中在移动设备上，而服务器软件则集中在 x86 上。

麦克唐纳说，但现在的情况大不相同。

## 新世界

“变化是什么——如果你看一下生态系统……有一个强大的成熟开发工具链，它被业内成熟的其他一些举措所加剧和加速。MacDonald 说:“从平台开发的角度来看，过去五年的开源和更广泛的软件包比过去有了更多的选择。

安培特别强调软件开发，以促进其芯片的采用，这样它就不会重复像 Calxeda 这样的公司的错误，尽管它在硬件方面做出了开创性的工作，但还是失败了。

“已经有许多先驱尝试在行业中建立替代方案。很难构建出比 x86 更好的东西，它是为客户端-服务器计算的构建而设计的。这是一个完美的工具。它不是云原生的完美工具，”詹姆斯说。

Ampere 发布了流行的云、数据库和其他本地应用的基准。它还在谷歌云等服务上测试其芯片系统，以确保可靠性和性能。

“我们确实对人们在我们的产品上使用的数百种不同的软件栈进行了夜间回归，”詹姆斯说。

## 让游戏开始吧

但 Ampere 最初的成功也使其面临来自包括亚马逊在内的大牌品牌的竞争，亚马逊已经建立了自己的基于 ARM 的芯片，名为 [Graviton](https://thenewstack.io/aws-pushes-forward-its-custom-chip-efforts-with-graviton3/) ，并正在 AWS 上使用。

根据 [Trendforce](https://www.trendforce.com/) 的一项研究，到 2025 年，ARM 架构将占据数据中心服务器 22%的份额。这次扩张将由 AWS 的 Graviton 领导，它现在已经是第三代了。

TrendForce 在 3 月份发表的一份研究报告中说:“AWS 在 2021 年部署的基于 ARM 的处理器达到了整体服务器部署的 15%，并将在 2022 年超过 20%。

HPE 的 MacDonald 表示，ARM 是其投资组合的一个补充，它将继续提供广泛的芯片，这意味着该公司将继续提供 x86 芯片。HPE 在名为 Frontier 的超级计算机中使用了 AMD 的 x86 芯片，这是上个月发布的最新 500 强名单中世界上最快的超级计算机。

基于 x86 的芯片仍然是云提供商的主流。但是来自 ARM 的日益激烈的竞争是英特尔和 AMD 致力于为大客户定制芯片的原因之一，Tirias Research 的首席分析师 [Jim McGregor](https://www.linkedin.com/in/tekstrategist/) 说。

“云提供商将自己生产芯片，比如 Graviton 处理器，或者谷歌的 TPU 加速器。或者他们会和搭档一起工作。如果你想成为合伙人，你必须灵活。我认为英特尔正在适应新的世界。新的世界是，你必须灵活应对你的客户和他们正在运行的工作负载，”McGregor 说。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>