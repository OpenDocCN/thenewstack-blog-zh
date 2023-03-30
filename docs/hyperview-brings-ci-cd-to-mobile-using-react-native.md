# Hyperview 使用 React Native 将 CI/CD 引入移动设备

> 原文：<https://thenewstack.io/hyperview-brings-ci-cd-to-mobile-using-react-native/>

当 [Instawork](https://www.instawork.com/) 工程总监[亚当·斯特平斯基](https://www.linkedin.com/in/adam-stepinski-214043b/)于 2017 年加入该公司时，那里的团队正在使用 [React Native](https://reactnative.dev/) 为 Android 和 iOS 构建跨平台应用。在质量保证和应用商店审查过程之间，他们最快的迭代是每周发布一次。然而，在 web 端，变化可以立即推送给用户，允许更敏捷的开发方法。

"我们能做些什么来打破这种周而复始的循环？"斯特平斯基在接受《新书库》采访时回忆了自己的思考过程，问道。“我们能在移动设备上获得与在网络上相同的体验吗？在网络上，我们基本上是从后端定义和控制界面，只要我们部署后端，用户就能从新的用户界面中受益。”

他开始四处寻找解决办法。发现没有一个符合他的需求，他开始构建现在的[Hyperview](https://hyperview.org/)——这是一个开源项目，提供了一个瘦 React 原生客户端，用于使用[超媒体](https://en.wikipedia.org/wiki/Hypermedia)方法开发服务器驱动的移动应用。Stepinski 说，他的灵感部分来自于[intercooler . js](https://intercoolerjs.org/)——现在被称为[htmx](https://htmx.org/)——通过调整为移动设备而不是网络提供服务器驱动的用户界面的方法。

虽然其他公司经常通过提供 Webview 的包装来解决这个问题，在网络和移动设备上使用相同的内容，但 Stepinski 说他不想使用这种方法。

“使用网络技术和 WebKit 构建的体验与移动应用平台目前为您提供的体验相比，仍有差距，”Stepinski 说。“流畅的导航，能够深度链接到应用程序的不同部分，以一种非常流畅的方式整合视频和照片等内容——即使是渐进式的，你也总能看出你使用的是 web 应用程序还是原生应用程序体验。我们的目标是实现本地应用体验。”

Hyperview 通过使用瘦客户端获取 [Hyperview XML (HXML)](https://hyperview.org/docs/guide_html) 来实现这一点，这是一种基于 XML 的格式，用于描述支持标题、滚动视图、列表和文本字段等元素的原生移动 ui；以及触摸、手势和输入交互等用户交互的样式和行为语法——所有这些都不需要脚本。

Stepinski 说，通过使用这种方法，开发者可以在后台使用他们喜欢的任何语言。虽然 Instawork 使用 Django，但任何后端语言——如 Node.js 或 Ruby on Rails——都可以用于逻辑层，这也允许在移动和 web 之间重用业务逻辑。

“正如我们认为包装 WebView 不是一个很好的移动体验一样，我认为包装移动体验对于桌面和浏览器来说也不是很好，”Stepinski 说。“但事实上，我们所有的逻辑都包含在后端，这意味着我们可以共享相同的后端逻辑，然后或者使用模板呈现为 HTML，或者使用相同的逻辑呈现为 Hyperview XML。”

该项目的[描述](https://github.com/Instawork/hyperview)宣称，有了 Hyperview，“真正的 CI/CD 最终可用于移动开发。”Stepinski 补充说，通过将所有这些逻辑转移到后端，“你只需遵循与你在网上相同的 [CI/CD 流程](https://thenewstack.io/category/ci-cd/)

Hyperview 还为开发人员提供了另一个好处，通过保持应用程序的大小-因为许多可能会使移动应用程序膨胀的逻辑都保留在后端。使用旧移动设备的用户不必担心你的应用程序占用太多空间——step inski 指出，Instawork 应用程序属于 30MB 以下的类别——即使增加了功能，应用程序的大小也可以保持不变。

目前，Hyperview 为 Instawork 应用程序提供了动力，其他公司也在使用它，但 Stepinski 表示，在他们正式宣布 1.0 版之前，他们还有一些事情要做。

他说:“我们在 2022 年有一些目标，要推出正式的 1.0 版，在那里我们对它进行清理，并提供我们认为任何人都需要的所有核心功能，以便能够使用 Hyperview 构建移动应用。”“作为其中的一部分，我个人正在努力改进我们的表单和用户输入与实时[验证](https://github.com/Instawork/hyperview/issues/305)的配合。”

除此之外，Stepinski 还指出 Hyperview 是可扩展的——这一点目前还没有正式提到。他说，Instawork 本身已经开发了 20 或 30 个组件，这些组件不属于开源项目，但有可能作为扩展库的一部分提供。

虽然 Hyperview 可能没有 1.0 版本的标签，但该项目本身拥有自己的变革方式:“Hyperview 完全改变了我们在 Instawork 的工作方式。开发人员工作效率的提高使我们能够更快地发布新功能，提高我们应用的性能，并最大限度地减少移动和 web 开发之间的上下文切换。对于快速变化的网络移动应用程序，Hyperview 提供了一套无与伦比的折衷方案，”[项目介绍](https://hyperview.org/docs/guide_introduction)中说道。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>