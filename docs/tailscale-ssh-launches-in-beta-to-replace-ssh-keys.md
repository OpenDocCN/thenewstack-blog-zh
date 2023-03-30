# Tailscale SSH 测试版发布，取代 SSH 密钥

> 原文：<https://thenewstack.io/tailscale-ssh-launches-in-beta-to-replace-ssh-keys/>

[Tailscale](https://tailscale.com/) ，这是一家生产设备互联和安全软件的公司，推出了 [Tailscale SSH](https://tailscale.com/tailscale-ssh/) 的测试版，通过用任何机器的 Tailscale 身份替换 SSH 密钥，简化了认证和授权。

安全外壳或 SSH 密钥是 [SSH 协议](https://www.ssh.com/ssh/protocol/)中的访问凭证。其功能类似于用户名和密码，但根据 SSH.COM 的说法，密钥主要用于自动化过程以及系统管理员和超级用户实现单点登录。

Tailscale 为每个服务器和用户设备提供了自己的身份和节点密钥，用于认证和加密 Tailscale 网络连接，并使用代码中定义的访问控制列表来授权连接，这使它成为 Tailscale 现在管理网络中 SSH 连接访问的自然扩展。

### 消除痛苦

Tailscale 产品经理 [Maya Kaczorowski](https://www.linkedin.com/in/mayakaczorowski/) 在一份声明中说:“SSH 是开发人员的日常工具，但管理服务器的 SSH 密钥并不那么简单或安全。“SSH 密钥很难保护，管理起来也很耗时。使用 SSH 密钥保护您的网络连接需要管理员花费大量资源来管理、供应或取消供应用户访问。Tailscale SSH 通过 Tailscale 为虚拟专用网提供的同样强大的简单性，消除了 SSH 密钥管理的痛苦。”

Tailscale SSH 使您能够在 Tailscale 网络中的设备之间建立 SSH 连接，正如您的访问控制所授权的那样，而无需管理 SSH 密钥，并使用 [WireGuard](https://www.wireguard.com/) 验证您的 SSH 连接，Tailscale 的联合创始人 [Brad Fitzpatrick](https://www.linkedin.com/in/bradfitz/) 在 Kaczorowski 与同为 Tailscale 开发人员的 [Maisem Ali](https://twitter.com/maisem_ali) 和 [Ross Zurowski](https://twitter.com/rosszurowski) 合著的[博客文章](https://tailscale.com/blog/tailscale-ssh/)中说道。

据该公司称，使用 Tailscale SSH，用户可以从运行 Tailscale 的 iPad 安全地编写代码，跨操作系统到 Linux 工作站，而不必考虑如何将他们的 SSH 私钥放到他们的 iPad 上。此外，该公司表示，企业 Tailscale 客户将减少 SSH 密钥管理或 bastion jump boxes 上的流失和资源，并避免将内存不安全的服务器暴露于开放的互联网的风险。

## 有什么不同？

Tailscale 与其他 SSH 解决方案有什么不同？

“当你在一个设备上启用 Tailscale SSH 时，Tailscale 要求端口 22 用于任何进入该设备的流量到它的 Tailscale IP 地址——也就是说，只用于通过 Tailscale 的流量，”博客帖子说。“该流量被重新路由到 Tailscale 守护程序内的 SSH 服务，而不是标准的 SSH 服务器。当您通过 Tailscale 网络创建一个从客户端到该服务器的新 SSH 连接时，服务器已经知道远程方是谁并接管，并且不需要 SSH 客户端提供进一步的证明。”

Tailscale SSH beta 提供身份验证和加密、单点登录和多因素身份验证以保护 SSH 连接、内置密钥轮换、重新验证 SSH 连接的能力、轻松撤销 SSH 访问的能力、以代码形式管理权限的能力、通过点对点连接减少延迟的能力，以及轻松添加新用户或服务器的能力。

“Tailscale 是我一生中最好的用户体验，”Twilio 的高级首席工程师兼分布式系统专家 Kris Nóva 在一份声明中说。Nova 使用 Tailscale 在她位于纽约的家庭实验室和冰岛的数据中心之间创建了一个专用网络。

“我在 tailnet 上运行了一个 Kubernetes 1.24 集群，eBPF CNI 网络位于 tail net 之上，它将我在家里的私有子网连接起来，穿过北冰洋，连接到冰岛一个火山供电的数据中心的私有子网，”她说。“它的易用性和强大功能让我大吃一惊…”

## 就像旧的 GitHub

与此同时，在[的一条推特](https://twitter.com/maddox/status/1539709811725590533) , [Jon Maddox](https://jonmaddox.com/) ，提供[频道](https://getchannels.com/)直播电视和 DVR 服务的 Fancy Bits 的联合创始人说:

“Tailscale ( [@Tailscale](https://twitter.com/Tailscale) )是唯一一个让我想起早期 [@github](https://twitter.com/github) 的组合。用不可思议的软件创造令人惊奇的、有用的、需要的体验。”

Maddox 在 GitHub 工作了八年，并加入了另一位前 GitHub-er， [Aman Karmani](https://twitter.com/tmm1?lang=en) ，创建了一些有趣的网站和频道。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>