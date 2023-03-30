# 攻击者如何从 Azure Active Directory 转移到本地 AD

> 原文：<https://thenewstack.io/how-attackers-move-from-azure-active-directory-to-on-prem-ad/>

[](https://www.linkedin.com/in/robbinsandy/)

 [安迪·罗宾斯

安迪·罗宾斯(Andy Robbins)是免费开源的活动目录攻击路径映射和分析工具 BloodHound 的联合创始人。Andy 曾在多个会议上发言，包括黑帽美国、黑帽欧洲和 DEF CON，并具有专业 red 团队和渗透测试的背景。](https://www.linkedin.com/in/robbinsandy/) [](https://www.linkedin.com/in/robbinsandy/)

微软的活动目录(AD)仍然是攻击者的主要目标，随着对云的依赖增加，组织面临着越来越大的压力来保护 AD，而不仅仅是那些内部部署。[Azure Active Directory](https://azure.microsoft.com/en-us/services/active-directory/)(Azure AD)是微软的目录服务平台，用于管理和保护云中的身份。就像本地 AD 一样，Azure AD 容易受到攻击者的攻击，攻击者利用错误配置的用户角色或访问权限横向移动、提升权限、访问敏感数据和部署恶意软件。在本地 AD 连接到 Azure AD 的混合环境中，其中一个甚至可能被滥用来利用另一个。

不幸的是，世界上的每一个活动目录环境都容易受到身份攻击。为了执行这种攻击路径(通常也称为身份雪球攻击)，对手使用网络钓鱼或其他策略来危害用户对网络上机器的访问。

一旦他们有能力执行代码，他们就会使用各种技术(以及像 [Mimikatz](https://github.com/gentilkiwi/mimikatz) 或 [Cobalt Strike](https://www.cobaltstrike.com/) 这样的工具)横向移动并提升权限，为拥有越来越多权限的用户获取凭证，直到他们获得完成目标所需的访问权限。由于这些技术滥用合法的服务和有效的用户凭证，防御者很难检测到它们。

但是，攻击路径不仅限于本地，也不仅限于云中。事实上，对手之所以能够依靠攻击路径来控制几乎任何企业的 AD 环境，部分原因是因为他们可以跨越内部和云。

具体来说，现有的安全研究没有很好地记录攻击者如何从 Azure AD 转移到本地 AD。但理解这是如何工作的是很重要的，因为它开启了使用 Azure AD 租户来弥合彼此不明确信任的不同环境之间的差距的可能性。这使得接管 Azure 广告租户的前景对攻击者来说更具吸引力和影响力。

## **注意差距:从 Azure 到本地 AD 的横向移动**

我和我的同事研究的其中一种攻击方法滥用 Microsoft Endpoint Manager，从 Azure 租户横向移动到本地 AD 域。Azure 为组织提供了管理用户和服务主体身份所需的所有工具，包括 ConfigMgr、Intune 和 Endpoint Manager。

这些工具允许管理员在一定程度上配置终端—它不允许像组策略那样多的控制，但是可以使用这些工具配置和控制的系统范围是很大的。此外，一台计算机可以加入本地 AD 域和 Azure AD 域，微软称之为“混合 Azure AD join”许多组织这样做是因为他们希望通过 Azure 管理尽可能多的端点，以减少他们需要使用的独立管理工具的数量。

如果组织使用混合 Azure AD join 来管理本地 Windows 系统，则控制“全局管理员”或“内部管理员”主体的攻击者可以作为系统用户在这些本地设备上执行任意 PowerShell 脚本。因为来自不同 AD 域的内部系统可以混合加入到同一个租户，所以攻击路径可以从一个内部域(或者可以向 Azure 进行身份验证的许多其他身份平台之一)开始，并在另一个内部域结束，其中绝对不存在域或林信任。

更直白地说，从 Azure AD 租户转向本地 AD 域可能会在完全不同的身份管理环境和平台之间形成攻击路径，这些环境和平台不会明确地相互信任，甚至不了解彼此。这是我们迄今为止发现的第一个攻击媒介，它允许将对 Azure 租户的控制转变为本地域内的代码执行，而无需重置本地用户密码。

## **保护和减少差距:服务负责人和用户扮演的审计角色**

为了防止这种攻击途径，Azure 管理员应该审核服务主体和用户所扮演的角色，并将它们与任何其他对应用程序有控制权的身份进行比较。这种攻击要求对手具有全局管理员或 Intune 管理员角色，因此从防范的角度来看，查看谁具有这些角色是一个很好的起点。防御者可以通过 Azure 门户审核哪些用户激活了这些角色。否则，Azure AD PowerShell 模块可用于考虑当前激活这些角色的任何人。

当检查激活了全局管理员角色的主体时，防御者应评估该列表中的所有用户是否都被信任，可以作为其组织的端点管理注册的混合加入系统上的系统来执行代码。此外，防御者可以审计内部域中的哪些系统由 Intune 管理。有几种方法可以做到这一点，这取决于防御者可以访问哪种遥测技术或信息。还有许多 AD 安全解决方案可以帮助检测和防止过程中的攻击，或者分析 AD 环境以发现错误配置和过度授权的用户，可以修复这些问题以消除攻击路径。

此处[提供了关于此攻击的枚举、执行和检测的更详细说明。](https://posts.specterops.io/death-from-above-lateral-movement-from-azure-to-on-prem-ad-d18cb3959d4d)

内部和云中的身份和访问管理是同一枚硬币的两面。

混合环境允许对手通过新的攻击途径从 Azure AD 等云服务转移到本地 AD，反之亦然。随着微软继续推出更多模糊云和本地之间界限的管理功能，预计会出现更多这种性质的攻击原语(如果不能保证)。对于采用混合基础架构模式的组织，全面的保护—包括使用 [攻击路径管理](https://bloodhoundenterprise.io/what-is-attack-path-management/) 等方法—可以帮助衡量和减轻组织的整体 AD 风险暴露，以确保用户和敏感数据的安全。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>