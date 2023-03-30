# 超越 API 安全测试:运行时保护

> 原文：<https://thenewstack.io/beyond-api-security-testing-runtime-protection/>

针对 API 的攻击呈上升趋势。根据 [Salt Security](https://www.darkreading.com/application-security/concerns-over-api-security-grow-as-attacks-increase) 的数据，2020 年，91%的组织至少遭遇了一次涉及其 API 的安全问题。超过一半(54%)的受访者表示，他们在生产 API 中发现了一个漏洞。略少一些(46%)的人说他们发现了一个问题，攻击者可能利用这个问题试图篡改他们的身份验证方案，从而获得对敏感数据的访问权。

## API 安全测试拯救世界

 [大卫·比松

David Bisson 是一名信息安全作家和安全迷。他是 IBM 的 Security Intelligence 和 Tripwire 的 State of Security 博客的特约编辑，也是 Bora 的特约撰稿人。他还定期为 Zix 和数字安全领域的许多其他公司撰写书面内容。](https://twitter.com/DMBisson) 

组织可以使用 API 安全测试来帮助解决上面讨论的问题。 [Linux 杂志](https://linuxnetmag.com/benefits-of-api-security-testing/)指出，API 安全测试包括检查 API 的对象级授权是否被破坏，以及由[开放 Web 应用安全项目](https://owasp.org/www-project-api-security/) (OWASP) API Top 10 发现的其他常见漏洞。信息安全人员有找到这些漏洞的动机，因为他们可以打赌恶意行为者会寻找它们。如果他们发现一个暴露的弱点，那些坏人可能会利用它来危害组织的系统和数据。相比之下，如果安全人员首先识别出漏洞，他们可以采取行动来修复缺陷或以某种方式减轻缺陷。

API 安全测试不仅有助于组织避免与安全事件相关的损失。这对他们在其他方面也有好处。这种测试可以提高客户满意度，因为它表明组织正在努力保护其信息免受内部和外部威胁。它还为组织提供了增加收入的机会，因为他们可以使用 API 安全测试来解决问题，从而可以更快地将新功能和产品推向市场。

这种测试可以采取各种形式。例如，静态应用程序安全测试(SAST)指的是测试人员有权访问指定系统或软件的架构图或源代码。然后，他们可以使用相应的工具，如源代码分析器，来检查非编译代码的缺陷，如输入验证和路径遍历。根据卡内基梅隆大学软件工程研究所的说法，二进制和字节码分析器可以对编译后的代码执行相同的功能。

相比之下，动态应用程序安全测试(DAST)假设测试人员没有系统的先验知识。因此，测试人员将使用 fuzzing 来检查系统如何处理无效和意外的测试用例。他们可以检测过程中的脚本、数据注入和其他问题。

## API 安全性测试的局限性

API 安全测试的问题在于，它只能有效地识别一些 API 安全问题。这就是为什么[盐业安全](https://salt.security/blog/api-security-checklist)认为组织需要做得更多:

对你的 API 进行安全性测试，但是要知道你还需要运行时保护来捕捉那些没有通过标准构建过程的变更和测试工具没有设计来发现的滥用。如果你什么都不做，就把重点放在运行时保护上，作为“止血”的一种方式，减缓攻击者的速度，为应用程序和 API 团队赢得时间。

安全团队可以通过激活可能对他们的 API 网关可用的威胁保护功能来确保 API 运行时保护。他们应该将此作为考虑不同类型攻击的多方面 API 运行时安全策略的一部分。例如，他们需要确保采取措施来帮助缓解拒绝服务(DoS)或分布式拒绝服务(DDoS)攻击。他们还希望确保能够利用大数据、人工智能、机器学习和行为分析能力来检测规避的 API 攻击。

在这方面，运行时应用程序自我保护(RASP)会有所帮助。正如 [TechBeacon](https://techbeacon.com/security/what-runtime-application-self-protection-rasp) 所指出的，RASP 的目的是提供针对应用攻击的实时保护。它可以通过拦截从应用程序到系统的调用、验证这些调用的安全性以及验证数据请求来持续监控恶意输入或行为。所有这些功能都在运行应用程序的服务器上运行，这意味着开发人员不需要重新设计应用程序来适应其检测和保护功能。因此，RASP 可以帮助识别和缓解攻击，而无需人工干预。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>