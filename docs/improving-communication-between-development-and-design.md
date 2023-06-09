# 改善开发和设计之间的沟通

> 原文：<https://thenewstack.io/improving-communication-between-development-and-design/>

[](https://www.linkedin.com/in/brian-leung-7246a858/?originalSubdomain=ca)

 [梁兆辉

Brian 是 ZenHub 的一名设计师，为软件团队设计大规模高效工作的方法。在 ZenHub 之前，他开发了几个获奖的移动应用程序，并从头开始设计了几个产品。](https://www.linkedin.com/in/brian-leung-7246a858/?originalSubdomain=ca) [](https://www.linkedin.com/in/brian-leung-7246a858/?originalSubdomain=ca)

啊，开发和设计——两个如此不同的实践，却又如此互补和相互依赖。当这两种实践相互孤立时，它很快就会成为错误沟通和浪费工作的温床。但是，当他们可以自由交流合作时，他们可以成为真正充满活力的二人组。

我们知道打破开发和设计之间的孤岛是一项挑战。从设定期望到记录项目需求，有很大的出错空间。建立一个允许设计和开发紧密合作的过程说起来容易，做起来难。我们已经看到，通过利用各种签到、会议、需求收集过程和其他技术，我们的团队在合作方式上取得了巨大的成功。

在这篇博文中，我们将带您了解我们团队在项目的不同阶段打破开发和设计之间孤岛的可靠方法。作为产品设计师(布莱恩)和工程经理(安德鲁)，我们经常在一起工作，所以你将要读到的一切都直接来自我们制作 [ZenHub](https://www.zenhub.com/) 的真实经历。

## 共同的目标

 [安德鲁·尼克森

Andrew 是一名前端开发人员和工程经理，在各种公司拥有十多年的经验。他曾在代理机构、初创公司和大型企业工作过，可以将这些丰富的经验用于改善 ZenHub 的项目管理和执行。](https://www.linkedin.com/in/andrew-nickerson-7170672b) 

产品定义确保开发和设计朝着一个共同的目标努力。

避免开发和设计之间的孤岛的第一步是尽可能早地创建一致性。我们使用的一个值得注意的方法是“三人小组”会议。这包括在讨论即将到来的特性或项目时，确保我们有技术(开发)、用户(设计师)和业务(产品经理)的观点。

第一次会议用于讨论目标并从不同角度理解复杂性。尽早讨论可行性和复杂性有助于我们设定现实的期望。在最初的“三位一体”会议之后，我们将大约每周进行一次检查，以提高整个产品开发流程的可见性，并在必要时进行重新调整。

### **来自设计师视点**

使用“三箱”会议，我们的设计团队可以尽早开始识别复杂性。通常，这将发生在任何设计工作开始之前，因此开发可以利用关于可行性的公正意见。对于设计师来说，“三个盒子”会议是展示不同设计阶段(用户研究或可用性结果)的产品的机会，允许我们从用户的角度推动对话。最终目标是确保团队对推进项目充满信心。

我们的设计团队有时会在项目的开始阶段组织研讨会。这可能包括像设计冲刺或亲和力映射这样的事情，并帮助建立跨职能的协作流程。

### **来自开发者视点**

在产品定义阶段，我们的开发团队识别任何潜在的技术挑战，以便我们可以将工作分解为可操作的步骤。任何产品中还没有的功能和一些复杂性都需要被识别为需要一个峰值，所以我们可以在提交任何工作之前处理细节。

作为一个团队，我们专注于尽早发货。在产品定义期间，我们的开发人员将提供备选方案来满足业务和用户需求。例如，在 ZenHub，我们可能会考虑利用 GitHub 平台来帮助我们更快地发货，并更快地为用户带来改进，而不是构建我们自己的通知系统。

## **范围界定和故事指向**

当项目走到一起时，设计和开发一起工作来识别实现挑战，并在满足用例的可行解决方案上进行协作。技术分解让我们可以优先考虑核心体验。一旦完成，我们会重新评估是否有任何超出范围的问题值得在首次发布前完成。

项目规范概述了这些特性，并将它们分解为用户故事和设计规范。一旦开发和设计团队相信他们在规范文档上有足够的定义，我们就把他们分成 GitHub 问题并评估它们。提前调整技术故障可以更好地逼近范围和期限。

### **来自设计师视点**

当构建一个项目规范文档时，我们将在 ZenHub 中创建一个 [epic，并在那里记录所有相关信息。(史诗是 ZenHub 中包含几个问题或子任务的工作主题)。当它们准备好被处理时，它将被分解成单个的问题。设计师使用小组的任务板，以及产品和设计任务板，来跟踪每个小组和每个功能完成的工作。](https://help.zenhub.com/support/solutions/articles/43000010341-an-intro-to-zenhub-epics)[工作流](https://www.zenhub.com/workflow-automation)经过配置，当问题和事件在管道间移动时，产品团队和团队都可以看到进度。

### **来自开发者视角**

开发人员将通过设计把史诗放在一起，并把它翻译成单个的工作单元，这些工作单元可以在团队成员之间分配。本着快速发布的精神，我们通常创建多个代表发布阶段的子计划，MVP 是第一个。当我们询问需求时，我们将问题放入 MVP epic 和后面的第二阶段。

在这个阶段，在决定什么是交付客户价值绝对必要的方面，学科之间有很多的来回。这些对话的理想结果是使我们获得初始版本的最小积压。分阶段的史诗给了我们一个逻辑的地方来跟踪我们在项目期间发现的额外工作，我们在最初的发布之后评估这些工作。我们的目标是让开发团队专注于手头的工作，同时不要忘记我们在前进的道路上想到的所有美好的事情。

## **设计和开发的一致性**

一旦项目规范到位，我们使用敏捷事件来理解在我们的双周冲刺中可以实现什么。从事该项目的开发人员、项目经理和设计人员将参加待办事项细化、冲刺规划和每日例会。目标是讨论更好的细节，并建立对故事的可靠估计。我们发现围绕设计的细节问题、边缘情况或缺失的规格细节往往会浮出水面。

### **来自设计师视点**

让设计人员参加 backlog 精化会议有助于消除信息孤岛，填补项目规范中可能缺少的信息空白。规格可以在细化过程中更新或减少，以确保及时冲刺。当我们进入 sprint 规划时，设计师们很好地了解了我们将发布哪些面向客户的改进，以及哪些资产是必需的。

### **来自开发者视点**

按照标准的敏捷方式，开发团队评估最小可行产品(MVP) epic 中的问题，因此我们可以识别团队成员之间理解上的任何差距。在每个人都理解了规范之后，开发人员将使用[计划扑克](https://www.zenhub.com/planning-poker)来合作评估每个故事。这让开发人员有更多的讨论，并将提供更可靠的估计和准确的 sprint 预测。

在准备会议之前，我们一直在尝试将我们围绕需求的大部分讨论转移到 GitHub 问题的评论部分，这样我们就可以有更集中的 backlog 精化会议。我们发现，当团队有更多的时间考虑需求，而不是试图在会议中同时做出决定时，这有助于我们进行更好的对话。

## **设计师和开发人员之间更好的信息共享**

一旦项目范围达成一致并被组织成问题，我们的工作流就是相当标准的 Scrum，但是有一些方便的自动化来删除那些无聊的东西。sprint 是使用一个[ZenHub sprint](https://www.zenhub.com/sprint-planning)工具组织和构建的，该工具自动创建下一个 sprint，并在当前 sprint 结束时将任何未完成的问题转移到下一个 sprint。

手动分配问题并将其拉入“进行中”管道，但是一旦推送拉式请求(PR)并将其与问题相关联，它会自动跟踪 PR 的完成状态，因此我们的问题会在工作合并后立即完成。当我们在过程中遇到范围蔓延或遗漏需求时，我们将生成新的标签，并作为一个小组决定额外的范围是属于当前的 epic 还是第二阶段。

### **来自设计师视点**

管道的清晰定义允许跨团队的可见性，以了解正在做什么和需要注意什么。当有设计或资产与开发同时进行时，开发人员可以很容易地标记一个设计者或将一个问题标记为阻塞。

### **来自开发者视点**

我们依靠 PR 模板来帮助我们自动化一些任务，并让开发人员按部就班地完成任务。我们的模板提示开发人员使用一个`Closes`关键字，这样 ZenHub 就会自动将 PRs 与他们的问题关联起来。如果变更是面向用户的，如果它需要任何特殊的测试，我们也确定我们期望什么样的审查。

## **设计评审和代码评审在一起**

我们所有的工作都需要经过产品所有者的代码审查、质量保证和批准。我们在工作空间中使用额外的管道来指示这些状态，因此我们可以可视化我们工作流中的瓶颈，并在日常会议中讨论它们。

### **来自设计师视点**

截图或视频提供了变更的历史，是设计师进行异步评审的一种快捷方式。通常，设计师、QA 或开发人员会在发布 PR 后，或者如果某个问题被标记为需要设计评审时，立即接到电话。让设计师直接在 GitHub 中意味着更少的上下文切换，我们可以利用内置的审查功能。

### **来自开发者视点**

我们一直在利用 GitHub 代码注释接口，在 PRs 通过我们的工作流程时，为它们提供线程化和可解析的反馈。QA 和设计师可以将注释放入代码中，开发人员可以一个一个地解决它们，这样我们就可以看到进度，并且有一些长期运行的评审的历史。

## **结论**

没有一个答案可以帮助你从团队中完全消除孤岛。然而，通过一致性、开放式交流和我们上面分享的一些技术，我们相信您可以为您的设计和开发团队释放新的生产力水平。不仅如此，他们在一起工作会更开心——对我们来说，这才是真正的胜利！

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>