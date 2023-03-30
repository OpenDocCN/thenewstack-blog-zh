# 使用 Terraform 供应 Kubernetes 的更好方法

> 原文：<https://thenewstack.io/a-better-way-to-provision-kubernetes-using-terraform/>

[](https://github.com/pst)

 [菲利普·斯特鲁贝

菲利普自从 2008 年从大学辍学创建 cloudControl PaaS 并帮助开发人员更快地构建更好的软件以来，他一直是云本地人。从那以后，Philipp 在 Exoscale 从事 IaaS 工作，在 CoreOS 从事 Enterprise Kubernetes 工作，最近在 Container Solutions 担任顾问，帮助组织进行云原生转换。Philipp 是 Kubestack 开源框架的维护者。Kubestack 是一个 Terraform GitOps 框架，面向希望自动化基础设施的团队，而不是重新发明自动化。](https://github.com/pst) [](https://github.com/pst)

Terraform 是由 HashiCorp 管理的一个开源项目，在将基础设施定义和维护为代码方面非常强大。结合声明式 API，如云提供商 API，它可以确定、预览和应用对编码基础设施的更改。

因此，团队通常使用 Terraform 来定义他们的 Kubernetes 集群的基础设施。作为一个构建平台的平台，Kubernetes 通常需要一些额外的服务才能部署工作负载。想想入口控制器或日志和监控代理等等。但是，尽管 Kubernetes 有自己的声明式 API，并且从与代码存储库相同的基础设施中维护集群的基础设施和服务有明显的好处，Terraform 远不是提供 Kubernetes 资源的首选。

有了我维护的开源 Terraform 框架 Kubestack，我的使命是为使用 Terraform 和 Kubernetes 的团队提供最好的开发人员体验。从集群基础设施到集群服务，所有平台组件的统一供应是我不懈追求上述开发者体验的关键。

正因为如此，使用 Terraform 提供 Kubernetes 资源的两种常见方法从未真正吸引过我。

一方面，有 Kubernetes 提供商。虽然它将 Kubernetes 资源集成到 Terraform 中，但在 HCL 中维护 Kubernetes 资源需要大量的工作。尤其是你从上游消费的库本妮特 YAML 葡萄酒。另一方面，还有[舵手提供者](https://registry.terraform.io/providers/hashicorp/helm/latest)和[库贝特尔提供者](https://registry.terraform.io/providers/gavinbunney/kubectl/latest)。这两个使用本地 YAML 代替 HCL，但是没有将 Kubernetes 资源整合到 Terraform 状态中，因此，生命周期。

我相信基于我的 [Kustomization 供应商](https://registry.terraform.io/providers/kbst/kustomization/latest)的模块是一个更好的选择，因为有三个明显的好处:

1.  像 Kustomize 一样，上游 YAML 保持不变，这意味着上游更新需要最少的维护工作。
2.  通过在 HCL 中定义 Kustomize 叠加，所有 Kubernetes 资源都可以使用 Terraform 中的值进行完全自定义。
3.  每个 Kubernetes 资源在 Terraform 状态下被单独跟踪，因此差异和计划显示了实际 Kubernetes 资源的变化。

为了使这些好处不那么抽象，让我们比较一下我的 [Nginx 入口模块](https://www.kubestack.com/catalog/nginx)和使用 Helm provider 提供 [Nginx 入口](https://github.com/kubernetes/ingress-nginx)的[模块。](https://registry.terraform.io/modules/terraform-module/release/helm/latest)

两个示例的地形配置都可以在[这个存储库](https://github.com/kbst/terraform-helm-vs-kustomize)中找到。我们先来看看舵模块。

## 基于舵的模块

该模块的使用非常简单。首先，配置 Kubernetes 和 Helm 提供程序。

```
provider  "kubernetes"  {
config_path      =  "~/.kube/config"
}
provider  "helm"  {
kubernetes  {
config_path  =  "~/.kube/config"
}
}

```

然后定义一个 kubernetes_namespace 并调用 release/helm 模块。

```
resource  "kubernetes_namespace"  "nginx_ingress"  {
metadata  {
name  =  "ingress-nginx"
}
}

module  "nginx_ingress"  {
source   =  "terraform-module/release/helm"
version  =  "2.6.10"
namespace   =  kubernetes_namespace.nginx_ingress.metadata.0.name
repository  =   "https://kubernetes.github.io/ingress-nginx"
app  =  {
name               =  "ingress-nginx"
version           =  "3.33.0"
chart              =  "ingress-nginx"
force_update   =  true
wait               =  false
recreate_pods  =  false
deploy            =  1
}

set  =  [
{
name  =  "replicaCount"
value  =  2
}
]

}

```

如果您现在为此配置运行一个平台计划，您将看到要创建的资源。

Terraform 将执行以下操作:

```
# kubernetes_namespace.nginx_ingress will be created
+  resource  "kubernetes_namespace"  "nginx_ingress"  {
+  id  =  (known after apply)
+  metadata  {
+  generation           =  (known after apply)
+  name                    =  "ingress-nginx"
+  resource_version  =  (known after apply)
+  uid                     =  (known after apply)
}
}

# module.nginx_ingress.helm_release.this[0] will be created
+  resource  "helm_release"  "this"  {
+  atomic                                =  false
+  chart                                 =  "ingress-nginx"
+  cleanup_on_fail                  =  false
+  create_namespace                 =  false
+  dependency_update               =  false
+  disable_crd_hooks               =  false
+  disable_openapi_validation  =  false
+  disable_webhooks                 =  false
+  force_update                       =  true
+  id                                      =  (known after apply)
+  lint                                   =  true
+  manifest                             =  (known after apply)
+  max_history                        =  0
+  metadata                             =  (known after apply)
+  name                                   =  "ingress-nginx"
+  namespace                           =  "ingress-nginx"
+  recreate_pods                     =  false
+  render_subchart_notes         =  true
+  replace                              =  false
+  repository                          =  "https://kubernetes.github.io/ingress-nginx"
+  reset_values                       =  false
+  reuse_values                       =  false
+  skip_crds                           =  false
+  status                                =  "deployed"
+  timeout                              =  300
+  values                                =  []
+  verify                                =  false
+  version                              =  "3.33.0"
+  wait                                   =  false
+  wait_for_jobs                     =  false
+  set  {
+  name   =  "replicaCount"
+  value  =  "2"
}

}

Plan:  2  to add,  0  to change,  0  to destroy.

```

这是 Helm 如何集成到 Terraform 工作流程中的关键问题。该计划没有告诉你 Kubernetes 将为 Nginx 入口控制器创建什么资源。在 Terraform 状态下也不会跟踪 Kubernetes 资源，如 apply 输出所示。

```
kubernetes_namespace.nginx_ingress:  Creating...

kubernetes_namespace.nginx_ingress:  Creation complete after  0s  [id=ingress-nginx]

module.nginx_ingress.helm_release.this[0]:  Creating...

module.nginx_ingress.helm_release.this[0]:  Creation complete after  6s  [id=ingress-nginx]

Apply complete!  Resources:  2  added,  0  changed,  0  destroyed.

```

类似地，如果计划变更，也没有办法知道 Kubernetes 资源会有什么变化。

因此，如果您增加 Helm 图表的 replicaCount 值，terraform 计划将仅显示对 helm_release 资源的更改。

```
set  =  [
{
name  =  "replicaCount"
value  =  2
}
]

```

库伯内特资源会有什么变化？更重要的是，它是简单的就地更新，还是需要销毁并重新创建？看计划，你无从得知。

Terraform 将执行以下操作:

```
# module.nginx_ingress.helm_release.this[0] will be updated in-place

~  resource  "helm_release"  "this"  {
id                                      =  "ingress-nginx"
name                                   =  "ingress-nginx"
# (27 unchanged attributes hidden)

-  set  {
-  name   =  "replicaCount"  -&gt;  null
-  value  =  "2"  -&gt;  null
}

+  set  {
+  name   =  "replicaCount"
+  value  =  "3"
}

}

Plan:  0  to add,  1  to change,  0  to destroy.

```

## 基于 Kustomize 的模块

现在，让我们看看基于 Kustomize 的模块的相同步骤。用法差不多。首先，需要 kbst/kustomization 提供程序并对其进行配置。

```
terraform  {
required_providers  {
kustomization  =  {
source  =  "kbst/kustomization"
}
}
}
provider  "kustomization"  {
kubeconfig_path  =  "~/.kube/config"
}

```

然后调用 nginx/kustomization 模块。

```
module  "nginx_ingress"  {
source  =  "kbst.xyz/catalog/nginx/kustomization"
version  =  "0.46.0-kbst.1"
configuration_base_key  =  "default"
configuration  =  {
default  =  {
replicas  =  [{
name  =  "ingress-nginx-controller"
count  =  2
}]
}
}
}

```

与基于 Helm 的模块不同，当您现在运行 Terraform plan 时，您将单独看到每个 Kubernetes 资源及其实际配置。为了让这篇博文更好看，我只展示了名称空间的细节。

Terraform 将执行以下操作:

```
# module.nginx_ingress.kustomization_resource.p0["~G_v1_Namespace|~X|ingress-nginx"] will be created

+  resource  "kustomization_resource"  "p0"  {
+  id           =  (known after apply)
+  manifest  =  jsonencode(

{
+  apiVersion  =  "v1"
+  kind           =  "Namespace"
+  metadata     =  {
+  annotations  =  {
+  app.kubernetes.io/version         =  "v0.46.0"
+  catalog.kubestack.com/heritage  =  "kubestack.com/catalog/nginx"
+  catalog.kubestack.com/variant   =  "base"
}

+  labels         =  {
+  app.kubernetes.io/component   =  "ingress-controller"
+  app.kubernetes.io/instance     =  "ingress-nginx"
+  app.kubernetes.io/managed-by  =  "kubestack"
+  app.kubernetes.io/name           =  "nginx"
}

+  name            =  "ingress-nginx"

}
}
)
}

# module.nginx_ingress.kustomization_resource.p1["apps_v1_Deployment|ingress-nginx|ingress-nginx-controller"] will be created
# module.nginx_ingress.kustomization_resource.p1["batch_v1_Job|ingress-nginx|ingress-nginx-admission-create"] will be created
# module.nginx_ingress.kustomization_resource.p1["batch_v1_Job|ingress-nginx|ingress-nginx-admission-patch"] will be created
# module.nginx_ingress.kustomization_resource.p1["rbac.authorization.k8s.io_v1_ClusterRoleBinding|~X|ingress-nginx"] will be created
# module.nginx_ingress.kustomization_resource.p1["rbac.authorization.k8s.io_v1_ClusterRoleBinding|~X|ingress-nginx-admission"] will be created
# module.nginx_ingress.kustomization_resource.p1["rbac.authorization.k8s.io_v1_ClusterRole|~X|ingress-nginx"] will be created
# module.nginx_ingress.kustomization_resource.p1["rbac.authorization.k8s.io_v1_ClusterRole|~X|ingress-nginx-admission"] will be created
# module.nginx_ingress.kustomization_resource.p1["rbac.authorization.k8s.io_v1_RoleBinding|ingress-nginx|ingress-nginx"] will be created
# module.nginx_ingress.kustomization_resource.p1["rbac.authorization.k8s.io_v1_RoleBinding|ingress-nginx|ingress-nginx-admission"] will be created
# module.nginx_ingress.kustomization_resource.p1["rbac.authorization.k8s.io_v1_Role|ingress-nginx|ingress-nginx"] will be created
# module.nginx_ingress.kustomization_resource.p1["rbac.authorization.k8s.io_v1_Role|ingress-nginx|ingress-nginx-admission"] will be created
# module.nginx_ingress.kustomization_resource.p1["~G_v1_ConfigMap|ingress-nginx|ingress-nginx-controller"] will be created
# module.nginx_ingress.kustomization_resource.p1["~G_v1_ServiceAccount|ingress-nginx|ingress-nginx"] will be created
# module.nginx_ingress.kustomization_resource.p1["~G_v1_ServiceAccount|ingress-nginx|ingress-nginx-admission"] will be created
# module.nginx_ingress.kustomization_resource.p1["~G_v1_Service|ingress-nginx|ingress-nginx-controller"] will be created
# module.nginx_ingress.kustomization_resource.p1["~G_v1_Service|ingress-nginx|ingress-nginx-controller-admission"] will be created
# module.nginx_ingress.kustomization_resource.p2["admissionregistration.k8s.io_v1_ValidatingWebhookConfiguration|~X|ingress-nginx-admission"] will be created

```

再次申请，拥有所有个人 Kubernetes 资源。因为模块使用显式的 depends_on 首先处理名称空间和 CRD，最后处理 webhooks，所以资源以正确的顺序可靠地应用。

```
module.nginx_ingress.kustomization_resource.p0["~G_v1_Namespace|~X|ingress-nginx"]:  Creating...
module.nginx_ingress.kustomization_resource.p0["~G_v1_Namespace|~X|ingress-nginx"]:  Creation complete after  0s  [id=aaed3f03-8a4b-481e-b6f0-d01e1701cf2f]
module.nginx_ingress.kustomization_resource.p1["rbac.authorization.k8s.io_v1_ClusterRoleBinding|~X|ingress-nginx"]:  Creating...
module.nginx_ingress.kustomization_resource.p1["apps_v1_Deployment|ingress-nginx|ingress-nginx-controller"]:  Creating...
module.nginx_ingress.kustomization_resource.p1["rbac.authorization.k8s.io_v1_Role|ingress-nginx|ingress-nginx-admission"]:  Creating...
module.nginx_ingress.kustomization_resource.p1["~G_v1_ServiceAccount|ingress-nginx|ingress-nginx-admission"]:  Creating...
module.nginx_ingress.kustomization_resource.p1["rbac.authorization.k8s.io_v1_RoleBinding|ingress-nginx|ingress-nginx"]:  Creating...
...
module.nginx_ingress.kustomization_resource.p1["batch_v1_Job|ingress-nginx|ingress-nginx-admission-create"]:  Creation complete after  3s  [id=a12aea4c-c92c-4655-912e-e8a0ca9bb67a]
module.nginx_ingress.kustomization_resource.p2["admissionregistration.k8s.io_v1_ValidatingWebhookConfiguration|~X|ingress-nginx-admission"]:  Creating...
module.nginx_ingress.kustomization_resource.p2["admissionregistration.k8s.io_v1_ValidatingWebhookConfiguration|~X|ingress-nginx-admission"]:  Creation complete after  0s  [id=b1046e97-bfa7-4427-96d7-c83137da2f8a]
Apply complete!  Resources:  18  added,  0  changed,  0  destroyed.

```

当然，这也意味着如果你像这样增加副本数量…

```
replicas  =  [{
name  =  "ingress-nginx-controller"
count  =  3
}]

```

…地形图显示了哪些 Kubernetes 资源将会发生变化以及有何不同。

Terraform 将执行以下操作:

```
# module.nginx_ingress.kustomization_resource.p1["apps_v1_Deployment|ingress-nginx|ingress-nginx-controller"] will be updated in-place
~  resource  "kustomization_resource"  "p1"  {
id           =  "366bd10d-745e-4172-9153-35ff5fad53d8"
~  manifest  =  jsonencode(
~  {
~  spec           =  {
~  replicas                    =  2  -&gt;  3
# (4 unchanged elements hidden)

}

# (3 unchanged elements hidden)
}
)
}

Plan:  0  to add,  1  to change,  0  to destroy.

```

也许更重要的是，Kustomization provider 还将正确显示资源是否可以使用就地更新进行更改。或者例如因为不可变字段有变化而需要销毁并重新创建。

这是两件事的结果:

1.  正如你刚才看到的，每个 Kubernetes 资源都是在 Terraform 状态下单独处理的
2.  Kustomization 提供者使用 Kubernetes 的服务器端模拟来确定每个资源的差异。

根据试运行的结果，提供商指示 Terraform 创建一个就地或破坏和重建计划。

因此，作为这种更改的一个例子，假设您需要更改 spec.selector.matchLabels。您将在计划摘要中看到 1 个要添加的和 1 个要销毁的。

Terraform 将执行以下操作:

```
# module.nginx_ingress.kustomization_resource.p1["apps_v1_Deployment|ingress-nginx|ingress-nginx-controller"] must be replaced

-/+  resource  "kustomization_resource"  "p1"  {
~  id           =  "d47635ae-16fd-4126-a07c-a9dca0b472c1"  -&gt;  (known after apply)
~  manifest  =  jsonencode(
~  {
~  spec           =  {
~  selector                    =  {
~  matchLabels  =  {
+  example-selector                    =  "example"

# (4 unchanged elements hidden)

}
}

~  template                    =  {
~  metadata  =  {
~  labels         =  {
+  example-selector                    =  "example"

# (4 unchanged elements hidden)

}

# (1 unchanged element hidden)

}

# (1 unchanged element hidden)

}

# (3 unchanged elements hidden)

}

# (2 unchanged elements hidden)

}  # forces replacement
)
}

Plan:  1  to add,  0  to change,  1  to destroy.

```

## 你自己试试

如果您想自己尝试这些模块，您可以使用捆绑上游 YAML 的目录中的一个模块，例如 [Prometheus operator](https://www.kubestack.com/catalog/prometheus) 、 [Cert-Manager](https://www.kubestack.com/catalog/cert-manager) 、 [Sealed secrets](https://www.kubestack.com/catalog/sealed-secrets) 或 [Tekton](https://www.kubestack.com/catalog/tektoncd) 。

但也有一个模块可用于以与目录模块完全相同的方式供应任何 Kubernetes YAML。

## 介入

目前，目录中可用的服务数量仍然有限。

如果你想参与进来，可以在 GitHub 上找到[源码库。](https://github.com/kbst/catalog)

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>