# Caliptra:从芯片开始构建云安全

> 原文：<https://thenewstack.io/caliptra-building-cloud-security-from-the-chip-up/>

当您考虑云安全时，现在谁不考虑呢？—芯片级安全性甚至可能不在您的考虑范围之内。但是，也许，它应该是。将开源方法和协作引入数据中心的[开放计算项目(OCP)](https://www.opencompute.org/) 是这样认为的。在其最新的项目 [Caliptra](https://146a55aca6f00848c565-a7635525d40ac1c70300198708936b4e.ssl.cf1.rackcdn.com/images/6dadf83e9f93ca89efaf3b93ab076cea8f9ac747.pdf) 中，OCP 正在引入一个硅[信任根(RoT)](https://www.design-reuse.com/articles/47992/rot-the-foundation-of-security.html) 的开放规范。

Caliptra 在西班牙语中是“根帽”的意思，是根的最深处，是一个可重用的硅级知识产权(IP)块的开放规范。这意味着集成到片上系统(SOC)和专用集成电路(ASICs)中。Caliptra 是完全开源的，一直到寄存器传输级(RTL)。

## 可验证的加密保证

对于我们这些不是芯片制造商的人来说，这意味着它为 SOC 的安全配置和工作负载保护机制提供了可验证的加密保证。这反过来又确保了只有可信的固件才能在 SOC 上执行。因此，Caliptra 的主要工作是为 ASIC 或 SoC 的[安全配置](https://thenewstack.io/kyverno-defends-containers-against-security-configuration-errors/)提供可验证的加密保证，通过片内机制确保引导代码可信。毕竟，没有人希望看到超云 [rootkit](https://thenewstack.io/rootkits-come-to-containers-and-bring-trouble-with-them/) 攻击。

Caliptra 的主要支持者微软 Azure 表示，它将提供“[基础安全属性](https://azure.microsoft.com/en-us/blog/delivering-consistency-and-transparency-for-cloud-hardware-security/)，为机密工作负载提供更高级别的安全保护。”它将提供身份等基本安全属性；硬件安全划分；和所有可变固件所有权的验证

历史上，这是用 ROT 芯片在主板上完成的。在这些基础上，开发人员可以建立一个“信任之塔”，以确保只有正确的固件才能在他们的设备上运行。这就确保了服务器或设备只能使用正确的固件进行引导。它还为密码唯一的机器身份提供了基础；保护加密密钥等机密，并提供权威的防篡改审计记录和其他运行时安全服务。

在很大程度上，这是通过专有芯片实现的，如 [Rambus RT-600 系列](https://go.rambus.com/cryptomanager-root-of-trust)和[英特尔 FPGA PAC D5005 BMC](https://www.intel.com/content/www/us/en/docs/programmable/683811/current/bmc-introduction.html) 。不用说，还有其他解决 RoT 的开源努力。其中最著名的是[谷歌的 OpenTitan](https://opentitan.org/) 。

## 通用设计

但 OCP 决定只为超大规模云数据中心打造一个 ROT。他们还希望通用设计“不会成为供应商‘增值’的跳板。”“这样，所有主要的云供应商都可以依赖 Caliptra，而不用担心被逼入绝境。另一个原因是边缘计算业务模式和云机密性需要更高级别的安全性、互操作性和透明度。

或者，正如谷歌云副总裁、工程研究员和 OCP 董事会成员帕萨·阮冈纳赞所说，“通过 Caliptra，我们将开源开发的速度带到了基础设施安全领域，使社区能够共同强化一个强大的 IP 块，我们所有人都可以在一系列不同的芯片产品中信任它。”

[Caliptra 0.5 规格](https://www.opencompute.org/documents/caliptra-silicon-rot-services-09012022-pdf)已经上市。固件协作将与开源硬件[芯片联盟](https://chipsalliance.org/)完成。Caliptra 得到了 OCP 成员、AMD、谷歌、Nvidia 和微软的支持。然而，值得注意的是，OCP 白金会员英特尔并没有支持这个项目。

尽管如此，有谷歌和微软的支持，Caliptra 将成为基础云安全的重要基础，这一点似乎已经很清楚了。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>