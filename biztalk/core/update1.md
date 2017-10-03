---
title: "Update1 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- Update function [Business Rules Engine]
- Update function [Business Rules Engine], TypedXMLDocument
- Update function [Business Rules Engine], TypedData table
- Update function [Business Rules Engine], .NET objects
- .NET objects
- Update function [Business Rules Engine], DataConnection
ms.assetid: 939e45dc-6433-42f3-a336-8f3c247417ac
caps.latest.revision: "10"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 3a4ea10e72be2a39eedaafa0e00c8f8ac630393b
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="update"></a>Update
当**更新**调用函数对象，该对象 reasserted 引擎重新评估，基于新数据和状态。 对象可以是类型**TypedXmlDocument**或.NET 类或**该组**或**TypedDataTable**。  
  
 你还可以使用**更新**函数以提高引擎性能并防止无限循环方案，如本主题中所述。  
  
 通常情况下，使用**断言**规则引擎中，工作内存中将新的对象并使用**更新**更新工作内存中的现有对象。 当您添加新的对象时，会评估所有规则的条件。 当您更新现有对象时，仅重新评估使用已更新事实的条件，并且如果这些条件评估结果为真，则会将操作添加到议程中。  
  
## <a name="using-update-function-on-net-facts"></a>对 .NET 事实使用更新功能  
 现以下面两个规则举例说明。 假设对象**ItemA**和**ItemB**工作内存中已存在。 规则 1 的计算结果**Id**属性**ItemA**，设置**Id**属性**ItemB**，然后 reasserts **ItemB**更改后。 当**ItemB** reasserted，它将被视为新的对象和引擎重新评估使用对象的所有规则**ItemB**中的谓词或操作。 这可确保规则 2 会针对的新值重新评估**ItemB.Id**，在规则 1 中进行设置。 规则 2 可能已失败第一次它已计算，但计算结果为**true**计算第二次。  
  
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
  
 通过将对象重新添加到工作内存的功能，用户可以显式控制正向链接方案中的行为。 而此示例中重新添加对象的副作用是还需要重新评估规则 1。 因为**ItemA.Id**未更改，规则 1 再次计算结果为**true**和**Assert(ItemB)**操作，将再次引发。 而这会导致规则产生无穷循环。  
  
> [!NOTE]
>  重新计算规则的默认最大循环计数为 2 ^32。 对于某些规则，策略执行无法持续很长时间。 你可以通过调整减少计数**执行循环的最大深度**策略版本的属性。  
  
 若要能够重新对象声明而无需创建无限循环，你需要与**更新**函数提供了此功能。 如重新声明，**更新**函数执行**收回**和**断言**关联的对象实例，其中已更改了规则操作，但有两个主要差异：  
  
-   对于只在操作中（而不在谓词中）使用实例类型的规则，其议程的操作将保留在议程中。  
  
-   只在操作中使用实例类型的规则将不会重新进行评估。  
  
 因此，只在谓词中或者既在谓词中也在操作中使用实例类型的规则将会重新进行评估，并且它们的操作也将根据需要添加到议程中。  
  
 更改该前面的示例，以使用**更新**函数会确保仅规则 2 会重新评估，因为**ItemB**用于规则 2 的条件。 不重新计算规则 1，因为**ItemB**仅用在规则 1，消除循环方案的操作。  
  
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
  
 因为**ItemA**使用在谓词中，它会重新评估时**更新**上调用**ItemA**。 如果值**ItemA.Id**不会更改到其他位置，规则 1 继续的计算结果为**true**，从而导致**更新**再一次调用上 a。规则设计器必须确保不会创建此类循环情况。  
  
 根据规则性质的不同，实现方法也会不同。 下面是解决上述示例中的问题的简单机制。  
  
 **更新**函数可能在类中，引用业务规则编辑器中使用与**断言**，**收回**，或**RetractByType**函数。  
  
### <a name="rule-1"></a>规则 1  
  
```  
IF ItemA.Id == 1 and ItemA.Value != 20  
THEN ItemA.Value = 20  
Update(ItemA)  
```  
  
 上添加检查**ItemA.Value**防止规则 1 评估结果为**true**再次规则 1 的操作在首次执行后。  
  
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
  
 如果您传入以下的采购订单 (PO) 消息输入到此策略，你注意到即使总项计数为 14，状态未设置为"需要审批"。 这是因为，rule2 被评估为只在开始时的值**TotalCount**字段为 0，并且该规则不会评估每次更新时可用的总数。 具有条件重新计算每次**TotalCount**是更新，你需要调用**更新**的父节点上的函数 (**项**) 的修改后的节点 (**TotalCount**)。 如果您按照如下所示更改规则 1，并对其进行多次测试，则您应该看到状态字段被设置成“需要批准”。  
  
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
  
 已修改**规则 1**如下：  
  
### <a name="rule-1"></a>规则 1  
  
```  
IF 1 == 1  
THEN ProcessPO.Order:/Order/Items/TotalCount = (ProcessPO.Order:/Order/Items/TotalCount + ProcessPO:/Order/Items/Item/Count) AND  
Update(ProcessPO.Order:/Order/Items)  
```  
  
## <a name="using-update-function-on-database-facts"></a>对数据库事实使用更新功能  
  
### <a name="typeddatatable"></a>TypedDataTable  
 如果**更新**上调用**TypedDataTable**，**更新**对所有关联引擎将调用**TypedDataRows**。 **更新**还能对单个调用**TypedDataRows**。  
  
### <a name="dataconnection"></a>DataConnection  
 中的更新**该组**不支持。 使用**断言**相反。  
  
## <a name="see-also"></a>另请参阅  
 [引擎控制功能](../core/engine-control-functions.md)