# 如何实施云本地计算基金会的安全建议

> 原文：<https://thenewstack.io/how-to-implement-security-recommendations-from-the-cloud-native-computing-foundation/>

[](https://www.linkedin.com/in/vinayvenkat/)

 [Vinay Venkataraghavan

Vinay 是 Palo Alto Networks 首席技术官办公室的技术总监。他在设计和构建云原生和容器化应用以及安全产品方面拥有丰富的经验。](https://www.linkedin.com/in/vinayvenkat/) [](https://www.linkedin.com/in/vinayvenkat/)

考虑到组成云原生应用的工作负载的规模和动态性质，保护云原生应用并非易事。在这些环境中，基于边界的安全方法和静态规则集往往很快就会失效。云中的安全性需要一种范式转变，这种转变侧重于提高应用程序安全生命周期和设计安全架构的自动化程度。

为了应对这一需求，[云原生计算基金会](https://cncf.io/?utm_content=inline-mention)的 Sig-Security 工作组发布了[白皮书](https://www.cncf.io/blog/2020/11/18/announcing-the-cloud-native-security-white-paper/)到[为开发全面云原生安全态势的组织提供指导](https://thenewstack.io/cncf-security-whitepaper-shows-the-complexity-of-securing-cloud-native-operations/)。它强调了在整个云原生开发生命周期中注入安全性的巨大机会，而不是像传统开发方法中经常出现的那样，被单独管理的干预“束缚”住。

在这里，我们强调并总结了一些组织应该采用的关键实践，正如本文所建议的那样。

## **保护应用生命周期**

本文强调了云原生应用开发生命周期:开发、分发、部署和运行时。它将每个阶段呈现为一个独特的安全关注领域，并为每个阶段提供了安全建议，从而创建了一种云原生安全清单。

接下来的几节重点介绍了每个阶段的安全控制建议。

### **开发**

该白皮书建议在部署和运行阶段之前，使用安全工具和技术来识别合规性和安全错误配置。目标是在应用程序生命周期的早期注入并提供对安全问题和违规的可见性。

### **分发**

该白皮书建议扩展通常在此阶段执行的操作的范围，以包括安全测试，如扫描容器图像以查找漏洞和恶意软件的存在。这有助于为安全团队提供一种在开发人员工作流中定义和实施策略的方法。

### **展开**

在将应用程序部署到运行时环境之前，此阶段的建议构成了一组安全“飞行前检查”。

### **运行时环境**

运行时考虑需要解决计算、存储、网络和身份访问管理(IAM)方面的问题；以及规模、活力、零信任等概念。该白皮书建议以自动扩展和发展的方式部署安全性，以满足高度动态环境的需求。

#### **计算机/容器**

#### **网络/细分/零信任**

#### **储存**

#### **IAM**

## **结论**

虽然本文提供了一些粗略的高级建议参考，但本文本身包含了对云安全实践更深入的讨论。这篇论文可以免费下载。

通过 Pixabay 的特征图像。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>