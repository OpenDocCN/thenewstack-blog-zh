# CNCF 孵化开放政策代理，一个政策代码项目

> 原文：<https://thenewstack.io/cncf-incubates-open-policy-agent-a-policy-as-code-project/>

作为一名年轻的程序员，您可能学到的早期经验之一是，如果您发现自己一遍又一遍地编写相同的代码，您应该将这些代码分离到一个类或一个函数中，这样既可以提高效率，又可以更容易地跨功能的多次使用来更改功能。如今，这种想法已经扩展到 DevOps 实践中，如基础设施即代码(IaC ),其中技术堆栈的管理和供应被分离出来，以实现自动化和一站式访问。最近，策略即代码的出现为将策略应用于多种目的和场景提供了同样的自动化和易用性。

[开放策略代理(OPA)](https://www.openpolicyagent.org/) 项目就是这样一个作为代码的策略提供者，该项目刚刚被[云本地计算基金会(CNCF)](https://www.cncf.io/) 接受为孵化级托管项目。根据该公司的一份声明，OPA 是“一个开源的通用策略引擎，可以在整个堆栈中实现统一的上下文感知策略执行”,它“比硬编码的服务逻辑或特定领域语言提供了更大的灵活性和表达能力”

在对新堆栈的采访中， [Torin Sandall](https://www.linkedin.com/in/torin-sandall-1967387) ，Styra 的软件工程师和 OPA 的技术负责人，将这种解耦作为项目的核心原则。

“这个项目背后的核心思想之一是将政策制定与政策执行分离开来。“OPA 为架构师、开发人员和安全从业者提供了一个将安全策略表达为代码并交付使用的好方法，”Sandall 说。“您可以将它用于微服务、API 网关、脚本和 CI/CD 管道。您可以在堆栈中的任何地方应用它来解决各种不同的策略相关问题。无论您是在谈论访问控制和微服务环境，还是对容器化的工作负载施加限制，OPA 的使命都是一样的，即帮助大型组织对这些类型的资源实施限制、防护或规则和治理。”

[https://www.youtube.com/embed/CDDsjMOtJ-c?feature=oembed](https://www.youtube.com/embed/CDDsjMOtJ-c?feature=oembed)

视频

OPA 通过使用 JSON over HTTP 的 RESTful APIs 提供了通用语言兼容性，并且易于部署，没有依赖性。它可以作为守护进程与您的服务并行运行，或者，对于用 Go 编写的服务，OPA 可以作为库嵌入和使用，消除了运行单独守护进程的需要。它还为用户提供了一个交互式 shell 来试验查询和数据集。

桑德尔说，OPA 被接受为孵化级项目表明该项目已经走了多远，一些大公司正在使用这项技术。CNCF 孵化级托管的其他项目包括 OpenTracing、Fluentd、gRPC、rkt、CNI、Jaeger、公证人、TUF、Vitess、NATS、Linkerd、Helm、Rook、Harbor 和 etcd。

“在过去的一年里，在生产中运行项目的人数有了很大的增长。网飞将该项目作为其内部安全平台的一部分，Intuit 和 Capital One 等公司正在为 Kubernetes 生产中的准入控制运行该项目。“越来越多的人在生产中使用这个项目来执行重要的政策。从沙盒更新试用的举动反映了该项目在过去一年中取得的进展。”

对 GitHub 上的 [OPA 库的访问显示了一些与第三方技术的集成，如 Kubernetes、Docker 和 Istio 等，Sandall 表示，他预计可见性的提高将导致集成的进一步发展。](https://github.com/open-policy-agent)

展望未来，Sandall 表示，该项目将专注于继续强化和优化项目的核心，同时也将扩展对将 OPA 策略编译成可分发和嵌入的 WebAssembly 二进制文件的开放支持。该项目最近还与 Styra、谷歌和微软合作推出了[看门人](https://github.com/open-policy-agent/gatekeeper)子项目，该项目“将 OPA 与 Kubernetes 集成在一起，以帮助管理员执行准入控制政策并审计现有政策违规的集群”，并将提供社区用例政策的标准库，如注册表白名单或标签管理，根据该公司的声明。

云计算原生计算基金会是新堆栈的赞助商。

专题照片是一个屏幕截图，来自 CNCF 的视频。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>