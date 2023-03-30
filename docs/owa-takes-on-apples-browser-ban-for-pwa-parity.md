# OWA 对苹果的浏览器禁令采取 PWA 平价

> 原文：<https://thenewstack.io/owa-takes-on-apples-browser-ban-for-pwa-parity/>

虽然许多 iPhones 上的 Chrome 和 Firefox 图标可能会说服用户，但苹果实际上已经禁止了除其 Safari 浏览器之外的任何浏览器，Safari 浏览器由 [WebKit](https://webkit.org/) 驱动，迄今已有十年。iOS 上的 Chrome 和 Firefox 浏览器(以及其他浏览器)仅仅是其同类产品的皮肤版本，使用 WebKit 构建，缺乏区分它们的功能。

据[开放网络宣传(OWA)](https://open-web-advocacy.org/) 组织称，这是苹果公司的一个纯粹反竞争的举动，不仅仅是降低了 iOS 用户的体验。更确切地说，浏览器禁令阻碍了渐进式网络应用(PWAs)的采用，从而影响了整个网络。渐进式网络应用是基于浏览器的应用，可以为开发者提供一种单一的方式来构建在桌面和移动设备上运行相同的应用，而不管手边的操作系统是什么。

OWA 是在英国垄断监管机构[竞争和市场管理局(CMA)](https://www.gov.uk/government/organisations/competition-and-markets-authority) 发起[移动生态系统市场研究](https://www.gov.uk/cma-cases/mobile-ecosystems-market-study)后成立的。该组织的一些成员被邀请向 CMA 做简报，并向他们建议他们所看到的“阻止可互操作的、基于标准的网络成为苹果和谷歌提供的本地专有生态系统的可行替代物”，正如他们在一份名为[“给围墙花园带来竞争”的监管提交文件中所写的那样](https://open-web-advocacy.org/files/OWA%20-%20Bringing%20Competition%20to%20Walled%20Gardens%20-%20v1.0.pdf)

在 OWA 的网站上，这个团队非常清楚地展示了他们所看到的利害关系:“应用程序开发的整个未来都岌岌可危。如果没有法规或立法的改变，我们可能会失去一个通用、免费、开放、一次编写、随处部署的应用程序分发和部署系统，这将大大降低企业和消费者的成本。”

虽然该小组的大多数成员都没有透露姓名，但因为害怕苹果公司的报复，也因为他们希望“讨论的是事实，而不是个人”，我们采访了三名成员，他们都将自己的名字与该项目联系在一起，以了解更多信息——网站开发人员和小企业主[马修·托马斯](https://twitter.com/mtomweb)、开发人员和顾问[斯图尔特·朗里奇](https://www.kryogenix.org/)以及可访问性和网站标准顾问[布鲁斯·劳森](https://brucelawson.co.uk/category/accessibility-web-standards/apple-browser-ban/)。

尽管苹果的 iOS“[围墙花园](https://www.pcmag.com/encyclopedia/term/walled-garden)”已经被讨论了很长时间，但 Langridge 认为该公司移动平台的最初愿景非常不同。

“当他们第一次宣布 iPhone 时，史蒂夫·乔布斯走上台说，‘我们做了这个全新的东西，就是它，iPhone’，他明确地介绍了它，说为它开发软件的方法是构建 web 应用程序。HTML、CSS 和 JavaScript 是你可以用来做这件事的平台，”Langridge 说。“从我们的角度来看，从一开始，他们就一直在谈论让网络成为平台。”

“我们会争辩说，我们正试图恢复乔布斯对 iOS 的最初愿景，”劳森补充道，他指的是史蒂夫·乔布斯在 2007 年介绍 iPhone 的同一段视频。

OWA 认为，鉴于整个 iOS 生态系统将被排除在外的事实，苹果的浏览器禁令是阻止开发者在他们的移动应用程序中进一步采用 pwa 的关键。

托马斯解释说:“苹果不仅在扼杀自己的网络应用，也在扼杀谷歌的网络应用，因为构建网络应用相对于原生应用的主要竞争优势是互操作性。”。

问题在于，Safari 以及支持 Safari 和 iOS 上其他浏览器的 WebKit 浏览器引擎缺乏与其竞争对手同等的功能。托马斯指出，其中一个缺乏的功能是推送通知，他说他和其他人从一开始就一直在要求这种功能。

“一个原生应用程序可以向你发送推送通知，但在 Safari 中运行的 web 应用程序不能，”Lawson 指出。“现在，如果它足够安全，能够从本机应用程序发送，那么它也足够安全，可以通过 Safari 发送，但它不在 Safari 中。我知道一些组织开发了一款 iOS 应用，纯粹是因为他们发送推送通知。”

其他缺失的功能包括 Safari 缺乏 PWAs 的全屏显示，无法使用硬件渲染，以及缺乏与打印机和扫描仪、支付设备、智能照明和家庭自动化等外围设备连接的网络蓝牙。

2021 年 12 月，CMA 发布了其[中期报告](https://www.gov.uk/government/publications/mobile-ecosystems-market-study-interim-report)，该报告建议[对当前形势采取三种潜在的补救措施](https://www.gov.uk/government/publications/mobile-ecosystems-market-study-interim-report/interim-report#:~:text=Remedies%20designed%20to%20enhance%20functionality%20and%20interoperability%20of%20browsers)。他们建议要求竞争对手的浏览器拥有同等的 API 访问权限，要求苹果允许其他浏览器在 iOS 上运行，作为替代，要求苹果“允许在 iOS 上使用 WebKit 的浏览器访问特定功能，包括支持 web 应用功能。”上个月，对中期报告的回应被接受，OWA 提交了其[回应](https://assets.publishing.service.gov.uk/media/622a2ee3e90e070ed1cf09b0/Open_Web_Advocacy_-_responses.pdf)，称要求访问功能将作为一个临时的权宜之计，“只有补救 1(等效 API)和补救 3(第三方引擎)才能恢复 iOS 上浏览器之间以及 iOS 上网络应用和本地应用之间的竞争。”此外，OWA 建议 CMA“‘需要广泛的网络应用程序支持’，该支持具有 Remedy 1(等效 API)和 Remedy 2(需要 Webkit 功能)未涵盖的特定技术方面。”

这就是目前的战斗。CMA 已经收到了对其报告的回应，并将于 2022 年 6 月 22 日发布最终调查结果。根据 Langridge、Lawson 和 Thomas 的说法，他们也向欧盟委员会提出了这些论点，但尚未得到美国监管机构的任何回应。尽管如此，CMA 发现的影响可能是广泛的。

“你确实会得到这样的印象，即全世界的监管者都在相互交流，”朗里奇说。“他们会饶有兴趣地关注此类案件，以及在英国发生的事情，以及苹果的合规程度和合规意愿。”

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>