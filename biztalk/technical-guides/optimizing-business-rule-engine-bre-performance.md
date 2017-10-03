---
title: "优化业务规则引擎 (BRE) 性能 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: c271b059-174d-4e8b-88b5-c3f408a97f1f
caps.latest.revision: "4"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 14c3adf32ac06d80c1aab8f870d82156470097a5
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="optimizing-business-rule-engine-bre-performance"></a>优化业务规则引擎 (BRE) 性能
在 BizTalk Server 解决方案中实施业务规则引擎 (BRE) 时，应考虑以下因素：  
  
## <a name="fact-types"></a>事实类型  
 规则引擎对访问.NET 事实相对于时间要花费数来访问 XML 和数据库事实的更少的时间。 如果你有一种策略中使用.NET 或 XML 或数据库事实，您应考虑使用.NET 事实以提高性能。  
  
## <a name="data-table-vs-data-connection"></a>与数据连接的数据表  
 当数据集的大小很小 (< 10 个）， **TypedDataTable**绑定提供更好的性能比**该组**绑定。 但是，**该组**绑定更好地执行比**TypedDataTable**绑定时数据集很大 （大于或等于 10 行大约）。 因此，你应确定是否使用**该组**绑定或**TypedDataTable**绑定基于数据集的估计大小。  
  
## <a name="fact-retrievers"></a>事实检索器  
 事实检索器实现标准方法通常用来提供到规则引擎的长期和渐变事实数据之前执行策略。 引擎将缓存这些事实，并在多个执行循环中使用它们。 而不是提交的静态或相当静态事实每次调用的规则引擎，你应创建的事实检索器第一次，提交这一事实，然后更新仅在必要时的内存中的事实。  
  
## <a name="rule-priority"></a>规则的优先级  
 优先级设置的任何一侧的范围规则可以**0**，有了更多具有更高的优先级。 从最高优先级到最低优先级的顺序执行操作。 当策略都实现通过使用正向链接行为**断言/更新**调用，链接，可优化通过使用的优先级设置。 例如，假定**Rule2**具有设置的一个值的依赖关系**规则 1**。 提供**规则 1**更高的优先级意味着**Rule2**将仅执行后**规则 1**激发和更新的值。 相反，如果**Rule2**已分配更高的优先级，它无法触发一次，并显示后再次然后激发**规则 1**触发并更新这一事实， **Rule2**使用条件。 尽管这可以提供正确的结果，让**规则 1**的优先级高于在此方案中将提供更好的性能。  
  
## <a name="update-calls"></a>更新调用  
 Update 函数会导致使用的更新的事实数据进行重新求值的所有规则。 更新函数调用可能开销大，尤其是在更新事实数据时，一大组规则进行重新计算。 在一些情况下此行为可以避免这样做。 例如，请考虑以下规则。  
  
 **规则 1:**  
  
```  
IF PurchaseOrder.Amount > 5   
THEN StatusObj.Flag = true; Update(StatusObj)  
```  
  
 **Rule2:**  
  
```  
IF PurchaseOrder.Amount <= 5   
THEN StatusObj.Flag = false; Update(StatusObj)  
```  
  
 策略使用的所有剩余规则**StatusObj.Flag**在其条件。 因此，当**更新**上调用**StatusObj**对象，将会重新计算所有规则。 任意值**量**字段为，除之外的所有规则**规则 1**或**Rule2**两次，计算一次之前**更新**调用和一次之后**更新**调用。  
  
 若要缓解关联开销，你可以设置的值**标志**字段**false**之前调用的策略和仅限然后使用**规则 1**中设置标志的策略. 在这种情况下，**更新**才会调用的值**量**字段大于 5，和**更新**如果，将不会调用函数的值**量**小于或等于 5。 因此，所有规则除**规则 1**或**Rule2**计算两次才的值**量**字段大于 5。  
  
## <a name="usage-of-logical-or-operators"></a>逻辑 OR 运算符的使用情况  
 在条件中使用越来越多的逻辑 OR 运算符创建展开规则引擎的分析网络的其他排列。 从性能角度看，你完全了解将条件拆分为不包含逻辑 OR 运算符的原子规则。  
  
## <a name="caching-settings"></a>缓存设置  
 规则引擎会使用两个缓存。 更新服务使用的第一个和第二个由每个 BizTalk 进程。 第一次使用策略时，BizTalk 过程从更新服务请求的策略信息。 更新服务从规则引擎数据库中检索的策略信息、 其进行缓存和到 BizTalk 进程返回的信息。 BizTalk 进程创建基于该信息的策略对象，并将该策略对象存储在缓存中，关联的规则引擎实例完成执行的策略时。 当再次调用相同的策略时，BizTalk 进程将重用缓存中的策略对象，如果有的话。 同样，如果 BizTalk 过程从更新服务请求有关策略的信息，更新服务查找其缓存中的策略信息是否可用。 每隔 60 秒，更新服务还检查是否已在数据库中的策略的任何更新。 如果有任何更新，更新服务检索信息，并缓存更新的信息。  
  
 与这些缓存相关的规则引擎的三个优化参数： **CacheEntries**， **CacheTimeout**，和**PollingInterval**。 您可以在注册表或配置文件中为这些参数指定值。 值**CacheEntries**参数是缓存中的最大项数，默认设置为值为 32。 你可能想要的值增加**CacheEntries**参数来提高某些方案中的性能。 例如，假设你重复; 使用 40 策略你可以增加的值**CacheEntries**为 40 以提高性能的参数。 这样可以允许更新服务维护的最多 40 策略在内存中的缓存详细信息。  
  
 值**CacheTimeout**是以秒为单位，在更新服务缓存中维护一个条目的时间。 换而言之， **CacheTimeout**的策略不所引用的情况下，在缓存中保留多长时间的缓存项引用值。 默认值**CacheTimeout**参数为 3600 秒或 1 小时。 这意味着，如果一小时内未引用的缓存项，该条目并被删除。 在某些情况下，它可能是有益的值增加**CacheTimeout**参数来提高性能。 例如，如果每两小时调用一个策略，则策略执行的性能将提高通过增加**CacheTimeout**参数大于两个小时的值。  
  
 **PollingInterval**的规则引擎的参数以秒为单位的更新服务检查更新的规则引擎数据库中定义的时间。 默认值为**PollingInterval**参数为 60 秒。 如果你知道策略未在所有更新或更新时极少数情况下，您可以更改此参数为更高版本的值，以提高性能。  
  
## <a name="sideeffects-property"></a>SideEffects 属性  
 **ClassMemberBinding**， **DatabaseColumnBinding**，和**XmlDocumentFieldBinding**类具有名为的属性**SideEffects**. 此属性确定是否缓存绑定字段的值、成员或列。 默认值**SideEffects**中的属性**DatabaseColumnBinding**和**XmlDocumentFieldBinding**类**false**. 默认值**SideEffects**中的属性**ClassMemberBinding**类是**true**。 因此，如果 XML 文档字段或数据库表的列是在策略中第二次访问或稍后访问的，则其值从缓存中检索。 不过，如果 .NET 对象的成员是第二次访问或稍后访问的，其值从 .NET 对象检索，而不是从缓存中检索。 设置**SideEffects** .NET 属性**ClassMemberBinding**到**false**将提高性能，因为从缓存中检索字段的值第二次及以上版本。 您只能通过编程方式来完成此步骤。 业务规则编辑器工具不会公开**SideEffects**属性。  
  
## <a name="instances-and-selectivity"></a>实例和选择性  
 **XmlDocumentBinding**， **ClassBinding**，和**DatabaseBinding**类具有两个属性：**实例**和**选择性**。 Instances 的值是工作内存中类的实例的预期数目。 值**选择性**是成功传递的规则条件的类实例的百分比。 规则引擎使用这些值来优化条件计算，这样在条件计算中最初尽可能使用最少的实例，以后再使用其余的实例。 如果必须事先了解的对象的实例数，请设置**实例**属性与此值会提高性能。 同样，如果必须事先了解这些对象传递条件的百分比，则设置**选择性**属性与此值会提高性能。 只能通过编程方式来设置这些参数的值。 业务规则编辑器工具不公开这些属性。  
  
## <a name="see-also"></a>另请参阅  
 [优化 BizTalk Server 性能](../technical-guides/optimizing-biztalk-server-performance.md)