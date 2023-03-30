# 僵尸烤面包机会对我的无服务器部署造成 DDoS 攻击吗？

> 原文：<https://thenewstack.io/zombie-toasters-eat-startup/>

不要介意关于[无服务器](/category/serverless/)的炒作。别管“无服务器”[这个词是否是正确的词](https://news.ycombinator.com/item?id=4655194)。我们需要开始思考，AWS Lambda 和类似的服务是否有可能为恶意软件打开一条道路，让它们攻击公司最受伤害的地方:银行存款余额。

## 托管成本受到攻击

如果你的企业是一个[分布式拒绝服务](http://www.digitalattackmap.com/understanding-ddos/) (DDoS)攻击的目标，你的服务很可能在太多请求的重压下陷入停顿。假设您在 AWS 或 Azure 等云服务上使用虚拟机，并且设置了自动缩放，那么您将自动创建新的机器实例，因为当前的机器实例工作过度。

您很可能设置了最大数量的自动伸缩实例，这将给出成本的上限:最大实例数量 x 这些实例每小时的成本 x 您意识到自己受到攻击所需的时间。

许多人都为扩展事件设置了通知，所以您可能很快就会知道正在添加新的机器。如果新机器的数量看起来不寻常，您的团队有机会很快发现攻击。租用一台典型机器的每小时价格只有几分钱，因此，尽管如果你遭受 DDOS 攻击，你的业务可能会有很多成本，但在托管上的[额外支出不太可能是一个脚注。](http://www.networkworld.com/article/2909523/network-security/a-true-story-of-combating-a-large-scale-ddos-attack.html)

## 但是如果你使用的是无服务器的呢？

使用无服务器，您可以处理的请求数量基本上没有限制——对于每个并发请求，该服务几乎可以即时自动扩展。如果你的产品突然变得成功，这很好，因为你真的不需要计划额外的规模；这一切都是自动为您处理的，甚至不需要考虑自动缩放设置。

但是，如果你的服务没有突然上升到受欢迎的排行榜上，而只是一个僵尸网络协同攻击的受害者呢？你被函数调用收费了。所有这些函数调用的无限成本会让你破产吗？让我们看看可能的成本。

尽管存在其他无服务器提供者，我们将在我们的例子中使用 AWS Lambda 定价。Lambda 定价基于请求数量和计算资源量。AWS 系统架构公司 [Trek10](https://www.trek10.com/) 整理了[这份方便的指南，告诉你对于你的工作负载来说，无服务器还是虚拟机更便宜](https://www.trek10.com/blog/lambda-cost/)。得出的结论是，对于大多数中等规模的企业来说，使用无服务器会更好，尽管计算的密集程度确实很重要。这些是对“正常”交通水平的预测。

让我们看看，如果您受到攻击，成本会如何上升。

## 攻击的规模

拒绝服务攻击的规模有多大？尽管最初报道称由“[数千万个](https://dyn.com/blog/dyn-statement-on-10212016-ddos-attack/)IP 地址组成，但去年 10 月攻击 Dyn 的 [Mirai 未来组合僵尸网络](https://www.wired.com/2016/12/botnet-broke-internet-isnt-going-away/)现在估计已涉及约 10 万个端点。假设他们被招募来以每秒 1 个请求的速度攻击你的 Lambda 服务，那么我们可能会看到每小时 100，000 * 3，600 = 3.6 亿个请求。

AWS Lambda 定价的第一部分是每百万个请求 0.20 美元，因此处理 3.6 亿个请求每小时 72 美元。然后是千兆秒计算时间的费用。假设函数使用 1 GB，耗时 200ms。AWS 每使用一 GB 秒向您收取 0.00001667 美元，因此这是 1200 美元。我们处理一小时攻击的总成本低于 1300 美元。这不太可能让许多初创公司破产。

以每秒一个请求的速度，这些机器人并没有努力工作。假设每个机器人都尽可能地攻击您的服务，在收到前一个响应后立即发送另一个请求。如果我们忽略网络延迟和客户端的任何处理时间，我们可以假设最坏的情况是每个 bot 导致您的 lambda 函数 100%的时间都在运行。

仅看计算时间成本，100，000 个僵尸网络都在持续攻击该功能，每秒将花费 1.667 美元，或每小时 6000 美元，因此我们处于同一数量级。根据你的初创公司资金的充足程度，在这个水平上，你可能会考虑在半夜发出警报叫醒某人的重要性，以确保像这样的攻击不会太久得不到解决。

## 当烤面包机攻击时

我们都知道，另一个非常时尚的技术领域，即物联网，正在大幅增加联网设备的规模。据估计，已经有[50 万台物联网设备的安全性较弱](http://www.securityweek.com/over-500000-iot-devices-vulnerable-mirai-botnet)。

这是参与 Mirai 未来组合/ Dyn 攻击的设备数量的五倍。但是，即使他们都被招募来同时攻击您的服务，我们仍然会看到无服务器成本大约为每小时 5 x 6，000 美元= 30，000 美元。这是一个很大的烦恼，如果你的初创公司在财务边缘运营，这足以让你破产，但我们正在谈论的是一个极不可能的事件组合。

但并不是每个人的烤面包机都可以上网，而且联网设备的数量也在快速增长。让我们来看看思科对[500 亿台机器](http://www.networkworld.com/article/3026315/internet-of-things/6-critical-issues-facing-the-internet-of-things.html)的估计，并假设一个末日场景，它们都被一个恶意僵尸网络接管，意图攻击你的公司。这是攻击能力的 100，000 倍，即使以每秒 1 个请求的速度，每小时也要花费 1 亿美元。那肯定会有影响！

当然，世界上所有的互联网设备都不太可能被同一家公司收购。如果你的服务遭受拒绝服务攻击，你真正需要担心的是你的真实用户不能正确使用你的产品。

## 减轻灾难

亚马逊考虑设置的限制也缓解了灾难场景。默认情况下[，一个 Lambda 函数被限制为 100 个并发执行](http://docs.aws.amazon.com/lambda/latest/dg/concurrent-executions.html)，作为防止函数失控的安全措施。你可以提高限额，而且随着你的服务越来越受欢迎，你可能也想这样做，但这确实会限制你的支出。(我认为，当我在上面说您不需要为无服务器环境中的自动伸缩做计划时，忽略了您想要考虑的关于您的服务的合理并发执行数量的问题。)

AWS 提供额外的服务，如 [WAF](https://aws.amazon.com/waf/) (Web 应用防火墙)来帮助保护您的部署免受攻击。它还提供了许多关于最佳实践的好建议，尽管他们目前更关注 EC2 而不是 Lambda 风格的部署

**结论——僵尸攻击的成本不会显示在你的托管账单上**

如果你是一个初创公司的创始人，有很多事情可能会让你彻夜难眠。但是，如果一大群僵尸烤面包机决定攻击你的服务，担心你可能招致的托管成本并不需要成为其中之一。

专题图片:[僵尸漫步](https://www.flickr.com/photos/cadampol/6425645177/in/photolist-aMP7rP-aUeTYP-pRPF4a-sxfWXh-drSTcW-aUeoZn-pzEm2f-3e8BAm-aUekAR-6QT8vU-6a92EV-qtpmB-dmdo5E-9h7DHc-6tGbiV-asziDS-cYDJBQ-oVg5za-as78FQ-nhMekp-p81jnj-cYHpzY-oVg6v8-oVcWuE-o8SZpd-p81jPw-cYE8eA-5LuXdA-aUeTA6-arRefk-77JppQ-cYE9ys-aUeU5P-aUep8X-4XrDYP-dd5AcW-aUeiCV-pzBmSY-cj9ews-aUepGc-hYkqMD-aUenGz-aUeFN4-7b3S9F-dmdqjR-cYHtcG-arReY2-cY81Qf-cYE6P3-cY7Ss5)作者:[卡洛斯亚当波尔加林多](https://www.flickr.com/photos/cadampol/)，[Attribution-share like 2.0 通用许可](https://creativecommons.org/licenses/by-sa/2.0/)。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>