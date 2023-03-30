# WebAssembly 旨在消除文件系统

> 原文：<https://thenewstack.io/webassembly-aims-to-eliminate-the-file-system/>

WebAssembly [继续扰乱](https://thenewstack.io/what-is-webassembly/)IT 生态系统。根据边缘服务平台 [Fastly](https://www.fastly.com/) 的高级首席工程师 [WASI 字节码联盟](https://bytecodealliance.org/)的联合创始人[林克拉克](https://twitter.com/linclark)在五月份举行的 [Qcon](https://qconferences.com/) 演讲，WebAssembly 系统接口(的最新计划旨在随着时间的推移，废除文件系统，甚至可能废除操作系统。

WebAssembly ( [WASM](https://webassembly.org/) )最初是为浏览器设计的，是一个安全的构建一次，在任何地方运行的运行时，它可以从你最喜欢的编程语言(假设你最喜欢的语言是 C/C++，C#或 Rust)摄取代码，并发出针对浏览器的超快速字节码。“WebAssembly 是一个编译目标，而不是编程语言，”Liam Randall 解释道，他是 [WasmCloud](https://wasmcloud.com/) 框架的联合创始人，在上个月举行的虚拟会议[kube con+CloudNativeCon EU](https://wasmcloud.com/?utm_content=inline-mention)的[会议](https://youtu.be/LfK7QYIU02A)上。“作为一个嵌入式引擎，WebAssembly 的关键价值主张是围绕速度、有效大小和安全性，这使它成为执行第三方代码的一个有吸引力的选择。”

WASI 本身被认为是将 WebAssembly 移出浏览器的一种方式。要做到这一点，并且为了让代码运行得更快，需要尽可能地针对特定的处理器架构进行定制。这需要在各种 ISAs 架构上创建一个低级抽象。一个非常模块化的接口，WASI 提供了一小组为主要操作系统量身定制的“小范围”API。由于其模块化架构，以后可以添加更多的平台和更高级别的跨平台功能。

最终，WASI 开发人员希望摆脱大多数操作系统所依赖的核心概念，即文件系统，理由是它将提高性能。

CompSci 中“文件系统”的概念实际上是一个隐喻，因为“文件”是用来存储数据集的，所以数据可以在程序之间共享。

“在软件开发的一个非常不同的时期，文件获得了它在系统界面中的中心位置，”Clark 指出。然而，这些天来，随着我们将更多的组件连接在一起构建应用程序，文件格式带来了各种部署和安全问题:“这些文件系统的使用方式基本上就像有一大堆全局共享的可变状态，”她说。

对于希望在特定硬件上使用 WASI 的开发人员，可以设置一个软件标志，它将告诉 WASI 运行时运行特定平台的字节码，允许程序访问文件系统或虚拟文件系统。

Clark 在她的演讲中解释说，但是 WASI 正在发展其他更快、更便携的选择。

一个是 WASI 文件系统接口，WASI 向开发者提供了自己的虚拟文件系统。在这种方法中，开发人员将使用相同的调用来打开和读取文件，但是文件本身将完全驻留在 WASM 模块中。

这意味着我们没有文件系统引入的全局共享可变状态问题。即使这些看起来像源代码中的文件，但实际上，它们会使用 WASI I/O 类型，如流和数组，这将使它们具有完全的可移植性，”Clark 解释道。

这种方法的缺点是，考虑到每个 WebAssembly 模块将携带的虚拟文件系统，模块的大小会膨胀。

为了充分的可移植性和效率，可以使用第三个 API，称为 WASI I/O。在这种情况下，程序根本不会调用文件，而是调用指向 I/O 类型本身的指针，比如数据数组或字符串。“有了这个，开发人员甚至不再考虑文件。都只是这些纯 I/O 类型，”她解释道。

“我们希望看到生态系统的其余部分逐渐迁移到只使用 WASI I/O，”Clark 说。

她解释说，一旦 WASI 意识到它正在处理的 I/O 类型，这种架构将会带来很多优化。例如，它可以极大地简化同一吊舱上两个独立容器之间的通信，这两个容器从事一项共同的任务。通常，在容器之间传递的数据必须被序列化，移入内存，然后再次移入内核内存，以便可以传递到 sidecar，sidecar 再一次重复这个过程，将数据移出到网络上(在这里，假设在接收端，所有这些过程必须以相反的方式再次进行)。

克拉克承诺，在 WASI 的装置中，这种复制过程可以缩短到仅纳秒。侧边栏和主程序可以合并到一个进程中，在这个进程中，对网络套接字的调用被程序内部更快的同步函数调用所取代。“这里没有中间的序列化和反序列化步骤，也没有对内核或进程间通信的重量级调用，”Clark 说。

QCon 的发言人告诉我们，最新 QCon 的视频将于今年年底在 InfoQ 网站和 YouTube 上发布。所以，一定要看看这篇发表的演讲。下一场 QCON 活动将于 11 月 1 日至 5 日在纽约举行，既有网络直播也有现场直播。

## WebAssembly 保护 Kubernetes

WebAssembly 已经在 Kubernetes 社区崭露头角，不仅仅是通过 [Krustlet，](https://thenewstack.io/krustlet-brings-webassembly-to-kubernetes-with-a-rust-based-kubelet/)一个 Kubernetes Kubelet 来代替容器运行 WASM 工作负载。

在同样于 5 月举行的 [KubeCon+CloudNativeCon EU](https://www.cncf.io/kubecon-cloudnativecon-events/?utm_content=inline-mention) 大会上，[开源企业软件公司](https://twitter.com/flavio_castelli?lang=en) [SUSE](https://www.suse.com/) 的工程经理 Flavio Castelli 和 SUSE 软件架构师 [Rafael Fernández López](https://www.linkedin.com/in/rafaelfernandezlopez) 讨论了如何通过 [KubeWarden](http://www.kubewarden.io/) 使用 WASM 编写安全容器工作负载，这是他们创建的一个 Kubernetes 策略引擎和准入控制器，可以将策略解释为 web 组装模块。

Kubernetes 的最佳实践策略是将用户权限策略写成代码，写成机器可以接受的声明性语法。这种策略即代码方法的问题在于，它需要开发人员花费大量时间来正确执行，要么填充大量的 YAML 文件，要么学习一种新语言来表达一组复杂的规则。

KubeWarden 目前在 alpha 版本中，提供了一种用 Rust 或 Golang 编写策略的方法，然后这些策略可以被编译成模块，由 Kubernetes 在 KubeWarden 策略服务器的一个隔离的 WASM 沙盒中执行。这些模块是可重用的，可以存储在容器注册中心或策略中心，由服务器提取。

KubeWarden 使用 Kubernetes 自定义资源定义(CRDs)和一个控制器来管理策略，减轻了开发人员学习低级 webhook 验证技术和其他 K8s 管理琐事的负担。

[https://www.youtube.com/embed/Bhw5Qi78jj8?start=713&feature=oembed](https://www.youtube.com/embed/Bhw5Qi78jj8?start=713&feature=oembed)

视频

## CSS 博士

QCon 上还有一场精彩的演讲，讲述了英国广播系统(BBC)如何测试 WASM，将其作为一种标准化跨平台内容处理的方式。

[BBC 研发软件工程师 Tim Pearce](https://www.bbc.co.uk/rd/people/tim-pearce) 在他的演讲中提到了[BBC 如何寻求使其所有的音频、视频和印刷内容“更加个性化、互动和身临其境”，鉴于 BBC 的节目已经在各种移动、桌面和智能电视平台上运行，这是一项艰巨的任务。这家媒体公司已经确定了一种通用格式“基于对象的媒体”，它可以从公司的“单一来源播放器”上运行](https://plus.qconferences.com/plus2021/presentation/experimenting-wasm-future-audience-experiences-bbc-iplayer)

基于对象的媒体允许内容节目根据每个观众成员的要求而改变。“对象是指他们用来制作内容的不同资产，可以是大对象，如用于制作戏剧的音频或视频，也可以是小对象，如单个帧或视频、字幕或其他屏幕上的图形，”他解释道。通过把一段媒体分解成独立的对象，赋予它们意义，并描述它们如何重新排列，一个程序就能改变以反映单个观众的环境。

目前，这是通过为不同的平台生成多个工件来实现的，比如为移动和网络浏览器。不过，理想情况下，WASM 字节码可以跨所有这些服务使用。

这家媒体公司正在测试 WebAssembly 工具链 [Emscripten](https://emscripten.org/) ，将 C 或 C++编写的交互式媒体资产编译成 WebAssembly 字节码。这提供了一种在网络上提供相同用户体验的方式，该公司现在通过其桌面和移动应用程序提供这种体验。此外，在所有不同的浏览器上，媒体体验将是相同的，这在本地很难实现，因为不同的浏览器实现 CSS 的方式不同——同时为 Web 带来接近本地的性能。

Pearce 解释说:“这种方法在不同的浏览器上提供了流畅、一致的用户体验。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>