# 基于角色的访问控制:五种常见的授权模式

> 原文：<https://thenewstack.io/role-based-access-control-five-common-authorization-patterns/>

授权很复杂，因为每个应用都必须发明自己的授权模型。然而，对于大多数应用程序来说，有一些老路可以作为良好的起点。这篇文章介绍了这些模式，以及一个授权平台(比如 Topaz 开源项目或 T2 授权服务)如何帮助你实现它们。

# 角色作为用户属性

最简单的授权模式将一组角色建模为用户的属性。这些角色可以在身份提供者(IDP)中配置，并且通常作为范围嵌入到由 IDP 生成的访问令牌中。

一些应用程序完全基于访问令牌中嵌入的角色(或离散权限)进行授权。但是这也有一些[的缺点](https://www.aserto.com/blog/oauth2-scopes-are-not-permissions):

*   **角色/权限/范围爆炸:**角色/权限越多，访问令牌中需要嵌入的范围就越多，导致大小问题。
*   **IDP 和应用程序之间的耦合:**每当向应用程序添加新的权限时，在访问令牌中生成附加范围的代码也必须修改。这通常由有权访问 IDP 的安全/身份和访问团队来完成，并且它会引入工作流复杂性。
*   **一旦发布**，访问令牌很难失效。只要访问令牌有效，经过身份验证的用户就拥有权限，即使他们的角色在令牌颁发后发生了变化。这进而导致了安全漏洞。

在这种情况下，使用像 Topaz 这样的授权服务有几个好处:

*   添加显式授权系统使应用程序能够实时检查用户是否仍然拥有角色或权限。
*   授权代码可以从应用程序中提取出来，并表示为一个策略。这使得在整个应用程序中推理授权逻辑变得更加容易。
*   每个 API 可以有不同的授权策略，其中包含用于授权操作的逻辑。一个示例策略可以是“如果用户具有‘管理’或‘编辑’角色，或者‘创建’权限，则允许操作。”
*   任何角色变化(或用户的全局“禁用”标志的值)都可以近乎实时地传输到授权系统。这消除了与盲目信任嵌入在访问令牌中的范围相关联的安全问题。
*   角色到权限的映射可以在授权系统中完成。因此，IDP 只需要知道用户到角色的映射，而不需要知道权限。这有助于从 IDP 中分离应用程序。

# 基于群体的 RBAC

下一个模式依赖组(和组层次结构)作为组织用户的方式。

大多数应用程序都有粗粒度的角色，如“超级管理员”、“管理员”、“编辑者”、“查看者”、“计费管理员”，这些角色决定整个租户对对象的权限。

这些角色通常是通过使用户成为组的成员来分配的。组成员资格意味着用户被授予了一个角色。可以将组组织成层次结构。例如，“审计员”组可以包括“内部审计员”和“外部审计员”这两个组又可以包括特定的用户。

这实质上是 LDAP 和 Active Directory 所围绕的模型。因此，大多数授权系统都支持将组作为其模型的核心部分。

例如，Topaz 和 Aserto 有一个内置的“组”对象类型。组对象类型有一个“成员”关系类型，该关系的目标可以是任何主体(用户或组)。该模型允许将组包含在其他组中。检查组成员资格是可传递的:当用一个用户和一个组实例调用 Topaz 的 check_relation 内置函数时，它将遍历组层次结构，如果用户是组的直接成员或传递成员，则返回 true。

以下策略(用开放策略代理的[减压阀](https://www.openpolicyagent.org/docs/latest/policy-language/)语言编写)使用 Topaz 内置的 check_relation 来评估用户是否是某个组的成员，如果是，则允许该操作:

```
allowed  {
   ds.check_relation({
     "subject":  {  "id":  input.user.id  },
     "relation":  {  "object_type":  "group",  "name":  "member"  },
     "object":  {
       "type":  "group",
       "key":  input.resource.key 
     }
  })
}

```

由于可以通过多个角色授予权限，策略可能需要检查每个相应组的组成员资格。例如，如果用户是任何“查看者”、“编辑者”或“管理”组的成员，则可以授予“查看”权限。这将通过以下政策来实现:

```
groups  :=  {  "viewer",  "editor",  "admin"  }
allowed  {
   ds.check_relation({
     "subject":  {  "id":  input.user.id  },
     "relation":  {  "object_type":  "group",  "name":  "member"  },
     "object":  {  "type":  "group",  "key":  groups[_]  }
   })
}

```

但这可能会变得复杂，而且可以说这只是将复杂性从应用程序逻辑转移到了策略上。下一个模式旨在解决这个问题。

# 具有细粒度权限的基于组的 RBAC

RBAC 代表基于角色的访问控制。权限可以包含在多个角色中。在上面的示例中，can-view 权限可能包含在“查看者”、“编辑者”和“管理员”角色中。更具可伸缩性的授权系统将定义一组离散的权限，并将这些权限分配给角色。

授权系统通常将权限定义为一级概念。该策略可以检查用户是否有权限，而不是检查用户是否是组的成员。

例如，Topaz 允许将权限与关系类型(也称为“角色”)相关联。它还允许角色包含其他角色，例如，“编辑”角色可以包含“查看者”角色。

下面的 Aserto 清单文件就是这样做的。它定义了一个“系统”对象类型，在它下面，有两个关系类型:“编辑器”和“查看器”“编辑者”关系类型包括“查看者”关系类型的所有权限，并添加了“可以编辑”权限。“查看者”关系类型包括一个单独的权限:可以查看。

```
system:
   editor:
     union:
     -  viewer
     permissions:
    -  can-edit

   viewer:
     permissions:
     -  can-view

```

如果用户(或组)具有“编辑”角色，那么在评估该用户是否具有 can-view 权限时，Topaz check_permission 内置将返回 true。这是因为“编辑”角色包含“查看者”角色，因此也包含“查看”权限。

# 特定于域的对象的细粒度授权

到目前为止，我们一直在处理“全球”角色。许多应用程序希望对它们管理的一组对象授予权限。例如，Google Drive 等文件共享应用程序将“文件夹”和“文件”定义为对象类型。文件夹和文件都可以有一个父文件夹。这些对象中的每一个都有一组关系(“所有者”、“编辑者”、“评论者”和“查看者”)，并且“所有者”可以将这些角色授予用户和组。因此，这些权限可以分配给离散的文件夹和文件，而不是拥有对每个文件和文件夹的编辑权限的全局“编辑”角色。

[谷歌的桑给巴尔](https://research.google/pubs/pub48190/)授权系统，支持谷歌文档和许多其他谷歌应用程序，实现了这种模式。桑给巴尔启发了许多授权系统，包括 Airbnb 的 Himeji，Carta 的 AuthZ 和一些开源实现，包括 Topaz。

使用 Topaz，您可以定义特定于领域的对象类型和关系类型。每个关系类型可以定义权限(和/或其他关系类型的联合)。支持这种模式的完整清单示例可以在[这里](https://github.com/aserto-dev/topaz-samples/blob/main/gdrive/model/manifest.yaml)找到。

纯粹以评估主体(用户和组)与对象(例如文件夹和文件)之间的关系(例如“查看者”、“编辑者”)的形式构建的授权模型可以用非常简单的策略来表达:

```
allowed  {
   ds.check_permission({
     "subject":  {  "id":  input.user.id  },
     "permission":  {  "name":  input.policy.path  },
     "object":  {
       "type":  input.resource.type,
       "key":  input.resource.key 
     }
   })
}

```

# 将基于团体的 RBAC 和 FGA 结合起来

大多数现实世界的应用程序都实现了基于组的 RBAC 和细粒度授权的某种组合。通常，授权包括检查全局角色(例如，“编辑”)，然后检查用户是否有权访问特定资源(例如列表)。用户需要满足这两个条件才能编辑列表上的项目。

另一个例子是“超级管理员”，由于拥有这个角色，他可以做任何事情。访问检查包括允许用户通过关系访问特定对象的逻辑，以及允许具有这些提升角色的用户访问的逻辑。

Topaz 也支持这些场景，因为它结合了策略和基于关系的访问控制。为了扩展前面的示例，我们可以向该策略添加另一个“允许”条款。如果用户被授予对特定对象的特定权限，或者如果他们是“超级管理员”:

```
allowed  {
 ds.check_permission({
 "subject":  {  "id":  input.user.id  },
 "permission":  {  "name":  input.policy.path  },
 "object":  {
 "type":  input.resource.type,
 "key":  input.resource.key
      }
})
}

```

```
allowed  {
 input.user.roles[_]  ==  "super-admin"
 }

```

# 结论

我们已经讨论了五种常见的授权模式，从最简单的基于 IDP 的 RBAC 开始，到基于组的 RBAC 与细粒度权限和细粒度资源的结合。

Topaz 支持所有这些模型，而且同样重要的是，通过改进授权策略，使得从简单模型向更复杂的模型发展变得容易。

最终，每个成功的应用程序都需要一套深入的授权功能。在您的旅程的早期采用像 Topaz 或 Aserto 这样的授权平台可以让您的应用程序经得起时间的考验，并使您的授权模型更容易适应您不断增长的需求。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>