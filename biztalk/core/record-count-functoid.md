---
title: 记录计数 Functoid |Microsoft 文档
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- Max Occurs property
- Record Count functoids
ms.assetid: e6aab13f-afbe-4401-abbe-020570e2ff16
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 10094a006e1b1c19f90731130e1e05b0392c0e45
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65398063"
---
# <a name="record-count-functoid"></a>“记录计数”Functoid
**记录计数**functoid 计数输入的实例消息中的记录。  
  
 **记录计数**functoid 有一个输入和一个输出。 输入是源自源架构中某个循环记录的链接。 输出**记录计数**functoid 是实际输入的实例消息中的循环记录的计数。  
  
 循环记录与输入实例消息中重复任意次数的元素相对应。 例如，在采购订单，**项**元素可能会出现多次。 并且，**项**元素可能包括产品、 说明、 价格和数量。 下面的代码显示了此类采购订单的一个简单示例：  
  
```  
<ns0:PurchaseOrder xmlns:ns0="http://RecordFunctoid.PurchaseOrder">  
    <From>Kevin F. Browne</From>  
    <To>Northwind Traders</To>  
    <LineItems>  
        <Item>  
            <Product>Laptop Computer</Product>  
            <Description>Thin profile laptop</Description>  
            <Price>1999.95</Price>  
            <Quantity>1</Quantity>  
        </Item>  
        <Item>  
            <Product>Monitor Swipes</Product>  
            <Description>Disposable monitor swipes</Description>  
            <Price>3.95</Price>  
            <Quantity>10</Quantity>  
        </Item>  
    </LineItems>  
</ns0:PurchaseOrder>  
```  
  
 **Max Occurs**属性**项**记录设置为不受限制。 这指示**项**记录循环和 BizTalk 映射程序编译时循环，该记录。  
  
 假设你想要查找的总数**项**元素中的采购订单输入实例消息并将结果放在输出实例消息中的字段。  
  
 下图显示**记录计数**functoid 对传入的采购订单中的项的数目进行计数，然后将该值放**ItemCount**字段**SummedPO**输出实例消息。  
  
 ![显示使用情况的记录计数 functoid 的映射。](../core/media/recordcountfunctoid.gif "recordcountfunctoid")  
“记录计数”Functoid 映射  
  
 请注意， **Max Occurs**属性**项**记录将**unbounded**。 这指示**项**记录循环和 BizTalk 映射程序编译时循环，该记录。  
  
 对于前面的示例采购订单实例消息，其中包含两个**项**元素、 的值**ItemCount**字段将设置为 2。  
  
```  
<ns0:SummedPO xmlns:ns0="http://RecordCountFunctoid.SummedPO">  
    <From>Kevin F. Browne</From>  
    <To>Northwind Traders</To>  
    <POTotal>2039.45</POTotal>  
    <ItemCount>2</ItemCount>  
</ns0:SummedPO>  
```  
  
> [!NOTE]
>  你还可以使用**记录计数**functoid 重复字段元素进行计数。 不仅仅限于记录。  
  
## <a name="see-also"></a>另请参阅  
 [如何在向地图添加记录计数 Functoid](../core/how-to-add-record-count-functoids-to-a-map.md)   
 [高级的 Functoid](../core/advanced-functoids.md)   
 [索引 Functoid](../core/index-functoid.md)   
 [迭代 Functoid](../core/iteration-functoid.md)   
 [循环 Functoid](../core/looping-functoid.md)