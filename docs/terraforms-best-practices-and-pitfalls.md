# Terraform 的最佳实践和缺陷

> 原文：<https://thenewstack.io/terraforms-best-practices-and-pitfalls/>

[Wix](https://www.wix.com/) 是一个基于云的开发网站，用于制作 [HTML 5](https://thenewstack.io/html-5-1-replaces-html-5-w3c-standard/) 网站和带有拖放工具的移动网站。Wix 的高级开发工程师 [Hila Fish](https://www.linkedin.com/in/hila-fish/?originalSubdomain=il) 在本月早些时候于洛杉矶举行的[hashi corp](https://www.hashicorp.com/)hashi conf 全球会议上接受[新堆栈制造商](https://thenewstack.io/podcasts/)采访时表示，它适合初级用户或高级开发人员。

[Terraform 的最佳实践和缺陷](https://thenewstack.simplecast.com/episodes/terraforms-best-practices-and-pitfalls)

我们对 Fish 的问题集中在 [Terraform](https://thenewstack.io/terraform-cloud-now-offers-less-code-and-no-code-options/) 上，这是一个开源的基础设施即代码软件工具:

*   自 2018 年 Fish 开始使用 Terraform 以来，它在用途上有了怎样的演变？
*   Wix 如何充分利用 Terraform 来扩展其基础设施？
*   Wix 在 Terraform 上有哪些最佳实践？
*   使用 Terraform 要避免哪些陷阱？
*   跨团队扩展和避免重构以保持集成优雅和工作的方法是什么

[https://www.youtube.com/embed/HaBrObyU-L0](https://www.youtube.com/embed/HaBrObyU-L0)

视频

Fish 于 2018 年开始以临时方式使用 Terraform。随着时间的推移，她已经学会了如何使用它进行缩放操作。

“如果你想扩展你的基础设施，你需要以一种允许你这样做的方式使用 Terraform，”Fish 说。

Terraform 可用于临时创建一台机器作为资源，但规模取决于支持基础设施，允许工程师开发可在许多服务器上重复使用的模板。

“你需要以一种允许你尽可能扩大规模的方式来使用它，”Fish 说。

Fish 说最佳实践来自如何构建 Terraform 代码库。

这在很大程度上取决于团队以及 Terraform 的实施方式。工程师们各有各的工作方式。标准实践会有所帮助。在新团队入职时，结构化的代码库是有益的。新团队加入并使用代码库中已经存在的模型。

使用 Terraform 有哪些陷阱？

我们在录音中谈到了这一点，并更多地谈到了集成、开发人员使用 Terraform 的一些新功能，以及让人们加入 Terraform 的新版本。

用户需要学习 HashiCorp 配置语言(HCL)才能使用 HashiCorp 配置语言。Fish 说，在 Wix，该公司正在用一个开发人员无需学习 HCL 就可以使用的 UI 在后端实现 Terraform。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>