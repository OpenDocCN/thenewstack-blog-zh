# 如何优化客户身份和访问管理

> 原文：<https://thenewstack.io/how-to-optimize-customer-identity-and-access-management/>

[](https://lk.linkedin.com/in/krishnamohan-theviyanthan)

[the viyanthan Krishnamohan](https://lk.linkedin.com/in/krishnamohan-theviyanthan)

[the viyanthan Krishnamohan 是 WSO2 的一名软件工程师，拥有丰富的 React 开发经验。他喜欢在机器学习、人工智能、进化计算和物联网领域闲逛。](https://lk.linkedin.com/in/krishnamohan-theviyanthan)

[](https://lk.linkedin.com/in/krishnamohan-theviyanthan)[](https://lk.linkedin.com/in/krishnamohan-theviyanthan)

客户身份和访问管理(CIAM)已经成为组织不可或缺的一部分。根据商业研究公司[的一篇文章](https://www.thebusinessresearchcompany.com/press-release/global-consumer-identity-and-access-management-market-2021)，CIAM 市场预计将在 2025 年达到 455.6 亿美元，年复合增长率为 18.6%。该研究公司补充说，越来越多的物联网设备(如智能手机、智能手表、智能家居和医疗传感器)的使用将是这一增长的主要驱动因素。

由于 CIAM 的主要目的是通过利用身份数据获取和保留客户来增加收入增长，因此组织不能再忽视这些迹象，需要采取行动。但是，各公司在 CIAM 实施方面的经验水平不同。在这篇文章中，我们来看看有三个层次经验的组织，并讨论每个组织应该考虑什么。

首先，我们需要了解 CIAM 和传统身份和访问管理(IAM)之间的区别。从表面上看，差异似乎很小，因为两者都处理身份和配置文件数据的管理，并控制用户对应用程序和服务的访问。然而，关键的区别在于，CIAM 与客户打交道，而传统的 IAM 与员工打交道。

由于员工受到合同和保密协议的约束，传统的 IAM 解决方案不需要过多关注数据和隐私。此外，当雇员在公司内加入、离开和转换角色时，用户账户的变更由行政部门处理。然而，在 CIAM，客户不受合同约束。因此，遵守数据和隐私法规对组织来说至关重要。此外，客户还执行注册、更新和管理许可等任务。

理解这些关键差异对实现企业目标起着重要作用。根据组织在 CIAM 的经验，成功实施 CIAM 解决方案还需要考虑其他方面。下文对这些进行了审查。

![](img/6334a50d062a3f85347ad296594a070f.png)

组织必须实施动态 CIAM 解决方案来满足需求。
*图像鸣谢:[爆裂](https://unsplash.com/photos/kUqqaRjJuw0) —不飞溅*

## **第 1 级:CIAM 的新组织**

这些组织对什么是 CIAM 以及期望从解决方案中得到什么一无所知。以下是他们应该考虑的六个方面:

### 1.单点登录

一个组织可能有几个应用程序。例如，电子商务门户可能拥有用于购买、销售、支付和支持的独立应用程序。期望用户创建多个用户帐户来访问这些应用程序是很麻烦的，更不用说记住他们的登录凭证了。这就是单点登录(SSO)的用武之地。使用 SSO，用户只需创建一个帐户，就可以使用它访问所有应用程序。

### 2.多因素认证

多因素身份验证(MFA)在密码之上增加了额外的安全层，以确保用户帐户免受黑客攻击。MFA 需要一个额外的身份验证因素，例如通常通过短信或电子邮件发送给用户的一次性密码(OTP)。例如，像 [WSO2 Identity Server](https://wso2.com/identity-server/) 这样的解决方案允许组织使用 SMS OTP、电子邮件 OTP、验证器应用程序和合格的生物识别阅读器作为额外的身份验证因素。这提供了更高的安全性，因为即使黑客获得了用户的密码，他们也无法访问用户帐户。然而，并不是所有的客户都喜欢经历必须进行身份验证的麻烦，这就引出了下一点。

### 3.自适应认证

由于 MFA 会吓跑很多客户，组织可以使用 adaptive authentication 在用户体验和安全性之间取得平衡。这决定了是否应该根据用户的属性(如 IP 地址(位置)、用户角色(管理员、普通用户等))提示用户通过其他因素进行身份验证。)和危险系数。 [WSO2 Identity Server](https://wso2.com/identity-server/) 使用 WSO2 Identity Server 分析来分析用户行为，并决定是否应通过其他因素提示用户进行身份验证。

### 4.社交登录

我们承认吧。没人喜欢注册新账户了。我们可以跳过这一步，允许用户使用他们的社交媒体账户登录，如脸书和 Twitter，或者其他登录方式，如 Hotmail 或 Google ID。像 WSO2 Identity Server 这样的解决方案可以集成包括微软、谷歌、脸书、Twitter、雅虎和 Office 365 在内的流行应用程序，并且允许组织添加自定义社交登录。

![](img/7c62c5cea105b4379bfdfc8998586685.png)

社交网站允许用户携带他们的社交 id。
*图片来源:[Mourizal za tiva](https://unsplash.com/photos/90JFNMyBeek)—Unsplash*

### 5.无密码认证

很难记住密码。这导致了一些危险的行为，例如不要在应用程序间使用多个密码，将密码写在不安全的地方，以及使用容易被黑客侵入的简单密码。无密码身份认证解决了这个问题，它允许客户通过其他因素进行身份认证，如 OTP、指纹和眼睛扫描等生物特征以及电子邮件链接。

![](img/811dcd27e6f4f06a224f1637a5286bf8.png)

眼睛扫描用于验证身份。
*形象信用:[品牌&人物](https://unsplash.com/photos/sWQrD5s0fWc) — Unsplash*

### 6.自行注册

客户应该能够创建自己的帐户，不像在传统的 IAMs 中，帐户是由其他人为用户创建的。

这些因素将允许新加入 CIAM 的组织开发一个 CIAM 解决方案，提供安全和良好用户体验的健康结合。

## **第二级:对 CIAM 有中等了解的组织**

这些组织可能会探索不同的方式来吸引新客户。在这一阶段，CIAM 的一家供应商将与他们合作，帮助他们更好地分析行业趋势和市场竞争。在这里，它有助于理解法规和遵从性的重要性，这些法规和遵从性可以为组织带来竞争优势。这就是有经验的技术供应商发挥作用的地方，因为他们丰富的经验可以帮助指导客户完成他们 CIAM 之旅的下一阶段。

![](img/160c81cebf9cdd1785b0b52e2c146441.png)

组织应该与有经验的 CIAM 供应商合作，以决定他们的下一步行动。
*图片信用: [Linkedin 销售解决方案](https://unsplash.com/photos/46bom4lObsA) — Unsplash*

客户数据对组织来说非常重要，这些数据的泄露会给他们带来经济损失并损害他们的声誉。最近的例子包括泄露 120 万个 [GoDaddy](https://techcrunch.com/2021/11/22/godaddy-breach-million-accounts/) 账户的电子邮件地址，泄露[1.06 亿名泰国游客的个人信息和护照细节](https://www.comparitech.com/blog/information-security/thai-traveler-data-leak/)，以及[黑客通过其 CRM 软件访问 USCellular 的客户数据](https://www.bleepingcomputer.com/news/security/uscellular-hit-by-a-data-breach-after-hackers-access-crm-software/)。

此外，组织应该合乎道德地收集、处理和存储客户数据。这就是通常所说的数据隐私。未经用户同意或未详细说明为何需要信息，不应收集数据。用户也应该能够要求公司删除他们的数据。

![](img/add69e3f711943fe830121e343496639.png)

数据泄露会导致重大的财务和声誉问题。
图片来源:[安德里亚·皮亚卡迪奥](https://www.pexels.com/photo/crop-businessman-signing-contract-in-office-3771097/) —佩克斯

一个好的 CIAM 解决方案将满足这些隐私要求，同时能够审计客户数据的使用。不尊重客户的数据隐私会让组织陷入困境。

## **第三级:在 CIAM 拥有丰富经验的组织**

这些组织将已经拥有符合数据隐私法规的功能性 CIAM 解决方案。在这方面，CIAM 解决方案可以更进一步，提供一种强大的方式来帮助他们提供出色的用户体验。

这意味着 CIAM 解决方案应该支持任何环境中的部署，包括内部环境、云环境或混合环境。CIAM 解决方案还应该确保与各种部署环境的集成尽可能顺畅，并且该解决方案支持与市场上各种其他产品的集成。

这些组织的用户群可能会呈指数级增长。因此，CIAM 解决方案应该是可扩展的，以满足这种增长。该解决方案应该使企业能够方便地访问用户信息，并且这些信息应该是最新的。

![](img/2d82252c20f6cf416c512d399bbc37db.png)

CIAM 解决方案必须可扩展，以应对显著的增长。
图片来源: [Pixabay](https://www.pexels.com/photo/abstract-close-up-cobweb-connection-276502/) —像素

此外，CIAM 解决方案应该支持访问控制，以限制对客户信息的访问。这确保了客户信息只对那些需要它的人可用。

## **结论**

我们已经了解了三种类型的组织，以及它们在实施 CIAM 时需要考虑的事项。公司可以通过考虑其他方面来进一步提升他们的 CIAM 解决方案，例如提供更简单的生物认证、自动化用户报告、保护所有端点免受暴力和网络钓鱼攻击、自动化用户报告以及提供分析和数据可视化。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>