---
title: Update1 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- Update function [Business Rules Engine]
- Update function [Business Rules Engine], TypedXMLDocument
- Update function [Business Rules Engine], TypedData table
- Update function [Business Rules Engine], .NET objects
- .NET objects
- Update function [Business Rules Engine], DataConnection
ms.assetid: 939e45dc-6433-42f3-a336-8f3c247417ac
caps.latest.revision: 10
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: ccb9c8e8b75bc67954c30bf2b4a6e6ff39b3ee01
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "37008822"
---
# <a name="update"></a>Update
当**更新**调用函数对象，该对象会重新添加到引擎会重新评估，基于新数据和状态。 该对象可以是类型**TypedXmlDocument**或.NET 类或**DataConnection**或**TypedDataTable**。  
  
 此外可以使用**更新**函数来提高引擎性能并防止无限循环方案，如本主题中所述。  
  
 通常情况下，使用**Assert**规则引擎工作内存中放置一个新的对象并使用**更新**更新工作内存中已经存在的对象。 当您添加新的对象时，会评估所有规则的条件。 当您更新现有对象时，仅重新评估使用已更新事实的条件，并且如果这些条件评估结果为真，则会将操作添加到议程中。  
  
## <a name="using-update-function-on-net-facts"></a>对 .NET 事实使用更新功能  
 现以下面两个规则举例说明。 假设的对象**ItemA**并**ItemB**工作内存中已存在。 规则 1 评估**Id**上的属性**ItemA**，设置**Id**属性**ItemB**，然后重新添加和**ItemB**在更改后。 当**ItemB**重新添加，它被视为新对象和引擎将重新评估使用对象的所有规则**ItemB**谓词或操作中。 这可确保，是对的新值重新计算规则 2 **ItemB.Id**，按照中的规则 1。 规则 2 可能已失败它已计算，但计算结果为第一次 **，则返回 true**第二次计算。  
  
### <a name="rule-1"></a>规则 1  
  
```  
IF ItemA.Id == 1  
THEN ItemB.Id = 2  
Assert(ItemB)  
```  
  
### <a name="rule-2"></a>规则 2  
  
```  
IF ItemB.Id == 2  
THEN ItemB.Value = 100  
```  
  
 通过将对象重新添加到工作内存的功能，用户可以显式控制正向链接方案中的行为。 而此示例中重新添加对象的副作用是还需要重新评估规则 1。 因为**ItemA.Id**未更改，规则 1 评估结果仍为**true**并**assert （itemb)** 操作会重新触发。 而这会导致规则产生无穷循环。  
  
> [!NOTE]
>  重新计算规则的默认最大循环计数为 2 ^32。 对于某些规则，策略执行可能会持续很长时间。 可以通过调整减少计数**最大执行循环深度**属性的策略版本。  
  
 您需要能够将对象重新添加而无需创建无限循环，并**更新**函数提供了此功能。 喜欢 reassert**更新**函数执行**Retract**并**Assert**的关联的对象实例中，这都已更改规则操作，但有两个主要区别：  
  
- 对于只在操作中（而不在谓词中）使用实例类型的规则，其议程的操作将保留在议程中。  
  
- 只在操作中使用实例类型的规则将不会重新进行评估。  
  
  因此，只在谓词中或者既在谓词中也在操作中使用实例类型的规则将会重新进行评估，并且它们的操作也将根据需要添加到议程中。  
  
  更改上面的示例使用**更新**函数还可确保只有规则 2 会重新评估，因为**ItemB**规则 2 的条件中使用。 不重新计算规则 1，因为**ItemB**仅用在规则 1，消除了循环情况的操作。  
  
### <a name="rule-1"></a>规则 1  
  
```  
IF ItemA.Id == 1  
THEN ItemB.Id = 2  
Update(ItemB)  
```  
  
### <a name="rule-2"></a>规则 2  
  
```  
IF ItemB.Id == 2  
THEN ItemB.Value = 100  
```  
  
 但是，它仍然可能会创建循环。 例如，考虑以下规则：  
  
