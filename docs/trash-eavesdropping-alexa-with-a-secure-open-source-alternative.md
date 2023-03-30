# 垃圾窃听 Alexa 与一个安全的开源替代

> 原文：<https://thenewstack.io/trash-eavesdropping-alexa-with-a-secure-open-source-alternative/>

Linux 基金会赞助了这篇文章。

 [金永国

Yongkook 是 Vicom Infinity 的大型机工程师/架构师。Yongkook 的职业生涯始于 IBM Z 密码协处理器的逻辑设计工程师。12 年来，他一直是纽约大都会区 Z 客户的技术顾问，现在是 IBM 首要业务合作伙伴 Vicom Infinity 的解决方案架构师。他最近的兴趣是将 IBM Z 与开源软件、区块链、物联网和语音用户界面(VUI)等新技术联系起来。](https://www.linuxfoundation.org/) 

*“亚历克莎，今天天气怎么样？”*

每天，当我为孩子们准备上学的背包时，我都会问 Alexa Echo 这个问题。这很方便，我不需要看我的智能手机就知道如何给他们穿衣服。

语音用户界面和语音助理设备已经成为我们日常生活中不可或缺的一部分。很可能你家里有一两台 Alexas，或者想过买一台作为礼物。虽然它可能无法完美地理解您提出的所有问题，也不具备您期望的所有功能，但它已经取得了长足的进步。

像《钢铁侠》中的“贾维斯”这样的电脑对话已经发展成为真正的对话引擎。这是一个不可避免的变化，电脑用户界面将在我的孩子这一代司空见惯。他们会像我们今天使用鼠标或触摸屏一样使用这项技术。

但是，仍然有很多人不喜欢使用这项技术。许多人担心[有人在偷听他们的谈话。这种担忧并非空穴来风——已经有多起](https://www.bloomberg.com/news/articles/2019-04-10/is-anyone-listening-to-you-on-alexa-a-global-team-reviews-audio)[事件报道](https://www.bloomberg.com/news/articles/2019-04-24/amazon-s-alexa-reviewers-can-access-customers-home-addresses)称这些设备和提供商缺乏 100%的隐私保护。这些设备不仅会侵犯隐私，还会暴露关键的公司数据。

因此，我想创建并演示一种方法来保护语音数据和对话，以及对话中的操作/约定，以便在企业中使用。 [Vicom Infinity](http://www.vicominfinity.com/) 打造了一款名为 VIVA (Vicom Infinity 语音助手)的设备，可以为企业用户提供安全的语音助手。VIVA 利用了 IBM 以及 Linux 基金会开放大型机项目的三项关键技术——用于 IBM Cloud Private 的 Watson Assistant/STT/TTS、IBM LinuxONE 安全服务容器和开放大型机项目的 Zowe。

首先， [IBM LinuxONE](https://www.ibm.com/it-infrastructure/linuxone) [安全服务容器](https://www.ibm.com/us-en/marketplace/secure-service-container) (SSC)提供了一个超级保护的容器/服务器来托管 API 处理程序的动作。SSC 可以配备[IBM Z crypto express HSM](https://en.wikipedia.org/wiki/IBM_4768)(CEX)，提供 FIPS 140-2 四级安全。IBM Z 十多年来一直提供这种级别的安全性。SSC 将使用受 CEX 主密钥保护的加密密钥对其根文件系统和永久数据存储进行加密。IBM Cloud Private on SSC 使用" [runq "而不是" runc "，](https://github.com/gotoz/runq)部署 Docker 容器，这也为托管多种对话技能和服务提供了另一层安全性。

其次，IBM Watson Assistant，语音转文本和文本转语音将托管在 IBM Cloud Private (ICP)上。ICP 是 IBM 针对本地云解决方案的 Kubernetes 集群管理器版本。您可以免费下载 ICP，并在试用的基础上访问许多软件目录。ICP 还提供各种企业产品。运行在 ICP 上的 IBM Watson 保证了对您的语音和对话数据的完全控制，因为它将位于您的数据中心，带有受保护的存储密钥，而不是位于云中。

最后，VIVA 使用 Open Mainframe Project 的 [Zowe](http://www.zowe.org) 作为框架来协调来自各种来源的 API，尤其是来自 IBM Z 大型机的 API。Zowe 框架最初于去年 8 月推出，它提供了互操作性，并在来自多个供应商的产品和解决方案中使用了最新的 web 技术。它还有助于开发人员使用熟悉的、符合行业标准的开源工具来访问大型机资源和服务。仅仅六个月后，Open Mainframe Project 推出了生产就绪的 Zowe 1.0，它使 z/OS 环境更加“类似云”，旨在改善混合云环境中的集成。

为什么选择 IBM Z？如今，IBM Z 上存储了大量企业数据。例如，超过 80%的信用卡交易都是通过 IBM Z 完成的。因此，如果你刷了卡(或用 Apple Pay 点击),你就有可能与 IBM Z 主机进行交互。因为 Zowe 运行在 IBM Z 上，所以它受到其高度安全的 API 访问控制的保护。

开放主机项目的 Zowe 社区对每个开发人员开放，而不仅仅是主机开发人员，因为它可以作为许多应用程序的主机外部的网关/连接器。

我们的 VIVA 是一个很好的例子，它展示了我们如何使用 Zowe 来管理 IBM Z system APIs，从而使用语音用户界面获取信息。

当我开始或结束一天的工作时，我会问 VIVA 以下一些问题(“嘿 TJ”是为了纪念 IBM 的创始人托马斯·J·沃森):

*“嗨 TJ，目前 CPU 利用率如何？”*

*“嘿 TJ，我的主机怎么样了？”*

要了解更多关于开放主机项目或 Zowe 的信息，请访问开放主机项目的[网站](https://www.openmainframeproject.org)。

通过 Pixabay 的特征图像。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>