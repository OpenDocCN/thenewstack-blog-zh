# Angular vs. React:如何选择适合自己的框架

> 原文：<https://thenewstack.io/angular-vs-react-how-to-choose-the-right-framework-for-you/>

当[为你的前端开发项目选择一个 JavaScript 框架](https://thenewstack.io/javascript-developers-on-what-matters-and-whats-next/)时，两个最合适的选项可能是 Angular 和 React，这两个选项都已经确立了自己的重要角色。两者都能够构建非常复杂和直观的界面，但每一个都有独特的功能使其与众不同。

在本文中，我们将讨论这两个开源平台之间的主要优势和差异，为如何为您的下一个项目选择正确的框架提供指导。

## 谁需要使用 JavaScript 框架？

一个 JavaScript 框架被[前端开发人员](https://thenewstack.io/prepping-for-2023-whats-ahead-for-frontend-developers/)用来帮助创建功能性应用，减少编码时间。随着定制应用需求的持续增长，市场上出现了越来越多的选项，包括 Angular 和 React。

这导致了对各种类型开发人员的强烈需求，他们在美国通常可以拿到超过 12.5 万美元的[薪水。](https://www.waveapps.com/freelancing/back-end-web-developer-salary)

## 什么是有角？

Angular 由 Google 软件工程师开发，是一个基于 TypeScript 和 HTML 的开源平台和 web 应用程序框架。它可以用来在手机和网络上创建单页应用程序(spa)。

使用 Angular，HTML 标记可以放在 TypeScript 文件中，有助于简化代码和实现一系列功能，如类型别名和抽象类。下面是一个在类型脚本文件中使用 HTML 标签的例子( [via StackOverflow](https://stackoverflow.com/questions/59628837/adding-html-tag-inside-typescript-file-in-angular) ):

```
import  {Component,  NgModule,  Pipe,  PipeTransform}  from  '@angular/core'
import  {BrowserModule}  from  '@angular/platform-browser'
import  {  FormsModule  }  from  '@angular/forms';

import  {  DomSanitizer  }  from  '@angular/platform-browser'

@Pipe({  name:  'safeHtml'})
export  class  SafeHtmlPipe  implements  PipeTransform  {
  constructor(private sanitized:  DomSanitizer)  {}
  transform(value)  {
    console.log(this.sanitized.bypassSecurityTrustHtml(value))
    return this.sanitized.bypassSecurityTrustHtml(value);
  }
}

@Component({
  selector:  'my-app',
  template:  `<div  [innerHtml]="tooltip('Hello World') | safeHtml">
    </div>`,
  styleUrls:  [  './app.component.css'  ]
})
export  class  AppComponent  {
  name  =  'Angular';
  tooltip(param:  any)  {
        return  `<span>  ${param}  </span>`;
      }
}

```

Angular 的独特之处在于它具有双向数据绑定功能，允许用户更改输入框中的值，以便组件类的属性值自动更新。这意味着当模型中的数据发生变化时，它也会在视图中实时更新和格式化。在此阅读更多关于模型视图的[。](https://www.visual-paradigm.com/guide/uml-unified-modeling-language/what-is-model-view-control-mvc/)

**注意:** Angular 和 AngularJS 不是同一个平台，因为后者完全基于 JavaScript。TypeScript 在许多方面改进了 JavaScript，包括提供项目可伸缩性、语言特性、引用验证、团队协作、改善开发人员体验以及更有效地维护代码的能力。

### 使用角度的好处

角度平台的主要优势包括:

*   Google 为 Angular 提供了长期支持，保证了未来的可扩展性。
*   详细的文档可以为开发人员提供支持。对于任何刚接触应用开发的人来说，在使用 Angular 等平台之前，熟悉一下[各种开发模型](https://www.atlantic.net/dedicated-server-hosting/how-to-adopt-a-devops-development-model-when-you-dont-know-where-to-start/)是很有帮助的。
*   Angular 需要最少的代码来创建应用程序，这导致了极快的开发过程，并有助于在应用程序创建的早期阶段轻松识别任何错误。

## 什么是反应？

React 是由来自脸书的团队开发的 T2，是一个开源的 JavaScript 库，可以用来创建单页面应用程序的界面。该库具有 web 和移动应用视图层，允许开发人员使用一系列隔离的组件构建界面。

React 非常灵活，允许在 web 和移动平台上开发复杂程度不同的应用程序，同时还集成了几个外部库来改进其产品。

与 Angular 不同，React 使用单向数据绑定作为标准；但是，使用平台的 LinkedStateMixin 插件可以实现双向数据绑定。不管有没有这个插件，开发者都不需要重新加载页面来查看任何更改。这是因为 React 不像使用传统数据流的平台那样创建任何额外的文档对象模型(DOM)。

### 使用 React 的好处

*   React 很好学。
*   脸书为该平台提供持续支持。
*   该库是 SEO 友好的，重点是快速渲染速度。
*   React 需要[很少的编码](https://thenewstack.io/low-code-vs-no-code/)。

## 角度与反应:结论

现在，我们已经了解了每个平台的功能以及它们可以实现的目标，让我们来看看有助于确定哪个选项最适合您的主要区别。

### 类似

这两个平台都是开源的，使用基于组件的架构，用于开发 web 和移动界面。其他相似之处包括客户端和服务器端渲染、可比的性能水平以及快速简单的更新。

### 易用性

Angular 是一个更复杂的平台，更适合有经验的开发者。另一方面，React 非常容易学习，对于新开发人员来说更容易使用，利用 JSX 可以轻松地将 JavaScript 和 HTML 结合起来。JSX 是 JavaScript 的语法扩展，允许开发人员使用他们熟悉的语法来构建组件呈现。JSX 在外观上与 HTML 非常相似。

Angular 的学习曲线比 React 的学习曲线陡峭得多。这是因为 React 使用单向数据流，并且有多种方式来执行类似的任务。使用 Angular，开发人员必须学习一种特定的做事方式——例如，像调试这样的任务可能会很复杂。

### 能力

Angular 是一个完整的框架，因此它提供了比 React 更多的特性，React 主要是一个 JavaScript 库。这意味着 React 需要与兼容的框架一起使用，如 [Redux](https://redux.io/) 或 [Atomize](https://atomizecode.com/) ，以提供类似的开发人员体验。

将 React 与像 Atomize 这样的框架结合起来，可以帮助开发人员:

*   轻松更改网格变量和设置小数列大小。
*   在整个应用程序中更新主题。
*   更可控的间距。
*   提高应用程序响应能力的附加控件。
*   还有更多…

### 发展特征

Angular 支持依赖注入(DI ),以提供灵活的测试和调试体验，同时还允许重用类。React 还内置了 DI，使用“道具”和“儿童”实现。

Angular 默认提供双向数据绑定；然而，由于其 LinkedStateMixin 插件，React 也可以用这种方式处理数据。当然，这取决于开发人员的偏好和他们的调试方法。

Angular 使用 NgRx 状态管理库来提供 UI 组件的反应式状态管理，比如文本字段或单选按钮。React 不同，因为每个单独的组件都可以有一个状态。这意味着每个状态都需要单独管理，除非您使用外部状态管理库。

当谈到本地状态管理时，UseState 是 React 最受欢迎的选项之一，允许开发人员在两个值之间切换(通常为真或假)。开发人员通常使用这样的库来对应用程序中的单个元素进行更多的控制。

### 相关工具

与 Angular 相关的工具有:VS 代码、Sublime、Aptana(代码编辑)；茉莉、量角器、羯磨(测试)；Angular CLI(项目设置)；和角度通用(服务器端渲染)。

同时，对于 React 常用的工具有:VS Code、Sublime、Atom(代码编辑)；Jest 和酵素(测试)；创建 React 应用程序(项目设置)；以及 Next.js 框架(服务器端渲染)。

## 那会是什么呢？

Angular 是一个更加全面的平台，但是 React 非常灵活，因为它兼容一系列的库、框架和工具。

虽然 React 提供了一个更容易的学习曲线，但 Angular 更宽泛。一旦开发人员对平台有了透彻的了解，Angular 就可以用来更容易地开发更大规模的项目(与 React 相比)。

React 应该被认为是一个更容易使用的选项，可以帮助新开发人员快速开始创建应用程序，然后有时会转移到更高级、更强大的平台 Angular。最终，决定取决于开发人员的经验和技能水平，以及他们的总体目标。

尽管不是所有的 React 开发人员都转向 Angular，但对于任何需要一个功能更多、特性更丰富的界面来构建大型项目的人来说，这是一条共同的发展道路。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>