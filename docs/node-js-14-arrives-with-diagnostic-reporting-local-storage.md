# Node.js 14 带来了诊断报告、本地存储

> 原文：<https://thenewstack.io/node-js-14-arrives-with-diagnostic-reporting-local-storage/>

每年都有新版本的 [Node.js](https://nodejs.org/en/) 服务器端 JavaScript 运行时引擎[发布](https://github.com/nodejs/Release#release-schedule)，此次发布的版本 14 带来了许多应该会让开发人员兴奋的功能和增强，包括内置的诊断报告和在 web 请求的生命周期中存储数据的能力。

尽管 Node.js 14 直到 2020 年 10 月才会被提示为长期支持状态，但这个版本应该被认为是许多人的必备版本，特别是考虑到 13 版本将于 2020 年 6 月终止。

让我们来看看这个新版本的一些更令人兴奋的特性。

## 诊断报告

诊断报告已经正式作为 Node.js 14 的稳定特性加入[。对于那些不知道的人，诊断报告提供了用户可使用的报告，其中包含用于在生产环境中调试和分类问题的信息。诊断报告能够识别生产中几乎所有的 Node.js 应用程序异常，例如:](https://github.com/nodejs/diagnostics/issues)

*   异常终止。
*   性能缓慢。
*   内存泄漏。
*   CPU 使用率高。
*   意外错误。
*   输出不正确。

诊断报告最初作为 npm 模块提供。为了使用该工具，用户必须在 npm 的帮助下安装模块，如下所示:

`npm install node-report`

安装后，您可以通过 API 调用触发报告，例如:

`var nodereport = require('node-report');
nodereport.triggerReport();`

随着 Node.js 的发布，不再需要安装 node-report，因为该功能已内置于 Node.js 中。

现在，可以从您的应用程序中生成以下形式的报告:

`process.report.writeReport('./filename.json');`

您也可以从命令行生成报告，如下所示:

`node --report-uncaught-exception --report-on-signal --report-on-fatalerror app.js`

您可以使用其他选项生成报告，例如:

*   *–report-on-fatal error*触发生成关于致命错误(如内存不足)的报告。
*   *–report-compact 以单行 JSON 格式生成*报告。
*   *–报告目录*定义存放生成报告的位置。
*   *–报告文件名*要生成的报告的名称。
*   *–报告信号*设置报告生成的信号(如 SIGUSR2)。Windows 不支持此功能。

## 实验性异步本地存储 API

另一个应该让很多开发者点头称赞的特性是增加了实验性的 AsyncLocalStorage API。这个高级 API 将使应用程序更容易达到稳定性，因为它暴露了更少的内部机制。

AsyncLocalStorage 用于在回调和承诺链中创建异步状态，并允许在 web 请求的整个生命周期中存储数据。 **AsyncLocalStorage** 类似于其他语言中的线程本地存储。

尽管您可能会发现其他 npm 模块提供了类似的功能，但是以一种综合的方式使用这些不同的包是具有挑战性的。因此，决定提供一个 API。

## 其他新变化

随着 v14.0.0 的发布，还有一些开发人员应该知道的其他变化。例如:

*   **国际化支持** : Node.js 14 将是第一个默认包含完整 ICU 数据的 LTS 版本。
*   **更简单的模块创建/构建/支持** : Node.js 14 发布了 N-API 版本 6，其中包括对 BigInt 的支持。
*   **V8 升级到 V8 8.1** :新的 V8 JavaScript 引擎带来了重大的性能调整和改进，包括可选链接、Nullish 合并、启用日历和编号系统。
*   **流**:为了提高流 API 之间的一致性，已经做了一些更改。这些更改将有助于消除模糊性，并简化 Node.js 核心中的行为。
*   **实验性 Web 组装系统接口**:对 WASI 进行了更改，以帮助支持某些用例并简化本机模块体验。

另请注意，以下内容已被否决:

*   **crypto** :将没有摘要的 pbkdf2 移至 EOL。
*   **fs** :反对在垃圾收集时关闭 FileHandle。
*   **http** :将 outbound message . prototype . flush 移至 EOL。
*   lib :将全局和根别名移至 EOL。
*   **os** :将 tmpDir()移至 EOL。
*   **src** :删除已弃用的 wasm 类型检查。
*   **stream**:move _ writablestate . buffer 到 EOL。
*   **单据**:弃用 process.mainModule
*   **doc** :弃用不带参数的 process.umask()。
*   **模块**:移除实验模块警告。

## 新系统要求

随着 Node.js 14 的升级，需要注意新的编译器和平台最低要求。比如现在最低的 macOS 目标版本是 10.13(高 Sierra)。对于 Linux，最低 GCC 级别仍然是 6，但是 Node.js 的开发人员正计划为使用 GCC 8 的平台构建和发布二进制文件。最后，Node.js 14 将不能在已经终止的 Windows 版本上运行。

图片由来自 Pixabay 的 Herney Gómez 提供。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>