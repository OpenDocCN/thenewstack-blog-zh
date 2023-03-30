# 快速浏览:Amazon Web Services 上的容器安全性

> 原文：<https://thenewstack.io/quick-take-container-security-on-amazon-web-services/>

不管是好是坏，容器在亚马逊网络服务上的使用方式将会影响这项技术的未来。因此，不管是好是坏，有必要对此进行跟踪，这是 AWS 开发者倡导者和云原生计算基金会(CNCF)大使 [Michael Hausenblas](https://twitter.com/mhausenblas) 连续第二年所做的。 [AWS 集装箱安全调查 2020](https://github.com/mhausenblas/aws-container-security-survey-2020) 有 156 名受访者，其中一半使用了[弹性云计算(EC2)服务上的](https://aws.amazon.com/eks) (EKS)弹性 Kubernetes 服务。此外，36%的人在 AWS Fargate 基础上运行容器服务，但是其中大约一半的人完全依赖 AWS ECS。

组织没有尽可能多地使用扫描来提高集装箱安全性。尽管 67%的人使用 Amazon ECR，但只有 40%的人真正使用容器注册中心的原生功能来扫描图像。也许这是因为他们认为 AWS 已经保证了注册表中图像的安全性。在运行时扫描集装箱几乎是不存在的——70%的人还没有这样做，尽管 17%的人使用 CNCF 的 Falco。

在管理敏感数据方面，AWS 的[参数存储](https://aws.amazon.com/systems-manager/features/)功能显然已经失宠——只有 26%的受访者使用该功能，而 2019 年的调查中这一比例为 55%。将这种用法与[AWS Secrets Manager](https://docs.aws.amazon.com/secretsmanager/latest/userguide/intro.html)(2019 年的 43%到 2020 年的 50%)和[hashi corp Vault](https://www.vaultproject.io/)(2019 年的 25%到 2020 年的 38%)进行比较。对于需要专用服务来处理内部和多云环境中的工作负载的公司，Vault 可能比依赖 AWS 的专用服务更有意义。

其他几个 CNCF 项目也被问到，其中 [Open Policy Agent](https://www.openpolicyagent.org/) 表现尤为出色，27%的受访者表示他们使用该技术来执行政策。有了一个充满活力的开源社区来支持这个项目，这个项目最初的支持者, [Styra](https://www.styra.com/) 的未来看起来一片光明。事实上，在 CNCF 最新的[调查](https://github.com/cncf/surveys/tree/master/cloudnative)中，该项目的生产使用增加了一倍多，从 2019 年的 5%增加到 2020 年的 11%，另有 24%的人对其进行评估。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>