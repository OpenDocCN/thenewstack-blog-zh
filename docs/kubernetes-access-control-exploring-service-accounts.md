# Kubernetes 访问控制:探索服务帐户

> 原文：<https://thenewstack.io/kubernetes-access-control-exploring-service-accounts/>

Kubernetes 有用户和服务帐户的概念来访问资源。用户与密钥和证书相关联，以认证 API 请求。来自群集外部的任何请求都使用配置的方案之一进行身份验证。验证请求最常用的技术是通过 X.509 证书。请参考关于创建证书并将其与用户相关联的教程 [Kubernetes 认证](/a-practical-approach-to-understanding-kubernetes-authentication/)。

重要的是要记住，Kubernetes 没有维护数据库或用户和密码的配置文件。相反，它希望在群集之外对其进行管理。通过身份验证模块的概念，Kubernetes 可以将身份验证委托给第三方，如 OpenID 或 Active Directory。

X.509 证书用于验证外部请求，而服务帐户则用于验证在群集内运行的进程。服务帐户与对 API 服务器进行内部调用的 pod 相关联。

每个 Kubernetes 安装都有一个名为 default 的服务帐户，它与每个正在运行的 pod 相关联。类似地，为了使 pods 能够调用内部 API 服务器端点，有一个名为 Kubernetes 的 ClusterIP 服务。这种组合使得内部流程调用 API 端点成为可能。

```
kubectl get  serviceAccounts

```

```
NAME      SECRETS AGE
default 1 122m

```

```
NAME TYPE        CLUSTER-IP EXTERNAL-IP PORT(S) AGE
kubernetes ClusterIP 10.96.0.1            443/TCP 123m

```

请注意，服务帐户指向安装在每个 pod 内的一个秘密。这个秘密包含 API 服务器所期望的令牌。

```
NAME                  TYPE                                  DATA AGE
default-token-4rpmv kubernetes.io/service-account-token 3      123m

```

当我们实际安排一个 pod 并访问它时，事情就清楚了。我们将推出一个基于 BusyBox 和 curl 命令的 pod。

```
kubectl run  -i  --tty  --rm  curl-tns  --image=radial/busyboxplus:curl

```

```
kubectl run  --generator=deployment/apps.v1 is DEPRECATED and will be removed in  a  future version.  Use kubectl run  --generator=run-pod/v1 or kubectl create instead.
If you don't  see  a  command  prompt,  try pressing enter.
[  root@curl-tns-56c6d54585-6v2xp:/  ]$

```

当我们在 BusyBox shell 中时，让我们尝试访问 API 服务器端点。

```
[  root@curl-tns-56c6d54585-6v2xp:/  ]$  curl https://kubernetes:8443/api

```

这不会产生任何结果，因为请求缺少认证令牌。让我们看看如何检索可以嵌入在 HTTP 头中的令牌。

如前所述，令牌作为秘密安装在 pod 中。导航到*/var/run/secrets/kubernetes . io/service account*找到令牌。

```
[  root@curl-tns-56c6d54585-6v2xp:/  ]$  cd  /var/run/secrets/kubernetes.io/serviceaccount

```

```
[  root@curl-tns-56c6d54585-6v2xp:/tmp/secrets/kubernetes.io/serviceaccount  ]$  ls
ca.crt namespace  token

```

让我们设置几个环境变量来简化 curl 命令。

```
CA_CERT=/var/run/secrets/kubernetes.io/serviceaccount/ca.crt
TOKEN=$(cat  /var/run/secrets/kubernetes.io/serviceaccount/token)
NAMESPACE=$(cat  /var/run/secrets/kubernetes.io/serviceaccount/namespace)

```

下面的 curl 命令请求在默认名称空间中运行的服务列表。让我们看看是否能从 API 服务器得到响应。

```
[  root@curl-tns-56c6d54585-6v2xp:~  ]$  curl  --cacert  $CA_CERT  -H  "Authorization: Bearer $TOKEN"  "https://kubernetes/api/v1/namespaces/$NAMESPACE/services/"

```

