# 编码器利用多云平台加快构建时间

> 原文：<https://thenewstack.io/coder-speeds-build-time-with-multicloud-platform/>

集成开发环境(IDE)通常是一个尺寸适合一个云，但是[代码服务器](https://hub.docker.com/r/codercom/code-server)的开发者打赌开发者会选择他们新的多云、多计算 IDE 平台。

简称为 [Coder](https://coder.com/) ，这个开源平台是为那些希望为开发者提供更多工具选择，同时仍然支持按需统一供应的开发公司而设计的。

它建立在通用开发接口(SSH)上，并利用后端的开源 [Terraform](https://www.terraform.io/) 来处理供应，允许开发人员在任何计算平台上运行云 IDE，包括内部数据中心、AWS、微软 Azure、谷歌云、DigitalOcean、Kubernetes 和 Docker。它还支持 ARM、Windows、Linux 和 MacOS 工作区。

Coder 联合创始人兼首席执行官 [Ammar Bandukwala](https://www.linkedin.com/in/ammar-bandukwala-439512140/) 指出[代码空间](https://github.com/features/codespaces)(被限制为 [VS 代码](https://thenewstack.io/eclipse-open-vsx-registry-offers-open-access-to-vs-code-extensions/)并且只运行在 Azure 虚拟机上)和 [Cloud9](https://aws.amazon.com/cloud9/?trk=b6fc9015-864f-4900-8dac-c8b864c8f671&sc_channel=ps&sc_campaign=acquisition&sc_medium=ACQ-P%7CPS-GO%7CNon-Brand%7CDesktop%7CSU%7CDeveloper%20Tools%7CSolution%7CUS%7CEN%7CDSA&ef_id=CjwKCAjwk_WVBhBZEiwAUHQCmVuq4AVRDmLAUd3eB1ShsDCIrgey1ErE8g0Wb9sD2mknnRvcNrU5cxoCEeUQAvD_BwE:G:s&s_kwcid=AL!4422!3!579296419434!!!g!!) (只运行在 AWS 上)是被云提供商限制的 ide 的例子。

“历史上，云 IDE 一直被限制在一种类型的计算和一种类型的 IDE 上，”Bandukwala 告诉新堆栈。“让 Coder 真正与众不同的是，你可以在虚拟机、容器、裸机、任何种类的计算基础上的任何云上运行，然后你可以引入任何 IDE——VS code、 [Jetbrains](https://www.jetbrains.com/) 、 [Jupyter](https://jupyter.org/) 或 [Studio](https://code.visualstudio.com/) ，无论什么，真的，你都可以梦想。”

标准普尔全球市场情报公司的高级分析师杰伊·莱曼说，尽管 Coder 建立在基础设施即代码解决方案 Terraform 之上，但它不是基础设施即代码，而是旨在帮助开发者自助服务。

“他们更面向开发者，所以他们更多的是为开发者服务，而不是为 IT 运营商提供服务或能力，”莱曼说。

其实 Terraform experience 并不需要使用 Coder，其中[为 AWS EC2、Azure、Google Cloud、Kubernetes 等云平台在产品中内置了模板](https://github.com/coder/coder/tree/c6b1daabc5a7aa67bfbb6c89966d728919ba7f80/examples/templates)。

“我们可以利用 Terraform 已经建立的成千上万的资源，为我们的客户提供完整的基础设施展示能力，”Bandukwala 说。

RedMonk 的首席分析师 [Stephen O'Grady](https://www.linkedin.com/in/sogrady/) 在 Coder 的[新闻稿](https://www.businesswire.com/news/home/20220620005078/en/Coder-Announces-First-Multi-Cloud-Multi-Compute-Integrated-Development-Environment-Platform)中说:“随着开发环境变得越来越复杂并依赖于外部服务，以及对更高速度的需求，团队之间的无缝协作往往遍布世界各地，对云 ide 的需求也在增长。”。"这是编码器为之而生的机会."

## 帕兰提尔的建造时间提高 75%

大数据公司 [Palantir Technologies](https://www.palantir.com/) 部署了 Coder，试图避免它在为开发人员提供足够的计算能力方面面临的挑战，而不必购买新机器或支持虚拟机的基础设施开销。拥有大型开发团队的企业所面临的挑战之一是不可避免的配置漂移，因为开发人员会加速他们自己的环境，这反过来会产生安全问题。Coder 允许开发人员在维护集中式协议的同时自助服务虚拟机。

“只需点击几下鼠标，开发人员就可以部署新环境、请求更多资源，并更快地开始工作，”Palantir 在 6 月的一篇博客文章中写道，“远程短暂工作空间的好处”该公司报告称，构建时间缩短了 78%，Git 克隆时间缩短了 71%。它还发现 Coder 在增加安全性的同时减少了对 onboarding 的支持。

“如果你想一想，你知道，事实上一个开发者一天建造多次，他们每次都节省 30 分钟——就像对工程、速度和工程快乐的巨大改进，”Bandukwala 说。

Palantir 还指出，编码器提高了整个开发团队的贡献。

Palantir 报告说:“有了一条通向开发环境的更容易的道路，团队可以很容易地为彼此的代码库做出贡献。”“这对我们直接与客户打交道的工程师特别有用。修复小错误的开销只是请求一个工作空间，而不是下载所有的产品依赖项。”

企业订阅的价格——包括 24/7 支持、审计和空中部署，以及其他功能——没有公开列出，但 [Coder 是开源的](https://github.com/coder/coder),个人开发者可以免费试用。他没有指明 Palantir 以外的具体客户，但新闻稿称美国国防部是用户之一。

据 [Crunchbase](https://www.crunchbase.com/organization/coder) 报道，这家总部位于得克萨斯州奥斯汀的编码器公司自 2016 年成立以来，已通过三轮融资筹集了 4780 万美元。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>