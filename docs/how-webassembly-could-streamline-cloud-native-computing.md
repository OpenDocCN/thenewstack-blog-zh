# WebAssembly 如何简化云本地计算

> 原文：<https://thenewstack.io/how-webassembly-could-streamline-cloud-native-computing/>

作为一个小型、快速、安全、跨平台的字节码， [WebAssembly](https://webassembly.org/) 应该是云原生模式的理想选择。 [Docker](https://www.docker.com/) 创始人 [Solomon Hykes](https://twitter.com/solomonstre)

但是由于 [WASM](https://thenewstack.io/what-is-webassembly/) 给了你一个二进制的而不是完整的环境，除非你把整个环境移入 WebAssembly 模块，否则它不是容器的替代品。这是一种在你想要的地方运行任意代码的方式，具有最少的开销和最少的(已知的)安全问题。

这非常适合在 Kubernetes 工作负载需要的地方嵌入第三方代码。例如，特使代理(通常用于 Kubernetes 中的网络路由和负载平衡)已经使用 WebAssembly 作为编写过滤器的方式，开放策略代理策略规则可以在 WASM 编写，Kubewarden [将 WebAssembly 模块用于许可策略](https://thenewstack.io/wasm-modules-and-envoy-extensibility-explained-part-1/)。

换句话说，不要再说“WASM 是集装箱的尽头”开始说“WASM 加集装箱”

## **Kubernetes 帮助 WebAssembly**

如果您认为云原生流程是您在需要时从 API 创建的，当您需要更多容量时纵向扩展，当您不需要时删除它们，WASM 是运行这些流程的绝佳方式。但是你仍然需要一个环境来运行它们。Cosmonic 首席执行官 Liam Randall 将 WebAssembly 比作一个虚拟的、潜在的通用 CPU，因为它充当了一个通用的编译目标，但指出“那里没有虚拟的操作系统。”

除非它们嵌入到另一个工作负载中，如 Envoy filters，或者在 Cloudflare Workers 等环境中用作无服务器功能，否则您需要一个 orchestrator 来协调它们。风险投资公司 [Amplify Partners](https://amplifypartners.com/) 的负责人 Renee Shah 指出:“对于服务器端的 WASM 来说，时间安排和协调仍然是一个开放的领域。

目前还没有专门针对 WASM 的调度和编排系统，从头开发这些系统而不是与现有选项集成可能没有意义。Kubernetes (K8s)当然不是编排云流程的唯一选择，但它是如此众所周知和广泛采用，以至于考虑将它与 WebAssembly 一起使用是合乎逻辑的。

有了 [Krustlet](https://krustlet.dev/) ，它现在是[云本地计算基金会](https://cncf.io/?utm_content=inline-mention)的[沙盒项目](https://deislabs.io/posts/towards-krustlet-v1-cncf/)，Kubernetes 可以本地编排 WebAssembly 运行时。Krustlets 是用 Rust 写的 Kubernetes Kubelets。当 Kubernetes API 将 pod 调度到 Krustlet 上时，Krustlet 在 WASM 运行时运行它们；在同一个集群中运行的 WebAssembly 和 container 工作负载可以相互通信，并使用 secrets、volume mounts 和 init containers 等功能与集群的其余部分进行交互。

## 

微软团队构建容器和 WebAssembly 技术(如 Helm、Draft 和 Krustlet)的负责人 Matt Butcher 告诉新的堆栈，Kubernetes 是 WebAssembly 的“隐藏宝石”,因为它不仅带来了调度，还带来了其他关键服务。

> WebAssembly 运行时的启动时间在 10 毫秒的范围内，相比之下，容器的启动时间为几秒钟(虚拟机的启动时间为几分钟)，这使得它非常适合无服务器，而且适合伸缩。

Kubernetes”还带来了存储层，这是一个非常大的问题；您希望能够移动您的工作负载，您希望确保它可以连接到正确的存储，无论它在哪里，这将是一个由我们自己编写的庞大项目，”Butcher 说。“Kubernetes 在那个领域已经成熟。秘密管理，网络层；就像得到一堆赠品。这里有个问题我不用担心，因为 Kubernetes 会做。这是让 Krustlet 成为如此棒的启动体验的原因之一，因为我们可以从非常基础的配置到非常有趣的配置，因为我们只需连接到 Kubernetes，而不用编写自己的实现。”

WebAssembly 也可以利用其他容器构造；有了 WAGI，[web assembly Gateway Interface](https://github.com/deislabs/wagi)作为构建编译成 WASM 的 HTTP 处理程序的变通方法，你可以从 OCI 注册中心引用和拉取模块。(Kubewarden 和 Krustlet 也利用 OCI 工件通过 [OCI 注册中心](https://github.com/engineerd/wasm-to-oci)分发 WASM 模块)。

Shah 指出:“WebAssembly 和 containers 的好处在于，它们都在打破铁板一块的趋势上发挥作用。“如果一家公司已经在使用微服务，那么添加由 WebAssembly 支持的新服务相对简单。”有了 Krustlet，他们可以在 Kubernetes 并肩奔跑。

## **更好、更快、更小:WASM 帮助库伯内特**

有很多领域 WASM 将是有用的，而 Kubernetes 将是不相关的，尽管其中一些可能需要另一个管弦乐队。但是也有 Kubernetes 的场景，WASM 将显著改进，因此 WebAssembly 可能成为 Kubernetes 的一个常见工作负载——同样，不需要替换容器。

WebAssembly 不是将整个应用程序编译成一个模块，而不是一个容器；您正在创建一个二进制文件，这非常符合云的原生原则，即代码只做一件事，而且做得很好。在 Kubernetes 中运行的 WASM 模块可以承担一些容器是唯一选择但不太适合的任务，但在大多数情况下，这些 WASM“荚”将做以前不可能做的新工作，也许在新的地方。

Butcher 告诉新堆栈，Kubernetes 中的 WASM 将特别适合需要高密度、快速可用性和可伸缩性的场景，或者在资源有限的情况下运行。正确保护 Kubernetes 和容器的默认运行时配置也需要做大量的工作。容器不是安全边界；WebAssembly 在防止代码溢出方面做得更多。WASM 沙箱的安全性和“默认拒绝”的方式 WASM 模块需要任何功能的显式权限在这里有明显的优势。

WebAssembly 运行时的启动时间在 10 毫秒的范围内，相比之下，容器的启动时间为几秒钟(虚拟机的启动时间为几分钟)，这使得它非常适合无服务器，而且适合伸缩。

Butcher 说:“当您想要处理一个工作负载，并说‘好吧，最多给我 5 个实例，这还不够，最多给我 15 个实例’，您会立即获得规模和非常高的吞吐量。他指出，这对于扩展到零也很有用(尽管名称如此，由于冷启动的延迟，通常不会扩展到一个实例以下)。“拥有一台服务器并等待他人使用是要花钱的。我们能否让它看起来总是可用的，但仅仅是因为它启动得如此之快，以至于最终用户在他们请求之前根本意识不到该进程正在运行？”

人们非常重视减小容器的大小，但是对于内存和存储有限或处理能力极低的边缘环境来说，容器通常太大了。运行 2MB WebAssembly 模块而不是 25MB Docker 容器意味着 Kubernetes 可以在更多的环境中管理工作负载(可能使用 K8s 的最小化版本，如 K3s 或 Kind)。

这可以显著提高工作负载密度，这可能会减少云账单，Butcher 指出:“有一个老笑话，云服务实际上只是支付别人的电费，密度的提高意味着成本的降低。”

但是 edge 更加异构的计算环境可能是 WASM 和 Kubernetes 合并的最大机会，这可能意味着“云”超越了超大规模数据中心。

“我们一直认为集群是生活在数据中心的东西，我们已经将它们部署为生活在数据中心的东西，”Butcher 说。这可能是 Azure 上的 AKS 或裸机服务器上的 Kubernetes，但它仍然是一个数据中心。“Krustlet 为我们解决了我们无法用 Kubernetes 和 containers 解决的问题，那就是我们需要能够将 Kubernetes 集群扩展到数据中心之外，扩展到越来越有异国情调的设备上，”他说。

支持 Arm 芯片是其中的一大部分，但物联网设备中使用的微控制器、许多硬件 AI 加速选项和异构 CPU 也是如此，甚至[英特尔](https://www.intel.com/)现在也在生产异构 CPU。“我们有奇特的架构，我们有新兴的架构，我们想要一个跨平台、跨架构的故事，我们想要一个跨操作系统的故事，”Butcher 说。

Cosmonic 公司的兰德尔附和了这一观点。“CPU 的多样性使得容器给生态系统带来的限制更加明显，”他说。“在 CI/CD 世界中。如果您必须针对数十或数百个不同的 CPU，您需要数十或数百个特定的 CPU 映像。”此外，他指出，“许多小型设备将永远无法运行 Linux。”

“WebAssembly 带来的是我们放弃了为单个 CPU 构建的假设，因为 WebAssembly 只是一个编译目标，我们可以将现有的代码和应用程序带入其中。”

## **边缘——但是实验性的**

因为模块可以在许多不同的设备上运行，而不需要重新编译，Butcher 建议 WebAssembly 提供“编写一次，在任何地方运行”的承诺，这是 Java 所熟悉的，但“以一种真正适合云原生开发的形式”

由于像 [Akri](https://github.com/deislabs/akri) 这样的项目，这可能是非常多样化的 Kubernetes 环境的一部分，这些项目将物联网和其他设备(从 IP 摄像头到现场可编程门阵列)作为资源连接到 Kubernetes 集群。“如果我们能够让集群从数据中心向外扩展到其他地方的不同设备，这不是很棒吗？”屠夫问。“如果我有一个存在于我的手机、笔记本电脑和任何离我最近的设备上的群集，并且当我靠近时，它们会加入和离开该群集，这不是很酷吗？”

最近，Akri 和 Krustlet 团队一直在尝试将 Akri 编译到 WASM，这样它就可以使用 [Krustlet、](https://github.com/deislabs/akri-on-krustlet)部署到 Kubernetes 集群中，这使得它对于 edge 来说更小更快。

然而，这取决于 WASI 提供 WASM 缺乏的虚拟操作系统原语，而 WASI 仍在崛起，需要做大量工作才能在网络等关键领域发挥作用。“WASI 规范仍然没有解决客户端网络接入问题；这总是一个通过宿主运行时来处理所有事情的问题。它没有解决一些基本的图书馆问题，”Butcher 指出。

分析公司 [Gartner](http://gartner.com) 的高级分析师 Fintan Ryan 告诉新的堆栈，“WASI 需要超越实验阶段，以实现任何重大的采用。”虽然它们还在开发中，但是这些健壮的 API 仍然需要 6 到 12 个月的时间。

Butcher 说，当它们真的到来时，将需要建立更多的工具，并在 WebAssembly 和 Kubernetes 生态系统之间完成更多的集成工作。“当我们的 WebAssembly 模块可以打开一千个服务器套接字并监听它们时，会是什么样子？Kubernetes 将如何连接它，让它有一千条路线进入 WebAssembly 模块？”

与此同时，他建议，“WAGI 和 Krustlet 之类的东西给了我们一个很好的方法，让人们走进门来，看看今天的技术，希望对它感到兴奋，有自己的想法，并开始他们自己的 GitHub 仓库和创业公司和工作组。”

他希望让人们兴奋的方式之一可能会引起一些强烈的反应:Krustlet 的 WAGI 提供商，他说，“将会给你一个快速、简单的开发体验来构建应用程序——我不骗你，1996 年风格的 CGI——因为这项技术坚如磐石，宇宙中的每个人都支持它！

“这是我们今天可以采取的一个步骤，让这项技术出现在人们面前，这样他们就可以在其上构建微服务的小应用程序。”

## **WASM 加库伯内特的可能性**

WASM 可以让 Kubernetes 的开发者体验像 Docker 和 containers 一样简单，Butcher 希望:“我想要一个漂亮的快速工作流，在那里我可以编写一个应用程序，然后在后台的某个地方，它被部署到某个地方，就像运行 Krustlet 的 Kubernetes 集群一样。”

他说，构建容器可能很容易，但部署、测试和与同事共享测试环境则更令人担忧。“这仍然有点慢，而且有一些粗糙的边缘，我们希望 WebAssembly 也能够平滑其中的一些。”

Cosmonic 的 [wasmCloud](https://wasmcloud.com/) ，[现在是一个 CNCF 沙盒项目](https://thenewstack.io/cncf-welcomes-webassembly-based-wasmcloud-as-a-sandbox-project/)，也旨在改善开发人员和体验，并且在一些场景中也依赖于 Krustlet，尽管它有自己的运行时，而不是字节码联盟的 Wasmtime 运行时。

“Kubernetes 和 WebAssembly 的结合使得如果你想将 wasmCloud 放入多个云上的一组 Kubernetes 服务器中，并让它们相互对话，”Randall 说。一个客户，一家大型欧洲银行，正在尝试使用它从一个云 Kubernetes 服务故障转移到另一个云 Kubernetes 服务，以便在其云提供商之一停机时保持可用性。

微服务中也有一些基本模式，WebAssembly 中的未来特性可能会对其进行改进。

“典型的微服务包括每个开发人员建立自己的 HTTP 服务器，并编写 JSON 来实现对象序列化，”Butcher 指出。在每个微服务中，总共有大约一千行样板代码需要编写、测试、保护和更新。web assembly[nano process model](https://bytecodealliance.org/articles/1-year-update)将 HTTP 层和序列化/反序列化放在 WASM 运行时中。

“当两个模块碰巧在同一个运行时相邻时，它们就直接通信，”他说。“但是当它们在网络上传播时，主机运行时会处理两者之间的流量，开发人员不必维护它。而且安全模式很棒，因为你不用每次 OpenSSL 有 bug 就更新每一段代码。”

那还有一段时间。“我们可能还需要一年的时间才能真正开始解决这个问题，”Butcher 指出。“如果我们解决了这个问题，我们将能够构建一个全新的应用程序类别。”

这仍然是一个“如果”,有很多移动的部分。“纳米过程被认为比 WASI 更具实验性，”Ryan 警告说。

“希望是巨大的，要实现这一目标，工作量也是巨大的。”

尽管 WebAssembly 和 Kubernetes 的前景并不遥远。Kubernetes 越来越重要的另一个异构、资源受限的领域，尤其是使用 Kubeflow 这样的工具，WebAssembly 可以带来显著收益的领域:机器学习。

WASI 不仅仅提供存储和网络等底层操作系统接口；它还可以为类似神经网络的东西提供高级接口。经过训练的机器学习模型必须在各种设备上运行，具有特定于平台的运行时，并使用不同的专业硬件加速器。因为它是平台独立的，WASM 将简化部署， [WASI-nn](https://github.com/WebAssembly/wasi-nn) 接口将让 WebAssembly 与多个机器学习运行时对话，如 ONNX、OpenVINO、PyTorch 和 TensorFlow。

“机器学习是 WebAssembly 可能足够安全的另一个领域，但在堆栈中足够低，比容器更容易与硬件集成，”Butcher 建议道。

“我们将 WebAssembly 视为容器难以完成的一些琐碎部分的粘合层，我们可能能够通过 WebAssembly 更容易地完成这些部分，然后将容器生态系统与一些更难的部分结合起来，比如说，硬件管理或部署机器学习算法。

“我认为这是你开始真正了解容器和 WebAssembly 如何互补的地方。”

[https://www.youtube.com/embed/Qu1CEdbLDRs?feature=oembed](https://www.youtube.com/embed/Qu1CEdbLDRs?feature=oembed)

视频

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>