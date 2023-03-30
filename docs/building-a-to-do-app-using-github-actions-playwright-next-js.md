# 使用 GitHub Actions 构建待办事项应用程序

> 原文：<https://thenewstack.io/building-a-to-do-app-using-github-actions-playwright-next-js/>

在本文中，我们将使用 API 和端到端(E2E)测试构建一个全面的“待办事项应用程序”,同时使用一些现代堆栈。它将演示如何通过使用持续集成(CI)管道来构建现代 web 应用程序，并监控 CI 流程，以便在将潜在错误引入生产之前捕捉它们。

这是这个项目中使用的现代堆栈:

*   **Next.js** 用于构建 web 应用的待办 app
*   **剧作家**进行端到端测试
*   **GitHub 行动**建设 CI 管道
*   **CI 和测试监控的预见**

## 该项目的目的

在科技界，快速创建生产应用程序的需求正在快速增长。我们创建这个项目的动机是为开发者社区贡献一个 web 应用的端到端堆栈。我们选择了免费的工具，所以没有人需要付费。

## 预期成果

我们希望以最简单的方式创建一个生产就绪的无服务器示例 web 应用程序。这就是为什么我们选择 Upstash 来创建一个基于 Next.js 的应用程序。

在测试阶段，我们使用了剧作家框架，因为它使得在任何浏览器和平台上工作都非常容易。我们实现了 JUnit，并用它生成了一个测试报告。

对我们来说，决定构建 CI 管道的平台是最不具挑战性的决定之一，因为 GitHub Actions 在这方面做得很好。

最后，我们发现监控我们的测试和 CI 渠道非常具有挑战性。尽管市场上有一些工具，比如用于测试监控的 Allure 和用于 CI 监控的 Meercode，但这些工具最终似乎并不那么有用。我们决定采用 Foresight，因为它为测试和 CI 渠道提供了深度分析。

## 使用 Next.js 设置待办事项应用程序

此项目需要一个 Next.js 应用程序。如果您的系统中已经配置了 Next.js，那么您可以使用它。如果没有，我们建议使用下面的例子。

这个指南是由 Upstash 团队创建的，它非常简洁，易于理解。

## 用剧作家设置测试

运行以下命令并初始化剧作家。快速配置后，您就可以开始了。

`npm init playwright@latest`

 `***   You can either choose JavaScript or TypeScript.
*   Give a name to your tests folder.
*   To run tests on CI, just add a GitHub Actions workflow.

You will have the base Playwright setup after the installation is completed. You will see your test under the tests folder and under the .github folder you will see your GitHub Action `playwright.yml`。

### 创建 E2E 测试

我们希望确保我们的 API 和用户交互正常工作。因此，我们将添加一个 E2E 测试，它将添加一个待办事项并完成它。

在 tests 文件夹下，您应该创建`add.spec.js`文件并粘贴以下代码:

```
// @ts-check
const  {  test,  expect  }  =  require('@playwright/test');

const TODO_ITEMS  =  [
  'buy some cheese',
  'feed the cat',
  'book a doctors appointment'
];

test.beforeEach(async  ({  page  })  =>  {
  await page.goto('https://localhost:3000/');
});

test('add a todo item',  async  ({  page  })  =>  {

  var todoName  =  TODO_ITEMS[0];

  // Text input
  await page.locator('#todo').fill(todoName);
  await page.locator('#todo').press('Enter');

  // Make sure the list only has one todo item.
  await expect(page.locator('.Home_card__2SdtB')).toHaveText([
 todoName
  ]);

});

test('complete a todo item',  async  ({  page  })  =>  {

  var todoName  =  TODO_ITEMS[0];

  // Text input
  await page.click(`.Home_card__2SdtB:has-text("buy some cheese")`);
  // Make sure the list only has one todo item.
  await expect(page.locator('.Home_card__2SdtB')).not.toHaveText([todoName]);
});

```

为了一个接一个地运行我们的测试，在`playwright.config.js`中禁用并行化。

```
  /* Run tests in files in parallel */
  fullyParallel:  false,

