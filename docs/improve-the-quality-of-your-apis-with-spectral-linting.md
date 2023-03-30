# 使用光谱林挺提高 API 的质量

> 原文：<https://thenewstack.io/improve-the-quality-of-your-apis-with-spectral-linting/>

Spectral 是 API 的开源林挺工具，特别是那些由 Stoplight 开发的使用 OpenAPI 规范(以前称为 Swagger)和 API 定义描述的工具。它旨在帮助开发人员创建、记录和维护易于使用和理解的 API。

该工具是一个 linter，可用于在 JSON 和 JSON 模式文档上实施规则和标准。通过检查 API 的请求和响应有效载荷的结构和内容，以及 API 文档的结构和内容，如 OpenAPI、 [AsyncAPI](https://thenewstack.io/asyncapi-could-be-the-default-api-format-for-event-driven-architectures/) 或 [RAML (RESTful API 建模语言)](https://raml.org/)文档，Spectral 可用于 lint APIs。

## 林挺如何改进 API

API 林挺在管理 API 方面提供了很多好处，例如:

**一致性:**林挺可以帮助确保您的 API 格式一致，并遵循一套既定的最佳实践，使开发人员更容易理解和使用您的 API，并减少错误和误解的机会。

**可维护性:**林挺可以帮助您识别 API 中的潜在问题，这些问题可能会使将来的维护变得困难。例如，它可以检测不推荐使用或不支持的功能，使您能够在它们成为问题之前解决并修复它们。

**可靠性:**确保你的应用程序接口功能最佳是它成功的关键，这也是林挺的用武之地。它可以帮助您识别和修复性能问题，例如改善 API 的响应时间。简而言之，林挺可以确保你的 API 的可靠性。

**安全性:**使用林挺工具，您可以检测您的 API 中潜在的安全性缺陷，例如缺少[认证和授权](https://thenewstack.io/how-do-authentication-and-authorization-differ/)检查。通过这样做，您可以保护您的 API 和它处理的数据免受可能的风险。

## 深入了解 API

要使用 Spectral 来 lint API，您需要定义一组 linter 应该执行的规则。这些规则可以在配置文件中指定，或者在运行 linter 时作为命令行参数传递。

一旦配置好规则，就可以使用 Spectral 对 API 进行 lint，方法是在相关的 JSON 或 JSON 模式文件上运行 linter，或者在定义 API 的 OpenAPI、AsyncAPI 或 RAML 文档上运行 linter。然后，Spectral 将根据您定义的规则检查文档，并报告它发现的任何违规情况。

例如，您可以使用 Spectral 来确保所有 API 响应都包含一组一致的头，或者所有 API 请求都包含一个必需的参数。您还可以使用它来强制命名约定或强制 API 文档的特定样式。

## 为什么光谱在 API 林挺广受欢迎

Spectral 是一个流行的 API 设计林挺工具，因为它具有可定制性、全面的内置规则、易于集成和社区支持。使用 Spectral，您可以编写自己的定制规则来执行自己的约定和最佳实践。

它的内置规则涵盖了广泛的最佳实践，从安全性和性能到可用性。此外，Spectral 很容易集成到您的开发工作流中，使其成为 CI/CD 管道、代码编辑器和[集成开发环境(ide)](https://thenewstack.io/are-cloud-based-ides-the-future-of-software-engineering/)的理想选择。

由于该项目的开源性质，如果您有任何疑问或问题，您可以从社区获得帮助和支持。

## 使用 Spectral 来定义 API 规范

您可以使用 Spectral 从命令行链接 API 规范。首先，您需要在系统上安装 Spectral。您可以通过运行以下命令使用 npm 安装 Spectral:

```
$  npm install  -g  @stoplight/spectral-cli

```

(让我们假设您使用 npm 作为您的包管理器。)

一旦安装了 Spectral，您就可以使用 spectral lint 命令来 lint 您的 API。该命令的基本语法是:

```
$  spectral lint  [options]  [files]

```

在这个例子中，“文件”是一个或多个 JSON 或 JSON 模式文件的列表，或者是您想要 lint 的 OpenAPI 或 AsyncAPI 或 RAML 文档。

您可以使用各种选项来配置林挺进程。例如，您可以使用`--ruleset`选项来指定一组要使用的特定规则，或者使用`--format`选项来指定林挺结果的输出格式。

一旦您修复了任何林挺错误，您将需要重新运行 Spectral 来验证您的 API 定义通过了林挺过程。应该重复这个过程，直到林挺过程没有任何错误或警告地通过。

为了确保您的 API 定义符合 Spectral 指定的标准，您可能需要相应地编辑 API 定义文件。有关可用选项和光谱 lint 命令的更多信息，请参考[光谱文档。](https://docs.stoplight.io/docs/spectral/674b27b261c3c-overview#-documentation)

## 提升面向事件的 API

在面向事件的 API 的上下文中，谱林挺可用于确保 API 的设计方式使开发人员能够轻松地创建、消费和处理事件。这可能包括为事件应该如何命名、构造和记录，以及 API 应该如何处理它们建立指导方针。

可能在面向事件的 API 的光谱林挺中使用的一些规则示例包括:

*   确保事件有清晰的描述性名称，准确反映其目的和内容。
*   确保事件以易于处理和理解的方式组织。
*   确保事件得到良好记录，清楚描述其目的、结构和任何其他相关信息。
*   建立 API 如何处理事件的指导原则，包括何时触发事件以及如何处理事件。

## 自定义规则和规则集

Spectral 附带了两个规则集:OpenAPI 和 AsyncAPI。但是您可以定制和创建适合您的项目或组织的规则集。这可以帮助您和您的团队创建更好的 API，以及改进 API 设计和 API 开发过程。

有几个内建规则集可用于 Spectral，或者您可以通过使用 Spectral 规则语法定义一组规则来创建自己的自定义规则集。下面是一些`oas`“open API 规范”内置光谱规则集的例子:

**`oas2-recommended` :** 该规则集包括一组使用 OpenAPI 2.0 规范设计和记录 API 的推荐最佳实践。

**`oas3-recommended` :** 这个规则集包括一组使用 OpenAPI 3.0 规范设计和记录 API 的推荐最佳实践。

**`oas3-security` :** 该规则集包括一组规则，用于验证使用 OpenAPI 3.0 规范定义的 API 的安全定义和安全要求。

**`oas3-parameters` :** 该规则集包括一组规则，用于验证使用 OpenAPI 3.0 规范定义的 API 的参数。

要使用光谱规则集，可以在运行光谱时将其指定为选项。例如:

```
$  spectral lint  --ruleset oas3-recommended  /path/to/api.yaml

```

您还可以通过将多个规则集指定为逗号分隔的列表来组合它们。例如:

```
$  spectral lint  --ruleset oas3-recommended,oas3-security  /path/to/api.yaml

```

您还可以使用扩展字段将自定义规则集作为更大规则集的一部分。例如:

```
extends:  oas3-recommended
rules:
-  message:  "Operations must have a summary"
path:  $.paths..operation
operation:  AND
assertions:
-  exists:
path:  $.summary
-  message:  "Parameters must have a description"
path:  $.paths..parameters[*]
operation:  AND
assertions:
-  exists:
path:  $.description

```

这个自定义规则集扩展了`oas3-recommended`规则集，并添加了两个额外的规则。当这个规则集与 Spectral 一起使用时，它将包括来自`oas3-recommended`规则集的所有规则以及在规则字段中定义的两个自定义规则。

还可以在光谱林挺中创建自定义规则集，方法是在单独的配置文件中定义一组规则，然后将该文件包含在主光谱配置文件中。如果您有大量的规则，并且希望将它们组织到单独的文件中以便于管理，这可能会很有用。

## 检测 CI/CD 工作流中的错误

为了使林挺过程更加有效，您可以通过将 Spectral 作为您的构建过程或持续集成管道的一部分自动运行来将它集成到您的工作流程中。

为了确保您的 OpenAPI 规范是最新的，您可以将您的 CI/CD 管道设置为在 Spectral 返回任何错误时失败，或者在出现错误时允许警告但失败。此外，您可以将 Spectral 集成到代码编辑器或 IDE 中，以便在编写 OpenAPI 规范时获得实时反馈。

要使 CI/CD 管道中的光谱林挺检查失败，您需要添加一个步骤来检查光谱林挺命令的退出代码，并在必要时使构建失败。根据您使用的特定 CI/CD 管道，您可能需要使用特定于您的 CI/CD 管道的工具或插件来处理林挺错误，并在必要时使构建失败。

例如，在 Jenkins 管道中，如果存在林挺错误，您可以使用“错误”步骤使构建失败。

总的来说，使 CI/CD 管道中的频谱林挺检查失败的方法将取决于您可用的工具和插件，但关键是找到一种方法来检查退出代码，并在必要时使构建失败。这样，您可以确保您的 OpenAPI 规范在部署之前始终符合标准。

## 建立组织规则

Spectral 中的组织级规则集提供了一种在组织内的多个 API 项目中定义和共享林挺规则的方法。通过使用 rules 键创建配置文件，您可以指定应该启用或禁用哪些规则。

也可以使用 extends 键指定一个基本规则集，然后使用 rules 键覆盖该规则集中的特定规则。这使得在整个组织中保持林挺规则的一致性变得更加容易，确保所有的 API 项目都遵循相同的标准。

例如，以下配置文件定义了一个组织级别的规则集，该规则集扩展了 OAS3 规则集并禁用了“操作-标签-字母顺序”规则:

```
"extends":  "spectral:oas3",
"rules":  {
"operation-tags-alphabetical":  false
}

```

一旦您定义了组织级规则集，您就可以通过向团队成员提供配置文件的副本或将其存储在每个人都可以访问的中心位置来与他们共享。

要使用组织级别的规则集，团队成员可以在林挺他们的 API 项目时将其指定为基本规则集。例如，他们可以将以下内容添加到他们的项目级光谱配置文件中:

```
"extends":  "path/to/organization-rules.yaml"

```

## API 林挺对设计、管理

提高 API 的质量和一致性。通过林挺你的 API 定义，你可以在潜在的问题或不一致变成问题之前抓住它们。这有助于提高 API 的整体质量和一致性。

实施最佳实践和标准。通过在林挺 API 时使用一组规则或标准，您可以确保您的 API 遵循最佳实践并符合行业标准。这有助于使您的 API 更可预测，更易于开发人员使用。

自动化测试和验证。API 林挺可以帮助自动化测试和验证过程，允许您在开发过程的早期发现问题。这可以节省时间和精力，并有助于确保您的 API 为生产做好准备。

提高文档质量。通过林挺你的 API 文档，你可以确保它是准确的、完整的和最新的。

## 结论

对于任何 API 开发者来说，Spectral 都是一个必不可少的工具，因为它有助于确保 API 是安全可靠的，并且它处理的数据是高质量的。它也非常易于使用，可以用来快速识别 API 的任何潜在问题。此外，它还可以用于生成客户端代码和手动测试 API，以确保它的行为符合预期。

总的来说，对于任何希望创建安全、高质量和可靠的 OpenAPI 文档的开发人员来说，Spectral 林挺都是一个非常有价值的工具。这是创建和维护 OpenAPI 文档过程的重要部分，有助于确保 API 的成功。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>