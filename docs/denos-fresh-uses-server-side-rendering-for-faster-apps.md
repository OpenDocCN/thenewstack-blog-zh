# Deno 的 Fresh 为更快的应用程序使用服务器端渲染

> 原文：<https://thenewstack.io/denos-fresh-uses-server-side-rendering-for-faster-apps/>

上周晚些时候，Deno 软件工程师 [Luca Casonato](https://www.linkedin.com/in/luca-casonato-15946b156/) 正在为周二[的正式发布](https://deno.com/blog/fresh-is-stable)Fresh 完成文档，这是 Deno 的一个新的全栈网络框架。他停下来分享他最新项目的细节。

“Fresh 是一种新风格的 web 框架，是为 Deno 而不是 NodeJS 编写的，”创建了 [Fresh](https://fresh.deno.dev/) 的 Casonato 告诉 New Stack。“它确实针对边缘计算进行了优化。”

他将它与 [Node.js](https://thenewstack.io/node-js-readable-streams-explained/) 或 [Vercel](https://thenewstack.io/vercel-and-svelte-a-perfect-match-for-web-developers/) 进行了比较，他说后者可能拥有[无服务器功能](https://thenewstack.io/rust-and-webassembly-serverless-functions-in-vercel/)，可以在一个地区的亚马逊网络服务上运行。卡索纳托说，从美国向服务器发出请求，如果主机在欧盟，那么这个请求就必须跨越大洋。相反，Fresh 利用边缘计算，将请求路由到离用户最近的服务器，他补充道。

## 又一个 JS 框架？

但是为什么在一个已经拥挤不堪并且可能没有必要的框架领域中出现另一个 JavaScript 框架呢？Casonato 说，首先，大多数框架都存在速度问题。其次，还有用户或开发者体验。

“他们都不够快，或者他们没有足够好的用户体验或足够好的开发者体验，”卡索纳托说。“对于 Fresh，我们尝试查看所有框架，查看它们能正确完成的所有事情，以及它们不能正确完成的所有事情。”

他认为，这个组合是一个比现有框架更好的框架，缺点更少。

他说:“这个框架实际上是为服务器端渲染而构建的，所以它向客户端发送很少的 JavaScript 和代码，并尽可能多地保留在服务器上，为用户提供非常快捷的体验。”。

公告称，大部分渲染都是在服务器上完成的，所以客户端“只负责重新渲染互动的小岛”。卡索纳托声称，这将转化为全世界的出色性能，即使是在慢速设备上。他说，相比之下，其他向客户端发送更多代码的 JavaScript 框架在慢速设备上往往很吃力。

## 新鲜未装箱

Fresh 基于 [Deno](https://deno.land/) 和 [Preact](https://preactjs.com/) ，这是一个 JavaScript 库，它将自己宣传为 Meta 的 [React](https://opensource.fb.com/projects/react/) 的替代品，后者是一个基于 UI 组件构建用户界面的 JavaScript 库。

根据文档，Fresh 结合了路由框架和模板引擎，在服务器上按需呈现页面。Fresh 还提供了一个界面，用于在客户端呈现一些组件，以实现最大的交互性。该框架使用 Preact 和 [JSX](https://reactjs.org/docs/introducing-jsx.html) 在服务器和客户端进行渲染和模板化。

它是为部署在 [Deno 上而构建的，Deno 是 JavaScript、TypeScript 和 WebAssembly](https://thenewstack.io/netlify-ceo-on-why-netlify-edge-functions-was-built-on-deno/) 的运行时——所以 Fresh 的唯一安装要求是下载 Deno 1.22.3 或更高版本。

根据文档，Fresh 支持现成的 TypeScript，并且不需要任何配置。然而，也许它更引人注目的特性之一是它没有构建步骤。Casonato 指出，构建步骤可能需要 10 分钟才能完成。

“使用 Fresh，这不需要几分钟——它是即时的，没有构建步骤，”他说。“因此，您可以将自己编写的源代码立即部署到您的所有服务器上，而无需在中间进行转换，这确实可以加快开发速度。”

它确实需要额外的一组将 TypeScript 代码转换为 Javascript 的代码，以便在本身不执行 TypeScript 的浏览器上执行 TypeScript。卡索纳托解释说，这需要几毫秒的时间。

“有一些努力正在进行中，最终将允许浏览器执行某种形式的类型脚本，但还没有完全实现，所以我们现在必须做的是在我们向浏览器提供 JavaScript 之前，获取类型脚本代码并去除所有类型，”他说。“当用户请求某种资源，而浏览器本身无法处理该资源类型时，我们必须即时转换它。”

卡索纳托预见 Fresh 的主要竞争对手是 [Astro](https://thenewstack.io/astro-revs-up-static-sites-with-partial-hydration/) 、 [Remix](https://remix.run/) 和 [Next.js](https://thenewstack.io/from-php-to-next-js-what-trivago-learned-rewriting-its-web-app/) 。

Deno 公司上周宣布，它在由红杉资本(Sequoia Capital)牵头的一轮投资中筹集了 2100 万美元。根据 Crunchbase 的消息，到目前为止，它已经在两轮融资中筹集了 2590 万美元。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>