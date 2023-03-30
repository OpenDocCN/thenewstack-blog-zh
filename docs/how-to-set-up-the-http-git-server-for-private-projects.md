# 如何为私有项目设置 HTTP Git 服务器

> 原文：<https://thenewstack.io/how-to-set-up-the-http-git-server-for-private-projects/>

你是开发商。您参与了许多项目，其中一些是全球合作的项目。这些项目可能托管在 GitHub 或其他大规模版本控制系统上。然而，你的一些项目可能很小或者很私人，以至于你不希望它们被托管在公共存储库上。这些项目可能是专有的，或者仅供内部使用。

对于那些项目，你是怎么做的？

一种可能是 HTTP Git 服务器。这个开源项目使用 NGINX 在局域网(LAN)上提供 Git 存储库。HTTP Git 服务器非常容易设置和管理。

我将带您了解在 Ubuntu 18.04 上安装和配置 HTTP Git 服务器的过程。一旦完成，您将拥有一个局域网上的任何人都可以使用的存储库。

## 你需要什么

为了成功启动并运行 HTTP Git 服务器，您需要以下内容:

*   Ubuntu Server 18.04 的运行实例。
*   拥有 **sudo** 权限的用户。

就是这样。让我们让你的 git repos 开始运行。

## 更新和升级

你要做的第一件事是更新和升级你的 Ubuntu 服务器实例。但是，请记住，如果内核在此过程中升级，您将需要重新启动服务器。因此，请确保在可能重启时运行更新/升级。

登录到您的 Ubuntu 服务器，使用以下命令更新 apt:

`sudo apt-get update`

apt 更新后，使用以下命令升级服务器:

`sudo apt-get upgrade -y`

完成后，重新启动服务器(如有必要)。

## 安装依赖项

您可以用一个命令安装 HTTP Git 服务器所需的一切。回到终端并发出:

`sudo apt-get install nginx git nano fcgiwrap apache2-utils -y`

这就是在您的服务器上安装软件的全部内容。

## 创建一个 Git 目录来存放存储库

安装好所有东西后，使用以下命令创建一个目录来存放我们的 Git 存储库:

`sudo mkdir /var/www/html/git`

使用以下命令赋予该目录适当的所有权:

`sudo chown -R www-data:www-data /var/www/html/git`

## 配置 NGINX

NGINX 现在必须进行配置，以便它知道在服务器上提供存储库。为此，使用以下命令打开默认的 NGINX 站点配置文件:

`sudo nano /etc/nginx/sites-available/default`

查找以下部分:

```
         location  /  {
                 # First attempt to serve request as file, then
                 # as directory, then fall back to displaying a 404.
                 try_files  $uri  $uri/  =404;
         }

```

在该部分下，粘贴以下内容:

```
location  ~  (/.*)  {
    client_max_body_size  0;  # Git pushes can be massive, just to make sure nginx doesn't suddenly cut the connection add this.
    auth_basic  "Git Login";  # Whatever text will do.
    auth_basic_user_file  "/var/www/html/git/htpasswd";
    include  /etc/nginx/fastcgi_params;  # Include the default fastcgi configs
    fastcgi_param SCRIPT_FILENAME  /usr/lib/git-core/git-http-backend;  # Tells fastcgi to pass the request to the git http backend executable
    fastcgi_param GIT_HTTP_EXPORT_ALL  "";
    fastcgi_param GIT_PROJECT_ROOT  /var/www/html/git;  # /var/www/git is the location of all of your git repositories.
    fastcgi_param REMOTE_USER  $remote_user;
    fastcgi_param PATH_INFO  $1;  # Takes the capture group from our location directive and gives git that.
    fastcgi_pass   unix:/var/run/fcgiwrap.socket;  # Pass the request to fastcgi
}

```

保存并关闭文件。

使用以下命令运行 NGINX 配置测试:

`sudo nginx -t`

您应该会看到以下报告:

`nginx: the configuration file /etc/nginx/nginx.conf syntax is oknginx: configuration file /etc/nginx/nginx.conf test is successful`

如果您确实看到了错误，请返回到配置文件，并确保将上述代码粘贴到了正确的部分。

## 创建用户帐户

我们现在需要创建一个可以访问 HTTP Git 服务器的用户。我们将通过 *htpasswd* 命令来实现这一点。我将通过创建用户“jack”来演示。您需要确保创建一个符合您需求的用户。

要创建新用户，请发出以下命令:

`sudo htpasswd -c /var/www/html/git/htpasswd jack`

系统会提示您键入并验证用户的新密码。完成后，用下面的命令重启 NGINX:

`sudo systemctl restart nginx`

## 创建您的第一个存储库

是时候创建您的第一个存储库了。因为我们刚刚创建了用户，jack，我们将坚持使用它。但是，请记住，要使用创建新用户帐户时使用的名称来创建存储库。

要创建新的存储库，使用以下命令切换到 git 目录:

`cd /var/www/html/git`

现在使用以下命令创建存储库:

`sudo mkdir jack.git`

使用以下命令切换到这个新目录:

`cd jack.git`

现在，我们将使用以下命令初始化存储库:

`sudo git --bare init`

接下来，我们想要更新 Git 服务器，这样它就知道这些变化了。发出命令:

`sudo git update-server-info`

使用以下命令更改新存储库的所有权:

`sudo chown -R www-data:www-data .`

使用以下命令更改存储库的权限:

`sudo chmod -R 755 .`

## 连接到存储库

终于到了将桌面连接到存储库的时候了。移动到网络上的另一台机器。如果那台机器没有安装 git，现在就安装。如果机器是 Linux 工作站，您可以使用以下命令之一安装 git(第一个用于基于 Debian 的发行版，第二个用于基于 Red Hat 的发行版):

`sudo apt-get install git -y`

`sudo dnf install git`

我将在一台 Ubuntu Linux 台式机上演示接下来的步骤。如果您使用不同的平台，有些步骤会有所不同。

使用以下命令创建本地存储库:

`mkdir ~/testproject`

使用以下命令切换到新存储库:

`cd ~/testproject`

使用以下命令初始化存储库:

`git init`

使用以下命令添加原点(取自我们的 HTTP Git 服务器):

`git remote add origin http://jack@SERVER_IP/jack.git`

其中 SERVER_IP 是 HTTP Git 服务器托管服务器的 IP 地址。

创建一些测试目录和文件。首先使用以下命令创建目录:

`mkdir test1 test2 test3`

接下来，使用以下命令创建测试文件:

`touch test1/testing1 test2/testing2 test3/testing3`

我们现在可以使用以下命令将这些文件添加到 git 中:

`git add .`

使用以下命令提交更改:

`git commit -a -m "Test directories and files added."`

使用以下命令将所有新内容推送到服务器:

`git push origin master`

## 克隆新存储库

将新的存储库上传到服务器后，转到 LAN 上的另一台机器(安装了 Git 的机器),使用以下命令克隆新的存储库:

`git clone jack@SERVER_IP:/var/www/html/jack.git`

系统将提示您输入您创建的用户密码。认证成功后，git 将克隆存储库，您应该会在当前工作目录中看到一个新目录(在本例中是 jack)。

这就是在 LAN 上建立自己的 Git 存储库服务器的全部内容。HTTP Git Server 对于希望托管自己的存储库的开发人员来说是一个出色的解决方案。尝试一下，看看它是否会让您选择本地 Git 托管。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>