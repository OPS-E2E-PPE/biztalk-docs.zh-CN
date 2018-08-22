---
title: 值映射 （拼合） Functoid |Microsoft 文档
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- Value Mapping (Flattening) functoids
ms.assetid: d30c3ffe-d3ed-46fd-a692-cd26d042033c
caps.latest.revision: 9
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: d17d5d64409cd434075dfd4c556209864784e4d5
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22287869"
---
# <a name="value-mapping-flattening-functoid"></a>“值映射(平展)”Functoid
**值映射 （平展）** functoid，可通过将多个记录转换为单个记录平展输入的实例消息的一部分。 在转换 Microsoft Commerce Server 目录时通常执行此操作。  
  
> [!NOTE]
>  **值映射 （平展）** 不应与组合 functoid**循环**functoid 或**表循环**functoid。 如果它们结合使用，这会导致的编译的地图，假定循环依赖关系如下的目标节点没有源**循环**或**表循环**functoid。  
  
 下面的代码显示了部分目录，其中列出了改型产品，改型产品的每一个特征都记录在单独的记录中。  
  
```  
<ns0:Root xmlns:ns0="http://ValueMappingFlat.ProductsIn">  
    <ProductVariant ListPrice="99.99" ID="45-01">  
        <Feature Name="Material" Value="Leather" />  
        <Feature Name="Color" Value="Black" />  
    </ProductVariant>  
    <ProductVariant ListPrice="69.99" ID="45-02">  
        <Feature Name="Material" Value="Vinyl" />  
        <Feature Name="Color" Value="Brown" />  
    </ProductVariant>  
</nso0:Root>  
```  
  
 平展目录的此部分将转换**功能**记录合并到的属性**ProductVariant**记录。  
  
```  
<ns0:Root xmlns:ns0="http://ValueMappingFlat.ProductsOut">  
    <ProductVariant ListPrice="99.99" ID="45-01" Material="Leather" Color="Black" />  
    <ProductVariant ListPrice="69.99" ID="45-02" Material="Vinyl" Color="Brown" />  
</ns0:Root>  
```  
  
 下图显示的地图，执行此转换。  
  
 ![映射源记录使用 functoid。](../core/media/valuemappingflattenfunctoid.gif "valuemappingflattenfunctoid")  
“值映射(平展)”Functoid 映射  
  
 **值映射 （平展）** functoid 返回其第二个参数的值，如果其第一个参数为 true。 此映射中第一个**相等**functoid 测试以查看是否**名称**属性等于"材料"。 如果该属性值等于"材料"**相等**functoid 返回**True**。 反过来，这会导致**值映射 （平展）** functoid 将的值分配**值**到输出的消息中的字段属性。  
  
## <a name="see-also"></a>另请参阅  
 [如何添加值映射到图 （拼合） Functoid](../core/how-to-add-value-mapping-flattening-functoids-to-a-map.md)   
 [平面架构到目录](../core/flat-schema-to-catalog.md)   
 [高级的 Functoid](../core/advanced-functoids.md)