# 将 OpenStack Cinder 部署为独立的存储服务

> 原文：<https://thenewstack.io/deploying-cinder-stand-alone-storage-service/>

我写过几篇关于[使用 OpenStack 块存储项目 Cinder](http://superuser.openstack.org/articles/how-to-use-openstack-cinder-for-docker/) 的帖子，用于涉及独立 Docker 或 Docker Swarm 的项目。Cinder 提供块存储即服务，作为 [OpenStack](https://www.openstack.org/) 的一部分。这些帖子的主要目的是演示如何使用 Cinder 作为 OpenStack 之外的数据块存储服务。

 [约翰·格里菲斯

John 是 NetApp 的首席软件工程师，在 SolidFire，Inc .担任相同的职务。在 SolidFire，John 帮助创建了 OpenStack 中的 Cinder 项目，并担任 OpenStack 和开源技术的技术贡献者。从数据块存储项目开始到 Juno 发布，他一直担任该项目的技术负责人，在过去四年中，他还断断续续地在 OpenStack 技术委员会中占有一个席位。](https://newsroom.netapp.com/blogs/interview-with-john-griffith-what-are-docker-and-containers-all-about/) 

自从我发表这些文章以来，容器的采用一直在快速增长，容器空间中的持久数据继续出现大量活动。如今，存储即服务领域正在发明许多闪亮的新轮子。虽然 NetApp 自己的创新之轮 Cinder 并不闪亮或新颖，事实上，它到处都有一些凹痕和丁丁声，但它是一个值得信赖的真实之轮。最棒的是，这些瑕疵是通过在生产环境中大规模广泛采用而获得的。

一次又一次，人们给我的关于在 Kubernetes 环境中使用 Cinder 的反馈是，OpenStack 太难安装和管理，而不是构建他们自己的存储插件解决方案。

与其争论这种说法是否正确，我想带您从源头上将 Cinder 部署为独立的存储服务，这是一种独立于供应商、平台和消费者的方法。你自己看一看，就可以决定是不是太难处理了。这个旧轮子可能会有所贡献。Kendall Nelson 和我在 5 月份的波士顿 OpenStack 峰会上演示了这个教程，你可以在下面观看完整的演示。

[https://www.youtube.com/embed/Tb12xJgxxp0?feature=oembed](https://www.youtube.com/embed/Tb12xJgxxp0?feature=oembed)

视频

为了让事情变得尽可能简单和容易，Cinder 现在包含了一个 **contrib** 目录和一个名为 **block-box** 的项目[。在 **block-box** 背后的想法是给你做一个超级简单、快速的独立 Cinder 部署所需要的一切。](https://github.com/openstack/cinder/tree/master/contrib/block-box)

通过 **block-box** ，我们将使用 **docker-compose** 在容器中部署 Cinder，同时启用 Cinder 的 **noauth** 选项，从而消除对 OpenStack Keystone 的需求。您还可以很容易地将 Keystone 添加到 compose 文件中，同时添加一个 **init** 脚本来设置端点。为了简单起见，我们将使用许多默认设置和 NoAuth 之类的服务，所以您可能不想在生产中部署它。尽管如此，这仍然是构建您自己的部署的良好基础。

## 准备主机

我们将配置 Cinder 使用 LVM 作为其后端驱动程序。目前 Cinder 中支持 80 多种后端存储设备。当存储设备在外部时，大多数集成都可以工作；Cinder 只是管理它，并通过 API 与之交互。

LVM 驱动程序是 Cinder 的参考实现，有点不同。我们烘焙了所有必要的 LVM 和 [iSCSI 目标](http://iscsitarget.sourceforge.net/)功能，以便在 OpenStack 中将您的 LVM 磁盘用作 SAN 设备。这意味着 LVM 需要一些额外的步骤；如果你没有使用 LVM 或者你有一个 Cinder 支持的外部后端，这就更容易了。不过，我们将通过“硬”的例子。这真的很简单，一旦你理解了它，添加其他后端就是小菜一碟。

因为容器是短暂的，用它们作为存储设备似乎有点违背直觉。实际上，在这种情况下，我们将运行 LVM，然后在 Docker 主机节点上为持久存储创建一个卷组(VG)。然后，我们将让 Cinder-LVM 容器访问主机的 VG 来创建逻辑卷(LV)，附加目标，并共享它们。这样，当容器失效、重启、失效、再重启时，数据仍然是安全的。您只需生成一个新的容器，并从您停止的地方继续。

## 安装 LVM2 和所需的额外部件

首先，我们将在我们的系统上安装 **lvm2** ，然后创建一个卷组供它使用。如果这里没有可用的磁盘，环回设备是测试 LVM 类型东西的绝佳“磁盘”。这里有一个代码片段，您可以使用它在您的节点
上轻松创建一个 **cinder-volumes** VG

```
sudo apt-get install  -y  lvm2 thin-provisioning-tools
sudo modprobe dm_thin_pool

sudo truncate  --size=10G  cinder-volumes.img
# Get next available loop device
LD=$(sudo losetup  -f)
sudo losetup  $LD cinder-volumes.img
sudo sfdisk  $LD  &lt;&lt;  EOF
,,8e,,
EOF
sudo pvcreate  $LD
sudo vgcreate cinder-volumes  $LD

```

如果你想在这台机器上使用 Curl 之外的东西与 Cinder 交互，你需要安装 **cinderclient** 和 **brick** 扩展来进行本地连接。(注意:目前 PyPi 上发布的 **cinderclient** 版本有一个已知问题，它会阻止 noauth 工作，所以从源代码安装。)

```
git clone  <a  href="https://github.com/openstack/python-cinderclient">https://github.com/openstack/python-cinderclient</a>
cd python-cinderclient
sudo pip install  -e  .

sudo pip install python-brick-cinderclient-ext

```

接下来当然需要 Docker 和 docker-compose。如果你还没有的话:

```
curl  -sSL https://get.docker.com/ | sudo sh
sudo usermod  -aG docker  $USERNAME
sudo pip install docker-compose

```

你可能需要重启才能以非 **sudo** 的身份访问 Docker。(我不确定是否有另一种方法可以在全新安装时获得它；如果你碰巧知道一个，请给我一声！)

准备工作的最后一步是克隆 Cinder repo，这样我们就有了合成文件和所有我们需要的各种容器。

```
git clone https://github.com/openstack/cinder
cd contrib/block-box

```

## 构建容器图像

我们将从构建所需的图像开始。这个 Cinder repo 包括一个 makefile 文件，用于构建 Cinder 的 **openstackloci** 图像。makefile 包括用于在平台(Debian、Ubuntu 或 Centos)之间进行选择的变量，还允许您从每个项目中指定要构建映像的分支。我们从源代码开始构建，所以您可以做的事情有很大的灵活性。

您的选择包括从**主**、**稳定** / **xyz** 或**补丁**版本构建。在 **build-args** 选项(用于在构建中指定基本映像)可用之前，您不会想要重命名映像，直到您准备好进行一些修补和定制。(有关映像构建和选项的更多信息，请查看 GitHub 上的[**open stack**/**loci**页面。)](https://github.com/openstack/loci-cinder)

现在，我们只是要构建运行**block-box**(**cinder**和 **cinder-lvm** )所需的图像。我们指定 **block-box** 作为函数的参数，用于生成和获取我们需要的图像。这需要四到五分钟，取决于您的网络连接速度。

```
cd contrib/block-box
make blockbox

```

这将在 **loci-cinder** repo 中的 docker 文件上运行 **docker build** 。我们只是提取最新的 Debian 基础映像，安装 Cinder source，然后将运行 LVM 和 LVM **c-vol** 服务所需的东西分层放入一个 **cinder-lvm** 映像中。几分钟后。你应该会看到几张 **openstackloci** 图片:

```
$  docker images
REPOSITORY                   TAG                 IMAGE ID             CREATED              SIZE
openstackloci/cinder-lvm   debian             a6d98d742488      About an hour ago    295  MB
openstackloci/cinder          debian             946aa4ae7fac       About an hour ago    256  MB

```

## 部署

一旦我们建立了我们的图像，我们就可以开始了。**块盒**目录应该有你需要的所有东西，默认设置应该有效，这样你就不会弄乱任何东西。当然，您可以稍后返回并修改内容以适应您的需要，但现在只需启动它:

就是这样！您刚刚使用 LVM 参考实现部署了独立的 Cinder。我们甚至包括了一个 **cinder.rc** 文件，你可以从中获取资源，并使用它运行一些命令。如果你想做类似本地附加的事情，你需要安装 **cinderclient** 和与之配套的 **os-brick** 扩展。如果你感兴趣，在**模块盒**目录中的自述文件有更多信息。

正如我们提到的，你可以很容易地修改它，使用你自己的外部驱动程序，比如 Ceph 或 SolidFire，或者任何一个由 Cinder 支持的 80 多个后端设备。记得适当调整**etc-cinder**/**cinder . conf**文件就行了。如果您需要任何额外的包，您需要自己将它们安装到映像中。

## 日常使用

此时，您可能希望将其插入 Docker(如果您希望将其插入 Kubernetes，这方面的工作仍在进行中)。现在您有了一个带有**无授权**的 Cinder 部署，因此您可以创建、删除和附加卷。

```
source cinder.rc
cinder create  --name blockbox-vol1  1
sudo  -E  cinder local-attach dcf8a94c-b2c0-43e6-9037-a6d7ca845589

```

您可以在运行容器的节点上运行它，或者在您的部署中的另一个节点上运行它，就像您通常使用 Cinder 一样。它使用 iSCSI 并连接到您运行该命令的机器(记住，您需要安装/配置 **iscsi 启动器**)。之后吹走:

```
sudo  -E  cinder local-detach dcf8a94c-b2c0-43e6-9037-a6d7ca845589
cinder delete dcf8a94c-b2c0-43e6-9037-a6d7ca845589

```

## 添加另一个后端(c-vol)

在这种类型的环境中，我们不做多后端；相反，我们只是添加另一个运行我们想要的后端的容器。我们可以使用附加的合成文件轻松地添加到我们已经创建的基本服务中。

文件**docker-compose-add-vol-service . yml**提供了一个示例附加合成文件，该文件将创建另一个配置为运行 SolidFire 后端的 cinder-volume 服务。启动主合成文件后，运行以下命令:

一旦服务被初始化并且数据库被同步，您可以通过运行这个命令添加另一个后端:

```
shell
docker-compose  -f  ./docker-compose-add-vol-service.yml up  -d

```

注意，网络设置和端口之类的东西在这里很重要！

别忘了，你可以在本文顶部观看我们演示的三分钟视频，如果你对入门有任何问题，可以通过 IRC 上的 **#openstack-cinder** 频道联系我们。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>