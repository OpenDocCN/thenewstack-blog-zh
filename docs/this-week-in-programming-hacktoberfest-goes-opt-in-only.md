# 本周节目:黑客啤酒节只接受选择

> 原文：<https://thenewstack.io/this-week-in-programming-hacktoberfest-goes-opt-in-only/>

十月突然降临，这是每个开源维护者一年中最喜欢的时间—[Hacktoberfest](https://hacktoberfest.digitalocean.com/)！

好吧，也许不是每个维护者。

至少在过去的几年里，每年由 DigitalOcean 举办的“为期一个月的开源社区庆典”Hacktoberfest 已经成为[偶尔有争议的](https://thenewstack.io/this-week-in-programming-digitalocean-hacktoberfest-creates-spam-for-open-source-projects/)，参与者可以因为成功地对开源项目提出请求而获得一些奖励。去年，该活动似乎达到了一个转折点，因为维护者再次抱怨，数字海洋采取了一些[具体措施来限制拉式请求垃圾邮件](https://hacktoberfest.digitalocean.com/faq)，允许项目选择退出该活动，并承诺禁止用户参加该活动和其他数字海洋活动，如果他们被发现向项目发送欺诈性拉式请求。

今年，随着 Hacktoberfest 再次向我们走来，DigitalOcean 对活动进行了一些[的进一步更新，从“维护者友好的规则”开始，包括“允许 repos 选择加入 Hacktoberfest，确保只有接受的 pull 请求才计入参与者的 Hacktoberfest 目标。“嘿，如果这还不够，作为维护者，您甚至不需要提交一个拉请求就可以获得一件漂亮的 Hacktoberfest t 恤！“维护者友好”怎么样？](https://www.digitalocean.com/blog/hacktoberfest-is-back-2021)

除此之外，今年该公司还鼓励参与者通过 Open Collective 和 GitHub 赞助商直接向开源项目捐款，并将 GitLab 纳入开源爱心节，在那里“只有对 GitLab 上以[‘hack toberfest’为主题的知识库的贡献才算](https://twitter.com/john_cogs/status/1442845945390108678?s=20)”事实上，根据 [FAQ](https://hacktoberfest.digitalocean.com/faq) 的说法，这种选择加入现在是 Hacktoberfest 的默认选择，DigitalOcean 写道，它已经“改变了程序，只对以‘Hacktoberfest’为主题或标有**hacktoberfest-accepted**的存储库的拉请求进行计数。”

当然，这并不意味着人们不再尝试。

抛开对垃圾邮件的抱怨不谈——正如一位开源倡导者指出的那样，[净收益可能比你关闭那些垃圾邮件拉取请求的时间更有价值](https://twitter.com/derberq/status/1442517616464105474)——有许多开源项目已经准备好并愿意接受你的贡献。所以，如果你考虑过为开源做贡献，现在可能是时候了——见鬼，你会得到一件 t 恤。

要注册，在开始之前，请前往[注册 Hacktoberfest](https://hacktoberfest.digitalocean.com/) 。

## 本周的节目中

*   **AWS Lambda 获得 Graviton2:** 亚马逊网络服务(AWS)本周发布了几项可能令人感兴趣的公告，尤其是 [AWS Lambda 功能现在可以由 Graviton2 处理器支持](https://aws.amazon.com/blogs/aws/aws-lambda-functions-powered-by-aws-graviton2-processor-run-your-functions-on-arm-and-get-up-to-34-better-price-performance/?utm_source=feedburner&utm_medium=feed&utm_campaign=Feed%3A+AmazonWebServicesBlog+%28Amazon+Web+Services+Blog%29)。他们说，基于 ARM 的处理器可以帮助你节省高达 34%的时间，基本上是因为当谈到无服务器时，时间就是金钱。或者，正如他们所说的那样，“使用 Lambda，您将根据对您的函数的请求数量和持续时间(您的代码执行所花费的时间)来收费，粒度为[毫秒](https://aws.amazon.com/blogs/aws/new-for-aws-lambda-1ms-billing-granularity-adds-cost-savings/)。”除了成本，他们还指出，Graviton2 处理器提供了更高的性能，如果您的功能不使用特定于架构的二进制文件，您可以在 x86 和 ARM 之间切换，甚至可以测量两者之间的差异，看看哪个更好。
*   **AWS Step Functions 步骤多达 200 个服务:**对于那些使用 AWS 的低代码可视化工作流服务 [Step Functions](https://aws.amazon.com/step-functions) 进行工作流自动化的人来说，你的世界刚刚扩大，因为 [AWS Step Functions 现在支持 200 个 AWS 服务](https://aws.amazon.com/blogs/aws/now-aws-step-functions-supports-200-aws-services-to-enable-easier-workflow-automation/)，而以前只有 17 个。此外，引入 Step Functions AWS SDK 服务集成也意味着用户不再需要依赖[之前支持的 46 个服务集成](https://docs.aws.amazon.com/step-functions/latest/dg/connect-supported-services.html)，而是“可以将其状态机直接集成到具有 [AWS SDK](https://aws.amazon.com/tools/) 支持的 AWS 服务中”，从而将 AWS API 操作从 46 个增加到 9000 多个。要了解更多这一切意味着什么，请前往[博客文章](https://aws.amazon.com/blogs/aws/now-aws-step-functions-supports-200-aws-services-to-enable-easier-workflow-automation/)获取示例，或者前往[文档](https://docs.aws.amazon.com/step-functions/latest/dg/supported-services-awssdk.html)本身。
*   **AWS 推出统一 API 访问 AWS 云控制 API:** 最后对于 AWS，公司[推出了 AWS 云控制 API](https://aws.amazon.com/blogs/aws/announcing-aws-cloud-control-api/) ，一个统一 API，可以访问 AWS 和[第三方服务](https://console.aws.amazon.com/cloudformation/home?region=us-east-1#/registry/public-extensions?visibility=PUBLIC&type=RESOURCE&category=THIRD_PARTY)。AWS 云控制 API 提供了“一套标准的 API 来创建、读取、更新、删除和列出数百个 AWS 服务的(CRUDL)资源”，为开发人员提供了统一的操作和统一的查询响应。有了这五个动词，开发人员可以像创建 EC2 集群一样轻松地创建一个新的 Lambda 函数——每个动作都使用相同的动词，“将您想要创建的资源的类型和属性作为参数传递”同样，当检索关于特定服务的信息时，该信息以统一的格式返回，而不需要开发人员知道每个服务的不同名称、命名约定和 JSON 格式。

*   **希波克拉底许可证 3.0 与“许可证生成器”一起到来:**[希波克拉底许可证](https://firstdonoharm.dev/)，这是一种开源许可证，最初[于 2019 年推出，部分是为了回应](https://thenewstack.io/this-week-in-programming-should-open-source-require-freedom-at-all-costs/)移民和海关执法局(ICE)正在使用的开源项目等事情，已经[发布了希波克拉底许可证 3.0](https://www.globenewswire.com/news-release/2021/09/29/2305597/0/en/Organization-for-Ethical-Source-Launches-Hippocratic-License-3-0-Strengthening-Enforcement-and-Adding-Flexibility.html) 。这一修订被称为“对卓越的道德源代码许可证的重大修订，明确禁止使用违反人权普遍标准的开源软件”，不仅引入了强化的“执行机制”，还引入了“模块化”。伦理资源组织在一份新闻稿中写道:“核心许可证为普遍公认的人权提供保护，包括对土著权利的具体规定，但也提供关注特定领域的可选模块，如环境正义或劳工权利。”。这种方法由“许可证生成器”提供支持，“允许采纳者定制 Hippocratic 许可证，以反映他们特定社区的需求和挑战”，该许可证将于本月晚些时候推出。

https://Twitter . com/killedbygoogle/status/1442275018969321474

*   **GitLab 获得代词:**当我们谈论试图做好事的科技公司时，GitLab 宣布[用户档案将包括代词和更多](https://about.gitlab.com/blog/2021/09/30/personal-profile/)。GitLab 公司本周宣布，该公司的用户资料现在将包含[代词](https://gitlab.com/gitlab-org/gitlab/-/issues/333042)、[发音指南](https://gitlab.com/gitlab-org/gitlab/-/issues/25742)和[当地时间](https://gitlab.com/gitlab-org/gitlab/-/issues/335459)。“除了更具包容性，GitLab 还希望帮助你在回复评论时使用正确的代词，以尊重人们的身份，”他们写道，并指出其他功能也将有助于正确说出姓名，并知道何时可以期待其他人。
*   最后，微软 Azure 本周表示，它将为开源项目发放 [Azure 信用。根据](https://cloudblogs.microsoft.com/opensource/2021/09/28/announcing-azure-credits-for-open-source-projects/)[的 FAQ](https://opensource.microsoft.com/azure-credits#credits-faq) ，“任何拥有 [OSI 批准的许可证](https://opensource.org/licenses/category)和正式行为准则的开源项目都有资格申请”，巧合的是，这将排除那些使用[希波克拉底许可证](https://firstdonoharm.dev/faq/#:~:text=It%20is%20the%20intention%20and,the%20OSD%20(see%20below).)的项目。要获得一年的学分，只需前往并[申请](https://opensource.microsoft.com/azure-credits#credits-apply)。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>