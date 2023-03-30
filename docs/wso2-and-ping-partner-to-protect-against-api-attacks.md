# WSO2 和 Ping 合作防止 API 攻击

> 原文：<https://thenewstack.io/wso2-and-ping-partner-to-protect-against-api-attacks/>

虽然有些人可能会将微服务和容器化视为提高效率和简化开发流程的好处之一，但我们当中关注安全的人可能会看到完全不同的东西:攻击面的指数级增长。简而言之，当我们将整体应用分解为微服务时，我们增加了每个微服务相互通信所需的应用编程接口(API)的数量，而这些端点中的每一个都提供了另一个潜在的攻击媒介。

考虑到这一点，开源集成供应商 [WSO2](https://wso2.com/) 与 [Ping](https://www.pingidentity.com/content/ping/en.html) 合作，将 Ping 的人工智能(AI)驱动的 API 安全保护添加到其自己的一套开源策略控制软件中。

[WSO2 营销副总裁肯·奥斯特里奇](https://www.linkedin.com/in/kenoestreich)在接受新堆栈采访时解释说，最近 API 的爆炸式增长使得传统的安全方法无法适应现代微服务环境的复杂性和动态性。

“如果你纵观 IT 历史，也许回到 20 年前，所有软件都是单一的。你只需要写一个软件，它就能做所有的事情。有时候，一个供应商的软件必须与另一个供应商的软件进行对话，这要么是胶水代码，要么是类似的东西。在过去的四五年里，使用 API 到前端软件出现了爆炸式增长，这样一个软件可以与另一个软件对话，”奥斯特里奇说。“随着微服务的出现，面向 API 的系统市场进一步扩大。我们现在有一系列真正的大系统必须与较小的系统交互，所有这些东西之间的粘合剂是 API。这些东西正在以数量级增长。随着我们进入更多的微服务，在这些微服务中，有数百、数千或数万个微服务在几毫秒内被执行，完全没有办法手动审查这些东西。”

通过 WSO2 和 Ping Identity 之间的合作，两个现有产品— [WSO2 API Manager](https://wso2.com/api-management/) 和[Ping intelligence for API](https://www.pingidentity.com/content/ping/en/platform/apiintelligence.html)—现在能够使用开源扩展进行集成，该扩展与部署在 WSO2 API 网关中的 Ping intelligence API Security Enforcer(ASE)模块进行通信。本质上，WSO2 API 管理器的用户可以将基于人工智能的安全分析和威胁拦截应用于他们的 API，以及由 Ping Identity 提供的基于静态策略的安全控制。

奥斯特里奇解释说，Ping Identity 能够提供动态的而不仅仅是静态的规则和控制，这使得它适合于通常由分布式团队开发的短暂系统。

“基于人工智能的威胁检测学习大量 API 使用和调用的模式，并标记它认为潜在可疑的 API 端点使用。它给了人们一种额外的安慰，即坏演员不会试图攻击数量迅速增长的端点和 API，”奥斯特里奇说。“这非常有用，因为这些 API 系统变得越来越复杂和不可预测。任何 IT 部门都有几十个、几十个、甚至几百个开发人员在集成 API，而且他们是异步地、独立地这样做的。你并不总是知道谁或者怎样使用一个 API。不同的开发团队会以不同的方式 going 一个 API。随着系统变得越来越复杂，拥有这样一个安全网是非常有用的。”

根据该声明，该集成将允许其用户防止多种不同类型的 API 攻击，包括“使用有效用户帐户对 API 进行反向工程并侵入其他帐户来窃取数据的攻击——同时看起来像普通用户”,以及“使用被盗令牌、cookies 或 API 密钥的攻击；对登录系统的攻击；远程应用控制；僵尸网络抓取数据；数据泄露；特定于 API 的拒绝服务/分布式拒绝服务(DoS/DDoS)攻击，以及来自经过身份验证的用户的一系列攻击。”

WSO2 是新堆栈的赞助商。

通过 [Ping](https://www.pingidentity.com/en/platform/apiintelligence.html) 的特征图像。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>