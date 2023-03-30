# 重新思考服务网格与应用流量管理

> 原文：<https://thenewstack.io/rethinking-service-mesh-with-application-traffic-management/>

[](https://www.linkedin.com/in/malanmurphy/)

 [艾伦·墨菲

艾伦是 F5 Networks NGINX 服务网格的高级产品经理。](https://www.linkedin.com/in/malanmurphy/) [](https://www.linkedin.com/in/malanmurphy/)

当许多客户说他们需要一个[服务网格](https://www.nginx.com/resources/glossary/service-mesh/)时，他们不是在谈论一个实际的服务网格。他们真正需要的是一种更好的方式来管理、观察、保护和扩展由[微服务](https://www.nginx.com/resources/glossary/microservices/)组成的应用。换个角度说，他们不要挖掘机，这样可以打基础；他们想在地上挖个洞。他们如何得到这个洞远没有洞的大小和深度重要。

不清楚实际需要什么是一个迹象，表明围绕 Kubernetes 和服务网的所有宣传已经淹没了首要原则的概念。[云原生](https://www.nginx.com/resources/glossary/cloud-native-app-delivery/)应用最重要的元素是将应用流量“最后一英里”交付给最终用户，无论这些用户是人类客户、服务器还是物联网设备。对于内部应用程序，客户通常是组织内拥有由基于微服务的应用程序组成的服务的其他团队。

在 Kubernetes 和服务网之外的更广泛的技术领域，最后一英里交付的责任落在了[应用交付控制器](https://www.nginx.com/resources/glossary/application-delivery-controller/)(ADC)身上，这是一个价值数十亿美元的行业，有几十个参与者。ADC 是确保出色最终用户应用体验的最重要因素。换句话说，ADC——及其管理、塑造和优化应用([第 7 层](https://www.nginx.com/resources/glossary/layer-7-load-balancing/))流量的能力——就是在地上挖洞的挖掘机。它是在应用程序体验中传递首要原则的媒介。

然而，在 Kubernetes 领域，ADC 和第 7 层流量管理基本缺失。

事实上，尽管 ADC 有其历史和市场验证，但应用流量管理可能是云原生环境中开发最少的元素。Kubernetes 传统上专注于网络层([第 4 层](https://www.nginx.com/resources/glossary/layer-4-load-balancing/))，第 7 层仍然是事后才想到的。这使得平台运营团队不得不自己保护自己，或者使用相对未经测试的解决方案，即使对于任务关键型应用程序也是如此。那么，Kubernetes 和服务网格架构师能做些什么来提升他们的游戏，并提供确保卓越的最终用户体验所需的健壮的应用流量管理呢？这里有三点建议。

## **1。部署具有最大第 7 层功能的数据平面**

虽然 Kubernetes 中有多种传输网络选项(想想容器网络接口)，但第 7 层的应用流量管理几乎没有。通过将具有丰富的第 4 层和第 7 层流量功能的数据平面侧柜附加到您的应用程序容器，您能够有效地管理网络和应用程序流量。出于我们上面讨论的所有原因，这两种类型的流量确实需要处于平等的地位。更丰富的数据平面使您能够专注于提供您的架构和复合应用程序所需的第 7 层功能，即安全性、可观察性、稳定性和弹性，同时在第 4 层增加可靠性和安全性。仅仅以可接受的速度推送数据包是不够的。您不会只接受 Kubernetes 之外的第 4 层功能，那么为什么要在 Kubernetes 和服务网格环境中接受它呢？

## **2。为应用而非工具设计您的集群**

您已经构建了 Kubernetes 环境来托管应用程序。然而，在设计和调整集群时，我们经常会问“我需要多少个[入口控制器](https://www.nginx.com/resources/glossary/kubernetes-ingress-controller)”而不是“我的应用需要什么类型的支持交付服务？”计算入口控制器而不考虑服务就像根据有多少人通过前门而不是他们需要在办公室做什么来设计摩天大楼。必须符合行业标准的应用——如医疗保健、金融服务和政府——可能需要不同的应用服务，而不是通用的微服务。即使是相同的服务，在两种不同的环境中也会有完全不同的需求。例如，如果一个数据流应用程序是持续监测患者生命体征的后端，而不是跟踪入站天气数据，则它可能有不同的可用性和安全性要求。

## **3。考虑将 ADC 部署为 Kubernetes 架构的一部分**

您在基础架构的其他任何地方都在应用程序安全性和灵活性方面进行了大量投资，包括在本地使用传统负载平衡器、使用 vADCs 进行虚拟化，以及在云中使用前端云原生负载平衡器。那么，为什么不在 Kubernetes 和您的服务网上投资同样的功能和基础设施呢？您计划使用 Kubernetes 来交付生产应用程序，对吗？最后一英里可能会成为集装箱化环境中的最后一英寸，但交通管理仍然至关重要。ADC 针对应用交付进行了优化，体现了数十年来从流量整形、加速和过滤中获得的智慧。

## **结论:ADC 是你的挖掘机**

纵观其历史，ADC 发展成为计算基础设施中每一次范式转变的前端流量解决方案:本地裸机、co-lo 架顶式、虚拟化以及云计算。Kubernetes 和容器化是最新的迭代，但有效管理应用交付以确保卓越的用户体验和优化运行全球规模应用的成本的需求保持不变。

在 Kubernetes 中，您仍然需要内容加速和缓存、SSL 终端、web 应用程序防火墙和负载平衡。这些功能最好作为统一流量管理解决方案中的补充功能。对于 Kubernetes 来说，需求是相同的，只是外形略有不同，并且需要适应更短暂和动态的基础设施。因此，请考虑在您的 Kubernetes 集群前安装云原生 ADC，以实现更高级别的应用管理，并使服务交付更加顺畅、可靠和安全。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>