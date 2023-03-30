# 最好的公共和私有密钥生成算法——为什么

> 原文：<https://thenewstack.io/the-best-public-and-private-keygen-algorithm-and-why/>

[](https://twitter.com/Mad_Eye_Mody)

 [维拉格莫迪

维拉格于 2020 年 1 月加入 gravity，此前他与人联合创办了一家以太坊应用软件代码审计公司。他继续学习流行技术，制作高质量的书面和视频内容。](https://twitter.com/Mad_Eye_Mody) [](https://twitter.com/Mad_Eye_Mody)

还有什么比让私人钥匙无人看管更糟糕的呢？拥有可以被暴力破解的公钥。

“安全外壳”中的“安全”来自哈希、对称加密和非对称加密的组合。总之，SSH 使用加密原语来安全地连接客户机和服务器。自成立以来的 25 年中，根据摩尔定律的计算能力和速度已经使得越来越复杂的低级算法成为必要。

截至 2020 年，PKI 世界中最广泛采用的非对称加密算法是 RSA、DSA、ECDSA 和 EdDSA。那么哪个最好呢？

## 那么用哪个呢？

选择正确的算法取决于几个标准:

*   **实施:**专家能处理吗，还是需要滚？
*   **兼容性:**有不支持某个方法的 SSH 客户端吗？
*   **性能:**生成一个足够安全的密钥需要多长时间？
*   **安全性:**公钥可以从私钥派生出来吗？(本文不讨论利用量子计算破解加密。)

### 南非共和国(Republic of South Africa)

时间是 RSA 最大的盟友，也是最大的敌人。RSA 于 1977 年首次发布，拥有跨所有 SSH 客户端和语言的最广泛支持，并且作为一种可靠的密钥生成方法真正经受住了时间的考验。随后，几十年来，它也受到摩尔定律的约束，密钥位长的大小也在增长。根据 NIST 标准，实现 128 位安全性需要长度为 3072 位的密钥，而其他算法使用更小的密钥。位安全衡量暴力破解密钥所需的尝试次数。128 位安全意味着要破解 2128 次尝试。

### 目录系统代理(Directory System Agent)

DSA 与 RSA 的不同之处在于 DSA 使用了不同的算法。它解决了一个完全不同的问题，称为离散对数问题，使用不同的一套方程，元素和步骤。

该算法使用随机生成的数字 m，该数字与私钥 k 一起用于对消息进行签名。该数字 m 必须保密。该值应该是一个 nonce，它是许多加密协议中包含的唯一值。然而，不可预测性和保密性的附加条件使得随机数更类似于密钥，因此极其重要。

不仅很难确保机器内部的真正随机性，而且不正确的实现可能会破坏加密。例如:

1.  众所周知，Android 的 Java SecureRandom 类会产生[冲突的 R 值](https://crypto.stackexchange.com/questions/9694/technical-details-of-attack-on-android-bitcoin-usage-of-securerandom)。换句话说，这个类重用了一些随机生成的数字。这暴露了许多不同的[基于安卓系统的比特币钱包](https://bitcoin.org/en/alert/2013-08-11-android)的私钥被盗。nonce m 的要求意味着任何两个具有相同 nonce 值的实例都可能被逆向工程，从而泄露用于签署事务的私钥。
2.  更进一步， [fail0verflow](https://fail0verflow.com/blog/) 发现了用于签署索尼 Playstation 3 固件更新的私钥。换句话说，程序员可以编写自己的代码，用公开的私钥签名，然后在 PS3 上运行。事实证明，索尼使用的是与 [*相同的*随机数](https://www.youtube.com/watch?v=LP1t_pzxKyE)来签署每条消息。

### ECDSA 和 EdDSA

上面两个例子并不完全真诚。索尼和比特币协议都采用 ECDSA，而不是 DSA 本身。ECDSA 是 DSA 的椭圆曲线实现。在功能上，RSA 和 DSA 需要 3072 位的密钥长度来提供 128 位的安全性，而 ECDSA 只需要 256 位的密钥就可以实现同样的功能。然而，ECDSA 依赖于与 DSA 相同水平的随机性，因此唯一的增益是速度和长度，[而不是安全性](https://blog.trailofbits.com/2020/06/11/ecdsa-handle-with-care/)。

为了响应椭圆曲线的期望速度和不期望的安全风险，另一类曲线已经获得了一些恶名。EdDSA 解决了与 DSA/ECDSA 相同的离散对数问题，但使用了不同的椭圆曲线系列，称为[爱德华兹曲线](https://en.wikipedia.org/wiki/Edwards_curve) (EdDSA 使用了[扭曲爱德华兹曲线](https://en.wikipedia.org/wiki/Twisted_Edwards_curve))。虽然在速度上比 ECDSA 稍有优势，但它的流行源于安全性的提高。EdDSA 不依赖随机数作为 nonce 值，而是确定性地生成一个 nonce 作为哈希，使其具有抗冲突性。

退一步说，椭圆曲线的使用并不能自动保证某种程度的安全性。不是所有的曲线都是一样的。只有几条[曲线](https://safecurves.cr.yp.to/)通过了严格的测试。幸运的是，PKI 行业已经慢慢接受了曲线——特别是对于 EdDSA。把这些放在一起就形成了公钥签名算法。

## 基本上，RSA 或 EdDSA

归根结底，要在 RSA 2048/4096 和 Ed25519 之间做出选择，要在性能和兼容性之间做出权衡。SSH 客户端普遍支持 RSA，而 EdDSA 执行速度快得多，并且使用小得多的密钥提供相同级别的安全性。彼得·鲁佩尔简洁地给出了答案:

*“这个问题的简短回答是:只要密钥强度在可预见的未来足够好，其实并不重要。因为这里我们考虑的是 SSH 会话中的认证签名。签名的加密强度只需要能够承受当前最先进的攻击。”—* [用于 SSH 的 ed 25519](https://blog.peterruppel.de/ed25519-for-ssh/)

就是不要用 ECDSA/DSA！

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>