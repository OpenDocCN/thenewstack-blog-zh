# Ubuntu 20.04 LTS 获得 FIPS 140-2 安全认证

> 原文：<https://thenewstack.io/ubuntu-20-04-lts-earns-fips-140-2-security-certification/>

[Canonical](https://canonical.com/) ， [Ubuntu Linux](https://ubuntu.com/) 的母公司，声称是私有云和公共云上最流行的操作系统。他们有理由自夸。在上次云市场对云操作系统的最新分析中，Ubuntu 在[亚马逊弹性计算云(EC2)](http://aws.amazon.com/ec2/) Linux 市场份额数字中占据主导地位。众所周知，[亚马逊网络服务](https://aws.amazon.com/?utm_content=inline-mention)，[拥有公共云市场](https://www.gartner.com/en/newsroom/press-releases/2021-06-28-gartner-says-worldwide-iaas-public-cloud-services-market-grew-40-7-percent-in-2020)的 40.8%，据 [Gartner](https://www.gartner.com/en) 称，拥有公共云的最大份额。现在，随着 FIPS 140-2 加密模块的一级认证，Ubuntu 似乎注定会获得更多的客户。

为什么？因为 FIPS 140-2，对于那些对安全性不感兴趣或没有追求过政府合同的人来说，是一个[NIST 国家标准与技术研究所](https://www.nist.gov/)的软件和硬件加密模块标准。如果您想向使用安全数据的美国联邦政府部门和机构或其承包商销售服务或服务器，您必须拥有 FIPS 认证。所有这些都是使用 FIPS 140 验证加密技术运行工作负载所必需的。

许多其他政府也需要 FIPS。在公共部门之外，数据安全受到严格监管的行业也采用了这种方法，如金融服务(PCI-DSS)和医疗保健(HIPAA)。

现在，[1 级是最低的安全级别。](https://nvlpubs.nist.gov/nistpubs/FIPS/NIST.FIPS.140-2.pdf)表示加密模块的基本安全要求已经满足。满足这一标准的操作系统适用于低级别的安全应用程序，即使不存在其他安全控制，如物理安全、网络安全和管理程序。

听起来可能不多，但确实如此。获得 FIPS 140-2 认证至少需要 6 到 9 个月的时间。如果在测试过程中有任何失败，那就太糟糕了。你必须从头再来。绝大多数用户只需要 FIPS 140-2 1 级安全性。

具体来说，Ubuntu 已经在 [Ubuntu 20.04 LTS](https://releases.ubuntu.com/20.04/) 获得了 FIPS 140-2，Level 1 认证，包括 [OpenSSL 1.1.1](https://www.openssl.org/news/openssl-1.1.1-notes.html) 。该认证建立在 Canonical 在设计 Ubuntu 以实现高安全性和受监管的工作负载方面的良好记录以及通过认证测试的基础上。

为了获得 FIPS 地位，NIST 和第三方实验室不仅仅是测试代码。他们只测试被认可的硬件和 Ubuntu 的组合。这意味着你需要一个 [Ubuntu Pro](https://ubuntu.com/aws/pro) 或 [Ubuntu Advantage](https://ubuntu.com/advantage) 账户来获得 FIPS 140 认证加密包。Ubuntu Pro 和 Ubuntu Advantage 软件包在常见的 CPU 类型上经过验证，也可在带有 Ubuntu Pro FIPS 的[公共云](https://ubuntu.com/public-cloud)上使用。没有硬件许可，这些包本身不符合 FIPS 140 标准。

当然，您可以自己完成，但是符合 FIPS140 是一项具有挑战性的任务。验证加密涉及一个漫长而昂贵的过程，需要加密专业知识，并涉及第三方实验室和 NIST 的审查。所有这些都带来了成本和复杂性，可能会推迟你的上市。因此，对于几乎所有的软件开发人员来说，如果您想按时交付并减少验证成本和时间，使用 Ubuntu 验证的标准开源包更有意义。

Canonical 的安全产品经理 Nikos Mavrogiannopoulos 博士在一份声明中表示，“通过新的 FIPS 140-2 验证，我们可以继续满足政府、金融和医疗保健客户的安全要求，实施最安全的开源软件来支持他们的基础设施。”

作为开发人员或公司所有者，这一切对您来说意味着，如果您想为注重安全性的客户部署解决方案，这款新的 FIPS 140 认可的 Ubuntu Linux 可能正是您所需要的。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>