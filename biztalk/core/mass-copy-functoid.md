---
title: 批量复制 Functoid |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- anyAttribute node
- Mass Copy functoids, about Mass Copy functoids
- any node
- Mass Copy functoids
ms.assetid: 228ff569-2e21-4e81-b564-6936241cdf6b
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: ffd3cb15f74bef774a9794d0fa6dbe910971f1b3
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65380046"
---
# <a name="mass-copy-functoid"></a>批量复制 Functoid
**批量复制**functoid，映射可使用包含的架构**任何**并**anyAttribute**元素。 从本质上讲，这些元素是 XML 架构定义语言为匹配未知的结构或属性中提供的通配符。  
  
 除了处理未知结构的数据**批量复制**functoid，您可以简化架构开发： 需详细指定仅将处理的架构部分。  
  
 **批量复制**functoid 复制到连接到源架构节点相对应的输入的实例消息中的元素**批量复制**functoid。 该 functoid 还将复制其子结构的所有和目标架构中所链接节点的输出实例消息中重新创建。 因此，您还可以使用**批量复制**functoid 复制任何具有相同子结构的源和目标记录。  
  
 下图显示**批量复制**映射中使用的 functoid。  
  
 ![说明如何使用批量复制 functoid](../core/media/masscopyfunctoid.gif "masscopyfunctoid")  
批量复制 Functoid 映射  
  
 请考虑以下输入的实例消息。  
  
```  
<ns0:Root xmlns:ns0="http://MassCopy.ComplexDocument">  
    <PurchaseOrder>  
        <From>Kevin F. Browne</From>  
        <To>Northwind Traders</To>  
        <LineItems>  
            <Item>  
                <Product>Laptop Computer</Product>  
                <Description>Thin profile laptop</Description>  
                <Price>1999.95</Price>  
                <Quantity>1</Quantity>  
            </Item>  
        </LineItems>  
    </PurchaseOrder>  
</ns0:Root>  
```  
  
 如果使用上面的映射来处理此消息，输出实例消息将具有与输入的实例消息相同。  
  
## <a name="see-also"></a>请参阅  
 [如何向映射添加批量复制 Functoid](../core/how-to-add-mass-copy-functoids-to-a-map.md)   
 [高级的 Functoid](../core/advanced-functoids.md)   
 [基本 Functoid](../core/basic-functoids.md)   
 [与“任何元素”和“任何属性”节点相关的链接](../core/links-to-and-from-the-any-element-and-anyattribute-nodes.md)