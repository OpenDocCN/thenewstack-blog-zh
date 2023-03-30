# CoreDNS 为微服务时代提供快速 DNS 服务

> 原文：<https://thenewstack.io/coredns-offers-a-speedy-dns-service-for-the-microservices-era/>

CoreDNS 是一个 DNS 服务器，最初是作为 [Caddy](https://caddyserver.com) webserver 的一个分支出现的，它以一种方式链接中间件，每个中间件实现一些 DNS 特性。这是[米克·吉本](https://github.com/miekg)的项目，他也[写了一本关于编程语言 Go](https://miek.nl/go/learninggo) 的书。

这个项目——CoreDNS-002 刚刚发布——实际上始于 Gieben 参与的 [SkyDNS](https://blog.gopheracademy.com/skydns/) ，这是一个返回位置信息的 DNS 服务。他说他构建了 SkyDNS 版本 2，作为一个建立在分布式键值存储 [etcd](https://thenewstack.io/about-etcd-the-distributed-key-value-store-used-for-kubernetes-googles-cluster-container-manager/) 之上的瘦 DNS 层，尽管它很受欢迎，但很明显它已经达到了极限。必须对它的内部结构做些什么，但他不知道是什么。

在对 Linux 基金会的[让我们为他的网站加密](https://letsencrypt.org/)证书中的自动证书管理环境(ACME)客户端感到沮丧之后，他找到了 Caddy，他认为这可能是构建服务器的一个好方法。

“它所做的每一件‘事情’都包含在一个你可以链接在一起的中间件中，例如，压缩一个网页只是在你在磁盘上找到一个页面后调用 zip 中间件的事情。它非常像 Unix，”Gieben 解释说。

“这让我再次想起了 SkyDNS2。也许我可以使用这种中间件方法来使 SkyDNS 分层。所以我分叉了 Caddy，把所有出现的“http”替换成了“dns”。"

Gieben 说，与依赖单一后端的竞争对手不同，CoreDNS 可以使用任何后端，只要有一个中间件让它连接。

[英特尔的尼克·韦弗讨论编排](https://thenewstack.simplecast.com/episodes/intels-nick-weaver-discusses-orchestration)

CoreDNS 可用于从文件而非 etcd 提供服务、代理请求、重写请求、对端点进行健康检查以及将指标发布到 [Prometheus](https://prometheus.io/) 中。

网络智能供应商 [Infoblox](https://www.infoblox.com/) 正在帮助 Kubernetes 整合，他还有其他个人贡献者参与 Gieben 的一个附带项目。

在 Kubernetes [一篇关于支持标准接口的博客文章](http://blog.kubernetes.io/2016/09/cloud-native-application-interfaces.html)中，谷歌的[布莱安·葛兰特](https://github.com/bgrant0607)和前谷歌人[克雷格·麦克卢奇](https://twitter.com/cmcluck)提到 [CoreDNS](https://coredns.io/) 在云原生 DNS 实现中显示出了希望。

## 更有活力

Gieben 说，在 DNS 层面上,“云”DNS 和“常规”DNS 没有区别。

“这主要归结为云 DNS 在本质上更加动态，这意味着动态后端，如数据库或键值存储，如 etcd，客户端可以存储发现信息，然后由 CoreDNS 传播。他解释说:“这些信息的生命周期([TTL](http://archive.oreilly.com/pub/a/wireless/2002/10/17/peap.html))通常很短，以秒计，而常规 DNS 的 TTL 值可能是几天或几周。

另一件事是,“常规”DNS 主要处理 IP 地址——A(IP v4)和 AAAA (IPv6)记录——“云”DNS 使用既有地址又有端口号的 SRV 记录。

仍在开发中且非常稳定的 SkyDNS 仍然是其竞争对手之一，像 [Consul](https://www.consul.io/intro/vs/skydns.html) 、 [Mesos-DNS](https://mesosphere.github.io/mesos-dns/) 等也是如此。

为什么有人会在内置的 DNS 服务上使用 CoreDNS，例如 kube-dns 和 SkyDNS 的组合(这是最近关于 CoreDNS 的一个问题)。

首先，kube-dns 的部署和维护更加复杂，尤其是对于服务发现这样的任务。该软件使用 [dnsmasq](http://www.thekelleys.org.uk/dnsmasq/doc.html) 来缓存答案，因为 SkyDNS 对缓存的支持有限。相比之下，CoreDNS 只是将缓存作为一个中间件，所以您可以放弃对 dnsmasq 的依赖。

为什么不是 DNS 本身呢？尽管它有很多缺点，但它已经为互联网服务了几十年。

吉本在电子邮件中说:“总有一类应用程序你不能这么做。”。“但你说得对。目前，DNS(ab)用于服务发现，可能是时候考虑更好的服务发现协议了——可能是推送通知？DNS 缺少的东西。另一方面，只要使用像 DNS 这样古老的东西，就能保证你的软件栈支持它。”

Gieben 表示，短期目标是能够在 Kubernetes 中取代基于 SkyDNS2 的 kube-dns。“我们正在努力实现所有需要的功能，”他说。

之后，他希望专注于使 DNSSEC ( 域名系统安全扩展)，一个安全的 DNS 扩展，尽可能容易地自动密钥滚动和密钥上传到注册服务商，以及使其成为一个稳定和快速的 DNS 服务器，具有 DNS 防火墙，DNS 路由和查询镜像。

“我也希望人们能提交完整的中间件，这些中间件实现了我从未想过的很酷的东西，”他说。

专题图片:[探索湾](https://www.flickr.com/photos/paintballphotos/17106805329/in/photolist-s4ERet-9kJpdt-dT3ct2-rpixsk-siPRym-s4EVS6-s4wgBd-s4wSxf-s4xzrm-s4uEEG-sm7BVT-skXSTU-rp5TFd-s4w25Y-rp7KPh-siNMQw-rphhqP-sm5SQM-s4xKU5-bDvDmL-siQbkQ-s4wiEd-rp5NmW-sm3DB2-sm5G8k-rphVY4-s2LWAZ-s4w6Ej-siNx2U-bDvC11-rp6b4y-skVPg7-siN31s-rphtAe-gaKLDA-bDvBQL-s2L2t6-bWUb9k-bSqmfV-siPuLj-gaL3Hj-skW3BL-s4xQ1w-s4E2cM-rp73AL-skXd1d-s2KQCZ-sm3UpP-s2KxQk-sm4XL6)作者[卡特布朗](https://www.flickr.com/photos/paintballphotos/)，授权**CC BY-SA 2.0。**

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>