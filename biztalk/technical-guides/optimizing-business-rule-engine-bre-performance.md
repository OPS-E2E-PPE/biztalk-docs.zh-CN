---
title: 优化业务规则引擎 (BRE) 性能 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: c271b059-174d-4e8b-88b5-c3f408a97f1f
caps.latest.revision: 4
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 18fdd1e642d211a79f591f5029dcd37ac618011b
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65242633"
---
# <a name="optimizing-business-rule-engine-bre-performance"></a>优化业务规则引擎 (BRE) 性能
在 BizTalk Server 解决方案中实施业务规则引擎 (BRE) 时，应考虑以下因素：  
  
## <a name="fact-types"></a>事实类型  
 规则引擎需要访问.NET 事实的时间访问 XML 和数据库事实所花费更少的时间。 如果您可以在策略中使用.NET 或 XML 或数据库事实的选择，应考虑使用.NET 事实会提高性能。  
  
## <a name="data-table-vs-data-connection"></a>数据连接和数据表  
 当数据集的大小很小 （< 10 个左右）， **TypedDataTable**绑定提供了更好的性能比**DataConnection**绑定。 但是， **DataConnection**绑定的性能更好地比**TypedDataTable**绑定时数据集较大 （大于或等于 10 行大约）。 因此，应决定是使用**DataConnection**绑定或**TypedDataTable**绑定基于数据集的估计大小。  
  
## <a name="fact-retrievers"></a>事实检索器  
 事实检索器实现通常用于提供长期和缓慢变化的事实，到规则引擎策略执行前的标准方法。 引擎将缓存这些事实，并使用多个执行循环。 而不是提交一个静态的或相当静态的事实每次调用规则引擎，则应创建事实检索器的第一次提交这一事实，然后更新仅在必要时的内存中的事实。  
  
## <a name="rule-priority"></a>规则优先级  
 优先级设置规则范围的任何一侧**0**，更大的数字越大优先级越高。 从最高优先级到最低优先级的顺序执行操作。 当此策略将实现通过使用正向链接行为**Assert/Update**可以使用优先级设置优化链接的调用。 例如，假定**Rule2**设置的值具有的依赖项**Rule1**。 为提供**Rule1**更高的优先级意味着**Rule2**将仅执行后**Rule1**触发和更新值。 相反，如果**Rule2**了更高的优先级，它可能触发一次，而且并触发后**Rule1**触发和更新这一事实的**Rule2**使用的条件。 虽然这可以提供正确的结果，使**Rule1**在此方案中更高的优先级将提供更好的性能。  
  
## <a name="update-calls"></a>Update 调用  
 Update 函数会导致使用的已更新事实数据进行重新求值的所有规则。 Update 函数调用可能成本高昂，尤其是当更新事实数据时将被重新计算一大组规则。 有些情况下，可以避免此行为。 例如，请考虑以下规则。  
  
 **规则 1:**  
  
```  
IF PurchaseOrder.Amount > 5   
THEN StatusObj.Flag = true; Update(StatusObj)  
```  
  
 **规则 2:**  
  
```  
IF PurchaseOrder.Amount <= 5   
THEN StatusObj.Flag = false; Update(StatusObj)  
```  
  
 策略使用的所有其余规则**StatusObj.Flag**在其条件中。 因此，当**更新**上调用**StatusObj**对象，将重新计算所有规则。 任何值**量**字段是，除了**Rule1**或**Rule2**计算两次，一次之前**更新**调用和一次之后**更新**调用。  
  
 若要缓解关联开销，你可以设置的值**标志**字段**false**之前调用策略，然后使用仅**Rule1**在策略中设置标志. 在这种情况下，**更新**才会调用的值**量**字段大于 5，并且**更新**如果不调用函数的值**量**小于或等于 5。 因此，所有规则除外**Rule1**或**Rule2**计算两次才的值**量**字段大于 5。  
  
## <a name="usage-of-logical-or-operators"></a>逻辑 OR 运算符的使用情况  
 在条件中使用越来越多的逻辑 OR 运算符可以创建其他排列，从而扩展规则引擎的分析网络。 从性能角度看，您完全了解条件拆分不包含逻辑 OR 运算符的原子规则。  
  
