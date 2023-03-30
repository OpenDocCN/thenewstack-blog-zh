# 为什么 Ansible 和 ONTAP 值得关注存储

> 原文：<https://thenewstack.io/why-ansible-and-ontap-deserve-a-look-for-storage/>

[](https://www.linkedin.com/in/david-blackwell-ba03879/)

 [戴维·布莱克维尔

大卫是一名拥有 20 年经验的 IT 老手，致力于通过 OpenStack 容器和配置管理工具简化 NetApp 资源的采用。当不在家工作或摆弄新软件时，大卫把大部分空闲时间都花在他四岁的儿子和他可爱的妻子身上。](https://www.linkedin.com/in/david-blackwell-ba03879/) [](https://www.linkedin.com/in/david-blackwell-ba03879/)

Ansible 是一款开源软件供应、配置管理和应用部署工具。几年前，Ansible(归 Red Hat 所有)与 NetApp 合作创建开源模块，用于 NetApp 系统，尤其是其旗舰操作系统 [ONTAP](https://www.netapp.com/us/products/data-management-software/ontap.aspx) 。自合作开始以来，NetApp 已经免费创建了超过 75 个模块，基础架构管理从未如此简单。

然而，有时，如果您单独运行多个模块，而不是在所谓的剧本中组合在一起，事情会变得复杂。顾名思义，剧本就是代码如何以协调的方式执行模块。一般来说，模块的制作者“负责”构建剧本，但是那些供应商可能没有时间或者没有兴趣创建他们自己的剧本。

幸运的是，Ansible 有一个名为“角色”的解决方案可以缓解这个问题。一个可行的角色是剧本、模板和变量的集合，可以由最终用户硬编码。在本帖中，我们将讨论为简化 ONTAP 管理而创建的一个可行角色。

## 集群配置

随着 Ansible 2.8 的发布，对一些模块的更改允许优化角色创建，并被合并到 GitHub for Ansible 上。在这个角色中，以下是可能的情况:

*   应用许可证代码。
*   分配磁盘所有权。
*   创建聚合。
*   设置 SNMP。
*   设置 DNS。
*   设置 MOTD 登录消息。
*   设置 NTP。
*   修改端口 MTU。
*   创建接口组。
*   修改广播域。
*   创建 VLANs。
*   为 SnapMirror 创建集群间 LIFS。

NetApp 保留我们在 GitHub 上生成的所有角色。使用 NetApp 角色非常简单。要为角色准备 Ansible 系统，您需要确保您有一个/etc/ansible 目录:

接下来，使用 Git 将模块下载到/etc/ansible 目录下的 content 文件夹中。

```
# git clone <a href="https://github.com/netapp/ansible.git">https://github.com/netapp/ansible.git</a> /etc/ansible/content

```

这些命令将在/etc/ansible 中创建一个内容文件夹，并允许在角色更新时进行访问:角色被释放或被更新:

```
# cd /etc/ansible/content
# git pull

```

还有最后一步，让在行动手册中使用这些角色变得毫无压力。首先在/etc/ansible 中为 Ansible 创建或修改一个配置文件。您将使用该文件告诉 Ansible 这些角色在哪里，以便您可以在行动手册中使用它们的简称。

```
# vi /etc/ansible/ansible.cfg

```

现在您已经完成了设置，使用该角色来配置 ONTAP 集群很容易。

首先，您需要一本剧本来称呼这个角色:

```
-  hosts:  localhost
  gather_facts:  no
  vars:
    input:  &amp;input
      hostname:  "{{ netapp_hostname }}"
      username:  "{{ netapp_username }}"
      password:  "{{ netapp_password }}"
    file:  globals.yml
  vars_files:
    -  "{{ file }}"
  tasks:
  -  name:  Get Ontapi version
    na_ontap_gather_facts:
      state:  info
      &lt;&lt;:  *input
      https:  true
      ontapi:  32
      validate_certs:  false
  -  import_Role:
      name:  na_ontap_cluster_config
    vars:
      &lt;&lt;:  *input

```

剧本要么读入同一个目录中名为 globals.yml 的文件，要么您可以为 file 指定一个额外的变量，以在每次运行的基础上指定使用哪个文件。该行动手册还使用 gather_facts 模块来查找 ONTAP 的版本，以便在该版本的 API 中运行的所有任务都能实现最高效率。此角色中的任务需要来自 gather_facts 模块的信息，因此不能将其排除在外。您要使用的配置设置的所有信息都是从文件中传递的中读取的。您可以为每个集群读入一个文件，也可以只为一个集群读入一个具有默认值(如 MOTD、DNS、NTP 和 SNMP)的文件，只需在 vars_files 部分指定两个变量文件。

这只是将工作负载压缩成可管理格式的众多角色之一。总是会创建新的角色，如 Vservers、NAS 和 SAN 卷(共享、导出、LUN)以及用于创建 SnapMirror 关系的角色，包括验证对等设置。这凸显了 NetApp 参与和支持开源社区的价值。NetApp 希望将 ONTAP 的使用流程简化到难以使用其他工具的程度。

这种奉献精神在 NetApp Slack 工作空间中一直发挥着作用。在#configurationmgmt 渠道中加入其他使用 Ansible 的开发人员。简单性、自动化和编排的自由比您想象的更容易实现。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>