# 糟糕的密码安全使得 ESLint 供应链对 Npm 发起攻击

> 原文：<https://thenewstack.io/poor-password-hygiene-enabled-eslint-supply-chain-attack-on-npm/>

上周，在攻击者破坏了与 [ESLint 库](https://eslint.org/docs/about/)相关的两个合法包并在其中植入恶意代码后，npm 注册表维护者宣布开发者登录令牌无效。

“2018 年 7 月 12 日，一名攻击者侵入了 eslint 维护者的 npm 账户，并向 npm 注册表发布了 eslint-scope 和 eslint-config-eslint 包的恶意版本，”ESLint 团队在[的一份事件报告](https://eslint.org/blog/2018/07/postmortem-for-malicious-package-publishes)中表示。

流氓版本包括[，一个恶意的安装后脚本](https://gist.github.com/hzoo/51cb84afdc50b14bffa6c6dc49826b3e)，它从 pastebin.com 下载并执行流氓代码，旨在窃取用户的代码。npmrc 文件。这些是本地配置文件，通常包含用于将软件包发布到 npm 注册表的访问令牌。

总之，这是一个完全成熟的软件供应链攻击，其目标是危害更多的开发人员，并潜在地毒害他们自己的包，以进一步进行更多的攻击。

ESLint 是林挺的一个流行的开源 JavaScript 实用程序，是一个静态代码分析过程，用于识别编程错误、风格错误和潜在的有问题的代码构造。该实用程序由 JS Foundation 托管，使用 Node.js 运行时环境，并通过 npm 安装。

根据 ESLint 事件报告，攻击者在第三方漏洞中发现了一个维护者的 npm 电子邮件和密码，这表明密码卫生很差。

跨多个服务重复使用密码是一种危险的做法，也是帐户劫持的常见原因。攻击者使用所谓的[凭据填充](https://owasp.org/www-community/attacks/Credential_stuffing)技术，针对多个网站自动测试泄露的凭据。

不幸的是，尽管易于使用的密码管理工具广泛可用，但凭据重用仍然是用户(包括开发人员)的常见做法。[最近的一起事件](https://wiki.gentoo.org/wiki/Project:Infrastructure/Incident_Reports/2018-06-28_Github)中，GitHub 上的 Gentoo Linux 存储库发布了恶意代码，这也是一名管理员的密码在第三方入侵中被泄露的结果。

在 ESLint 的情况下，攻击者使用他们获得的 npm 身份验证令牌来发布 eslint-config-eslint 包的新版本(5.0.2 ),其中包含恶意的安装后脚本。然后他们发布了包含相同脚本的 eslint-config-eslint 5.0.2 和 eslint-scope 3.7.2。

幸运的是，恶意代码[在 40 分钟内被 ESLint 用户](https://github.com/eslint/eslint-scope/issues/39)发现，项目的维护者也收到了警告。一个半小时后，eslint-scope 3.7.2 包被取下，一个干净的 eslint-scope 版本(3.7.3)被发布在它的位置，以便更新缓存。

npm 团队还决定使 UTC 时间 2018-07-12 12:30 之前创建的所有登录令牌无效，以减轻攻击可能对其他开发人员造成的任何潜在影响。此操作导致了 npmjs.com 上的一些加载问题，这些问题很快得到解决。

“你的 npm 登录令牌不会给攻击者你的 npm 密码，”npm 注册维护者说。“您可以通过访问 https://www.npmjs.com/settings/~/tokens 的(需要登录)来撤销所有现有的代币。

事件发生后，ESLint 团队为所有在 npm 上发布的开发人员发布了以下建议:

*   软件包维护者和用户应该避免在多个不同的站点上重复使用同一个密码。像 1Password 或 LastPass 这样的密码管理器可以帮助您做到这一点。
*   软件包维护人员应该[启用 npm 双因素认证](https://www.npmjs.com/settings/~/tfa)。npm 有一个向导[在这里](https://docs.npmjs.com/getting-started/using-two-factor-authentication)。如果用 Lerna，可以按照这个[期](https://github.com/lerna/lerna/issues/1091)来。
*   软件包维护者应该审核并限制有权在 npm 上发布的人数。
*   包维护者应该小心使用任何自动合并依赖升级的服务。
*   应用程序开发人员应该使用一个锁文件(package-lock.json 或 yarn.lock)来防止新包的自动安装。

有关密码管理和在线账户安全的更多详细信息，您可以[阅读我们自己的 TNS 指南](https://thenewstack.io/manage-passwords-keep-online-accounts-secure/)。

通过 Pixabay 的特征图像。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>