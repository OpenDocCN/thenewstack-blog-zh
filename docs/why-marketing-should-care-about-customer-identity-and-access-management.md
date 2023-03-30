# 为什么营销应该关注客户身份和访问管理

> 原文：<https://thenewstack.io/why-marketing-should-care-about-customer-identity-and-access-management/>

[](https://www.linkedin.com/in/darshana-gunawardana-a23b6037/)

 [达尔夏纳·古纳瓦达纳

Darshana 是 WSO2 的副总监/架构师，也是 WSO2 Identity Server 团队的重要成员。他主要关注身份管理和计算机安全领域。](https://www.linkedin.com/in/darshana-gunawardana-a23b6037/) [](https://www.linkedin.com/in/darshana-gunawardana-a23b6037/)

到 2020 年，移动到网上的浪潮反过来推动了对高性能、经济高效的[客户身份和访问管理(CIAM)](https://wso2.com/what-is-ciam/) 解决方案的需求。随着 2021 年的到来，这些解决方案对于任何企业真正了解他们的客户都变得至关重要；这就是为什么首席营销官(CMO)应该积极参与并关心他们的 CIAM 系统。在客户购买之旅的各个阶段(如认知、考虑、购买和服务)，CIAM 通常在后台运行，通过提供显著改善的入职、个性化、全渠道体验和隐私控制，确保合适的解决方案增强客户的数字体验，并与客户建立至关重要的信任。

那么，让我们来看看 CIAM 是如何工作的，以及它在客户旅程的各个不同阶段提供的好处:

**认知阶段**是第一步，顾客与公司品牌互动。这是客户了解企业提供的产品或服务的地方，这可能会导致他们访问公司网站或社交媒体等其他平台上的内容。

在这个阶段，客户互动通常发生在匿名级别。因此，CIAM 解决方案的参与将是最小的，因为没有身份信息可用。然而，重要的是利用像[网络分析](https://is.docs.wso2.com/en/latest/learn/web-analytics-solutions/)这样的产品来保持客户的兴趣，这在以后的阶段是有益的。

**在** **考虑阶段**，客户将有更集中的需求，他们将通过下载数据表、跟随产品演示/试用等方式展示更多参与度。通常，在此级别的 CIAM 中会捕获一到两个客户属性。根据属性的重要性，这将是在 CIAM 系统中将客户表示为 *light* 用户帐户的起点。这些帐户没有任何关联的凭据，因为客户没有经过入职流程。

在这一级，CIAM 的[入站](https://is.docs.wso2.com/en/latest/learn/identity-provisioning/#inbound-provisioning)和[出站](https://is.docs.wso2.com/en/latest/learn/identity-provisioning/#outbound-provisioning)供应能力起着关键作用。例如，潜在客户通过提供电子邮件从产品网站下载目录；然后，该网站将在 CIAM 系统中创建一个轻型账户，使用标准的供应协议，如 [SCIM](https://is.docs.wso2.com/en/latest/develop/scim2-rest-apis/) 。接下来，CIAM 解决方案将(向外)向不同的营销工具提供该用户帐户——例如， [Hubspot](https://is.docs.wso2.com/en/latest/learn/provisioning-users-to-hubspot/) ，CRM 工具如 [Salesforce](https://is.docs.wso2.com/en/latest/learn/provisioning-users-to-salesforce/) ，或 [web analytics](https://is.docs.wso2.com/en/latest/learn/web-analytics-solutions/) 工具如 [Mixpanel](https://is.docs.wso2.com/en/latest/learn/web-analytics-solutions/#mixpanel) 。

同样，组织可能会将轻量级帐户与 web 分析相关联。这有助于获得更多关于用户的信息，比如地理位置和他们在感知阶段看了什么类型的内容。这些细节可以用来在将来提供更相关的、个性化的信息。

**采购阶段**是最受大多数组织关注的阶段。根据法律法规，验证用户详细信息至关重要。然而，确保[客户注册](https://is.docs.wso2.com/en/latest/learn/self-registration/)和入职流程简单易用非常重要。

最大限度地减少客户要求的强制信息字段非常有帮助。这可以通过自动填充已经与轻型帐户关联的信息来完成。另一种方法是使用[渐进式剖析](https://is.docs.wso2.com/en/latest/learn/configuring-claims-for-a-service-provider/#mandatory-claims)，这样客户只有在访问需要这些细节的特定服务时才需要提供额外的细节。

从客户的角度来看，必须维护许多帐户和凭据是一个主要的难题。能够[携带自己的 ID (BYOID)](https://is.docs.wso2.com/en/latest/learn/identity-provisioning/#just-in-time-provisioning) 来帮助简化注册流程是非常重要的。这也将有助于减少后期的自助服务或呼叫中心交互，因为它将减少因遗失或忘记凭据详细信息而不得不恢复帐户的需要。

此外，与 CIAM 解决方案中的 [Evident ID](https://store.wso2.com/store/assets/isconnector/details/1a85a226-177c-4a90-8da3-b142c46ae658) 等[身份验证](https://is.docs.wso2.com/en/latest/learn/fraud-detection/#identity-verification)服务直接集成，减少了提供各种文档的开销，或者减少了必须通过手动流程来验证客户信息(如公民身份证明、保险有效性等)的开销。

**服务阶段**也是许多消费者业务的关键阶段。这个层面的用户体验决定了现有客户是成为品牌的拥护者还是诋毁者。

从 CIAM 的角度来看，用户应该能够无缝访问他们消费的任何产品或服务。如果涉及到多种服务，那么像用同一个帐户消费两种服务的能力以及在多个应用程序之间实现单点登录这样的基本功能就成为了必备功能。[访问敏感应用程序时，还需要具备附加因素的强身份认证](https://wso2.com/identity-and-access-management/strong-authentication/)。此外， [adaptive authentication](https://wso2.com/identity-and-access-management/adaptive-authentication) 在平衡便利性和安全性方面发挥着关键作用。拥有像[账户锁定](https://is.docs.wso2.com/en/latest/learn/user-account-locking-and-account-disabling/)和[基于风险的认证](https://is.docs.wso2.com/en/latest/learn/configuring-risk-based-adaptive-authentication/)这样的机制可以更好地保护客户账户免受恶意方的侵害。

这导致了另一个至关重要的需求:[自助服务](https://wso2.com/library/articles/introducing-the-wso2-identity-server-self-care-portal/)。客户应该能够更新和审查他们的[隐私偏好](https://is.docs.wso2.com/en/latest/learn/my-account/#consent-management)(例如不同活动使用不同的电子邮件)，更改相关的[个人资料信息](https://is.docs.wso2.com/en/latest/learn/my-account/#user-profile-management)，并更新联系信息。同时，用户应该能够通过配置[恢复机制](https://is.docs.wso2.com/en/latest/learn/my-account/#account-recovery)和[注册可信设备](https://is.docs.wso2.com/en/latest/learn/my-account/#add-security-device)进行登录来调整他们的安全配置文件。随着世界各地隐私法规的进步，现代企业也必须给予用户[数据可移植性](https://is.docs.wso2.com/en/latest/learn/my-account/#export-user-profile)和[注销](https://is.docs.wso2.com/en/latest/develop/scim2-rest-apis/#/Me%20Endpoint/deleteUserMe)的能力。

此外，在服务阶段，企业也可能会经历变化，例如并购其他[品牌](https://is.docs.wso2.com/en/latest/develop/customizing-login-pages-for-service-providers/)，这些活动不应严重影响客户体验。正确的 CIAM 解决方案可以以渐进的方式促进这些迁移。

CIAM 甚至可以帮助旨在提高客户参与度的忠诚度项目。忠诚的客户可能会选择提前接触新产品，并给出更准确的反馈，这些反馈可用于产品或服务变更的 A/B 测试。

由于 CIAM 解决方案与涉及客户的每一个系统都有很好的[联系，它使组织能够生成增强的和可操作的](https://is.docs.wso2.com/en/latest/learn/fraud-detection/#business-intelligence)[行为数据](https://is.docs.wso2.com/en/latest/learn/analytics/#analytics)，这些数据可用于预测和确定可能的利益。即使在前所未有的时期，这些信息也有助于做出更明智的决策。

提升客户体验是数字化转型的核心。如今，越来越成熟的客户将数字互动视为与产品和服务互动的主要机制，因此，他们希望以简单、安全和无缝的方式建立更深入的在线关系。CIAM 在将应用和 API 连接到客户方面发挥着至关重要的作用，提供了交付无与伦比的客户体验所需的所有功能。

通过 Pixabay 的特征图像。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>