# Ansible Container:剧本作为唯一的构建和管理工具

> 原文：<https://thenewstack.io/ansible-container-playbooks-sole-build-management-tool/>

Red Hat 旗下的 IT 自动化软件提供商 Ansible 继续致力于扩展其用于构建和部署容器的管理工具组合，包括 Docker 容器和非 Docker 容器。

[Ansible 2.1 版](https://www.ansible.com/blog/ansible-2.1)，去年 5 月发布，增加了 Docker 插件，以及一个模块，使 ansi ble 的 [YAML](http://yaml.org/) 自动化脚本或“剧本”包括 Docker Compose 风格的语法。这使得许多手工编排容器的工作可以重新用于自动化整个 IT 基础设施。

它还推出了 [Kubernetes 模块](http://www.businesswire.com/news/home/20160620005670/en/Red-Hat-Launches-Ansible-Native-Container-Workflow-Project)，允许直接从可翻译剧本中创建 [Kubernetes](/category/kubernetes/) 模板。它还扩展了自动化功能，将[网络基础设施](https://thenewstack.io/red-hat-ansible-will-handle-networking/)纳入其中，使用户能够同时管理 Docker 机器环境和自动化其网络层。

这项工作后来发展成了 Ansible Container，这是一个只使用 Ansible 剧本构建 Docker 图像和编排容器的开源项目。

Red Hat 的 Ansible 社区总监 Greg DeKoenigsberg 表示，该项目的目标是让人们能够使用和重用 Ansible 内容来构建容器，而不仅仅是虚拟机。Red Hat 于 2015 年收购了这家自动化技术公司。

“许多人使用可变角色来定义他们的系统可能做的事情:web 服务器角色、数据库角色。我们的想法是，一个可行的角色与微服务的想法重叠，所以将这些角色转变为容器，并以可行的方式移动这些容器，这似乎是一个好主意，”他说。

Ansible 中的模块允许用户操作 Docker 本身和其他工具。他说，这里的不同之处在于，它提供了在一个工具中完成所有这些的能力，在这个工具中，你可以实际操作容器的内部，将这些容器保存到注册表中，然后发布这些容器，并进行实际的容器管理。

“它们以前是社区工具，我们将其中一些工具和想法整合到一个更加固执己见的项目中，关于我们认为你应该如何用 Ansible 做这些事情，”他说。

他举例说，他们会启动一个容器，然后将 SSH 放入容器，这样他们就可以使用 Ansible 来管理它。Docker 连接插件使得不必将 SSH 放入容器就可以使用 Ansible。你只需要写一个剧本来联系。

## 营销层

虽然 Ansible Container 允许您仅使用 Ansible 剧本来构建 Docker 映像和编排容器，但它不使用 Dockerfile。

DeKoenigsberg 解释说:“Dockerfiles 基本上是 shell 脚本。我们首先编写 Ansible 的原因之一是 shell 脚本很快就会变得非常难看。Ansible 是容器本身的主要定义语言。默认情况下，这些容器位于 Docker 下方。我们只需要决定我们需要支持哪些其他引擎。

“在部署阶段，我们也有一种机制来从 Ansible 描述文件中构建 Kubernetes 和 OpenShift 工件，这样您就可以直接进入 OpenShift 和 Kubernetes 部署。它有助于从构建到部署过程的全程自动化。”

他说，该项目的目标不是完全取代 Docker。OpenShift 是 Red Hat 支持的 Kubernetes 版本，这是一个容器编排引擎。

“Ansible 假设你今天有 Docker，但我们将 Ansible 构建成可插拔的，所以如果有一天有人想使用[开放容器倡议](https://thenewstack.io/amazon-aws-now-supports-oci-format-will-mixed-registry-now/)的一些部分，我们只需要在幕后构建一些东西来做到这一点，”他说。

在一次更加公开的[远离 Docker](https://thenewstack.io/oci-building-way-kubernetes-run-containers-without-docker/) 的行动中，Red Hat 工程师是另一个项目背后的人之一，该项目简称为 [OCID](https://github.com/kubernetes-incubator/ocid) (OCI 守护进程)，以使 Kubernetes——而不是 Docker——能够大规模启动和管理容器。红帽毫不掩饰其对 Kubernetes 的支持，而不是 Docker Swarm 中的编排。

DevOps 市场分析师 Chris Riley 表示，他认为“可折叠容器”是“一种营销手段”，而不是 Red Hat 对 Docker 的挑战。

“在我看来，Red Hat 正在做的事情是试探:‘如果我们拥有自己的容器技术，那会是什么样子？’他说。

当你拥有操作系统时，这是有意义的，但他预计围绕 CloudForms 的计划会更有成效。

“在我看来，如果有人要接受容器，那将是 Azure、AWS 或谷歌，或者是用无服务器代码篡夺它的人。”

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>