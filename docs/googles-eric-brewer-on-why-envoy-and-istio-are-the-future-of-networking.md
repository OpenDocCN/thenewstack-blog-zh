# 谷歌的埃里克·布鲁尔解释了为什么 Envoy 和 Istio 是网络的未来

> 原文：<https://thenewstack.io/googles-eric-brewer-on-why-envoy-and-istio-are-the-future-of-networking/>

在本期[新堆栈制造商](https://thenewstack.io/podcasts/makers)播客中，我们采访了[的 Eric Brewer](https://www.linkedin.com/in/eric-brewer-1031254/) 博士，他是谷歌研究员兼基础设施副总裁，也是该公司云原生系统的架构师。自 1994 年以来，他还是加州大学伯克利分校的计算机科学教授[。在最近旧金山的服务网格日活动中，我们采访了布鲁尔博士，他谈到了服务网格，比如谷歌诞生的 Istio。](https://www2.eecs.berkeley.edu/Faculty/Homepages/brewer.html)

布鲁尔说:“Istio 的核心是将开发者从运营中分离出来。”

这种脱钩让双方走得更快，也更有信心。传统上，当开发人员编写服务时，他们非常担心 API，有哪些方法，它是如何工作的？但是，当您部署微服务时，您需要开始考虑其他问题:调用此服务的策略是什么？它有配额吗？它有拒绝服务吗？它是如何被认证的？它是如何保护的？所有这些问题都不是关于 API 做什么，而是操作部分。

[埃里克·布鲁尔谈为什么特使和 Istio 是网络的未来](https://thenewstack.simplecast.com/episodes/eric-brewer-on-why-envoy-and-istio-are-the-future-of-networking)

在过去，这些已经被编码到 API 的源代码中。但是，如果你把操作拉进基础设施，然后由 Istio 管理，Envoy 执行。然后开发人员只需编写 API 的核心部分，这是他们一直想要做的，然后代理服务器处理所有的策略问题。

这为系统提供了速度和灵活性，因为当运营团队想要更改策略时，他们只需通过[特使数据平面](https://www.envoyproxy.io/)进行部署。API 保持不变，开发者不需要做任何改变。事实上，在策略更新时，API 仍然可以运行(在大多数情况下)。

“Istio 解决了开发人员没有着手解决的问题，”布鲁尔说。如果你开始在笔记本电脑上开发服务，并且有五六个服务，你就不需要 Istio 了。但是，当你是一个拥有许多不同团队的企业，这些团队编写的服务彼此之间并不了解，你希望所有这些团队都有共同的策略时，现在你需要 Istio。你需要把管理你的服务视为世界级的事情，他说。

请收听 Brewer 博士关于迁移到服务基础设施、Google 如何创建团队来管理服务以及其他有用提示的演讲。

### 在这个版本中:

[0:57:](https://thenewstack.simplecast.com/episodes/eric-brewer-on-why-envoy-and-istio-are-the-future-of-networking?t=0:57)Istio 的核心是如何将开发人员与运营分离。
T3:23:开发商和运营。
[8:22:](https://thenewstack.simplecast.com/episodes/eric-brewer-on-why-envoy-and-istio-are-the-future-of-networking?t=8:22) 为什么服务网格需要代理。
[12:28:](https://thenewstack.simplecast.com/episodes/eric-brewer-on-why-envoy-and-istio-are-the-future-of-networking?t=12:28)API 的黑盒。
[21:42:](https://thenewstack.simplecast.com/episodes/eric-brewer-on-why-envoy-and-istio-are-the-future-of-networking?t=21:42) 特色旗帜、金丝雀和 CI/CD。
[25:51:](https://thenewstack.simplecast.com/episodes/eric-brewer-on-why-envoy-and-istio-are-the-future-of-networking?t=25:51) 工程师应该把他们的教育经费用在什么地方？他们现在能学到什么来真正巩固他们未来 3-5 年的职业生涯？

通过像素的特征图像。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>