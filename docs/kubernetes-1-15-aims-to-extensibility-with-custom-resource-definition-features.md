# Kubernetes 1.15 旨在通过定制资源定义特性来实现可扩展性

> 原文：<https://thenewstack.io/kubernetes-1-15-aims-to-extensibility-with-custom-resource-definition-features/>

随着 Kubernetes 1.14 的推出，该团队将 10 个增强功能转移到了 stable，但这一次这个数字下降到了两个，引入了更多的 alpha 和 beta 功能。团队负责人 [Claire Laurence](https://www.linkedin.com/in/claire-laurence-ba151982/) 说，Kubernetes 1.15 更关注引入新功能，而不是稳定的功能，并在宣布它们稳定之前花时间构建这些功能。

“这个版本与上一个版本形成了鲜明的对比，上一个版本是一个版本中最稳定的功能。在这个周期中，我们没有太多稳定的功能。我们有两个 kubectl 命令——get 和 describe——现在应该可以很好地处理扩展，并且是稳定的。第二个稳定的增强是添加 go 模块支持，这是实际开发 Kubernetes 或我们的第三方供应商的人最感兴趣的，”劳伦斯在接受新堆栈采访时说。“除此之外，我们已经有相当数量的功能进展到测试版。我认为，随着这些 alpha 和 beta 功能的发展，我们已经看到了很多对稳定性和整体改进的持续关注，然后才表明这些功能是稳定的。”

Kubernetes 1.15 是 Kubernetes 在 2019 年发布的第二个版本，与 2018 年的四个版本保持同步，并专注于继续努力实现稳定性和可扩展性，两个新的稳定功能以及对[自定义资源定义(CRDs)](https://kubernetes.io/docs/concepts/extend-kubernetes/api-extension/custom-resources/) 的大量添加就是证明。例如， [go 模块支持](http://k8s.io/kubernetes)为 Kubernetes 的核心开发人员以及那些希望构建第三方扩展的人员带来了最近添加的 go 功能，而根据 GitHub 上的评论，kubectl [get 和 description](https://github.com/kubernetes/enhancements/issues/515)现在“允许更好的可扩展性”，这使得“第三方 API 扩展和 CRD 可以为 kubectl get 提供定制输出，以避免 kubectl 必须拥有代码来解释这些资源”。

根据发布 Kubernetes 1.15 的博客文章，CRDs 的新特性围绕着数据一致性和本机行为的思想，最终目标是“用户不应该注意交互是与 CustomResource 还是与 Golang 本机资源。”为此，Kubernetes 1.15 增加了四个新的 beta 特性和一个与 CRDs 相关的 alpha 特性。首先，CRDs 的 OpenAPI 发布将可用于测试版中的[结构模式](https://kubernetes.io/docs/concepts/extend-kubernetes/api-extension/custom-resources/#specifying-a-structural-schema)，而 CRD 修剪将根据该模式提供“自动删除发送到 Kubernetes API 的对象中的未知字段”。CRDs 也将获得拥有默认值的 alpha 能力，这将“在 OpenAPI 验证模式中使用`default`关键字指定”最后，CRDs 将围绕 Webhooks 获得两个测试版特性，首先是支持“在不同版本之间动态转换的能力，就像用户习惯于从本地资源转换一样”，然后是围绕重新定位的改进。虽然 1.15 可能有最少数量的新稳定功能，但博客文章透露，该团队正在努力在下一个版本中发布 CRDs 和 admission webhooks 的 GA 版本。

Kubernetes 1.15 的其他显著特性包括:

所有这些还不算 Kubernetes 团队的其他大新闻——kube ADM 现在[有了自己的标志](https://github.com/kubernetes/kubeadm/issues/1588)。

通过 Pixabay 的特征图像。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>