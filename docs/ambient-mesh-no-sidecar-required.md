# 环境网格:不需要边车

> 原文：<https://thenewstack.io/ambient-mesh-no-sidecar-required/>

西雅图——在 [Cloud Native Security Con](https://www.cncf.io/blog/2023/01/04/cloudnativesecuritycon-north-america-2023-5-sessions-you-dont-want-to-miss/) 上，我们与 [Solo.io 的](https://solo.io?utm_content=inline-mention) [Marino Wijay](https://www.linkedin.com/in/mwijay) 和[Jim Barton](https://www.linkedin.com/in/jameshbarton/)一起参加了新堆栈制造商播客的“在路上”一集，他们讨论了[服务网格技术](https://thenewstack.io/service-mesh/)是如何成熟的，特别是现在 Solo 与谷歌一起开发的[环境网格](https://istio.io/latest/blog/2022/introducing-ambient-mesh/)中的 sidecars 已经被移除。

[https://www.youtube.com/embed/AVQ0d6C5gAk](https://www.youtube.com/embed/AVQ0d6C5gAk)

视频

Ambient Mesh 是“一种新的代理架构，根据 Solo.io 网站的说法，”将代理移动到节点级别，用于 [mTLS](https://www.cloudflare.com/learning/access-management/what-is-mutual-tls/) 和身份。它还允许策略执行策略来管理第 7 层安全过滤器和策略。

[环境网格:不需要边车](https://thenewstack.simplecast.com/episodes/ambient-mesh-no-sidecar-required)

为 Solo 做开发者关系和宣传的 Wijay 说，sidecar 是一个迷你代理，一个迷你防火墙，就像一个多功能路由器。边车接收来自上游控制平面的指令。

“现在，对于不同的工作负载和不同的通信模式，我们开始意识到的一件事是，并非所有这些工作负载都需要边车或可以利用边车，”Wijay 说。"有些最好不用边车."

## 安全网日趋成熟

Solo 的现场工程师 Barton 说，环境网格反映了服务网格的成熟度以及第 1 天和第 2 天操作之间的差异。

巴顿说:“第一天的运营主要是理解概念、帮助开发人员、初始配置等等。“社区真的更加关注，环境网格是第二天关注点的一个很好的例子。

“我如何衡量这一点？我如何让它在大型环境中运行？我如何跨群集、多个区域的多个分区中的群集扩展这一点，诸如此类？这些都是我们目前真正看到的最重要的举措。”

随着服务网格的成熟，用户也随之而来。Barton 说，在安全的背景下，这意味着开发者安全操作人员。连接服务不是开发人员的工作。他们的工作是构建服务。

巴顿说:“平台运营商或 DevSecOps 工程师有责任创建一个基础平台或基础，用于部署服务，然后在此基础上提供安全性。”

然后，工程师们必须对其进行配置并仔细考虑，他补充道:“我如何知道谁在做什么，谁在和谁说话，这样我就可以开始形成我的[零信任](https://thenewstack.io/what-is-zero-trust-security/)姿态？”

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>