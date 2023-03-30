# 本周节目:Kubernetes 说不要对 Docker 贬值感到恐慌

> 原文：<https://thenewstack.io/this-week-in-programming-kubernetes-says-dont-panic-about-docker-deprecation/>

到现在为止，你可能已经听说了这个消息——Kubernetes 在 Docker 1.20 版发布后对其进行了抨击——因为它可能是在一条气喘吁吁、惊慌失措的推文或博客帖子中表达的，但不要担心，[说](https://kubernetes.io/blog/2020/12/02/dont-panic-kubernetes-and-docker/)Kubernetes 团队，“这并不像听起来那么戏剧化。”

虽然 Kubernetes 管理员可能需要处理一点配置，但开发人员可能不需要做任何更改，这里有几个要点可以解释为什么。对于开发人员来说，Docker 仍然是构建将在 Kubernetes 上运行的图像的完美有效的工具，没有什么可担心的。该团队解释说，这里真正发生的是“Docker 作为底层运行时正在被弃用，取而代之的是使用为 Kubernetes 创建的[容器运行时接口(CRI)](https://kubernetes.io/blog/2016/12/container-runtime-interface-cri-in-kubernetes/) 的运行时。”

本质上，你通常所说的“Docker”是由几个部分组成的，其中包括一个用户界面。“由于这个对人类友好的抽象层，你的 Kubernetes 集群必须使用另一个名为 Dockershim 的工具来获得它真正需要的东西，这就是 containerd，”容器运行时，Kubernetes 团队写道。“这不太好，因为它给了我们另一个必须维护并且可能会损坏的东西。这里实际发生的是，早在 1.23 版本中，Dockershim 就被从 Kubelet 中删除了，结果是删除了对 Docker 作为容器运行时的支持。”

他们解释说，更多的活动部件意味着更多的东西断裂的可能性，而这恰恰减少了这些可能性。与此同时，管理员需要了解这些变化，因为需要进行一些更改来避免出现问题。为此，该团队整理了一个更恰当的标题 [Dockershim 弃用常见问题](https://kubernetes.io/blog/2020/12/02/dockershim-faq/)(因为这里弃用的实际上是 Dockershim，而不是 Docker)，应该可以回答你的所有问题。

## 本周的节目中

*   **AWS 发布所有东西:**好像你可能已经错过了一样，AWS 在过去的一周开始了它的 [re:Invent 2020](https://reinvent.awsevents.com/) 虚拟活动，这场马拉松式的在线主题演讲和小组讨论将持续到 12 月 18 日。该公司已经推出了一堆相关的东西，占用的空间比我们现有的要多得多，所以我们会把你引向他们漂亮简洁(并且不断更新)的 2020 年 T4 顶级公告列表，其中提供了按类别组织的所有发布，或者如果你喜欢，按发布日期组织的[。也就是说，有几个相关的版本值得注意，我们将在下面列出，但在我们继续之前，我们还会注意到 Docker 提供了一个针对 AWS re:Invent](https://aws.amazon.com/new/reinvent/) 的 [Docker 开发人员指南，其中还包括一些亮点，特别是针对 Docker 开发人员的。如果这能描述你，也许值得一看。](https://www.docker.com/blog/the-docker-developer-guide-to-aws-reinvent/)
*   **Lambda 获得容器支持，增加。NET 5:** 首先， [AWS Lambda](https://aws.amazon.com/lambda/) ，该公司的无服务器计算服务，已经推出了[容器映像支持](https://aws.amazon.com/blogs/aws/new-for-aws-lambda-container-image-support)，这意味着你现在可以将 Lambda 函数打包并部署为最大 10 GB 的容器映像，而不是单独的代码 ZIP 文件。新功能不仅简化了操作，还允许您部署具有“相当大的依赖性，如机器学习或数据密集型工作负载”的更大工作负载除了新功能，AWS 还开源了一个用于本地测试的 [Lambda 运行时接口仿真器](https://github.com/aws/aws-lambda-runtime-interface-emulator/)，以确保您的容器映像可以在 Lambda 上正常运行，这将包含在 AWS 提供的所有基础映像中。除了支持容器图像，该公司还推出了支持。NET 容器映像，并对 AWS Lambda 进行了更新。NET 工具来支持构建 Lambda 函数作为。NET Core 2.1 和 3.1，以及对。NET 5 使用 [AWS Lambda。NET 5 基础镜像](https://gallery.ecr.aws/lambda/dotnet)。
*   **AWS 预览用于管理容器和无服务器部署的 Proton:**当我们谈论混合工作负载的话题时，AWS 也通过 [AWS Proton](https://aws.amazon.com/proton/) 的公开预览解决了容器和无服务器部署的[管理](https://feedproxy.google.com/~r/AmazonWebServicesBlog/~3/7A6FEfOsEW4/)。针对基础设施团队，AWS Proton 将集成常用的 CI/CD 管道和可观察性工具，提供遵循 AWS 最佳实践的[精选模板](https://github.com/aws-samples/aws-proton-sample-templates)，并帮助在 AWS 管理控制台中可视化和管理服务模板列表。

[https://www.youtube.com/embed/yWXT21enYYc?feature=oembed](https://www.youtube.com/embed/yWXT21enYYc?feature=oembed)

视频

*   **Lambda 增加毫秒计费:**最后，Lambda 推出了[1 毫秒计费粒度](https://feedproxy.google.com/~r/AmazonWebServicesBlog/~3/-rbrFFJWnzc/)，低于之前的 100 毫秒测量值，该公司表示，这将意味着“大多数时候你将支付更少的费用，但当你拥有执行时间远低于 100 毫秒的功能时，这将更加明显，如低延迟 API。”
*   **亚马逊首次推出公共容器注册表:**最近，Docker 表示，这将是从 Docker Hub 进行限速图像提取(参见我们在[上的帖子，它们是什么以及如何绕过它们](https://thenewstack.io/docker-hub-limits-what-they-are-and-how-to-route-around-them/))每个人，[包括亚马逊](https://aws.amazon.com/blogs/containers/advice-for-customers-dealing-with-docker-hub-rate-limits-and-a-coming-soon-announcement/)都承诺了一个替代方案。随着亚马逊弹性容器注册公共(ECR Public)的推出，这种替代方案现在已经到来，它“允许你存储、管理、共享和部署容器映像，供全球任何人发现和下载。”这扩展了该服务的功能，将公共容器图像与私有图像一起包括在内，以及一个用于浏览和搜索公共容器图像的公共图库，它与亚马逊 EKS 发行版图像和 AWS 合作伙伴的数百张图像一起推出。所有 AWS 客户每月将获得 50 GB 的免费存储，而匿名用户每月将获得 500 GB 的免费数据带宽，认证帐户每月获得高达 5 TB 的免费数据带宽。当从 ECR Public 中提取公开共享的映像时，运行在 AWS 中的工作负载将从任何地区获得无限的数据带宽。

[https://www.youtube.com/embed/Vv-E5cXRaFg?feature=oembed](https://www.youtube.com/embed/Vv-E5cXRaFg?feature=oembed)

视频

*   **Docker 的社区全体会议:**如果更多的 AWS re:Invent 没有占据你未来一周的时间，那么还有另一个虚拟活动可以添加到你的日历中， [Docker 的社区全体会议](https://www.docker.com/blog/join-dockers-community-all-hands/)，将于 12 月 10 日星期四太平洋标准时间上午 8 点/欧洲中部时间下午 5 点举行。长达一小时的活动将包括公司和产品更新、现场演示、社区大声疾呼以及与 Docker 首席执行官 Scott Johnston、产品副总裁 Donnie Berkholz 和工程副总裁 Jean-Laurent de Morlhon 的问答。您可以[注册活动](https://goto.docker.com/community-all-hands-201210.html?utm_medium=blog)和[提交问题](http://dockr.ly/allhandsquestions)给 Q & A。
*   **GitHub 关注 10 月宇宙:** GitHub 的年度反思，即 2020 年 10 月宇宙的[状态，已经出来提供一些关于过去一年的见解，如你所知，这是不平凡的一年。](https://github.blog/2020-12-02-the-state-of-the-octoverse-2020/)[报告](https://octoverse.github.com/)对三个特定领域进行了深入探讨，着眼于 COVID 时代的开发人员生产力、社区和协作以及开源安全。亮点包括生产力的提高，2020 年创建的存储库比 2019 年多 35%，2020 年有超过 5600 万开发人员的大型开源社区，预计到 2025 年将有 1 亿人，安全漏洞往往在 4 年多后才被发现，94%的项目依赖开源组件。
*   **VS Chromebook 上的代码:**这最后一个是一个与我的心灵[密切相关的主题](https://thenewstack.io/week-programming-dogfooding-developers-chromebooks/)——使用 chrome book 来编码。虽然在 Chromebook 上编码有时需要一些操作，但随着时间的推移，它变得越来越容易，本周微软提供了一个关于在 chrome book 上使用 VS 代码进行编码和学习的指南。这篇文章是两篇文章中的第一篇，讲述了如何在 Chromebook 上安装 Visual Studio 代码，以及如何设置一个环境来开始用 Python 或 JavaScript/Node.js 进行编码。下一篇尚未发表的文章将讲述如何使用 VS 代码的[远程开发](https://marketplace.visualstudio.com/items?itemName=ms-vscode-remote.vscode-remote-extensionpack)扩展来连接到更强大的开发环境。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>