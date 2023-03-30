# Rust 和 OS，Web，数据库和其他语言

> 原文：<https://thenewstack.io/rust-and-the-os-the-web-database-and-other-languages/>

这是两部分系列的第二部分。阅读第一部分。

对 2022 年 Rust 大会的兴趣增加，突显出各种类型的项目正在拥抱流行的编程语言。人们很自然会对这种语言的深度和它目前包含的技术感到好奇。本文将指出几个亮点。

## 操作系统可以用 Rust 编写吗？

简单地说:是的，Rust 中有各种各样的操作系统和类似 OS 的系统。这包括单核、虚拟机管理程序、其他虚拟机技术和固件项目。

**谷歌的 KataOS** 是一个安全的操作系统，出于安全目的，它使用 seL4 作为微内核。Performant seL4 在数学上被证明是正确的，并且非常安全。保证完整性、可用性和保密性的令人愉快的概念令人耳目一新。在内部，KataOS 还能够动态加载和运行在 seL4 的 CAmkES(基于微内核的嵌入式系统的组件架构)框架之外构建的第三方应用程序。

当前的 GitHub 版本包含了 KataOS 的大部分核心组件:

*   用于 Rust 的框架，比如用于 sel4 系统调用 API 的 sel4-sys crate。
*   用 Rust 写的备用根服务器。
*   seL4 的内核补丁也允许回收根服务器使用的内存。

Google 参考实现称为 Sparrow，允许用户在安全的硬件平台上评估 katao。此外，Sparrow 还包括一个在 RISC-V 架构上用 OpenTitan 构建的逻辑安全的信任根。

KataOS 的另一个目标是作为 Android 系统的底层操作系统。如果这成为现实，Rust 的最终用户和开发者将会爆炸。

氧化还原是更传统的操作系统 ilk 的老项目之一。它为那些对“类 Linux”开发平台感兴趣的人提供了一个合理的起点。一些氧化还原观察结果:

*   当前版本是 0.7(我们跑的是 0.6)，所以不是最新的。
*   这可能是持续时间最长的 Rust OS 项目。
*   靴子速度极快。QEMU 在 M1 ARM 上模拟 x86_64 只花了不到 15 秒。
*   它类似于 Unix/Linux，但是有一个微内核设计，可能是 POSIX。
*   它有基本的工具互联网浏览器，文件编辑器，文件浏览器，日历，图像浏览器。
*   版本 0.6 运行在大约 350MB。

