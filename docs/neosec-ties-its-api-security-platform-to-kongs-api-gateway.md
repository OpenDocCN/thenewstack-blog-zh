# Neosec 将其 API 安全平台与 Kong 的 API 网关绑定

> 原文：<https://thenewstack.io/neosec-ties-its-api-security-platform-to-kongs-api-gateway/>

今年早些时候， [Neosec](https://www.neosec.com/?utm_campaign=Kong%20Partnership&utm_source=press%20release) ，一个编程安全新人，从秘密行动中走了出来。他们的任务？Neosec 首席执行官 [Giora Engel](https://www.linkedin.com/in/giorae/) 表示，采用一种完全不同的方法来保护应用和应用编程接口(API)的安全，无需签名、预先确定的漏洞数据库或内部部署。

它是怎么做到的？通过自动查找所有 API，维护它们的完整清单，然后自动为以前未知的 API 生成缺失的文档。凭借这些数据，Neosec 对 API 的风险态势进行了审计。然后，它识别那些传输敏感数据的人，揭示现有 API 文档和 API 参数之间的任何差异。根据 Engel 的说法，通过自动学习每个 API 的基线行为，Neosec 可以标记易受攻击或配置错误的 API。

## 发现有问题的 API

现在，发现有问题的 API 并不新鲜。像[诺名安防](https://nonamesecurity.com/)、[盐安](https://salt.security/)、[溯源](https://www.traceable.ai/)等公司，使用签名已经做了一段时间了。但是根据 Neosec 的说法，他们不做的是检查这些 API 实际上在做什么。他们的基本假设是已知的 API 是安全的。也许是真的，也许不是。

正如[42 crunch](https://www.linkedin.com/in/colindomoney/)的 API 安全研究员 Colin Domoney 最近在 [The New Stack](https://thenewstack.io/) 中指出的，使用静态应用程序安全测试(SAST)和动态应用程序安全测试 [(DAST)的现有 API 安全测试根本无法正确处理 API 问题](https://thenewstack.io/application-security-tools-are-not-up-to-the-job-of-api-security/)。因此，我们需要向左移动并测试每个单独的 API。Neosec 就是这样一种方法。

它通过长期观察您的应用程序如何使用它们的 API 来做到这一点。在分析了 30 天的 API 数据集后，程序获得了基线行为的一个线索。这种行为分析方法用于为每个 API 构建动态行为配置文件。这样，您的安全团队和开发人员可以通过了解您的程序中 API 的上下文来做出更好的决策。这反过来又防止了滥用和数据泄露。

## 孔合伙企业

现在，Neosec 与[孔合作。](https://konghq.com/?utm_source=pressrelease&utm_medium=referral&utm_campaign=neosec-partnership)将其 API 安全平台与他们的[孔网关](https://konghq.com/kong/?utm_source=pressrelease&utm_medium=referral&utm_campaign=neosec-partnership)集成。Neosec 声称，这为您提供了“管理和保护 API 和微服务的完整企业级解决方案。Kong 提供世界上最受欢迎的 API 网关，专为微服务和分布式架构优化的混合、多云环境而构建。Neosec 使 Kong 客户能够轻松获得企业 API 安全能力，以保护其关键业务流程。”

Neosec 会持续观察旧 API 的使用情况以及新 API 的更新情况。它还监控他们的虐待行为。然后，与 Kong API 网关协作，它们自动将特定消费者实体上的条件响应编排到 Kong API 网关中。

“随着越来越多的企业采用数字化转型计划并公开 API，业务流程的核心方面正日益面临风险。Engel 说:“在现代环境中，API security 不仅可以为安全团队创建警报以供评估，还必须与现有的 API 技术一起创建自动响应。“我们与孔的战略合作伙伴关系实现了这些平台。”

看来他们会合作得很好。Kong Gateway 提供了一种出色的方法来管理部署和使用 API 的复杂性，而 Neosec 平台则通过 API 发现、风险评估和人工智能驱动的行为分析、检测和响应来增强安全态势。

然后，当安全事件出现时(这种情况经常发生)，Neosec 集成会自动在 Kong Gateway 中创建安全策略，并实现自动响应。

Kong Gateway 提供 API 认证、授权、日志、流量控制、缓存和管理。就 Neosec 而言，它从 cdn、web 应用防火墙和 API 网关等流行技术中获取访问日志。Neosec 平台支持 API 发现，并自动标记其中有意义的异常行为。这种结合使企业能够在不改变生产流水线的情况下最大限度地降低风险。

## API 攻击呈上升趋势

Kong 的产品副总裁 [Reza Shafii](https://www.linkedin.com/in/rezashafii/) 表示:“随着公司越来越依赖于开放基础设施，并将应用程序、系统和数据相互连接，以及与客户和合作伙伴连接，API 暴露的风险不断攀升。

沙菲没有错。根据 Gartner [网上研讨会](https://www.gartner.com/en/webinars/4002323/api-security-protect-your-apis-from-attacks-and-data-breaches)预测，明年，也就是 2022 年，API 攻击将成为针对企业 web 应用的最常见攻击。我们越依赖 API，它们就越容易被攻击。

你明天可能用不到 Neosec。但我可以有把握地说，如果你很聪明，你正在构建和运行云原生应用，你将在明年使用它或类似的东西。另一种选择是在未来一两年内出现严重的安全漏洞。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>