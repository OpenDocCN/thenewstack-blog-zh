# 实践:在 Apache OpenWhisk 中创建您的第一个无服务器应用程序

> 原文：<https://thenewstack.io/hands-guide-creating-first-serverless-application-apache-openwhisk/>

来自 IBM 的开源[无服务器](/category/serverless/)平台，OpenWhisk 有两种模式，[托管](https://console.ng.bluemix.net/openwhisk/)和内部部署。开发人员可以很容易地开始使用它来实现事件驱动、松散耦合的功能。IBM 和 Adobe 一起向 [Apache 软件基金会](http://www.apache.org)提交了 OpenWhisk，并作为孵化项目被接受[。](http://incubator.apache.org/projects/openwhisk.html)

上周，我们运行了一个[教程](https://thenewstack.io/openwhisk-open-source-serverless-computing-platform/)来让 OpenWhisk 在 Bluemix 云环境中运行。本文涵盖了在您的本地环境中配置和测试 OpenWhisk 的设置过程和步骤。然后探讨创建动作、触发器和规则的关键概念。在 45 分钟内，您将能够在 OpenWhisk 中编写和部署您的第一个无服务器应用程序。

Apache OpenWhisk 的架构反映了一个现代的、容器化的分布式系统。看到在设计这个第一个开源无服务器平台时如何利用多种技术是很有趣的。

## 在虚拟机中设置、配置和测试 Apache OpenWhisk

让我们首先设置一个流浪者盒子，在 Mac 或 Windows 上运行 Apache OpenWhisk。它包括配置平台和命令行界面(CLI)。

平台的配置简单明了。只需克隆 GitHub repo 并运行一个命令。

```
$  git clone https://github.com/openwhisk/openwhisk.git

$  cd openwhisk/tools/vagrant

$  ./hello

```

根据您的互联网带宽，此过程大约需要 30 分钟才能完成。等到您在屏幕上看到以下输出:

```
wsk action invoke  /whisk.system/utils/echo  -p  message  hello  --blocking  --result

{

   "message":  "hello"

}

```

现在 OpenWhisk 已经启动并运行，让我们继续配置 CLI**wsk**。根据您使用的平台，[从 OpenWhisk 网站下载合适的二进制文件](https://openwhisk.ng.bluemix.net/cli/go/download/)。

在 Mac 或 Linux 上，运行下面的命令将 **wsk** 添加到路径中。

```
$  chmod  +x  ./wsk

$  sudo mv wsk  /usr/local/bin

```

在我们开始在本地机器上使用 CLI 之前，我们需要将它指向[浮动框](https://www.vagrantup.com/)。我们还需要一个令牌来获得 OpenWhisk 的认证。我们可以通过登录流浪者之家来找回它。

从克隆存储库的同一目录运行以下命令。

```
$  cd tools/vagrant

$  vagrant ssh

$  wsk property get  --auth

whisk auth  23bc46b1-71f6-4ed5-8c54-816aa4f8c502:123zO3xZCLrMN6v2BKK1dXYFpXlPkccOFqm12CdAsMgRU4VrNZ9lyGVCGuMDGIwP

$  exit

```

复制上述令牌，并从您的 Mac 上运行以下命令:

```
$  wsk property set  --apihost  192.168.33.13  --namespace guest  --auth  23bc46b1-71f6-4ed5-8c54-816aa4f8c502:123zO3xZCLrMN6v2BKK1dXYFpXlPkccOFqm12CdAsMgRU4VrNZ9lyGVCGuMDGIwP

```

运行 OpenWhisk 的流浪汉箱配置为使用 192.168.33.13 作为静态 IP 地址。

这一步为基于 travel 的 OpenWhisk 设置配置了 CLI。**–API host**开关指向 API 端点，**–名称空间**代表用户名，**–auth**携带唯一令牌。通过切换这些参数，同一个 CLI 可以用于基于 Bluemix 的 OpenWhisk。

要测试设置，请在 Mac 上运行以下命令。

```
$  wsk  -i  namespace list

namespaces

guest

```

上面的输出确认 OpenWhisk 环境已经成功配置。需要开关 **-i** 来访问不安全的端点。我们现在可以继续下一步来创建操作。

## 关键概念和术语

OpenWhisk 处理三个关键组件:触发器、动作和规则。

触发器代表特定的事件，如在数据库中插入新记录、提交源代码库、传感器读数达到特定值。当满足特定条件时，触发器由事件源触发。

动作是开发人员编写的函数，可以通过 HTTP 调用或触发器直接调用。OpenWhisk 支持 JavaScript、Java、Swift，甚至打包成 Docker 容器的任意二进制文件。

规则将操作与触发器相关联。它们充当将代码片段与事件源绑定在一起的粘合剂。一个规则可以将多个触发器与一个操作相关联。

## 创建发送电子邮件的操作

在上一个教程中，我们探讨了如何在 OpenWhisk 中构建第一个返回城市天气信息的操作。虽然这是一个简单的“hello world”样式的示例，但我们现在将构建一个更有用的操作，在特定事件发生时向用户发送电子邮件通知。

这个示例将演示如何使用定制的 [node.js](/tag/node.js/) 包来构建一个函数，并异步调用它。

因为我们使用 [SendGrid](https://sendgrid.com/) 来发送电子邮件，所以我们需要注册并获得一个 API 密匙。使用您的凭据登录后，导航到设置部分并单击 API 密钥。确保在显示 API 密钥时保存它。它仅在第一次创建时显示。

在您的 Mac 上，创建一个文件夹并在其中运行 **npm init** 命令，接受默认值:

```
$  mkdir mailfunc

$  cd mailfunc

$  npm init

```

然后，我们将为 SendGrid 安装我们功能中需要的 npm。

```
$  npm install sendgrid  -save

```

让我们继续创建函数。打开您最喜欢的编辑器并粘贴代码片段。

```
function main(params)  {

   return new Promise(function(resolve,  reject)  {

       if  (!params.from  ||  !params.to  ||  !params.subject  ||  !params.content)  {

           reject("Insufficient number of parameters");

       }

       var helper  =  require('sendgrid').mail

       var sg  =  require('sendgrid')("YOUR_SENDGRID_API_KEY");

       from_email  =  new helper.Email(params.from)

       to_email  =  new helper.Email(params.to)

       subject  =  params.subject

```

```
       content  =  new helper.Content("text/plain",  params.content)

       mail  =  new helper.Mail(from_email,  subject,  to_email,  content)

       var request  =  sg.emptyRequest({

           method:  'POST',

           path:  '/v3/mail/send',

           body:  mail.toJSON()

       });

       sg.API(request,  function(error,  response)  {

```

```
           if  (error)  {

               reject(error);

           }  else  {

               console.log(response.statusCode)

               console.log(response.body)

               console.log(response.headers)

               resolve({

                   msg:  "Message sent!"

```

```
               });

           }

       })

   });

}

exports.main  =  main;

```

该函数接受发送电子邮件所需的各种参数。当我们调用动作时，我们将从触发器传递这些参数。

现在是我们包装和部署功能的时候了。以下命令将把所有依赖项压缩到一个 zip 文件中，并将它们部署到 open whish:

```
$  zip  -r  action.zip *

$  wsk  -i  action create sendmail  --kind nodejs:6  action.zip

ok:  created action sendmail

$  wsk  -i  action list

actions

/guest/sendmail private nodejs:6

```

## 调用操作

sendmail 操作就绪后，让我们继续调用它。首先创建一个新文件夹。

```
$  mkdir  ~/trigger

$  cd  ~/trigger

```

创建一个名为 parameters.json 的文件，其中包含发送电子邮件所需的参数。用适当的值替换占位符。

```
{

 "from":  "FROM_EMAIL_ADDRESS",

 "to"  :  "TO_EMAIL_ADDRESS",

 "subject"  :  "Alert from OpenWhisk",

 "content"  :  "Hello Serverless"

}

```

我们现在可以通过将参数文件传递给函数来调用动作:

```
$  wsk  -i  action invoke  --blocking  --result sendmail  --param-file parameters.json

{

"msg":  "Message sent!"

}

```

如果您看到上面的输出，这表明该函数被成功调用。parameters.json 中提到的收件人将收到一封电子邮件提醒。

**–阻塞**开关强制同步调用该功能。但是当外部事件源触发它时，调用必须是异步的。

让我们看看如何异步调用相同的操作。为此，我们简单地省略了**–阻塞**和—**–结果**开关。

```
$  wsk  -i  action invoke sendmail  --param-file parameters.json

ok:  invoked  /guest/sendmail with id  1671372a9f974b9080e24f3cc5081c2a

```

注意，OpenWhisk 现在已经返回了一个激活 id，可以用来跟踪状态。我们还可以列出与之前调用相关的所有激活。即使是同步调用的函数也会有一个激活 id。

```
$  wsk  -i  activation list

activations

1671372a9f974b9080e24f3cc5081c2a  sendmail

690895452c6c4d719a8dc77301376165  sendmail

```

ID 为 1671372 a9f 974 b 9080 e 24 F3 cc 5081 c2a 的激活反映的是最近的一次。让我们看看激活的结果。

```
$  wsk  -i  activation  result  1671372a9f974b9080e24f3cc5081c2a

{

   "msg":  "Message sent!"

}

```

最后，让我们从 [cURL](https://curl.haxx.se/) 调用相同的动作。

```
$  export TYPE='Content-Type: application/json'

$  export AUTH='Authorization: Basic '`wsk property get  --auth  |  awk  '{printf("%s", $3)}'  |  base64  `

$  export NAMESPACE=guest

$  curl  -k  -s  -X  POST  -d  '{"from": "FROM_EMAIL_ADDRESS", "to": "TO_EMAIL_ADDRESS","subject":"Alert from OpenWhisk","content":"Hello Serverless"}'  -H  "$TYPE"  -H  "$AUTH"  https://192.168.33.13/api/v1/namespaces/$NAMESPACE/actions/sendmail?blocking=true

```

如您所见，这个动作现在可以从任何能够与 REST 端点对话的事件源触发。您可以轻松地将该功能与任何需要以电子邮件形式发送通知的应用程序集成在一起。

在接下来的文章中，我们将探索 Apache OpenWhisk 的架构。敬请期待！

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>