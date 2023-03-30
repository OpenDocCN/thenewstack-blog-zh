# 实时 Ubuntu 现在已经普遍可用

> 原文：<https://thenewstack.io/real-time-ubuntu-is-now-generally-available/>

[Canonical](https://canonical.com/),[Ubuntu Linux](https://ubuntu.com/)的制造商宣布了 Ubuntu 22.04 LTS 实时版本的可用性，该版本旨在为有时间限制的工作负载带来端到端的安全性。

这个版本的 Ubuntu 的特别之处在于发行版中包含的实时内核。据 Canonical 首席执行官[马克·舒托沃尔斯](https://www.linkedin.com/in/mark-shuttleworth/?originalSubdomain=im)称，“实时 Ubuntu 内核为软件定义的制造、监控和运营技术提供了工业级的性能和弹性。”

## 实时内核

这不是标准的[实时](https://thenewstack.io/hazelcast-and-the-benefits-of-real-time-data/)内核，它是为许多特定的低延迟工作负载(比如音频和视频制作)而创建的。相反，这种实时内核已经针对工业、电信、汽车、航空航天和国防部门的低延迟要求进行了优化。借助该内核，企业业务可以可靠地为时间敏感型应用开发应用，如机器人、自动化、工业 PC、人机界面和其他工业 4.0 工作负载和用例。

实时 Ubuntu 中的实时内核基于 5.15 内核，并为 X86 和 ARM 架构添加了树外 PREEMPT_RT 补丁，以减少内核延迟并确保时间可预测的任务执行。这个内核适用于所有的 Ubuntu 版本，并且有两个部署选项:

Arm 开源软件副总裁 Mark Hambleton 表示:“Arm 上实时 Ubuntu 的商业可用性展示了开源协作的力量，并有利于整个 Arm 生态系统，从云到边缘。”Hambleton 继续说道:“从软件定义的车辆和智能工业 4.0 工厂到 5G vRAN 功能和基于 Arm 的高能效超大规模数据中心，Canonical 正在实现 Arm 上的未来计算。”

实时 Ubuntu 不仅能实现低延迟性能，还能节省成本。通过利用 Canonical 在新版本和实时内核方面的专业知识，它将减少内部提供的修复、安全补丁和平台测试，这些都是成本高昂的。不必为低延迟工作负载和增强的安全性配置 Ubuntu 服务器，公司可以相信实时 Ubuntu 已经考虑到了这些事情。为此，Canonical 首席技术官 [Arno Van Huyssteen](https://www.linkedin.com/in/arno-van-huyssteen-37a0a61/) 表示，内部提供修复程序、安全补丁、内核模块集成和操作系统平台测试对于组织来说成本过高，因此利用 Canonical 的专业知识和支持可确保客户实现其业务目标，同时从开源采用战略中实现经济效益和投资回报。"

## 入门指南

当然，要利用实时 Ubuntu，你必须注册并启用 [Ubuntu Pro](https://thenewstack.io/what-is-ubuntu-pro-and-how-can-you-use-it/) 。一旦你注册了 Ubuntu Pro，你必须从你的订阅中领取一个令牌。为此，打开您的 [Ubuntu Pro Dashboard](https://ubuntu.com/pro/dashboard) ，并在您的订阅下复制令牌。

有了令牌后，登录到您的 Ubuntu Server 实例，使用以下命令安装 Ubuntu Advantage 包:

*sudo apt-get 安装 Ubuntu-advantage-tools = XXX ~ $(LSB _ release-RS). 1*

其中 XXX 是最新的稳定版本，可以在[这里](https://launchpad.net/ubuntu/+source/ubuntu-advantage-tools)找到。

使用以下命令验证安装:

*专业安全-状态*

使用以下命令将服务器连接到您的 Ubuntu Pro 帐户:

*sudo pro 附加令牌*

其中 TOKEN 是之前复制的 Ubuntu Pro token。

最后，使用以下命令启用实时内核:

*sudo pro 启用实时内核*

系统会提示您禁用 Livepatch，以便启用实时内核。之后，重新启动机器，实时内核应该在机器上启动并运行。

## 企业级

NVIDIA 企业和边缘人工智能副总裁 Justin Boitano 谈到新的 Ubuntu 选项时说:“我们很高兴看到实时 Ubuntu，这是一个企业级的 Linux 操作系统，将加速这些市场的发展。”

Canonical 确实为个人和小规模商业用途提供了免费的 Ubuntu Pro。对于较大的企业业务，将需要一个专业订阅，以获得实时 Ubuntu 的好处。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>