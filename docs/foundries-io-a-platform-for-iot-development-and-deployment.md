# Foundries.io:物联网开发和部署平台

> 原文：<https://thenewstack.io/foundries-io-a-platform-for-iot-development-and-deployment/>

传统上，如果你的冰箱里有一个电子传感器，制造商会安装它，它会在设备的生命周期内一直存在，即使 10 年后出现安全漏洞，也不会更新。

如今，随着物联网设备的激增，供应商更加意识到需要能够在整个产品生命周期中保护、更新和管理这些设备。与此同时，雇佣工程师来做这件事仍然很困难。

总部位于伦敦的 [Foundries.io](https://foundries.io/) 旨在填补这一空白，为构建、部署和保护[物联网和边缘设备](https://thenewstack.io/category/edge-iot/)提供云原生 [DevOps 平台](https://thenewstack.io/category/devops/)。

“我们着手解决的问题本质上是，当你考虑物联网和边缘设备时，每个设备都是不同的。应用的数量非常非常广泛。从你家里的智能电器到机器人，到生产线，到自动驾驶汽车，甚至宇宙飞船，以及介于两者之间的一切。所以很难想象一个操作系统一个平台就能运行所有这些设备，”Foundries.io 首席执行官[乔治·格雷](https://www.linkedin.com/in/georgegrey/?originalSubdomain=uk)说

从历史上来看，供应商已经创建了自己的操作系统，这是昂贵的。格雷指出，“正如我们开始发现的那样，很难把安全这样复杂的事情做好。”。

我们的想法是创建一个标准平台，“能够进行安全更新，因为我们知道我们会发现我们还不知道的东西。那么在未来，你如何维护所有这些设备 10-15-20 年？”他说。

## **物联网开发“机身”**

首席技术官泰勒·贝克(Tyler Baker)将这个名为 FoundriesFactory 的平台比作航空业，波音(Boeing)和空客(Airbus)等制造商为飞机制造基本的机身，让航空公司定制内部布局。毕竟，航空公司从事的是运输业务，而不是制造业。类似地，设备制造商也在销售设备的创新能力。

FoundriesFactory 提供安全固件、Linux 操作系统、设备和设备群服务、公共和私有云接口以及安全更新后端。

它的基本组件，它称之为工厂，本质上是一个沙箱，使其供应商客户能够在这个基本的“机体”之上构建自己的 IP。

它由许多开源组件组成，这些项目是它的工程师们一直在参与的。它们包括为物联网和边缘设备构建 Linux 微平台(LmP)操作系统的 [Yocto](https://www.yoctoproject.org/software-overview/) 、基于 [OSTree](https://ostreedev.github.io/ostree/introduction/) 的空中更新支持、为 Arm 和其他片上系统(SOC)提供安全固件的 [U-Boot](https://source.denx.de/u-boot/u-boot) 引导加载程序、使用 [Tianocore](https://www.tianocore.org/) 项目为英特尔架构 SOC 上的 Linux 微平台操作系统提供安全引导的统一可扩展固件接口(UEFI)固件，以及 [WireGuard 【T9 它使用 Docker 容器将客户的技术与自己的技术隔离开来。](https://www.wireguard.com/)

它还为所有主要的公共云供应商提供安全接口，并为私有云及内部配置提供协议。

它支持一系列标准开发[板](https://foundries.io/products/hardware-support/)，包括 Arm、Nvidia、恩智浦、Raspberry Pi 等。

“我们的客户是制造产品的人。他们可以更快地将产品推向市场，产品更安全，节省时间，节省大量资金，”格雷说。

“我们让客户能够将他们的投资和资金集中在他们自己的应用程序和知识产权上，而不是所有这些复杂的底层基础架构上。”

[https://www.youtube.com/embed/6sH6Xwp5A7M?feature=oembed](https://www.youtube.com/embed/6sH6Xwp5A7M?feature=oembed)

视频

贝克解释说，在传统的过程中，在本地机器上工作的开发人员构建一个操作系统，将其闪存到他们桌子上的一块板上，将代码放在一些服务器上，团队必须复制该构建，并想出如何将其分发到其他开发人员的板上。

如果您推动变更，有一个中央存储库，一切都需要重建，然后在整个组织内重新刷新以保持一切同步。

“我们说，‘好吧，让我们远离这些。“让我们构建一个云工具，为您提供一切您需要的东西，让您可以进行闪存，一旦您闪存一次，您就再也不用闪存了。”现在你可以将代码推送到云端，它会为你建立，我们会计算出软件的增量，并将增量更新传送到你的设备，”他说。

它允许用户在云中协作构建和创建可重复的构建，由代工厂处理自动化。它在顶部添加了一个设备管理框架。

“一旦他们投入生产，他们就能够基本上规定这些设备应该运行什么版本的软件，有哪些应用程序，什么在里面，什么在外面，他们控制所有这些，”贝克说。

## **安全的同心圆环**

Baker 将其安全性方法称为同心环。他说，安全存在于规划阶段，尽管很难总是运行最新的软件，这将是最安全的。考虑到这一点，它可以确保软件的每一部分都可以更新。

它提供了将设备的信任根设置到硬件中的选项。您可以融合设备，以便 SOC 将只引导正确签名的软件；那么这些密钥存在于 SOC 内部，尽管已经有 SOC 在熔毁级攻击中受损的情况。

您还可以将信任根嵌入到外部硬件安全元素中，并卸载硬件安全措施(HSM)。对于安全引导，它还使用用户空间，因此更新守护程序使用这些硬件安全元素后端进行密钥派生和安全密钥存储。它使用 [TUF 框架](https://theupdateframework.io/)进行安全更新。

第三环涉及教育用户如何采用最佳实践来增强安全性。

“我们正在使用一个水平平台，每个人都可以使用它来构建自己的产品……然后每个客户都可以定制它，并添加他们自己的特殊酱料，他们自己的知识产权。但是因为核心平台是开源的，每个使用它的人都在增加它的功效。…这一切都是公开的；我们的做法符合最佳行业实践。我们正在使用最新的加密算法，并且随着新东西的发现，我们正在为我们所有的客户更新软件，”Grey 说。

## 让物联网开发变得简单

格雷是 [Linaro](https://www.linaro.org/) 的首席执行官，这是一家推进 Arm 生态系统部署的工程组织，当时他看到了代工厂的商业可能性。他与连续创业者、Arm 和英特尔的前高管、Linaro 的非执行董事伊恩·德鲁(Ian Drew)合作开展了这个项目，该项目于 2017 年启动。

该公司最近宣布了由 IQ Capital 牵头的 800 万美元的 A 轮融资，使其总融资额达到 1150 万美元。

它的客户包括加热控制和家庭自动化供应商[施耐德电气](https://www.se.com/us/en/)，滑板车制造商[联合国大学](https://unumotors.com/de-de/scooter/)和“智能”集装箱供应商 [Aeler](https://foundries.io/insights/case-studies/20200622-aeler-c3-containers/) 。

Aeler 的物联网主管 [Quentin Cabrol](https://www.linkedin.com/in/quentincabrol/) 表示:“Foundries 的 Linux 微平台(LmP)即服务在与丰富的物联网节点合作时克服了几个障碍，简化了新产品的开发并缩短了上市时间。

“该平台将我们操作系统的不同元素捆绑在一起，如 air 解决方案、定期平台安全更新和车队管理工具，使我们能够控制在现场向我们的物联网设备逐步部署版本。

“与代工厂合作的另一个优势是降低了成本，因为他们以通用 Linux 板支持包[bsp]的形式在多家使用公司之间分配支持新嵌入式系统架构的成本，而不是像更传统的定制 bsp 那样只在一家公司之间分配。”

Foundries 最近也宣布了与 Arduino 的合作，Arduino 生产开放硬件开发板。用户将能够访问 Arduino Portenta X8 硬件平台的 foundries 工厂。

他们的合作项目之一， [Arduino Pro](https://www.arduino.cc/pro) ，提供了一个面向工业物联网用户的低代码应用开发环境。

“他们所做的是试图让那些不了解构建物联网和边缘产品细节的工业公司变得非常容易——他们只想从传感器中获得数据，并从中操作一些机械，”格雷说。“所以 Arduino 正在使用我们的软件，让客户可以非常容易地做到这一点。Arduino 负责管理平台上的硬件。它们使客户能够在容器中非常简单地构建自己的应用程序和业务逻辑。”

分析公司 Moor Insights & Strategy [指出](https://moorinsightsstrategy.com/wp-content/uploads/2022/06/Foundries.io-Offers-Industrys-First-Complete-Edge-Platform-as-a-Service-for-IoT-Applications-By-Moor-Insights-And-Strategy.pdf)物联网即插即用技术统一了应用开发，就像 iOS 和 Android 统一移动应用以及 Windows 和 Linux 统一 PC 应用一样。然而，处理如此小的外形尺寸的功率、计算需求、安全性、网络、耐用性、可靠性、空中(OTA)更新、长期支持和成本阻碍了该领域的创新，通常需要定制。

除了提供安全性、更新和定制能力之外，开发人员还可以通过代工厂创建容器化的、独立于平台的应用程序。“开发者关注的是应用，而不是操作系统或平台代码，”它说。

“FoundriesFactory 不是一个‘黑盒’开发系统。该代码是开源的，建立在行业标准组件上，不会将项目锁定在特定的芯片、模块或电路板上。这是你所能得到的最经得起未来考验的东西，”它补充道。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>