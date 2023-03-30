# Jamstack 面板:边缘将如何改变开发

> 原文：<https://thenewstack.io/jamstack-panel-how-the-edge-will-change-development/>

一个小组在本周的 Jamstack 会议上告诉观众，JavaScript 开发者现在应该尝试将代码发送到边缘。

直到最近，Sunil Pai 一直在 Cloudflare 担任高级系统工程师，他建议开发者在本季度内将他们网站的一部分放在 edge 上。

“我们目前正在研究剩下的部分。有很多工作要做，但你今天应该充分利用它，”派在周二的会议上对观众说，他现在是为边缘应用程序开发开发工具的[酷电脑俱乐部](https://www.coolcomputerclub.com/)的创始人。“这需要时间来适应，特别是当涉及到 NPM 剧本的时候，”Pai 说。

“事实证明，现在 NPM 上的许多软件包在这些新的 edge 运行时上并不能真正工作，”他说。“感觉现在有一个阶段，我们将为生产用途充实生态系统。没有人想使用有人在 GitHub 上发布的周末项目。它必须经受生产的考验，才能做好战斗准备。”

有些已经走到了边缘。 [Netlify](https://www.netlify.com/) 联合创始人兼首席执行官 [Matt Biilmann](https://www.linkedin.com/in/mathias-biilmann-christensen-a5a3805/) 表示，这家基于云的开发公司最近的边缘用例月环比增长约为三倍。

## 运行时的新可能性

[open sauce](https://www.linkedin.com/in/brianldouglas/)的创始人兼首席执行官 Brian Douglas 问小组成员，现在开发人员可以在新的运行时基础上开发什么可能性。Pai 说，这种可访问性将使普通开发者能够构建雄心勃勃的、全球规模的应用程序。

“我喜欢零对一对多的系统。我不想投入大量的金钱或时间，我只想写点东西，然后迅速发布出去，让人们看到，”Pai 说。“因此，能够有效地免费做这件事与 15 年前的 JavaScript 场景有很大的不同，那时我必须从我叔叔那里获得一张美国信用卡。”

Biilmann 补充说，构建在具有强大安全保证的隔离(如 [Deno](https://deno.land/) )之上的运行时，以及围绕 [WebAssembly](https://thenewstack.io/whats-stopping-webassembly-from-widespread-adoption/) 构建的运行时，在为不同开发人员解锁的可能性方面是相似的。他说，这些运行时将允许系统更加灵活，并支持围绕缩放、并发性和在哪里运行代码的更明智的决策。

“我们将看到的一些可能性是，既在非常接近最终用户的地方运行代码，又在非常接近我们的数据的地方运行相同类型的代码，”Biilmann 说。“所以我也期待看到有趣的工具集成，比如将 Deno 集成到数据库等等，因为这两种途径都非常有趣。我们能否让代码运行得非常接近边缘，但我们能否有时也翻转脚本，将代码发送到数据所在的位置，然后获得更简单的结果，而不是进行多次往返，等等。”

JavaScript 的核心隔离层——或者更通用编程语言的[web assembly](https://thenewstack.io/webassembly-users-a-mix-of-backend-and-full-stack-developers/)——将允许开发人员构建架构，随着时间的推移，他们可以更多地考虑代码实际应该在哪里运行。他补充说，当核心抽象是一个长期运行的应用服务器时，它还将使代码运输变得容易，而开发人员不能这样做。

## 更好、更便宜、更快

[Deno](https://thenewstack.io/with-additional-funding-deno-sets-out-to-challenge-node-js/) 创始人兼首席执行官 [Node.js](https://thenewstack.io/linux-manage-multiple-versions-of-node-js-with-the-nvm-manager/) 创始人 [Ryan Dahl](https://thenewstack.io/denos-ryan-dahl-is-an-asynchronous-guy/) 说，在不久的将来，开发者可以利用的这些优化将使它更好、更便宜、更快。

Dahl 说:“与传统的 AWS Lambda 解决方案相比，这实质上是一个数量级的成本改进，例如，对于无服务器的解决方案。”

他还提到了 SSR——采用 [React](https://thenewstack.io/typescript-vs-react-js/) 代码【或】 [JSX](https://reactjs.org/docs/introducing-jsx.html) 风格的代码，在服务器端运行，并使用服务器端 JavaScript 运行时(如 Deno deployment)呈现 HTML，他说。

Dahl 说:“你可以获取 React 代码并在服务器端运行，实际上生成静态 HTML 并发送给你的用户，但这样做不是提前构建，而是在第一次请求时及时完成。”

## 对未来的预测

该小组提供了关于边缘将如何改变发展的未来预测。Dahl 说，更多的网络框架将会以 edge 用例为目标。

“回到状态，就像要么让运行时接近状态，……要么让数据接近运行时本身，这也是将要解决的一件重要事情，”Dahl 说。"在这些边缘运行时，我们将看到更多关于如何管理状态的迭代."

比尔曼预测，公司将构建自己的 API，使其在开箱即用的边缘上运行，以确保 API 能够在全球范围内快速响应，以及围绕如何进行缓存的新模式。

Pai 认为，人们将更加关注流媒体技术和模式。

Pai 说:“有一些技术已经存在很多年了，那就是流式响应，但是没有人真正知道如何使用它。”。“现在，框架为你提供了这种抽象，事实证明，edge 运行时是一种很好的方式。因此，React 应用程序现在启动速度更快，因为它们可以在开始呈现页面的其余部分之前发送几个字节和您的 head 标签。API 和网页的流模式似乎是一个需要关注的问题。”

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>