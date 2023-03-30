# SAP 在 K8s 和云功能上搭建低代码平台

> 原文：<https://thenewstack.io/sap-builds-a-low-code-platform-on-k8s-and-cloud-functions/>

拉斯维加斯——新的 [SAP Build](https://news.sap.com/2022/11/business-expertise-sap-build-sap-teched/) ，一个基于[SAP Business Technology Platform](https://www.sap.com/products/technology-platform.html)(BTP)的低代码服务，在该公司 11 月的 TechEd 会议上宣布，使用 Kubernetes 作为其底层架构来扩展其多云服务。

与 SAP Build 集成的是一个自主开发的云功能平台，用于扩展为 [SAP](https://www.sap.com/index.html?utm_content=inline-mention) 低代码平台提供业务逻辑的能力。SAP Build 使用基于元数据的方法和云功能，为业务人员构建应用程序、自动化流程和网站提供粒度服务。

BTP 是 SAP 为应用程序开发、数据分析和一系列其他服务开发的整体平台。SAP 已经停止使用 [SAP 云平台作为品牌名称](https://en.wikipedia.org/wiki/SAP_Cloud_Platform)。但是，SAP 云平台的功能内置于 SAP BTP 系统中。

SAP Build 的目的是为业务用户提供拖放功能，以构建通过 IT 控制的应用程序。SAP 首席技术官兼执行董事会成员 Juergen Mueller 说，IT 控制是与其他缺乏边界和 IT 治理的低代码平台的区别。

SAP 产品开发高级副总裁 Bhagat Nainani 说:[元数据定义了 SAP 构建中的业务逻辑。SAP 团队构建了其可视化云功能能力，以在最终由 Kubernetes 集群管理系统](https://people.sap.com/bhagat.nainani) [Gardener](https://thenewstack.io/growing-kubernetes-at-scale-with-open-source-project-gardener/) 管理的容器中交付逻辑，这是该公司为处理其 Kubernetes 集群而构建的一个开源项目。

可视化云功能允许用户通过前端用户界面定义数据模型。用户将描述符定义为元数据，存储在工件存储库和相关的数据库中。SAP 表示，作为运行数据库服务器的软件，其主要功能是存储和检索应用程序请求的数据。然后，元数据被封装在容器中，跑步者将这些容器推送到 Kubernetes 集群。

集群运行在多种云服务和 SAP 业务技术平台上。

## 解释元数据的运行程序

BTP 的基金会大量使用库伯内特斯。直到一年前，SAP 还拥有低代码能力，但没有通过添加可视化云功能获得的连接部分和持久性。此前，通过收购 [AppGyver](https://www.appgyver.com/) ，SAP 有了一个可以与 [Firebase](https://thenewstack.io/firebase-suite-google-fires-new-mobile-dev-powers/) 或其他数据库一起运行的模型，但进一步的后端逻辑仍然需要部署定制代码。

“描述符就是描述逻辑的东西，”奈纳尼说。然后元数据在跑步者身上运行。然后运行者将元数据原封不动地保存在一个容器中。”

Nainani 说，runner 是一个理解元数据的 Node.js 映像。它就像元数据的解释器，允许它提供所描述的功能。元数据包含后端功能的声明性描述，允许 Node.js 映像动态地将自身转换为 API 服务器，其行为如元数据描述符中所示。

SAP 构建团队称“描述符”可能比元数据更准确。描述符定义了由 UI 创建的应用/后端做什么，然后由运行时解释，以其可执行的形式产生最终的应用/云解决方案。设计时以 JSON 格式编辑元数据/描述符。没有特定的编码

在这种方法中，SAP 为构建、测试、部署和运行低代码应用程序提供了托管解决方案。

## 增强企业用户的能力

在 TechEd 的主题演讲中，穆勒表示，分析公司 IDC 预测，到 2025 年，开发人员将短缺 400 万人。答案是让业务用户自己构建他们组织需要的应用程序。

Mueller 说，SAP Build 通过将业务用户与开发人员和 IT 团队结合起来，为他们提供支持。开发团队使用 SAP App Studio，一个集成开发环境(IDE)来构建组件，业务用户将这些组件集成到他们的 web 和移动应用程序中。

“它还可以通过开发在所有应用程序中实施一致的治理和生命周期管理能力，”穆勒说。通过这种方式，IT 团队可以确信企业部署的所有应用程序都满足必要的安全性和治理要求

SAP Build 将迎合了解 SAP 系统的人， [Julia White，](https://www.linkedin.com/in/juliawhite2/)首席营销和解决方案官和 SAP SE 执行董事会成员说。White 说，他们看到企业希望重复性任务更加自动化，这在他们的整体供应链管理中显而易见。

“大多数人在他们的供应链中使用几个不同的系统，”怀特说。“他们不仅仅是在整个端到端供应链中使用单一来源。因此，运行供应链系统的人可能会说，“嘿，我需要这些系统之间的东西，”或者“我需要一些可以跨越这些系统的东西。”"

## 案例研究:Qualtrics 如何使用 SAP Build

大多数商务人士使用电子邮件和电子表格来尝试和完成手工任务。但是有一些情况下，离线系统就是不切实际。

Qualtrics 是一家制作调查工具的软件公司。它使用 SAP Build，但从另一个提供商的低代码平台开始。该应用程序将潜在客户与 Qualtrics 平台的最终用户联系起来，在 SAP TechEd 的一次采访中，XM 倡导者、Qualtrics 的负责人斯潘塞·库克说道。

Qualtrics 团队在选择使用 SAP Build 之前构建了整个应用程序。库克不愿透露该团队之前使用的是哪家供应商。尽管如此，由于各种因素，包括安全问题和需要更清晰的应用程序业务逻辑，基于前一家供应商的平台构建的应用程序没有获得 IT 管理层的批准。

“逻辑不像 SAP Build 那样清晰，”库克说。“你可以清楚地看到流程是如何进行的。在另一个工具中，步骤被压缩了。你无法真正看到每一步都发生了什么。”

Qualtrics 在库克的指导下开发了一个非常复杂的应用程序。这项服务以一种精细的方式将人们联系起来，这是 LinkedIn 这样的服务所不能做到的。

库克说，用户下载应用程序并创建个人资料。他们提供使用案例、最喜欢的功能、他们使用该应用的时间以及集成。对于 Qualtrics，库克可以过滤数据，以显示，例如，哪些客户使用 Qualtrics 和 Salesforce。此外，库克可以添加品牌和圆形边缘等细节，使应用程序更加专业。库克说，Qualtrics 使用为低代码服务设计的 [Xano、](https://www.xano.com/)作为后端。它的 API 与 AppGyver 集成，后者现在是 SAP Build 的服务。

## 旨在扩展的服务

SAP Build 的粒度为 SAP 提供了可为客户扩展的服务。据穆勒称，这是一个拥有 2.2 亿用户的市场。SAP Build 还可以通过其 API 与第三方应用集成。

如何获得采用是 SAP Build 的大问题。低代码平台经常面临临时使用，但如果它减少了开发人员和 it 的负担，就有可能通过协作来构建广泛使用的低代码应用程序。

1992 年，史蒂夫·乔布斯在麻省理工学院斯隆管理学院做了一次著名的演讲。他是来谈论 NeXT 电脑的，这是一家开创性的硬件公司，他曾在该公司担任首席执行官。他谈到了任务关键型应用在运营中的崛起。

今天，应用程序占主导地位，但开发者构建它们。现在考验来了。商业用户会是下一波开发 app 的人群吗？这将主要取决于应用的采用、应用的复杂性以及开发应用所需的时间。SAP 仍然需要对 SAP Build 进行大量的 IT 控制，这可能会减慢开发速度，但它的复杂程度使其具有竞争力。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>