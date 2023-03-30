# Red Hat OpenShift 的日志管理

> 原文：<https://thenewstack.io/log-management-for-red-hat-openshift/>

[LogDNA](https://logdna.com/) 赞助本帖。

 [弗朗西斯·埃斯佩尼多

Franciss 是 LogDNA 的合作伙伴项目经理，在那里他专注于 IBM Cloud 上的可观测性产品的技术支持。他曾担任该公司的技术支持工程师，在那里他对现代日志实践和开发人员工作流程中的挑战有了深入的了解。](https://www.linkedin.com/in/franciss-espenido-1bb84725/) 

OpenShift 由多个组件和层组成，确保所有组件和层的健康需要从各个部分收集日志和指标。同时，管理员必须管理日志数据，以便从整体上了解 OpenShift 集群的运行状况。除此之外，根据您采用的部署 OpenShift 的方法，您还应该收集和分析与底层基础设施相关的日志。

为了帮助管理员理解以上所有内容，本文提供了关于 OpenShift 的日志记录和日志管理的入门知识。它解释了哪些 OpenShift 监控指标是可用的，以及如何查看访问监控和日志数据。下面的大部分信息适用于任何 OpenShift 部署，但是我们将使用 IBM Cloud 上的 [Red Hat OpenShift 作为具体示例的基础。](https://www.ibm.com/cloud/openshift)

## **什么是 OpenShift？**

在深入研究如何管理 OpenShift 上的日志之前，让我们快速了解一下 OpenShift 是什么以及它在哪些表单中可用。这个背景很重要，因为 OpenShift 是一个多方面的平台，可以用多种方式部署。理解 OpenShift 是如何工作的，OpenShift 的特性在不同的部署模型中是如何变化的，以及 OpenShift 与 Kubernetes 的关系是掌握 OpenShift 日志管理的第一步。

OpenShift 是一个管理容器化应用的平台。它由 Red Hat 开发，提供多种部署选项:

*   OpenShift 容器平台，您可以在自己的基础设施上部署它。这是一个你付费的商业平台。红帽提供支持。
*   OKD(原名 OpenShift Origin)，这是一个完全开源、完全免费的平台。Origin 是社区支持的。
*   OpenShift Online，这是 OpenShift 的 SaaS 实现，托管在由 Red Hat 维护的基础设施上。是红帽支持的商业平台。
*   OpenShift dedicated，这是 Red Hat 提供的完全托管产品。这也是一个商业产品，它提供了 Red Hat 最广泛的支持。

### **IBM Cloud 上的红帽 open shift**

除了直接从 Red Hat 获得的 OpenShift 的先前版本之外，一些公共云供应商(与 Red Hat 合作)提供托管在其云上的完全托管的 OpenShift 服务。这包括 IBM Cloud 上的 OpenShift，这是一种允许用户在 IBM 提供和管理的基础设施上旋转 OpenShift 集群的服务，只需几次点击。

IBM Cloud 上的 OpenShift 提供了对 OpenShift 大部分原生功能的访问。然而，正如我们将在本文后面探讨的那样，它还提供了某些附加特性——包括比 OpenShift 的内置日志工具更加用户友好的 OpenShift 日志管理解决方案。

### **OpenShift vs. Kubernetes**

经常可以看到 OpenShift 和 Kubernetes 之间的比较。那是因为 OpenShift 是基于 Kubernetes 的。事实上，OpenShift 是经过认证的 Kubernetes 发行版，完全兼容 Kubernetes 的原生工具。这意味着如果你愿意的话，你可以在 OpenShift 上使用像 kubectl 这样的工具。

然而，这并不意味着 OpenShift 只是一个 Kubernetes 发行版。它在几个关键方面不同于 Kubernetes。首先，有一些特定于 OpenShift 的工具——比如 oc，它提供了许多与 kubectl 相同的特性以及一个内置的容器注册表——管理员通常应该使用这些工具，而不是依赖于通用的 Kubernetes 工具。另一方面，尽管 OpenShift 中的技术是开源的，但该平台是由 Red Hat 开发的商业产品。像升级和日志管理这样的过程(请继续阅读更多相关内容)在 OpenShift 中的工作方式也与 Kubernetes 有所不同。

## **登录什么 OpenShift**

无论您选择哪个 OpenShift 部署选项，都有几种类型的指标需要监控和记录。

### **OpenShift 事件**

在 OpenShift 中，一个事件是集群中可能发生的几十个不同动作中的一个。其中一些是日常事件(如创建容器)，通常不需要您的注意。其他情况表示不希望出现的情况(如存储卷未能装入，或内存不足的情况)，您可能希望进一步调查。OpenShift 事件类型的完整列表可在[这里](https://access.redhat.com/documentation/en-us/openshift_container_platform/3.11/html/developer_guide/dev-guide-events)获得。

事件数据中包含的信息是基本信息。OpenShift 告诉您事件发生了，但是它没有提供事件发生的原因、是否发生了故障或者故障的范围等细节。OpenShift 也不会将相互关联的事件映射在一起；由你来决定一个事件如何与另一个事件联系起来。由于这些原因，事件只能提供有限的可见性。

尽管如此，事件提供了一种快速了解集群状态和识别常见问题的方法。历史事件数据对于研究失败的根本原因也很有用。

### **OpenShift API 审计日志**

OpenShift 支持记录用户和管理员以及集群的其他组件发出的 API 请求。这些数据称为 API 审计日志，提供了对集群内执行的操作的更深层次的可见性。这是因为审计日志为每个请求提供了完整的上下文:它来自哪里，它影响了哪个名称空间(如果相关的话)，响应是什么，等等。

### **基础设施日志**

如果您负责管理承载 OpenShift 集群的基础设施，那么跟踪底层服务器的健康状况是非常重要的。您可以通过查看 OpenShift 集群中每个 pod 的/var/log 目录中的标准 Linux 日志文件来做到这一点。

## **如何在 OpenShift 中管理日志**

与标准的 Kubernetes 相比，OpenShift 中的日志管理总体上更方便一些，这要归功于 OpenShift 本机工具中内置的对访问和解释日志数据的强大支持。

### **访问 OpenShift 事件数据**

可以通过多种方式访问事件数据。一种是通过浏览>事件来使用 OpenShift Web 控制台。如果您需要快速检查事件数据，这是很方便的，但是您不能以这种方式以编程方式访问它。

如果您想要更多地控制您正在查看的事件数据，或者想要将它传递给外部工具，您可以使用 CLI 实用程序 **oc** 和一个命令，例如:

您可以传递一些参数来控制输出，比如使用 *-n* 标志指定某个名称空间。但是，使用 oc 关注特定事件的范围是有限的，因此可能有必要将 oc 输出传送到外部工具(如 grep ),以关注与特定节点相关的事件、特定类型的事件等。

第三种方法是使用外部日志管理工具来读取和分析事件数据。例如，如果您在 IBM Cloud 上使用 OpenShift，您可以利用[本机 LogDNA 集成](https://cloud.ibm.com/docs/openshift?topic=openshift-health#openshift_logdna)通过几个简单的步骤来设置日志分析。使用 LogDNA 的 IBM 日志分析支持对日志数据的实时访问、基于日志内容的警报，以及根据需要存储日志数据的能力。后一个特性可能特别重要，因为如果您删除一个名称空间，OpenShift 本身会永久删除日志数据。但是，如果您使用 LogDNA 将日志数据导入 IBM Log Analysis，那么您可以根据需要存储它，即使原始数据源消失了。

要使用此选项，必须首先在 OpenShift 集群中创建一个 LogDNA 服务实例。您可以通过 IBM Cloud UI，按照一组简单的配置步骤以图形化的方式实现这一点，或者使用带有如下命令的 CLI:

```
ibmcloud resource service-instance-create NAME logdna SERVICE_PLAN_NAME LOCATION

```

关于该命令的完整文档，请参考 [IBM Cloud 文档](https://cloud.ibm.com/docs/Log-Analysis-with-LogDNA?topic=Log-Analysis-with-LogDNA-provision)。

然后，您需要部署 LogDNA 代理来连接到您的 OpenShift 集群，并使用 LogDNA 将日志转发到 IBM Log Analysis。

可以使用 oc 实用程序在 OpenShift 中部署 LogDNA 代理。为此，首先在集群中创建一个新的名称空间来托管代理，命令如下(这里，我们将创建一个名为 ibm-observe 的名称空间):

```
oc adm new-project  --node-selector=''  ibm-observ

```

接下来，为 LogDNA 代理创建一个服务帐户:

```
oc create serviceaccount logdna-agent  -n  ibm-observe

```

接下来，配置权限，以便 logdna-agent 服务帐户可以创建特权 log DNA pod:

```
oc adm policy add-scc-to-user privileged  \  system:serviceaccount:ibm-observe:logdna-agent

```

接下来，为 LogDNA 代理将用来发送日志的摄取密钥添加一个密码:

```
oc create secret generic logdna-agent-key  --from-literal=logdna-agent-key=INGESTION_KEY  -n  PROJECT

```

最后，使用 kubectl 将 LogDNA 代理部署到节点。预配置的 YAML 文件可用于不同的公共 IBM cloud 端点，因此您可以使用如下命令来部署代理:

```
kubectl create  -f  https://assets.eu-de.logging.cloud.ibm.com/clients/logdna-agent-ds-os.yaml -n ibm-observe

```

有关可用公共端点的完整列表，以及在 IBM cloud 上部署 LogDNA 代理的其他上下文，请参考[文档](https://cloud.ibm.com/docs/Log-Analysis-with-LogDNA?topic=Log-Analysis-with-LogDNA-config_agent_os_cluster)。

完成配置后，LogDNA 服务实例和代理会在 OpenShift 控制台中提供一个 LogDNA 仪表板。在那里，您可以完全访问 LogDNA 的特性集，以查看和管理 OpenShift 事件和其他日志数据。

### **查看 OpenShift API 审计日志**

要在通用 OpenShift 安装中查看 API 审计日志，您必须首先通过在主节点上的/etc/origin/master/master-config . YAML 中添加 auditConfig 节来启用审计日志记录，如下例所示:

```
auditConfig:
  auditFilePath:  /var/lib/origin/log/ocp-audit.log
  enabled:  true
  maximumFileRetentionDays:  5
  maximumFileSizeMegabytes:  20
  maximumRetainedFiles:  20

```

**使能:真**参数开启审计记录；其他字段定义日志设置。

启用审计日志后，审计日志数据将通过 systemd 进行管理，并且可以通过在存储日志数据的节点上运行 **journalctl** 进行访问。通常，这是您的 OpenShift 主节点。如果您愿意，也可以使用类似于
的命令直接访问审计日志文件

```
less  /var/lib/origin/log/ocp-audit.log

```

在 OpenShift 版和更高版本中，您还可以使用 oc 实用程序访问审计日志:

```
oc adm node-logs  <node-name>  --path=openshift-apiserver/<log-name>

```

如果在 IBM Cloud 上使用 OpenShift，OpenShift 的原生审计日志记录实用程序会被 IBM Log Analysis with LogDNA 所取代。您可以使用本文上一节中描述的相同的 LogDNA 集成过程来配置 LogDNA 以收集和分析审核日志数据。

与依赖原生 OpenShift 工具相比，这种方法有几个优点。IBM Log Analysis with LogDNA 提供了高级日志分析特性，以及一个图形界面，使得访问审计日志数据更加方便。它还将审核日志与其他类型的日志数据聚合在一起，使管理员能够从一个中心位置查看所有日志。它使您能够在您选择的保留期内存储日志数据，即使它从 OpenShift 本身消失。

### **访问基础设施日志**

访问底层主机基础架构的日志非常简单。您可以使用相同的日志和分析工具来访问任何类型的 Linux 或*nix 服务器日志。

您可以通过登录到每个节点并直接查看/var/log 中的日志文件来访问基础设施日志。或者，为了简化这个过程，您可以使用一个日志聚合和管理工具，比如 IBM Log Analysis with LogDNA，它可以从您的所有主机服务器收集和管理日志数据，并在一个中心位置提供给您。如果您有多台服务器，汇总这些数据是跟踪所有数据的唯一可行方法。使用 IBM Cloud observability 插件上的 Red Hat OpenShift 为集群中的 IBM Log Analysis with LogDNA 创建一个日志配置，并使用该日志配置自动收集 pod 日志并将其转发给 IBM Log Analysis with LogDNA。

除了上面描述的 OpenShift 集成之外，IBM Cloud 还为 LogDNA 提供了通用服务器监控的[集成。或者，无论服务器是否是公共云的一部分，您都可以在任何 Linux 服务器上安装 LogDNA。(LogDNA 也支持 Windows 和 macOS，但是因为 OpenShift 只在 Red Hat Enterprise Linux 上运行，所以与本文的讨论无关。)](https://cloud.ibm.com/docs/Log-Analysis-with-LogDNA?topic=Log-Analysis-with-LogDNA-config_agent_linux)

## **结论**

OpenShift 提供了本地日志管理工具，这些工具提供了对 OpenShift 集群的各个关键部分的可见性。如果您来自一个普通的 Kubernetes 背景，您可能会对 OpenShift 提供的相对于普通 Kubernetes 的原生日志功能的丰富程度印象深刻。

也就是说，OpenShift 的本地日志管理解决方案并不总是这项工作的最佳工具。在某些情况下，例如当您需要聚合大量日志数据并且能够将日志数据存储的时间超过 OpenShift 本身支持的时间时，LogDNA 等第三方日志管理工具是更好的选择。LogDNA 提供了比 OpenShift 本身更丰富的日志聚合、分析和管理功能。而且，由于 LogDNA 与 IBM Cloud 等平台的集成，部署 LogDNA 来管理这些平台上的 OpenShift 日志就像运行几个命令或在 Web UI 中单击几个按钮一样简单。

这篇文章是探索 Kubernetes 日志记录和 RedHat OpenShift 日志记录之间区别的系列文章的一部分。下载完整电子书 [*点击这里*](http://go.logdna.com/openshift-vs-kubernetes) *。*

红帽是新堆栈的赞助商。

通过 Pixabay 的特征图像。

*目前，新堆栈不允许直接在该网站上发表评论。我们邀请所有希望讨论某个故事的读者通过推特或脸书与我们联系。我们也欢迎您通过电子邮件发送新闻提示和反馈:[feedback @ thenewstack . io](mailto:feedback@thenewstack.io)。*

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>