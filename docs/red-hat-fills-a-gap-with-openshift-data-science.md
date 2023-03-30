# 红帽填补了 OpenShift 数据科学的空白

> 原文：<https://thenewstack.io/red-hat-fills-a-gap-with-openshift-data-science/>

继今年早些时候首次发布之后，红帽发布了[红帽 OpenShift 数据科学](https://www.redhat.com/en/technologies/cloud-computing/openshift/openshift-data-science)作为“现场测试”。托管云服务在[红帽 OpenShift](https://cloud.redhat.com/products/dedicated/?extIdCarryOver=true&sc_cid=701f2000001OH7EAAW) 上为企业提供了一个为人工智能和机器学习(AI/ML)量身定制的环境。

据 Red Hat 人工智能产品管理高级总监 Steve Huels 称，AI/ML 对 Red Hat 来说并不新鲜，Red Hat OpenShift 数据科学的起源在于该公司在自己的平台上构建 AI/ML 功能的经验，如 Red Hat Insights。最终，Red Hat 吸收了这一经验，并将其编入了 [Open Data Hub](https://opendatahub.io/) 开源项目，但 Huels 解释说，Red Hat 的客户正在寻找一种他们可以购买的提供这些功能的托管服务。

“他们说，这太棒了，它做了我们想做的一切，我们能买下它吗？答案总是围绕一组 Red Hat 组件和合作伙伴组件，但这在中间留下了一个小点，没有人以独立的身份提供，”Huels 说。“你总是可以从合作伙伴那里购买更大的套房，但它附带了许多其他东西，可能你还没有准备好或不需要。最终，这导致了 OpenShift 数据科学的诞生。它能够填补合作伙伴围绕一组核心 AI/ML 组件的空白。”

## **建立在组件子集上**

Red Hat OpenShift Data Science 建立在开放数据中心提供的组件子集基础上，如 JupyterLab、Tensorflow、PyTorch、SciKit、Panda 和 NumPY，然后作为托管服务的一部分，与 Red Hat OpenShift 进行更深入的集成，并提供 SRE 支持。Huel 解释说，集成的一部分还围绕着用户执行可重复操作的能力，而不是每次都必须从头开始配置和部署。

“AI/ML 面临的部分挑战是，我们如何将这些东西放入可重复的生命周期过程中，对吗？作为一次性实验来做是一回事，能够接受、重复做、常规做又是另一回事，”Huel 说。“这就是 Red Hat 在 DevOps 中的 DNA 真正发挥作用的地方。我们已经在 GitOps 生命周期上为开发人员管理了很长很长时间，”他补充道，指的是像 Red Hat 使用 Tecton 进行管道管理这样的事情。

## **用例**

至于谁应该考虑使用 OpenShift Data Science，Huel 表示，这项服务对每个人都有好处，从那些刚刚开始使用 AI/ML、希望更容易地尝试训练模型和使用 ML 的人，到那些希望运行最新工具但不想被管理它们所困扰的人。Red Hat 每两周发布一次新版本，帮助数据科学家跟上组件的快速变化，运营团队不必做任何不寻常的事情来保持最新。

Huel 解释说:“当需要将该模型带回内部并将其部署到更靠近源系统的地方时，运营方对此感到满意，因为该模型是以容器的形式出现的。”。“这有助于缓解这种紧张关系，因为两个社区都能得到他们需要的东西，而且他们都对工作环境感到满意。”

Huel 解释说，OpenShift 数据科学的另一个潜在用例是那些发现自己由于这样或那样的原因无法雇用数据科学家的组织。

“这有助于填补一个空白，你可以让真正优秀的工程师，他们可以自己做一些建模，”Huel 说。“他们不再依赖数据科学社区，而是能够完成部分工作，然后让数据科学家对其进行验证，而且能够更快地前进。这有助于缓解人才短缺的担忧，并让人们继续前进。”

## **新功能**

这个最新版本的 Red Hat OpenShift Data Science 提供了几个新功能，包括[英特尔 oneAPI AI 分析工具包](https://www.intel.com/content/www/us/en/developer/tools/oneapi/ai-analytics-toolkit.html)和对[英特尔 OpenVINO Pro for Enterprise](https://marketplace.redhat.com/en-us/products/openvino) 的支持，以及对 [Anaconda 商业版](https://www.anaconda.com/products/commercial-edition)、 [IBM Watson Studio](https://www.ibm.com/cloud/watson-studio) 、 [Seldon Deploy](https://www.seldon.io/tech/products/deploy/) 和 [Starburst Galaxy](https://www.starburst.io/platform/starburst-galaxy/) 的新集成。

Huel 说，随着该服务作为“现场试验”发布，这是 Red Hat 开始与传统内部软件中常见的 alpha，beta，general availability (GA)周期平行的另一件事。他说，现场试验提供了一个具有支持和 SRE 监控的“代码就绪产品”，但还没有达到 GA 的水平。相反，Red Hat 正在寻求反馈，以确保它在正式发布之前适合市场。

展望未来，该服务预计将获得对英伟达图形处理单元(GPU)和谷歌云平台(GCP)和微软 Azure 的支持。从更广泛的角度来说，Huel 说，Red Hat 希望扩展到提供“一个更强大的模型服务环境”。

“我们希望能够提供完整的端到端模型操作，因为这确实是完整 DevOps 生命周期的自动化实现:开发、发布、监控、清洗和重复，”Huel 说。“这些事情符合红帽的 DNA。我们在那里有很长的历史，我们可以把这些插上。这只是人工智能/人工智能世界的标准问题，已经有了一些共识。”

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>