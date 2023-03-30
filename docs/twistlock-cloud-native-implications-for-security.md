# Twistlock:云对安全性的固有影响

> 原文：<https://thenewstack.io/twistlock-cloud-native-implications-for-security/>

Twistlock 赞助了这个播客。

[云安全与扭锁 18.11](https://thenewstack.simplecast.com/episodes/cloud-native-implications-for-security-and-twistlock-18-11)

云原生架构需要一种新的安全方法。云原生堆栈不像分层前端、中间件和后端层那样以可预测和紧密耦合的方式进行通信。由微服务和无服务器功能组成的应用程序是松散耦合的代码片段，它们以独特的异步方式相互交流——而且数量呈指数级增长。

“这是一个复杂性的爆炸，”上个月在西雅图的 KubeCon + CloudNativeCon 的播客采访中， [Twistlock](https://www.twistlock.com/) 的福音传道总监 Sonya Koptyev 说。

在管理如此复杂的环境时，运营和安全团队甚至很难知道开发人员在不同的云提供商上运行了哪些服务，更不用说识别和修复关键漏洞，例如 Kubernetes 中最近出现的重大[权限提升漏洞，如果不修补，攻击者将能够接管整个计算节点。](/critical-vulnerability-allows-kubernetes-node-hacking/)

Koptyev 说:“一旦[公司]超过了几百名员工，他们就会有各种各样的服务在运行，而安全团队对此一无所知，这样一来，就会给环境带来各种各样的漏洞和威胁。”。“安全团队无法保护它们，因为他们不了解它们。”

Twistlock 倡导一种由三部分组成的补救方法，将开发人员、运营人员和安全专家聚集在同一页面上。这种“深度防御”策略始于可见性:了解哪些云服务正在被使用，来自哪些提供商，这些服务之间的正常交互是什么样的，以及跟踪基础架构中存在关键漏洞的位置。第二是对常规行为模式中的异常情况的感知，以便检测匿名访问。最后是运行时防御，它允许规则和检查点触发任何显示异常行为的容器的自动关闭，作为防止利用的一种手段。

一旦代码进入生产阶段，这种检查就会发生，但也是至关重要的，在它离开软件开发生命周期的构建阶段之前。开发人员能够在编写代码时解决潜在的安全性和合规性问题。代码必须通过一定的安全检查，然后才能发布。这种方法允许开发人员快速地将代码交付到产品中，同时保持合规性和安全性标准。

“这是一种全团队的安全方法。我们帮助使它成为每个人的责任，”科普特耶夫说。

随着其最新的 [18.11 版本](https://thenewstack.io/twistlock-enhances-visibility-into-multicloud-istio-kubernetes/)，Twistlock 的云原生安全工具增加了许多新功能，包括云平台合规性，允许团队找到云提供商正在使用的所有服务，并在仪表板上可视化它们。新版本还集成了 Istio 服务网格，允许跨 Istio 组件进行漏洞和合规性检查，以及它为其他云服务提供的检查。

[https://www.youtube.com/embed/4aQ1KJE6Lrs?feature=oembed](https://www.youtube.com/embed/4aQ1KJE6Lrs?feature=oembed)

视频

### 在这个版本中:

[2:45:](https://thenewstack.simplecast.com/episodes/cloud-native-implications-for-security-and-twistlock-18-11?t=2:45) 你能告诉我们你的开发团队在 Twistlock 18.11 版本中关注了什么吗？
[5:52:](https://thenewstack.simplecast.com/episodes/cloud-native-implications-for-security-and-twistlock-18-11?t=5:52) 论多云之回潮。
[9:58:](https://thenewstack.simplecast.com/episodes/cloud-native-implications-for-security-and-twistlock-18-11?t=9:58) 我们来说说服务网格组件。在服务网状循环中，您的客户处于什么位置？
[14:27:](https://thenewstack.simplecast.com/episodes/cloud-native-implications-for-security-and-twistlock-18-11?t=14:27) 其中有多少可以自动化？
[17:17:](https://thenewstack.simplecast.com/episodes/cloud-native-implications-for-security-and-twistlock-18-11?t=17:17) 利用 18.11 Twistlock 工具，您能检测到这个严重漏洞吗？
[20:41:](https://thenewstack.simplecast.com/episodes/cloud-native-implications-for-security-and-twistlock-18-11?t=20:41) 以自动化的方式主动出击。

KubeCon + CloudNativeCon 是新堆栈的赞助商。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>