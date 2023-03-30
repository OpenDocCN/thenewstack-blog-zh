# 数据访问平台供应商 Immuta 发布新的增强和集成

> 原文：<https://thenewstack.io/data-access-platform-vendor-immuta-issues-new-enhancements-and-integrations/>

总部位于波士顿的数据访问平台提供商 [Immuta](https://www.immuta.com/) 公布了其[数据访问平台](https://www.immuta.com/product/)的许多新功能和集成，包括与谷歌 [BigQuery](https://cloud.google.com/bigquery) 的原生集成，为 BigQuery 客户带来 Immuta 功能。该版本还包括对[雪花](https://www.snowflake.com/en/data-cloud/platform/)的三个增强:外部 OAuth、对表授权管理的改进和数据源接收。审计日志导出到[亚马逊 S3](https://aws.amazon.com/s3/) 以及为其[数据块](https://www.databricks.com/product/data-lakehouse)集成升级到 policy onboarding 完善了附加增强列表。新的 Stack 与 Immuta 联合创始人兼 CTO [Steve Touw](https://www.linkedin.com/in/steventouw) 讨论了投资 BigQuery 原生集成的决定，以及[版本中包含的其他功能的细节](https://www.immuta.com/blog/google-bigquery-access-control-immutas-latest-release/)。

## **深入**

关于 Google BigQuery 的搭售，Touw 表示，构建原生集成允许 Immuta“深入并…基本上在数据库供应商身上下注”，从而形成更强大的合作伙伴关系，并允许 Immuta 在数据库中原生执行策略。这种“非侵入性”的策略实施使得 Immuta 对最终用户来说基本上是不可见的，Touw 说这是构建原生集成的关键原因。这与没有本机集成的情况形成对比，在没有本机集成的情况下，Immuta 在数据库前充当代理，并重写查询。此外，本机集成为 BigQuery 用户带来了数据屏蔽、数据发现和分类的核心 Immuta 功能，通过 Immuta 基于属性的访问控制模型构建可扩展的策略，以及审核用户和策略活动以生成合规性报告。

## **让我了解最新情况**

新版本还包括了许多针对雪花的更新功能。第一个是将外部 OAuth 引入雪花:Immuta 客户可以使用其身份提供商(IdP)向雪花进行身份验证，而无需客户共享其凭据，从而为这些客户的工作负载提供更高级别的安全性。接下来，对雪花表授权管理的更新代表了 Immuta 对雪花表进行访问控制的模型的微小变化。以前，表访问权限是手动授予的，一个用户可能被分配了多个不同的角色，在这些角色之间切换，每个角色赋予用户对不同表的不同访问权限。现在，Immuta 引入了一种算法，将分配给每个用户的雪花角色层次结构整合到一个角色下，并在下面提供所有适用的策略，旨在简化这些角色的管理。第三个与雪花相关的增强功能增加了从雪花向 Immuta 大规模接收元数据的能力，并提供了基于 API 的进度报告。

如上所述，这个 Immuta 版本还包括审计日志导出到亚马逊 S3，以及为 Databricks 用户更新政策。第一个功能允许将 Immuta 中收集的审计日志数据导出到亚马逊 S3，然后可以使用 [Splunk](https://www.splunk.com/en_us/products/log-observer.html) 等工具进行分析。然后，用户可以跨捕获的所有审核日志构建控制面板，从而允许用户分析数据访问方式的历史趋势以及策略随时间的变化情况。Touw 表示，引入这一功能是帮助客户理解和分析其底层数据系统模式的第一步。

最后，针对 Immuta 的 Databricks 集成的策略加入更新现在将策略构建与敏感数据发现分离开来。有了这个新的缺省值，当用户注册表时，Immuta 现在保留现有的访问控制，允许用户仍然跨表运行敏感数据发现，分析结果，并相应地更新和应用策略。这种方法将入职流程分解为多个步骤，允许用户采取更加迭代的方法。

## **现在回报，未来回报**

总的来说，Touw 表示，审计日志导出到 S3 功能和对数据块的默认无策略设置的更改可能会在解决现有痛点方面为当前客户带来最直接的回报。Immuta 还希望与 BigQuery 的集成将允许它打开 BigQuery 客户的市场，并将其功能带给更广泛的受众。安全和隐私问题在全球范围内日益增加。将这些功能带给不断扩大的用户群有可能扩大对数据访问管理的需求，并鼓励客户主动、成功地实施数据访问管理。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>