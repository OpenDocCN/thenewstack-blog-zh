# Node.js:企业情况报告

> 原文：<https://thenewstack.io/node-js-an-enterprise-situation-report/>

Node.js 在开源领域磨砺了几年，然后被 LinkedIn 和 Joyent 这样的大型创业公司使用，现在正走向企业。从扩展虚拟化 hyper visors 到采用 Docker、Node.js 等热门新技术的操作系统级虚拟化，JavaScript 程序员大军正在推出新产品、产品和项目，使企业采用这些技术变得轻而易举。

让我们深入了解是什么让 Node.js 成为企业 JavaScript 中如此优秀的开发人员和服务器工具。

在 Node.js(以及一般的 JavaScript)如此受欢迎和成功的今天，它的成功有一个很大程度上不为人知的原因，可以说比它的速度、简单或没有任何准入门槛的技术优势更重要。这并不是缺乏一个中央集权的公司体制或所有者，就像微软和微软的情况一样。NET，或者甲骨文和 Java 的混合分支专制政权。Rails 社区为构建 web 应用程序而构建一个简化的系统并不是基于中心约定的努力。Node.js 成功的核心是社区消除了前面提到的以前语言和堆栈的障碍。这一成功已经并将继续完全归功于 Node.js 社区的人们。

> 人

node.js 生态系统中涉及的组织、公司和人员正在快速增长。现在，它通常是第一个以可用的方式实现 web 套接字和实时 web 流等新技术的技术堆栈。社区也比其他竞争技术更快地将这些新技术引入稳定的核心。它正处于从一个前沿社区向企业开发人员可以信赖的稳定且有弹性的堆栈转变的风口浪尖上。

扩展到 Node.js 是一个很好的方法，可以扩展技术选项，构建一个管道和社区来构建和支持企业项目。这里有一些想法来帮助将这些项目带入企业，以帮助建立一些技术多样性，从而建立候选管道！

> 财务 API 处理

金融是一个很大的空间，有很多问题需要解决。已经有一些库提供与彭博 API ( [node-blpapi](https://github.com/bloomberg/node-blpapi) )的连接，通过[开放汇率项目](https://openexchangerates.org/)([NPM-汇率](https://github.com/josscrowcroft/npm-exchange-rates))提供实时货币汇率，以及围绕 Excel 电子表格的库。其中最流行的是 [excel-export](https://www.npmjs.org/package/excel-export) 。从一开始就不缺少通过 NPM 安装的库。使用基于 Node.js 的项目的财务数据。

建议:一个非常有趣的 web 应用程序的建议是，使用实时 Node.js 功能，如 socket.io 或任何具有 web 套接字和财务数据的功能，这将成为一个优秀的交易或投资组合管理应用程序。为彭博数据连接一个漂亮的仪表板，尤其是那些经常更新的数据。内置一些用于后期分析的 Excel 导出选项，您将有一个绝佳的机会来构建一个使用独特的实时流数据的应用程序，并且易于使用库。这是获得经验和扩展团队多语言技能的好方法。

> 货运物流数据

货运数据需要花费大量时间进行各种格式的解析: [XLS/XLSX (excel)](https://www.npmjs.org/package/excel-export) 、 [EDI](https://github.com/rinie/node-edi-parser) 、 [XML](https://github.com/Leonidas-from-XIV/node-xml2js) 、 [CSV](https://www.npmjs.org/package/csv) 、X12 EDIFACT、410 交易集、价格权限、运输时间、零担货物的调度、TL、联运数据和实时交付数据，这只是其中一些来源。使用 Node.js 库可以在高容量和高事务需求的情况下轻松管理这些数据。

处理这类数据最简单的方法之一是编写一些已经需要完成的东西，简单地将 Node.js 放入生态系统的某个地方。货运业务已经使用了大量不同的工具来导入数据，从通过浏览器的用户界面到带宽有限的移动应用程序。Node.js 是构建中间件的一个很好的服务解决方案，可以用最少的资源集成到已经是高事务、大容量和高吞吐量的数据中心。

用 node.js 在这些不同的系统之间提供一些粘合剂，增加了从事货运业务的任何内部 IT 开发团队的选择和能力。

> 工具箱里还有一件工具

node.js 的用户群在去年(以及前年和前年)急剧增长。图书馆的藏书从几百册增加到几万册。这个社区已经发展到数万名用户、数百名开发者、数千名观察者和其他以不同方式参与其中的人。可以说它是当今最大的项目框架团队之一。所有这一切都是由社区的力量建立起来的，由你希望在企业空间中出现的那类人组成。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>