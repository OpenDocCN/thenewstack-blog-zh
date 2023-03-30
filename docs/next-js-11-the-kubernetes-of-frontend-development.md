# Next.js 11:前端开发的“Kubernetes”

> 原文：<https://thenewstack.io/next-js-11-the-kubernetes-of-frontend-development/>

流行的 [Next.js](https://nextjs.org/) [React](https://reactjs.org/) 和 [JavaScript](https://en.wikipedia.org/wiki/JavaScript) 框架的创建者 Vercel ，最近推出了 Next.js 11，这是该框架的最新版本，具有加速性能和开发人员协作的新功能。

Vercel 首席执行官兼联合创始人、Next.js 联合创始人 Guillermo Rauch 表示，Next.js 11 的新功能为开发人员提供了更快的启动和更改、实时反馈、即时实时协作和显著的图像优化增强。

在最近的 [Next.js Conf 2021](https://nextjs.org/conf#room-bu2pg) 上，Vercel 推出了 [Next.js Live](https://nextjs.org/live) 的预览版，使 Next.js 能够完全在 web 浏览器内部运行。

“Next.js Live 是我们的系统，它使开发基本上是实时的，不仅仅是你自己的实时-就像在 10 毫秒内看到你的变化一样-也让你团队的其他人看到你在他们的屏幕上所做的变化，”Rauch 告诉 New Stack。“10 毫秒是我们内部给你做出改变的最后期限，以及你应该多快在屏幕上看到它。”

Rauch 说，这背后的主要创新是，Vercel 将整个 dev 服务器技术完全放在了 web 浏览器中，而在此之前，该技术存在于本地计算机的节点进程中。

“因此，所有用于转换前端 UI 组件的技术现在都完全被‘喂’进了网络浏览器，这给了我们开发人员性能方面的下一个里程碑，”他说。"它使前端开发多人而不是单人游戏."

此外，通过利用 [ServiceWorker](https://developer.mozilla.org/en-US/docs/Web/API/ServiceWorker) 、 [WebAssembly](https://webassembly.org/) 和 [ES Modules](https://hacks.mozilla.org/2018/03/es-modules-a-cartoon-deep-dive/) 技术，Vercel 使得在远程协作环境中在本地机器上运行 Next.js 时可能发生的一切成为可能。Next.js Live 在离线时也可以工作，并且不需要运行或操作远程虚拟机。

与此同时，谷歌 Chrome 部门的 [Aurora](https://web.dev/introducing-aurora/) 团队一直致力于推进 Next.js 的技术，并为 Next.js 和 [Next.js 脚本组件](https://nextjs.org/docs/basic-features/script)提供了[一致性。](https://nextjs.org/blog/next-11)

劳赫将[一致性](https://web.dev/conformance/)描述为一个副驾驶员，帮助开发人员保持在一定的性能范围内。

Next.js 的一致性是一个提供精心制作的解决方案和规则以支持最佳加载的系统，谷歌网络平台的技术负责人 Shubhie Panicker 在 Next.js Conf 主题演讲中说。

“作为一名开发人员，一致性意味着你不必为了加载性能和跟上不断变化的形势而记忆大量复杂的规则，”她说。“你可以把一致性想象成一个编译器，就像 TypeScript 一样——遵循规则是一种约束，但却是一种建立信心的方式，因为它确保了可预测的结果。随着功能的增加和团队规模的扩大，它使团队变得富有成效，变得必不可少。”

Panicker 说，一致性是 ESLint 规则和运行时检查和开发的结合。

“一致性是我们如何开源我们在谷歌使用的系统，”她说。“我们正处于这一旅程的早期，希望根据社区的反馈来发展这项技术。”

劳赫将一致性与 Kubernetes 进行了比较，因为两者都来自谷歌的内部项目。

“如果你在整个云原生空间的背景下看待它，以及 Kubernetes 在其中发挥的作用，有越来越多的可信案例表明 Next.js 正在成为前端空间的 Kubernetes，”他说。“在与谷歌和脸书的合作方面，它有着巨大的动力，投入了大量资源，并且在整个生态系统范围内投资进行整合和改进。”

此外，就像 Kubernetes 来自谷歌从 Borg 学到的所有经验一样，谷歌现在正在向 Next.js 这样的框架内部提供从他们的一致性系统中学到的经验，以帮助加载性能，劳赫说。

Rauch 说，Next.js 脚本组件是谷歌的另一项优化，它通过允许开发人员设置第三方脚本的加载优先级来提高加载性能。

在 Next.js Conf 主题演讲中，谷歌网络平台团队的开发者关系工程师胡赛因·吉尔德(Houssein Djirdeh )表示:“开发者经常为在应用程序中放置第三方脚本以实现最佳加载而苦恼。“有了这个新的脚本组件，开发人员只需定义策略属性，Next.js 就会优先处理。这可以极大地提高加载性能。”

新的脚本组件支持三种不同的加载策略:pre-interactive，用于在页面交互之前需要获取和执行的脚本，如安全性和身份验证；after-interactive，用于标签管理器和分析等脚本，这些脚本可以在页面交互后获取和执行；Djirdeh 说，还有 lazy-onload，用于聊天支持小部件等脚本，这些小部件可以在空闲时间等待最后加载。

“在谷歌 Chrome，我们相信我们与 Next.js 的合作是如何为加载性能设定可预测结果的一个例子，”他说。“在与浏览器的潜在解决方案角力之后，我们逐渐意识到框架是解决方案中缺失的一块……我们喜欢与伟大的框架一起工作，帮助开发人员让网络变得更快。”

Next.js 11 中的其他新特性包括字体增强自动化、图像增强等等。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>