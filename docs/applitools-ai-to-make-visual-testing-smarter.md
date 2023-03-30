# Applitools:人工智能让视觉测试更智能

> 原文：<https://thenewstack.io/applitools-ai-to-make-visual-testing-smarter/>

新尺寸的新手机可能会让消费者高兴，但对于试图跨设备标准化应用外观的组织来说，这是一个令人头疼的问题。

视觉测试初创公司 [Applitools](https://applitools.com/) 的联合创始人兼首席技术官亚当·卡尔米(Adam Carmi)表示:“公司花了很多钱来开发漂亮的应用，但他们也必须确保这些应用能在所有不同的设备和浏览器上正常运行。

它专注于自动化测试应用程序的外观，就像人眼看到的那样。实际上，它的算法旨在更好地处理人眼，通过它所谓的应用视觉管理(AVM)技术达到像素完美。

AVM 结合测试、图像处理和人工智能工具来识别应用程序在发布时看起来不正确，或者平台、设备或浏览器发生变化。

“用户界面对设备、浏览器和平台的任何差异都非常敏感。每个像素都可能导致按钮溢出屏幕。开发人员在 CSS 中所做的每一个改变都可能改变应用程序中的其他地方，导致品牌出现问题，完全禁用应用程序，最终花费大量资金，因为应用程序无法使用，”Carmi 说。

[https://www.youtube.com/embed/id0moFoDHG0?feature=oembed](https://www.youtube.com/embed/id0moFoDHG0?feature=oembed)

视频

该公司最新发布的产品名为[超快视觉网格](https://applitools.com/visualgrid)，它允许用户指定设备、浏览器和视口大小的组合来同时进行测试。它的 SDK 上传文档对象模型(DOM)快照(不是截图)和容器，这样它们可以更快更可靠地加载。

“我们有特殊的 SDK，它们不是抓取图像，而是从页面中抓取所有资源，CSS、HTML、图像、字体，将这些上传到我们拥有自己的设备和浏览器的网格，然后并行呈现所有资源的截图。这意味着您在本地运行所有的测试，甚至是在开发机器上。

“一个开发人员可以坐在咖啡店里，在他的 Mac 电脑上，在不同的移动设备上，在运行 IE 10 的 Windows 电脑上，对他的应用程序进行 20 次测试，而他甚至不需要这样的环境，也不需要等待 20 次来运行所有这些测试。这比建立一个真正的设备实验室要快得多，成本也低得多，”卡尔米说。

跨浏览器和跨设备测试不具成本效益。他说，在客户端，99%的错误不是特定于客户端的。

“我们认为，你可以编写一个涵盖这些边缘情况的测试，在 20 台设备上运行该测试，但你需要运行 1000 个其他测试，而不需要所有这些开销。所有这些测试都运行 20 次是没有意义的。你可以用更智能的方式做事，节省大量资金，并从中获得更多收益。”

它还利用可视化网格支持 Selenium Java、Selenium Javascript、Selenium C#、Selenium Python、Selenium Ruby、Webdriver IO、Cypress、Storybook，以及面向人工 QA 和营销团队的 Selenium IDE 扩展。该公司计划在年底前支持 50 个 SDK。

该公司还凭借 Selenium IDE(记录和回放网络自动化测试的开源工具)占据了领先地位。它最初是 Firefox 中的一个浏览器扩展，但不再支持 API。

它使不会编码的 QA 工程师能够编写和维护自动化测试。

新的 Selenium IDE 被设计为一个现代浏览器扩展，支持 Chrome 和 Firefox，并支持其他正在开发的浏览器。该公司已经在 IDE 和 Applitools Eyes 之间建立了一个集成，这是一个人工智能视觉测试和监控解决方案。

“我们采用 Selenium IDE 并从头开始重写。现在它是一个强大的现代工具。它可以从您的持续集成服务器回放这些测试，我们还添加了一个扩展，允许您记录可视化测试，”Carmi 说。

[https://www.youtube.com/embed/Lk2T1yv_kO8?list=PLkqF-NUszJY64CJ-ahQPwHciDw7nMLW04](https://www.youtube.com/embed/Lk2T1yv_kO8?list=PLkqF-NUszJY64CJ-ahQPwHciDw7nMLW04)

视频

## 难题

2012 年，卡尔米在一家以色列安保公司管理一个 R&D 组织。

“我们为几个品牌的用户界面贴上了白色标签，并用六种不同的语言进行了本地化。我们有富士通的白色标签。这些人对用户界面非常严格。2012 年的时候，UI 还没那么重要。但这些人非常细致——字母边上有一个像素，颜色不完全合适，日文标题当然也不一样……我们就是无法满足他们的质量要求，”他说。“我们要花整整一周的时间来测试一切，但我们仍然会遇到 UI 问题。”

他开始从 IBM、微软、惠普等供应商那里寻找工具，但毫无结果。功能测试，可以；视觉测试，没有。所以他开始自己造一个。他发现这非常困难。

“我花了八个月的时间才得到一个几乎不起作用的东西。他说:“我的联合创始人摩西[米尔曼]很喜欢它，我们在 2013 年创立了这家公司。

“当我们得到一个非常可靠的工具时，世界发生了变化……突然之间，用户界面成了所有应用程序中最重要的部分。”

该公司现在位于加利福尼亚州的圣马特奥，在特拉维夫设有 R&D 办事处。他说，它的客户包括索尼、万事达、Salesforce、Gannett 和以色列政府，以色列政府经常受到试图破坏其网站的黑客的攻击。

大约有 30 个用于视觉测试的开源项目，如 PhantomCSS、Huxley、Wraith、Shoov、Gemini。商业产品包括 Screener.io 和 Percy.io. Carmi 认为它们都是玩具，没有 Applitools 的成熟度或功能性。

他举例说，Applitools 可以在内容不变的情况下忽略间距的变化。您可以要求工具不要向您显示在不同环境中的每个测试中都会弹出的标题更改。它可以处理重复出现的模式，比如一个零售网站某一天有七种产品，但第二天只有四种。如果有一个不断变化的广告，你可以屏蔽它，这样它就会被忽略。如果有东西在移动，你可以指定一个浮动区域，在这个区域内移动是可以的。

“与开放工具类似，[商业产品]稍微好一点，但它们没有围绕人工智能的维护、布局中的动态数据、跨设备、跨浏览器测试、对不同 SDK 的支持。我们支持超过 40 个 SDK，所有主要的网络和移动测试技术。如果你想测试 pdf，我们支持。如果你有一个不能用标准方式测试的机顶盒或物联网设备，如果你有一个截图，我们可以验证它，”他说。

除了用于监控网站、本地化和安全性，如在以色列政府示例中，它还可用于根本原因分析。他说，它不仅显示了变化，还显示了在页面的执行过程中是什么导致了这些变化。

专题图片:[杰瑞米·基思](https://www.flickr.com/photos/adactio/)的[设备](https://www.flickr.com/photos/adactio/7753864240/in/photolist-cPbzGu-DRhWyL-gS8e2R-fq91nm-9Xe4DZ-NYLYHW-5ipxWW-orFJ77-bB5WUj-2b7suZT-rm5HkE-9sM9ka-584UoN-29J9KQz-95Afh5-29KwZ97-96bybq-4Um4BF-5dKpze-R969vW-aREgkr-c42Msy-9o5DAX-gWjy43-gWjxc5-ajh5Mg-8J6Ej-4xc2sa-zZf8NR-ahgwDn-dNvDeh-bwCbbu-2jr8nK-5fD979-ajh6yk-2fMu6Ho-29KwYYN-dyq8bp-29WhaXo-7FDBma-5uNqN5-27wfKbE-ik78vy-29sBmdM-4cKQkP-SqRhCW-S2GW42-2b7svoi-2fKbeYQ-2fUTGPB)。根据 [CC BY-SA 2.0](https://creativecommons.org/licenses/by/2.0/) 授权。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>