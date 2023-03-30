# Canonical 的快照:好、坏、丑

> 原文：<https://thenewstack.io/canonicals-snap-great-good-bad-ugly/>

几周前，Canonical 宣布了对 Snap 应用交付机制的交叉分发支持，该机制可以支持移动、桌面和基于服务器的应用。这一声明激怒了 Linux 社区的一些人，他们没有看到任何其他 Linux 发行版支持快照的证据。

Snap 是 Canonical 在 Linux 平台上完善 app 打包和交付机制的尝试。Snap 的起源可以追溯到 [Click，这是 Canonical 在 2014 年](https://www.linux.com/news/can-ubuntu-click-address-linus-torvalds-binary-problems)为其移动平台创建的解决方案，用于处理向 Ubuntu 手机和平板电脑用户提供应用程序的复杂性，这是一个与台式机和服务器截然不同的生态系统。此外，移动设备还需要限制应用程序并对它们进行沙箱保护，这样它们就不会危及整个平台。

Click 使开发人员能够将所有依赖项捆绑到单个应用程序包中，因此用户和开发人员不必担心系统和应用程序库的冲突。它允许开发人员在他们的应用程序中使用最新的库，提供新的功能，因为他们与系统上安装的库是分离的。

## 从移动到服务器和物联网

Click 演变为 Snap，Canonical 将其潜在用途扩展到了服务器、云、物联网(IoT)和桌面空间。随着 4 月份 Ubuntu 16.04 的发布，Canonical 正式将 Snap 带到了 Ubuntu 桌面。

Canonical 还在开发 [Snappy Ubuntu Core](http://www.ubuntu.com/cloud/snappy) ，这是一个基于 Linux 的微型操作系统，用于大规模云容器部署、物联网设备等，以及任何需要过渡更新和微小占用空间的东西。Snappy Ubuntu Core 的工作方式或多或少类似于谷歌的 Chrome OS 和 CoreOS，它为系统和应用程序提供基于过渡图像的更新，这些更新可以回滚。同时，它提供了在容器世界中已知的限制。

Snap 是这项技术的灵魂。

## 应用交付的 Linux 混乱

Linux 上现有的应用交付模型有许多缺陷。Linux 世界大多分为 app 打包两大阵营: **rpm** 和 **deb** 。此外，相同发行版的不同版本使用不同的库，因此应用程序开发人员为 Linux 打包应用程序变得非常具有挑战性。

因此，如果发行版仍在使用较旧的库，应用程序开发人员就无法利用最新的库并向用户提供更多功能。

在大多数情况下，开源应用开发者不会打包他们的应用进行分发。流行的或历史悠久的应用程序通常由发行版开发者打包。较新或不太流行的版本要么被上游打包成他们想要支持的发行版，要么根本不作为发行版包提供。当一个应用程序的新版本发布时，这些开发人员会测试该应用程序，然后将其发布到发行版中。正如你所看到的，不是应用开发者只为整个平台写一个应用，在这个例子中是 Linux，而是有很多人把那个应用带给用户。

它增加了更多的复杂性。

有些情况下，Windows 和 MacOS 可以立即获得最新版本，因为应用程序是由主要开发者打包的，而 Linux 发行版可能需要一段时间。这还不是全部；有些发行版很快就能拿到，有些则要等上几周或几个月。

对于像 Skype、Dropbox、Chrome 这样的商业应用，主要开发者有责任打包应用并为不同的发行版提供二进制文件。许多应用程序无法在许多发行版支持的旧版本上运行。

总之，一塌糊涂。

甚至连 Linux 的创始人 Linus Torvalds 也对 Linux 上现有的应用交付模式不满意。他没有为 Linux 平台提供他的应用程序的二进制文件，理由是这一团糟。[Dirk Hohndel](https://plus.google.com/+DirkHohndel/posts),[Subsurface](https://subsurface-divelog.org/)(由 Linus 发起的一个项目)[的维护者解释道](https://plus.google.com/u/0/+DirkHohndel/posts/cFZLu9bEGx2)，“目前有几十个发行版，每个都有不同的规则，每个都有不同版本的不同库，有些还缺少某些库，每个都有不同的打包工具和打包格式……这基本上是在告诉应用程序开发人员‘走开，专注于关注应用程序的平台’"

Red Hat Enterprise Linux 产品管理总监 Gunnar helle kson[表示同意:“应用程序打包非常重要，但所有相关部分的来源和维护也非常重要。](https://twitter.com/ghelleks)

Snap 旨在为这种状态带来一些秩序。但它是否会被采纳完全是另一个问题。

Hellekson 认为，像 Snap 这样的工具并不能“神奇地解决 Linux 发行版之间的互操作性问题，实际上是将更多的维护和安全责任转移给了应用程序供应商。这样，尽管对用户有很多好处，但他们可能会使在 Linux 上开发变得更加困难。”

SUSE 产品和技术项目副总裁[杰拉尔德·普费菲](https://www.suse.com/communities/blog/author/geraldpfeifer/)说:“Snap 的优点与其缺点直接相关……本质上，Snap 相当于静态链接——一方面它很方便，但另一方面在安全性(和安全修补)方面却造成了重复和挑战。

然而，并不是每个人都有相同的看法。[CoreOS 的联合创始人兼首席技术官 Brandon Philips](https://github.com/philips) 告诉我们，容器是 Linux 应用的未来。但是 Docker 容器并不是到处都能用。它们有其局限性。我们需要一个类似容器的解决方案，类似 Snap。

[在另一次采访](https://thenewstack.io/design-system-can-update-greg-kroah-hartman-linux-security/)中，领先的 Linux 内核开发者 [Greg Kroah-Hartman](https://github.com/gregkh) 告诉我们，Android 已经为“你的应用”做了八九年的容器。每个应用程序都在自己的命名空间中运行。除此之外它什么也看不见。那是你必须做的方式。这是 Linux 的未来，也是系统工作的方式。”他说 Snap 是相同的概念，相同的想法。

## Snap 跨平台

Snap 的成功在很大程度上取决于更大的开源社区对它的采用。一个 app 格式如果没人用还有什么用？作为一项 Ubuntu 独有的技术，它甚至可能不会得到其衍生产品如 [Linux Mint](https://www.linuxmint.com/) 、 [KDE neon](https://neon.kde.org/) 或[elemental OS](https://elementary.io/)的官方支持，Snap 可能会面临一个不太成功的职业生涯。

当 Canonical 宣布 Snap 时，它在新闻发布会上声称，它一直在与各种发行版合作，以增加对 Snap 的支持。

Canonical 表示，Snaps 原生适用于 Arch、Debian、Fedora、Kubuntu、Lubuntu、Ubuntu GNOME、Ubuntu Kylin、Ubuntu MATE、Ubuntu Unity 和 Xubuntu。Canonical 还致力于在 CentOS、Elementary、Gentoo、Mint、OpenSUSE、OpenWrt 和 Red Hat Enterprise Linux 上验证快照。

> Canonical 和 SUSE 目前没有参与 Snaps 的协作开发，事实上，这似乎不是开放社区设计和开发的结果，”SUSE 的杰拉德·普费菲说。

Canonical 宣布他们与其他发行版合作，这招致了开源社区一些成员的批评。Fedora 开发人员并不乐意接受这一声明，并批评 Canonical 声称这两个项目之间没有任何合作。

当我们追踪采访 Canonical 创始人[马克·舒托沃尔斯](http://www.markshuttleworth.com/)，询问这些费用时，他回应道，“我们确实与红帽桌面团队进行了简短的交流，并且一直对与所有 Linux 发行版合作以支持快照持开放态度。”

然而，这对引领 Fedora 发行的 Red Hat 来说是个新闻。

“当我们在几个社区与 Canonical 合作时，当他们宣布我们参与这一特定计划时，我们和其他人一样感到惊讶。我们愿意就此进行更多的讨论，并看看 Linux 社区总体上希望如何合作，”Hellekson 说。

SUSE 的官员也淡化了任何合作。“Canonical 和 SUSE 目前没有参与 Snaps 的合作开发，事实上，这似乎不是开放社区设计和开发的结果，”普费菲说。

似乎发生的事情是，Canonical 与其他项目的一些开发人员合作，也许只是少数，他们帮助为其他发行版打包快照。

## 典范并不完美

Canonical 受到的部分阻力可能是其经营方式的副产品。

首先，其他 Linux 公司，如 Red Hat 和 SUSE，在 Fedora 和 openSUSE 方面保持着非常明确的权力分离。Fedora 和 openSUSE 是相当独立的、社区驱动的项目，由社区成员而不是赞助公司做出决定。

相比之下，Ubuntu 是一个规范的产品，同时也是一个社区项目。由于与 openSUSE 和 Fedora 相反，Canonical 可以直接控制 Ubuntu。我们已经在 ownCloud 的案例中了解到；在社区和公司的需求之间保持平衡真的很难；它经常以类似 ownCloud 的灾难告终。

> 问题是一个人如何“工作”一个项目？

此外，许多人觉得 Ubuntu 缺乏透明度。很多 Ubuntu 的主要贡献者都表示失望，因为 Canonical 对 Ubuntu 的主要公告保密，甚至对核心成员也不公开。Ubuntu 成员对 [Ubuntu for Windows](https://insights.ubuntu.com/2016/03/30/ubuntu-on-windows-the-ubuntu-userspace-for-windows-developers/) 或[命运多舛的 Edge](http://news.softpedia.com/news/Dropping-Ubuntu-Edge-Was-Canonical-s-Biggest-Mistake-482327.shtml) 项目一无所知。

“我们不会阻碍事情的发展，”红帽公司首席执行官吉姆·怀特赫斯特回应了一个关于该公司开源方法的问题。“当我们开发产品时，我们不会对人们隐瞒，而是进行一次大的展示，然后说‘这是代码。’我们不这样做。我们从第一天起就一直在社区中工作。我确实认为我们努力成为真正优秀的参与者，我认为这是可以实现的。"

除了这些差异，Canonical 在发布信息时也会犯一些错误。在宣布对 Snap 的跨发行版支持时，情况确实如此；让 Fedora 开发人员烦恼的措辞是“来自多个 Linux 发行版的开发人员”。需要澄清的是，Canonical 从未在[的新闻稿中明确表示与 Fedora](https://insights.ubuntu.com/2016/06/14/universal-snap-packages-launch-on-multiple-linux-distros/) 合作。根据我们收集的信息，没有“官方的”Linux 发行版，如 Fedora、Red Hat、SUSE 或其他。

也就是说，问题是一个人如何“工作”一个项目？如果一个开发应用程序的开发人员与 Ubuntu 开发人员、Fedora 开发人员和 openSUSE 开发人员合作，将该应用程序带到这些平台上，那么说该开发人员与多个发行版合作，将该应用程序带到这些平台上，这是否是错误的？或者开发人员需要与这些发行版的项目负责人进行官方接触才能做出这样的声明？毕竟，这是一个分布式的开源社区。

## 哪里快照？

更大的问题是，Snap 会被其他发行版正式采用吗？这就是事情变得有点复杂的地方。它变成了一个技术和政治问题。

首先，Snap 不是唯一的解决方案。有许多项目试图为 Linux 生态系统提供与发行版无关的打包生态系统。但是在 Linux 发行版中很难找到共识。还有 [AppImage](http://appimage.org/) 和 [Flatpak](http://flatpak.org/) ，为 Snap 提供合适的替代品；[这些项目比 Snap](https://blogs.gnome.org/alexl/2007/08/07/experiments-with-runtime-less-app-bundles/) 存在的时间要长得多。

那么 Canonical 为什么不采用这些解决方案而开始 Click 或 Snap 呢？

“我们研究了一下，发现 AppImage 非常适合‘叶节点’桌面应用，”舒特尔沃斯说。叶节点应用程序不需要与任何其他应用程序集成。Snap 的设计更多是为了打包具有依赖性的应用程序和相关应用程序。快照具有描述这些连接的一系列功能—接口、插头和插槽，以及共享文件等

除此之外，舒特尔沃斯告诉我们，与 AppImage 相比，Snap 的安全性更高，部分原因是手机团队专注于安全性和效率，部分原因是 Snap 使用了更新的内核功能。

Flatpak 被认为是 Canonical 和 Red Hat 竞争的牺牲品，因为它是由 Fedora 人开发的。当我问及此事时，舒特尔沃斯表示这是一个由单一开发商开发的项目。

这解释了为什么 Canonical 继续使用 Snap。

现在，其他发行版会采用吗？Fedora 开发者已经声明他们不会使用 Snap。一名 Fedora 开发人员在邮件列表中写道，“我们当然没有计划在 Fedora 中采用 Snappy，事实上，多个 Fedora 开发人员正在开发一个竞争解决方案 Flatpak。”

Red Hat 之前接受了一个名为 [Upstart](http://upstart.ubuntu.com/getting-started.html) 的系统初始化规范项目。Hellekson 说，“所有这些打包工作还处于初期阶段，我们期待着与所有相关社区合作，让 Linux 用户的生活尽可能轻松。”

除了 Red Hat 和 Canonical 之间的竞争，还有一些技术问题可能会阻碍其他项目在 Snap 上的合作。其中一个原因是，如果开发者为 Snap 项目做出贡献，他们必须签署 CLA(贡献者许可协议)。[规范开发者迈可·何](https://twitter.com/mhall119)说“当开发者想为 Snap 项目本身做贡献时，CLA 是需要的。创建或分发应用程序的快照不需要 CLA。”

[CLAs 允许 Canonical 更改项目的许可。](http://www.ubuntu.com/legal/contributors/licence-agreement-faq)这对 Canonical 有利，因为他们可以重新许可一个项目，允许它与非自由或不兼容的许可证一起使用。开发者通常不喜欢 CLAs。

Nextcloud 的 Frank Karlitschek 告诉我们，它正在终止 Nextcloud 的 CLAs，因为他觉得 CLAs 在开源社区中名声不太好。

当我们问 Red Hat CLAs 是否会抑制围绕 Snap 的合作时，Hellekson 说，“贡献者许可协议确实让我们难以参与。我们相信简单明了的开源许可是一种更好、更具包容性的方法。”

SUSE 的回答也大同小异。普费菲说:“SUSE 的工程师和员工继续为大量的开源项目做出贡献，无论是在工作时间还是在我们自己的时间，在必要的地方我们都签署了 CLAs。然而，无论何时何地，当我们发起或影响项目时，我们都试图远离阶级。我们通常不喜欢分配版权类，这种版权允许组织使用非开源许可证重新许可开源代码。”

当我们问舒特尔沃斯是否会考虑从 Snap 中放弃 class 以获得其他发行版的更广泛支持时，他首先解释了 class 为什么是好的，但随后又说“如果这会有所不同，那么是的，我们会找到一种方法放弃它。”

## 然后还有一个？

随着时间的推移，其中一个相对于另一个的成熟度、受欢迎程度和技术优势可能会给我们留下一个解决方案。我们以前已经在 Upstart 和 systemd 中看到过，systemd 作为一种卓越的技术出现，并成为所有三个领先的 Linux 发行版的默认版本:Ubuntu、RHEL 和 SUSE。

无论哪种情况，这两种技术都处于非常早期的发展阶段，很难说哪个项目会成功。然而，很明显，在以容器为中心的世界里，Linux 确实需要一种新的应用交付机制。

许多公司和社区都表示支持 Snap 这样的解决方案。三星和戴尔在新闻发布会上加入了 Canonical，并表示需要这样的解决方案。在桌面端，LibreOffice 和 Firefox 等项目已经表示支持 Snap。

时间会证明 Snap 是否会在 Ubuntu 之外被采用。无论 Snap 的未来如何，我们都应该给予 Canonical 应有的信任，因为它突破了极限，迫使 Linux 社区的其他人最终专注于解决一个我们已经习以为常，或者可能从未有动力去解决的问题。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>