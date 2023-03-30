# 通过安全检查缓和库贝内特斯和集装箱 FOMO

> 原文：<https://thenewstack.io/temper-kubernetes-and-container-fomo-through-security/>

[](https://www.threatstack.com/)

 [克里斯·福特

克里斯是 Threat Stack 的产品副总裁，负责产品管理和用户体验。他拥有 20 多年领导产品团队和构建创新安全解决方案的经验，包括数据丢失预防、企业移动性管理和安全云协作。在加入 Threat Stack 之前，Chris 是 Blue Cedar Networks 的首席产品官和安全云协作平台 Intralinks 的产品管理高级副总裁。](https://www.threatstack.com/) [](https://www.threatstack.com/)

Gartner 估计，到 2020 年，50%的公司将使用容器技术，而 2017 年这一比例还不到 20%。很多时候，企业在没有完全理解如何正确保护他们正在部署的新技术的情况下，匆忙采用像容器这样的“热门技术”。通过利用 Kubernetes 等编排工具来加速其容器部署并帮助他们大规模管理多容器集群，公司可能会无意中加倍其不安全的云安全实践。

容器的操作优势是显而易见的，但是让 Kubernetes FOMO (" [害怕错过](https://www.urbandictionary.com/define.php?term=fomo)")忽视在他们的堆栈中实现这些技术的风险，而没有完全理解它们的安全含义，可能会产生重大的有害影响。与[云基础设施安全](https://www.threatstack.com/)的许多方面一样，容器和 Kubernetes 可能会产生重大的、通常是意想不到的影响，组织必须调整其业务和安全运营，以有效降低风险。

## 库伯内特的爆炸半径

“爆炸半径”的概念是许多 Kubernetes 相关攻击场景的核心。类似于受爆炸影响的区域，在这种情况下，爆炸半径指的是恶意方可以从最初的危害点获得多少访问权限。受损的 Kubernetes 控制台可以轻松提升权限并控制集群中的其他节点；因此，任何安全部署都将重点放在访问控制和限制潜在爆炸半径上。

> 对 API 的 etcd 后端的写访问权限相当于获得整个群集的 root 权限，读访问权限可用于快速升级

特别是，网络犯罪分子已经通过在 Shodan 等网络爬虫上搜索[来瞄准 Kubernetes 的后端数据库(etcd ),因为许多企业由于缺乏技术经验而没有给予他们充分的保护。根据](https://nakedsecurity.sophos.com/2018/03/26/shodan-and-passwords-sitting-in-a-tree-s-h-o-w-i-n-g/) [Kubernetes](https://kubernetes.io/docs/tasks/administer-cluster/securing-a-cluster/) ['](https://kubernetes.io/docs/tasks/administer-cluster/securing-a-cluster/) [安全文档](https://kubernetes.io/docs/tasks/administer-cluster/securing-a-cluster/)，“API 对 etcd 后端的写访问权限相当于获得整个集群的 root 权限，读访问权限可以用来相当快地升级。”

好消息是 Kubernetes 内置了基于角色的访问控制(RBAC ),可以管理容器访问并限制受损容器的影响。通过利用 Kubernetes 的隔离机制，如名称空间和网络分段，这种隔离得到了进一步加强。

大多数组织还应该尽量减少可以在特权模式下运行的容器的数量，要记住，随着对集群的访问越来越多，爆炸半径会呈指数级增大。

### 在集装箱安全方面，配置错误代价高昂

正如大多数数据泄露可以通过基本的网络安全卫生措施(即例行补丁)来防止一样，[容器安全](https://www.threatstack.com/securing-containerized-environments)从确保每个集群都有适当的安全配置开始。我们的研究表明[73%的公司至少有一个严重的 AWS 安全错误配置](https://www.threatstack.com/blog/what-happens-when-you-sacrifice-security-for-speed-and-common-ways-security-gets-sacrificed)，这种类型的基本错误也延伸到容器。缺乏容器经验的开发和运营团队在部署过程中会增加配置错误的风险，这会将关键数据置于风险之中。

通常，企业没有意识到秘密，包括服务密码和 API 密钥，经常被硬编码到容器中。第三方工具，如 [Docker secrets](https://docs.docker.com/engine/swarm/secrets/) 、 [CyberArk 魔术师](https://www.conjur.org/)和 [HashiCorp Vault](https://www.vaultproject.io/) 使 IT 管理员能够加密这种类型的敏感信息，但许多组织正在犯一个错误，即依赖 Kubernetes 自己的机制来执行这一功能。这种做法实际上没有什么错。但是，如果再加上配置错误，结果可能是灾难性的。Kubernetes 提供了详细的[文档](https://kubernetes.io/docs/concepts/configuration/secret/#risks)，IT 管理员可以用它来帮助他们避免这类错误。

部署 Kubernetes 时出现的另一个常见配置错误是，默认情况下，许多集群都自动配置了一个身份验证令牌来提供对 Kubernetes API 的访问。配置 RBAC 控制有助于降低风险，但是如果该令牌拥有集群管理权限，访问单个容器的攻击者可以[提升这些权限](https://techbeacon.com/hackers-guide-kubernetes-security)并接管整个集群。

确保 Kubernetes 安全的最佳方式是阅读“手册”，也就是[文档](https://kubernetes.io/docs/home/?path=users&persona=app-developer&level=foundational)。组织可以做的第二好的事情是从一开始就在他们的容器和 Kubernetes 部署中构建安全性。通过适当的配置来主动保护您的环境，比在数据泄露发生后试图做出响应要简单得多，也便宜得多。

通过 Pixabay 的特征图像。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>