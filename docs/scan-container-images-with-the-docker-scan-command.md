# 使用 docker 扫描命令检查容器图像

> 原文：<https://thenewstack.io/scan-container-images-with-the-docker-scan-command/>

如果你对[集装箱安全](https://thenewstack.io/container-security-a-troubling-tale-but-hope-on-the-horizon/)很认真，那么你知道这一切都始于 beguine…图像。无论您在[投入多少工作来锁定您的部署](https://thenewstack.io/container-security-manage-secrets-with-portainer/)、您的网络和您的基础设施，如果您将您的容器基于有漏洞的映像，这些部署将根本不安全。简单地相信从 Docker Hub 中随机提取的图像就足够了，这是一个很大的错误。

当然，在 [Docker Hub](https://www.docker.com/?utm_content=inline-mention) 上有经过验证的图片，但这些验证对一家公司来说成本相当高，所以不是每张图片都经过验证。虽然你通常可以信任经过验证的图片，但最好直接知道，这种信任是有保证的。

至于未经验证的图片，你试图使用的每一张都会给你带来麻烦。为此，您必须扫描它们的漏洞。如果您发现映像包含漏洞，至少会通知您，并且在某些情况下，您可以通过更新映像中包含的包来缓解漏洞。

幸运的是，有很多工具可以用来扫描这些图像。Docker 内置了一个这样的工具，叫做 [docker scan](https://docs.docker.com/engine/scan/) 。它非常容易使用，并报告了非常简单的信息，任何已知的漏洞，它发现。

让我们看看 docker scan 命令有多容易使用。

## 你需要什么

为此，您只需要一个支持 Docker 的操作系统和一个具有管理员权限的用户。我准备在 Ubuntu Server 22.04 上演示一下。如果您使用不同的平台，您只需要调整安装 Docker 的安装步骤。如果你已经安装并运行了 Docker，你就不用担心安装任何东西了。您还需要一个有效的 Docker Hub 帐户和一个为此创建的访问令牌。

让我们忙起来。

## 安装 Docker 的最新版本

首先要做的是添加必要的 Docker 存储库。为此，您必须使用命令添加官方的 Docker GPG 键:

```
curl  -fsSL https://download.docker.com/linux/ubuntu/gpg | sudo gpg --dearmor -o /usr/share/keyrings/docker-archive-keyring.gpg

```

接下来，添加 Docker 存储库:

```
echo  "deb [arch=amd64 signed-by=/usr/share/keyrings/docker-archive-keyring.gpg] https://download.docker.com/linux/ubuntu $(lsb_release -cs) stable"  |  sudo tee  /etc/apt/sources.list.d/docker.list  &gt;  /dev/null

```

然后，您需要使用命令安装一些依赖项:

```
sudo apt-get install apt-transport-https ca-certificates curl gnupg lsb-release  -y

```

最后，我们可以用这两个命令安装最新版本的 Docker 引擎:

```
sudo apt-get update

sudo apt-get install docker-ce docker-ce-cli containerd.io  -y

```

您可能还想安装 Docker Compose，带有:

```
sudo apt-get install docker-compose  -y

```

最后，使用以下命令确保您的用户是 docker 组的成员:

```
sudo usermod  -aG docker  $USER

```

注销并重新登录以使更改生效。

## 创建 Docker Hub 访问令牌

登录您的 Docker Hub 帐户，点击右上角的用户资料图标。从下拉菜单中，选择帐户设置。在出现的窗口中，单击左侧边栏中的“安全性”,然后单击“新建访问令牌”。将令牌命名为 DOCKER SCAN，授予它读、写、删除权限，然后单击 Generate。

生成令牌后，请确保将其复制到您的计算机剪贴板。

回到终端窗口，您需要使用命令登录 Docker Hub:

出现提示时，键入您的 Docker Hub 用户名，然后将访问令牌粘贴到终端中。按回车键，你应该成功登录。

最后，您需要使用命令:
来接受许可

```
docker scan  --accept-license  --version

```

这将接受许可并打印出您系统上可用的 docker 命令版本。

需要记住的一点是，除非您使用 Snyk 帐户进行身份验证，否则一个月只能扫描 10 次。这样做有一个注意事项，那就是你正在使用的机器必须有一个网络浏览器。因此，如果您在服务器操作系统上工作，必须有一个 GUI，因为身份验证是在 web 浏览器中进行的。

为此，您必须像这样运行 docker scan 命令:

这将为您生成一个链接，单击该链接将打开您的默认网络浏览器。按照提示创建帐户并登录。一旦你完成了，认证就结束了，你就可以开始了。

您现在可以使用 docker 扫描命令。

## 使用 docker 扫描命令

让我们快速浏览一下 nginx:最新图片。为此，发出命令:

Docker 将下载最新的 NGINX 映像并扫描其漏洞。在我的例子中，它报告了以下内容:

```
Testing nginx:latest...
Organization:         xxx-k42
Package manager:     maven
Target file:           /usr/share/java
Project name:         nginx:latest:/usr/share/java
Docker image:         nginx:latest
Licenses:               enabled

✔  Tested nginx:latest for known issues,  no vulnerable paths found.

```

接下来，我使用以下命令测试了一个存在大量漏洞的映像:

docker 扫描信息松弛/dvwa

docker scan 命令拉下测试映像，扫描它的漏洞并得出母负载(1101 个问题)。如果您运行该命令，您会发现如下列出的漏洞:

```
High severity vulnerability found in apt/libapt-pkg4.12
  Description:  Improper Certificate Validation
  Info:  https://security.snyk.io/vuln/SNYK-UBUNTU1404-APT-407425
  Introduced through:  apt/libapt-pkg4.12@1.0.1ubuntu2.10,  apt@1.0.1ubuntu2.10,  apt/libapt-inst1.5@1.0.1ubuntu2.10,  apt/apt-utils@1.0.1ubuntu2.10,  ubuntu-meta/ubuntu-minimal@1.325
  From:  apt/libapt-pkg4.12@1.0.1ubuntu2.10
  From:  apt@1.0.1ubuntu2.10  &gt;  apt/libapt-pkg4.12@1.0.1ubuntu2.10
  From:  apt/libapt-inst1.5@1.0.1ubuntu2.10  &gt;  apt/libapt-pkg4.12@1.0.1ubuntu2.10
  and  7  more...
  Fixed in:  1.0.1ubuntu2.17

```

这就对了。您现在能够轻松地扫描 Docker 图像中的漏洞。如果您运行扫描并遇到许多问题，您可能希望避开您扫描的图像。毕竟，当您使用有漏洞的映像时，您部署的容器也会有漏洞。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>