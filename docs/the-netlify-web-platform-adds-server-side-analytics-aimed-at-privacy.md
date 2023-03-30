# Netlify 网络平台增加了针对隐私的服务器端分析

> 原文：<https://thenewstack.io/the-netlify-web-platform-adds-server-side-analytics-aimed-at-privacy/>

专注于简化网站开发的初创公司 Netlify 推出了一款服务器端分析工具，旨在加强隐私保护和遵守数据保护法规。

“GDPR[欧洲的[通用数据保护条例](https://eugdpr.org/)产生的一个结果是，许多大公司对个人用户进行密集跟踪——在许多不同的网站上运行脚本，从浏览器中捕获大量详细信息。这就让你拥有了各种人的大量数据，” [Netlify](https://www.netlify.com/) 的[马特·比尔曼](https://github.com/biilmann)联合创始人兼首席执行官说。

他说，问题是:你是在建立一个大型系统来跟踪用户在网络上做的事情，还是在报告你的网站现在在做什么？

他说，该公司创建 Netlify Analytics 是因为其客户想要一种不存储用户数据并将其发送给第三方组织的解决方案。

虽然大多数第三方客户端分析程序使用像素、JavaScript 和 cookies 来跟踪用户行为，但 Netlify Analytics 直接从其全球边缘节点收集数据，无需在客户端运行任何代码。据该公司称，直接使用服务器日志中的数据意味着对性能没有影响。

这也意味着不会因为广告拦截器、僵尸程序或禁用的 JavaScript 而丢失任何信息。

“最酷的事情之一是 404 未找到部分。因为我们来自服务器，而不是像其他一些分析工具一样来自客户端，当他们遇到一个资源而它不在那里时，[他们]遇到一个未发现的错误。我们将这些数据呈现出来，您可以看到并纠正这些情况—重定向、图像丢失。对于开发者来说，这是巨大的，”net lify 的开发者体验主管 Sarah dras ner 说。

Biillmann 说，如果图像上的名称被更改，网站在两个页面上使用该图像，但名称只在一个页面上更改，404 not found 部分将指出这种类型的错误。

她说，如果一个开发者忽略了将一个项目添加到 Google Analytics，那么数据就消失了，因为它是客户端的。Netlify Analytics 使开发人员能够继续添加它，并看到过去。

因为 Netlify 是一家网络提供商，GDPR 允许它存储 IP 地址来运营这项服务，但据该公司称，这是因为它没有做任何跟踪用户的事情。它只报告系统行为和页面服务的 IP 地址总数。它说，它不会以允许客户获得可识别用户信息的方式与客户共享信息或 IP 地址，并且分析服务从不处理任何个人信息。

虽然还有其他基于服务器日志的分析选项，包括 [Matomo](https://matomo.org/log-analytics/) 、 [AWStats](https://awstats.sourceforge.io/) 和 Webalizer，但这是一个无需集成的一键式设置，联合创始人兼总裁[克里斯巴赫](https://twitter.com/chr_bach?lang=en)指出。

来自日志的数据每小时一次被拉入 Netlify suite 中的仪表板，包括页面浏览量、独立访问者、热门页面、热门来源和使用的带宽。

该公司在伦敦 JAMstack 会议上宣布了 Netlify Analytics。JAMstack 是使用 JavaScript、API 和标记来构建动态 web 应用程序的方法。它是该公司基于 Git 的全球应用交付平台的附加产品，每月额外支付 9 美元，浏览量为 25 万次。

该公司最近还发布了 [Netlify Dev](/netlify-site-deployment-adds-development-testing-for-the-laptop/) ，这是一个强大的本地开发服务器，具有实时共享功能，使开发人员能够直接在笔记本电脑上构建和测试他们的应用程序。

图片来自 Pixabay 的免费照片。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>