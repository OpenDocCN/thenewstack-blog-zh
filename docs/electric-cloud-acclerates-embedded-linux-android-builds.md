# 电云加速嵌入式 Linux，Android 构建

> 原文：<https://thenewstack.io/electric-cloud-acclerates-embedded-linux-android-builds/>

考虑到典型的新车有大约 1 亿[行代码](https://www.visualcapitalist.com/millions-lines-of-code/)，比波音 787 梦想飞机的航空电子设备和在线支持系统的 650 万行代码还多。

一切都在变成一种设备，使用越来越多的代码，然而公司花费在构建上的时间继续限制了创新的时间。

在 devo PS Research and Assessment(DORA)团队最新的[devo PS State](https://electric-cloud.com/blog/2018/09/strategies-for-a-new-economy-accelerate-the-state-of-devops-in-2018/)报告中，Electric Cloud 发现，在表现最好的公司，开发人员只花一半的时间在创新上，其余的时间花在解决问题上。这种哀叹在最近的网络安全管理软件产品调查中也得到了回应。

在其最近的补救措施中，Electric Cloud 在其发布的 ElectricAccelerator 11.0 中增加了对基于 [Yocto 项目](https://www.yoctoproject.org/)、 [Buildroot](https://buildroot.org/) 和 Android 平台的嵌入式 Linux 版本的支持。

它还为 AWS EC2 和 Kubernetes 环境添加了云爆发功能，因此客户可以在需要时快速启动容器和实例，然后关闭它们以控制成本。

“一切都变得聪明了。电子设备公司必须更加敏捷、快速地推向市场，同时降低风险，”电子云产品营销总监蒂姆·约翰逊说。“我们帮助这些组织，让他们每天有更多的时间来试验、测试和提高产品质量。”

电子加速器已经存在了大约十年。这是一个持续集成(CI)构建和测试加速平台，客户包括 Cisco、GE、Samsung 和 Juniper，承诺将构建时间加快 20 倍。

有了 Accelerator，您只需运行一次构建，它就会找出所有的依赖项并解决任何冲突，然后重新构建构建以进行优化，消除冗余工作，并在每个 CI 周期中支持更多的测试。然后，工作会在您指定的内核数量上并行化。

通过一个 [Bitbake](https://github.com/openembedded/bitbake) 构建，它加速了六个命令中的两个:编译和配置。Bitbake 还创建了一个 buildstats 文件，您可以使用 Electric Insights 对其进行分析，这样您就可以提前知道在构建过程中会节省多少时间。

他说:“我们的优势是任何人都可以做嵌入式的东西，因为那些操作系统构建需要很长时间，而且那些 C 和 C++构建是大多数人在那些类型的设备上使用的，我们也可以加快这些速度。”

另一个吸引人的领域是测试加速。

“建造速度非常快，但仍然需要 20 个小时来完成我们所有的测试，”他说。“我们能做点什么吗？是的，我们可以，主要围绕单元测试和静态代码分析。我们可以并行处理大量工作，因此周期只与最长的测试一样长。”

他说，加速构建只使用了一半或四分之一的资源，因为它们得到了更明智的使用。

“我们在半导体、网络和设备领域取得了巨大成功。我们看到汽车、物联网、医疗保健和金融领域越来越成功，”他说。

加速器还增加了对人工智能融合的 Android 9 的支持。它还更新了对 CentOS 7.4 和 7.5 (64 位)、Debian 9 (64 位)和 RHEL 6.10 的支持。

不久前，首席技术官 [Anders Wallgren](https://github.com/awallgren) 在[的新堆栈制造商](https://thenewstack.io/devops-plumbing-last-mile/)播客上参与了关于 DevOps 状态的讨论:

其最新发布的 [ElectricFlow](https://electric-cloud.com/products/electricflow/) 发布和部署工具使组织能够在适合其特定任务的平台内创建基于角色的角色。它之前发布了对[滚动部署](https://thenewstack.io/electric-cloud-automates-rolling-deployments/)的支持。

专题图片:[芬兰航空](https://www.flickr.com/photos/25905127@N00/3535901582/in/photolist-6osqmo-aoopcN-a5JypV-a4azSj-ftK7cJ-HBDYXD-aokyVn-re7Ge1-8gWiis-dbLqnn-8Erwc7-dakGVd-ayYh7m-hKqtfk-9yRmMw-gEQuj7-gLY9DH-aUNVjc-CjpQci-Kym6dx-qwpngz-8KgZi9-qMU4Zt-BHxF3w-yD6y8T-aokgTK-rTEyJK-fcj6n1-83pViP-bsEfEV-9zgnwc-cdynuf-e5Ljph-Heacxs-J55ijp-aw1rZ9-esgejh-rZhEdL-Avdffi-QJvB5a-PyL5hM-MmyFwc-GWirPx-axMmLA-e21McZ-9vzs9s-nGLTYv-egGuH-JXPctr-KfTngB)由 [votredame](https://www.flickr.com/photos/25905127@N00/) 拍摄。根据 CC BY-SA 2.0 获得许可。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>