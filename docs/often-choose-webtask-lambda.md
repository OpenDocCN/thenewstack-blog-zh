# 为什么我经常选择 Webtask 而不是 AWS Lambda

> 原文：<https://thenewstack.io/often-choose-webtask-lambda/>

为 makes Webtask 的开发者)工作的 Ado Kukic 在本文中提供了帮助。

[](http://www.emisonian.com/)

 [乔·艾米森

简历:乔·艾米森是 BuildFax 的创始人兼首席技术官，build fax 是保险和贷款行业唯一的自动化房产状况信息提供商。Joe 在 2008 年推出了基于云的 BuildFax，并为许多其他公司的云发布和迁移提供咨询。Joe 负责监督 BuildFax 的所有技术和产品管理。Joe 毕业于威廉姆斯学院，获得英语和数学学位，并拥有耶鲁法学院的法律学位。在推特上找乔:@JoeEmison。](http://www.emisonian.com/) [](http://www.emisonian.com/)

[无服务器计算](/category/serverless/)是一个软件开发过程，其中应用程序代码从服务器中抽象出来。传统上，开发人员必须至少对他们的基础设施有所了解，才能开发软件。无服务器计算的目标是允许软件的开发，而不需要站起来管理服务器的麻烦。

两种不同的无服务器架构模式正在出现:“功能即服务”和“全服务”架构。前者是“将代码扔给运行它的服务”的更直接的应用，后者是使用基于云的服务来构建应用(例如， [Algolia](https://www.algolia.com/) 、 [Cloudinary](http://cloudinary.com/) 、 [Twilio](https://www.twilio.com/) )，而不是在硬件上编写代码/运行库。

为了这篇文章的目的，我将把我的想法集中在以前的无服务器架构模式，功能即服务(FaaS)上。我认为 FaaS 公正的两个平台是 Auth0 [Webtask](https://webtask.io/) 和 AWS [Lambda](https://aws.amazon.com/lambda/) 。每个人都有不同的方法。

Webtask 是由 [Auth0](https://auth0.com) 创建的，它允许开发人员轻松构建无服务器应用程序和可编程的 webhooks，在应用程序中的某个事件发生后触发。Webtask 平台集成了 Auth0 的授权和认证平台以及许多其他功能，使 Webtask 成为一个完整的无服务器平台，所有这些都可以通过 HTTP 调用来访问。Webtask 用 Node.js 编写，通过 [Webtask CLI](https://github.com/auth0/wt-cli) 创建。

Lambda 从 [AWS](https://aws.amazon.com/lambda/) 出来，心中有着同样的目标。“运行代码以响应事件”是 Lambda 的口号。Lambda 已经深入整合到 AWS 生态系统中，无论好坏，它可以跨许多不同的语言执行代码，包括 Java、Python 和 node . js。Lambda 更多地可以被视为后端处理平台，而不是纯粹的无服务器平台。Lambda 更喜欢配置而不是代码，需要集成各种 AWS 产品才能正常工作。

## 无服务器计算的案例

如果你曾经在你的应用程序中使用过第三方 API，比如实现 Algolia 进行搜索或者使用 Cloudinary 管理图片上传，那么你实际上已经使用了无服务器计算。这个例子可能有些牵强，但从长远来看，实施第三方 API 不需要了解他们的基础设施、服务器等，您只需要知道如何访问服务器提供的资源。

对于我们的用例，让我们假设我们正在构建一个不需要后端的应用程序。我们可以用谷歌的实时数据库 [Firebase](https://thenewstack.io/google-firebase-trims-middle-tier-faster-app-dev/) 构建一个应用程序，它允许我们构建完全在客户端运行的可扩展应用程序。因此，我们构建了 Firebase 应用程序，但希望使用 [WalkScore API](https://www.walkscore.com/professional/api.php) 让我们的用户看到热门地区的“可步行性”评分。WalkScore 要求我们注册一个帐户并获得一个 API 密钥。这些凭证，我们不想让除了我们之外的任何人接触到。

> Lambda 函数的工作方式与 Webtasks 稍有不同。Lambda 需要更多的配置来启动和运行。

我们可以去为我们的应用程序建立一个完整的后端。配置服务器，构建部署管道，以及设置后端的所有其他有趣的事情。或者我们可以利用一个无服务器的计算提供商，编写代码与 WalkScore API 接口，并在我们的客户端应用程序中访问这些代码。无服务器选项似乎更有吸引力。让我们看看如何在 Webtask 和 Lambda 中实现这一点，并比较两者。

## Webtask 实现

Webtask 充分利用了节点生态系统。要开始使用 Webtask，您需要通过 npm 安装 **wt-cli** 命令行工具。一旦安装了节点和 npm，运行`npm install wt-cli -g`命令在您的机器上全局安装 Webtask CLI。

安装 CLI 后，运行`wt init {email}`命令进行身份验证。注册 Webtask 帐户时，您可以使用电子邮件地址或电话号码。您将收到一封电子邮件或短信，其中包含一个代码，您需要输入该代码来确认您的身份。一旦处理好了，就可以创建 Webtask 了。

创建 Webtask 是通过运行`wt create {name}.js`命令来完成的，其中`name`是您的 Webtask 的名称。Webtask 当前只能在 Node.js 中编写。web task 是一个导出单个函数的 Node.js 模块。下面我们来看看我们的 WalkScore 集成

```
<span style="font-weight: 400;">var request  =  require('request');</span>

<span style="font-weight: 400;">const API_KEY  =  'YOUR-WALKSCORE-API';</span>

<span style="font-weight: 400;">module.exports  =  function(context,  callback){</span>

<span style="font-weight: 400;">   var city  =  context.query.city;</span>

<span style="font-weight: 400;">   switch(city){</span>

<span style="font-weight: 400;">     case  "1":</span>

<span style="font-weight: 400;">       var url  =  'http://api.walkscore.com/score?format=json&amp;address=San%20Francisco&amp;lat=37.774929&amp;lon=-122.419416&amp;wsapikey='  +  API_KEY;</span>

<span style="font-weight: 400;">       break;</span>

<span style="font-weight: 400;">     case  "2":</span>

<span style="font-weight: 400;">       var url  =  'http://api.walkscore.com/score?format=json&amp;address=New%20York&amp;lat=40.712784&amp;lon=-74.005941&amp;wsapikey='  +  API_KEY;</span>

<span style="font-weight: 400;">       break;</span>

<span style="font-weight: 400;">     case  "3":</span>

<span style="font-weight: 400;">       var url  =  'http://api.walkscore.com/score?format=json&amp;address=Seattle&amp;lat=47.606209&amp;lon=-122.332071&amp;wsapikey='  +  API_KEY;</span>

<span style="font-weight: 400;">       break;</span>

<span style="font-weight: 400;">   }</span>

<span style="font-weight: 400;">   if(url){</span>

<span style="font-weight: 400;">     request(url,  function  (error,  response,  body)  {</span>

<span style="font-weight: 400;">         if  (!error  &amp;&amp;  response.statusCode  ==  200)  {</span>

<span style="font-weight: 400;">           body  =  JSON.parse(body);</span>

<span style="font-weight: 400;">           callback(null,  body);</span>

<span style="font-weight: 400;">         }  else  {</span>

<span style="font-weight: 400;">           callback(null,  "Something went wrong!");</span>

<span style="font-weight: 400;">         }</span>

<span style="font-weight: 400;">       })</span>

<span style="font-weight: 400;">     }  else  {</span>

<span style="font-weight: 400;">       callback(null,  "No City Requested");</span>

<span style="font-weight: 400;">   }</span>

<span style="font-weight: 400;">}</span>

```

我们将保存这个文件，并将其命名为 walkscore.js。运行命令`wt create walkscore.js`来创建 Webtask。你会收到一个`https://webtask.it.auth0.com/api/run/{your-email}/{webtask-name}`形式的链接。导航到此链接并添加一个城市参数链接`?city=1`，您将看到预期的结果。

我们的 Webtask 已经建立。我们的 API 密钥是安全隐藏的，在我们的客户端应用程序中，我们可以调用这个 API 来安全地获取数据。

接下来，我们将看看如何用 Lambda 做同样的事情。

## Lambda 实现

Lambda 需要更多的配置来启动和运行。您将需要一个 AWS 帐户来访问 Lambda 服务。

Lambda 函数的工作方式与 Webtasks 稍有不同。我们将使用与 Webtask 实现中相同的代码，但处理问题的方式会有所不同。我们必须在本地构建整个应用程序，将其压缩并上传到 AWS 控制台。像许多 AWS 服务一样，Lambda 函数可以用 [AWS CLI](https://aws.amazon.com/cli/) 创建，但我们将坚持使用 AWS 控制台，因为我们将广泛使用控制台来启动和运行我们的无服务器 Lambda 应用程序。

由于我们的代码并不太复杂，我们可以通过在 walkscore.js 文件所在的目录中运行`npm install request`来简单地在本地安装`request`模块。这将创建一个名为`node_modules`的新文件夹，其中将包含请求模块和所需的任何其他模块。我们需要稍微更新 walkscore.js 代码，以确保我们符合执行 Lambda 函数的进程的期望。看看下面的代码变化:

```
<span style="font-weight: 400;">var request  =  require('request');</span>

<span style="font-weight: 400;">const API_KEY  =  'YOUR-WALKSCORE-API';</span>

<span style="font-weight: 400;">// In the Lambda console, you will need to set the handler that will execute when your Lambda function is called. For our examples the handler will be walkscore.handler.</span>

<span style="font-weight: 400;">exports.handler  =  function(event,  context,  callback){</span>

<span style="font-weight: 400;">   var city  =  event.querystring;</span>

<span style="font-weight: 400;">   switch(city){</span>

<span style="font-weight: 400;">     case  "1":</span>

<span style="font-weight: 400;">       var url  =  'http://api.walkscore.com/score?format=json&amp;address=San%20Francisco&amp;lat=37.774929&amp;lon=-122.419416&amp;wsapikey='  +  API_KEY;</span>

<span style="font-weight: 400;">       break;</span>

<span style="font-weight: 400;">     case  "2":</span>

<span style="font-weight: 400;">       var url  =  'http://api.walkscore.com/score?format=json&amp;address=New%20York&amp;lat=40.712784&amp;lon=-74.005941&amp;wsapikey='  +  API_KEY;</span>

<span style="font-weight: 400;">       break;</span>

<span style="font-weight: 400;">     case  "3":</span>

<span style="font-weight: 400;">       var url  =  'http://api.walkscore.com/score?format=json&amp;address=Seattle&amp;lat=47.606209&amp;lon=-122.332071&amp;wsapikey='  +  API_KEY;</span>

<span style="font-weight: 400;">       break;</span>

<span style="font-weight: 400;">   }</span>

<span style="font-weight: 400;">   if(url){</span>

<span style="font-weight: 400;">     request(url,  function  (error,  response,  body)  {</span>

<span style="font-weight: 400;">         if  (!error  &amp;&amp;  response.statusCode  ==  200)  {</span>

<span style="font-weight: 400;">           body  =  JSON.parse(body);</span>

<span style="font-weight: 400;">           callback(null,  body);</span>

<span style="font-weight: 400;">         }  else  {</span>

<span style="font-weight: 400;">           callback(null,  "Something went wrong!");</span>

<span style="font-weight: 400;">         }</span>

<span style="font-weight: 400;">       })</span>

<span style="font-weight: 400;">     }  else  {</span>

<span style="font-weight: 400;">       callback(null,  "No City Requested");</span>

<span style="font-weight: 400;">   }</span>

<span style="font-weight: 400;">}</span>

```

最后，选择 walkscore.js 文件和 node_modules 目录，并将它们压缩成一个名为‘walk score . zip’的文件`. This is the file we will upload as our Lambda function.`

当我们创建 Webtask 时，我们自动获得了一个 HTTP 端点，我们可以在这里访问 Webtask。使用 Lambda，一旦我们创建了 Lambda 函数，我们就可以选择挂钩到现有的 AWS 服务，或者我们可以使用 AWS API 网关服务来获取 HTTP 端点以访问我们的代码。我们将使用 [API 网关](https://aws.amazon.com/api-gateway/)并创建一个新的 GET 端点。

API Gateway 是一个相当复杂的服务，需要大量现成的配置。我们将创建一个新的 API 端点。在您的 [AWS 控制台](https://console.aws.amazon.com/)中，在您刚刚创建的 Lambda 函数下，导航到 API 端点，然后单击 Add New Endpoint 链接。您可以随意命名您的端点。将端点的方法设置为 GET，并确保选择 Open for Security。对于这个简单的演示，我们不会添加身份验证。一旦创建了端点，单击它，您将被带到 AWS 控制台的 API 网关服务部分。

默认情况下，API Gateway 不允许任何查询参数或数据通过，因此我们需要手动进行配置。导航到您创建的 API 端点，首先我们需要选择方法请求选项，并添加我们想要启用的查询参数。在我们的例子中，我们将只添加一个名为 city 的查询参数。接下来，导航到 Integration Request 部分，这里我们需要添加一个主体映射，它允许我们将查询参数映射到一个数据变量，我们可以在 Lambda 代码中访问该变量。

有很多方法可以解决这个问题，但是为了保持简洁，添加一个应用程序/json 的内容类型，并在设置中粘贴以下代码:

```
<span style="font-weight: 400;">{</span>

<span style="font-weight: 400;">     "querystring":  "$input.params('city')"</span>

<span style="font-weight: 400;">}</span>

```

这将在名为 querystring 的变量中存储 city 参数的值。如果您查看我们的 Lambda 集成代码，您会发现我们从传递给我们的处理程序的事件变量中获取了这些数据:var city = event.querystring`.`

完成所有这些工作后，在 API Gateway 部分部署端点，并导航到新创建的端点。尝试传递不同的查询参数，以确保它正常工作。现在，您已经在 Lambda 中创建了一个简单的无服务器应用程序。

## Webtask 与 Lambda 的深入比较

到目前为止，我们已经了解了如何使用 Webtask 和 Lambda 编写无服务器应用程序。在孤立的场景中，这两个平台非常相似。Lambda 需要跨各种产品进行大量的配置才能启动和运行，而我们的 Webtask 是用一个简单的命令部署的。让我们比较一下他们的生态系统，以便更好地理解这两个平台。

### 身份验证:Auth0 与 IAM 和 Cognito

身份验证是任何应用程序的重要组成部分。无服务器应用也不例外。Webtask 是由 Auth0 构建的，所以很自然，他们通过自己的主要产品 [Auth0](https://auth0.com) 提供认证选项。

Auth0 提供的不仅仅是认证和授权。多因素认证、[无密码](https://auth0.com/passwordless)、一个简单易用的认证部件 [Lock](https://auth0.com/lock) 等等，让你可以开发高度安全的网络任务。Auth0 集成紧密集成到 Webtask 中。 [webtask-tools](https://github.com/auth0/webtask-tools) `node module provides helper function to integrate Auth0 authentication and authorization easily with your serverless project. I won’t go deeply into the different options, but if you are considering Webtask, you can learn about them [here](https://webtask.io/docs/auth).`

另一方面，亚马逊通过他们的[身份&访问管理](https://aws.amazon.com/iam/) (IAM)和[认知到](https://aws.amazon.com/cognito/)服务来支持认证。当创建一个新的 Lambda 函数时，你必须首先给它分配一个 IAM 角色。IAM 角色决定了用户帐户将拥有的权限类型。然后，您必须创建一个 Cognito 用户池并[配置](http://docs.aws.amazon.com/cognito/latest/developerguide/cognito-user-identity-pools.html)它。Cognito 是提供 API 来处理用户认证的服务。最后，您将[在您的应用程序中集成](https://aws.amazon.com/documentation/cognito/)cogn ITO 库，它将处理授权和认证。

与 Webtasks Auth0 集成相比，AWS 方法需要更多的配置。IAM 和 Cognito 服务是更大的 AWS 生态系统的一部分，有时会感觉被附加到 Lambda 上。两者在文档方面的差异也非常惊人。Auth0 文档为如何设置提供了清晰的路径，而 IAM 和 Cognito 需要大量的修补和实验才能正确设置。

### 访问:标准 HTTP 与 API 网关

Webtasks 采用以协议为中心的方法来实现无服务器，HTTP 是您的代码向外界公开的主要方式。当您运行 wt create {webtask}时。js `command to create a new Webtask you will get a URL to access that Webtask. You can use any standard HTTP verb such as GET, POST or PUT to interact with that Webtask and can programmatically edit the behavior based on the request.`

另一方面，Lambda 函数需要通过 API 网关公开，以便可以通过 HTTP 访问。API 网关传统上很难使用。正如我们在上面 Lambda 函数的集成中看到的，API Gateway 提供了 HTTP 协议的一个更窄的视图，并且由于配置选项的数量而陷入困境。由于 Lambda 被深度集成到 AWS 中，它确实有额外的好处，允许在 AWS 生态系统中调用 Lambda 函数，而不需要 API 网关。例如，使用 Cognito 服务，您可以设置不同的 Lambda 函数在用户注册、登录时触发，或者在用户向 S3 上传新文件时调用 Lambda 函数，等等。

### 生态系统:集成和可扩展性

Webtasks 被编写为 Node.js 模块，所以很自然地，您正在编写 JavaScript。如果你愿意，你可以为你的 Webtask 额外编写带有 [edge.js](https://github.com/tjanczuk/edge) 模块的 C#代码。而 Lambda 则支持 Node.js、Python 和 Java。Webtask 旨在让你写代码，不用担心模块的导入和管理。它们本身支持 800 多个模块，所以你只需要模块，你的代码就会运行。如果不支持您需要的模块，您可以自己手动创建一个包。在这里学习如何用 wt create–bundle’命令来做这件事。有了 Lambda，你可以随意使用任何模块，但是你必须在本地编译你的程序，然后上传到 AWS。

可以使用 Webtask CLI 在本地或从远程资源创建 Webtask。Lambda 函数也可以通过 CLI 在本地创建，如果需要多个文件，可以上传为. zip 文件，例如在使用不同节点模块的情况下，如果上传到亚马逊的 S3 服务，也可以访问这些函数。

两个平台都支持多种运行代码的方式。Webtask 支持通过 HTTP 请求直接访问，但也可以设置为作为 Cron 作业定期运行。Lambda 函数可以通过 HTTP 进行类似的调用，但是它与 AWS 生态系统有很深的集成，并且可以基于 AWS 服务提供的许多不同事件来激活。

## 结论

Webtask 是一个完整的产品。Lambda 不是一个完整的东西。它是后端框架的一部分，可以与 AWS RDS 和 DynamoDB 很好地集成。如果你正在寻找建立一个无服务器的应用程序，无论它是一个完整的应用程序还是一个微服务，Webtask 都有一个更好的开发者体验，几乎没有负面影响，除非你使用其他 AWS 服务作为应用程序的一部分。Lambda 在扩大 AWS 生态系统方面有其作用，但与 Webtask 相比，它过于复杂，需要太多其他服务和太多配置，对于大多数无服务器应用程序来说，这不是一个好的默认选择。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>