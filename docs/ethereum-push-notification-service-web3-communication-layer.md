# 以太坊推送通知服务:Web3 通信层

> 原文：<https://thenewstack.io/ethereum-push-notification-service-web3-communication-layer/>

[](https://twitter.com/jakeludington)

 [杰克·卢丁顿

杰克是一名自由记者和博客写手，对 Web3 技术、企业 IT 和流媒体视频充满热情。在推特上关注他@ jakeludington。](https://twitter.com/jakeludington) [](https://twitter.com/jakeludington)

当你在一个应用程序中实现通知时，你通常会有信号来触发事件。用户帐户属性和设置可用于确定谁将收到何种类型的通知。在 Web3 dApps 中，用户账户就是钱包。虽然钱包持有者签署了到 dApp 的连接，但是在认证握手中没有通知层的概念；除了验证钱包中特定货币或 NFT 的存在，没有相同类型的信号可用。

进入[以太坊推送通知服务](https://epns.io/) (EPNS)协议。在接受 New Stack 采访时，EPNS 的联合创始人 Richa Joshi 解释说，以太坊应用程序缺乏内置的通信层“意味着利用 Twitter、Discord 等不合标准的间接通信，或者在最好的情况下，拥有一个移动应用程序，通过他们的平台发送应用内通知。”移动应用程序的应用内通知仍然受限于在认证钱包握手之外的层所暴露的内容，并且不针对可能不使用钱包应用程序的用户——或者甚至是具有移动应用程序的钱包。

实现 EPNS 协议的 [EPNS dApp](https://app.epns.io/) 于 1 月 11 日在以太坊主网上上线。根据 Joshi 的说法，“EPNS 现在正在使用不同的应用程序，向开发人员演示如何以多种不同的方式实现该协议。EPNS 适用于以太坊名称服务等消费者基础设施、清算和治理等 DeFi 实用程序以及媒体警报等手动通知。这种链上+链下和自动+手动的结合意味着开发者有足够的参考资料来建立他们自己的渠道和通知。”

## 使用您的 dApp 实施 EPN

EPNS dApp 允许您创建频道并向该频道的订户发送通知。消息可以在链上发送，这在今天会产生与任何以太坊交易相关的气体费用，也可以根据 [EIP-712](https://eips.ethereum.org/EIPS/eip-712) 在链外发送，该协议旨在通过链外消息签名提供人类可读的消息上下文。用 TypeScript 编写的一个[前端 SDK](https://www.npmjs.com/package/@epnsproject/frontend-sdk) 被设计为与 Node.js v10.0.0 或更高版本一起工作，允许额外的灵活性。

前端 SDK 目前执行三个关键功能:

*   从 EPNS 后端获取通知。
*   解析提取的通知。
*   在手机或浏览器中呈现解析的通知

EPNS 还包括一个用 TypeScript 编写的[后端 SDK](https://www.npmjs.com/package/@epnsproject/backend-sdk) ，它允许开发人员使用定制逻辑基于个性化需求构建有效负载并发送通知——这提供了 EPNS dApp 之外的额外灵活性。由于 EPN 相对较新，我怀疑这种后端定制的许多用例还没有实现。

## 最大化无噪声信号

鉴于垃圾邮件发送者滥用每一种可用的信息技术的倾向，我问 Joshi EPNS 是如何看待通知滥用的。

“dApp 中的每个用户和频道都绑定到一个唯一的地址，”他回答道。“这确保了每个渠道都是独一无二的，并且有自己的一组用户对该渠道发出的特定类型的通知感兴趣。最重要的是，通过特定渠道发出的通知只会到达订阅该渠道的用户的收件箱。对于其他未订阅的用户，通知将始终在垃圾邮件框中。

如果通知生态系统中存在不良行为者，Joshi 强调了智能合约在清除他们方面的作用，并解释说:“根据 EPNS 智能合约的当前架构，我们有一个链上验证功能，允许对渠道进行充分的验证程序，以增强特定渠道的信任和可靠性。然而，尽管恶意行为者可能出现在任何平台上，我们也承认这一点，我们的合同也包含了阻止频道的功能。如果某个渠道表现不佳，可以基于完全链上和分散的治理过程来阻止该渠道。一旦被封锁，同一个钱包地址就再也不能用来创建任何渠道了。”

正如我们在应用程序开发中认为理所当然的许多基础一样，通知在 Web3 世界中还处于起步阶段。EPNS 在为 dApp 通知提供解决方案方面处于领先地位。您可以通过加入 [EPNS Discord](https://discord.gg/YVPB99F9W5) 来获得您的实施问题的答案或帮助塑造项目的未来。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>