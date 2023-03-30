# Azure Stack，不是 Windows Server

> 原文：<https://thenewstack.io/azure-stack-its-not-windows-server/>

在芝加哥举行的 Ignite 2015 大会上，微软采取了迄今为止最大胆的措施，切断与客户端/服务器时代的联系，进入新堆栈的其他读者生活和工作的世界。周一，该公司在这个新方向上迈出了一大步，正式宣布推出 Azure Stack，这是其为希望成为 Azure 的数据中心提供的私有云基础设施。

[![150504 Ignite 2015 05 (keynote, Brad Anderson)](img/8397d040c24ff8abf4c06d465d6a6c7a.png)](https://thenewstack.io/wp-content/uploads/2015/05/150504-Ignite-2015-05-keynote-Brad-Anderson.jpg)

布拉特·安德森

“如果你想到 Azure，你会发现在网络、存储和计算方面有你所知道的所有基础设施。我们提供一系列服务，如 IaaS 和 PaaS。然后是你所有的应用程序，这就是 Azure 的真正含义，”微软负责云和企业的公司副总裁布拉特·安德森在周一上午的主题会议上解释道。“两年前，我们宣布我们将把它的一部分带到您的数据中心，我们称之为 Azure Pack。”

这个 Azure Pack 的一部分在过去已经进入了合作伙伴供应商的硬件——例如，戴尔的云平台系统。因此，我们看到了第三方供应商品牌的私有云平台，围绕微软制造的服务器软件构建，但不称为 Windows。

除了 Azure Pack 之外，Azure Stack 所成为的不仅仅是 Azure 的缩影，而是 Azure 本身的扩展。正如几位微软官员周一证实的那样，Azure Stack 将 Azure 的文件和对象系统扩展到了私人空间。(而且 Azure Stack 不会是唯一做到这一点的微软技术。)

> “你希望能够获得这些云应用，并在你的环境中托管它们，”安德森说。“你告诉我们你想要 Azure——所有的 Azure——在你的数据中心。Azure Stack……实际上是我们给你所有的 Azure 来运行在你的数据中心。

Azure Stack 的进一步演示预计将在本周的 Ignite 上进行，但在早期阶段，我们看到了一个用户访问策略管理系统，该系统基本上复制了当前在公共 Azure 云上使用的系统，只是背景是黑色而不是蓝色。

“微软 Azure Stack 让应用程序所有者能够‘一次编写，随处部署’，无论是你的私有云、服务提供商的云还是公共 Azure 云，”周一微软服务器和云博客上的一篇帖子写道。“开发人员将能够最广泛地访问 Windows 和 Linux 上的应用开发平台，使用一致的工具、流程和工件来构建、部署和操作云应用。一个跨越公共云、私有云和托管云的 Azure 生态系统将允许您加入一个统一、强大的 Azure 云合作伙伴网络。”

有一次，微软集团工程经理 Jeff Woolsey 在 Azure 中向许多 Windows 服务器管理员演示了一个熟悉的概念，基于角色的访问控制(RBAC)。他演示了多个并发组件如何共存于一个公共名称空间中，以及一个策略如何同时应用于该空间中的所有组件，因为 Azure 认为它们绑定到一个应用程序。

[![150504 Ignite 2015 06 (keynote, Jeff Woolsey)](img/dd0bd51d8ad8e76e864ece6510cd30ff.png)](https://thenewstack.io/wp-content/uploads/2015/05/150504-Ignite-2015-06-keynote-Jeff-Woolsey.jpg)

杰夫·伍尔西

“如果我可以利用这个云应用程序、所有这些资源、这个 BLOB 存储、这个简单的基于角色的身份验证，[并且]我还可以在您的数据中心运行它，那该多好啊？”伍尔西问道。然后，他展示了一个四行 PowerShell 脚本，可以在公共 Azure 或私有 Azure 堆栈中启动应用程序，只需调整脚本的位置变量。

然后他展示了运行在 Azure Stack 上的相同应用程序。

“好好看看这里，”伍尔西宣称。“看起来就像天蓝色，不是吗？那是因为它是。”

为了证明他的观点，他展示了从公共 Azure 和在芝加哥 McCormick Place 的另一个房间启动的私有 Azure Stack 服务器运行的相同应用程序。“我们给了你想要的东西，”伍尔西说。“我们将 Azure 带到您的数据中心。”

微软的想法是使用相同的工具集使私有云空间和公共空间可寻址和可管理，并通过扩展，有效地将数据中心制成木板，如果你愿意，用于 Azure。这就是为什么“Windows 服务器”这个词越来越少被你认为是负责它的人提及的一个重要原因。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>