```

然后转到`package.json`并添加一个测试脚本。

```
  "test":  "playwright test"

```

您将能够在您的终端和 GitHub 操作中通过`npm run test`命令运行测试。

运行您的测试，检查您的配置到目前为止是否工作正常。

### 创建 JUnit 报告

为了确保我们测试的健康，我们使用测试报告。JUnit reporter 生成一个 JUnit 风格的 XML 报告。这对于确保我们的待办事项网络应用达到可接受的质量水平至关重要。

在`playwright.config.js`文件中添加以下内容:

```
  reporter:  [  ['junit',  {  outputFile:  'results.xml'  }]  ],

```

当您运行您的测试时，会生成一个名为`results.xml`的文件。

测试报告器包括错误日志和出错时的消息。

## GitHub 操作配置

将您的代码推送到 GitHub 库。最初的`playwright.yml`动作将帮助我们在每个提交和拉取请求中运行我们的测试。您的配置应该如下所示:

```
on:
  push:
 branches:  [  main,  master  ]
  pull_request:
 branches:  [  main,  master  ]
jobs:
  test:
 timeout-minutes:  60
 runs-on:  ubuntu-latest
 steps:
 -  uses:  actions/checkout@v2
 -  uses:  actions/setup-node@v2
 with:
 node-version:  '14.x'
 -  name:  Install dependencies
 run:  npm ci
 -  name:  Install Playwright Browsers
 run:  npx playwright install  --with-deps
 -  name:  Run Playwright tests
 run:  npx playwright test
 -  uses:  actions/upload-artifact@v2
 if:  always()
 with:
 name:  playwright-report
 path:  playwright-report/
 retention-days:  30

```

如果您的操作有效，您将能够看到您的工作流程运行。

GitHub Action 可以完美地自动完成您手动完成的工作。不需要自己跑`npm run test`；GitHub Actions 会在你提交新代码的时候自动完成。然而，GitHub Actions 并没有提供足够的关于测试及其性能的信息。当它们失败时，您需要通过在工作流运行细节的日志堆中找到它们来理解。

我们将使用预见来监控我们的测试。它对开源项目是免费的，并且需要一个简单的配置来启动。

## 为监控建立前瞻性

配置预见不到两分钟。你所需要做的就是建立一个帐户，安装 Foresight 的 GitHub 应用程序，并观看你为本教程创建的资源库。

看完这个库之后，您需要更新您的 YAML 文件。您可以删除最后一个步骤，并添加 Foresight 的测试套件。

```
name:  Playwright Tests
on:
  push:
 branches:  [  main,  master  ]
  pull_request:
 branches:  [  main,  master  ]
jobs:
  test:
 timeout-minutes:  60
 runs-on:  ubuntu-latest
 steps:
 -  uses:  actions/checkout@v2
 -  uses:  actions/setup-node@v2
 with:
 node-version:  '14.x'
 -  name:  Install dependencies
 run:  npm ci
 -  name:  Install Playwright Browsers
 run:  npx playwright install  --with-deps
 -  name:  Run Playwright tests
 run:  npx playwright test
 -  name:  Foresight test kit
 if:  success()  ||  failure()
 uses:  runforesight/foresight-test-kit-action@v1
 with:
 api_key:  ${{  secrets.FRS_PROD_API_KEY  }}
 test_format:  JUNIT
 test_framework:  JEST
 test_path:  ./results.xml

```

如您所见，我们通过上面创建的配置输入了格式、框架和路径字段。

此操作将自动将您的测试报告发送给 Foresight，Foresight 将以最用户友好的方式分析您的测试。更新 YAML 后，工作流将自动运行，您将能够看到工作流运行结果。

Foresight UI 类似于 GitHub Actions。它使您能够跟踪您的 CI 工作流步骤，收集所有的指标，并监控和调试您的测试。你可以从它的[文档](https://docs.runforesight.com/)中了解更多关于 Foresight 的信息。

## 总结

就是这样！我们创建这个项目是希望通过展示如何轻松、免费地创建一个生产就绪的 web 应用程序来帮助开发人员社区。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>**`