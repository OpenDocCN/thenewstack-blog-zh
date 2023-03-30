# 在 OpenShift 上管理 RBAC 的 7 个专家策略

> 原文：<https://thenewstack.io/7-expert-strategies-for-managing-rbac-on-openshift/>

随着容器化和云计算的兴起，保护基础设施和管理细粒度访问控制对于使用 [Red Hat OpenShift 的组织来说是一个巨大的挑战。](https://www.openshift.com/try?utm_content=inline-mention)该平台提供了大量的工具和功能，但保持严格的安全标准意味着在粒度级别管理访问和权限。

如果您是基于角色的访问控制(RBAC)的新手，可能很难跟踪谁可以访问哪些资源，并确保用户只能访问他们需要的资源。

在本文中，我们将探索在 OpenShift 中管理细粒度访问的最佳实践。

OpenShift 中的授权使用基于角色的访问控制(RBAC)来管理。OpenShift 对 RBAC 采用默认拒绝的方法。角色是使用规则集合建立的，这些规则允许对容器集群中的对象执行某些操作。这些角色可以通过角色绑定分配给用户和组。

角色按层次结构排列，允许定义集群范围的角色以及定制的、特定于项目的“本地”角色。RBAC 评估考虑了这种层次结构，首先检查集群范围的角色，然后检查本地角色。这允许在必要时在项目级别增加或覆盖集群范围的角色。

RoleBindings 也遵循相同的集群和本地层次结构，使得[授权](https://thenewstack.io/how-do-authentication-and-authorization-differ/)能够使用公共角色来确定范围。例如，本地绑定可以使用在集群级别定义的角色，将其应用于特定的项目。

以下部分提供了七个推荐的最佳实践，可以帮助组织保护其 OpenShift 基础架构，同时保持有效管理访问和权限的灵活性。

## 1.遵循最小特权原则。

仅授予最低限度的必要访问权限可以降低意外或故意滥用资源的风险。定义角色时，重要的是只包括角色执行其设定功能所需的动词和资源。

定期检查和更新角色以确保他们继续与组织不断变化的需求保持一致也是很好的。通过遵循最小特权原则，组织可以最大限度地减少攻击面，并确保其 OpenShift 集群的安全性。最小特权原则是[整体零信任安全方法](https://thenewstack.io/why-cloud-native-systems-demand-a-zero-trust-approach/)的基石。

这种策略要求一个角色只应被授予对资源的最低限度的必要访问权。

下面是 OpenShift 中遵循最小特权原则的角色定义的一个例子:

```
kind:  Role
apiVersion:  rbac.authorization.k8s.io/v1
metadata:
name:  developer-role
namespace:  dev
rules:
-  apiGroups:  [""]
resources:  ["pods",  "services"]
verbs:  ["get",  "watch",  "list"]

```

在这个例子中，`developer-role`是为`dev`命名空间定义的。该角色只能访问 pod 和服务资源的`get`、`watch`和`list`动词。这允许开发人员查看关于这些资源的信息，但不能对它们进行更改。

这里还有一个例子:

```
kind:  Role
apiVersion:  rbac.authorization.k8s.io/v1
metadata:
name:  admin-role
namespace:  dev
rules:
-  apiGroups:  [""]
resources:  ["pods",  "services",  "replicationcontrollers",  "configmaps",  "secrets"]
verbs:  ["get",  "watch",  "list",  "create",  "update",  "delete"]

```

在这个例子中，`admin-role`也是为`dev`命名空间定义的，但是对资源有更广泛的访问权。该角色可以访问`pods`、`services`、`replicationcontrollers`、`configmaps`和`secrets`资源的所有动词，允许管理员对这些资源执行所有操作。

通过定义仅包含严格要求的动词的角色，组织可以确保用户仅拥有履行其职责所需的访问权限。这有助于最小化攻击面并增加 OpenShift 集群的安全性。

在 OpenShift 中，使用角色和角色绑定来定义访问控制规则。角色定义用户或服务帐户对特定资源类型拥有的权限(动词)。RoleBinding 将角色映射到用户或服务帐户。

下面是一个`Role`定义的例子，它只授予对名称空间
中的`pods`资源进行读访问的严格必需的动词

```
apiVersion:  rbac.authorization.k8s.io/v1
kind:  Role
metadata:
name:  pod-reader
namespace:  my-namespace
rules:
-  apiGroups:  [""]
resources:  ["pods"]
verbs:  ["get",  "watch",  "list"]

```

在本例中，pod-reader 角色对`my-namespace`名称空间中的 pod 资源拥有`get`、`watch`和`list`权限。这意味着具有该角色的用户可以检索有关 pod 的信息，但不能修改或删除它们。

接下来，我们可以使用 RoleBinding 将角色映射到用户或服务帐户:

```
apiVersion:  rbac.authorization.k8s.io/v1
kind:  RoleBinding
metadata:
name:  pod-reader-binding
namespace:  my-namespace
subjects:
-  kind:  User
name:  john-doe
apiGroup:  rbac.authorization.k8s.io
roleRef:
kind:  Role
name:  pod-reader
apiGroup:  rbac.authorization.k8s.io

```

在本例中，`pod-reader-binding`将`pod-reader`角色映射到名为`john-doe`的用户。用户`john-doe`现在拥有对`my-namespace`名称空间中的`pods`资源的读取权限。

通过遵循这种方法，您可以确保授予角色的权限只是严格要求的动词，从而降低意外或故意滥用资源的风险。

## 2.对命名空间资源使用集群角色时要小心。

集群角色是强大的资源，可以提供对整个集群资源的广泛访问。虽然它们在某些情况下很有用，但如果使用不当，也会带来安全风险。

通常更好的做法是使用本地角色，比如作用域在名称空间级别的角色，来提供对特定名称空间的访问。这种方法提供了更细粒度的控制，并降低了授权访问非预期资源的风险。

例如，如果要授予用户对特定名称空间中所有资源的访问权限，可以创建一个具有必要权限的本地角色，并使用 RoleBinding:
将其绑定到用户

```
apiVersion:  rbac.authorization.k8s.io/v1
kind:  Role
metadata:
name:  namespace-admin
namespace:  my-namespace
rules:
-  apiGroups:  ["*"]
resources:  ["*"]
verbs:  ["*"]
---
apiVersion:  rbac.authorization.k8s.io/v1
kind:  RoleBinding
metadata:
name:  namespace-admin-binding
namespace:  my-namespace
subjects:
-  kind:  User
name:  john-doe
apiGroup:  rbac.authorization.k8s.io
roleRef:
kind:  Role
name:  namespace-admin
apiGroup:  rbac.authorization.k8s.io

```

在本例中，`namespace-admin`角色提供了对`my-namespace`名称空间中所有资源的完全访问权。`namespace-admin-binding`将`namespace-admin`角色映射到用户`john-doe`。

通过尽可能使用本地角色和避免集群角色，可以确保对资源的访问受到严格控制，并且仅限于需要的用户。

## 3.使用预定义的集群角色。

OpenShift 团队对预定义的集群角色进行了良好的测试、维护和管理，这有助于确保它们的安全性和稳定性。通过使用预定义的 ClusterRoles，您可以降低定义自定义角色时可能出现的意外行为、安全问题和其他问题的风险。

例如，您可以使用预定义的`cluster-reader` ClusterRole，而不是为用户或服务帐户定义一个定制的 ClusterRole 来访问特定名称空间中的 pod 日志。此集群角色提供对集群中大多数资源的读取权限，包括命名空间中的 pod 日志。

下面是一个角色绑定的例子，它将`cluster-reader` ClusterRole 映射到一个用户或服务帐户:

```
apiVersion:  rbac.authorization.k8s.io/v1
kind:  RoleBinding
metadata:
name:  cluster-reader-binding
subjects:
-  kind:  User
name:  jane-doe
apiGroup:  rbac.authorization.k8s.io
roleRef:
kind:  ClusterRole
name:  cluster-reader
apiGroup:  rbac.authorization.k8s.io

```

在这个例子中，`cluster-reader-binding`将`cluster-reader` ClusterRole 映射到一个名为`jane-doe`的用户。用户`jane-doe`现在可以读取集群中的大多数资源，包括名称空间中 pod 的日志。

## 4.使用特定的服务帐户，而不是默认的服务帐户。

这种做法对授予 pod 的权限提供了更多的控制。创建 pod 后，它可以与特定的服务帐户相关联。这允许您授予 pod 执行其前置功能所需的确切权限，仅此而已。这有助于最大限度地降低意外访问的可能性，并减少集群的攻击面。

下面是如何为 pod 创建特定服务帐户的示例:

```
apiVersion:  v1
kind:  ServiceAccount
metadata:
name:  my-service-account
namespace:  my-namespace
---
apiVersion:  v1
kind:  Pod
metadata:
name:  my-pod
namespace:  my-namespace
spec:
serviceAccountName:  my-service-account
# ... other pod specification

```

在这个例子中，在名称空间`my-namespace`中创建了一个名为`my-service-account`的新服务帐户。然后，通过设置 pod 规范中的`serviceAccountName`字段，指定 pod `my-pod`使用`my-service-account`服务帐户。

最佳做法是为每个 pod 使用特定的服务帐户，而不是依赖默认的服务帐户。通过使用特定的服务帐户，您可以确保每个 pod 的权限是明确的，并且易于记录和跟踪。

## 5.通过组管理绑定。

通过组管理绑定，您可以集中定义一组用户，并使查看和管理组变得更加容易。如果您需要删除用户的绑定，这一点尤其重要，因为您只需要从组中删除用户，而不是更新绑定来删除单个用户。

这里有一个如何使用组来管理绑定的例子:

```
kind:  Group
apiVersion:  user.openshift.io/v1
metadata:
name:  my-group
annotations:
description:  Group for my-app developers
users:
-  developer1
-  developer2

---

kind:  RoleBinding
apiVersion:  rbac.authorization.k8s.io/v1
metadata:
name:  my-rolebinding
namespace:  my-namespace
subjects:
-  kind:  Group
name:  my-group
apiGroup:  user.openshift.io
roleRef:
kind:  Role
name:  my-role
apiGroup:  rbac.authorization.k8s.io 

```

在本例中，创建了一个包含两个用户`developer1`和`developer2`的组`my-group`。然后在名称空间`my-namespace`中创建一个角色绑定`my-rolebinding`，它将组`my-group`作为主题，并将其绑定到角色`my-role`。

(注:apiVersion: `user.openshift.io/v1`用于指定 OpenShift 中集团资源的 API 版本，用于管理平台中的用户和集团定义)。

## 6.定期检查和测试 RBAC 配置。

这对于确保用户能够正确访问他们需要的资源，并且不会被授予不必要的权限非常重要。

以下是检查和测试 access 的一些方法:

使用`oc get`命令检索集群中的 ClusterRoles、ClusterRoleBindings、Roles 和 RoleBindings。例如，要列出集群中的所有集群角色，可以使用以下命令:

使用`oc describe`命令显示特定集群角色、集群角色绑定、角色或角色绑定的详细信息。例如，要显示`cluster-reader`集群角色的详细信息，可以使用以下命令:

```
$  oc describe clusterrole cluster-reader

```

使用`oc auth`命令测试用户对集群中特定资源的访问。例如，要测试用户是否可以在当前名称空间中创建秘密，可以使用以下命令:

```
$  oc auth can-i  create secrets

```

或者，检查用户是否可以在默认名称空间中创建机密:

```
$  oc auth can-i  create secrets  –n  default

```

这将返回 yes 或 no，表明用户是否拥有执行该操作所需的权限。

这些工具可用于定期检查 RBAC 配置和测试访问权限，以确保用户拥有在集群中执行任务的正确权限。

## 7.使用模拟。

模拟是一项强大的功能，它允许管理员临时采用另一个用户的身份以该用户的身份执行操作。这对于排除和调试 RBAC 问题或者允许用户执行原本需要提升权限的操作非常有用。

然而，负责任地使用模拟并理解假装成另一个用户时所执行的操作的含义是很重要的。

例如，您可以使用以下命令来测试一个用户在模拟另一个用户时是否有权限获取部署的详细信息:

```
$  oc auth can-i  --as=<impersonated-user>  get deployments

```

这里有一个 YAML 文件的例子，它创建了一个组，并允许组中的成员扮演`cluster-admin`角色:

```
apiVersion:  v1
kind:  Group
metadata:
name:  impersonators
annotations:
openshift.io/description:  "This group allows members to impersonate cluster-admin for debugging purposes."
users:
-  user1
-  user2

---

apiVersion:  rbac.authorization.k8s.io/v1
kind:  ClusterRoleBinding
metadata:
name:  impersonators-as-admin
roleRef:
apiGroup:  rbac.authorization.k8s.io
kind:  ClusterRole
name:  cluster-admin
subjects:
-  apiGroup:  rbac.authorization.k8s.io
kind:  Group
name:  impersonators

```

有了这个配置之后，“impersonators”组的成员就可以在模拟`cluster-admin`角色时使用下面的命令创建一个秘密:

```
$  oc adm policy add-role-to-user cluster-admin  -z  default  -n  <namespace>

$  oc create secret generic  <secret-name>  --as=cluster-admin  -n  <namespace>

```

(注意:这是一个强大的工具，应该只用于调试目的。模拟应该只授予受信任的用户)。

通过使用`oc auth can-i`插件和模拟测试访问，集群管理员可以验证正确的权限是否已授予正确的用户，并确保 RBAC 策略按设计运行。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>