---
title: 成批复制 Functoid |Microsoft 文档
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
ms.openlocfilehash: 2fe0a9bc65369327a17591fb6adecb6bd6105333
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22262653"
---
# <a name="mass-copy-functoid"></a>“批量复制”functoid
**大容量复制**functoid 使你使用包含的架构的映射**任何**和**anyAttribute**元素。 实际上，这些元素是 XML 架构定义语言为匹配未知结构或属性而提供的通配符。  
  
 除了处理具有未知的结构、 数据**大容量复制**functoid，可简化架构开发： 仅将处理的架构部分需要在详细信息中指定。  
  
 **大容量复制**functoid 对应于连接到源架构节点的输入的实例消息中复制元素**大容量复制**functoid。 该 functoid 还可复制其任意或全部子结构，并在目标架构中所链接节点的输出实例消息中重新创建子结构。 因此，你还可以使用**大容量复制**functoid 来复制任何具有相同的子结构的源和目标记录。  
  
 下图显示**大容量复制**functoid 映射中使用。  
  
 ![映射的大容量复制 functoid 用法](../core/media/masscopyfunctoid.gif "masscopyfunctoid")  
“批量复制”Functoid 映射  
  
 请注意以下输入实例消息：  
  
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
  
 如果使用上面的映射处理此消息，则输出实例消息将与输入实例消息相同。  
  
## <a name="see-also"></a>另请参阅  
 [如何在向地图添加大容量复制 Functoid](../core/how-to-add-mass-copy-functoids-to-a-map.md)   
 [高级的 Functoid](../core/advanced-functoids.md)   
 [基本 Functoid](../core/basic-functoids.md)   
 [链接到和从任何元素和 anyAttribute 节点](../core/links-to-and-from-the-any-element-and-anyattribute-nodes.md)