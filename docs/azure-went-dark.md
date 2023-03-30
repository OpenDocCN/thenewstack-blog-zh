# 蔚蓝变黑了

> 原文：<https://thenewstack.io/azure-went-dark/>

全世界所有的微软 365 服务都瘫痪了。

反对将企业信任放在云端的一个流行观点是，如果你的超级云提供商倒闭了，你的企业也会倒闭。嗯，在美国东海岸的清晨，它发生了。微软 Azure 倒下了，随之倒下的还有微软 365、Exchange Online、Outlook、SharePoint Online、OneDrive for Business、 [GitHub](https://thenewstack.io/github-copilot-a-powerful-controversial-autocomplete-for-developers/) 、[微软认证器](https://thenewstack.io/github-kisses-passwords-goodbye/)以及团队。简而言之，Azure 上运行的几乎所有东西都爆炸了。

Azure 的状态页面显示，美国、欧洲、亚太、中东和非洲的所有地方都受到了影响。中国是唯一躲过这场危机的地区。

## 第一份报告

微软在美国东部时间凌晨 2 点 31 分首次报告了这个问题，当时欧洲正在开始工作。微软 365 状态推特账号报道，“我们正在调查影响多个微软 365 服务的[问题。”](https://twitter.com/MSFT365Status/status/1618149579341369345?ref_src=twsrc%5Etfw%7Ctwcamp%5Etweetembed%7Ctwterm%5E1618149579341369345%7Ctwgr%5Ef90f7fc2911c40ff407a5ab2225d5af03d6490f2%7Ctwcon%5Es1_&ref_url=https%3A%2F%2Fwww.redditmedia.com%2Fmediaembed%2F10kuh87%3Fresponsive%3Dtrueis_nightmode%3Dfalse)

当然，那时候用户已经在尖叫了。正如 sysadmin subreddit 上的一名 Reddit 用户所写的那样，“T10 把它移到云上，他们说 T11，它永远不会停机，他们说，我们会节省很多钱。”

## 该决议

后来，微软报告说，“我们已经[回滚了一个我们认为会造成影响的网络变化](https://twitter.com/MSFT365Status/status/1618178407316987905)。当回滚生效时，我们会监控服务。”到上午 9 点 31 分，微软表示灾难已经结束。“我们已经确认[受影响的服务已经恢复并保持稳定。“但是，我们正在调查对 Exchange Online 服务的一些潜在影响。”那么，Exchange 管理员和用户？现在还不要放松。](https://twitter.com/MSFT365Status/status/1618255289165168640)

## 是什么原因造成的？

那么，到底是什么原因造成的呢？微软没有说，但作为一名前[网络管理员](https://thenewstack.io/20-years-open-source-admin-engineer/)，我敢打赌，这不是域名系统(DNS)就是边界网关协议(BGP)配置错误。鉴于多个 Azure 地区的失败纯粹是全球性的，我把我的钱押在 BGP 上。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>