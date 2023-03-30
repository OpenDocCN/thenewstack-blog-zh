# Linux:使用 NVM 管理器管理 Node.js 的多个版本

> 原文：<https://thenewstack.io/linux-manage-multiple-versions-of-node-js-with-the-nvm-manager/>

Node.js 是云原生开发的关键开发工具。因为 [Node.js 非常节省资源](https://thenewstack.io/node-js-14-arrives-with-diagnostic-reporting-local-storage/)和高性能，所以它非常适合需要大规模运行的应用和服务。有了 Node.js，你可以开发 SaaS 应用，比如网飞、优步和 Linkedin 使用的那些应用。

你可能已经知道 Node.js 是什么了。对于那些不了解的人来说，这是一个[开源服务器软件](https://thenewstack.io/open-source-profile-mikeal-rogers-node-js/)，它可以在几乎所有平台上运行。Node.js 是一个异步、事件驱动的 JavaScript 运行时，是构建可伸缩网络应用和服务的理想选择[。Node.js 可以用来创建非常基本的应用程序(比如总是很有趣的“Hello，World”应用程序)到非常复杂的应用程序。](https://thenewstack.io/qa-tracy-hinds-bringing-node-js-people/)

提供 Hello World 应用程序的 Node.js web 服务器示例可能如下所示:

```
const http  =  require('http');
const hostname  =  '127.0.0.1';
const port  =  3000;

const server  =  http.createServer((req,  res)  =&gt;  {
  res.statusCode  =  200;
  res.setHeader('Content-Type',  'text/plain');
  res.end('Hello World');
});

server.listen(port,  hostname,  ()  =&gt;  {
  console.log(`Server running at http://${hostname}:${port}/`);
});

Okay,  so it's not nearly as simple as, say, Python, but it's  also much more flexible,  powerful,  and usable in  a  cloud-native world.

```

然而，在你使用 Node.js 的职业生涯中，有一个问题你可能最终会遇到……那就是必须使用不止一个版本的 Node。为什么这是一个问题？有时，您可能需要构建一个与 Node.js 的旧版本一起工作的应用程序，而其他时候，您可能需要在最近的迭代中找到的新功能。

这可能是一个挑战，因为您的操作系统可能不喜欢安装该语言的多个版本。

幸运的是，有一种方法可以解决这个问题。如果您选择的开发平台是 Linux，您总是可以求助于节点版本管理器(又名 NVM)。有了 NVM，您可以在每个项目的基础上轻松地在 Node.js 的多个版本之间切换，确保您覆盖了所有的基础。

让我向您展示如何在 Linux 上安装 NVM。我将在 Ubuntu Server 22.04 上演示，这意味着您所需要的只是该发行版(或任何基于 Debian 的发行版)的一个运行实例和一个拥有 sudo 特权的用户。您甚至不需要安装 Node.js，因为一旦您安装了 NVM，您就可以处理这项任务。

话虽如此，让我们来看看步骤。

## 更新/升级

在我们安装 NVM 之前，让我们首先确保我们的操作系统(和附带的软件)是最新的。

登录到您的 Linux 实例(可以在裸机或云托管服务上)并使用命令更新 apt:

apt 更新后，使用
运行升级

如果在此过程中升级了内核，您需要重启服务器以使更改生效。

## 安装 NVM

现在，让我们安装 NVM。为此，您首先需要确保使用命令安装两个依赖项:

```
sudo apt-get install curl gnupg2  -y

```

安装完依赖项后，使用命令下载并运行安装程序脚本:

```
curl https://raw.githubusercontent.com/creationix/nvm/master/install.sh | bash

```

安装完成后，注销并再次登录，这样所有需要的东西都会添加到您的。bashrc 文件。重新登录后，使用
激活设置

您现在可以使用命令来验证安装:

你应该会看到这样的东西:

## 如何使用 NVM

既然安装了 NVM，就该使用它了。首先要做的是用命令安装 Node.js 的最新版本:

安装完成后，您应该会在输出中看到类似这样的内容:

```
Computing checksum with sha256sum
Checksums matched!
Now using node v18.10.0  (npm v8.19.2)
Creating default alias:  default  -&gt;  node  (-&gt;  v18.10.0)

```

您现在使用的是 Node.js 的 18.10.0 版本。

让我们安装一个不同的版本。Node.js 的 LTS(长期支持)版本怎么样？这是通过命令完成的:

假设您有一个项目需要一个不是最新版本的 Node.js 版本。首先，您可以使用命令:
找出 Node.js 当前安装的版本

您应该在输出中看到类似这样的内容:

```
-&gt;        v18.10.0
default  -&gt;  node  (-&gt;  v18.10.0)
iojs  -&gt;  N/A  (default)
unstable  -&gt;  N/A  (default)
node  -&gt;  stable  (-&gt;  v18.10.0)  (default)
stable  -&gt;  18.10  (-&gt;  v18.10.0)  (default)
lts/*  -&gt;  lts/gallium  (-&gt;  N/A)
lts/argon  -&gt;  v4.9.1  (-&gt;  N/A)
lts/boron  -&gt;  v6.17.1  (-&gt;  N/A)
lts/carbon  -&gt;  v8.17.0  (-&gt;  N/A)
lts/dubnium  -&gt;  v10.24.1  (-&gt;  N/A)
lts/erbium  -&gt;  v12.22.12  (-&gt;  N/A)
lts/fermium  -&gt;  v14.20.1  (-&gt;  N/A)
lts/gallium  -&gt;  v16.18.0  (-&gt;  N/A)

```

要查看所有可用版本的列表，发出命令:

该命令的输出将列出相当多的版本。假设您有一个项目需要 17.9.1 版本的 Node.js

安装后，您可以使用命令切换到它:

上述命令的输出应该是:

```
Now using node v17.9.1  (npm v8.11.0)

```

好了，现在你可以在你的 Linux 机器上轻松地安装和切换 Node.js 的不同版本了。对于任何需要不同语言版本的开发人员来说，NVM 工具对于您的云原生开发过程绝对是无价的。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>