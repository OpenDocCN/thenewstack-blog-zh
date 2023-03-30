# ScaleFT 的零信任平台:用于访问管理的自适应结构

> 原文：<https://thenewstack.io/scaleft-brings-zero-trust-access-management/>

2014 年，在遭到中国政府黑客攻击四年后，谷歌发表了一篇论文，概述了他们为应对攻击而开发的安全技术。

这篇名为 [BeyondCorp](https://cloud.google.com/beyondcorp/) 的论文详细介绍了谷歌新的安全策略。根据 BeyondCorp 的说法，谷歌将访问控制从网络转移到了用户身上，并且不需要虚拟专用网络(VPN)。谷歌的网络安全方法强调系统对用户和设备的了解。它不信任用户从哪个网络登录。它不允许全面获得服务。一切都必须经过“认证、授权和加密”

BeyondCorp 有一个明确的使命，声明“让每个谷歌员工在不使用 VPN 的情况下，在不受信任的网络上成功工作。”VPN 不太爱。它们反映了企业使用防火墙作为保护基础设施的历史趋势。但是正如有据可查的那样，当黑客突破边界进入公司内部网时，这种方法会带来一些实际问题。移动和云技术使网络变得更加漏洞百出，这导致人们对使用 VPN 的传统安全做法产生了更大的怀疑。

Rackspace 的一个团队发现，他们采取了与谷歌类似的方法。该团队包括 [ScaleFT](https://www.scaleft.com/) 的创始人，该公司现在是旧金山的一家初创公司，已经建立了一个跨服务器和应用程序的可编程和实时的零信任平台。该系统适应可能与导致黑客攻击企图的自动动作相关联的变化。例如，如果有来自未知位置的登录，该服务可能会触发用户重新认证。

“我们的团队还认为边界是错误的方法，因为有更多的移动设备、更多的远程工作人员和更多的云应用程序。ScaleFT 产品营销副总裁 Ivan Dwyer 说:“把东西带到网络上不再有效。

ScaleFT 最近推出了 Access Fabric 的预发布计划，这是其零信任访问管理平台的核心。该平台既包括服务器保护，又包括员工的 web 访问，无论他们是在办公室工作还是远程访问公司资产，服务器保护由短暂的客户端证书提供支持，客户端证书对每个请求的范围和时间都有限制。

Dwyer 解释说，它将控制放在应用层，而不是网络层。

微边界位于特定数据或资产周围，因此可以实施更精细的规则。随着网络被单独视为传输，认证和授权成为更加独立的服务。访问控制成为一个全球分布式系统，能够做出非常快速的决策。

**无默认信任**

Forrester Research 创造了术语“[零信任](http://www.darkreading.com/attacks-breaches/zero-trust-the-way-forward-in-cybersecurity/a/d-id/1327827)”，意思是对任何用户、设备、应用程序或数据包都没有默认的信任——每次都必须实时进行身份验证和授权。

Forrester 副总裁兼首席分析师 John Kindervag 在 Dark Reading 上解释说，这是通过一个严格的微粒度安全模型实现的，该模型将安全性与单个工作负载联系起来，并自动配置策略。

这种方法可以防止恶意参与者突破边界，然后在网络中横向移动。

据 Kindervag 称，它涉及实时检查所有流量，并结合取证、数据包捕获、元数据分析和网络发现流量分析等工具，以不妨碍员工工作流程的方式快速提供访问。

在一份关于 2015 年人事管理办公室违规的事后报告中，众议院监督和政府改革委员会建议联邦机构采用零信任模型。

## 分布式、快速

前 Rackers [Robert Chiniquy](https://github.com/robert-chiniquy) ， [Russell Haering](https://github.com/russellhaering) ， [Jason Luce](https://www.linkedin.com/in/lucejason/) ， [Paul Querna](https://github.com/pquerna) 在 2015 年创立了 ScaleFT，发现他们的方法与 BeyondCorp 的方法非常相似。

德怀尔说，零信任平台的关键要素是它必须很快，员工必须喜欢它，否则他们会想办法绕过它。这就是 ScaleFT 专注于最大限度减少延迟和提升用户体验的原因。

它通过服务器上的代理与身份提供商合作，如 Google、Okta、Active Directory 或 LDAP(轻量级目录访问协议)。拥有 BYOD 政策的公司将需要要求员工在他们的设备上使用一个小应用程序，该应用程序与平台通信并收集基本状态和属性的数据。他说，这不是端点监控，而是设备和时间的状态。

[https://www.youtube.com/embed/8bgRQObwgxQ?feature=oembed](https://www.youtube.com/embed/8bgRQObwgxQ?feature=oembed)

视频

在一篇[博客文章](https://www.scaleft.com/blog/how-we-built-an-access-fabric-to-eliminate-vpns/)中，首席技术官[保罗·奎尔纳](https://github.com/pquerna)将接入结构描述为一个全球分布式、低延迟、认证、授权、加密和连接代理引擎。

它建立在 [Apache Kafka](https://kafka.apache.org/) 、 [Go 编程语言](https://golang.org/)和 [gRPC](https://grpc.io/) 、跨语言和平台工作的远程过程调用框架之上。

从各种来源收集设备状态、用户属性、会话数据和访问策略等数据，然后实时传输到分布在全球的授权引擎。

ScaleFT 使用机器和用户的身份通过访问网关对会话进行身份验证，访问网关充当用户、设备和他或她想要访问的资源之间的中介。在做出授权决策时，它会强制执行该资源的访问策略。

如果访问被拒绝，用户将被重定向到补救助手服务，这清楚地解释了原因。Dwyer 说，事情可能很简单，只需要将设备更新到最新的操作系统，并强调减少员工的挫折感是首要任务。

## 基于策略

Dwyer 指出，因为它涉及到与特定资产相关的公司安全政策，所以它不是一个现成的解决方案。

正如 Kindervag 指出的，它涉及到识别关键资产和绘制数据如何围绕它们流动。然后，公司需要编写具体的策略，并确定如何在分段网关上最好地实施访问控制和检查策略。

“这确实始于一个政策框架。你如何在你的公司里执行规则？你可能会说，为了访问公司的 wiki，所有员工都必须拥有最新版本的操作系统。或者每个人都必须打开防火墙。你可以观察员工或承包商如何访问内部资源，并据此制定政策，”德怀尔说。

ScaleFT 在这些方面与客户合作，并建议客户找到一个特定的用例，如服务器访问或承包商访问，作为起点。

亚历克斯·威廉姆斯为这个故事做出了贡献。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>