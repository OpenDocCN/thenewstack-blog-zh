# 微软:在你的公司实现开源的 5 种方法

> 原文：<https://thenewstack.io/microsoft-5-ways-to-make-open-source-a-reality-at-your-company/>

斯托米·彼得斯

斯托米·彼得斯是微软开源项目办公室主任。她与微软的人员和团队合作，帮助确保微软使用开源软件并为其做出贡献，使世界有可能通过开源软件取得更多成就。在加入微软之前，Stormy 在 Red Hat 担任过开源和开发方面的领导职务，她在 Cloud Foundry Foundation 担任开发人员关系副总裁，在 Mozilla 担任开发人员关系主管。此前，她担任 GNOME 基金会的执行董事，并在 OpenLogic 建立了他们的 OpenLogic 专家社区。斯托米毕业于莱斯大学，获得计算机科学学士学位。

开源已经成为几乎每个公司的技术战略的关键，开源在每个行业的开发者中的使用持续增长。GitHub 上现在有超过 5600 万开发者，开源项目的创建同比增长了 40%。在开发过程中使用开放源码增加了上市时间，降低了拥有成本，并提高了软件质量。

虽然开源已经成为一种趋势，但是许多公司都在努力让他们的员工安全地使用开源软件，为客户提供安全的解决方案，并有效地为开源软件做出贡献。公司需要在制定开源政策的同时保持员工授权和自主权之间取得平衡。

在微软，我们在过去的几年里进行了重大的转变，使我们的开发人员能够在他们的常规开发周期中无缝地使用开源软件。这不是快速或容易的，是自上而下和自下而上的文化变革的结果。

今天，我们的开源工作集中在我们的开源项目办公室(OSPO)。如今，许多公司都在寻求建立 OSPO，我们希望分享我们在 OSPO 之旅中的一些经验和最佳实践，这样我们就可以继续学习，共同成长。

**1:建立跨职能工作组。**成功的关键之一是在整个组织内合作。当与对创建 OSPO 感兴趣的客户交谈时，他们通常会问的第一个问题是 OSPO 应该在哪里？在法律上？在工程方面？答案是你需要和他们所有人一起工作。微软有一个跨职能小组，我们的法律部门、市场营销、Azure CTO 办公室、业务部门、工程工具等都积极参与其中。这个跨职能小组有助于指导政策并推动整个组织的变革。每个公司都有不同的结构，OSPO 通常源于有人看到的需求。无论 OSPO“坐”在组织的哪个位置，从不同的业务职能引入利益相关者都是很重要的<wbr>。一年后，重新评估 OSPO 是否在正确的地方，是否有正确的人参与进来。