```
{
  "kind":  "Status",
  "apiVersion":  "v1",
  "metadata":  {

  },
  "status":  "Failure",
  "message":  "services is forbidden: User \"system:serviceaccount:default:default\" cannot list resource \"services\" in API group \"\" in the namespace \"default\"",
  "reason":  "Forbidden",
  "details":  {
    "kind":  "services"
  },
  "code":  403
}

```

令人惊讶的是，默认服务帐户没有足够的权限来检索运行在同一名称空间中的服务。

请记住，Kubernetes 遵循从关闭到打开的惯例，这意味着默认情况下，任何用户或服务帐户都没有任何权限。

为了满足这个请求，我们需要创建一个角色绑定，将默认服务帐户与适当的角色关联起来。这个工作流类似于我们如何将一个角色绑定到 Bob，授予他列出 pod 的权限。

退出窗格并运行以下命令，为默认服务帐户创建角色绑定。

```
kubectl create rolebinding default-view  \
  --clusterrole=view  \
  --serviceaccount=default:default  \
  --namespace=default

```

```
rolebinding.rbac.authorization.k8s.io/default-view created

```

上面的命令将默认服务帐户与集群角色视图相关联，这使得 pod 能够列出资源。

如果您想了解所有可用的集群角色，可以运行命令， *kubectl get clusterroles* 。

让我们再次启动 BusyBox pod 并访问 API 服务器。

```
kubectl run  -i  --tty  --rm  curl-tns  --image=radial/busyboxplus:curl

```

```
kubectl run  --generator=deployment/apps.v1 is DEPRECATED and will be removed in  a  future version.  Use kubectl run  --generator=run-pod/v1 or kubectl create instead.
If you don't  see  a  command  prompt,  try pressing enter.
[  root@curl-tns-56c6d54585-2cx44:/  ]$

```

```
CA_CERT=/var/run/secrets/kubernetes.io/serviceaccount/ca.crt
TOKEN=$(cat  /var/run/secrets/kubernetes.io/serviceaccount/token)
NAMESPACE=$(cat  /var/run/secrets/kubernetes.io/serviceaccount/namespace)

```

```
curl  --cacert  $CA_CERT  -H  "Authorization: Bearer $TOKEN"  "https://kubernetes/api/v1/namespaces/$NAMESPACE/services/"

```

```
{
  "kind":  "ServiceList",
  "apiVersion":  "v1",
  "metadata":  {
    "selfLink":  "/api/v1/namespaces/default/services/",
    "resourceVersion":  "11076"
  },
  "items":  [
    {
      "metadata":  {
        "name":  "kubernetes",
        "namespace":  "default",
        "selfLink":  "/api/v1/namespaces/default/services/kubernetes",
        "uid":  "b715a117-6be1-4de0-8830-45bddcda701c",
        "resourceVersion":  "151",
        "creationTimestamp":  "2019-08-13T09:45:27Z",
        "labels":  {
          "component":  "apiserver",
          "provider":  "kubernetes"
        }
      },
      "spec":  {
        "ports":  [
          {
            "name":  "https",
            "protocol":  "TCP",
            "port":  443,
            "targetPort":  8443
          }
        ],
        "clusterIP":  "10.96.0.1",
        "type":  "ClusterIP",
        "sessionAffinity":  "None"
      },
      "status":  {
        "loadBalancer":  {

        }
      }
    }
  ]
}

```

随意为默认服务帐户创建额外的绑定，以检查 RBAC 如何扩展到 pods。

Kubernetes 访问控制系列到此结束，在这个系列中，我们讨论了身份验证、授权和服务帐户的基本构件。

*贾纳基拉姆·MSV 的网络研讨会系列“机器智能和现代基础设施(MI2)”提供了涵盖前沿技术的信息丰富、见解深刻的会议。在 [http://mi2.live](http://mi2.live/) 上注册参加即将举行的 MI2 网络研讨会。*

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>