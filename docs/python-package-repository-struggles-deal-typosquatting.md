# Python 包存储库努力应对域名仿冒

> 原文：<https://thenewstack.io/python-package-repository-struggles-deal-typosquatting/>

最近在社区贡献的 Python 组件的主要存储库 [Python 包索引](https://pypi.python.org/pypi) (PyPI)中发现了 10 个故意选择错误名称来欺骗用户的流氓包。这是过去几年在开源软件仓库中发现的一系列域名仿冒攻击中的最新一起。

在 PyPI 维护者被斯洛伐克国家[计算机安全事件响应小组](https://www.csirt.gov.sk/) (CSIRT)警告后，流氓 Python 包被移除。然而，PyPI 管理员在过去已经被各种安全研究人员警告过域名抢注的风险，直到现在他们才开始研究一个更永久的黑名单解决方案。

几个著名的 Python 包的副本以稍微修改过的名字发布在官方 Python 包库 PyPI 中(突出的例子包括 urllib vs. urrlib3、bzip vs. bzip2 等)。)，”SK-CSIRT 上周在[的一次安全咨询](http://www.nbu.gov.sk/skcsirt-sa-20170909-pypi/)中说道。这些软件包包含与其上游软件包完全相同的代码，因此它们的功能是相同的，但是安装脚本 setup.py 被修改为包含恶意(但相对良性)代码

据 SK-CSIRT 称，这些流氓包是:

*   *采集(已上传 2017-06-03 01:58:01，模仿采集)*
*   *apidev-coop(已上传 2017-06-03 05:16:08，模仿 apidev-coop_cms)*
*   *bzip(已上传 2017-06-04 07:08:05，冒名顶替 bz2 文件)*
*   *crypt(已上传 2017-06-03 08:03:14，冒名顶替 crypto)*
*   *django-server(已上传 2017-06-02 08:22:23，冒充 django-server-guardian-API)*
*   *pwd(已上传 2017-06-02 13:12:33，冒名顶替 pwdhash)*
*   *设置-工具(已上传 2017-06-02 08:54:44，模仿设置工具)*
*   *[telnet](https://thenewstack.io/the-lost-worlds-of-telnet/) (已上传 2017-06-02 15:35:05，冒名顶替 telnetsrvlib)*
*   *urlib3(已上传 2017-06-02 07:09:29，冒名顶替 urlib 3)*
*   *urllib(已上传 2017-06-02 07:03:37，冒名顶替 urllib3)*

有证据表明，至少有一些用户在 6 月至 9 月期间安装了这些软件包，因为他们在网上报告了安装错误。这些错误是由添加到与 Python 3.x 不兼容的流氓包中的代码引起的。

成功执行后，恶意代码会收集诸如假冒软件包的名称和版本、安装软件包的用户的用户名以及计算机的主机名等信息。该信息用密码加密并发送到外部服务器。

尚不清楚这一行动是否有任何恶意，但攻击者经常使用环境指纹技术来识别有趣的目标，为更严重的攻击做准备。

> “令人震惊的是，PyPI 这个对整个 Python 生态系统如此重要的项目完全依赖志愿者。”—汉诺·博克

这些包也可能只是某人研究项目的一部分，尽管提取数据的混淆有些可疑。这不是研究人员第一次测试对 PyPI 或其他组件库的域名仿冒攻击。

2016 年，一个名为 [Nikolai Tschacher](https://twitter.com/incolumitas_) 的计算机科学学生上传了大约 200 个包，这些包的名称与几个存储库(包括 PyPI)上流行组件的名称相近。他包括了一个通知系统，当软件包被安装时会报告回来，并且[统计出流氓 Python 软件包有 15，221 个独特的安装](http://incolumitas.com/2016/06/08/typosquatting-package-managers/)。

一位名叫[史蒂夫·斯塔格](https://twitter.com/stestagg)的软件开发人员[有一个不同的想法](https://hackernoon.com/building-a-botnet-on-pypi-be1ad280b8d6):他在 PyPI 上注册了与 Python 标准库中的模块同名的包。用户不需要从 PyPI 下载和安装这些模块，因为如果他们有 Python，他们的系统上已经有了这些模块，但是他们中的许多人显然还是试图这样做。

斯塔格的软件包在几个月内被下载了大约 244，000 次。今年 5 月，他说他试图联系 PyPI 的管理员，但没有得到任何回应。

另外两名名为 [Benjamin Bach](https://overtag.dk/v2/) 和[Hanno bck](https://hboeck.de/)的研究人员最近用标准库名重做了 Stagg 的实验，但这与 SK-CSIRT 发现的包没有联系。两位研究人员在 PyPI 上注册了 128 个标准 Python 库包的名称，并在三天内记录了 7556 次下载尝试。

在这些新的报告之后，PyPI 的维护者们，他们是志愿者，开始致力于[一个黑名单工具](https://github.com/pypa/warehouse/pull/2396)，还不清楚这是用于被动还是主动响应，一些人已经表达了对批量将软件包列入黑名单的担忧。从 PyPI [下载和安装软件包的命令行工具](https://github.com/pypa/pip/issues/4527) [pip](https://pip.pypa.io/en/stable/) 的开发者似乎并不热衷于解决这个问题。

博克告诉我，很难解释为什么 Tschacher 在 2016 年报告中使用的软件包没有被列入黑名单。“同样令人震惊的是，PyPI 这个对整个 Python 生态系统如此重要的项目完全依赖于志愿者。”

PyPI 有超过 117，000 个包，但是根据 bck 的说法，可能有 50 到 100 个非常流行的包是大多数 Python 开发人员经常使用的。他认为，一个解决方案可以是，当用户试图安装除了那些流行的“确认”软件包之外的任何其他软件包时，警告用户潜在的风险。

软件包域名抢注不仅仅是 PyPI 的问题。类似的攻击也影响了其他编程语言的库。然而，在 Python 的情况下，风险可能更高，因为从 PyPI 下载并通过 pip 安装的每个包都有一个 setup.py 文件，其中包含将由 Python 解释器执行的代码。

这意味着恶意软件包会导致严重的系统危害。Tschacher 在他 2016 年的报告中指出，大约 40%下载和执行他的流氓包的用户是通过管理权限这样做的。

通过 Pixabay 的特征图像。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>