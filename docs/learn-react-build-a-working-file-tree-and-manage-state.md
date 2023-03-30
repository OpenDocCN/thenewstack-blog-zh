# 学习 React:构建一个工作文件树并管理状态

> 原文：<https://thenewstack.io/learn-react-build-a-working-file-tree-and-manage-state/>

React 的一个特性是使用虚拟 DOM。虚拟 DOM 是 React 能够如此快速地更新网页的[文档对象模型](https://developer.mozilla.org/en-US/docs/Web/API/Document_Object_Model/Introduction) (DOM)的原因。

React 拍摄了实际 DOM 的两个快照。当一个组件在虚拟 DOM 上更新时，它还没有在 DOM 上更新。将更改与 DOM 的第二个快照进行比较，这是一个虚拟 DOM 更新前的快照，允许 React 查看在哪里进行了更新，并轻松更新实际的 DOM。这个过程比遍历整个 DOM 要快得多。这里有一个很棒的 [YouTube 视频](https://www.youtube.com/watch?v=QZ-QWUnTBiI)，有这个过程的更多细节。

[*public/index . html*](https://github.com/JessicaWachtel/React-To-Do-List-Tutorial/blob/main/index.html)(在 GitHub repo 中)是这个应用程序连接到 DOM 的地方。这个文件中第 11 行的 id“root”就是发生这种情况的地方。Root 或 app 是这个 id 非常常见的名称，但它可以被命名为任何名称。

## **引擎盖下**

*[ReactDOM。Render](https://reactjs.org/docs/react-dom.html)* 是一个 react 方法，将 React app 渲染到网页上。 *ReactDOM.render* 采用两个参数，元素和容器。在 [*src/index.js*](https://github.com/JessicaWachtel/React-To-Do-List-Tutorial/blob/main/index.js) 中，您可以看到我们正在将 BasicApp 元素呈现到上一节讨论的“根”容器中。这是[一篇关于 *ReactDOM.render* 的更详细的文章](https://adiati.com/reactdomrender)。

*index.html*和 *index.js* 是 React 应用中的标准。关于 React 应用程序的文件结构以及它们如何协同工作的更详细的分类，[这是一篇优秀的文章](https://we-are.bookmyshow.com/get-started-with-your-first-react-js-app-part1-34eee7b8559b)。这个深入到了 *npx-create-react-app* 中的 boiler plate 文件，所以其中一些并不适用于此处，但是总体主题和概念是相同的。

JavaScript 的一个扩展, [JSX](https://reactjs.org/docs/introducing-jsx.html) 本质上是一个 JavaScript/ HTML 组合和 React 的构建块。JSX 允许您在同一个文件中对 HTML 和 JavaScript 进行编码，并极大地减少了编码时间。在我们的应用程序中，来自 BasicApp.js 的文本显示在浏览器中。“欢迎来到本教程”标题是 React 类组件中 h1 标签内的简单文本。  在引擎盖下，Reacts 库将此内容读作*reactor . create element(' h1 '，{}，“欢迎来到本教程”)*。

[看看这段视频](https://www.youtube.com/watch?v=VWadE7PMF0c)，它展示了 JSX 代码和它的普通 HTML/ JavaScript 代码的并行视觉效果。更多关于 JSX 的细节，也请查阅本文。

在继续之前，我建议在页面上添加一个 HTML 按钮。您可以通过保存更新的代码文件并刷新浏览器来查看浏览器中的更改。

## **状态及部件**

组件是反应的[基本构建模块](https://www.geeksforgeeks.org/reactjs-components/)。UX 是一套组件。(我第一次选择了[类组件](https://www.w3schools.com/react/react_class.asp)。稍后，我将使用功能组件和钩子来重构这个，但是旧的类组件在说明生命周期方法方面做得很好，并且在继续之前，确实有助于在 React 概念中进行训练。)

### **什么是国家？**

简单地说，state 是一个 JavaScript 对象[，它保存着你想在你的网站上显示的数据](https://www.geeksforgeeks.org/reactjs-state-react/)。在类组件中，状态是用构造函数设置的。在我们的报告中， [App.js](https://github.com/JessicaWachtel/React-To-Do-List-Tutorial/blob/main/App.js) 文件是状态所在的位置。该组件中的第 6-8 行和第 10-11 行是标准的类内组件状态，但是该状态中的内容因应用程序而异。

对于我们的示例，有一个简单的任务数组。当我们继续前进时，这将变成一个空的对象，因为我们将通过浏览器侧的文本输入框动态添加删除状态。

请注意 *App.js* 与*base cap . js*之间的差异。BasicApp.js 很简单，没有任何真正的功能。这一页旨在介绍 JSX，不会被用来向前推进。

### **部件是如何工作的？**

查看 *App.js* 中的第 17 行。尽管这一页仍然很简单，但它展示了一种方式——从父母到孩子。

在这个实例中， *App.js* 是父节点， *TaskComponent.js* 是子节点。我们将状态从父级传递到子级的方式是在组件上命名它，然后将它放在花括号中，让 React 知道期待 JavaScript，并按照命名约定命名它，就像对其他任何东西一样。 *this.state* 是对象的名字，然后 tasks 是键，我们引用的是值。看一下 TaskComponent.js 页面，您可以看到具体的元素是如何被引用的。

在 *index.js* 中，注释掉 *< BasicApp >* 和 *BasicApp* 导入，取消注释 *< App >* 和 App 导入，就可以看到

React 的单向数据流是其主要特点之一。如果你想了解更多，这里有一篇很棒的文章。

## **接下来的步骤**

基本都涵盖了！您有一个工作文件树和组件。在接下来的一周里，您能做些什么来更熟悉将 React 组件呈现到 DOM 中呢？你怎么能操纵国家？你能映射一个对象或添加另一个组件吗？

下周，我们将添加[一个文本输入框并通过网页](https://thenewstack.io/learn-react-add-event-functionality-to-a-component/)操纵状态，添加可点击的功能，并学习生命周期方法。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>