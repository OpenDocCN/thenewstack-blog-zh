# 英伟达为训练自动驾驶汽车提供了一个数据中心模拟器

> 原文：<https://thenewstack.io/nvidia-offers-a-data-center-simulator-for-training-self-driving-automobiles/>

本月早些时候，一辆优步自动驾驶汽车[在亚利桑那州坦佩市意外撞上了](https://www.nytimes.com/2018/03/19/technology/uber-driverless-fatality.html)，随后撞死了一名过马路的妇女。据报道，这起事故是有史以来第一起行人死于自动驾驶汽车的事故，这在许多人的心中埋下了疑问，即自动驾驶测试在被认为适合上路之前[还有很长的路要走](https://www.nytimes.com/2018/03/23/technology/uber-self-driving-cars-arizona.html)。

尽管如此，汽车制造商和 IT 公司，如谷歌和优步，已经在机器学习驱动的技术上投资了亿美元，希望有一天它最终会被证明比人类司机更安全。自主导航是由机器学习推动的，机器学习需要无数小时的测试数据。但是他们如何在不给民众带来更多伤害的情况下获取这些数据呢？

为此，GPU 制造商英伟达(Nvidia)推出了一种基于云的系统，可以生成大量逼真的模拟图像，可用于存储许多小时的驾驶体验。该公司在本周于加州圣何塞举行的 [GPU 技术大会](https://www.nvidia.com/en-us/gtc/) (GTC)上公布了这项名为 Drive Constellation Simulation System 的技术。

“我们能够在数据中心建立虚拟世界，并行驶数十亿英里来测试自动驾驶汽车算法，”Nvidia 副总裁兼自动驾驶机器总经理 Danny Shapiro 在 GTC 的新闻发布会上说。“本质上，我们运行的是完整的硬件-软件解决方案，通常位于车辆中，但我们已将其移至数据中心。”

Constellation 带来的主要优势是可伸缩性。人们每行驶 10 亿英里就会发生大约 770 起事故，然而大多数自动驾驶研究项目都没有记录这么多英里。英伟达首席执行官黄仁勋在 GTC 的主题演讲中指出，一个由 20 辆车组成的车队每年可以行驶 100 万英里。

英伟达的软件可以让研究人员记录数百万额外的测试里程，而无需在公共道路上测试车辆。它可以不断测试边缘情况，如在日落或雪地中驾驶，这在现实世界中很少发生。模拟软件可以再现各种各样的环境，包括暴雨、暴风雪和眩目的光线。

Constellation 基于英伟达为自动驾驶车辆提供动力的平台，名为 [Drive](https://www.nvidia.com/en-us/self-driving-cars/drive-px/) 。Drive 可以接收来自车辆传感器的多种输入，如车辆的摄像头、超声波传感器、激光雷达和雷达单元，以提供车辆周围环境的表示。另一个组件接收这些数据，并通过使用深度神经网络对对象进行检测和分类来提供安全的前进路径。

Constellation 还包括英伟达的[驾驶模拟软件](https://blogs.nvidia.com/blog/2017/10/26/self-driving-simulation/)，该软件生成这种系统通常会提供的传感数据。该系统基本上是一个闭环反馈回路:Constellation 由两个组件组成，一台服务器上的 Drive 平台从另一台服务器上的 Drive Sim 收集数据，后者用一组 Nvidia GPUs 模拟 Drive 数据。这两个组件以每秒 30 次的速度来回交换数据。

[从](https://waymo.com/)[谷歌自动驾驶汽车项目](https://thenewstack.io/sxsw-googles-self-driving-car-current-limits-ai/)剥离出来的 Alphabet 的子公司 Waymo ，也有类似的想法，通过虚拟测试加强算法，其 [Carcraft](https://www.theatlantic.com/technology/archive/2017/08/inside-waymos-secret-testing-and-simulation-facilities/537648/) 项目。该项目已经通过虚拟环境[记录了 800 万自动驾驶车辆里程](https://www.engadget.com/2017/09/11/waymo-self-driving-car-simulator-intersection/)，利用了该公司 25，000 辆汽车的数据。

Nvidia 的 GPU 天生适合深度学习所需的矩阵处理，它已经成为推进人工智能应用的大力支持者。今年的用户大会——该公司预计将吸引至少 8000 名与会者——将有超过 400 小时的人工智能会议内容。该公司估计，与标准 CPU 相比，采用该公司 [CUDA 库](https://developer.nvidia.com/cuda-zone)的 Nvidia GPU 可以在矢量运算方面提供 20 倍的性能提升。

Drive Constellation 将于今年下半年全面发售。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>