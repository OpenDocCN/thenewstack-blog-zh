# API 版本控制的技巧

> 原文：<https://thenewstack.io/tricks-api-versioning/>

[](https://twitter.com/subhibeidas?lang=en)

 [苏卜希·贝达斯

苏卜希·贝达斯是希波 API 团队的负责人。API 团队负责开发 API，同时提供出色的开发人员体验。Subhi 拥有伊利诺伊理工学院的计算机工程学位。](https://twitter.com/subhibeidas?lang=en) [](https://twitter.com/subhibeidas?lang=en)

API 是一个契约，用于在特定请求到来时执行特定的服务。改变 API 的行为方式会给 API 用户带来意想不到的连锁反应，因为他们在实现时会花时间围绕 API 的行为来配置软件。就像在现有的管道系统周围改造厨房一样，每次管道需要修理时都要改变厨房的结构，这是一项繁琐且具有破坏性的任务。这可能会扼杀您的 API 的开发，因为需要创建新的功能，但是您不希望因为您更改了管道而破坏您当前客户的东西或让他们破坏他们的厨房。输入 API 版本:允许 API 用户在更新 API 时不中断软件的解决方案。

在 [Shippo](http://goshippo.com/) ，我们考虑了几种 API 版本化的方法。在整个过程中，我们的问题是:

*   它是否使我们能够做出适应短期和长期产品路线图的向后不兼容的 API 更改？
*   我们需要投入多少工程资源来建造这个？
*   每个版本都是可测试的吗？我们能有多确定一个版本中的变化不会无意中影响到其他版本？

以下是我们团队在前进之前考虑的三种方法。

### 1)将请求指向不同版本代码库的代理

就可以完成的事情而言，代理方法是最灵活的，因为您可以在不同版本之间更改 API 的所有内容。你可以实现一个全新的架构或者新的设计。这听起来很神奇，但它确实有一些重大的后勤缺陷。首先，您必须维护指向旧代码库的 API 的静态版本。这意味着保留大量的遗留代码和服务。此外，数据迁移可能会变得非常痛苦和具有挑战性。最后，您可能会以大量代码重复结束，这只是浪费工程资源，不得不在 API 版本之间重新发明轮子。

### 2)带有版本化控制器的路由器

拥有一个带版本化控制器的路由器意味着您将拥有一个共享的模型，并且只改变每个 API 版本的控制器的行为。这使您可以避免代码重复，从而节省时间。这听起来也很诱人，但是也有一个缺点，就是可能会破坏 API 的以前版本。您最终需要健壮和可靠的测试来确保后续版本不会出错。

### 3)共享控制器但具有版本化视图的路由器

这与前一种方法非常相似，但是我们不是对控制器进行版本化，而是对视图进行版本化。您最终会共享更多的资源，因此制作新版本的 API 所需的工作量最少。您不需要进行数据迁移，因为模型是共享的，并且代码重复最少。然而，它仍然有可能破坏以前版本的 API 的缺点。

## 我们的最终决定

我们最终决定采用第三种方法——使用共享控制器但拥有版本化视图的路由器。我们需要能够快速实现的东西，并且不需要用这种方法重写我们的数据模型。它与我们需要进行的所有向后不兼容的变更保持一致。对于我们的 API 的每个新版本，我们只需创建一个新的版本化视图，并将更改交付给我们的用户。我们最近对 API 的更新清理了许多字段，并废弃了不必要的字段。这个过程是无缝的，因为用户可以按照自己的速度升级。

我们知道没有处理 API 版本控制的完美方法，必须做出很多妥协才能使它工作，但是我们已经找到了最适合我们的方法。在 Shippo，我们非常关注确保我们的用户在与我们的 API 交互时有稳定一致的体验。随着更新更好的特性开始出现，吸引用户升级，他们总是可以通过在头文件中指定使用 API 的最新版本来开始实现。一旦他们建成，他们就可以在他们的仪表板上[升级](https://goshippo.com/docs/versioning)。

通过 Pixabay 的特征图像。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>