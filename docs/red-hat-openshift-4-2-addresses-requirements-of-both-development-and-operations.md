# Red Hat OpenShift 4.2 解决了开发和操作两方面的需求

> 原文：<https://thenewstack.io/red-hat-openshift-4-2-addresses-requirements-of-both-development-and-operations/>

本周，Red Hat 发布了 OpenShift 4.2，今年早些时候在[发布的 OpenShift 4](/red-hats-openshift-4-adds-knative-key-coreos-features/) 中引入的许多功能都朝着正式发布的方向发展。虽然 [OpenShift 服务网格](https://blog.openshift.com/red-hat-openshift-service-mesh-is-now-available-what-you-should-know/)、 [OpenShift 无服务器](https://www.openshift.com/learn/topics/serverless)和 [OpenShift 管道](https://www.openshift.com/learn/topics/pipelines)继续成熟，后两者在 OpenShift 4.2 的技术预览版和开发者预览版中可用，但最新版本的 Red Hat 托管 Kubernetes 扩展了其多云支持，包括 AWS、Azure 和 Google 云平台，以及 OpenStack 等私有云，以及 air-gap 安装。

“我们将继续投资该平台，但会更积极地扩展到两个领域。一个是为开发者提供更高效的服务——让开发者在平台上更高效的新功能，”Red Hat 产品副总裁 Joe Fernandes 在接受 New Stack 采访时说。“其次是为管理员改进第一天和第二天的操作。这项投资可以追溯到 Red Hat 对 CoreOS 的收购，我们对运营商技术的投资，以及我们对全栈自动化和第二天监控等的投资。”

OpenShift 服务网格在 OpenShift 4 最初发布几个月后[发布](/red-hat-creates-service-mesh-for-openshift/)，它结合了开源项目 [Istio](https://github.com/istio/istio) 、 [Kiali](https://www.kiali.io/) 和 [Jaeger](https://www.jaegertracing.io/) ，以及 [Prometheus](https://prometheus.io/) 和 [Grafana](https://grafana.com/) ，以提供一个易于实现的服务网格，并在第二天的操作中强调了这一点。随着 OpenShift Serverless 和 OpenShift Pipelines 进入预览，开发人员可以分别获得 Knative 和 Tekton 的托管实例，使用 Red Hat 操作符可以轻松安装这些实例。OpenShift 4.2 中包含的 [CodeReady Containers](https://developers.redhat.com/products/codeready-containers) 也说明了 Fernandes 关于提高开发人员生产力的第一点，即作为本地开发人员环境，开发人员可以在笔记本电脑上安装预先构建的 OpenShift 环境。

OpenShift 4.2 的另一个重点是将平台带到更多地方，因此将 Azure 和 Google 云平台添加到现有的 AWS 支持中。除了多云支持，Fernandes 解释说，还有一些 OpenShift 客户对非传统操作环境有特殊要求，如空气隙网络，这些网络不连接到外部网络，使得安装和更新很困难。

“将 Kubernetes 带给企业客户意味着解决他们希望如何运行 it 的需求。我们已经从 OpenShift 3 中看到，现在继续到 OpenShift 4，政府客户和一些金融服务客户需要在空气间隙环境中运行，”Fernandes 说。“今天，我想 OpenShift 上有超过 1300 个客户，其中一些包括政府客户，他们希望在飞机、轮船、潜艇等设备上运行它。这带来了挑战。”

与任何非 SaaS 产品版本一样，让客户更新到最新版本也是一个挑战，Red Hat 为此发布了迁移工具。

“自我们发布以来，我们已经看到数百名客户安装了 OpenShift 4，但还有更多客户仍在评估它并计划全面迁移，因为在他们的 OpenShift 3 部署中，他们可能有几十个集群。他们有许多大型环境，所以一般来说，这个过程是你在 OpenShift 4 上踢轮胎，理解它，并确保它会按照你想要的方式工作，”费尔南德斯说。

他解释说，迁移工具将检查当前的 OpenShift 3 部署，发现所有的名称空间、pod 和服务，然后允许用户选择他们想要迁移的部分。

“最酷的是，它不仅仅是将应用程序移动到它上面。它有一个状态的概念，因此如果您的应用程序连接到存储，它可以移动存储卷或将它们重新连接到在您的 OpenShift 4 集群中运行的相同 pods。这不仅仅是移动豆荚那么简单，”他说。

最后，OpenShift 4.2 还支持 [OpenShift 容器存储 4](https://blog.openshift.com/red-hat-openshift-container-storage-4-driving-innovation-through-collaboration/) ，这是一个目前在测试版中可用的软件定义的存储栈。今天发布的 OpenShift 4.2 将在未来几周内推出，并可在 try.openshift.com[进行预览。](https://try.openshift.com/)

红帽是新堆栈的赞助商。

人物形象由[张](https://unsplash.com/@zhang54213?utm_source=unsplash&utm_medium=referral&utm_content=creditCopyText)在 [Unsplash](https://unsplash.com/?utm_source=unsplash&utm_medium=referral&utm_content=creditCopyText) 上。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>