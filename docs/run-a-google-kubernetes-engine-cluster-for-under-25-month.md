# 以每月不到 25 美元的价格运行 Google Kubernetes 引擎集群

> 原文：<https://thenewstack.io/run-a-google-kubernetes-engine-cluster-for-under-25-month/>

[](https://www.linkedin.com/in/ericmurphy2/)

 [埃里克·墨菲

埃里克是 Solo.io 的现场工程师，他喜欢思考软件设计以及技术如何解决业务问题的大图景。在过去，Eric 主持过关于 Kubernetes、Java 和领域驱动设计等主题的研讨会。此外，Eric 是 O'Reilly 的出版作者，并在全球技术会议上发表过论文。](https://www.linkedin.com/in/ericmurphy2/) [](https://www.linkedin.com/in/ericmurphy2/)

如果你正在学习或摆弄 Kubernetes，你有很好的选择来运行 Kubernetes 与折扣服务提供商，如 [Civo](https://www.civo.com/) ，或简单地在你的笔记本电脑上运行 Kubernetes。然而，在主要的云提供商上运行 Kubernetes 是获得 Kubernetes 的完整体验和获得在云中使用 Kubernetes 的工作所需的关键技能的唯一方法。

在亚马逊网络服务、Azure 和谷歌云上以折扣价运行 Kubernetes 的选项令人困惑，最终充斥着隐性成本。此外，许多免费学分是暂时的。Civo 的一个主要好处是——成本是固定的，易于理解。作为一名学习者或修补者，你希望保持最低的成本，如果可能的话，每天低于 1 美元。

本文将展示一个解决方案(可从 [GitHub](https://github.com/murphye/cheap-gke-cluster) 上获得)，在 [Google Cloud](https://cloud.google.com/) 上运行一个成熟的 GKE 集群，目标是将每天的成本控制在 1 美元以下。该集群有三个节点、六个内核和 24GB RAM，足够运行重要的工作负载，以学习如何在 Kubernetes 上扩展应用程序的关键技能。

您可以使用 [GitHub repo](https://github.com) 中的说明和提供的 Terraform 配置轻松部署廉价的 GKE 解决方案。设置好你的 Google 项目 ID 后，运行 terraform init 和 terraform apply 一样简单。

## **廉价 GKE 解决方案的成本比较**

通过利用谷歌云的大幅折扣，运行一个全包式 GKE 集群可以节省 90%以上的成本。这是一个成本比较表:

如您所见，如果您使用最少的数据出口，每月 24 美元的廉价 GKE 解决方案还不到同等 Civo 部署成本的一半。但是，您应该在 [计算引擎定价](https://cloud.google.com/compute/all-pricing) 页面上查看 Spot 虚拟机的信息，以了解您推荐的地区的对比情况。美国-西方 4 是目前最便宜的地区，亚洲-东方 2 稍微贵一些。

## **便宜的 GKE 解决方案成本明细**

为了帮助理解和预测运行廉价的 GKE 解决方案的费用，这里是 GCP SKU 每天的成本明细。数据处理费用适用于来自 GKE 的外部服务呼叫，例如从 Docker Hub 提取图像。如果您经常提取图像，建议使用 [工件注册表](https://cloud.google.com/artifact-registry) 以保持 NAT 网关数据处理费用较低。

## **廉价 GKE 解决方案的优势**

好的，所以你可以用最便宜的 GKE 解决方案以最小的成本运行一个真正的 GKE 集群。假设这个集群有一个非同寻常的六核和 24GB RAM，那么您可以对它做些什么呢？

1.  运行几个微服务，复制几个。尝试部署的高级功能，如反关联性规则。
2.  在群集本身上运行构建管道。为此，您可以考虑尝试 Tekton。最好将图像推送到 [工件注册表](https://cloud.google.com/artifact-registry) 。
3.  运行 GitOps 部署工具。您可以考虑 ArgoCD 从您的 Git 存储库中自动部署应用程序和配置。
4.  运行入口网关并试验 API 网关特性。 [Gloo Edge](https://github.com/solo-io/gloo) ，一个免费开源的、基于 Envoy 的、Kubernetes-native API 网关已经包含在廉价的 GKE 解决方案中。
5.  运行服务网格。 [这里的](https://istio.io/latest/docs/setup/platform-setup/gke/) 是在 GKE 上安装 Istio 的说明。
6.  运行数据库。 [这里的](https://cloud.google.com/architecture/deploying-highly-available-postgresql-with-gke) 是在 GKE 上用区域持久磁盘运行 PostgreSQL 的指令。
7.  为机器学习运行服务。 [Kubeflow](https://www.kubeflow.org/) 可能很适合这个。

通过拥有一个具有更多 CPU 和 RAM 的更大的集群，新的大门向学习者和修补者敞开，他们可以在他们的 Kubernetes 集群上可行地运行工作负载。

## **廉价 GKE 解决方案的缺点**

关于廉价的 GKE 解决方案如何工作的细节在 [GitHub repo](https://github.com/murphye/cheap-gke-cluster) 中有大量记载。您应该记住四个主要缺点:

1.  每个 GCP 帐户只允许一个免费的 GKE 控制平面。这些都很贵，每月 72 美元。因此，建议一次只运行一个集群。
2.  该集群由三个没有 SLA 的 Spot 虚拟机组成，是 GKE 的测试版功能。有可能三个节点中的两个会同时被替换。对于开发工作负载，这不是什么大问题，因为 pod 将在新节点上再次旋转。在 [GitHub repo、](https://github.com/murphye/cheap-gke-cluster) 中，有关于如何让您的应用程序适应节点替换场景的详细信息。根据我的经验，GKE 集群节点在被替换之前通常会连续运行几天。
3.  区域云负载平衡器是一项测试服务，可能会产生费用，但目前处于免费推广阶段。我预计费用最终会是每月几美元，但这只是猜测。
4.  从一开始就按每 GB 收取数据出口费用。对于那些只是学习 Kubernetes 的人来说，成本影响是最小的，如成本明细所示。

正如我之前所说，廉价的 GKE 解决方案主要是为 GKE 的学习者和修补者。虽然节省的成本很大，但是在操作集群时要记住一些明显的缺点。

## **便宜的 GKE 解决方案价格缩放**

所提供的廉价 GKE 解决方案具有可扩展的定价模型。例如，您可以运行一个 6 节点、24 核、96GB RAM 的集群，每月花费大约 100 美元。运行的节点越多，受并发节点替换严重影响的可能性就越小。对于一个非常擅长构建容错应用程序的超级精明的初创公司来说，使用 Spot VM 节点是非常有吸引力的。您还可以结合非现场虚拟机节点池来处理有状态的工作负载。因此，廉价的 GKE 解决方案可能为那些在预算紧张的情况下愿意接受风险的人提供一些令人信服的想法。

## **结论**

使用 GitHub repo 中的说明，尝试一下廉价的 GKE 解决方案。如果让它在自己的 Google Cloud 项目中运行几天，就很容易检查运行集群的成本。假设您只有一个 GKE 集群在运行，那么每天不到 1 美元就可以拥有一个很棒的 Kubernetes 集群。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>