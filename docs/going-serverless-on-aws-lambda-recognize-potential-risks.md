# 在 AWS Lambda 上没有服务器？识别潜在风险

> 原文：<https://thenewstack.io/going-serverless-on-aws-lambda-recognize-potential-risks/>

无服务器计算允许开发人员构建和运行应用程序，而无需担心基础设施。无服务器计算服务消除了容量供应和修补等基础架构管理任务，并提供自动可扩展性、高可用性和精细的按使用付费计费模式。

[亚马逊网络服务(AWS) Lambda](https://aws.amazon.com/lambda/) 是一个流行的事件驱动的无服务器计算平台，允许用户运行代码，而无需管理基础设施。在 Lambda 中，代码存储在代码部署包中。与代码的所有交互都通过 Lambda API(应用程序编程接口)进行，没有从服务外部直接调用函数。Lambda 函数有许多用例，但主要的一个是响应和处理事件。虽然它因其提供的许多好处而在 DevOps 社区中很受欢迎，但它也带来了一系列常常被忽视的安全风险。

## **为什么在使用 AWS Lambda 时要考虑安全性？**

使用 AWS Lambda 时，安全性是一个关键的考虑因素，主要有三个原因。

1.  **AWS Lambda 函数用于构建应用:** AWS Lambda 提供高度可靠的服务，允许用户放心地部署[无服务器](https://thenewstack.io/serverless/)应用。Lambda 适用于许多行业的关键任务应用。从媒体、零售和消费服务到银行和金融服务以及其他受监管行业，各种各样的客户都在利用 Lambda。托管运行时环境模型使 Lambda 能够管理运行无服务器工作负载的大部分实现复杂性。危及 Lambda 功能的安全事件可能会对您业务的几个关键方面造成大范围的破坏。
2.  **AWS Lambda 函数处理敏感数据:**敏感数据包括可识别个人身份的个人身份信息(PII)，如客户姓名、社会安全号码、驾照号码、财务信息和医疗记录。如果这些数据被未授权方访问或修改，可能会对个人和您的企业造成严重损害。
3.  **AWS 采用安全责任共担模式:**安全和合规是 AWS 和客户之间的[共担责任](https://thenewstack.io/understand-the-aws-shared-responsibility-model-for-kubernetes/)。这意味着[亚马逊网络服务(AWS)](https://aws.amazon.com/?utm_content=inline-mention) 拥有“云的安全性”并负责保护运行 AWS 云中提供的所有服务的基础设施。另一方面，“云中的安全性”始终是客户的责任。例如，对于抽象服务，如亚马逊 S3 和亚马逊 DynamoDB，AWS 运行基础架构层、操作系统和平台，客户访问端点以存储和检索数据，同时客户处理管理其数据(包括加密选项)、分类其资产以及使用身份和访问管理(IAM)工具来应用正确的权限。对于 Lambda，数据完整性和机密性是 AWS 客户的责任。因此，AWS 及其客户有共同的责任来确保 Lambda 实现的持续安全性，确保它们免受潜在的安全威胁。

## 这里可能存在哪些安全风险？

让我们检查一下不安全的 Lambda 函数可能面临的一些安全风险:

### **认证和访问控制**

使用无服务器函数构建的应用程序包含许多 AWS Lambda 函数。每个程序功能都是不同的，都有特定的用途。当拼接在一起并进行编排时，这些功能创建了总体业务逻辑，其中服务器的配置和管理对最终用户是不可见的。一些功能收集、存储和动态显示实时数据，而其他功能连接支付和 API 网关以自动化交易。

此外，一些函数“消费事件”或订阅触发函数运行的事件。触发 Lambda 函数的事件几乎可以是任何事情，从通过 API Gateway 的 HTTP 请求、由 EventBridge 规则管理的时间表、IoT(物联网)事件或 S3 事件。

换句话说，当使用 AWS 作为云提供商时，“事件”是 AWS 中触发 Lambda 功能的任何事件，如 S3 桶上传、SNS 主题或通过 API Gateway 创建的 HTTP 端点。您可以想象，由于每个功能具有不同的预期结果，由不同的事件触发，并且没有其他活动部分的概念，因此会产生安全复杂性。

无服务器架构中的身份验证失败是由于[身份和访问控制管理](https://thenewstack.io/best-practices-for-securing-identity-and-access-management-on-amazon-web-services/)应用不当造成的，尤其是在多服务、事件、触发器和无连续流的情况下。

任何未经验证和未经授权的函数访问都可能破坏系统的业务逻辑和执行流程。应用严格的 AuthN+AuthZ 方案，为每个功能、事件类型和触发器提供强大的访问控制，必须小心管理，以杜绝安全漏洞的可能性。

### **功能事件-数据注入**

在 AWS 上，Lambda 函数必须连接到来自几个触发其执行的源的事件。过多的事件源扩大了攻击面。保护 Lambda 函数免受事件数据注入变成了一项复杂的任务。事件的类型及其来源决定了事件输入是否受攻击者控制。某些类型的事件数据可以抵抗攻击者的破坏。

例如，数据库事件的标准通知。但是其他如 HTTP/S API 调用更容易被恶意劫持。无服务器架构中常见的几种类型的注入缺陷有操作系统(OS)命令注入、函数运行时代码注入(Node.js/JavaScript、Python、Java、C#、Golang)、SQL 注入、NoSQL 注入和发布/订阅消息数据篡改(MQTT 数据注入)。

### **身份访问管理**

对于 Lambda 函数，AWS 管理底层基础设施和应用程序平台、操作系统和执行环境。DevOps 团队处理 SDLC(软件开发生命周期)中的持续安全性，从代码安全性开始，以及对 Lambda 服务及其无服务器功能的身份和访问管理。

根据经验，授予权限和访问应该遵循“最小特权原则”，这实际上意味着 Lambda 函数只应该被赋予那些对于执行它们的预期逻辑来说必不可少的特权。

在现实世界中，这说起来容易做起来难。例如，如果您需要为一个需要访问 DynamoDB 服务的 Lambda 函数编写 IAM 策略，您需要遍历 50 多个不同的 DynamoDB 权限，并只授予 Lambda 函数需要在其预期逻辑上执行的权限集的最低特权访问权限，而不授予其他权限。您还必须使用允许在特定条件下授予访问权限的条件键。

现在考虑另一个非常现实的场景，其中您的无服务器应用程序由几十个(如果不是几百个)不同的 Lambda 函数组成。庞大的数量使得管理功能权限和角色成为一项艰巨的任务。如果您对所有 Lambda 函数依赖单一的权限模型或安全角色，您将无意中授予所有函数完全访问权限，从而产生安全风险。

另一个需要注意的问题是，IAM 策略配置错误可能会导致 IAM 凭据泄漏。Lambda 函数在被授予 IAM 角色时使用临时安全凭据。当该函数执行时，它从 AWS 安全令牌服务接收访问令牌。恶意获取令牌访问权的攻击者可以从 Lambda 环境外部远程模拟该函数，并检索任何可用的资源。

### **记录和监控**

无服务器监控允许开发人员获得关于每个执行和事件的重要见解。AWS 提供日志服务 CloudTrail 和监控服务 CloudWatch。创建帐户后，AWS CloudTrail 在每个 AWS 帐户上默认启用。当 AWS Lambda 中发生受支持的事件活动时，该活动将与其他 AWS 服务事件一起存储在 CloudTrail 事件中的“事件历史”控制台中。

Lambda 代表您自动监控功能，并通过 Amazon CloudWatch 报告指标。从安全角度来看，记录和监控安全相关事件以实时检测和降低风险至关重要。虽然这两个工具都非常有价值，但对于一些开发人员来说，这些工具的开箱即用配置并不总是有助于捕获为您的应用定制的整个安全事件审计跟踪。

## **确保安全是共同的责任**

AWS 为其用户提供了一套强大的安全控制。但是，如何充分利用这些内置功能取决于用户。AWS Lambda 控制台允许您查看和管理 Lambda 函数，包括它们的配置文件和 IAM 角色，从而帮助保护您的 Lambda 函数。然而，为了消除 Lambda 函数中继承漏洞的可能性，重要的是要确保 Amazon Lambda 中只部署来自可信发行商的经过验证的代码，并且剔除易受攻击的函数。这些是更安全部署的关键。

## **Panoptica 保护 AWS Lambda 无服务器功能**

很明显，AWS Lambda 无疑是无服务器应用程序的核心。Lambda 函数的“无状态”特性与底层基础设施没有任何关联，这使得您可以专注于自己最喜欢做的事情——开发代码。

Cisco Panoptica 扫描 AWS 帐户中的无服务器功能，并评估它们的安全问题和漏洞。在连接到您的 AWS 帐户后，Panoptica 会扫描您的无服务器功能的安全问题和漏洞，并为它们分配一个风险分数，根据分数对它们进行排名。风险评分基于功能代码和云配置元数据，并考虑以下因素:

*   功能的认证和授权，验证已识别和授权的功能触发器。
*   开源包或依赖关系中的代码漏洞。
*   函数代码或环境变量中存在的秘密，如密钥和密码。
*   授予函数的权限不适当或过多。
*   公开访问和访问可能成为渗透目标的数据源的功能。
*   失效或不活动的功能。

您可以随时手动触发扫描，也可以安排扫描定期运行。还有什么？配置策略，自定义适用于您环境的风险类型。如果 Panoptica 的风险评分上升到不可接受的水平，您可以将其设置为终止进程并向您发出警报，让您确切知道哪个无服务器功能触发了警报。

对于核心云功能工件的签名和验证，如图像或代码，请使用我们的开源工具 [FunctionClarity](https://github.com/openclarity/functionclarity?utm_source=website_newstack&utm_campaign=tns3_aws_lambda&utm_medium=paid&utm_content=panoptica) 。它的代码签名功能确保了函数的信任和完整性，允许防篡改和不可否认。

[免费试用 Panoptica](https://panoptica.app/sign-up?utm_source=website_newstack&utm_campaign=tns3_aws_lambda&utm_medium=paid&utm_content=panoptica)并参考本[快速入门](https://www.panoptica.app/quick-start?utm_source=website_newstack&utm_campaign=tns3_aws_lambda&utm_medium=paid&utm_content=panoptica)指南，立即将 Panoptica 连接到您的 AWS 云帐户。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>