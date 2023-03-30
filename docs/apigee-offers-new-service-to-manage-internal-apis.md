# Apigee 提供管理内部 API 的新服务

> 原文：<https://thenewstack.io/apigee-offers-new-service-to-manage-internal-apis/>

API 平台供应商 Apigee 宣布了一种新的用于管理内部 API 的轻量级服务，称为“Apigee Edge Microgateway”。

这项新服务旨在补充其现有的 [Apigee Edge](http://apigee.com/about/products/api-management) 产品，帮助公司管理其外部 API，它专注于企业内部，提供安全、监控和分析功能。

Apigee 产品战略高级副总裁 Ed Anuff 解释说:“我们看到的情况是，我们的许多客户希望使用与他们管理 API 的系统相同的系统，并向外界开放……他们管理的每种 API 都希望在一个地方完成。

然而，他们不希望所有的 API 都必须通过一个集中的系统。

“如果我在欧洲数据中心有一个微服务，有人从我的德国办公室调用它，我不能让流量通过可能在我的达拉斯数据中心的集中安装来保护这项服务，”他说。

“但是，对我来说，在我想做的每个地方大规模部署一个平台也不是很有效。有了微服务网关，我可以在任何一个办公室部署它，我仍然可以监控和管理，并且我可以根据需要允许所有这些流量在本地运行。”

据该公司称，Apigee Edge Microgateway 为客户提供了轻量级内部 API 管理的简单性和性能，以及云托管服务的规模和功能。

它是一个本地网关，部署在私有网络内的微服务旁边，可以简化部署、减少延迟并提高 API 程序性能。

它被设置为微服务通过的网关。网关验证访问凭证，确保使用安全令牌，跟踪使用情况并监控其性能。您还可以获得服务使用频率的审计跟踪，以及其他分析。

“对于面向服务的架构，你经常会听到人们说，‘我们有所有这些服务，但我们不知道是否有人在使用它们，所以我们永远不会因为有人可能在使用它而关闭任何东西。’这给了你那些数据，”阿努夫说。

它还会定期与 Apigee Edge 进行通信，这样您就可以了解所有服务的情况。

用 Node.js 编写，它被设计成非常轻量级的。它可以与它管理的 API 实现共享一个服务器，或者在单独的服务器上运行。它也可以在 Docker 容器内运行，在 OpenStack、CloudFoundry 或云平台(如 RHEL、SUSE 或 CentOS)上运行。

Anuff 说，客户一直在寻求一种更好的方法来管理内部 API，到目前为止还没有一个好的答案。他说，这一直是业内每个人都在谈论的问题，但却没有推出产品。

他说，在过去，供应商可能会试图用集成服务器或企业服务总线来解决这个问题，这非常笨重，对开发人员不友好。

“面向服务的架构和企业服务总线是上一代企业架构的一部分。它们是集中管理的。现在，API 正以分散的方式在各地出现，”他说。

“企业仍然需要有集中的管理能力，但他们必须有一种分散的方式来连接所有这些 API。API 已经在公司的每个工程团队中实现了民主化。

“你过去可以走进一家公司，然后说，‘我想和管理你的 API 的人谈谈’，真的会有一个人这么做。如果你这样做，你会得到一个有趣的外观，因为可能有 10，000 人用 API 来构建。可能有数百人在管理这些 API。如果你没有办法在组织中找到每一个 API，你就不能有效地管理它们。”

Apigee Edge Microgateway 现已面向特定客户推出，并将于今年晚些时候广泛推出。要申请参加 Apigee Edge Microgateway 早期采用者计划的邀请，[请点击此处](https://pages.apigee.com/edge-micro-request.html)。

Apigee 的平台，除了 Apigee Edge，还包括高级预测分析产品 Apigee Insights 以及 API-first 的物联网(IoT)产品 Apigee Link。该公司于 4 月 24 日上市。

3scale 和 Docker 是新堆栈的赞助商。

专题图片: [Lostinawave](https://www.flickr.com/photos/27483745@N03/) 的《[纽约之窗](https://www.flickr.com/photos/27483745@N03/6421402197/in/photolist-aMrn9Z-kFkvuF-f7xaSN-225ohE-bF3Vzh-7hVRZr-871AM5-qcaS5E-iUEXy4-pJbPSK-r6hZtA-Qsd2n-qVqMEK-hJDZyX-gX8gzj-gn5pXt-cYcDuA-9qq71r-gn1qbA-bF3Xdj-gn1fcM-rsYEyM-9FNFJk-j1rKKL-fc9n6m-aqFtxF-pEoKAJ-cskyrY-8bc91r-3dda2E-d4Jdqd-8rZ9vm-boqtP4-aU9wqa-g6hf-gX58n3-4LqJhd-5rBivm-5nuXBt-aGcYfK-oBjwhB-398wXs-9Jozmg-czZWa-pPd8pL-hJq1wQ-qCvYXQ-7mNb7t-p4AT6o-4pmFRt)由 2.0 在 [CC 下授权。](https://creativecommons.org/licenses/by/2.0/)

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>