表格的主要来源:[https://github.com/flosse/rust-os-comparison](https://github.com/flosse/rust-os-comparison)

## 铁锈和网络

任何稍微接触过 Rust 的人都知道 WebAssembly (Wasm)有很多可用的技术。许多人认为这项技术是一种进化的 web 用户界面。Rust 技术提供了从网页基础设施中减少大量 CSS、HTML 和 JavaScript 的机制。由于互联网将继续成为许多人生活中至关重要的一部分，随着 Rust 在网络空间的发展，它还可能提供更多的安全检查和内存安全。

Wasm 作为编译目标包含在许多 Rust 库栈环境中。这意味着无需修改代码，您的程序就可以在 web 上运行。 [Bevy](https://bevyengine.org/) ，一个游戏开发工具包，就是这样一个环境。

[WebGPU](https://surma.dev/things/webgpu/) 是一个崭露头角的 API，它为在您的环境中访问多个 GPU 提供了更简单的接口。不仅仅是为了游戏。科学可视化的许多方面以及与增强现实/虚拟现实(AR/VR)技术的集成将在智能视觉交互和设计方面实现许多功能。这将有助于那些在许多行业拥有丰富数据的人。

Rust 也有很好的库来创建 web 服务基础设施。所以，无论你是在开发一个平台，发布一个 API 还是发布一个网站，你都有工具。Actix、Hyper、Iron 和 Russell less 是这一领域的一些有用工具。

## 数据库可以用 Rust 编写吗？

Rust 中实现了许多实验性的 SQL 和 NoSQL 存储。一些数据库引擎已经浮出水面，为那些希望完全接受这种语言能力的人提供了选择。考虑到环境中固有的速度和责任，不难想象这种适合。超现实数据库(商业)、FeOphant(类似 Postgres)、Databend (Arrow2)和 GlueSQL 就是几个例子。许多支持移动和物联网环境的项目也即将上线。如果你的梦想是一堆可以发展的铁锈，那它就在路上了。当然，大多数主流数据库也有 API 和驱动程序。

## Rust 能与其他编程语言很好地集成吗？

铁锈有一些有利因素。多语言 API 已经成为开发环境的标准，因此编写后端时也考虑到了这一点。在这样的环境中，添加另一种语言 API 通常不是很困难。正因为如此，现有系统的 Rust APIs 扩大了 Rust 开发者的范围。

## 广为报道的语言配对

Rust 似乎能够[很好地扩充其他语言](https://thenewstack.io/rust-vs-go-why-theyre-better-together/)，创建高效的混合开发环境。

**C** — Rust 通过其[外部函数接口(FFI)](https://static.rust-lang.org/doc/master/book/ffi.html) 直接支持开发与 C 的接口。您会发现，在许多情况下，可以在这里编写近乎安全的代码，也可以在 Rust 代码中实现类似 C 回调的功能。此外，FFI 远远超出了 c。

**Javascript**——除了 JS 和 Rust link with WebAssembly，再加上一点搜索引擎的魔力，很明显有很多项目和论文都采用了协调这两种环境的技术。甚至还有用 Rust 写的 JavaScript 解释器/前端。同样显而易见的是关于构建个性化或定制解释器的教程。Rust 可以愉快地与许多语言交互，比如 Python、Lua、Erlang、Haskell 等等。

## 谁有可能很快使用 Rust？

一些领域似乎已经成熟，尤其是内存安全和性能是关键问题的领域。在这些努力中不使用 Rust 可能会更难证明，特别是如果它们本质上是绿地。如前所述，大多数大量使用云服务和软件开发技术的行业可能会无意中将其与移动和 web 应用程序一起使用。

除了计算和 IT 部门，政府/国防、物联网/嵌入式、电信、医疗保健和教育/研究似乎也很突出。IT 经理关注的几个趋势也可能对 Rust 有利。例如，网络安全和云战略是长期和短期的主导主题。Rust 对这两者都发出了强烈的信号。不同种类的新自治基础设施必须满足增加的安全性和稳定性属性。这显然有助于在公共安全和各种规模的基础设施管理的共同所有权方面取得最佳成果。这将包括民用、智能家居、驾驶、传感器等等。

制造商福特、通用、宝马、博世、大众、沃尔沃、丰田都加入了 [Autosar 功能安全工作组(WG-SAF)](https://www.autosar.org/news-events/details/autosar-investigates-how-the-programming-language-rust-could-be-applied-in-adaptive-platform-context/) 的一个新小组，这是一个汽车标准小组，负责检查 Rust 在参考平台中的使用。

SAE 国际也成立了一个特别工作组，负责汽车工业安全相关系统的防锈。在这种情况下，你的车上有一点锈迹是受欢迎的。

创新的铁路系统也有所发展。[并联系统](https://www.youtube.com/watch?v=qaj5q88eLjk)在这个空间中允许单独列车车厢的动态(解)耦合和自推进。

在金融领域，一个有用的交易库 Quants/QuantLib 正在被氧化。证券(股票)领域的术语“quants”指的是编写高速交易算法程序的数据专家，这些算法通常对做市商比对散户有优先权。尽管存在争议，但这表明华尔街正在观望。

顺便说一下，Rust 环境中至少有 25 个活跃的面向加密的箱子，用于处理各种令牌。无论如何，Rust 已经准备好进入这个领域，并可能带来解决方案。到处都是 NFT 和 eft！

娱乐和游戏似乎是采用 Rust 的令人惊讶的领域，但它也可能出现在电影处理和游戏开发等领域。你会在音乐流媒体应用程序中找到它，包括 Spotify 客户端、各种游戏、主机模拟器，当然还有丰富的游戏开发环境，如 Bevy、Fyrox、Piston 和 Unrust。这似乎是一个动力区。游戏开始。

## 结论

这个由两部分组成的系列有四个要点:

1.  Rust 将继续在基础计算基础设施领域取得巨大进展。
2.  内存管理模型正在改变游戏规则，你可以期待它在其他语言中被模仿。
3.  像 Wasm 这样的技术将把 Rust 更多地带入应用领域。
4.  这种到来伴随着更高生产率的交换，但这可能是有限的时间。

Rust 团队通常非常支持新人，并且与新生的技术一起工作是值得的。Rust 同时使用 [Discord](https://discord.com/invite/rust) 和 Zulip 进行聊天。[在这里了解如何跳跃](https://www.rust-lang.org/community)。不要害怕让你的手生锈。

*衷心感谢《未来微》的林宗芳、张燕和陈燕对武打细节和语言表现分析的贡献。*

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>