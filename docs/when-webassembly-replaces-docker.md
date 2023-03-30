# 当 WebAssembly 取代 Docker

> 原文：<https://thenewstack.io/when-webassembly-replaces-docker/>

在 KubeCon + CloudNativeCon 期间，吸引了一些注意力的一个更有趣的讨论是，由于其设计，WebAssembly(也称为 Wasm)如何在许多情况下取代 Docker。但是正如我们将在本文下面看到的，过度关注 WebAssembly 的这一方面是没有抓住重点的，因为更重要的是 WebAssembly 可以支持的业务用途，如下所述。

然而，就像任何有趣的新编程语言或技术一样，Wasm 价值的真正测试是其商业用途，Wasm 在简单性、可移植性和安全性方面的优势似乎至少使其成为弥补 Docker 缺点的良好候选，特别是对于 edge 和分布式应用程序。

除了 HTML 和 CSS 之外，WebAssembly 还可以用于将 [JavaScript (JS)](https://developer.mozilla.org/en-US/docs/Web/JavaScript) 、 [C++](https://en.wikipedia.org/wiki/C%2B%2B) 和 [Rust](https://www.rust-lang.org/) 集成到一个二进制格式的运行时平台中，直接在 CPU 上的机器级别上运行。它可以用于支持 web 应用，并扩展到任何运行在 CPU 上的边缘环境和云原生平台，包括服务网格和边缘 Kubernetes 支持。Wasm 也有一段时间了，在 2019 年[万维网联盟(W3C)](https://thenewstack.io/this-week-in-programming-the-time-has-come-to-pay-attention-to-webassembly/) 将其命名为 web 标准，从而成为与 HTML、CSS、JavaScript 并列的第四个 Web 标准。

[Colin Murphy，](https://www.linkedin.com/in/colin-murphy-08b3601b/)[Adobe](https://www.adobe.com)高级软件工程师，在关于 CDN edge compute 和 Wasm/ [WASI](https://wasi.dev/) 平台以及当前和未来 Adobe 应用的演讲中详细介绍。为了提高业务绩效，墨菲提到 Wasm 可以作为 Docker 的继任者。墨菲说，他“只是四处看看，看看 Docker 和 Kubernetes 的继任者是什么’，所以当我进入 WebAssembly 时，我开始说‘嗯，我能不能把一个实际用于生产的微服务，我能不能用 WebAssembly 把它部署在服务器边缘的客户端上？’”他发现自己的预感是正确的。

## 使用 Wasm 避免漏洞

例如，与 Docker 相关的一个主要问题是 CVE 文件中的潜在漏洞。“有时，同一个漏洞可以有多个 CVE 作为 Docker 容器。有了 WebAssembly，你就没有任何第三方的东西了。墨菲在一次播客采访中说:“你就把它当成一个二进制吧。”。“然而，当然，总会有安全问题。但是，你不必带上操作系统的所有其余部分，也不必假装它是一个操作系统，因为它实际上是它自己的单元，这种想法“有助于使 Wasm 具有吸引力。

然而，墨菲说，也不要指望 Wasm 会完全取代 Docker。

“仍然有大型机，仍然有主机操作系统，仍然有具有非常特殊的业务案例的虚拟机，并且将继续被使用。但也有一些非常好的地方，特别是 5G 汽车的边缘，以及所有这些物联网与世界和边缘相遇的应用，在这些地方，你将无法随身携带 Docker。”

“Wasm 是否有可能最终在某一天完全取代 Docker 的使用”这个问题是一个不合理的推论， [产品负责人杰克·莱维恩](https://www.linkedin.com/in/jakelevirne) ， [Docker](https://www.docker.com/) ，在一封电子邮件中回应道。Levirne 说，这个问题没有正确地描述开发者市场是如何运作的，因为 Wasm 作为一种技术，不能取代 Docker。

“Wasm 是 Docker 的补充——无论开发人员选择何种方式来设计和实现他们的应用程序，Docker 都会支持他们的开发体验，”Levirne 说。

Levirne 说，使用 Docker 的开发、测试和部署工具链可以更容易地维护应用交付的可再生管道，而不管应用架构如何。此外，数百万预先构建的 Docker 图像，包括数千个官方的和经验证的图像，提供了“核心服务(例如，数据存储、缓存、搜索、框架等)的主干。)”他说，这可以与 Wasm 模块一起使用。

“随着时间的推移，容器运行时和注册表将扩展到包括本机 Wasm 模块支持。事实上，这已经在今天发生了，”勒维恩说。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>