# 在 Flatcar Container Linux 上自动安装 K3s 集群

> 原文：<https://thenewstack.io/automate-k3s-cluster-installation-on-flatcar-container-linux/>

本教程是运行 Flatcar 容器 Linux 系列的第四部分，也是最后一部分。 *( [第一部分](https://thenewstack.io/flatcar-container-linux-the-ideal-os-for-running-kubernetes-at-the-edge/))，([第二部分](https://thenewstack.io/tutorial-explore-container-runtimes-with-flatcar-container-linux/))。([第三部分](https://thenewstack.io/tutorial-install-flatcar-container-linux-on-remote-bare-metal-servers/))。*

在本教程中，我们将安装一个高度可用的 [K3s](https://k3s.io/) 集群以及 [Flatcar Container Linux](https://www.flatcar-linux.org/) 。K3s 是一个精简的 Kubernetes 发行版，专为边缘计算部署而设计。

要完成本教程，您需要熟悉将 Flatcar Linux 放在远程裸机服务器上的[安装过程](https://www.flatcar-linux.org/)。我们扩展了这个场景，使 K3s 和操作系统的安装自动化。

### 利用点火来配置 K3s 安装

让我们快速回顾一下 Flatcar Container Linux 的裸机安装过程。

我们借助两个点火文件来配置操作系统。Ignition 是一个专门为集装箱操作系统(如平板车集装箱)设计的供应工具。第一个文件在 PXE 启动安装过程中运行，该过程通过下载第二个点火文件并将其保存到磁盘来结束。

```
systemd:
  units:
    -  name:  installer.service
      enabled:  true
      contents:  |
        [Unit]
        Requires=network-online.target
        After=network-online.target
        [Service]
        Type=forking
        TimeoutStartSec=600
        RemainAfterExit=yes
        ExecStart=/usr/bin/sh  -c  "flatcar-install -d /dev/sda -i /opt/ignition.json &amp;&amp; udevadm settle &amp;&amp; systemctl reboot"
        [Install]
        WantedBy=multi-user.target
storage:
  files:
    -  path:  /opt/ignition.json
      filesystem:  root
      mode:  777
      contents:
        remote:
          url:  http://10.0.0.5:8080/node-1-ignite-boot.ign

```

存储为`/opt/ignition.yaml`的持久点火文件`node-1-ignite-boot.ign`在引导期间用于配置操作系统。它配置用户、主机名、NTP 服务器和其他设置。

```
passwd:
  users:
    -  name:  core
      ssh_authorized_keys:
        -  ssh-rsa AAAAB3NzaC1yc2EAAAADAQABAAABAQDGdByTgSVHq...
storage:
  files:
    -  path:  /etc/hostname
      filesystem:  root
      mode:  0644      
      contents:
        inline:  node-1  

```

我们还可以在这个文件中包含 systemd 单元文件，这些文件可能会在引导过程中运行。我们将利用这一点来安装 K3s。

### 在第一个节点上安装 K3s 服务器

K3s 的典型安装包括运行下面的命令，该命令首先下载一个脚本，然后通过管道将输出发送到 shell。

```
curl  -sfL https://get.k3s.io | sh -

```

我们将把这一步转换成一个 systemd 单元文件，它将在引导时运行。为了避免重新安装 K3s，我们将检查`/opt/bin/k3s`是否存在，如果存在的话就跳过这个过程。

在网关服务器上，修改`node-1-ignite-boot.yaml`文件添加 K3s 安装过程。

```
systemd:
  units:
    -  name:  k3s-install.service
      enabled:  true 
      contents:  |
        [Unit]
        Description=Run K3s script
        Wants  =  network-online.target
        After  =  network.target network-online.target        
        ConditionPathExists=/opt/k3s-install.sh
        ConditionPathExists=!/opt/bin/k3s
        [Service]
        Type=forking
        TimeoutStartSec=180
        RemainAfterExit=yes
        KillMode=process
        Environment="K3S_TOKEN=secret_edgecluster_token"
        Environment="INSTALL_K3S_EXEC=--cluster-init"
        ExecStart=/usr/bin/sh  -c  "/opt/k3s-install.sh"
        [Install]
        WantedBy=multi-user.target        
passwd:
  users:
    -  name:  core
      ssh_authorized_keys:
        -  ssh-rsa AAAAB3NzaC1yc2EAAAADAQABAAABAQDGdByTgSVHq...
storage:
  files:
    -  path:  /etc/hostname
      filesystem:  root
      mode:  0644      
      contents:
        inline:  node-1  
    -  path:  /opt/k3s-install.sh
      filesystem:  root
      mode:  777
      contents:
        remote:
          url:  https://get.k3s.io

```

首先，我们从`https://get.k3s.io`下载 K3s 安装脚本并保存到`/opt/k3s-install.sh`。

`storage`部分下面的代码片段将执行这个步骤。

```
    -  path:  /opt/k3s-install.sh
      filesystem:  root
      mode:  777
      contents:
        remote:
          url:  https://get.k3s.io

```

然后，我们创建一个 systemd 单元文件，该文件在网络服务启动后执行。它检查`/opt/bin/k3s`文件，只有在没有找到文件时才运行下载的安装脚本。

注意，我们通过环境变量传递 K3s 脚本期望的参数。

```
systemd:
  units:
    -  name:  k3s-install.service
      enabled:  true 
      contents:  |
        [Unit]
        Description=Run K3s script
        Wants  =  network-online.target
        After  =  network.target network-online.target        
        ConditionPathExists=/opt/k3s-install.sh
        ConditionPathExists=!/opt/bin/k3s
        [Service]
        Type=forking
        TimeoutStartSec=180
        RemainAfterExit=yes
        KillMode=process
        Environment="K3S_TOKEN=secret_edgecluster_token"
        Environment="INSTALL_K3S_EXEC=--cluster-init"
        ExecStart=/usr/bin/sh  -c  "/opt/k3s-install.sh"
        [Install]
        WantedBy=multi-user.target

```

通过运行配置传输程序将 YAML 文件转换成 JSON。

```
ct  <  node-1-ignite-boot.yaml  >  node-1-ignite-boot.ign

```

继续 PXE 引导过程的剩余部分，安装 Flatcar Linux，然后安装 K3s。

### 在剩余节点上自动安装 K3s 服务器

除了生成引导时点火文件之外，整个安装过程保持不变。

我们需要包含 K3s 配置，以便将节点加入第一台服务器。

以下点火文件用于配置第二个节点:

```
systemd:
  units:
    -  name:  k3s-install.service
      enabled:  true 
      contents:  |
        [Unit]
        Description=Run K3s script
        Wants  =  network-online.target
        After  =  network.target network-online.target        
        ConditionPathExists=/opt/k3s-install.sh
        ConditionPathExists=!/opt/bin/k3s
        [Service]
        Type=forking
        TimeoutStartSec=180
        RemainAfterExit=yes
        KillMode=process
        Environment="K3S_TOKEN=secret_edgecluster_token"
        Environment="INSTALL_K3S_EXEC='--server' 'https://10.0.0.70:6443'"
        ExecStart=/usr/bin/sh  -c  "/opt/k3s-install.sh"
        [Install]
        WantedBy=multi-user.target        
passwd:
  users:
    -  name:  core
      ssh_authorized_keys:
      ssh_authorized_keys:
        -  ssh-rsa AAAAB3NzaC1yc2EAAAADAQABAAABAQDGdByTgSVHq...
storage:
  files:
    -  path:  /etc/hostname
      filesystem:  root
      mode:  0644      
      contents:
        inline:  node-2  
    -  path:  /opt/k3s-install.sh
      filesystem:  root
      mode:  777
      contents:
        remote:
          url:  https://get.k3s.io

```

注意用于配置 K3s 节点的环境变量。

```
Environment="K3S_TOKEN=secret_edgecluster_token"
Environment="INSTALL_K3S_EXEC='--server' 'https://10.0.0.70:6443'"

```

除主机名外，相同的配置适用于集群的第三个节点。

### 最终确定并验证配置

此时，`/var/lib/tftp/ignition`中应该有 6 个点火文件——三个文件用于 PXE 引导每个节点，三个文件用于在每个节点上配置和安装 K3s。

在`/var/lib/tftp/pxelinux.cfg`目录中，确保每个节点都有三个 PXE 引导文件和一个映射到节点 IP 地址的链接。关于这个主题的细节，请参考本教程的前一部分。

确保 PXE 启动服务器正在运行，并重新启动节点。在几分钟内，您将拥有一个完全配置的、高度可用的 K3s 集群，部署在运行 Flatcar Container Linux 的裸机服务器上。

贾纳基拉姆·MSV 的网络研讨会系列“机器智能和现代基础设施(MI2)”提供了涵盖前沿技术的信息丰富、见解深刻的会议。在 [http://mi2.live](http://mi2.live) 注册参加即将举行的 MI2 网络研讨会。

由 [Pascal van de Vendel](https://unsplash.com/@pascalvendel?utm_source=unsplash&utm_medium=referral&utm_content=creditCopyText) 在 [Unsplash](https://unsplash.com/s/photos/railroad-car?utm_source=unsplash&utm_medium=referral&utm_content=creditCopyText) 上拍摄的特征图像。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>