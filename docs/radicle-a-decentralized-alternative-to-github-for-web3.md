# radicle:GitHub for web 3 的分散式替代方案

> 原文：<https://thenewstack.io/radicle-a-decentralized-alternative-to-github-for-web3/>

阿姆斯特丹会议于周末举行，结束了为期一周的阿姆斯特丹 T2 会议。日程安排得满满的，会议涵盖了广泛的 Web3 主题。吸引我眼球的一次会议是 Radicle 的[亚历克西斯·塞利耶](https://twitter.com/cloudhead)在周五的一次会议上做的，题为“Radicle 的点对点代码分发”。

你可以在下面的 YouTube 视频中观看会议。我对演讲的想法如下。

[https://www.youtube.com/embed/S-sks01SE4s?feature=oembed](https://www.youtube.com/embed/S-sks01SE4s?feature=oembed)

视频

## 什么是胚根？

Radicle 宣称自己是一个分散的代码协作网络。他们基本上采用了大家熟悉的 [GitHub](https://github.com/about) 和 [GitLab](https://about.gitlab.com/) 作为代码协作的集中存储库，利用了 Git 版本控制系统的全部功能，并增加了去中心化功能——同时还集成了许多 Web3 身份功能。

您可以通过克隆存储在 Git 存储库中的东西来启动 Radicle 项目。因此，如果您已经在使用 Git，但是想要从一个集中式的存储库转移，那么 onboarding 体验是非常无缝的。从视频中的演示可以看出，命令行界面会感觉很熟悉。集中式 GitHub 模型和 Radicle 的版本控制方法之间的一个根本区别是，没有一个单一的不可变的主版本，贡献者合并到其中——每个对等者维护项目的一个分支版本，其中包含他们有兴趣维护的任何更改。

## 恒等式和根号

Radicle 网络中有两种类型的身份，Radicle Link 点对点八卦协议使用这两种身份。有一些单独的身份，基本上相当于在 GitHub 上有一个用户名——但是它们是在 Radicle CLI 中作为密钥对生成的身份。项目是第二种类型的身份，可以由一个或多个个人操作。

与 GitHub 和 GitLab 上的集中式模型不同，在 GitHub 和 git lab 上，你需要注册一个用户帐户，Radicle 让你从 CLI 用一个密钥对创建一个身份。当项目发布到胚根网络中的一个或多个种子节点时，该身份作为项目的一部分持续存在。这种方法的一个好处是，您可以看到一个身份的完整历史，并知道该身份在其参与的所有项目中都是相同的——就像钱包的声誉可以通过区块链的长期参与来确定。

Radicle 还与 ENS 集成，因此您可以直接将. eth 域与 Radicle 身份相关联——这进一步允许将代码项目的参与与其他链上行为联系起来。

## 推动变革

推送更改也很熟悉，因为您仍然在利用“git add”和“git commit”。当您提交更改时，这些更改会发布到您在设置项目时选择的默认种子节点。这可能是一个种子节点，您自己托管并使用 Radicle Link gossip 协议与其他对等方共享，或者您可以依赖 Radicle foundation 维护的一个节点。

项目可以有多个经批准的签署人，他们可以被委派为项目的签署人。如果有多个代表，那么您可以有效地获得多签名类型的支持，其中不止一个代表需要批准对项目的更改。

项目也可以在带有 Radicle network 网络前端的浏览器中查看。任何种子节点都可以充当 web 前端的后端，这取决于项目被推送到哪里。演示中有一个观众提问，如果种子节点关闭，您是否会丢失代码。现在的假设是，您要么还维护代码的本地备份，要么可能推送到多个种子节点。一旦 Radicle 完全建立了它的对等复制，网络中就会有额外的冗余。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>