### <a name="rule-1"></a>规则 1  
  
```  
IF ItemA.Id == 1  
THEN ItemA.Value = 20  
Update(ItemA)  
```  
  
 因为**ItemA**用于在谓词中，它会重新评估时**更新**上调用**ItemA**。 如果的值**ItemA.Id**不会更改到其他位置，规则 1 仍将评估为**true**，从而导致**更新**再一次调用 a规则设计器必须确保不会创建此类循环情况。  
  
 根据规则性质的不同，实现方法也会不同。 下面是解决上述示例中的问题的简单机制。  
  
 **更新**可能会在类中，引用业务规则编辑器中使用函数与一样**Assert**， **Retract**，或**RetractByType**函数。  
  
### <a name="rule-1"></a>规则 1  
  
```  
IF ItemA.Id == 1 and ItemA.Value != 20  
THEN ItemA.Value = 20  
Update(ItemA)  
```  
  
 在添加复选**ItemA.Value**阻止规则 1 评估结果为**true**再次规则 1 的操作第一次执行后。  
  
## <a name="using-update-function-on-xml-facts"></a>对 XML 事实使用更新功能  
 现以下面两个规则举例说明。 假定 规则 1 评估采购订单消息中项目的总数，如果总数大于或等于 10，规则 2 便将状态设置为“需要批准”。  
  
### <a name="rule-1"></a>规则 1  
  
```  
IF 1 == 1  
THEN ProcessPO.Order:/Order/Items/TotalCount = (ProcessPO.Order:/Order/Items/TotalCount + ProcessPO:/Order/Items/Item/Count)  
```  
  
### <a name="rule-2"></a>规则 2  
  
```  
IF ProcessPO.Order:/Order/Items/TotalCount >= 10  
THEN ProcessPO.Order:/Order/Status = "Needs approval"  
```  
  
 如果将以下采购订单 (PO) 消息传递作为此策略的输入，你发现即使总项计数为 14，状态未设置为"需要批准"。 这是因为，只在开始评估 rule2 时的值**TotalCount**字段为 0，且不评估规则每次更新时可用的总数。 有条件重新计算每次**TotalCount**是更新，需要调用**更新**函数在父节点 (**项**) 的修改后的节点 (**TotalCount**)。 如果您按照如下所示更改规则 1，并对其进行多次测试，则您应该看到状态字段被设置成“需要批准”。  
  
```  
<ns0:Order xmlns:ns0="http://ProcessPO.Order">  
    <Items>  
        <Item>  
            <Id>ITM1</Id>  
            <Count>2</Count>  
        </Item>  
        <Item>  
            <Id>ITM2</Id>  
            <Count>5</Count>  
        </Item>  
        <Item>  
            <Id>ITM3</Id>  
            <Count>7</Count>  
        </Item>  
        <TotalCount>0</TotalCount>  
    </Items>  
    <Status>No approval needed</Status>  
</ns0:Order>  
```  
  
 已修改**规则 1**如下所示：  
  
### <a name="rule-1"></a>规则 1  
  
```  
IF 1 == 1  
THEN ProcessPO.Order:/Order/Items/TotalCount = (ProcessPO.Order:/Order/Items/TotalCount + ProcessPO:/Order/Items/Item/Count) AND  
Update(ProcessPO.Order:/Order/Items)  
```  
  
## <a name="using-update-function-on-database-facts"></a>对数据库事实使用更新功能  
  
### <a name="typeddatatable"></a>TypedDataTable  
 如果**更新**上调用**TypedDataTable**，**更新**上关联的所有引擎将调用**TypedDataRows**。 **更新**也可能在单个上称为**TypedDataRows**。  
  
### <a name="dataconnection"></a>DataConnection  
 更新**DataConnection**不受支持。 使用**Assert**相反。  
  
## <a name="see-also"></a>请参阅  
 [引擎控制函数](../core/engine-control-functions.md)