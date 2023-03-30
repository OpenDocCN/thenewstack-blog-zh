# 使用 Raspberry Pi 构建媒体服务器，用于向 Galaxy S5 播放流媒体音乐

> 原文：<https://thenewstack.io/building-a-media-server-with-a-raspberry-pi-for-streaming-music-to-a-galaxy-s5/>

我只想听听我的音乐，看看我从 Linux 笔记本或 Galaxy S5 超级手机上收集的大量照片。我对流媒体视频并不感兴趣，因为我没有太多的视频。观看像网飞这样的在线电影服务对我也没有吸引力。

这个故事概述了我如何使用一个流行的纳米计算平台，组装一个基本系统来传输音乐，并让我无线访问我的照片集。有很多可能性可以让这个项目更进一步，所以请随意以此为起点。

你需要一个 Raspberry Pi 或克隆版，minidlna 媒体服务器，WiFi 连接，外部 USB 磁盘驱动器上的一些内容，WiFi 网络适配器，以及 Android 手机的媒体之家应用程序。

## **设置服务器**

我从一个树莓派克隆开始，被称为[鹰嘴豆板](http://www.solid-run.com/products/hummingboard/)，由[固体运行](http://www.solid-run.com/)。我用的是他们的高端 Hummingboard-i2eX 型号，1 GB 内存，2 个 USB 端口，一个 i.MX6 双处理器，一个有线以太网插座。蜂鸣板也有一个微型 SD 插座，而不是 Pi 的正常 SD 类型配置。我使用了 Debian Linux 的副本，而不是更常见的 Raspbian，因为我在另一个项目中使用过，但没有。这种分布在性能和安装上不会有太大的不同。我假设您有一个基本的 Raspberry Pi 或 Hummingboard，它连接到您的本地网络，可以使用 ssh 从 Linux 笔记本上访问该板。

将大容量外部 USB 驱动器和网络适配器插入蜂鸣板上的两个 USB 端口，并接通电源。

ssh 进入 Hummingboard(在我的例子中，它只是 user: debian，p/w: debian)，用下面的代码替换主板正在使用的 IP 地址。

*rob % ssh-X debian @ 192 . 168 . 1 . 107*

我使用了 [mini-dlna 媒体服务器程序](http://sourceforge.net/projects/minidlna/),因为它很容易设置，而且重量很轻。它的新名字叫 ReadyMedia。我将把它称为 mini-dlna，因为在所有的包管理器中，包括 apt-get，仍然是这样称呼它的。

回到 Hummingboard，用下面的命令行安装 mini-dlna。

*debian% sudo apt-get 安装迷你 dlna*

过一会儿 mini-dlna 会显示它已经安装在小型纳米计算机上。

接下来是连接外部驱动器。在 Hummingboard 上创建一个新的目录用于你的驱动器。我把我的叫做“大磁盘”。

*debian % sudo mkdir/big disk*

接下来，将外部驱动器(可能名为/dev/sda1)挂载到该目录，以便 mini-dlna 可以提供文件。使用 lsblk 命令查找正确的设备。

*debian % sudo mount/dev/sda 1/big disk*

需要编辑名为/ect/minidlna.conf 的配置文件，以告诉 minidlna 音乐和照片的存放位置。

*debian % sudo VI/etc/minid LAN . conf*

向下滚动到“使用不同的容器作为目录树的根”部分。注释掉“root_container=”行并添加以下内容。

root_container=B，/bigdisk

Android UPnP/DLNA 客户端程序，如 MediaHouse，能够从该目录向下搜索，找到音乐、照片、视频等。

查找“您想要扫描的媒体文件的目录的路径”部分，并在这些注释的底部添加以下行。

media_dir=A，/bigdisk/music

media_dir=P，/bigdisk/images

这几行命令 minidlna 扫描目录并索引各种音乐和图像文件，这些文件已经存在于我的外部 USB 驱动器上。

在 minidlna.conf 文件中再往下一点，找到以下内容，并相应地修改这些行。

" #network_interface= "更改为" network_interface=wlan0 "(如果您使用有线以太网端口，您可能会使用 eth0)

" #listening_ip= "更改为" listening_ip=192.168.1.107 "(使用您的网络接口地址)。

" #inotify= "更改为" inotify=是"

" #friendly_name= "更改为" friendly_name=hummingboard "

进行更改后，保存并退出 minidlna.conf 文件。

现在更新迷你 dlna 数据库。

*debian% sudo 服务 minidlna 强制重新加载*

然后，重新启动 minidlna。

*debian% sudo 服务 minidlna 重启*

接下来，我们将在 Galaxy S5 超级手机上安装和配置 MediaHouse。

**在 Galaxy S5 上使用 media house**

去 Play Store 在你的 Galaxy S5 上安装迪瓦卡尔巴蒂亚的 MediaHouse UpnP/DLNA 浏览器。

确保您的 Galaxy 与 minidlna 媒体服务器连接到同一个本地网络，并打开 MediaHouse 应用程序。

您应该会立即看到一个“设备”屏幕和“hummingboard”minidlna 服务器名称。点击名字，它会带你到一个有浏览、电影、播放列表等图标的屏幕。单击浏览。然后你就可以选择是看不同的文件夹或图片，还是听音乐。您保存在外部磁盘驱动器上的图片和图像应该都出现在不同的目录下。

图片很容易查看。只需浏览目录，点击图片即可查看。

音乐也是如此。遍历目录，选择一首歌曲。一个小播放器将会出现，您可以在那里停止、暂停、前进等等。使用后退按钮在目录中向上移动。

如果您没有看到任何文件，您可能需要重新启动 minidlna 服务器。

*debian% sudo 服务 minidlna 重启*

## **下一步是什么**

我只介绍了构建基于 Raspberry Pi 的 DLNA 媒体服务器的基础知识。更进一步的想法可能包括在启动时启动服务器，或者增加上传音乐和照片到机器的功能。其他想法可能是使用固态驱动器或电池供电。将电池与将 WiFi 配置为可随身携带的便携式音乐服务器的接入点相结合。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>