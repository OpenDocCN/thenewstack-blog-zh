# 火星上的 TypeScript:HubSpot 如何将 TypeScript 带给其产品工程师

> 原文：<https://thenewstack.io/typescript-on-mars-how-hubspot-brought-typescript-to-its-product-engineers/>

[](https://www.linkedin.com/in/duncanwalter)

 [邓肯沃尔特

邓肯是 HubSpot 前端平台团队的高级软件工程师。他致力于为工程师同事提供符合人体工程学的工具和强大的自动化。在 HubSpot，他专注于引入 TypeScript 以及增强编辑器、代码模块、代码生成和 lint 工具。](https://www.linkedin.com/in/duncanwalter) [](https://www.linkedin.com/in/duncanwalter)

TypeScript 是 JavaScript 工具箱的一个极好的补充。随着项目的扩展，静态类型减少了摩擦，JavaScript 项目正在快速扩展。现在，用户比以往任何时候都更期待复杂而愉快的浏览器体验，以推动现有技术的发展。自 2018 年以来， [HubSpot](https://www.hubspot.com/) 的基础设施团队一直使用类型化 JavaScript 来保持领先于不断变化的客户期望、技术债务和整体竞争。

不幸的是，这里有一个陷阱。虽然像我们这样的基础设施团队受益于 [TypeScript](https://thenewstack.io/what-is-typescript/) ，但是我们的产品工程师却被落在了后面。简单地说，TypeScript 从根本上与我们的产品工程师用来构建前端产品的“包含电池”工具不兼容。

我们对自己提供的基础设施抱有很高的期望。我们的角色是尽可能让工程师成为最快乐、最有生产力的团队。我们的责任之一是方便使用现代工具，如 TypeScript。因此，我们一直在努力消除障碍，以便我们的工程师可以享受他们应得的优秀的打字稿基础设施。对于我们的团队来说，这是令人兴奋的一年，因为我们在 TypeScript 上的工作终于有了回报。HubSpot 的产品组织今年将转换为 TypeScript。

这种迁移是一项持续的工作，涉及许多方面；在 TypeScript 中构建代码只是第一步。从组织的角度来看，我们正在加大对内部打字培训和支持的投资。在技术方面，我们还发布了用于迁移、编辑和维护 TypeScript 代码的新工具。今天，我们想分享一些问题和解决方案，我们一直在努力把 TypeScript 带到一个前所未有的地方。

## 带着同情迁徙

 [乔治·坎普

George 是 HubSpot 基础设施工程团队的高级软件工程师。在 HubSpot，他热衷于构建优秀的开发人员体验和坚实的工具基础。George 对 JavaScript 充满热情，但目前正致力于将 TypeScript 引入 HubSpot 的前端。当不在键盘前时，他是一个狂热的航空爱好者和新培养的私人飞行员。George 拥有科罗拉多丹佛大学的机械工程学士学位。](https://www.linkedin.com/in/georgekemp) 

今年，我们团队的主要关注点是确保我们的 TypeScript 迁移不会对产品工程师造成干扰。切换到 TypeScript 是一个[有影响力的变化](https://thenewstack.io/what-trivago-learned-adopting-typescript/)，即使在理想的情况下，情况往往并不理想。例如，我们的许多工程师几乎没有使用 TypeScript(或任何静态类型语言)的经验。维护团队自治是另一个关注点。我们的前端产品团队充满活力。一些团队可能专注于性能和工具，而其他团队则在积极开发新特性。我们知道 TypeScript 迁移不会是每个团队的当务之急。考虑到这一点，我们的方法是提供灵活的自助式迁移资源。有了合适的工具，团队可以创建与其任务和可用资源相兼容的 TypeScript 迁移策略。

鉴于我们的分布式迁移战略，教育和支持是关键。整天使用不熟悉或缺乏文档记录的工具是不可持续的疲惫。工程师必须能够自由访问 TypeScript 学习材料，并控制自己采用 TypeScript 的速度。例如，除了所有 HubSpotters 享受的标准学习福利之外，我们现在还为工程师提供免费访问以 TypeScript 为中心、基于订阅的在线学习工具。即使有这些资源，学习也需要时间。期望并指导工程师将工作时间用于打字稿学习。

请记住，工程师通常和我们一样对 TypeScript 感到兴奋。在迁移过程中，我们不能夸大热情的影响力。基础结构团队的角色通常不提倡 TypeScript。相反，要专注于消除进入壁垒。一点一滴都有帮助。使用`ts-migrate`或类似工具自动完成重命名文件和添加道具类型等繁忙的工作。在每个项目中配置 TypeScript 并将单个小文件迁移到 TypeScript，这样团队就不需要自己担心配置步骤。提供工具来识别哪些模块适合迁移或者迁移后最有影响。一次。

也就是说，寻找并保持与打字稿怀疑论者的健康对话也很重要。对话的双方都有很多收获。怀疑论者通常可以在早期指出迁移策略中的弱点，这为分类和缓解提供了宝贵的额外时间。交换座位，让工程师们知道他们的声音被听到并在他们的工具中有发言权是至关重要的。即使他们在一般意义上被否决，怀疑论者也应该得到一个有同情心的迁移过程，在可能的情况下适应他们现有的工作流和偏好。根据我们的经验，当怀疑论者的担忧被认真对待时，他们甚至可以成为倡导者。

## **幕后**

从表面上看，迁移到 TypeScript 的 HubSpotters 将会看到他们在其他地方所期望的相同行为。TypeScript 增强了编辑器功能，在每次构建时运行，并在编译时被清除。但是在幕后，我们的 TypeScript 基础结构是独一无二的。既然我们已经从人类的角度看到了 HubSpot 的 TypeScript 迁移，那么我想拉开帷幕，揭示一下我们是如何在技术层面上实现这种迁移的。

首先，一些背景。HubSpot 拥有自以为是的集成工具，抽象出了常见的工程需求，如本地开发服务器、linter 配置、传输、捆绑、测试自动化和部署。我们的工具始终是工程师喜欢开发我们产品的首要原因。固执己见的工具确实会带来一些维护成本，但是我们从中获得的价值是不可替代的。

出于支持类型脚本的目的，我们工具中的关键问题是我们不在`node_modules`中存储依赖关系。这很重要，因为 TypeScript 只知道如何找到位于`node_modules`中的依赖项。此外，与 JavaScript 生态系统中的大多数其他工具不同，TypeScript 有意不支持配置替代模块解析策略。幸运的是，有志者事竟成。我们决定放弃打字稿。虽然这不是一个容易解决的项目，但我们发现，在 TypeScript 中支持自定义解析策略只需要进行令人惊讶的少量更改。

如前所述，大多数 JavaScript 工具支持自定义解析策略，因此有大量的现有技术可供使用。几乎所有这些工具都允许用户提供一个`resolve`功能。通常`resolve`会接受一个文件路径和一个导入说明符，然后将路径返回给所请求的依赖项。这是任何模块解析策略的核心，TypeScript 也不例外。修补类型脚本的第一步是使`resolve`可配置。`resolve`也是我们的 TypeScript 补丁中唯一影响类型检查的部分，这意味着它是补丁中唯一需要保持稳定的部分。

```
  // resolve('.../module.ts', 'react') -&gt; '.../react/index.ts'
 function resolve(fromPath:  string,  identifier:  string):  string  {
      // return the path of the resolved module specifier
      return  '...';
 }

```

TypeScript 需要几个其他函数来支持关键的编辑器特性，比如自动导入。一、  的反面解析功能: getModuleIdentifier 。就像`resolve`告诉 TypeScript 在给定导入语句的情况下在哪里找到依赖项一样， getModuleIdentifier 告诉 TypeScript 如何导入给定位置的依赖项。它采用两个模块的路径，并返回一个导入说明符。具体来说，它返回从第一个模块导入第二个模块所需的导入说明符。最后，TypeScript 需要一个getAutoImportableModules函数，该函数接受项目根的路径并返回一组模块路径说明符对。

```
  // getModuleIdentifier('.../module.ts', '.../react/index.ts') -&gt; 'react'
 function getModuleIdentifier(fromPath:  string,  toPath:  string):  string  {
      // return the identifier for referring to toPath from fromPath
      return  '...';
 }

 type ImportableModule  =  {
      path:  string;
      identifier?:  string;
 };

 function getImportableModules(projectPath:  string):  ImportableModule[]  {
      return  [...];
 }

```

这三个函数是对 TypeScript 中现有逻辑的替代。一旦它们变得可配置，就用配置的版本替换 TypeScript 的默认逻辑，以便使用修补的 TypeScript 版本启动和运行。此修补程序是轻量级的，通常在不同的 TypeScript 版本中是稳定的，因此当新的 TypeScript 发布分支可用时，可以将它作为基础。

## **展望未来**

既然 TypeScript 已经在我们的工具箱中，我们看到了许多增强现有工具的机会。我们可以用 evergreen 生成的 API 类型在前端和后端项目之间架起一座桥梁。从那里，我们很高兴在 TypeScript 现有支持的基础上构建新的编辑器功能，分析包的类型健康状况，并向我们的代码 mod 堆栈添加类型信息。TypeScript 在 HubSpot 有着光明的未来。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>