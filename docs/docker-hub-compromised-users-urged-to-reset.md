# Docker Hub 受损，用户被要求重置密码和令牌

> 原文：<https://thenewstack.io/docker-hub-compromised-users-urged-to-reset/>

[Docker Hub](https://hub.docker.com/) 容器注册表的一些用户需要更改他们的凭据，检查他们的日志并重启他们的自动构建，因为 [Docker](https://www.docker.com/) 披露了一个未知方临时获得了对 Docker Hub 数据库的未经授权的访问，并能够访问大约 190，000 个帐户的敏感数据。

除了 Docker Hub 帐户之外，此次违规还可能危及这些用户的一些相关 BitBucket 和 GitHub 帐户。

“2019 年 4 月 25 日，星期四，我们发现对存储非金融用户数据子集的单个中心数据库的未经授权的访问。Docker 支持总监 Kent Lamb 在周四发给 Docker Hub 用户的一封电子邮件中写道:“发现后，我们迅速采取了干预措施，并保护了网站。该公司于周四通知了受此次事件影响的用户。

暴露的数据包括这些用户子集的用户名和散列密码。用于 Docker 自动构建的 Github 和 Bitbucket 令牌也被曝光。该公司已经撤销了受影响用户的 GitHub 令牌和访问密钥。来自公司自动化构建服务的正在进行的构建也可能被禁用。

Docker 建议受违规影响的人员采取以下措施:

截至周六，Docker 尚未在其网站上披露任何其他信息。据该公司称，Docker Hub 的总用户群中约有 5%受到了此次入侵的直接影响。

“为了帮助防止将来发生类似的事情，我们正在加强我们的整体安全流程并审查我们的政策。Docker 首席技术官 [Kal De](https://twitter.com/thinklets) 在一份声明中写道:“额外的监控工具已经到位。

有其他问题的人可以发电子邮件给 Docker Support，地址是[info@docker.com](mailto:info@docker.com)。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>