## <a name="caching-settings"></a>缓存设置  
 规则引擎使用两个缓存。 更新服务使用的第一个和第二个由每个 BizTalk 进程。 首次使用一个策略，BizTalk 进程从更新服务请求的策略信息。 更新服务从规则引擎数据库中检索策略信息、 对其进行缓存和将信息返回到 BizTalk 进程。 BizTalk 进程创建基于该信息的策略对象，并将该策略对象存储在缓存中，相关联的规则引擎实例完成后执行策略。 再次调用同一个策略时，BizTalk 进程重用缓存中的策略对象，如果有可用。 同样，如果 BizTalk 进程从更新服务请求有关策略的信息，更新服务将查找其缓存中的策略信息是否可用。 每隔 60 秒更新服务还会检查是否已对数据库中的策略的任何更新。 如果有任何更新，更新服务检索信息，并将缓存的更新的信息。  
  
 有三个规则引擎与这些缓存相关的优化参数：**CacheEntries**， **CacheTimeout**，和**PollingInterval**。 在注册表或配置文件中，可以指定这些参数的值。 值**CacheEntries**参数是在缓存中的最大项数，默认情况下设置为值为 32。 你可能想要增加的价值**CacheEntries**参数，以提高某些方案中的性能。 例如，假设重复; 使用 40 个策略可能的值增加**CacheEntries**至 40 以提高性能的参数。 这将允许更新服务维护的最多 40 个策略在内存中的缓存详细信息。  
  
 值**CacheTimeout**是以秒为单位的更新服务缓存中维护一个条目的时间。 换而言之， **CacheTimeout**值指的多长时间的缓存项的策略不被引用的情况下维护在缓存中。 默认值**CacheTimeout**参数为 3600 秒或 1 小时。 这意味着如果一小时内未引用的缓存项，则删除该条目。 在某些情况下，可能会有所帮助增加的价值**CacheTimeout**参数，以提高性能。 例如，如果每隔两小时调用策略，策略执行的性能将提高通过增加**CacheTimeout**参数的值大于两小时。  
  
 **PollingInterval**规则引擎的参数以秒为单位的更新服务检查更新的规则引擎数据库中定义的时间。 默认值为**PollingInterval**参数为 60 秒。 如果您知道策略不在所有更新或者很少更新，也可以更改此参数为更高版本的值以提高性能。  
  
## <a name="sideeffects-property"></a>SideEffects 属性  
 **ClassMemberBinding**， **DatabaseColumnBinding**，并**XmlDocumentFieldBinding**类具有一个名为属性**SideEffects**. 此属性确定是否缓存绑定的字段、 成员或列的值。 默认值**SideEffects**属性中的**DatabaseColumnBinding**并**XmlDocumentFieldBinding**类是**false**. 默认值**SideEffects**属性中的**ClassMemberBinding**类是**true**。 因此，XML 文档的字段或数据库表的列访问时的第二次或更高版本的策略内，从缓存检索其值。 但是，第二次或更高版本访问.NET 对象的成员时，从.NET 对象，而不是从缓存检索的值。 设置**SideEffects**的.NET 属性**ClassMemberBinding**到**false**会提高性能，因为从缓存中检索的字段的值第二次及更高版本。 您可以仅执行此操作以编程方式。 业务规则编辑器工具不会公开**SideEffects**属性。  
  
## <a name="instances-and-selectivity"></a>Instances 和 selectivity  
 **XmlDocumentBinding**， **ClassBinding**，并**DatabaseBinding**类具有两个属性：**实例**并**选择性**。 实例的值为预期的工作内存中的类的实例数。 值**选择性**是成功传递规则条件的类实例的百分比。 规则引擎使用这些值来优化条件评估，以便在条件计算中首次使用最少可能实例，然后使用剩余的实例。 如果您有经验的对象的实例数，则将设置**实例**属性设置为该值也会提高性能。 同样，如果必须预先知道满足条件这些对象的百分比，则设置**选择性**属性设置为该值也会提高性能。 只能以编程方式设置这些参数的值。 业务规则编辑器工具不公开它们。  
  
## <a name="see-also"></a>请参阅  
 [优化 BizTalk Server 性能](../technical-guides/optimizing-biztalk-server-performance.md)