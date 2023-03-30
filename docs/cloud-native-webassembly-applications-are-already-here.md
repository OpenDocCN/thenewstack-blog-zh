# 云原生 WebAssembly 应用程序已经在这里

> 原文：<https://thenewstack.io/cloud-native-webassembly-applications-are-already-here/>

[](https://twitter.com/juntao)

[Michael Yuan](https://twitter.com/juntao)

[Michael Yuan 是 WasmEdge 的创始人和维护者，WasmEdge 是一个由 CNCF 托管的开源 WebAssembly 运行时，用于边缘计算、服务网格和嵌入式功能。袁博士是六部软件工程书籍的作者，也是一名长期的开源贡献者。他是 Second State 的联合创始人，Second State 是一家由风险投资资助的初创公司，支持并商业化 WebAssembly 和 Rust 生态系统中的企业应用程序。](https://twitter.com/juntao)

[](https://twitter.com/juntao)[](https://twitter.com/juntao)

2021 年 7 月，计算机器协会编程语言特别兴趣小组将其享有盛誉的[编程语言软件奖](https://www.sigplan.org/Awards/Software/)授予 WebAssembly，以表彰其作为“自 JavaScript 以来第一种在网络浏览器中广泛采用的新语言”的成就今年也标志着 WebAssembly 在 web 浏览器之外的爆炸式增长，特别是在服务器端和云原生环境中。

2021 年到目前为止，[云原生计算基金会](https://cncf.io/?utm_content=inline-mention)已经正式接受了至少三个 [WebAssembly 项目](https://thenewstack.io/what-is-webassembly/)，包括 [WasmEdge Runtime](https://wasmedge.org/) ，一个云原生 WebAssembly 运行时， [wasmCloud](https://github.com/wasmCloud/wasmCloud) ，一个 WebAssembly 应用框架， [Krustlet](https://krustlet.dev/) ，一个在 Kubernetes pods 中运行 WebAssembly 程序的工具，还有更多现有的 CNCF 项目开始采用 WebAssembly。

为了适应云原生社区对 WebAssembly 日益增长的兴趣， [KubeCon+CloudNativeCon](https://www.cncf.io/kubecon-cloudnativecon-events/?utm_content=inline-mention) 北美于 10 月在洛杉矶举办了一场专门的[云原生 Wasm 日活动](https://events.linuxfoundation.org/cloud-native-wasm-day-north-america/)。超过 300 名开发人员注册(并付费)参加了为期一天的活动。我是这个活动的策划委员会成员，亲自参加了这个活动。

活动以微软 Azure 的 [Ralph Squillace](https://twitter.com/ralph_squillace) 和 [Cosmonic](https://cosmonic.com/) 的 [Liam Randall](https://twitter.com/Hectaman) 的主题演讲开始。斯奎莱斯和兰德尔都是云计算的老手。他们的主题讨论了云计算架构的演变，并为 WebAssembly 作为云原生运行时的兴起提供了背景。

WebAssembly 是一个轻量级、快速、安全和多语言的函数“容器”。它将由 Kubernetes 和 Docker 开创的云原生编程模型从大型数据中心带入了边缘计算和微服务领域。

该活动传达的信息是，云原生 WebAssembly 应用程序已经被各种规模的企业采用，随着这些应用程序的出现，我们还看到了一个蓬勃发展的框架、工具和运行时生态系统的出现。

## 库伯内特斯

由于 Kubernetes 已经成为所有云原生应用程序的事实上的“控制平面”,所以为了看到认真的采用，必须在 Kubernetes 中支持 WebAssembly。服务器上的云原生 WebAssembly 不仅需要 WASI 访问操作系统功能，还需要 Kubernetes 集成。我们需要在 Kubernetes 集群中与其他容器(例如 containerd、Docker 和 cri-o)并行运行 WebAssembly 工作负载。在这次事件中，我们看到了两种主要的方法。

Krustlet 项目直接从 Kubernetes pod 运行 WebAssembly 程序。在整个 Wasm 日活动中，我们看到了多个使用 krustlet 的演示。事实上，[微软 Azure AKS 在大会期间宣布了一个基于 krustlet 的 WebAssembly 服务](https://azure.microsoft.com/en-us/updates/public-preview-aks-support-for-webassembly-system-interface-wasi-workloads/)。看看吧！

crun 项目是 Kubernetes 生态系统的一个流行的容器运行时。它可以[自动检测容器映像是用于 WebAssembly](https://github.com/second-state/wasmedge-containers-examples) 还是 containerd/Docker，然后启动并管理适当的运行时/容器。它使 WebAssembly 程序成为 Kubernetes 集群中的一等公民。

WebAssembly 程序不仅仅是由 Kubernetes 管理和控制的工作负载。他们也可以扩展 Kubernetes 本身。来自 SUSE [的 Rafael Fernández López 向我们介绍了](https://youtu.be/oNJxPbvPzLk)kube warden 项目，该项目为 Kubernetes 提供了一个基于 WebAssembly 的策略引擎。

## 应用框架

应用程序框架构建在 Kubernetes 之上，为应用程序提供公共服务。一个很好的例子是由微软创建的 Dapr，它很快将成为 CNCF 的一个孵化项目。Dapr 利用 sidecar 模式来提供常用的服务，例如服务发现和调用、弹性重试、日志记录和跟踪、监控、秘密存储、连接安全等。连接到这些边车的微服务应用。这些边车应用程序(微服务)可以由 Kubernetes 管理。我们了解到基于 WebAssembly 的 sidecar 应用程序现在在 Dapr 上得到支持。

[wasmCloud](https://github.com/wasmCloud/wasmCloud) 项目是专门为 WebAssembly 设计的基于 actor 的应用程序框架。来自 Red Badger 的 Stuart Harris 和 Aayush Attri 讲述了他们如何使用由 Kubernetes 管理的 wasmCloud 集群在一家欧洲银行内部实施大规模应用程序。

服务网格构建在应用程序框架之上。它们提供额外的功能，例如通过代理进行流量路由和分流。特使代理是基于 WebAssembly 的服务网格扩展的早期采用者。蚂蚁集团的 [MOSN](https://mosn.io/en/) 是一个管理超过 200，000 台服务器的大型集群的服务网格。

MOSN 团队的 Jason Song 在活动中做了一个简短的发言，讨论了在服务网格中运行 WebAssembly 功能来代替传统的容器。MOSN 的代理支持 [proxy-wasm](https://github.com/proxy-wasm) 规范作为扩展机制。MOSN 的 sidecar 框架被称为 [Layotto](https://github.com/mosn/layotto) ，支持用 WebAssembly 编写的微服务。Jason 现场演示了如何在一个电子商务应用中使用 Kubernetes 在 MOSN 和 Layotto 上部署和管理 WebAssembly 功能。

## SaaS 的嵌入式功能

到目前为止，我们已经了解了 WebAssembly 在云原生基础设施中的应用。商业逻辑应用怎么样？

WebAssembly 使业务应用程序能够轻松支持第三方插件或扩展。集中托管的云原生应用程序(例如 SaaS)可以使用 WebAssembly 运行时来安全高效地执行任何用户提交的代码功能。

[亚轨道](https://suborbital.dev/) 的康纳·希克斯给了 [一个非常清晰的解释](https://youtu.be/ID5z3ZkQ1-M) 为什么反应式嵌入式功能比传统的 webhooks 或“原生集成”(即定制模板)更适合扩展和定制 SaaS。 [Suborbital](https://github.com/suborbital) 是一个应用程序框架，可以轻松地将 WebAssembly 函数嵌入到 SaaS 中。

Shopify 是使用嵌入式 WebAssembly 功能来扩展和定制其 SaaS 的先驱。人们发现，开发人员真的希望使用 JavaScript，而不是 Rust 或 C/C++来编写这些函数。Shopify 的 Saul Cabrera[做了一个关于如何在 WebAssembly 上运行和优化 JavaScript 程序的讲座](https://youtu.be/IGH0zIgJ6rg) 。同样，我们也见过 WebAssembly 运行时，比如 [WasmEdge](https://github.com/WasmEdge/WasmEdge) ，支持 [高级 JavaScript 特性](https://www.secondstate.io/articles/run-javascript-in-webassembly-with-wasmedge/) ，比如 ES6 模块，异步联网，以及 [Rust / JavaScript 交互](https://www.secondstate.io/articles/embed-rust-in-javascript/) 。

Bailey Hayes & Carl Sverre 做了一个[](https://youtu.be/TqZsbrvhD54)的演讲，讲述了 [SingleStore 如何使用 WebAssembly](https://github.com/singlestore-labs/Wasm-Day-2021-Distributed-Computation-with-WASM-and-WASI) 来执行嵌入在云数据库中的用户自定义功能。它允许数据存储和计算紧密结合，提高效率。在他们的谈话中，该团队演示了如何在大型数据集上使用人工智能模型进行实时情绪分析。作为该领域的早期采用者，该团队还参与了标准化工作，提出了一个 [WASI 数据](https://github.com/singlestore-labs/wasi-data) 规范，以支持数据库和 WebAssembly 运行时之间的标准双向通信协议。

## 人工智能和物联网

正如 Liam Randall 在他的主题演讲中所讨论的，WebAssembly 最大的应用机会可能在边缘，包括边缘网络和边缘设备。

Dan Mihai Dumitriu [展示了索尼物联网应用部门 Midokura 如何在传感器设备上部署 WebAssembly 应用。WebAssembly 的小内存占用和高性能使其能够作为用户应用程序的安全沙箱在小型设备上运行。来自微软的凯特·戈登林和来自伯南布哥联邦大学的罗德里戈·法瑞斯·罗德里格斯·莱默斯](https://youtu.be/w4_Ju0E8958)[展示了作为 Krustlet 运行的 WebAssembly 应用程序](https://youtu.be/8hF9hnUJyCY) [Akri](https://github.com/deislabs/akri) ，以发现物联网设备并使它们作为资源在 Kubernetes 集群中可用。

事实上，CNCF 现在至少有三个 Kubernetes-on-the-edge 项目， [KubeEdge](https://kubeedge.io/en/) ，[superge](https://superedge.io/)和 OpenYurt。有了前面提到的 Kubernetes 集成，WebAssembly 在物联网设备上的前景一片光明。

今天边缘网络上的一个重要应用是 AI 推理。轻量级和快速的 WebAssembly 运行时可以使 AI 推理计算更接近边缘的传感器和数据源。在这个事件中有两个关于人工智能推理的演讲。

来自 Layer5 的 Shivay Lamba 和来自 Hackerrank 的 Mritunjay Sharma 做了一个[演讲](https://youtu.be/wjt11RbOcww)，讲述了如何使用 [WasmEdge 的 Tensorflow 和 Tensorflow Lite API](https://www.secondstate.io/articles/wasi-tensorflow/) 扩展，以每幅图像毫秒的速度进行图像识别。这个 API 可供 [Rust](https://www.secondstate.io/articles/wasi-tensorflow/#a-rust-example) 和 [JavaScript](https://www.secondstate.io/articles/wasi-tensorflow/#a-javascript-example) 开发者使用。

来自微软[的拉杜·马泰(Radu Matei)讨论了](https://youtu.be/jnM0tsRVM_8)WASI-NN 规范，该规范提供了一个标准 API 来将任何人工智能推理库合并到 WebAssembly 中。WasmEdge Tensorflow 扩展也适用于 WASI-NN。

## 生态系统创新

随着 WebAssembly 应用程序的增长，开发人员争相改进 WebAssembly 本身及其相关工具。本次活动中有两个引人注目的 WebAssembly 生态系统成果， [Bindle](https://github.com/deislabs/bindle) 和 [Grain](https://grain-lang.org/) 。

Bindle 的目标是为 WebAssembly 模块和工件提供一个包管理系统。正如我们从 NPM、Docker Hub、Go 和 Rust crates 的成功中所看到的，包管理可以促进协作，并使开发人员能够建立在彼此工作的基础上。微软 Azure 的 Matt Butcher 和 Cosmonic 的 Taylor Thomas 做了一个关于 Bindle 如何设计和如何使用的[演讲。我们期待更多人采用这项重要技术。](https://youtu.be/ZCYuWesDyu0)

Grain 是一种 WebAssembly-first 编程语言。静态类型和编译的编程语言可以最有效地利用 WebAssembly 的轻量级运行时。但是 Rust、C/C++等静态类型语言对于初学者来说并不容易。来自 Grain 项目[的奥斯卡·斯潘塞讨论了](https://youtu.be/XfUcky-Sh5g)如何将 Grain 设计成一种易于使用的编程语言，可以编译成高效的 WebAssembly 字节码。这个项目仍然是早期的，但非常有前途。

## 下一步是什么

云原生 WebAssembly 应用在 2021 年开始腾飞。随着 WebAssembly 被整合到几乎所有领先的云原生项目中，我们可以在未来 12 个月内看到 WebAssembly 应用程序在云中的普遍部署。你还在等什么？

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>