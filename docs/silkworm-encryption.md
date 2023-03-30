# 蚕加密

> 原文：<https://thenewstack.io/silkworm-encryption/>

建立一个防弹加密系统并不容易。所有经典密码系统的一个主要组成部分是随机数。但是随机有多随机呢？随机数生成器经常存在致命的缺陷。一些[耗尽了熵](https://qvault.io/cryptography/what-is-entropy-in-cryptography/)，比如数十亿——这不是一个错别字——[数十亿不安全的物联网设备](https://thehackernews.com/2021/08/a-critical-random-number-generator-flaw.html)。其他的，比如 2008 年臭名昭著的 [Debian Linux OpenSSL 失败](https://www.schneier.com/blog/archives/2008/05/random_number_b.html)，都是因为编程太草率。我们不要忘记，NSA 过去常常通过玩随机数游戏来削弱商业密码术。那么，为什么不用基于蚕的随机数发生器来改进你的加密呢？

## 蚕？蚕！！？是的，蚕。

它是这样工作的。韩国光州科学技术研究所(GIST)的研究人员从家养的蚕身上提取了天然蚕丝纤维。他们用这种丝绸来构建“可持续和环保的安全解决方案”他们声称这“几乎牢不可破”

嗯，[蛛丝非常坚韧](https://www.nature.com/articles/s41467-019-09350-3#Tab1)，尽管[蜘蛛丝不如钢](https://www.reconnectwithnature.org/news-events/the-buzz/myth-buster-spider-silk-is-as-strong-as-steel)结实，但却牢不可破？

下面是他们这么说的原因。这是第一个用于环保数字安全的自然“物理不可克隆功能(PUF)”，它利用光线通过天然丝绸中的天然微孔的衍射来创建一个安全而独特的数字密钥

来自家蚕的丝，也被称为家养的蚕，充满了微观的不规则。你的丝巾可能感觉像织物一样光滑，但它的原始形态要粗糙得多。

为了从中生成随机数，这项研究的高级作者年轻的宋敏教授解释说:“当一束光照射到最佳密度的无序丝纤维上时，会引起光衍射。单个微纤维中的纳米结构增强了光强度相对于背景的对比度。衍射光然后被图像传感器捕获。因为微孔的图案是自然形成的，所以它是独特的，产生了独特的光图案。”

## 无法攻破的

这是通过一个使用光反射镜和三个三色发光二极管的设备来完成的。然后，捕获的光图案被转换成数字格式。研究人员声称“结果令人震惊:伪造认证所需的平均时间约为 5×1041 年，因此洛浦-PUF 模块实际上是无法破解的设备。”

每当我听到“牢不可破”，我的第一个想法是“你希望”，其次是“现在。”但是，这听起来很有效。此外，从丝绸中生成随机数所需的设备成本低、便携、环保，并且不需要预处理或后处理。换句话说，这可能是一种廉价、可靠的方式来生成用于加密消息的真随机数。

这可能比保留一面熔岩灯墙更便宜。“熔岩灯！”你问？是的，熔岩灯。

[Cloudflare](https://www.cloudflare.com/) 使用熔岩灯，又名[lavanand](https://blog.cloudflare.com/randomness-101-lavarand-in-production/)，为其加密生成随机数。Cloudflare 并不是唯一一个使用乍听起来疯狂的方法来产生随机数的公司。例如，[Random.org](https://www.random.org/)使用[无线电检测世界各地的雷击](https://www.random.org/randomness/)作为其随机性来源。因此，虽然蚕的确…与众不同，但它们绝不是唯一用来创造真正随机数的奇怪方法。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>