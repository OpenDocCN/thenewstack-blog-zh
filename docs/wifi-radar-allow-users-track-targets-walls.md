# Wi-Fi 雷达将允许用户通过墙壁追踪目标

> 原文：<https://thenewstack.io/wifi-radar-allow-users-track-targets-walls/>

有进取心的研究人员现在正在利用我们大多数人生活在其中的无处不在的无线电波雾。一个团队创造了无需电池的设备，可以通过这些信号供电，现在执法部门也可以从 Wi-Fi 中获得推动，这种基于 Wi-Fi 的“雷达”可以让他们“看到”厚达 25 厘米(9.8 英寸)的墙壁，即使是石头或混凝土。

## 无源 Wi-Fi 雷达利用多普勒效应

在“IEEE Explore”上发表的一篇[论文](http://ieeexplore.ieee.org/xpl/articleDetails.jsp?arnumber=7179036)中，伦敦大学学院(UCL)的科学家陈庆超、卡尔·伍德布里奇和凯文·切蒂描述了他们所谓的“高多普勒分辨率无源 Wi-Fi 雷达”的实验，这将允许用户跟踪目标的移动，甚至连手势都可以跟踪。

这样的系统在紧急情况下非常有用，甚至可以挽救生命；例如，对于想要揭示和确定罪犯位置的当局来说，罪犯可能躲藏在银行里、被围困在大楼里或劫持人质。当然，像任何工具一样，这项技术也可能被滥用来侵犯人们的隐私。在任何情况下，所需要的只是来自任何常规 Wi-Fi 路由器的被动传输波，或移动电话信号，这些信号会被物体反射并反弹回检测设备。

该系统的工作原理如下:两个多频、软件定义、基于 FPGA 的收发器用于接收来自标准 802.11 Wi-Fi 接入点的信号，该接入点充当“照明器”。一组检测信号用作基线参考组，而另一组信号用于监视。这就是[多普勒效应](https://en.wikipedia.org/wiki/Doppler_effect)出现的原因:由于物体相对于观察点的运动而引起的波频率的任何微小变化都会被比较，以确定目标的实际位置和方向。

## 更多秘密

该系统是对以前以类似方式工作的设备的改进，但同时也会传输指示信号。麻省理工学院 [Wi-Vi](http://people.csail.mit.edu/fadel/wivi/) 的迪娜·卡塔比和法德尔·阿迪布就是一个例子，他们也使用普通的 Wi-Fi 信号来追踪目标。虽然基本概念是合理的，但在监控情况下，这种同时传输可能会给使用正确反监控技术的骗子带来致命的泄露。

实验中使用了两种算法跟踪滤波器，即[扩展卡尔曼滤波器](https://en.wikipedia.org/wiki/Kalman_filter)和[顺序重要性重采样(SIR)粒子滤波器](https://en.wikipedia.org/wiki/Particle_filter#Sequential_importance_resampling_.28SIR.29)，SIR 似乎提供了更高的精确度。根据“[频谱 IEEE](http://spectrum.ieee.org/tech-talk/at-work/test-and-measurement/see-through-walls-by-the-glow-of-your-wifi) ”，研究人员优化了算法的处理参数，如信号积分时间和检测阈值，以便出现目标的彩色“雷达式散点图”。

目前，还没有高分辨率的图像，这将使用户能够明确知道他们的目标是谁或什么，但该团队正在努力改进这项技术，并开发一种能够实现多目标跟踪的应用程序。那么它对 Wi-Fi 的未来意味着什么呢？随着 Wi-Fi 接入和饱和度的增加，移动生态系统无疑将进一步发展此类复杂性和应用，我们可以预计反技术将被开发为逃避监控的一种方式。更多信息请见[频谱 IEEE](http://spectrum.ieee.org/tech-talk/at-work/test-and-measurement/see-through-walls-by-the-glow-of-your-wifi) 。

图片:[伦敦大学学院](http://www.ucl.ac.uk/)。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>