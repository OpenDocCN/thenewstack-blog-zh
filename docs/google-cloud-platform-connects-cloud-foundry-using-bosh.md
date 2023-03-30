# Cloud Foundry 如何使用 Bosh 与 Google 云平台连接

> 原文：<https://thenewstack.io/google-cloud-platform-connects-cloud-foundry-using-bosh/>

上周，谷歌[在其云平台上推出了](https://cloud.google.com/solutions/cloud-foundry-on-gcp)一项服务，使得运行基于云计算的工作负载变得非常容易。当使用可抢占的虚拟机(ML)时，该配对将允许快速供应和扩展，或者节省成本。

Cloud Foundry 的 [Bosh](https://thenewstack.io/bosh-hooks-cloud-foundry-google-cloud-platform-offers-large-scale-vm-lifecycle-management/) 部署软件有助于实现这种集成。谷歌最近完成了云提供商接口(CPI)的构建，该接口允许在[谷歌云平台](https://cloud.google.com/)上运行的云铸造工作负载管理他们的计算引擎虚拟机。

上个月，在 Cloud Foundry Europe 峰会上，我们与 Bosh GCP CLI 背后的两位谷歌软件工程师,[科琳·布里安特](https://twitter.com/ccbriant)和[埃里克·约翰逊](https://github.com/erjohnso)进行了交谈，以了解如何在谷歌和其他公共云和私有云部署中使用 CLI。收听最新一期[新堆栈制造商](https://thenewstack.io/podcasts/makers/)播客的采访:

[Cloud Foundry 如何使用 Bosh 连接 Google 云平台](https://thenewstack.simplecast.com/episodes/how-cloud-foundry-connects-with-the-google-cloud-platform-using-bosh)

采访[也可以在 YouTube](https://www.youtube.com/watch?v=AbhBzNIA49I) 上观看。

Johnson 解释说，在 Cloud Foundry 领域，CLI 是 Bosh 用来与外部云提供商(如 GCP)进行交互的模块。“Bosh 允许 Cloud Foundry 安装在云提供商上。Bosh CPI 将为 Cloud Foundry 增加虚拟机，”他说。

Bosh 负责虚拟机的生命周期管理。拥有操作系统的云铸造虚拟机被称为干细胞。“Bosh 将处理这些虚拟机的配置。stemcells 中内置了代理，允许 Bosh director 通过该代理与虚拟机进行通信和管理。”

结果是“应用程序开发人员不再关心操作系统。更重要的是他们编写应用程序的环境，”约翰逊说。

Briant 一直致力于一套 Cloud Foundry 服务代理，向 Cloud Foundry 用户公开 GCP 服务，包括 [Cloud SQL](https://cloud.google.com/sql/docs/) 、 [BigQuery](https://cloud.google.com/bigquery/) 、[机器学习](https://cloud.google.com/products/machine-learning/)和 [PubSub](https://cloud.google.com/pubsub/docs/overview) 。

“Cloud Foundry Service Broker 支持在 Cloud Foundry 中本地使用这些 GCP 服务。布里安特说:“因此，开发人员不必去[GCP]控制台(开发人员可能连访问权限都没有)或请求其他人来创建这些服务，他们只需创建实例并为他们的应用程序开发绑定它们就可以了。”。

[![barcelona](img/19403431e61caee7d8e0ebecb3ae0718.png)](https://www.eventbrite.com/e/openstack-summit-pancake-breakfast-tickets-27692501016)

[Cloud Foundry Foundation](https://www.cloudfoundry.org/)是新堆栈的赞助商。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>