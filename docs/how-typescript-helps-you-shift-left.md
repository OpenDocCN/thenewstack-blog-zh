# TypeScript 如何帮助您向左移动

> 原文：<https://thenewstack.io/how-typescript-helps-you-shift-left/>

[](https://www.linkedin.com/in/charlottemfreeman/)

 [夏洛特·弗里曼

夏洛特从事科技和安全方面的写作已经超过 20 年。她目前是 Synopsys 软件完整性小组的高级安全作家。](https://www.linkedin.com/in/charlottemfreeman/) [](https://www.linkedin.com/in/charlottemfreeman/)

我们都知道我们[应该将安全性转移到左边](https://www.synopsys.com/blogs/software-security/new-devsecops-study-highlights-need-address-appsec-throughout-sdlc/)并在软件开发生命周期的早期修复 bug(SLDC)，但是我们如何去做呢？一种方法是使用允许开发人员在提交代码之前发现并修复代码问题的工具。对于使用 JavaScript 的开发人员来说，TypeScript 就是这样一种工具。

TypeScript 是微软开发的一种开源编程语言，可以编译成 JavaScript。发布于 2012 年，现在是 GitHub 上第四大使用语言。虽然 TypeScript 和 JavaScript 是两种独立的编程语言，但 TypeScript 是 JavaScript 的超集。这意味着所有有效的 JavaScript 代码也是有效的 TypeScript 代码。开发 TypeScript 是为了使构建企业级 web 应用程序更容易、更安全。

## 为什么 TypeScript 比 JavaScript 更安全？

TypeScript 既是强类型语言，也是静态类型语言。强类型语言需要显式声明来在类型之间进行转换或比较。强类型语言比弱类型语言更安全，因为它们需要一个额外的步骤来在语言之间进行转换。这意味着，例如，他们不允许你将一个字符转换成一个数字，这可以帮助防止类似 [CWE-704 不正确的类型转换或转换](https://cwe.mitre.org/data/definitions/704.html)这样的错误。

TypeScript 也是一种静态类型语言，这意味着它在编译时检查类型。像 JavaScript 这样的动态类型语言在运行时检查类型。将这些检查转移到编译阶段意味着 TypeScript 可以在类型错误传播到程序之前找到它们，从而防止可利用的漏洞到达生产应用程序。

## 为什么左移很重要？

当我们从每个业务都是软件业务的想法开始时，很明显软件风险就是业务风险。这就是为什么从一开始就必须在你的软件中建立信任。在开发过程中更早地移动安全性，并在开发过程中构建安全性检查("[左移](https://www.synopsys.com/blogs/software-security/shift-left-application-security-tools/)")认识到了安全性的重要性，并让更多的人对其实现负责。

向左移动意味着开发人员需要意识到他们代码的安全含义，而不是将这一责任外包给单独的安全团队。安全团队仍将执行启动前审查和所需的任何补救措施，但如果从一开始就考虑到了安全性，则该过程耗时会少得多。

## 帮助您建立对软件信任的解决方案

通过在开发过程的早期实施更安全的编码，将 TypeScript 添加到开发过程中可以增加您在软件中建立的信任。然而，像任何工具一样，如果使用不当，TypeScript 可能会有安全问题。这就是为什么将支持安全优化语言的应用程序安全测试工具添加到您的工具箱中是至关重要的。

虽然 TypeScript 可以提高开发流程的安全性，但添加像 Synopsys Coverity 这样的[测试工具可以将安全性转移到 SDLC 中，并支持开发人员的工作流和时间表。通过添加开发人员*希望*使用的工具，你可以确信你对你的安全态势产生了真实、切实的影响。](https://www.synopsys.com/software-integrity/security-testing/static-analysis-sast.html?)

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>