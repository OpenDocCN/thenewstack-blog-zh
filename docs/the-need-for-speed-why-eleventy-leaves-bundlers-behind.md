# 速度的需要:为什么 Eleventy 把 Bundlers 甩在后面

> 原文：<https://thenewstack.io/the-need-for-speed-why-eleventy-leaves-bundlers-behind/>

Eleventy 是一个为速度而建的静态网站生成器，它能够提供的原因是它留下了一个捆绑器，Eleventy 的创作者扎克·莱瑟曼在接受新堆栈采访时说。

“在许多方面，[eleven](https://github.com/11ty/eleventy)比我们在同一领域的许多竞争对手快得多的真正原因是，我们没有使用捆扎机，”莱泽曼告诉 New Stack。"我们并不严格地与捆绑器紧密耦合."

## 莱泽曼起诉邦德勒的案子

他补充说，很多站点生成器确实使用捆扎机。例如， [Next.js](https://thenewstack.io/what-developers-told-us-about-vercels-next-js-update/) 使用了 [Webpack](https://webpack.js.org/) ，但是正在转向 [Turbopack](https://turbo.build/pack) 。Vite 是另一个流行的捆绑器，Eleventy 用一个插件支持它。

“但是你做的工作越多，速度就越慢，事实就是这样，”莱瑟曼说。“我们正试图押注于后捆绑式发展阶段，这种趋势在你需要捆绑式者做什么和你不需要捆绑式者做什么之间来回波动。”

[静态网站生成器](https://thenewstack.io/get-back-basics-static-website-generators/)使用 HTML、 [CSS](https://thenewstack.io/a-hotter-pink-css-devs-get-an-explosion-of-new-colors/) 和 [JavaScript](https://thenewstack.io/jamstack-panel-multiple-javascript-frameworks-are-a-good-thing/) 来创建大型网站，自动创建页面。与 Eleventy 竞争的其他站点生成器包括 Astro、Gatsby、Next.js、Next、Remix 和 SvelteKit。

[莱泽曼已经进行了测试](https://www.zachleat.com/web/build-benchmark/#benchmark-results)，测试显示 Eleventy version 1 比大多数竞争对手跑得都快，[在 1.93 秒内构建×4000 个降价文件](https://www.11ty.dev/docs/performance/)，相比之下 [Astro](https://thenewstack.io/astro-revs-up-static-sites-with-partial-hydration/) 用了 22.90 秒， [Gatsby](https://thenewstack.io/netlify-acquires-gatsby-its-struggling-jamstack-competitor/) 用了 29.05 秒， [Next.js](https://thenewstack.io/next-js-13-debuts-a-faster-rust-based-bundler/) 用了 70.65 秒。只有[雨果](https://thenewstack.io/tutorial-use-hugo-to-generate-a-static-website/)，以 0.68 秒的成绩，击败了十一。

他解释说，随着网络标准的不断完善，对捆绑软件所支持的功能的需求会减少。一个例子:ECMA 脚本模块。几年前，许多 bundlers 正在将使用 ECMAScript 模块的代码转换成更容易访问的 JavaScript 形式。他说，但是随着网络标准的发展，浏览器的改进以及将这些东西原生地融入浏览器，捆绑软件不再需要支持这些功能。他补充说，通常，“昂贵”的功能会被打包，以处理甚至不再相关的用例。

“我的观点是，你不需要捆绑器，”他说。“对于大多数 web 开发用例来说，捆绑器是不必要的。现在，如果你想把这两个东西集成在一起，你可以用一个捆绑器。但我多年来一直在建设网站，是的，我认为在许多网站和许多用例中，bundler 带来的客户流失和性能下降是不值得的。”

Eleventy 使用 Node.js 作为其运行时，因此必须安装它才能运行 Eleventy。然后通过 [npm](https://thenewstack.io/is-npm-a-hotbed-of-malware/) 安装，npm 与 Node.js 捆绑在一起，Eleventy 通过命令行运行。

“我们希望在你的编辑器中编写一个 HTML 文件的基础上更上一层楼，”莱泽曼说。" Eleventy 将允许你自动完成建立网站的一些工作."

例如，Eleventy 将以脚本方式重复页眉或页脚，这样开发人员就不必复制和粘贴代码。

Eleventy 由 Netlify 赞助，但归 Leatherman 所有。2.0 版本于 2 月 8 日正式发布；它只包括测试版的一些更新，因为莱泽曼在过去的一年里已经在使用该软件的[金丝雀版本](https://thenewstack.io/primer-blue-green-deployments-and-canary-releases/)。

“我已经在生产中使用它很长时间了，并在预发布中进行工作，金丝雀版本真的允许我在生产网站上进行实时迭代，”他说。“人们喜欢 Eleventy 的一点是它非常稳定。许多回到使用旧版本 Eleventy 升级到 Eleventy 2.0 的项目的人都说，这是一个非常无缝的升级，他们没有大量的开发需要进入升级过程。

“稳定性是一种很难推销的东西，但我们作为一个五六年前的项目，并在这五六年里真正为人们提供价值的记录本身就说明了这一点，”他补充道。

## 新的开发服务器和 Web 组件

已经发布的一个更新是一个新的开发服务器。

莱泽曼说:“这让我们摆脱了大量的依赖负担，相当于人们在电脑上安装了 11 个设备。”。“因此，安装 Eleventy 时，它要轻便得多。我觉得你现在装的是 34 兆左右而不是 150 兆。”

另一个让 Leatherman 兴奋的更新是新的 WebC 文件格式，它代表“web 组件”[包括许多好处](https://www.11ty.dev/docs/languages/webc/#why-use-webc)，包括对边缘流媒体的支持。

“JavaScript 生态系统已经深入第三方或独立组件框架。所以你的反应，你的角度，这些都是独立于平台和网络标准而存在的东西，”他说。“它们存在于上一层，在 web 组件和 web 标准人员以及框架库人员之间存在很大的矛盾。当组件框架成为平台的一部分和 web 标准的一部分时，这两个团队在组件框架应该是什么样子的问题上存在相当大的分歧。”

他解释说，WebC 正试图在这两个世界之间架起一座桥梁。

“我们可以从平台中获得尽可能多的长期利益，而不会遇到我们今天在许多 JavaScript 框架中看到的相同的流失问题或沉重的 JavaScript 问题，”他说。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>