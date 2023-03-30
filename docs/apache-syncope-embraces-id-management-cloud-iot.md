# Apache 晕厥提供开源单点登录身份管理

> 原文：<https://thenewstack.io/apache-syncope-embraces-id-management-cloud-iot/>

瑞士组织 [SWITCH](https://www.switch.ch/about/projects/) ，管理大学和研究机构之间的教育网络，正在为大学成员开发一个安全的[数字身份](https://projects.switch.ch/eduid/)，它将提供单点登录功能和与其他服务的连接。

对于瑞士的大学来说，数字身份服务是从当前的认证和授权基础设施发展而来的。

[![screen-shot-2016-09-23-at-5-24-46-am](img/838d50ea0a7d5d71a861a56e6a13692e.png)](https://syncope.apache.org/)

该组织最近选择了 [Apache 晕厥](https://syncope.apache.org/)作为该项目考虑中的领先技术，击败了包括 CA、戴尔、IBM、微软、Oracle、SAPSailpoint、Okta、OneLogin、ForgeRock、OpenIAM 等小众玩家；甚至开源 [Evolveum](https://evolveum.com/) 。

“Apache census 提供了一个开发良好且可配置的工作流引擎，以及一个用于扩展的文档化 API。它允许在一个小配置中启动，可以随着时间的推移逐渐扩展，”SWITCH 在回应其信息请求(RFI)的[报告](https://projects.switch.ch/export/sites/projects/eduid/.galleries/documents/SWITCH_edu-ID_IdM_Market-Analysis_public.pdf)中总结道。它指出，晕厥与开源技术的整合是其决定继续开发晕厥原型的关键因素之一。

Apache census 在 Java EE 技术中实现，旨在跨存储库、数据格式和模型保持企业身份数据的一致和同步。

该项目最近推出了[晕厥 2.0](http://www.tirasa.net/news/apache-syncope-2.0.0-is-now-available.html) ，项目副总裁[Francesco chichiriccò](https://www.linkedin.com/in/francescochicchiricco?authType=NAME_SEARCH&authToken=XmlA&locale=en_US&srchid=164693751475077851809&srchindex=1&srchtotal=1&trk=vsrp_people_res_name&trkInfo=VSRPsearchId%3A164693751475077851809%2CVSRPtargetId%3A3191603%2CVSRPcmpt%3Aprimary%2CVSRPnm%3Atrue%2CauthType%3ANAME_SEARCH)将其誉为一个重要的里程碑。

新特性包括:

*   原生支持管理工作站、打印机、文件夹、传感器、服务等，这应该是物联网管理的福音。

*   多租户，将不同租户的所有数据物理分离到不同的数据库实例中，用于基于云的部署。

*   重新设计的管理员和最终用户用户界面，包括一个自助式 web 应用程序，用户只能在其中编辑自己的信息。

*   新的“入门”和参考指南。Chicchiriccò称文档是许多开源项目中最常见的缺失特性。

除了默认的全 Java 实现之外，还有与 [Swagger](http://syncope.tirasa.net/news/apache-syncope-2.0.0-and-swagger.html) 和 Apache Camel [供应引擎](http://coheigea.blogspot.it/2016/09/integrating-apache-camel-with-apache.html)的集成。

晕厥通过 JAX-RS 2.0 RESTful 接口连接到任何编程语言编写的第三方应用程序。它的可插拔设计意味着每个部署都可以从提供的列表中指定或定制。供应层依赖于 [ConnId](http://connid.tirasa.net) 。它使用[弹簧框架](https://projects.spring.io/spring-framework/)进行存储。

容器方面，晕厥 2.0 支持 [Apache Tomcat 8 和 8.5](http://tomcat.apache.org/download-80.cgi) 、 [Glassfish 4.1](https://glassfish.java.net/) 、 [Payara Server](http://www.payara.fish/) 、 [Wildfly 9 和 10](http://www.wildfly.org/) 以及数据库 PostgreSQL、MariaDB、MySQL、Oracle Database 和 MS SQL server。

## **根源于意大利**

“单一账户的数据通常分散在不同的应用程序中。在一个典型的组织中，每个人都有电子邮件、时间跟踪、ERP、CRM 等等。通常情况下，每当有人加入公司时，这种做法都会很好，但如果有人升职或离职，就麻烦了。这可能会带来一些严重的安全威胁，”奇奇里科在接受采访时解释道。

Apache 晕厥可以创建信息的虚拟表示，让管理员处理它。他说，它还为企业高管提供了强大的报告和提取工具。

其用户包括德国保险集团 ARAG、身份即服务供应商 [iWelcome](https://www.iwelcome.com/) 、混合云应用交付平台 UShareSoft，以及[赫尔辛基](https://www.helsinki.fi/en)和[米兰](http://www.unimi.it/ENG/)的大学。

Chicchiriccò和该项目的其他创始人是 Sun Microsystems technology 在意大利的讲师，并在甲骨文 2010 年收购 Sun 时为那里的一家服务集成商工作。由于担心 Oracle 会将 Sun 的技术变成专利，他们开始从零开始构建自己的开源身份管理解决方案。

晕厥于 2012 年 2 月进入 Apache 孵化器，2012 年 11 月成为顶级项目。

奇奇里科基于该项目成立了意大利公司 [Tirasa](http://www.tirasa.net/) ，来自数据集成商 [Talend](https://www.talend.com/) 的工程师也是其贡献者之一。

Chicchiriccò说，开源项目不仅仅是一家公司的工作，这一点至关重要，处于 Apache 软件基金会的权限之下增加了它在客户中的合法性。

“当一些潜在客户问我，‘我应该相信 Tirasa 五年后还会继续运营吗？’，我可以坦率地回答‘可能吧。请记住，六年前没有人认为太阳微系统公司会被收购。无论如何，我打赌 Apache 软件基金会仍然会存在更长时间。"

Tirasa 也在为中间件和安全服务在 [CHOReVOLUTION](http://www.chorevolution.eu/bin/view/Interviews/Francesco_Chicchiricco) 平台中的集成做出贡献。它由欧盟的 Horizon 2020 研究和创新计划资助，专注于为未来的互联网开发分布式服务协调技术。

展望未来，该项目将进一步支持成熟的标准，如 [OAuth 2.0](https://oauth.net/2/) 、 [OpenID Connect](http://openid.net/connect/) 和 [SAML 2.0](http://docs.oasis-open.org/security/saml/Post2.0/sstc-saml-tech-overview-2.0.html) ，以实现与移动设备的更紧密集成和系统核心组件的实时定制，从而增加部署灵活性。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>