# Immunio 的应用程序-安全开发的安全工具

> 原文：<https://thenewstack.io/immunios-app-security-tool-aims-stop-attacks-tracks/>

应用安全初创公司 Immunio 宣布其应用安全即服务解决方案正式上市，该解决方案旨在实时检测和阻止攻击。

Gartner 最初将这种细分市场称为运行时应用程序自我保护(RASP)。

在 Aberdeen Group 的一份报告中，分析师 Derek Brink 将 RASP 称为一个新兴类别，随着企业的应用程序组合变得越来越复杂和笨拙，企业应该考虑这个类别。

> “如今的安全模式是快速发现漏洞并快速修复漏洞。而这些事情都不会很快发生，”Immunio 的联合创始人兼首席执行官扎伊德·阿尔·哈萨米说。

查找 bug 需要很长时间，大多数组织都有修复 bug 的积压工作。

Immunio 库提供了将安全性构建到应用程序本身的能力，没有锁定和代码集成。据该公司称，它提供主动保护，对企图攻击的实时可见性，并且易于安装。

“它不需要任何安全专家来部署或使用它——团队中的任何开发人员或 DevOps 人员都可以部署和管理它，”他说。

“实际的保护发生在运行时你的应用程序内部，没有任何东西离开你的网站，”他说。发送到云中的唯一信息是仪表板的元数据。

经过大约八个月的测试，Al Hamami 指出了几个教训:

> “我们了解到，互联网上的几乎所有应用程序都受到了攻击。如果你是安全资产，你每天都在遭受攻击。如果你不能回答这些问题，我会受到攻击吗？被谁？他们有多老练？–那么在如何管理你的网络应用程序方面就有一个很大的盲点，”他说。

他说，虽然网络和服务器监控工具相对成熟，但应用层的监控却缺乏同样的成熟度。

另一个问题是，组织可能知道他们的应用程序中的漏洞，但无法修复它们。

“一个[客户]在网络上有大约七个应用程序在为流量服务，这些应用程序运行的是旧的、已知易受攻击的框架版本，但升级这些框架需要几个月的时间。在 Immunio 之前，他们的选择是接受风险，不做任何事情，或者花钱做所需的工作，这将需要几个月的时间，并使我们的主要业务目标偏离轨道。Immunio 的价值在于立即消除风险——不一定是通过修复漏洞，而是消除这些应用程序被利用的可能性，”他说。

Immunio 的工作原理是在应用程序内部部署传感器，当应用程序被锁定时发出警报。例如，如果您的代码有一个 SQL 注入漏洞，Immunio 会知道 SQL 语句在正常情况下应该是什么样子，然后可以检测到带有 SQL 注入迹象的异常请求。SQL 查询将被阻止进入您的数据库，Immunio 将开始报告该攻击者的活动。

据该公司称，它可以检测 SQL 注入、跨站脚本、远程命令执行攻击以及其他攻击。

目前为止，Immunio 支持 Ruby on Rails、Python 和 Java，并计划添加 PHP、。Al Hamami 说。它提供免费试用的服务。

总部位于蒙特利尔的 Immunio 成立于 2013 年，已经筹集了 270 万美元的资金。它在四月份从秘密状态中显露出来。Venture Beat 最近将其列为 14 家最有前途的种子期创业公司之一。

虽然 Al Hamami 指出 [Prevoty](https://www.prevoty.com/) 是其主要竞争对手，但应用安全领域的其他公司包括 [Shape Security](https://www.shapesecurity.com/) 、 [whiteCryption](http://www.whitecryption.com/) 、 [Waratek](http://www.waratek.com/) 、 [CheckMarx](https://www.checkmarx.com/) 和 [HP Application Defender](http://www8.hp.com/us/en/software-solutions/appdefender-application-self-protection/) 。

然而， [RASP 解决方案可能会带来意想不到的后果](http://www.channelworld.in/features/the-unintended-consequences-of-a-rasp-focused-application-security-strategy)，应用安全供应商 Soha Systems 的副总裁 Mark Carrizosa 在 Channel World 的一篇文章中说道。

他说，其中，开发人员可以在试图满足关键期限的同时，让安全编码最佳实践溜走，认为 RASP 技术会发现问题；停止攻击可能会导致停机，这可能会对 SLA 产生严重影响，并导致收入损失；这项技术可能会增加应用程序的延迟。

Immunio 的 RASP 产品在概念上类似于 Prevoty 和惠普的 Application Defender，但只专注于 Ruby on Rails 和 Python 应用程序，位于西班牙的 Continuum Security 公司的创始人兼首席技术官 Stephen de Vries 指出，该公司提供自己的应用程序安全技术。

“与更传统的 web 应用程序防火墙相比，易于使用和安装将是有吸引力的卖点，传统的 web 应用程序防火墙通常是外部设备，维护起来可能很复杂，特别是(对于)频繁修改代码的应用程序来说，”他告诉新的堆栈。

他说，对于还没有成熟的安全开发方法的开发团队来说，Immunio 的产品将是一个有吸引力的选择，因为它可以帮助防止某些类别的漏洞被利用。

> “与所有 RASP 产品一样，它只对当前 OWASP(开放 Web 应用程序安全项目)十大列表中列出的 10 类漏洞中的大约 5 类有效，因此它绝对不应该被视为解决所有安全问题的灵丹妙药，”他说。

他说，与其他 RASP 技术一样，它被设计为在生产中运行，所以尚未回答的问题之一是嵌入式传感器对性能有多大影响。

“但作为时间紧张的开发团队的补充工具，它可以证明对注入和跨站点脚本漏洞非常有效，这些漏洞今天仍然困扰着许多应用程序。”

专题图片: [NIAID](https://www.flickr.com/photos/niaid/) 的[耐甲氧西林金黄色葡萄球菌(MRSA)细菌](https://www.flickr.com/photos/niaid/5927204872/in/photolist-a2Ltvs-qYNLZD-y7P4q2-dQorNR-opdGHH-6Z431r-9Vc5f2-r3mKZ2-kDRH-4QfPgY-c9v3mj-pVCjgF-9djCHD-oUqw4E-gVmfP7-6Ltnyu-4QfP11-4QfPSo-4Qbzne-4ZkqzR-9JMuyQ-9JJF78-9JMu9q-9JJETF-9JJENc-9JJEHe-9JMtM3-9JJEzg-9JJEqp-9JJEjc-9JJEdK-9JMtgj-9JJE48-9JJDYv-jMJGGZ-jMKud6-jMLXyC-jMJFnz-jMLWxj-jMJEEx-jMJEpx-jMKrZt-jMKruF-jMLUW3-jMKqZT-jMLUyQ-eUkRdv-e8B5tr-a4NU78-c9uRwQ)在 [CC 下获得 2.0](https://creativecommons.org/licenses/by/2.0/) 的许可。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>