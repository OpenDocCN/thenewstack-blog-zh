# 演示:APIcast，一个用于管理和保护 API 的云中代理

> 原文：<https://thenewstack.io/demo-apicast-a-proxy-in-the-cloud-for-managing-and-securing-apis/>

在这个简短的教程中， [3Scale](http://www.3scale.net/) 联合创始人兼首席执行官史蒂夫·威尔莫特展示了， [APIcast](https://thenewstack.io/apicast-an-api-gateway-suited-for-the-startup-and-small-business-its-free/) ，一个用于管理 API 的云中代理。该演示展示了开发人员如何使用 APIcast 作为代理，将其放在他们的 API 前面。

[https://www.youtube.com/embed/jaUzKCvwKO4?feature=oembed](https://www.youtube.com/embed/jaUzKCvwKO4?feature=oembed)

视频

首先，威尔莫特使用了来自 API 搜索引擎 [APIs.io](http://apis.io/) 的 API。他选择了一个呼叫，并将其放入浏览器，然后浏览器为他返回了 JSON。

威尔莫特指出，这个问题源于调用 API 时缺乏可见性。用户不知道谁在使用 API，没有分析，有人可以通过强力攻击来摧毁服务器。

为了补救，Wilmott 随后为 APIs.io 服务器配置了一个 APIcast 帐户。他在服务中添加了三个方法，用于获取 API 列表、提交 API 和第三个用于搜索。

通过 APicast，API 被推到一个沙盒中，开发人员用它来玩 API。电话是在厕所里打的。此时，调用是通过 APIcast 代理进行的。生成一个密钥，开发者可以按照他们的意愿使用它。如果密钥发生变化，开发人员会得到一个身份验证失败的消息，演示代理如何保护 API 免受未经身份验证的请求。

API 在部署到 APicast 后，前面有一个代理，使其可以投入生产。可以设置速率限制。该帐户还创建了一个门户，开发人员可以通过这个门户获取他们的密钥。门户还有一个 [Swagger](https://thenewstack.io/why-swagger-makes-apis-easier-to-describe-and-consume/) 规范来创建文档。

APicast 每天最多可免费完成 50，000 笔交易。

通过 Flickr Creative Commons[获得特色图片。](https://www.flickr.com/photos/swimfinfan/6490751071/in/photolist-aTyNae-aTyLfr-7KxkX1-mTgjda-nP1Dte-9QZQxd-e6Bbo6-86ULj6-61aJvt-fqVMS2-frb3Rb-aAABLG-9fDaE9-9GVWdq-3yCmWD-5nHbAn-9Vi9sJ-ppuVx3-7LjGGM-aTyQ1t-9ZaHXM-aYzR8D-deeZuz-5nMs5o-5nMrPL-9LTbPg-dbSGma-fo1gY7-7eVCjY-dipUNm-joLFU8-9X27Sc-4B39Yb-cX2S4f-bR7fRp-a2H328-mKQA9S-4ote7o-95h6xa-aTyPeF-cRwLCN-4wVrkM-7bDTti-7bHDJy-88ZMBQ-5z8VD9-4v3oWD-6dmcZf-dR5pK8-amDjG6)

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>