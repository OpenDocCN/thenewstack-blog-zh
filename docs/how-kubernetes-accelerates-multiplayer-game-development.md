# Kubernetes 如何加速多人游戏开发

> 原文：<https://thenewstack.io/how-kubernetes-accelerates-multiplayer-game-development/>

[Honeycomb](https://www.honeycomb.io/) 正在赞助新 Stack 对 Kubecon+CloudNativeCon 北美 2020 的报道。

你知道以前做一个游戏要花多长时间吗？对于像《魔兽世界》这样的多人游戏来说，这可能需要四到五年的时间，根据电脑游戏开发商[网语游戏](https://netspeakgames.com)的平台负责人[多米尼克·格伦](https://www.linkedin.com/in/dominicgreen/?originalSubdomain=uk)的说法，这还不包括游戏发布后不断进行的修补，他在今年的 [KubeCon+CloudNativeCon](https://onlinexperiences.com/scripts/Server.nxp?LASCmd=L:0&AI=1&ShowKey=113608&LoginType=0&InitialDisplay=1&ClientBrowser=0&DisplayItem=NULL&LangLocaleID=0&SSO=1&RFR=https://onlinexperiences.com/Launch/Event.htm?ShowKey=113608) 上讲述了他使用 Kubernetes 建立游戏开发平台的经历。

通过使用 Kubernetes 和容器化的支持工具，Netspeak 已经能够大幅缩短构建多层的时间，现在该公司可以在短短六个月内完成组装。

开发速度在游戏中至关重要。游戏公司需要让他们的产品出现在玩家面前，他们需要反馈来判断游戏是成功还是失败。在免费游戏市场尤其如此，吸引和留住用户对商业成功至关重要，竞争非常激烈。

多人游戏可能需要至少几十名工程师来构建，并且可能经常涉及大量定制后端开发。基础设施团队的角色(或者在格林的情况下，他的角色，因为他是 Netspeak Games 的平台团队)是为了让游戏团队的其他成员，特别是美工人员，轻松完成他们的工作。在他的经验中，只有大约 25%的游戏开发时间花在与技术相关的任务上，而基础设施管理只是其中的一部分。大部分时间花在内容上——这就是为什么游戏公司有这么多艺术家。

尽管如此，合适的基础设施也有助于加快游戏开发的创新部分，格林构建网络游戏平台的目标是尽可能地消除游戏团队的摩擦。但他也必须充分利用自己的时间。为此，他非常依赖开源，除非绝对必要，否则从不从头开始构建任何东西。

即使作为一名工程师，Green 也能够构建一个平台，为成千上万的并发用户提供服务，每秒处理成千上万的请求，可以灵活扩展，可以在多个位置运行，以减少全球用户的延迟，并且仍然易于游戏团队使用。即使有这些限制，Netspeak 也能在六个月内从构思到制作完成游戏。

格林选择 Kubernetes 来管理可扩展性，因为它允许游戏在任何云提供商或裸机上运行——但这并不意味着让游戏平台在 Kubernetes 上运行就能神奇地解决所有问题。

首先，将[虚幻引擎](https://www.unrealengine.com/en-US/)容器化是困难的 Netspeak 使用的版本是在 2005 年重建的，甚至与原生云不兼容。容器化虚幻需要从 Windows 到 Linux 的交叉编译。

让多个容器在一个节点上运行而不发生冲突也是一个挑战。扩大规模很容易，但在不杀死活跃用户的情况下缩小规模也不简单——同样，弄清楚如何在不干扰活跃玩家的情况下升级是一个挑战。格林最终用 [Agones，](https://agones.dev/site/)解决了这些问题，这是一个开源项目，它使得在 Kubernetes 上托管、运行和扩展游戏服务器变得更加容易。

KubeCon+CloudNativeCon 是新堆栈的赞助商。

由 allinonemovie 通过 Pixabay 制作的专题图片。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>