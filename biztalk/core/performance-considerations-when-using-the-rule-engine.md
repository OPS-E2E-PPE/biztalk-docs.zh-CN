---
title: 使用规则引擎时的性能注意事项 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 9e9020c2-5152-40f6-940b-d4ce4081f069
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 41501ad852fe30ba54245a26a10e22e42979a1f5
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65262890"
---
# <a name="performance-considerations-when-using-the-rule-engine"></a>使用规则引擎时的性能注意事项
本主题介绍规则引擎如何执行各种方案，并且具有不同的配置/优化参数值。  
  
## <a name="fact-types"></a>事实类型  
 规则引擎需要更少时间来访问 XML 和数据库事实比访问.NET 事实。 如果选择在策略中使用.NET、 XML 或数据库事实，您应考虑使用.NET 事实的更好的性能。  
  
## <a name="data-table-vs-data-connection-binding"></a>数据的表与。数据连接绑定  
 当数据集的大小很小 （少于大约 10 行）， **TypedDataTable**绑定的性能更好地比**DataConnection**绑定。 当数据集较大 （大于或等于大约 10 行）， **DataConnection**绑定的性能更好地比**TypedDataTable**绑定。 因此，应决定是使用**DataConnection**绑定或**TypedDataTable**绑定基于数据集的估计大小。  
  
## <a name="fact-retrievers"></a>事实检索器  
 您可以编写事实检索器 — 实现标准方法，并通常使用它们来提供长期和渐变事实到规则引擎之前执行了策略的对象。 引擎将缓存这些事实，并使用多个执行循环。 而不是调用规则引擎每次提交一个静态的或相当静态的事实，则应创建事实检索器，将这一事实提交第一次，并仅在需要时，然后更新内存中的事实。  
  
## <a name="rule-priority"></a>规则优先级  
 优先级设置规则范围的任何一侧**0**，更大的数字越大优先级越高。 从最高优先级到最低优先级的顺序执行操作。 当此策略将实现通过使用正向链接行为**Assert/Update**可以使用优先级设置优化链接的调用。 例如，假设**Rule2**具有一个值，通过设置该值的依赖项**Rule1**。 为提供**Rule1**更高的优先级意味着**Rule2**后才会执行**Rule1**触发和更新值。 相反，如果**Rule2**是更高的优先级，它可以触发一次，并触发后**Rule1**触发和更新这一事实， **Rule2**条件中使用。 这可能会或可能不会产生正确的结果，但显然触发两次会影响性能与触发一次。  
  
## <a name="update-calls"></a>Update 调用  
 **更新**函数更新事实的规则引擎工作内存中存在并导致在条件中使用已更新的事实重新评估所有规则。 **更新**函数调用可能很昂贵，尤其是如果许多规则需要因更新事实而重新计算。 有些情况下，可以避免不得不重新计算规则。 例如，请考虑以下规则：  
  
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
  
 策略使用的所有其余规则**StatusObj.Flag**在其条件中。 因此，当**更新**上调用**StatusObj**对象，将重新计算所有规则。 任何值**量**字段为，除非所有规则**Rule1**并**Rule2**计算两次，一次之前**更新**调用后, 一次**更新**调用。  
  
 相反，可以设置的值**标志**字段**false**调用策略，则仅使用前**Rule1**在策略中设置标志。 在这种情况下，**更新**才会调用的值**量**字段大于 5，并且**更新**如果金额小于或等于 5 不调用。 因此，所有规则除外**Rule1**并**Rule2**计算两次才的值**量**字段大于 5。  
  
## <a name="use-of-logical-or-operators"></a>使用逻辑 OR 运算符  
 规则引擎进行了优化的执行逻辑**AND**运算符，它重新构造分析的规则在析取范式中因此所**或**运算符仅在最高级别使用。 使用越来越多的逻辑**或**中条件的运算符创建其他排列，从而扩展规则引擎的分析网络，并可能需要很长时间的规则引擎来规范化规则。 以下列表包含此问题的可能解决方法。  
  
-   修改规则为析取范式中因此**或**运算符是仅在最高级别。 请注意，开发了析取范式在业务规则编辑器中的规则可能比较棘手。 您可能想要以编程方式创建规则，请考虑。  
  
-   开发的帮助器组件执行**或**操作并返回一个布尔值，并在规则中使用该组件。  
  
