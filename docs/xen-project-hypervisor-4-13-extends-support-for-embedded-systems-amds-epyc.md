# Xen Project Hypervisor 4.13 扩展了对嵌入式系统的支持，AMD 的 EPYC

> 原文：<https://thenewstack.io/xen-project-hypervisor-4-13-extends-support-for-embedded-systems-amds-epyc/>

Xen 项目正在发布其开源 Xen 项目管理程序的最新版本。这个版本 4.13 带来了新的安全性和嵌入式特性，以及对新硬件平台的支持。版本 4.13 反映了来自社区和生态系统的广泛贡献。这个版本也代表了 Xen 长期发展方向的一个根本性转变，即更好地抵御来自旁路攻击和硬件相关问题的安全威胁。

Xen 项目顾问委员会主席 [Lars Kurth](https://twitter.com/lars_kurth) 表示:“除了我们正在增加的重要功能，包括核心调度、后期 uCoding 加载、实时补丁和对 OP-TEE 的支持以及对 [Dom0less](https://xenproject.org/2019/12/16/true-static-partitioning-with-xen-dom0-less/) 的改进，我们的社区正在为 Xen 的全功能和更容易通过安全认证的平台奠定基础。”

至于新功能的具体情况，我们来看看。

## 安全性

4.13 版本提供了大量安全更新，有助于防御硬件漏洞。主要更新包括:

*   核心调度是一项实验性技术，允许 Xen 将虚拟 cup 分组到虚拟核心中，然后在物理核心上调度这些虚拟核心。
*   通过后期 uCode 编码运行时安装 uCode 更新。这将避免系统重新启动，否则可能是必要的。
*   实时补丁改进。
*   使用 Spectre v1 进行分支硬化以减少攻击面。

虚拟内核和物理内核之间的切换是同步的，不会有虚拟内核的虚拟 CPU 同时在物理内核上运行。目前，核心调度不允许用户重新启用超线程。但是，这种包含被认为是未来提供改进的安全性能的关键。

## 嵌入式和安全关键型

在 4.13 版本中，有一些新特性旨在为嵌入式和安全关键用例(如 ASIL-B 和 ISO 2626)提供更轻松的采用。主要功能和更新包括:

*   无 Dom0less Xen 的扩展范围和改进的可用性。
*   支持瑞萨面向基于 Arm 的第三代 R-Car SOC 的 VMSA 兼容 IO-MMU。
*   支持 [OP-TEE](https://www.op-tee.org/) ，支持所有访客在 Arm 的 TrustZone 上并发运行可信应用。

除了这些新特性，Xen 项目社区还创建了一个新的功能安全工作组(由众多供应商支持)，使供应商能够使用 Xen 项目软件，使其与 [ASIL-B 要求](https://www.safetty.net/tt-design-examples/iso-26262-asil-b-ecu)兼容。这将要求所有代码和开发过程符合 ISO 2626(由国际标准化组织定义的生产汽车中电气和/或电子系统功能安全的国际标准)的关键原则，这还需要通过任何开源项目来解决。

## 新硬件平台支持

Xen 4.1 包括对许多新硬件平台的支持，例如:

*   AMD 第二代 EPYC ( [代号罗马](https://www.datacenterknowledge.com/amd/amd-unleashes-its-second-epyc-assault-intel-s-data-center-reign))。
*   Hygon Dhyana 18h 处理器。
*   树莓 Pi4。
*   英特尔 AVX512。

对 AMD EPYC 处理器的支持为 Xen 用户提供了额外的选择，有助于降低成本，同时提高性能和安全性。AMD 公司副总裁兼数据中心生态系统和应用工程首席技术官 Raghu Nambiar 在介绍该产品时说:“运行在 AMD EPYC 处理器支持的服务器上的基于 Xen 4.13 的虚拟机管理程序非常适合许多不同的工作负载，并有助于为客户提供有吸引力的总拥有成本。特别是，VDI 性能测试的结果展示了 Xen 在 AMD EPYC 处理器上的强大功能。”

来自 Pixabay 的 S. Hermann & F. Richter 的特写图片。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>