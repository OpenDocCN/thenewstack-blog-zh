# 什么是码头工人。env 文件以及如何使用它？

> 原文：<https://thenewstack.io/what-is-the-docker-env-file-and-how-do-you-use-it/>

当您部署 [Docker 容器](https://thenewstack.io/how-to-install-docker-on-ubuntu-and-centos/)时，您经常需要添加定制的变量。这些变量可能包括各种信息，包括用户名、密码、数据库名称等。当然，你总是可以将这些变量硬编码到容器清单中，但这被[广泛认为是安全问题](https://thenewstack.io/5-docker-security-best-practices/)。最重要的是，如果您一次又一次地部署类似的容器，重新输入所有这些信息并不十分有效。

为了解决这类问题，大多数开发人员选择使用*。env* 文件。本质上，一个*。env* 文件是为容器部署设置特定变量的密钥对值的列表。因此，不必将这些变量编码到清单本身中，而是将它们添加到。env 文件，当您运行 *docker-compose up -d* 时，这些变量将从*中应用。env* 文件(“env”是*环境变量*的简称)。

这真的很简单。

*。env* 文件可以用于简单的容器部署，甚至复杂的全栈部署。无论哪种方式，这都是使用秘密进行部署的更安全的方式。虽然没有什么是完美的，但是使用隐藏文件(在 Linux 中以.开头的文件被认为是隐藏的)来防止将秘密硬编码到清单中，不应该仅仅被认为是明智的做法，它应该是您的默认做法。是的，还有更安全的方法来处理秘密。

一些需要记住的事情。环境文件:

*   *。env* 文件用于 docker-compose.yml 文件的预处理步骤。
*   从*传递变量。env* 文件添加到命令中，您使用 *$* 作为 *$DB_DATABASE* 。
*   ENV 值可以通过 docker-build 或 run-style 命令获得(如上所述，使用$)。
*   ENV 文件允许您一次传递多个环境变量。
*   你可以通过。使用*–env-file*选项将 env 文件变量添加到 docker run 命令，就像这样:docker run*–env-file。env mysql:最新*

例如，您可以创建一个新的 Docker 密码，如下所示:

首先，用
创建一个包含秘密的文件

```
echo  "this-is-my-secret"  &gt;  $HOME/secret.txt

```

接下来，使用
创建 Docker 秘密

```
docker secret create password-secret  $HOME/secret.txt

```

输出如下:

```
fx0ziezaw0xjpb0i7bt092xmi

```

你可以用命令列出你的秘密:

输出将包含您刚刚创建的秘密，如下所示:

```
fx0ziezaw0xjpb0i7bt092xmi password-secret  48  seconds ago  48  seconds ago

```

然后，您可以在部署这样的服务时使用这个秘密:

```
docker service create  --name test-service  --secret password-secret mysql:latest

```

上面命令的输出看起来会像这样:

```
zcoz2b2xvzakoq1x7jny6l5x5
overall progress:  1  out of  1  tasks
1/1:  running
verify:  Service converged

```

也有第三方服务，如 [HashiCorp Vault](https://www.vaultproject.io/) ，提供可用于存放秘密的加密金库。

但是如果你想简化事情。env 文件是一个很好的方法。最重要的是。env 文件不仅仅是为了保密。有了这个文件，您可以添加任何您需要的环境变量。

让我告诉你如何创建一个。

## 创造你的第一个。环境文件

假设您已经创建了一个目录来存放项目的所有工作文件，名为~/my-project。用命令 *cd ~/my-project* 切换到那个目录。在该目录中，创建。env 文件与命令:

记住了，*。env* 文件必须包含在项目的基目录中，否则，部署命令将不会选择它。

一个很基础的*。env* 文件可能包含以下密钥对:

```
USERNAME=olivia
PASSWORD=b3stp@$$w0rd

```

然而，假设您正在部署一个包含 MySQL 数据库容器的堆栈，您需要设置数据库服务器、数据库端口、数据库名称、数据库用户名和数据库密码。那个*。env* 文件可能如下所示:

```
DB_HOST="127.0.0.1"
DB_PORT="3306"
MYSQL_ROOT_PASSWORD="r00tp@$$w0rd"
DB_USER="dbuser"
DB_PASSWORD="p@$$w0rd"
DB_DATABSE="database"

```

使用[Ctrl]+[X]快捷键保存文件。现在，你的 YAML 文件需要被正确设置。让我们稍微简化一下。说我们的。env 文件看起来像这样:

```
MYSQL_ROOT_PASSWORD="r00tp@$$w0rd"
MYSQL_ALLOW_EMPTY_PASSWORD="p@$$w0rd"
MYSQL_RANDOM_ROOT_PASSWORD="p@$$w0rd"

```

要将这些变量传递给 docker-compose.yml 文件，该文件必须包含如下内容:

```
MYSQL_ROOT_PASSWORD:  ${MYSQL_ROOT_PASSWORD}
MYSQL_ALLOW_EMPTY_PASSWORD:  ${MYSQL_ALLOW_EMPTY_PASSWORD}
MYSQL_RANDOM_ROOT_PASSWORD:   ${MYSQL_RANDOM_ROOT_PASSWORD}

```

当您运行 docker-compose up -d 命令时，环境键值将被传递给部署，事情应该会很好地发展，而不必将这些值保存在 *docker-compose.yml* 文件中。

这也非常方便，因为您可以创建单个。env 文件以重新用于其他部署。在创建复杂的部署时尤其如此。然而，我建议不要将这些文件中的秘密保存在您的本地存储器上。你总是可以创造。要重用的 env 文件，带有密码占位符，如下:

```
MYSQL_ROOT_PASSWORD="ROOT_PWORD"
MYSQL_ALLOW_EMPTY_PASSWORD="PASSWORD"
MYSQL_RANDOM_ROOT_PASSWORD="PASSWORD"

```

你去用那个的时候。env 文件，将其复制到项目的基本目录中，替换实际的密码，保存文件，然后运行您的 *docker-compose* 命令。

当然，没有什么是绝对安全的。如果有东西接触到装有。env 文件，它们所要做的就是在包含。env 文件来验证是否存在环境变量文件，然后使用类似 cat .env 的文件来查看内容。当您处理高度敏感的信息时，最好的办法是使用第三方服务，如前面提到的 HashiCorp Vault。但是对于您的标准 Docker 部署。env 文件是一个很好的方法。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>