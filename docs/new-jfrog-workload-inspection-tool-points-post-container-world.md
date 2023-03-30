# 新的 JFrog 工作负载检查工具指向后容器时代

> 原文：<https://thenewstack.io/new-jfrog-workload-inspection-tool-points-post-container-world/>

在容器化时代的开端，高端的方法论讨论是关于容器如何改变开发人员对工作负载本质的看法。然后是来自 [HashiCorp 创始人 Mitchell Hashimoto](https://thenewstack.io/new-stack-mitchell-hashimoto-containers-no-containers-one-question-2015/) 和其他人的一些警告，警告说可以想到的控制工作负载的方法都是朝着一个共同目标的不同方法——在这种程度上，我们应该停止将容器视为架构，并着眼于与实现无关的工作负载。

显然，工作负载协调行业已经注意到了这一点。周一， [JFrog](https://www.jfrog.com/) ，其 [Artifactory](https://thenewstack.io/jfrog-announces-artifactory-4-0/) 知识库已经被设计成集成各种开发工具的代码产品，朝着将工作负载与包含它们的格式分离的方向又迈进了一大步。为了回应 Docker Inc .上周发布的容器漏洞扫描器，以及 Twistlock 发布的新改编的容器行为分析系统。这是一个检查系统，它揭示了应用程序与支持它们的操作系统内核和代码库之间的深度依赖关系——无论以何种形式。

“每个人都需要在二进制层面上保护他们的软件，”JFrog 的首席执行官什洛米·本哈姆在接受新堆栈的采访时说，“否则就没有办法实现自动化，没有它就没有 DevOps。而且应该是通用的。”

## 正在扫描什么，为什么

许多早期关于容器的批评——或者在 OCI 形成之前被称为“Docker 容器”——集中在这种格式的可利用性似乎是一个公开的问题。Docker Inc .已经在多个场合解决了这些问题，包括其自己的 Docker 可信注册中心，以及最近的 Docker 安全扫描。

但是开源生态系统的范围更广，包括诸如 Maven 用于 Java 项目的 JAR 和 Node.js 使用的 **[npm 包管理器等格式的包。无论什么样的安全问题会影响 OCI 容器的可利用性，从这个角度来看，都同样会影响包含依赖(甚至非依赖)代码组件的其他包格式的相同特征，这些组件可能包含漏洞。](https://www.sitepoint.com/beginners-guide-node-package-manager/)**

在某种程度上，通过 Xray 的发布，JFrog 使得这个问题不再是 Docker 要解决的问题，而是每个人的问题。本哈姆告诉新的堆栈，它将对软件包进行深度扫描，收集其内容的大量日志，并以开发人员更容易理解的格式制作一个依赖图，直观地描述代码组件之间的依赖关系。然后，它将生成一个影响分析报告，根据 JFrog 之前积累的信息，为开发人员提供这些包(OCI 容器或其他容器)可利用性的最坏情况。

“今天最重要的事情是，当你运送一个集装箱或分发一个包裹时，你基本上不知道里面有什么，”本哈姆说。“有各种各样的安全漏洞、许可证和合规性数据库。虽然您拥有所有这些信息，但是它们并没有为您提供这些图像中包含的内容的依赖关系图。最重要的是，他们无法为您提供开发运维及自动化最重要的东西之一:影响分析。”

本哈姆继续说道，JFrog 此次发布的目标不是克隆那些在中小企业 IT 界如此常见的[绿灯/红灯安全扫描器](http://www.notebookreview.com/softwarereview/system-mechanic-pro-review/)，而是给开发者一份真实的报告，说明他们的代码如何与依赖它的软件交互。通过这种方式，开发人员可以借此机会简化他们的代码，并尽可能减少依赖性。

## 单核的可信度更高

本哈姆表示，x 射线将写入常见的日志数据库，如[黑鸭](https://thenewstack.io/red-hat-enlists-black-duck-fortify-container-security/)、[白源](http://www.whitesourcesoftware.com/how-it-works-setting-up/)和[版本眼](https://www.versioneye.com/)——后者将包含在 x 射线中。当然，新工具将与 JFrog 的 Artifactory 集成，以实时收集构建信息，在将构建提交到生产环境之前呈现依赖图*。首席执行官表示，该图将包括生产环境中的具体影响点，当潜在易受攻击的代码被推向生产时，这些点将受到影响。*

“DevOps 工程师现在正遭受的一件事是，虽然容器是分发你的软件包的一种很好的方式，”他告诉我们，“你仍然需要知道，你仍然需要报告，这个容器映像包括什么……这不仅仅是容器的问题，[*这是人们现在指出的事情之一。它也适用于各种包装。一旦你推出了某样东西，你就想知道它包括什么，它有哪些依赖关系，并确切地知道你过去把它推到了哪里，以及你将来要把它推到哪里。”*

JFrog Xray 将生成的潜在复杂图形可能也适用于单内核的情况，这是一种工作负载打包方式，其中完整的操作系统内核被小型化，替换为只包含软件包可能需要的依赖代码的库。依赖图可以提供直观的证据，表明当应用程序被部署在数据中心时，修整其未使用或无用代码的软件分发可以简化应用程序的组织。包包含的依赖越少，它们被利用的机会就越少，包括在未来。

Docker 是新堆栈的赞助商。

专题图片:[约瑟夫·玛丽亚·埃德尔和爱德华·瓦伦塔在公共领域拍摄的两只青蛙的 x 光照片](https://commons.wikimedia.org/wiki/File:Josef_Maria_Eder,_frog_x-ray.jpg)，大约在 1896 年。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>