**2:记录政策并找到你的拥护者。**微软的开源软件政策在我们的内部网上为所有员工详细记录。我们还有一组来自整个组织的专家可以回答问题。为了帮助其他人开始，我们公开分享[我们政策的摘要](https://opensource.microsoft.com/program/.)。我们定期更新我们的政策，由一个跨组织的开源倡导者小组审查，然后由我们的开源执行委员会审查，开源执行委员会是一个由来自微软各业务部门的高管组成的小组，他们相互分享他们的开源战略和最佳实践。除了政策方面的投入，这些拥护者还帮助将<wbr>信息传播回他们的团队，帮助鼓励开源软件的使用，并在需要时为他们的同行提供指导。例如，微软的 Dapr 团队最近在他们的决策中纳入了社区反馈，这使他们优先考虑简化 API 的工作，以检索应用程序机密-这项工作不在他们当前计划的工作周期中，但社区主张这将有助于解决许多开发人员的挑战，因此团队调整并优先考虑 API，这也导致了客户的增加。

**3:通过政策和工具给予员工自主权<wbr>。**OSPO 的角色是制定明确的政策，用知识和工具来赋予员工权力，让人们容易做正确的事情。OSPO 在那里提供培训并促进团队之间的对话，然后允许每个开发人员和商业<wbr>团队决定如何将开源软件整合到他们的商业战略中。在微软，我们所有的团队都使用开源软件，但是他们如何贡献以及他们决定开源的内容在开发者工具团队和微软 Office 中可能会有所不同。工具还提供了<wbr>自主性，让员工更容易有效和合规地使用开源。当微软的一个团队创建一个新的回购协议时，一个向导会引导他们完成创建过程，设置良好的行为准则和支持流程，并启动内部所需的任何法律和业务审查。我们已经将我们的一些工具和流程开源为项目，例如[clear defined](https://clearlydefined.io/)或者与 Linux 基金会合作的 [OpenChain](https://www.openchainproject.org/) 。我们[列出了我们的开源工具](https://opensource.microsoft.com/program/#program-tools)，此外，我们使用并合作了一个名为 Tern 的开源软件项目，作为我们识别容器中组件的内部工具的一部分，以确保我们能够快速纠正漏洞。

向他人学习并与其合作。加入团体和基金会，为你的旅程提供帮助。开源本质上是社区驱动的，向他人学习和分享最佳实践只会加强你自己的开源项目。我们<wbr>参与了各种开源行业团体和基金会，如开源倡议、Linux 基金会、Eclipse 基金会、云计算基金会等。我们还积极参与 TODO 小组，该小组由 OSPO 负责人组成，每两周会面一次，讨论 OSPO 的最佳实践，我们最近就保护开源供应链进行了对话，我们分享了各自实施的实践以及我们可以共同创建的工具，以解决常见问题。去年，微软联合 GitHub、谷歌、IBM 和其他公司创建了[开源安全基金会](https://nam02.safelinks.protection.outlook.com/?url=https%3A%2F%2Furldefense.proofpoint.com%2Fv2%2Furl%3Fu%3Dhttps-3A__nam06.safelinks.protection.outlook.com_-3Furl-3Dhttps-253A-252F-252Fcloudblogs.microsoft.com-252Fopensource-252F2020-252F08-252F03-252Fmicrosoft-2Djoins-2Dopen-2Dsource-2Dsecurity-2Dfoundation-252F-26data-3D04-257C01-257CStormy.Peters-2540microsoft.com-257C12f2452eeac948c7900e08d8e02a4266-257C72f988bf86f141af91ab2d7cd011db47-257C1-257C0-257C637505819389297973-257CUnknown-257CTWFpbGZsb3d8eyJWIjoiMC4wLjAwMDAiLCJQIjoiV2luMzIiLCJBTiI6Ik1haWwiLCJXVCI6Mn0-253D-257C1000-26sdata-3DESt4l1SwSKg5oxmdGfOhF2WudWJdOncla77eW855wpE-253D-26reserved-3D0%26d%3DDwMGaQ%26c%3DeuGZstcaTDllvimEN8b7jXrwqOf-v5A_CdpgnVfiiMM%26r%3DKt6IbW8z7lZIqJGcu3dRV9VNgDSGTNqdBQS7YG5OOFo%26m%3DKotnHE_CT_koX1BsI5QuoPuA-ZgSH9H5Xcxl-fKzh8E%26s%3DDAgN6TunVPUs2BkwKSv-cEb56dh6-r1c8BpLboOwaE4%26e%3D&data=04%7C01%7Cmsacchi%40we-worldwide.com%7C55f18b2e58bc4bcd542108d8f3882d17%7C3ed60ab455674971a5341a5f0f7cc7f5%7C0%7C0%7C637527113508911638%7CUnknown%7CTWFpbGZsb3d8eyJWIjoiMC4wLjAwMDAiLCJQIjoiV2luMzIiLCJBTiI6Ik1haWwiLCJXVCI6Mn0%3D%7C1000&sdata=a01RK4bh2CXNfGHjUVJadLwEn0ttGIWb8XjXSJDUf6M%3D&reserved=0) (OpenSSF)。该组织正在利用资源帮助开发人员识别开源项目的安全威胁，提供教育和学习资源，并寻找加快漏洞披露的方法。

提供奖励和激励。持久的文化变革需要与奖励和补偿保持一致。在每次绩效评估中，微软员工都被要求描述他们是如何授权和建立在他人工作的基础上的——这与开源实践非常一致。此外，开源是微软官方认可的开发人员技能的核心方面。除了表彰个人的努力之外，我们还召集了一个来自整个公司的“开源冠军”小组，他们相互分享和学习开源最佳实践，并将这些学习成果带回他们的小组。这为他们提供了跨组织的可见性，同时提高了他们的技能，并使他们能够利用自己的知识来帮助他人。

开源几乎是每个公司技术战略的核心，所有企业都应该考虑如何让他们的开发者能够有效和安全地使用软件，这一点很重要。我们每天都在继续学习和成长，我们分享我们的学习成果，希望能帮助其他人起步。您可以访问我们的[开源网站](https://nam02.safelinks.protection.outlook.com/?url=https%3A%2F%2Furldefense.proofpoint.com%2Fv2%2Furl%3Fu%3Dhttps-3A__opensource.microsoft.com_%26d%3DDwMGaQ%26c%3DeuGZstcaTDllvimEN8b7jXrwqOf-v5A_CdpgnVfiiMM%26r%3DKt6IbW8z7lZIqJGcu3dRV9VNgDSGTNqdBQS7YG5OOFo%26m%3DKotnHE_CT_koX1BsI5QuoPuA-ZgSH9H5Xcxl-fKzh8E%26s%3Dm0OOM8aOc5fI1TZmcCiFpMOPhM5y7WvB3V3v5jHVw2Q%26e%3D&data=04%7C01%7Cmsacchi%40we-worldwide.com%7C55f18b2e58bc4bcd542108d8f3882d17%7C3ed60ab455674971a5341a5f0f7cc7f5%7C0%7C0%7C637527113508921636%7CUnknown%7CTWFpbGZsb3d8eyJWIjoiMC4wLjAwMDAiLCJQIjoiV2luMzIiLCJBTiI6Ik1haWwiLCJXVCI6Mn0%3D%7C1000&sdata=EIE7b37boocoF9Z8jVoml6vIuxW43pAx%2FET%2FlSX0EUY%3D&reserved=0)，该网站提供了我们开源活动和项目的详细信息，以及我们用来指导我们内部开源项目的政策、工具和资源。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>