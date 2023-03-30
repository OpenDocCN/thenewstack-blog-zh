# 以下是您应该保护您的 Etcd 部署的原因

> 原文：<https://thenewstack.io/heres-why-you-should-secure-your-etcd-deployment/>

一名开发人员最近发现，Etcd 是一个键值存储和 Kubernetes 集群的核心组件，用于存储高度敏感的配置数据，但也很容易不受保护。

波多黎各软件开发人员乔瓦尼·科拉佐正在研究由 CoreOS 首先开发的 etcd，并意识到在 2015 年 7 月发布的 2.1 版本之前，它不支持任何类型的身份认证。即使在添加了[之后，出于向后兼容的原因，这个特性在默认情况下](https://coreos.com/etcd/docs/latest/v2/authentication.html)是关闭的。

MongoDB 开发人员过去也采用过类似的方法，导致互联网上数千个不安全的部署被黑客滥用。因此，科拉佐着手研究 etcd 的设计决策是否有类似的效果。

在 Shodan(一个设备和服务搜索引擎)上进行快速搜索，发现有 2284 台 etcd 服务器可以通过 RESTful APIs 从互联网上直接访问。

“我点击了几个，在第三次尝试时，我看到了我不希望看到的，”科拉佐在[的博客文章](https://elweb.co/the-security-footgun-in-etcd/)中说。“凭据，很多凭据。cms_admin、mysql_root、Postgres 等的凭证。”

开发人员编写了一个脚本来抓取 JSON 格式的暴露的 etcd 密钥存储，并在从 1，485 台服务器收集了大约 750MB 的数据后停止。然后，他在数据中搜索有趣的字符串，发现了 8781 个密码，650 个“aws_secret_access_key”实例，23 个“secret_key”实例和 8 个“private_key”实例他还偶然发现了一些证书。

“我没有测试任何证书，但如果我不得不猜测，我会猜测至少有几个应该工作，这是可怕的一部分，”科拉佐说。“任何只有几分钟空闲时间的人都可能最终获得数百个数据库凭据的列表，这些凭据可用于窃取数据或执行勒索软件攻击。”

除了用于存储 Kubernetes 集群数据之外，etcd 还可以与其他工具一起使用，比如 locksmith、vulcand 和 Doorman。因此，除了窃取有价值的秘密，攻击者还可能更改各种服务的配置数据。

管理员应避免将 etcd 部署直接暴露在互联网上，并应通过启用身份验证来保护它们。根据 Kubernetes 官方文档，目前不支持基于用户的 etcd 身份验证模型，但支持基于 TLS 的身份验证，即客户端通过证书来标识自己。

“在配置安全通信后，将 etcd 集群的访问权限限制为仅 Kubernetes API 服务器，”[文档建议](https://kubernetes.io/docs/tasks/administer-cluster/configure-upgrade-etcd/)。

etcd v2 和 [etcd v3](https://coreos.com/etcd/docs/latest/learning/auth_design.html) 中的认证模型[也有区别，后者使用 gRPC 作为其传输，而不是 RESTful 接口。](https://coreos.com/etcd/docs/latest/v2/auth_api.html)

[红帽](https://www.openshift.com/)，最近收购了 CoreOS，是新堆栈的赞助商。

由 [Jason Blackeye](https://unsplash.com/photos/8yYAaguVDgY?utm_source=unsplash&utm_medium=referral&utm_content=creditCopyText) 在 [Unsplash 上拍摄的特征图像。](https://unsplash.com/search/photos/secure?utm_source=unsplash&utm_medium=referral&utm_content=creditCopyText)

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>