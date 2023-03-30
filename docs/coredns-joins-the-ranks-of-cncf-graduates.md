# CoreDNS 加入 CNCF 大学毕业生的行列

> 原文：<https://thenewstack.io/coredns-joins-the-ranks-of-cncf-graduates/>

DNS 服务器 [CoreDNS](https://coredns.io/) 三年前创建，一年后[将](/cncf-host-coredns-boosting-big-tent-service-discovery/)纳入[云本地计算基金会](https://www.cncf.io/) (CNCF)的孵化项目，已经走过了漫长的道路。上个月，CoreDNS 被[命名为 Kubernetes](/kubernetes-team-pushes-toward-shorter-release-cycles-with-1-13-release/) 的默认 DNS，现在 CNCF 宣布，该项目将于 2019 年第一年作为 CNCF 毕业生加入 Kubernetes 、 [Prometheus](https://prometheus.io/) 和[特使](https://www.envoyproxy.io/)的行列。CoreDNS 将在成为 CNCF 的孵化项目一周年之际毕业。

CNCF 根据成熟度的三级递进来孵化项目，首先从沙箱开始，然后进入孵化阶段，最后毕业。[毕业的标准](https://github.com/cncf/toc/blob/master/process/graduation_criteria.adoc)包括许多资格，例如“至少来自两个组织的委托人”，这表明如果单个个人或公司退出，项目不会失败，但也意味着有更多的资格来帮助确保项目未来的成功。

一份 CNCF 声明详细说明了该项目的进一步资格，其中不仅包括基本要求，如采用 CNCF 行为准则，还包括各种其他成熟信号。为此，它引用了 CoreDNS 的“100 多个贡献者、16 个活跃的维护者和许多在 Kubernetes 内外的生产中使用它的组织——包括 Bose、Hellofresh、Skyscanner、SoundCloud、Trainline 和 Zalando。”除此之外，基于 GoLang 的 DNS 服务号称“去年发布了 12 个版本，现在有 35 个内置插件和 15 个外部插件，其中几个是为 Kubernetes 社区开发的。”

CoreDNS 的联合维护者 Michael Grosser 在声明中说:“CoreDNS 项目和社区已经走过了漫长的道路，成为 CNCF 的一个巨大的里程碑。“从公开 Prometheus metrics 的简单 DNS 服务器，到内置巨大灵活性的成熟 DNS 解决方案。成为大多数 Kubernetes 集群中的核心组件，为用户带来更多的稳定性和灵活性，让我们对支持 CoreDNS 的 awesome 社区充满信心。”

CNCF 还指出，“在构建 CoreDNS 时，社区考虑到了其他 DNS 服务器的局限性，以创建一个通用的 DNS 服务器，可以与多个后端对话，如 etcd、Consul 和 Kubernetes。”正如我们[在 2017 年 CNCF 首次采用 CoreDNS](/cncf-host-coredns-boosting-big-tent-service-discovery/) 时所写的那样，该项目诞生于“一个想法，即掏空一个名为 [Caddy](https://caddyserver.com/) 的网络服务器的内部，并使其响应服务发现的复杂请求。”服务发现也是 Prometheus 的一个关键特性，这是 CNCF 孵化的最后一个项目，也是“过去庞大的、集中的面向服务的模型和今天敏捷的、轻量级的系统之间的关键区别”

根据 CoreDNS 维护者 Francois Tur 的说法，Kubernetes 用户对 CoreDNS 的选择是显而易见的，特别是它最近被指定为默认状态。

Tur 在一封电子邮件中写道:“只有两个公认的 DNS 服务器可以作为 Kubernetes 的集群 DNS:由 Kubernetes 社区开发的传统 kube-DNS 和现在的 CoreDNS。后者完全支持 IPv6，autopath 是一种优化 DNS 流量的方法，有几个协议支持向上游转发非 kubernetes 请求，[以及]在服务迁移期间添加您自己的记录或重写域的能力。"

Tur 还对该项目的下一步提供了一些见解，包括其“通过为 DNS 服务器添加重要功能来增加 CoreDNS 的功能集”的努力，如“递归解析器插件”和“基于 Go-like 表达式语言的 ACL-like 插件，但[它]也允许与远程策略引擎协作。”

云计算原生计算基金会是新堆栈的赞助商。

通过 Pixabay 的特征图像。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>