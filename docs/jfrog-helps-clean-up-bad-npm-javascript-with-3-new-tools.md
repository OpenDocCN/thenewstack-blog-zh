# JFrog 用 3 个新工具帮助清理坏的 npm JavaScript

> 原文：<https://thenewstack.io/jfrog-helps-clean-up-bad-npm-javascript-with-3-new-tools/>

当微软收购拥有超过 130 万个软件包和 750 亿次下载的 JavaScript Node package manager(npm)公司 npm 时，我希望 NPM 的一些臭名昭著的不稳定版本最终会得到修复。我的希望落空了。例如，[最近的 npm 库](https://www.zdnet.com/article/when-open-source-developers-go-bad/)[【colors . js】](https://www.npmjs.com/package/colors)和[【faker . js】](https://github.com/faker-js/faker)[mess](https://www.zdnet.com/article/when-open-source-developers-go-bad/)显示，从 2016 年臭名昭著的[【左垫 NPM】](https://www.theregister.com/2016/03/23/npm_left_pad_chaos/)插曲来看，我们并没有改善多少。在这三个案例中，成千上万的国家预防机制项目化为乌有。

因此，使用 DevOps 原则来保护软件供应链的公司 [JFrog](https://jfrog.com/) 发布了三个新的开源程序来检测和阻止恶意 npm 包的安装，这是一件好事。

## 保护供应链

这些是对颜色和 faker 惨败的直接回应。在那一次，他们的维护者故意破坏了包。JFrog 和许多其他公司一样，越来越关注开源软件供应链的安全性。

在 npm 生态系统中，新代码经常从存储库中取出，在项目中使用，并在没有检查问题的情况下投入生产。事实上，很多时候，开发人员可能甚至没有意识到其中一个组件已经被更改，更不用说被破坏了。我们再也不能盲目信任公共存储库中的开源代码了。

发生这种情况是因为，正如 JFrog 的高级技术和安全研究主管所写的那样，Ilya Khivrich 写道:

*[在项目中强制使用特定版本的 npm 依赖项的常用方法是使用 package-lock.json 文件](https://jfrog.com/blog/mind-your-dependencies-defending-against-malicious-npm-packages/)，它指定了允许的库版本。我们强烈建议使用 package-lock.json 并尽可能指定精确的依赖版本。然而，一个鲜为人知的事实是，当前的 npm 安装程序在全局安装软件包(npm 使用-g 或 global 运行)时，不支持 package-lock.json 文件，而是会根据 package.json 文件中指定的依赖项，很乐意下载任何软件包依赖项的最新可用版本。这就是为什么[用户发现他们的应用程序使用了被劫持版本的颜色包](https://twitter.com/_rsc/status/1480610521418289155)，即使他们确信他们受到 package-lock.json 的“保护”*

这需要修补，而且现在就需要修补。但这是 npm 及其开发者的问题，而不是 JFrog 的问题。

## 修复

同时，为了帮助处理这个基本的软件供应安全问题， [JFrog 在](https://github.com/jfrog/jfrog-npm-tools) [GitHub](https://github.com/) 上提供了三个新的开源 npm 安全工具。这些方案是:

*   **package_checker:** 一个工具，提供一个给定包的特定版本是否可信的指示。该工具寻找供应链攻击中使用的软件包的泄露迹象，并可用于识别新发布版本的潜在风险。检查的条件包括 1。)版本号的显著差异(即从 5.5.3 跳到 6.6.6，就像 faker npm 包的情况一样)2。)对未维护包的新更新；npm 中出现的版本与其链接的 GitHub 库之间的差异；以及该版本是最近发布的，因为一个非常新的版本还没有经过审查，并且可能包含恶意代码。
*   **NPM-secure-installer:**NPM 安装的安全包装器，它将拒绝全局安装不包含 [npm-shrinkwrap](https://docs.npmjs.com/cli/v8/configuring-npm/npm-shrinkwrap-json) 锁文件的软件包。
*   **package _ issues _ history:**一个实验性工具，旨在监控有问题的包更新，以便在发现某个包版本引入了重大更改之前找到它们。

Khivrich 补充说，有了这些工具，您将能够更好地“通过在使用前验证每个新软件包版本的安全性和健壮性，保持良好的网络卫生，此时专门针对 npm 软件包库。”

这不会解决坏的 npm 文件的问题，但这是一个很大的进步。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>