# GitTorrent:通过 BitTorrent 共享的 Git 存储库的 P2P 网络

> 原文：<https://thenewstack.io/gittorrent-a-p2p-network-of-git-repositories-shared-over-bittorrent/>

GitTorrent 是由 Chris Ball 开发的一个项目，它将允许开发者使用分散的远程 Git 库。虽然 Git 本身在本质上是分布式的——许多开发人员可以拥有自己的项目历史的完整副本——但几乎所有项目都需要一些权威的地方来存放项目代码。目前，这个单一的真实来源将位于一个地方，如 GitHub，并且不会有任何形式的分发或回退。GitTorrent 试图通过在点对点(P2P)网络上存储代码来解决这个问题。不过，你可能会想，既然我们有 GitHub，为什么还会有人想要这个呢？

GitHub 是存放开源代码的主要目的地。鉴于 GitHub 早在 2013 年就达到了[1000 万个存储库](https://github.com/blog/1724-10-million-repositories)，这在这一点上有点过时了。GitHub 已经成为事实上的标准，以至于像微软这样的巨头已经在 GitHub 上托管项目，而不是他们自己的 CodePlex 平台。

微软的 CodePlex 并不是向 GitHub 做出重大且出乎意料的让步的第一个例子。不久前，谷歌宣布关闭谷歌代码，并向 GitHub 卓越的存储库产品脱帽致敬。

我怀疑很多人，包括我自己，会觉得 GitHub 的统治地位有问题。GitHub 也没有让我们担心。但是没有办法保证我们目前所了解和喜爱的 GitHub 在多年以后还是同一个 GitHub。重要的是要记住，即使 GitHub 可以被认为是自由和开源软件的堡垒，GitHub 也为开源本身做出了巨大的贡献( [Hubot](https://hubot.github.com/) )，有人吗？)，组织会随着时间而变化。

## 进入 SourceForge

受人尊敬的老 SourceForge 已经为托管开源项目提供了多年的服务——至少在软件时间表方面。然而，当对 SourceForge 的爱开始转移到 GitHub 时，SourceForge 的心和意图变得苦涩，越来越绝望。为了弥补失去的流量，SourceForge 在他们的下载页面上显示越来越多的广告，其中一些是无意中恶意的。SourceForge 甚至承认——他们应该为此受到表扬——广告问题已经失控。尽管广告可能很烦人，但与 GIMP 项目最近的问题相比，这个问题就相形见绌了。

GIMP 已经厌倦了 SourceForge 的方式，决定停止使用 SourceForge 作为他们代码的下载镜像。SourceForge 的回应是托管 GIMP 的一个版本，这个版本被秘密地[捆绑了广告软件](http://www.infoworld.com/article/2929732/open-source-software/sourceforge-commits-reputational-suicide.html)。这是 SourceForge 声誉的最后一颗钉子:曾经从 SourceForge 到 GitHub 的逐渐迁移变成了全面的大迁移。五年前，甚至十年前，我怀疑任何人都不会想到心爱的 SourceForge 会沦落到如此地步。

虽然 Bitbucket 是另一个很好的源代码库，也是 GitHub 的有力竞争对手，但就开源用户群而言，它仍然有些遥远。SourceForge 的行为在某种程度上被减轻了，因为这一切都发生在他们失宠很久之后。如果 GitHub 要做类似的事情，有没有类似的服务可供选择？不管是哪家公司，这种风险总是存在的。真正减少这种机会的唯一方法是拥有一个 Git 托管服务，就像 Git 本身一样去中心化。

GitTorrent 使用多种技术来避免这些可能来自非分布式来源(如 GitHub)的问题。除了 Git 本身，GitTorrent 还引入了 Torrenting P2P 技术，以及比特币区块链。虽然最后一个区块链组件还没有准备好投入使用，但它正在积极开发中，到目前为止所做的工作非常出色。

## GitTorrent 组件

让我们更深入地了解一下每个组件。让我们从 Git 的可扩展网络协议开始。安装后，可以使用 GitTorrent 前缀克隆一个 repo。例如，要克隆 Hubot repo，我们将调用以下命令:

|  | 

gitclonegit torrent://github . com/github/hubot

 |

这是将`git clone`命令传递给`git-remote-gittorrent`，然后它将处理 url。这个 Git 传输助手也可以用于其他操作，比如获取、克隆和推送。

因此，这可能看起来有点奇怪，我们刚刚谈到 GitTorrent 是一种避免 GitHub 的方法，然后我们做的第一件事是指向 GitHub repo 然而，这里并不像看上去那么简单。从这里开始，GitTorrent 实际上不会从 GitHub 下载任何文件；我们只是询问 GitHub 对存储库的最新提交是什么。在我们确定该提交的唯一 Git SHA1 是什么之后，我们将询问 GitTorrent 网络上的对等体他们是否有那个 SHA1，然后我们将从对等体下载 Git 对象。具体来说，我们将获取特定 Git 项目的所有提交。就像常规的 Torrenting 一样，我们将从不同的用户那里获取不同的提交，有些用户甚至可能没有完整的提交集。

此外，GitHub 还有另一种工作方式，它不使用 GitTorrent 之外的任何东西。每个 GitTorrent 用户都有一个公钥。如果我们输入用户公钥散列的 SHA1:
，我们就可以从用户那里获得特定的回购协议

|  | 

git克隆git torrent:///reponame

 |

虽然通过散列来引用用户在概念上很简单，但是散列值并不能成为容易记忆的用户名。目前正在研究的一种替代方案是在比特币区块链中对用户信息进行编码，但这一工作目前仍在进行中。

不管你用上面哪种风格查询回购，下一步都涉及到 GitTorrent 网络的分布式哈希表。这个分布式哈希表非常像 BiTtorrent 的分布式哈希表。对于我们感兴趣下载的每个 Git 提交，作为 repo 的一部分，我们可以要求分布式哈希表为我们提供具有我们正在寻找的特定提交的节点。

为了从对等点实际下载这些文件——类似于 Git transport helper——有一个 BitTorrent 协议扩展来促进传输。在连接到一个节点后，客户机将把它的请求作为 bencoded JSON 发送。下面是一个来自[gitorrent 项目](https://github.com/cjb/GitTorrent)的请求响应示例。

一旦一个客户端连接到另一个节点，它就发送一个请求，请求它正在寻找的 SHA1 作为 bencoded JSON:

|  | 

{gitorrent:问:【sha1】}

 |

提供 packfile 的节点返回:

|  | 

{gitorrent:sentorrent:【info hash】}

 |

## 结论

虽然 GitTorrent 项目还有点新，但看起来它有很大的希望。BitTorrent 和 Git 都已经存在一段时间了，看到这个项目如何将它们结合在一起是很有趣的。使用比特币区块链进行验证也是一个非常有趣的想法，我很好奇它会如何发展。如果你之前错过了，一定要看看这个项目的 [GitHub Repo](https://github.com/cjb/GitTorrent) ，并尽可能为其做出贡献。

专题图片:[米奇奥特曼](https://www.flickr.com/photos/maltman23/)的《[北京 2014 年 11 月](https://www.flickr.com/photos/maltman23/15154373634/in/photolist-dPcqJ1-oRswTL-x6p7KR-gmZd-3YdgT-gmZp-gmZo-mVta-fqC5AM-p698j3)》在 [CC BY-SA 2.0](https://creativecommons.org/licenses/by-sa/2.0/) 下授权。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>