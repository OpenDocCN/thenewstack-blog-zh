# Angular 5 让开发者为现代网络做好准备

> 原文：<https://thenewstack.io/angular-goes-2-five/>

如果说有一件关于 [Angular](http://angular.io) 团队的事情是真实的，那就是他们一直致力于一个在 JavaScript 世界中不常见到的愿景。这个愿景是在单个应用程序或 JavaScript 应用程序聚合上协作的大型团队之一。为了帮助实现这一点，Angular 2 做出了突破性的改变，采用了 TypeScript，这是微软创建的 JavaScript 的类型化版本。

在语言层面向 JavaScript 添加类型意味着 Angular 应用程序总体上更容易在大型团队中开发和维护。这仍然意味着 Angular 2 与 Angular 1 完全不同，所以上周，Angular 团队发布了 [Angular 2 版本 5.0.0](https://blog.angular.io/version-5-0-0-of-angular-now-available-37e414935ced) 。

这个版本被简单地称为 Angular 5.0，它建立在以前版本的众多变化之上。 [Stephen Fluin](https://twitter.com/stephenfluin) ，谷歌[Angular 团队的开发者顾问，他的任务是帮助开发者更高效地使用 Angular。自然，他对最新版本的变化了如指掌。](https://cloud.google.com/kubernetes-engine)

其中一个变化是将包含的 HTTP 客户端升级到今年早些时候推出的新实现。随着 Angular 5.0 的发布，该团队认为这是默认的新客户端，并建议用户迁移到新的实现。

“我们以前有一个 HTTP 客户端，”Fluin 说，“但我们想做一些 API 的改变，这将是突破性的改变。开发团队根据框架设计者在现场观察到的情况重新构建了客户端。以前，软件将如何从消息中提取 JSON 有效负载的任务留给了开发人员。”“现在它是自动的，”弗卢因说。它更简单、更小，我们减少了您需要添加到应用程序的文件大小。我们让它变得更加强大；我们可以使用像泛型这样的东西，你可以输入从服务器返回的东西，或者做拦截器来修改和拦截所有输出的东西。

Fluin 说，这有助于保持服务器响应的一致性，并且更容易使用。“当我进行 HTTP **get** 调用时，我可以说，‘嘿，我知道我要从服务器上获取什么。它看起来像这样，有这样的结构，这样的数组，这些是数字，这些是字符串……“我可以给它一个类的接口，TypeScript 会认为我正在获取那个类的数据，”Fluin 说。

Fluin 说，Angular 的命令行界面已经随着平台本身的成熟而成熟。“当我们发布 CLI 时，我们希望帮助不想自己动手的开发人员入门。这已经成为人们开始锻炼棱角的主要方式。

该团队改进 CLI 的方法之一是将其分解为自己的项目，称为 [Angular Development Kit](https://github.com/angular/devkit) 。“我们发布的第一版 CLI 在一个代码库中包含了它能做的一切，从搭建新项目到用新内容修改项目，再到构建和部署生产捆绑包。我们有大量的企业，他们需要调整一件事情或者定制构建到他们的工具中。我们已经开始利用 CLI 中的智慧，并将其提取到可单独使用的包中。大多数人都可以使用 CLI，但工具供应商现在只能使用其中的一部分。

## 谷歌之路

Fluin 说 Angular 平台的未来可能会包括一些谷歌内部工具，尽管他指出这仍处于考虑阶段。Fluin 说:“我们希望充分利用谷歌开发人员的优势，并让公众能够利用这一优势。”

具体来说，他说 Angular 团队希望将谷歌构建软件的方式带给大众。这将以某种方式复制 Angular、[、Bazel](https://www.bazel.build/) 和 [Closure](https://developers.google.com/closure/) 。Bazel 是 Google 流行的内部构建系统，可以快速输出到多个构建目标。Closure 是 Google 的 JavaScript 编译器，已经在 Google 工作了 10 年。所述封闭甚至可以实现单级树摇动。

这与 Angular 5.0.0 中默认打开的[构建优化器](https://www.angulararchitects.io/aktuelles/shrinking-angular-bundles-with-the-angular-build-optimizer/)相吻合。Fluin [在一篇博客文章](https://blog.angular.io/version-5-0-0-of-angular-now-available-37e414935ced)中写道:“构建优化器是我们 CLI 中的一个工具，它使用我们对 Angular 应用程序的语义理解来使您的包变得更小。

所有这些将有助于使 Angular 整体更加模块化。Fluin 说，最终目标是实现 Angular Elements，一个可以将单个角度组件与应用程序一起导出的系统。这将允许根本不使用角度的开发人员通过复制和粘贴所需的代码将角度功能嵌入到 JavaScript 应用程序中，而不是必须将整个角度分布包含到他们的应用程序中。

在这个版本的其他地方，引入了 Angular 通用状态转移 API。正如 Fluin 所写的，“Angular Universal 是一个专注于帮助开发人员执行 Angular 应用程序的服务器端渲染(SSR)的项目。通过在服务器上呈现您的 Angular 应用程序，然后在生成的 HTML 之上进行引导，您可以添加对不支持 JavaScript 的抓取器和爬行器的支持，并且您可以提高您的应用程序的感知性能。”

Fluin 表示，Angular 1 的最初愿景今天仍然存在，是团队的核心动力。“如果你回顾 2009 年，Angular 真的试图设计一种发展方式。如果我们能重新设计当时浏览器的工作方式，这就是我们希望应用程序开发的样子，”Fluin 说。

“我们正在推进这项工作。我们实际上是一个比以前更简单的框架。比以前简单了。我们更加依赖现代网络，”Fluin 说。他补充道，自 Angular 创立以来，变化最大的就是网络和浏览器。

“我认为大概在 2.5 到 3 年前，现代网络开始出现。我们开始拥有打字系统、构建系统和所有的中间步骤，这使得开发变得更难，但是更好。通过拥抱这些并在它们的基础上进行构建，我们真的让很多开发者受益匪浅，”Fluin 说。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>