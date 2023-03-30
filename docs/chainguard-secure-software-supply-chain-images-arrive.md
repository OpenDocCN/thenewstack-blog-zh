# Chainguard 安全软件供应链图像到达

> 原文：<https://thenewstack.io/chainguard-secure-software-supply-chain-images-arrive/>

谈论保护软件供应链很容易。诀窍是实际去做。现在，[链家](https://chainguard.dev/)，新[零信安全](https://thenewstack.io/zero-trust-security-and-the-software-development-lifecycle/)公司，为了让软件供应链默认安全，发布了[链家图片](https://blog.chainguard.dev/announcing-chainguard-images/)。

Chainguard 映像是为安全软件供应链设计的基于容器的映像。他们通过向开发人员和用户提供持续更新的基本容器映像来做到这一点，这些映像具有零已知漏洞。

这些图片基于 Chainguard 的[开源发行版图片项目](https://github.com/distroless)。这些是基于 [Alpine Linux](https://www.alpinelinux.org/) 和 [Busybox](https://busybox.net/) 的最小 Linux 映像。通过削减除绝对必要的软件元素之外的所有软件元素，Chainguard 映像具有最小的可能攻击面。

虽然这些开源图像没有 Chainguard 的保证，但它们会不断更新，并尽可能保持最基本的内容。这些对于不需要支持和保证的开源项目和组织来说是完美的。或者，只是给这种方法一个尝试，然后再投入商业链卫队的形象。

## 基于开源项目

Chainguard 图像是使用其开源项目 [apko](https://blog.chainguard.dev/introducing-apko-bringing-distroless-nirvana-to-alpine-linux/) 和 [melange](https://github.com/chainguard-dev/melange) 构建的。这些工具利用 Android Package (apk)生态系统，通过完整的软件材料清单(SBOM)来提供声明性的、可复制的构建。这些图像还支持针对漏洞信息的行业标准[开源漏洞(OSV)模式](https://ossf.github.io/osv-schema/)。

人们以前曾试图提供干净的图像，但很难做到。为了完成这一壮举，链卫队使用自己的第一个产品，[链卫队执行](https://www.chainguard.dev/chainguard-enforce)。具体而言，Enforce 的证据湖提供了集装箱化程序组件的实时资产清单。反过来，证据湖是基于开源的 Sigstore 项目。它通过为程序元素创建数字签名来保护软件供应链。

## 轻松的漏洞管理

在此基础上，Chainguard 建立了他们所谓的“无痛漏洞管理”

这是一个手动管理的漏洞源。然后，该公司将资金投入到它所说的地方。Chainguard 为其映像提供服务级别协议(SLA)。他们保证为新的漏洞提供补丁或缓解措施。您不必一直监控安全披露。Chainguard 为他们的图像这样做，所以你不必。

所有护链图像都带有签名。它们还包括一个签名的 SBOM。签名和出处可以通过 Sigstore 进行追踪和验证。这些签名和签名信息保存在公共的 [Rekor 透明性](https://docs.sigstore.dev/rekor/overview)日志中。

该公司还为政府机构提供符合联邦信息处理标准(FIPS)的图像变体。FIPS 验证即将到来。

这些图像也是为了达到软件产品的高[供应链水平(SLSA)](https://slsa.dev/) 评级而设计的。作为其中的一部分，护链图像意味着“完全再现性”也就是说，Chainguard 解释说，“任何给定的图像都可以从源按位重新创建。”

## 成交！

至少有一位顾客已经购买了 Chainguard 的新产品。[安全 CTO 办公室的 HPE 研究工程师蒂姆·普莱彻](https://www.linkedin.com/in/tim-pletcher-2a41ba5b/)说，“我们对积极策划的基础容器映像发行版的前景感到兴奋，它有可能让 HPE 进一步增强我们客户的软件供应链完整性。”

最后，为了让这一切发生并让它持续到未来，Chainguard 还筹集了 5000 万美元的首轮融资。这是由红杉资本和许多其他风险投资家和天使投资者领导的。换句话说，无论是在技术上还是在经济上，Chainguard 映像都将在保护云本地计算世界方面发挥重要作用。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>