-   请考虑将规则拆分为多个规则和具有规则检查标志由以前执行的规则设置，或者使用一个对象，如以下示例所示添加由以前执行的规则：  
  
    -   规则 1:如果 (1 = = 或 = = 3) 然后 b = true  
  
         规则 2： 如果 (b = = true) 然后...  
  
    -   规则 1:如果 (1 = = 或 = = 3) 然后断言 (新 c())  
  
         规则 2:IF (c.flag == true) THEN …  
  
## <a name="caching-settings"></a>缓存设置  
 规则引擎使用两个缓存。 第一个参数是在更新服务和第二个是在每个 BizTalk 进程。 首次使用一个策略，BizTalk 进程从更新服务请求的策略信息。 更新服务从规则引擎数据库中检索策略信息、 缓存，并将信息返回到 BizTalk 进程。 BizTalk 进程创建基于该信息的策略对象，并将该策略对象存储在缓存中，相关联的规则引擎实例完成后执行策略。 再次调用同一个策略时，BizTalk 进程重用缓存中的策略对象，如果有在缓存中可用。  
  
 同样，如果 BizTalk 进程从更新服务请求有关策略的信息，更新服务首先查找其缓存中的策略信息。 更新服务还会检查每隔 60 秒 （一分钟） 以查看是否已对数据库中的策略的任何更新。 如果有任何更新，更新服务检索信息，并将缓存的更新的信息。  
  
 有三个规则引擎与这些缓存相关的优化参数：**CacheEntries**， **CacheTimeout**，和**PollingInterval**。 在注册表或配置文件中，可以指定这些参数的值。  
  
 值**CacheEntries**是缓存中的最大项数。 默认值**CacheEntries**为 32。 你可能想要增加的价值**CacheEntries**参数，以提高在某些情况下的性能。 例如，假设您重复使用 40 个策略。 在这种情况下你可能想要增加的价值**CacheEntries**至 40 以提高性能。 这将在内存中允许更新服务的最多 40 个策略的缓存详细信息。 此外可以使 BizTalk 服务能缓存多达 40 个在内存中的策略实例。 可能有多个实例中的 BizTalk 服务的缓存策略。  
  
 值**CacheTimeout**是从更新服务缓存条目的时间 （以秒为单位）。 换而言之， **CacheTimeout**值参考了多长时间策略某个缓存项保存在缓存中是否存在任何对它的引用。 默认值**CacheTimeout**为 3600 秒 （1 小时）。 这意味着，如果一小时内未引用的缓存项，将其删除。 在某些情况下，你可能想要增加**CacheTimeout**值以提高性能。 例如，假设将调用策略，每隔两小时。 您可以通过增加的值提高策略执行的性能**CacheTimeout**值超过两个小时以上的参数。  
  
 **PollingInterval**参数的规则引擎更新服务会检查更新的规则引擎数据库的时间间隔 （秒） 定义的时间。 默认值为**PollingInterval**参数为 60 秒 （一分钟）。 如果您知道策略不在所有更新或者很少更新，可以增加此值以提高性能。  
  
## <a name="sideeffects-property"></a>SideEffects 属性  
 **ClassMemberBinding**， **DatabaseColumnBinding**，并**XmlDocumentFieldBinding**类具有一个名为属性**SideEffects**. 此属性确定是否缓存绑定的字段、 成员或列的值。 默认值**SideEffects**属性中的**DatabaseColumnBinding**并**XmlDocumentFieldBinding**类是**false**. 默认值**SideEffects**属性中的**ClassMemberBinding**类是**true**。 因此，XML 文档的字段或数据库表的列访问时的第二次或更高版本的策略内，从缓存检索其值。 但是，第二次或更高版本访问.NET 对象的成员时，从.NET 对象，而不是从缓存检索的值。 设置**SideEffects**的.NET 属性**ClassMemberBinding**到**false**会提高性能，因为从缓存中检索的字段的值第二次及更高版本。 您可以仅执行此操作以编程方式。 业务规则编辑器工具不会公开**SideEffects**属性。  
  
## <a name="instances-and-selectivity"></a>Instances 和 Selectivity  
 **XmlDocumentBinding**， **ClassBinding**，并**DatabaseBinding**类具有两个属性：**实例**并**选择性**。 值**实例**是预期的工作内存中类的实例数。 值**选择性**是成功传递规则条件的类实例的百分比。 规则引擎使用这些值来优化条件评估，以便在条件计算中首次使用最少可能实例，然后使用剩余的实例。 如果您有经验的对象的实例数，则将设置**实例**属性设置为该值也会提高性能。 同样，如果必须预先知道满足条件这些对象的百分比，则设置**选择性**属性设置为该值也会提高性能。 只能以编程方式设置这些参数的值。 业务规则编辑器工具不公开它们。