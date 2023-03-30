# Nginx 与 Istio 配对以简化服务网格

> 原文：<https://thenewstack.io/nginx-pairs-istio-simplify-service-mesh/>

开源 [Nginx](https://nginx.org/en/) 高速网络服务器软件背后的 [Nginx Inc.](https://www.nginx.com/) 公司，在波特兰的 [nginx.conf](https://www.nginx.com/nginxconf/) 发布了一系列新产品，目的是扩展到容器和管理领域。

Nginx 的产品负责人 Owen Garrett 表示，目标是提供一个可配置和可管理的平台，以便在容器化的环境中使用 Nginx 作为 web 服务器、负载平衡器、HTTP 缓存和反向代理服务器。

为此，该公司正在迎合 Istio 项目，并提供 Nginx 作为入口控制器。Istio 为 Kubernetes 实例提供了一个基于云的服务网格，Nginx 的负载平衡和代理特性现在可以用来处理进入这种环境的所有流量。 [Kubernetes](/category/kubernetes/) 是 Google 开发的开源容器编排工具，现在由[云原生计算基金会](https://www.cncf.io/)管理。

谷歌的 Istio 产品管理负责人 [Varun Talwar](https://www.linkedin.com/in/varuntalwar/) 说:“Istio 项目由创新公司和开发人员组成，他们正在合作开发下一代基于服务的架构。“我们很高兴 Nginx 加入 Istio 社区，因为它是一款广泛使用、高性能和值得信赖的产品，许多 Nginx 客户希望使用 Istio 更轻松地保护、监控和管理微服务。我们欢迎他们加入社区，并期待他们为 Istio 项目做出贡献。”

“如果你设计微服务，”加勒特说，“有两种方法可以采用。第一，您可以部署一个服务总线，一次处理一个，或者您需要一个网状拓扑。你需要一个控制器来为你建立网状拓扑，建立通信。如果您在该环境中进行部署，这是一个必要的组件。我们有一个微服务参考架构，它鼓励我们的用户使用多个服务器，并在它们旁边运行代理，但我们没有构建控制平面。现在，Istio 已经做到了。”

“这是关于控制，”加勒特说。“这是为了消除设置应用程序路由的复杂性。拥有一个应用程序和多个服务是一回事，到处都有容器是另一回事，容器可以在任何时候互相对话。如果其中一个受到损害，它可以损害其他一切。在服务网格中，您可以设置相互 TLS。您可以管理相互通信的服务，服务不必知道该 IP 后面是一个还是两个服务。我们发现 Nginx 非常适合这一点。”

“Kubernetes 有入口控制器的概念，”加勒特说。入口控制器实施负载平衡规则以响应拓扑的变化。我们的[入口控制器解决方案](https://github.com/kubernetes/ingress)是 Nginx Inc .完全支持的项目。”

Garrett 说 Nginx 也提供了自己的替代者来代替 [Lyft 的特使](https://thenewstack.io/lyfts-envoy-provides-move-monolith-soa/)，这个代理包含在 Istio 中。“我们已经用 Nginx 代替了 Envoy，作为端代理运行。我们正与谷歌团队密切合作。Istio 是谷歌和 IBM 联手打造的，某种程度上还有 Lyft。”Garrett 说 Nginx 也将以正式的方式加入 Istio 项目。

## API 驱动的微服务

然而，Istio 新闻只是 Nginx 更大难题的一部分。该公司宣布了 Nginx 控制器、Nginx 单元和新的网络应用防火墙。

Garrett 说:“Nginx Controller 源于这样一个事实，即许多公司都在构建定制工具来链接业务需求，如自动扩展和更新。这是一个单一平台，可以管理配置，并从 Nginx 设备中提取数据和统计信息。Nginx 控制器可以管理大量 Nginx 设备并应用策略，例如[蓝/绿部署](https://martinfowler.com/bliki/BlueGreenDeployment.html)和更新。”

Controller 通过 2016 年末收购 Zokets 来到 Nginx。最终目标是构建一组自治功能，管理员可以在部署成熟并需要大规模操作时重用这些功能。

控制器将于 10 月开始扩展测试版测试，量产版将于 2018 年初推出。

对于[微服务](/category/microservices/)环境，Garrett 说 Nginx 单元提供了一个轻量级应用服务器，用于动态构建的容器和虚拟机。

Garrett 说，现代应用服务器不应该从过去开始使用队列。不要把应用服务器想成一个单一的、长时间运行的进程，它们应该更小，可以通过 API 配置，并且像容器一样是短暂的。

“我们所做的是重新思考作为一个应用服务器意味着什么。Nginx 单元可以支持一系列不同的应用程序运行时；PHP，Python，还有 Go。加勒特说:“我们将在未来几个月内增加 Java 和 Node.js。

“单元是通过 API 配置的持久应用服务器。所有更改都是通过对服务器进行内部重新编程来动态执行的。您可以通过 API 更改路由或权限。该单元将包括一个代理模块，作为负载平衡器，处理进出流量，并允许应用服务器与其他应用服务器建立网状网络，提供联网和发现，”Garrett 说。

“我们在应用服务器方面有很多经验，”加勒特说。“这种体验为我们与 Unit 的合作提供了信息。它是由我们的创始人伊戈尔·塞索耶夫创立的。他已经想了四年了。Unit 将是开源的，首先提供 beta 语言支持，然后是额外的语言支持和服务网状网络。”

这些额外的语言，Java 和 Node.js，将在今年晚些时候到来，而 service mesh 将在明年的某个时候到来。该单元仍然需要常规的旧 Nginx 或商业支持的 [Nginx Plus](https://www.nginx.com/products/) 来处理输入流量并增加安全性。

为了更好地帮助管理员解决安全和稳定性问题，Nginx 开始开发一种新的监控解决方案，名为 [Amplify](https://www.nginx.com/amplify/) 。这个 SaaS 监控解决方案可以聚合 Nginx 服务器生成的所有日志，并以合理的方式呈现它们。这包括图形、图表和生成报告的能力。从今天起，该服务正式全面推出，并且对前五个受监控的服务器免费。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>