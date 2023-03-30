# 开放策略代理:5 大 Kubernetes 准入控制策略

> 原文：<https://thenewstack.io/open-policy-agent-the-top-5-kubernetes-admission-control-policies/>

Styra 赞助了这篇文章。

 [托林·桑德尔

Torin 是开放策略代理(OPA)项目的联合创始人。作为一名软件工程师，Torin 已经在大型分布式系统项目上工作了 10 多年。Torin 经常在 KubeCon、DockerCon、Velocity 等活动上发言。在从事 OPA 之前，Torin 是 Cyan(已被 Ciena 收购)的高级软件工程师，负责设计和开发 SDN/NFV 平台的核心组件。](https://www.linkedin.com/in/torin-sandall-1967387/) 

Kubernetes 的开发人员和平台工程师通常承受着巨大的压力，要保持应用程序的快速部署。以 Kubernetes 的规模和实力，这可能会令人望而生畏。也许你是一家零售商，正在为一次大减价推出一项新的电子商务功能。也许你是一家在全球范围内推广金融应用的银行。在这两种情况下，总是会为了速度和进度做出妥协。平台团队越来越有责任确保这些妥协——例如管理入口——不会导致像客户数据暴露在整个互联网上这样的后果。

如果没有正确的政策，Kubernetes 的巨大权力可能会导致与设计一样严重的后果。幸运的是，Kubernetes 为[提供了制定政策](https://kubernetes.io/docs/reference/access-authn-authz/extensible-admission-controllers/)的能力，通过检查并防止部署错误进入生产环境来限制这些后果。为了确保你的团队的应用程序不会比信心更重要，这里是你现在应该在集群中运行的五大 Kubernetes 准入控制策略。

注意:下面的每个示例策略都可以通过开放策略代理(OPA)实现，OPA 是云原生(开源)的事实上的策略引擎。更简单的是，所有这些 OPA 策略都可以通过 [Styra 声明式授权服务(DAS)免费](https://www.styra.com/kubernetes-security-guardrails-with-styra-das-and-open-policy-agent?utm_campaign=MKT%202020-12-16%20The%20New%20Stack%20sponsorship&utm_source=PR&utm_medium=article)在几分钟内跨集群实现。

## **1。可信回购**

这个策略很简单，但是很强大:只允许从可信存储库中提取容器映像，并且可以选择只提取那些与批准的 repo 映像路径列表相匹配的映像。

当然，从互联网上(或者除了可信任的回购之外的任何地方)下载未知的图片会带来风险——比如恶意软件。但是还有其他很好的理由来维护单一的事实来源，例如在企业中启用可支持性。通过确保映像仅来自受信任的回购，您可以严密控制您的映像库存，降低软件熵和蔓延的风险，并提高群集的整体安全性。

*相关政策:*

*   禁止所有带有“最新”图像标签的图像
*   仅允许签名的图像，或匹配特定哈希/SHA 的图像

*样本政策:*

```
package kubernetes.validating.images

deny[msg]  {
  some  i
  input.request.kind.kind  ==  "Pod"
  image  :=  input.request.object.spec.containers[i].image
  not startswith(image,  "hooli.com/")
  msg  :=  sprintf("Image '%v' comes from untrusted registry",  [image])
}

```

## **2。标签安全**

这个策略要求所有的 Kubernetes 资源都包含一个指定的标签，并且使用适当的格式。由于标签决定了 Kubernetes 对象和策略的分组，包括工作负载可以在哪里运行——前端、后端、数据层——以及哪些资源可以发送流量，因此错误的标签会导致生产中难以描述的部署和可支持性问题。此外，如果没有对如何应用标签的访问控制，您的集群就缺乏基本的安全性。最后，手工输入标签的危险在于会出现错误，尤其是因为标签在 Kubernetes 中既非常灵活又非常强大。应用此策略并确保您的标签配置正确且一致。

*相关政策:*

*   确保每个工作负载都需要特定的注释
*   指定污点和容忍度，以限制可以部署映像的位置

*样本策略:*

```
package kubernetes.validating.existence

deny[msg]  {
  not input.request.object.metadata.labels.costcenter
  msg  :=  "Every resource must have a costcenter label"
}

deny[msg]  {
  value  :=  input.request.object.metadata.labels.costcenter
  not startswith(value,  "cccode-")
  msg  :=  sprintf("Costcenter code must start with `cccode-`; found `%v`",  [value])
}

```

## **3。禁止(或指定)特权模式**

这个策略确保了默认情况下，容器不能在特权模式下运行——除非您在特殊情况下(通常很少)允许这样做。

当然，通常您希望避免在特权模式下运行容器，因为它提供了对主机资源和内核功能的访问——包括禁用主机级保护的能力。虽然容器在某种程度上是隔离的，但它们最终共享同一个内核。这意味着，如果一个特权容器受到危害，它就可能成为危害整个系统的起点。尽管如此，还是有合理的理由在特权模式下运行——只要确保这些时间是例外，而不是规则。

*相关政策*:

*   禁止不安全的功能
*   禁止容器以根用户身份运行(以非根用户身份运行)
*   设置用户 ID

*样本策略:*

```
package kubernetes.validating.privileged

deny[msg]  {
  some  c
  input_container[c]
  c.securityContext.privileged
  msg  :=  sprintf("Container '%v' should not run in privileged mode.",  [c.name])
}

input_container[container]  {
  container  :=  input.request.object.spec.containers[_]
}

input_container[container]  {
  container  :=  input.request.object.spec.initContainers[_]
}

```

## **4。定义和控制入口**

入口策略允许您根据需要公开特定服务(允许入口)，或者根据需要公开*无*服务。在 Kubernetes 中，很容易意外地启动一个与公共互联网对话的服务(在 [Kubernetes 失败故事](https://k8s.af/)中有很多这样的例子)。同时，过度许可的进入会导致不必要的外部负载平衡器加速运转，这也会很快变得非常昂贵(如每月预算支出)!此外，当两个服务试图共享同一个入口时，可能会直接破坏您的应用程序。

下面的策略示例防止不同名称空间中的入口对象共享同一个主机名。这一常见问题意味着新工作负载会从现有工作负载中“窃取”互联网流量，从而产生一系列负面后果，从服务中断到数据泄露等等。

*相关政策*:

*   需要 TLS
*   禁止/允许特定端口

*样本策略:*

```
package kubernetes.validating.ingress

deny[msg]  {
  is_ingress
  input_host  :=  input.request.object.spec.rules[_].host
    some other_ns,  other_name
    other_host  :=
    data.kubernetes.ingresses[other_ns][other_name].spec.rules[_].host
  [input_ns,  input_name]  !=  [other_ns,  other_name]

  input_host  ==  other_host

  msg  :=  sprintf("Ingress host conflicts with ingress %v/%v",  [other_ns,  other_name])
}

input_ns  =  input.request.object.metadata.namespace

input_name  =  input.request.object.metadata.name

is_ingress  {
  input.request.kind.kind  ==  "Ingress"
  input.request.kind.group  ==  "extensions"
  input.request.kind.version  ==  "v1beta1"
}

```

## **5。定义和控制出口**

每个应用程序都需要护栏来控制出口流量的流动方式，该策略允许您指定集群内和集群外的通信。与入口一样，默认情况下，很容易意外地“允许出口”到全世界的每个 IP。有时这甚至不是一个意外——全面允许通常是确保新部署的应用程序可以访问的最后一搏，即使它过于宽松或带来风险。在集群内部，也有可能无意中向不应该拥有数据的服务发送数据。如果您的服务受到威胁，这两种情况都会带来数据泄露和失窃的风险。另一方面，对出口的过分限制有时会导致错误配置，破坏应用程序。实现两全其美意味着使用这个策略来选择何时允许出口以及出口到哪些服务。

*相关政策。*

*   请参见上面的入口策略

*样本政策:*

```
package kubernetes.validating.egress

allow_list  :=  {
"10.10.0.0/16",
"192.168.100.1/32"
}

deny[reason]  {
  network_policy_allows_all_egress
  reason  :=  "Network policy allows access to any IP address."
}

deny[reason]  {
  count(allow_list)  >  0
  input.request.kind.kind  ==  "NetworkPolicy"
  input.request.object.spec.policyTypes[_]  ==  "Egress"
  ipBlock  :=  input.request.object.spec.egress[_].to[_].ipBlock
  not  any({t  |  t  :=  net.cidr_contains(allow_list[_],  ipBlock.cidr)})
  reason  :=  "Network policy allows egress traffic outside of allowed IP ranges."
}

network_policy_allows_all_egress  {
  input.request.kind.kind  ==  "NetworkPolicy"
  input.request.object.spec.policyTypes[_]  ==  "Egress"
  egress  :=  input.request.object.spec.egress[_]
  not egress.to
}

```

有了这些政策，你就可以专注于构建一个世界一流的平台——一个可以防止你的应用程序开发人员意外导致整个系统瘫痪、将数据暴露给潜在的窃贼，或者通常为你和你的团队招来手动补救的幽灵的平台。当然，如果你想为 Kubernetes 添加更多必要的政策，请查看[openpolicyagent.org](https://www.openpolicyagent.org/)或探索 [Styra DAS](https://www.styra.com/pricing?utm_campaign=MKT%202020-12-16%20The%20New%20Stack%20sponsorship&utm_source=PR&utm_medium=article) 免费层附带的即插即用政策库。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>