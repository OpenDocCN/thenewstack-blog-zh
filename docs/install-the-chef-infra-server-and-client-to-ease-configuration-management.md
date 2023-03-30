# 安装 Chef Infra 服务器和客户端以简化配置管理

> 原文：<https://thenewstack.io/install-the-chef-infra-server-and-client-to-ease-configuration-management/>

借助 [Chef Infra](https://www.chef.io/products/chef-infra) 配置管理平台，管理员会发现实现大规模的一致配置非常容易。该软件提供了一种简单的方法来配置物理或虚拟机，甚至是基于云的机器。

Chef Infra 被 Cheezburger、Etsy、脸书和 Indiegogo 等公司使用，所以你可以肯定这个工具已经过审查，可以执行。

Chef Infra 的工作原理很简单:安装一台服务器和一台客户机。您可以从客户端创建发送到服务器并由服务器分发的配方。

我们要做的是安装客户端和服务器。我将在服务器的 Ubuntu Server 20.04 上进行演示。您几乎可以在任何台式计算机上安装客户端。当然，我会继续使用 Linux 作为我的客户端(这次是 Ubuntu Desktop 20.04)。

为此，您需要具备以下条件:

*   Ubuntu Server 20.04 的一个实例。
*   Ubuntu Desktop 20.04 的一个实例。
*   拥有 sudo 权限的用户。
*   网络连接。
*   一点时间。

这就是让这个系统启动并运行所需的全部内容。让我们从服务器开始。

## 安装 Chef 基础架构服务器

我们要做的第一件事是安装 Chef Infra 服务器。我们将安装最新的稳定版本，即(在撰写本文时)13.2.0-1。

下载必要的。deb 文件，登录到您的 Ubuntu 服务器并发出命令:

`wget https://packages.chef.io/files/stable/chef-server/13.2.0/ubuntu/18.04/chef-server-core_13.2.0-1_amd64.deb`

文件下载完成后，使用以下命令安装软件包:

`sudo dpkg -i chef-server-core*.deb`

安装完成后，使用以下命令启动服务:

`sudo chef-server-ctl reconfigure`

创建一个新的目录来存放 Chef Infra 所需的安全密钥。使用以下命令执行此操作:

`mkdir ~/.chef`

下一步是创建一个将与 Chef Infra 一起工作的新用户，并为这个新用户创建一个密钥。这可以通过一个命令来完成:

`sudo chef-server-ctl user-create USERNAME FNAME LNAME EMAIL 'PASSWORD' --filename ~/.chef/USERNAME.pem`

其中:

*   用户名是新 chef 用户的用户名。
*   FNAME 是新用户的名字
*   LNAME 是新用户的姓氏。
*   电子邮件是与新用户相关联的电子邮件地址。
*   密码是新 chef 用户的强/唯一密码。

创建新用户后，您需要为 Chef Infra 创建一个组织。此命令会将新创建的用户与您将要创建的组织相关联。用于此目的的命令是:

`sudo chef-server-ctl org-create ORGNAME "ORGFULLNAME" --association_user USERNAME --filename ~/.chef/ORGNAME.pem`

其中 ORGNAME 是新组织的名称，USERNAME 是您刚刚创建的新用户的名称。值得注意的一点是 ORGNAME 必须全部小写。如果试图创建大写或混合大写的组织，将会失败。

信不信由你，这就是服务器安装的全部内容。你已经准备好进入客户端了。

## 安装 Chef 客户端

现在我们继续安装 Chef Infra 客户端。登录到您的客户机，使用以下命令下载必要的安装包:

`wget https://packages.chef.io/files/stable/chef-workstation/20.8.125/ubuntu/20.04/chef-workstation_20.8.125-1_amd64.deb`

使用以下命令安装下载的软件包:

`sudo dpkg -i chef-workstation*.deb`

当软件包安装完成后，就该为 Chef Infra 初始化一个新的存储库了，这个存储库将包含所有的刀具配置。使用以下命令创建一个新目录(和一个隐藏的子目录):

`mkdir -p ~/chef-repo/.chef`

使用以下命令切换到新创建基本目录:

`cd ~/chef-repo`

现在，我们将生成必要的 RSA 密钥，并将它们复制到 Chef Infra 服务器。使用以下命令生成新密钥:

`ssh-keygen -b 4096`

当您的密钥准备好时，使用以下命令将公钥复制到 Chef Infra 服务器:

`ssh-copy-id USER@SERVER`

其中，USER 是生成密钥对的用户名，server 是 Chef Infra server 的 IP 地址。

接下来，您需要将 PEM 文件从 Chef Infra 服务器复制到 Chef Infra 客户端。重新登录到您的 Chef Infra 服务器，发出以下命令:

`scp USER@CLIENTIP:~/.chef/*.pem ~/chef-repo/.chef/`

其中 USER 是生成 PEM 文件的用户名，CLIENTIP 是客户端计算机的 IP 地址。

## 添加版本控制

您需要为 Chef Infra 添加版本控制，这样您就可以更好地跟踪 Chef Infra 食谱的变化。在此之前，使用以下命令在 Chef Infra 客户机上安装 git:

`sudo apt-get install git -y`

安装 git 后，使用以下命令对其进行配置:

`git config --global user.name NAME`

`git config --global user.email EMAIL`

其中 NAME 是您的姓名，EMAIL 是您的电子邮件地址。

添加。chef Infra 客户端上的 Chef 目录，使用命令 gitignore:

`echo ".chef" > ~/chef-repo/.gitignore`

使用以下命令切换到新的存储库:

`cd ~/chef-repo`

使用以下两个命令添加并提交存储库中的文件:

`git add .`

`git commit -m "Initial Chef Commit"`

## 生成食谱并配置刀具

我们现在可以制作我们的第一本食谱了。烹饪书定义了一个场景，并包含支持所述场景所需的所有必要信息。这些信息包括:

*   指定要使用的资源及其应用顺序的配方
*   属性值
*   文件分发
*   模板
*   Chef 的扩展，如自定义资源和库

让我们用以下命令生成一本名为 my_cookbook 的食谱:

`chef generate cookbook my_cookbook`

一旦创建了 cookbook，我们就必须使用以下命令创建一个刀配置文件:

`nano ~/chef-repo/.chef/config.rb`

在该文件中，粘贴以下内容:

```
current_dir  =  File.dirname(__FILE__)
log_level                        :info
log_location                    STDOUT
node_name                        'USER'
client_key                       "USER.pem"
validation_client_name     'ORGNAME-validator'
validation_key                 "ORGNAME-validator.pem"
chef_server_url               'https://SERVER/organizations/ORGNAME'
cache_type                       'BasicFile'
cache_options(  :path  =&gt;  "#{ENV['HOME']}/.chef/checksums"  )
cookbook_path                  ["#{current_dir}/../cookbooks"]

```

其中:

*   用户是生成客户端密钥的用户名。
*   ORGNAME 是您创建的组织名称。
*   SERVER 是 Chef 服务器的主机名或 IP 地址。

保存并关闭文件。

使用以下命令切换到 repo 基本目录:

`cd ~/chef-repo`

我们现在需要从 Chef 服务器获取 SSL 文件。使用以下命令执行此操作:

`knife ssl fetch`

## 引导节点

该过程的最后一步需要在服务器上安装和验证客户端(也称为“引导”)。为此，我们必须首先编辑 Chef Infra 客户机上的 hosts 文件，以便它知道 Chef Infra 服务器在哪里。

在客户端机器上发出命令:

`sudo nano /etc/hosts`

在该文件的底部，为 Chef Infra server 添加一个条目，格式如下:

`SERVER_IP HOSTNAME`

其中，SERVER_IP 是 Chef Infra 服务器的 IP 地址，HOSTNAME 是 Chef Infra 服务器的主机名。

保存并关闭该文件。

使用以下命令切换到客户端上存放刀配置文件的目录:

`cd ~/chef-repo/.chef`

使用以下命令引导节点:

`knife bootstrap SERVER -x USER -P PASSWORD --node-name NODE`

其中:

*   SERVER 是 Chef 服务器的主机名或 IP 地址。
*   用户是您创建的用户。
*   密码是用户的密码。
*   节点是节点的名称。

将服务器与创建 PEM 文件时使用的服务器相匹配非常重要。如果使用了 IP 地址，则必须在引导命令中使用 IP 地址。如果使用了主机名，则必须使用主机名进行引导。

引导完成后，您可以使用命令(在客户端上运行)验证引导是否成功:

`knife client list`

您应该看到 ORG-validator(其中 ORG 是新创建的组织的名称)。

至此，您已经准备好开始创建您的第一本 Chef Infra cookbooks，并使用它们来配置您网络上的任何/所有机器。

通过 Pixabay 的特征图像。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>