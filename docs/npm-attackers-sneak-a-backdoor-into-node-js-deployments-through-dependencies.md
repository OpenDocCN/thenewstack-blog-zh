# Npm 攻击者通过依赖关系在 Node.js 部署中隐藏一个后门

> 原文：<https://thenewstack.io/npm-attackers-sneak-a-backdoor-into-node-js-deployments-through-dependencies/>

JavaScript 代码的 npm registry 的维护者最近发现了一种似乎是利用 Node.js 模块的嵌套依赖模型的软件供应链攻击。

在得到开发社区成员的通知后，npm 安全团队最近开始调查三个可疑的包，其中一个被证明包含一个用户不知道的后门或秘密入口。这些模块名为 **getcookies** 、 **express-cookies** 和 **http-fetch-cookies** ，由同一用户上传。

**getcookies** 包包含恶意代码，允许远程用户通过隐藏在 HTTP 请求头中的命令在服务器上执行任意代码。另外两个包是诱饵，它们的目的是让发现 getcookies 变得更加困难。

后门模块被列为 **express-cookies** 的依赖项，而后者本身被列为 **http-fetch-cookies** 的依赖项。调查还显示，几周前，一个名为 **mailparser** 的现有包开始将 **http-fetch-cookies** 列为依赖项，完成了恶意链。

npm 安全团队在的一篇博客文章[中说:“尽管被弃用， **mailparser** 每周仍有大约 64000 次下载。”。“我们研究了该模块的用户可能会受到的影响。我们确定依赖于 **http-fetch-cookies** 的 **mailparser** 的发布版本没有以任何方式使用该模块，消除了后门带来的任何风险。我们推测 **mailparser** 要求 **http-fetch-cookies** 是为了在未来执行攻击或者增加 express-cookies 的下载数量以增加其合法性。"](https://blog.npmjs.org/post/173526807575/reported-malicious-module-getcookies)

但是，虽然使用 **mailparser** 的应用程序没有受到影响，但是那些直接引入其他三个模块的应用程序可能已经受到威胁。

这些模块以及三个版本的**邮件解析器**——2 . 2 . 3、2.2.2 和 2 . 2 . 1——将 **http-fetch-cookies** 列为依赖项，已经从 npm 注册表中取消发布。目前还不清楚 rogue 依赖项最初是如何被添加到 **mailparser** 中的，它已不再被维护，但仍被列为 213 个其他模块的依赖项。

研究人员在过去警告说[大量的模块维护人员使用弱密码](https://thenewstack.io/npm-password-resets-show-developers-need-better-security-practices/)，但是 npm 维护人员[已经采取了几项措施](https://thenewstack.io/forthcoming-npm-update-add-two-factor-authentication/)来解决这个问题。也就是说，开发人员可以通过许多方式让他们的计算机感染恶意软件，任何这种妥协都为攻击者提供了后门合法代码和发起软件供应链攻击的机会。

这不是第一次在 npm 注册表或其他编程语言的流行[包库中发现恶意包](https://thenewstack.io/python-package-repository-struggles-deal-typosquatting/)[，但大多数攻击都使用了域名仿冒——发布名称与流行包非常相似的流氓包。](https://thenewstack.io/npm-cleans-typosquatting-malware/)

然而，这一事件是经过深思熟虑的，它滥用了依赖系统，使后门程序包看起来更合法，并使用户更难检测到它。它强调了开发人员仔细检查他们在应用程序中使用的模块并维护软件材料清单的重要性，以便他们可以在任何组件受到损害时快速评估损害。

通过 Pixabay 的特征图像。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>