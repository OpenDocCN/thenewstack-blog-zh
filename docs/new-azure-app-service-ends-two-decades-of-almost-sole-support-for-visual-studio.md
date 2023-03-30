# 新的 Azure 应用服务结束了 20 年来对 Visual Studio 几乎唯一的支持

> 原文：<https://thenewstack.io/new-azure-app-service-ends-two-decades-of-almost-sole-support-for-visual-studio/>

周二，微软宣布为其 Azure 平台增加一个名为 Azure App Service 的托管应用程序，旨在使移动应用程序完全通过基于云的门户网站开发和运行。这一举措可能会将基于云的应用平台进一步扩展到工作场所，并使与商业交易平台的互操作性成为网络应用的新前提。

这可能是微软二十年来支持 Visual Studio 之外的开发平台的最大胆的举动。在许多开发者看来，这可能会让 Azure 重新成为竞争对手，Salesforce 的 Heroku，亚马逊的 Elastic Beanstalk，以及越来越多托管 Pivotal 的 Cloud Foundry 的 PaaS options。

“当我们与开发这些应用的开发者交谈时，我们听到了一些事情。他们想要更简单，”微软 Azure 应用服务产品经理 Omar Kahn 谈到新的堆栈时说。“他们希望应用程序可以面向任何平台上的任何设备。他们希望能够使用他们现有的技能组合以及他们熟悉的工具和语言来构建这些应用程序。”

## RAD 的崛起

理论上，如果云平台与设备级客户端的通信如此密切，以至于它能够理解这些客户端是 HTML5 Web 浏览器还是原生 iOS 应用，那么开发人员可以使用他们最擅长的任何语言，然后专注于他们试图完成的逻辑。

理论上。尽管 HTML5 取得了成功，但 iOS 和 Android 平台确保了它永远不会成为基于云的应用程序在移动设备或任何设备上接触用户的完全通用的方式。我们最近称之为“全渠道营销”的是 25 年前被称为“营销”的一种努力——通过人们用来打电话给你的相同设备与他们沟通。

因此，Azure App Service 的目标是让开发人员，无论是业余的还是熟练的，都能在云中构建一个链接到云可访问的数据库(包括本地数据仓库)的应用程序，然后让该应用程序可以在任何主要设备上下载和部署。在输入方面，应用程序可以在 Visual Studio 中使用任何。NET 语言(当然)或者 Java，Node.js，PHP 或者 Python。或者，可以在 VS 之外，在 App Service 自己的开发环境中设计。

在输出端，可以为原生 iOS 或 Android 渲染应用，通过各自的应用商店下载；或者通过使用 HTML5 的现代网络浏览器呈现——同样的应用程序。

“应用服务允许开发人员使用 git 等方法部署他们的代码，所以你可以从任何编辑器或任何支持 git 的客户端进行部署，”Kahn 说。“然后在移动应用开发方面，我们也在客户端提供 SDK，以便能够与后端代码进行交互。我们不仅为原生移动平台(iOS、Windows 和 Android)提供 SDK。”

## 跨平台库

App Service 将支持的 SDK 和外部库包括 [Apache Cordova](https://cordova.apache.org/) ，因此开发人员可以使用 JavaScript、HTML 和 CSS 以及 [Xamarin](http://xamarin.com/) 平台构建本地应用，以编写跨平台应用。像 C#这样的网络语言。该平台支持[持续集成](http://www.martinfowler.com/tags/continuous%20integration.html) (CI)，支持每天多次更新，以及内置的分析、日志记录和实时监控。自动扩展使已部署的应用程序能够根据流量情况放大或缩小其实例。

虽然 Visual Studio 可以让 App Service 变得“可消费”,但它本身也被设计成一个开发环境。事实上，业务流程经理——比如说，比 PHP 或 Clojure 更精通 SAP 或 BizTalk 的人——将获得一种通过图表构建应用程序的方法，通过在 VS 之外运行的浏览器呈现。

这些外部库将以 Khan 所说的“统一 API”的方式呈现给开发者。他将其描述为一种可插拔的组件，任何开发人员(无论是熟练的还是业余的)都可以使用它来投影应用程序的图像，然后应用程序服务将该图像编译成一种或多种本机代码格式。

“如果开发者愿意，他们可以选择在更多的本地客户端上提供更丰富的体验，”Khan 说。“他们可以从拥有一个具有真正响应性设计的 Web 应用程序，并且当在移动设备上显示时可以基本上重新格式化自己，到下一步:你可以使用像 Cordova 这样的框架用更原生的包包装 Web 应用程序，以便你可以在商店(如 App Store)中交付它……[或]在 iOS 或 Windows Universal 或 Android 中构建完全原生的应用程序，但仍然连接到应用程序服务中托管的相同 API，并提供更丰富的功能，如推送通知。”

App Service 不是，因为可以理解的原因，它是非 Windows 设备的本地应用商店中应用的部署机制。

## 四类应用程序

在应用服务的背景下，会有不同类别的应用，你必须原谅它们的名字，因为它们看起来有点武断。“逻辑应用”包含了 BPM 老手可以用图解法构建的一类应用。其理念是为 BizTalk Server 客户提供一个平台，将他们现有的业务线应用程序迁移到云中。

Khan 称之为“API 应用程序”，使用元数据描述任何位置(云或内部)的任何 API。更准确地说，它们是使用 [Swagger](https://swagger.io/) 记录的 API 的组件表示，这已经是广泛使用的 API 表示和文档格式。“我们将这些信息提供给逻辑应用程序的可视化设计界面，”他说，“这样你就可以在构建业务流程时看到你可以用这个 API 做什么。但我们也让这些 API 可用于您的移动应用和网络应用中的代码，因此您也可以在那里使用它们。”

微软很快将有两次机会更详细地展示 Azure 应用服务:4 月 29 日至 5 月 1 日在旧金山举行的 [Build 大会，以及 5 月 4 日至 8 日在芝加哥举行的](http://www.buildwindows.com/) [Ignite 大会。](http://ignite.microsoft.com/#fbid=nhfTreytfYe)

特色图片[通过](https://www.flickr.com/photos/iliyangochev/6842632071/in/photolist-6fipeR-g7EtMM-6nhdpz-9fJ4yY-bGLe6V-oC9vKr-5ZWfLF-bqEh82-87y3MC-7jtoeo-6p1wLg-iDN2d6-6sSWhC-gLsfYr-9MUxKm-fnWi21-a6xPKm-ayscod-4kChCx-eJd2St-6hSnKT-9xDCrG-52h1uq-83UWdw-5Ti9F3-oZKiez-9fJapN-9GpTeV-8a4DJo-g7DHoX-5ivDkr-5ZLFwo-6hSnPK-4y977U-fSuTy7-8tiMtV-euVvmC-4y4MVD-aePKWj-6h75Dx-c7gKEd-9xBvoG-9xzAyF-9xCJZW-4VXEqq-a6XBtT-k7xVit-4tbQuw-8dv1w3-83UVGb) Flickr 知识共享。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>