# Parler 真的是一个进步的网络应用吗？

> 原文：<https://thenewstack.io/was-parler-really-a-progressive-web-app/>

出于各种错误的原因，渐进式网络应用程序(PWAs)上周成为一个热门的社交媒体术语。当右翼微博应用 Parler 从谷歌和苹果应用商店下架时，其用户立即开始搜索基于浏览器的版本。他们中的一些人专门寻找 PWA 版本，这导致了这种滑稽的交流:

这么多的问题…但保持事情的技术方面:帕勒的网站实际上是一个 PWA，还是只是一个普通的网站，只是碰巧在移动浏览器中呈现良好？到底什么是 PWA？

事实证明，Parler 用户中的 PWA 搜索并没有持续多久。当亚马逊网络服务取消了 Parler 的主机服务后，网页版也很快关闭了。这可能是 Parler 的末日，除非它能找到一个分布式的应用商店和云主机的替代品。

 [理查德·麦克马努斯

Richard 是 New Stack 的高级编辑，每周撰写一篇关于 web 和应用程序开发趋势的专栏文章。此前，他在 2003 年创立了读写网，并将其打造为全球最具影响力的科技新闻和分析网站之一。](https://twitter.com/ricmac) 

当然，与帕勒为什么会出现在新闻中相比，帕勒的网站是否是 PWA 是一个小问题。关键的争论围绕着像谷歌、苹果和亚马逊这样的“大型科技”公司是否应该“充当监管者”(正如科技分析师 Benedict Evans [所说](https://twitter.com/benedictevans/status/1348322370793172994))并单方面关闭像 Parler 这样有争议的服务。这是一个棘手的问题，因为这涉及到你认为互联网公司——尤其是像 AWS 这样在底层运营的公司——应该拥有多大的权力。这个争论超出了我的范围，但是我建议你关注电子前沿基金会的[讨论。](https://www.eff.org/deeplinks/2021/01/beyond-platforms-private-censorship-parler-and-stack)

对于本专栏，让我们回到 PWA 是什么以及它对未来意味着什么的问题上来。这个术语是 2015 年由谷歌在[创造的，用来描述可以在现代网络浏览器上运行的增强型网络应用。从技术上讲，PWA 只是一个网站，但它经过优化，在浏览器中运行时看起来和感觉上都像一个原生应用程序。](https://developers.google.com/web/updates/2015/12/getting-started-pwa)

在[的一篇介绍性文章](https://web.dev/what-are-pwas/)中，谷歌将 PWAs 定位为具有传统网站的影响力，但也具有一些原生应用程序(如 Android 或 iOS 应用程序)的功能。谷歌是这样定义的:

*“渐进式网络应用程序(PWA)是使用现代 API 构建和增强的，以提供增强的功能、可靠性和可安装性，同时使用单一代码库在任何设备上向任何人、任何地方提供服务。”*

顺便说一句，PWA 这个名字应该是暂时的。谷歌工程师[亚历克斯·罗素](https://twitter.com/slightlylate)和[弗朗西斯·贝里曼](https://twitter.com/phae)一起想出了这个主意。拉塞尔[在推特](https://twitter.com/slightlylate/status/1347736468802871296)上表示，它“从来就不是终端用户的名字。”然而，这个词似乎已经流行起来，并被广泛用于指与原生移动应用程序有类似用户体验的网站。但是正如我将在这篇文章的其余部分解释的那样，成为一名 PWA 的意义远不止于此。

## PWA 的定义特征

现在，web 技术可能实现的一些高级功能是“文件系统访问、媒体控制、应用程序标记和完全剪贴板支持”这些都是本机应用程序熟悉的功能，因为它们可以直接访问您设备的操作系统。但是现在有了新的 API，web 应用程序也可以访问至少一些操作系统级别的功能。

PWAs 的“可安装性”特性似乎经常被误解。它并不**而不是**意味着给一个网站添加书签，让它成为你智能手机上的一个小工具(在 iPhone 上，你可以在 Safari 浏览器中点击“添加到主屏幕”来实现这一点)。根据另一个谷歌帖子的说法，要“可安装”，你的网络应用需要包括一个网络应用清单和一个“带有功能性*获取*处理程序的服务人员”在 Android 设备上的移动浏览器中，这将启用一个弹出提示，询问您是否要将该网站添加到您的主屏幕。即便如此，不同的浏览器也有不同的要求，更复杂的是，iPhone OS 不允许弹出提示。

但当我和亚历克斯·罗素一起检查这些细节时，他告诉我，关键点在于，这个 web 应用“有一个服务人员，所以它可以离线工作，还有一个足够好的清单文件，可以很容易地从主屏幕上识别出来。”

## 领先的 PWA 示例

在 Parler 的争议之后，我从一个随机的 YouTuber 上看了一个视频，该视频旨在解释如何将 Parler 安装为 PWA。但它显示的只是“添加到主屏幕”功能。所以根据这个标记，我的猜测是帕勒实际上是一个 PWA。考虑到它甚至不能保证其用户数据的安全，这并不奇怪。

Twitter 是一家肯定会提供 PWA 版本的公司。它在 2017 年以“Twitter Lite”[的名字首次浮出水面；很明显，即使是在那个时候，它也比一个基本的移动网站提供了更多的功能。一个](https://blog.twitter.com/en_us/topics/product/2017/introducing-twitter-lite.html)[谷歌开发者的故事](https://developers.google.com/web/showcase/2017/twitter)当时提到 Twitter Lite 实际上是一个非常轻的应用:“PWA 只有 600KB，而安装原生 Android 应用需要 23.5MB 的下载数据。”它还指出，网页推送通知和“几乎即时加载服务人员脚本”是该应用程序的另外两个功能。

多年来，Twitter 一直在不断迭代其 PWA，使其越来越接近其原生应用的功能。例如，Twitter 工程师 Charlie Croom [在 2019 年 7 月发布了](https://blog.twitter.com/engineering/en_us/topics/infrastructure/2019/user-centric-web-push-aggregation.html)关于 Twitter 如何将 nuance 添加到其 PWA 推送通知中。Croom 解释说，通过使用服务人员参数 *silent* 、 *renotify* 和 *tag* ，Twitter 能够“对我们如何以及何时提醒用户进行大量控制。”

同样值得指出的是，PWA 不仅仅在移动环境中有用。一些 Mac 用户更喜欢 PWA 版本的 Twitter [而不是其官方 Mac 应用](https://www.idownloadblog.com/2019/12/05/install-twitter-progressive-web-app-mac/)。为此，在你的浏览器中进入 Twitter.com(必须是基于 Chromium 的浏览器，比如 Chrome、Edge 或 Brave)，在地址栏的右侧，你会看到一个小圆圈图标，里面有一个加号。点按它会将 Twitter 的 PWA 版本添加到您的应用程序文件夹中(并将其放入您的 dock 中)。

## 结论

帕勒是 PWA 吗？大概不会。但是我很高兴地告诉大家，Twitter 确实是进步的，至少从网络技术的角度来看是这样的。其他方面是否进步，由你自己决定。

最后一点:要检查一个(仍在运行的)网站是否是 PWA，你可以使用 Google 开发的开源 [Lighthouse](https://developers.google.com/web/ilt/pwa/lighthouse-pwa-analysis-tool) 工具。

图片来源:Pixabay

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>