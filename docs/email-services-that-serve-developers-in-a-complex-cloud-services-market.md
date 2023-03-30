# 在复杂的云服务市场中为开发者服务的电子邮件服务

> 原文：<https://thenewstack.io/email-services-that-serve-developers-in-a-complex-cloud-services-market/>

电子邮件、数据库、API 平台等基础服务和一系列其他服务现在被打包到公共云服务中。但独立提供商仍然通过与基础设施和平台即服务产品的集成显示出实力。电子邮件交易市场类别是云服务提供商和独立供应商如何找到自己的方式来区分彼此的一个例子。

SparkPost 是 Heroku marketplace 上的一个新插件，它每月向开发者提供多达 10，000 封免费电子邮件。这一消息指出了对电子邮件集成的持续需求，开发者可以将电子邮件集成到他们的应用中。在了解一些供应商之前，让我们先退后一步，看看电子邮件的使用，以及它对整个市场格局的影响。

据电子邮件营销供应商[mobile Ink](http://www.marketingprofs.com/charts/2015/27708/email-opens-conversions-and-read-times-by-device-type#ixzz3jxVzqi10)称，今年第一季度，美国所有打开的电子邮件中有三分之二(67%)发生在移动设备上。

虽然苹果设备拥有最高的电子邮件打开率，但根据 SendGrid 的调查，基于 Android 和 Linux 的设备是美国电子邮件打开增长最快的两个领域，去年增长了 71.4%。

除了营销和时事通讯，每月还会发送大约 600 亿封交易电子邮件，包括密码重置提醒、注册确认和购买发货通知。

交易型电子邮件不同于营销和时事通讯，因为它必须与应用程序进行交互，这要求开发人员参与集成，同时还要确保它能在多种设备上正常工作。更多的电子邮件集成也在不断出现，例如 Outlook 的优步乘车提醒插件和通过 PayPal 插件在线汇款的功能。

这意味着让开发者满意。这对主流云服务和独立云服务一样重要。以下是一些正在日益交织的云服务领域寻找出路的电子邮件递送提供商。

## 亚马逊 SES

亚马逊 SES(简称“简单电子邮件服务”)是一种准系统产品，价格也很低。

这是一种仅用于通过 API 或 SMTP 服务器发送电子邮件的出站服务。你用亚马逊的 [SNS](http://aws.amazon.com/sns/) 通知系统追踪被退回的邮件，用 [Route 53](http://aws.amazon.com/route53/) 设置 DKIM(域名密钥识别邮件)记录，用 [S3](http://aws.amazon.com/s3/) 存储文件。

作为其服务的核心部分，它不提供点击跟踪、打开跟踪、传入电子邮件支持或为大发件人定制价格——鉴于有如此多的供应商提供类似服务，许多供应商正指望额外的功能来吸引客户。

价格:通过 EC2 或通过 AWS Elastic Beanstalk 每月免费发送多达 62，000 封电子邮件；高于每千封邮件 0.10 美元。

## 发送网格

SendGrid 提供交易电子邮件服务和电子邮件营销平台。

它使用 API 来发送电子邮件，使用事件 API 来自动获取电子邮件的通知和统计信息，使用解析 API 来获取回复的内容，以便在应用程序中使用。

它提供自定义的电子邮件认证证书；与 ISP 反馈环集成，以了解您的邮件何时被标记为垃圾邮件；IP 地址信誉评分，用于确定您的邮件被标记为垃圾邮件的可能性；详细的分析和报告；以及下载数据并自己浏览的选项。

集成合作伙伴包括 Windows Azure、惠普云、Softlayer、Rackspace、Heroku、Engine Yard 和 CloudBees 客户包括 Airbnb、Pandora、HubSpot、Spotify 和优步。

然而，它是 4 月份的一次攻击的[目标，并且一直在努力加快 API 密钥、IP 白名单和增强型双因素身份验证的发布。](https://sendgrid.com/blog/update-on-security-incident-and-additional-security-measures/)

它在 7 月宣布了新的白标管理[功能，以及一个带有新 UX 和 UI 的客户门户；改进的 web API 标准化了返回数据模式、响应代码和端点名称；高级抑制管理器(ASM)，允许收件人管理他们的电子邮件首选项。](https://sendgrid.com/blog/introducing-the-general-availability-of-sendgrids-new-customer-portal/)

价格:每月 4 万封邮件 9.95 美元，70 多万封邮件 399.95 美元的白金级，以及更高的定制价格。

## 山魈

[Mandrill](https://mandrill.com?utm_source=zapier&utm_medium=profile&utm_campaign=partnership) 由 MailChimp marketing email pros 构建，其整个 SMTP 中继基础设施构建在 AWS 之上。

Mandrill 提供专用 IP 地址、深度分析、模板托管、入站电子邮件解析等。还有一个分割测试工具，允许你尝试和测试，这样你就可以使用不同的模板；所有计划上的自定义 SPF(发件人策略框架)、DKIM 和跟踪域；过去 30 天发送的电子邮件的详细统计数据和可搜索日志以及您定义的标签和元数据的仪表板。

您可以在 Mandrill 中针对垃圾邮件过滤器测试您的电子邮件模板，以实现最高的发送率。

然而，它也是三月份的一次入侵的[目标。](http://www.pcworld.com/article/2899292/mandrill-warns-attack-may-have-exposed-some-data-about-email.html)

价格:每月最多 25000 封邮件 9.95 美元；下 100 万 0.20 美元/千；下 500 万 0.15/千；超过这个数的话 0.10 美元/千。

## Mailgun

[Mailgun](https://www.mailgun.com?utm_source=zapier&utm_medium=profile&utm_campaign=partnership) 是为大寄件人设计的。Rackspace 在 2012 年收购了这家自称为“电子邮件 Twilio”的初创公司。

它为您添加的每个域提供独立的子帐户，批量发送电子邮件的个性化功能，详细的分析和日志，以及一个强大的解析引擎，可以将收到的电子邮件转换为 JSON 并路由到您想要的地方。

您可以通过一个 API 调用发送多达 1000 封个性化电子邮件，使用标签对您的电子邮件列表进行分段，并运行 A/B 测试。Mailgun 可以将一个 webhook 推送到你的应用程序中，以便在电子邮件被发送、打开或你指定的任何其他事情发生时通知你。

它允许你单独处理你公司的每个项目或客户账户，或者如果你不想自己处理，它还提供了一个[托管服务](https://www.mailgun.com/managed)。

它集成了 Heroku、Engine Yard 和 AppFog。客户包括 GitHub、Stripe、37 Signals、PagerDuty 等。

价格:价格是每封邮件，前 10，000 封免费；接下来的 50 万每封邮件加收 0.00050 美元(51 万封邮件加收 250 美元)；下 100 万加 0.00035 美元/邮件(151 万邮件 600 美元)；接下来的 500 万为 0.00015 美元(651 万封邮件为 1，350 美元)；任何额外费用为 0.00010 美元/封电子邮件(1000 万封电子邮件为 1，699.00 美元)。

## 火花柱

SparkPost 拥有所有电子邮件提供商中最高的投递率——包括 Pinterest、Zillow、LinkedIn 和 Twitter 在内的客户的投递率为 97%至 98%。该公司最近还宣布支持在 Apple Watch 上发送[电子邮件。](https://www.sparkpost.com/blog/email-on-apple-watch/?utm_source=Twitter&utm_medium=CPC:%20Twitter%20&utm_campaign=Social%20Ads&utm_content=blog%20apple%20watch)

SparkPost 的 SMTP 和 REST APIs 允许开发人员在他们的 web 或移动应用程序中使用电子邮件，而不管语言如何。与 Heroku 的集成简化了注册和安装过程，允许用户开始使用全面的电子邮件 API 和预建的 SDK 库，并使用 webhooks 实时访问电子邮件分析。它还提供对支持文档的访问，如何在 Heroku 中收集关于 SparkPost 应用程序使用的见解，以及在平台之间建立简单导航的最佳实践。

据该公司称，其自适应电子邮件网络通过 SMTP 协议自动定制邮件，以解决各种 ISP 的跳票代码，从而遵守他们的规则并确保更高的交付率。

价格:每月 10000 封邮件免费，最高 100 万/月 574.95 美元；定制价格更高。

## 邮戳

[邮戳](https://postmarkapp.com/)专门针对交易类邮件。它声称可以让你看到谁打开了你的电子邮件，他们在哪里打开的，他们使用什么客户端和平台，甚至他们花了多长时间阅读它。

它提供了一个 API，带有流行语言和平台的代码片段和库，便于集成到网站或应用程序中；45 天的可搜索历史；入站解析，将消息转换为 JSON，可以在应用程序或 API 中直接搜索和检索。

它出售可以按需使用的电子邮件信用，而不是必须订阅某个使用级别的计划。

价格:试用他们的服务可以免费获得 25000 信用点；否则就是 1000 个信用点 1.50 美元/千；500，000+积分为 1.00 美元/千；200 万+积分最高 0.50 美元/千。

专题图片:[golly force 的《](https://www.flickr.com/photos/see-through-the-eye-of-g/)[公平时间](https://www.flickr.com/photos/see-through-the-eye-of-g/6013789220/in/photolist-aaqf23-96sytB-96syke-4GzW4h-96sy46-ohEJCt-pgRsyC-8ARt5o-9Gkzwb-xoEixb-jjxUNN-ojJVi7-pKEAzT-aTTdCa-zAueB-fdj1St-ndrgn-2jyocR-3vnVkg-naA7Ab-s78zTL-ruUVuT-cUJf7U-ohCWWv-cLhZXA-ohY7pp-4e5cS4-qQU27P-dd9jbS-tksSoH-o1vyt2-w3YnjW-sU2Ria-mdWf2w-kVMaAP-o1zmJT-ohLoa5-4RQCBM-vQdYSE-ogsVu3-ofUzHo-oVLRFt-zJzHD-prZVze-5Upg4E-o244hm-kVFtZc-o1U6Rj-o1z1Jb-q362j4)——活出我最糟糕的噩梦由 2.0 在 [CC 下授权。](https://creativecommons.org/licenses/by/2.0/)

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>