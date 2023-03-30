# Scarf 旨在通过 Scarf Gateway 锁定软件包管理器

> 原文：<https://thenewstack.io/scarf-takes-aim-at-package-manager-lock-in-with-scarf-gateway/>

本周从 stealth 崛起的初创公司 Scarf 希望帮助开源开发者衡量他们的软件使用情况，并与他们的商业最终用户联系，他们正在通过推出 [Scarf Gateway](https://about.scarf.sh/scarf-gateway) 的公开测试版来实现这一目标。

对于大多数开源维护者来说，项目使用统计的范围可以局限于下载数量和像 GitHub stars 这样的公众流行度指标。虽然这可以作为吹嘘的权利，但它并不能告知维护者他们的项目是如何或在哪里被使用的，并且当问题和议题滚滚而来时，你会惊讶地发现你的软件被跨国公司所依赖，而不仅仅是像你这样的个人开发者。

Scarf Gateway 实际上瞄准了这个中心思想，同时也试图解决开源项目面临的另一个问题，即与包管理器打交道时的锁定问题。Scarf Gateway 为独立于主机注册表的软件包提供了一个安全的中央访问点，因此从 Docker Hub 切换到 GitHub Container Registry 是一个不间断的变化，不涉及任何停机时间或最终用户的工作。

“如果另一家提供商进入市场，仅仅转换一下，把你所有的用户都转移过来，这不一定是小事一桩。比那要复杂得多。这是我们真正要解决的问题。它本质上只是一个非常薄的重定向层，位于你的注册表前面，允许你使用自己的域来托管你的容器，”在一次采访中， [Scarf](https://scarf.sh/) 联合创始人兼首席执行官 [Avi Press](https://www.linkedin.com/in/avi-press-4437a356/) 解释道。

“有了 Scarf，项目就能提供那个 URL，并有效地将你从注册中分离出来。您可以任意多次切换注册表。用户再也不会受到这种变化的影响。因为 Scarf 是第一个被点击并重定向或代理到最终注册中心的东西，所以我们可以向维护者提供所有这些数据。”

[https://www.youtube.com/embed/KyX1_cBvmCA?feature=oembed](https://www.youtube.com/embed/KyX1_cBvmCA?feature=oembed)

视频

虽然收集这种数据的想法听起来像是一项潜在的风险业务，但 Press 保证不会收集个人身份信息(PII)，并且 Scarf Gateway 确保不会违反通用数据保护条例(GDPR)等法规，这些法规可能会很快使问题复杂化。相反，Scarf Gateway 收集诸如唯一安装、客户端容器运行时信息、包版本、粗粒度位置、设备和操作系统信息等信息，以及通常任何其他可能有用的元数据，同时确保丢弃 PII。

“我们正努力让维护人员真正做到这一点。普雷斯说:“想要了解你的软件是如何被使用的，这不应该是一件禁忌的事情，因为在我们的世界里，银行、医院和核电站都在运行开源软件，在它们的堆栈上上下下。“当关键基础设施位于软件之上时，编写软件的人根本不知道发生了什么，这种情况越来越成问题。理想情况下，维护人员可以提前发现问题，并主动解决它们，而不是等待人们来使用 GitHub。地球上技术最成熟的人现在利用调查来了解这一点，这真的很疯狂。”

在发布时，Scarf Gateway 将可用于 Docker 容器，但 Press 表示，该公司期待在不久的将来添加其他包类型，如 Java 和 Python。

虽然发布的时间是偶然的，随着[最近围绕 Docker Hub 和图像拉速率限制的问题](https://thenewstack.io/docker-hub-limits-what-they-are-and-how-to-route-around-them/)，Press 表示该功能已经工作了六个多月，是客户请求的直接结果。

对于担心将他们的包注册信息转移到 Scarf 只是一种不同形式的锁定的用户，Press 指出，该公司计划在 Scarf Gateway 正式上市后将其作为开源软件发布，尽管他也指出这些收集信息的附加功能是使用 Scarf 的原因。

在当前功能集下使用 Scarf Gateway 是免费的，并将继续免费，未来还将提供额外的付费功能，如服务水平协议和与 Segment 等商业智能工具的集成。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>