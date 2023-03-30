# 机密计算向云进军

> 原文：<https://thenewstack.io/confidential-computing-makes-inroads-to-the-cloud/>

云中数据的安全性阻止了许多公司将敏感工作负载迁移到云中。但是云提供商和芯片制造商希望通过“[机密计算](https://thenewstack.io/confidential-computing-is-transforming-data-encryption-in-healthcare-finance/)”来解决这个问题

这个概念围绕着当数据在系统之间移动、在存储中静止或在服务器或云中被处理时保护数据。

## 更多安全性

云提供商和芯片制造商在每个阶段都增加了更多的安全机制，以保护数据不被窃取。这些公司正在对更多受保护的区域和安全块进行分层，以证明和验证授权用户正在访问数据和工作负载。

包括 Intel、Advanced Micro Devices、ARM 和 Nvidia 在内的所有主要芯片供应商都在为其硬件和软件产品组合添加新功能，以保护数据系统中的数据。芯片制造商的机密计算产品将主要通过来自谷歌云、微软 Azure 和[亚马逊网络服务](https://aws.amazon.com/?utm_content=inline-mention)的云提供商的虚拟机实例提供。

顶级云提供商也有自己的针对云原生软件堆栈进行调整的机密计算产品。AWS 今年通过其 [Graviton](https://thenewstack.io/aws-graviton-marks-the-emergence-of-arm-for-cloud-native-workloads/) 芯片组为其用于虚拟机产品的 Nitro V5 芯片组添加了新的安全功能。微软和谷歌分别提供 [Pluton](https://thenewstack.io/new-linux-laptops-come-with-right-to-repair-and-more/) 和 [Titan](https://thenewstack.io/google-puts-open-source-in-chip-design-and-manufacturing/) ，对访问云服务的用户进行身份验证。

## 卡利普特拉

10 月，谷歌、英伟达、AMD 和微软联手形成了一个名为 [Caliptra](https://thenewstack.io/caliptra-building-cloud-security-from-the-chip-up/) 的机密计算规范，目标是将安全保证直接引入芯片。该规范的开发将由开放计算项目管理，希望这些功能将由服务器和云提供商实现，以防止数据被盗。

该规范的部分动机是 2018 年发现的 Spectre 和 Meltdown 漏洞，这些漏洞使数据在芯片上传输时容易被窃取。Caliptra 涉及通过特殊的硅安全模块创建安全保证，确保可信的启动代码，并防止电磁攻击。Caliptra 的另一个关键特性是对代码进行认证，并验证试图访问安全区域中的应用程序的用户，这称为证明。

## 可信执行环境

微软的 Azure 云服务首席技术官 Mark Russinovich 一直是数据移动各个阶段保密计算的大力支持者。在去年的[微软 Ignite](https://news.microsoft.com/ignite-2022/) 大会上，他称机密计算为“数据保护的终极”

声明发布后，推出了面向云原生工作负载的新 Azure 虚拟机产品，这些产品在安全的弹出区域中具有不可导出的加密密钥，数据是短暂的，不会保留。这些飞地被称为[可信执行环境(TEE)](https://www.techtarget.com/searchitoperations/definition/trusted-execution-environment-TEE) ，它们更像是保存加密数据的黑匣子，被锁在一个受保护的空间内，只有授权用户才能访问。用户可以使用正确的凭证解锁数据。

安全飞地为人工智能等应用提供了多种好处，其中多个数据集可以加强学习模型。例如，银行将能够引入第三方数据集，以加强对其业务和服务至关重要的专有模型。一旦数据被合并到学习模型中，第三方数据集可以从 enclave 中移除。

Azure 机密计算产品围绕 AMD 在其 Epyc 处理器中提供的片上功能。SEV-SNP(安全加密虚拟化-安全嵌套分页)功能允许用户将代码放在作为锁的飞地内。用户可以输入代码来解锁 enclave 并访问数据。AMD 功能对虚拟机进行加密，虚拟机管理程序无法访问其中的数据。

## 走向主流

CCS Insights 的云计算、基础设施和量子首席分析师 James Sanders 表示，机密计算去年成为云计算的主流，传统基础设施供应商将在 2023 年效仿。

“AMD 的 SEV 等机密计算技术可以极大地缓解这种转变中的安全问题，”桑德斯说。

## 英特尔的举动

英特尔进军机密计算是通过一项名为 Project Amber 的基于云的产品，这是一项认证服务，可以验证计算环境中的硬件和软件资产，从而创建一个安全区域，公司可以在其上运行软件或人工智能模型。Amber 项目验证网络上代码、数据和计算端点的完整性。它将独立于云提供商，但依赖于英特尔在其芯片上提供的功能，包括 SGX(软件保护扩展)，这是其芯片上的一个安全区域，以及名为 Gramine 的 Linux 中间件，它将允许内核在 SGX 飞地运行未经修改的 Linux 应用程序。

英特尔很快也将发布其新的服务器芯片，名为 Sapphire Rapids，其中包括保密计算功能。这些芯片有新的指令，称为 TDX(信任域执行)，它可以保护虚拟机作为一个受信任的飞地。这个想法是为了防止管理虚拟机的管理程序通过加密读取虚拟机中的数据。

当与 TDX 和 SGX 联合时，琥珀计划将只允许经过验证的数据进入安全的飞地。Amber 将能够识别数据在传输到飞地的过程中是否被黑客攻击。Tirias Research 的首席分析师 Steve Leibson 说:“证明为软件机器提供了安全性，就像硅为硬件处理器提供的安全性一样。”。

## Nvidia Morpheus

Nvidia 开发了一种基于人工智能的软件栈，称为 Morpheus，可以分析用户行为以保护网络。例如，总体模型聚集了网络上的用户行为。随着时间的推移，人工智能可以为用户建立一种行为模式。如果人工智能发现了违反模型的异常行为，这可能是异常的登录类型，它会向安全操作发出警报，然后安全操作可以对问题进行分类。

“Morpheus 提供了新的工具来做更多的事情，如日志解析，并作为另一层安全措施向安全分析师提供更好的可见性，”Nvidia 企业和边缘计算业务副总裁兼总经理[贾斯汀·博伊塔诺](https://www.linkedin.com/in/justinboitano/)说。

## ARM、HPE 和戴尔

ARM 今年对机密计算有重大计划。ARM 在其芯片设计中创建了一个专用的机密计算架构，具有一个称为动态“领域”的功能。该技术用“安全井”隔离不同环境中的特定程序和数据，防止黑客访问数据。ARM 将在未来两年内发布硬件和软件数据，以便芯片制造商可以创建硬件，软件制造商可以编写代码。

机密计算的交付将主要通过云服务进行，但传统的基础设施提供商将在混合云模型中采用机密计算，以满足喜欢控制自己的 IT 基础设施的客户的需求。

HPE 的 GreenLake multicloud 产品和戴尔的 APEX 产品可以改进面向单租户的“即服务”模式，以采用保密的计算功能，但这可能需要大量的工作。

CCS Insights 的 Sanders 表示:“数据中心运营商和 MSP 将从提供给企业客户的相同技术和财务模式中受益，尽管要让这种多租户服务于这些新客户群，将需要大量的软件开发工作来确保安全连续性。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>