# Red Hat 将 Ansible 扩展为一个完整的 IT 自动化平台，提供协作、分析

> 原文：<https://thenewstack.io/red-hat-expands-ansible-into-a-full-it-automation-platform-with-collaboration-analytics/>

Red Hat 正在扩展其 Ansible enterprise 包，以应对 IT 自动化使用增加带来的新需求，并解决如何进一步使用可编程基础设施来加速运营的可能性。

在该公司今年在亚特兰大举行的年度 [AnsibleFest](https://www.ansible.com/ansiblefest) 上，红帽发布了[红帽 Ansible](https://www.ansible.com/products/automation-platform) [自动化平台](https://www.ansible.com/products/automation-platform)，这是一个企业就绪集成 Ansible 功能的集合，将于 11 月份发布。它建立在 Red Hat Ansible Automation package 的基础上，具有围绕协作和分析的新组件。几周前[宣布](https://thenewstack.io/context-new-versions-of-hashicorps-terraform-cloud-for-teams-and-for-governance/)，就像 HashiCorp 在自己的 Terraform 云服务中构建协作功能一样，Red Hat 也在解决因 IT 自动化使用增加而出现的新需求。

Red Hat 的管理副总裁 Joe Fitzgerald 在一次采访中解释说，Red Hat 已经见证了围绕 Ansible 的 IT 自动化的爆炸。不仅信息技术的使用方式正在进入新的领域，如安全和网络，而且信息技术的使用深度也在增加。现在所做的只是可能做到的一小部分，因为 Ansible-ites 开始探索可编程基础设施的新用途。

[![](img/aa79e3b98e81af14647258e4b88bd0a7.png)](https://cdn.thenewstack.io/media/2019/09/ea9fb404-fitzgerald.jpg)

红帽公司的乔·菲茨杰拉德。

在会议的主题演讲中，摩根大通的克里斯多佛·费斯塔解释了这家金融服务巨头是如何将公司的许多日常工作自动化放在首位的。该公司有 500 名开发人员正在致力于业务流程自动化，这一举措带来了诸多好处，其中之一是恢复时间缩短了 98%。“过去需要 6-8 个小时(才能恢复)的事情，现在只需要 2-5 分钟，”他说。

此外，在主题演讲中，微软网络工程师 [Bart Dworak](https://github.com/BDworak) 解释了该公司如何使用 Ansible 进行基于事件的自动修复(“自我修复”)，该技术将状态设置为所需的状态配置，其中宣布了系统的理想状态，系统本身会努力使自己达到该状态。“网络工程师正在成为网络开发者，”他说。

Fitzgerald 解释说，这种增加的使用带来了自己的挑战，该平台试图通过“协作可扩展性”来解决这一问题。“团队如何共享内容。在一个非常大的组织中，可能有 300 部部署了 NGINX 的行动手册。大家都在用哪个？我怎么能告诉人们，‘别造了。我已经有一个了。"

“我们试图通过一个平台来提供一系列服务，帮助人们在更大范围内、跨团队、跨组织地管理内容，”他说。

## 自动化所有的事情

作为一个自动化引擎， [Ansible](https://github.com/ansible) 因其易用性和可扩展性而备受推崇，红帽产品领域工程师 [Jake Jackson](https://www.ansible.com/blog/author/jake-jackson) 在后来的技术会议上指出。它使用基于 YAML 的简单声明性语言。用户可以创建针对特定资源集或资源组运行的模块。可以创建行动手册来描述一组可用于库存的策略。Ansible 可用于管理任何可通过网络寻址的部署。

红帽 Ansible 自动化平台包括核心的红帽 Ansible 引擎、红帽 Ansible 塔、红帽网络自动化，这些都在之前的红帽 Ansible 自动化包中。新功能包括:

*   Content Collections 是一种新的打包格式，它简化了对敏感内容的管理、分发和消费。该公司希望第三方软件供应商和内部开发团队使用 collection 来帮助部署复杂的工件。一个集合可以由可翻译的模块、插件、角色和剧本组成，集合将存储在…
*   **自动化中心，**各种红帽认证内容的集中存储库。思科、F5、谷歌云、微软和 NetApp 等公司已经启动了首批项目。
*   **Automation Analytics** ，一种显示具体自动化操作如何详细执行的服务，包括模块和资源的统计和数据。

该软件还包括 Ansible 企业版的最新版本，[红帽 Ansible Tower](https://www.ansible.com/products/tower) 。3.6 版支持 Ansible 内容集合，以及基于来自 GitHub/GitLab 的源代码推送和其他源代码控制事件启动部署的能力(通过 Webhooks)。

8 月，分析公司 Forrester 在其[基础设施自动化平台综述](https://www.forrester.com/report/The+Forrester+Wave+Infrastructure+Automation+Platforms+Q3+2019/-/E-RES146715#)、[中强调了 Red Hat Ansible Automation，称赞了该公司的路线图以及该软件包与其他自动化工具的兼容性](https://www.redhat.com/en/about/press-releases/red-hat-recognized-leader-independent-research-firm-infrastructure-automation-platforms-evaluation?source=pressreleaselisting)。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>