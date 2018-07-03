---
title: 平面架构转换为目录 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: a0e37afa-2329-4691-9fa1-82b8c7bcd59a
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: a1dc8093d477773d5efbab46670bac7e9c839d8d
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "36999038"
---
# <a name="flat-schema-to-catalog"></a>将平面架构转换为目录

## <a name="overview"></a>概述
可以使用**循环**functoid 通过将单个记录映射到多个记录将平面架构转换为分层架构。 将平面架构转换为 Microsoft Commerce Server 目录时通常会执行此操作。  
  
 下面的代码显示了目录，其中列出产品变体，其作为其自己的记录每个变体的一部分。  
  
```  
<ns0:Root xmlns:ns0="http://ValueMappingFlattening.FlatCatalog">  
    <ProductVariant ListPrice="99.99" ID="45-01" Material="Leather" Color="Black" />  
    <ProductVariant ListPrice="69.99" ID="45-02" Material="Vinyl" Color="Brown" />  
</ns0:Root>  
```  
  
 展开目录此部分将转换部分或全部**ProductVariant**为记录的属性。  
  
```  
<ns0:Root xmlns:ns0="http://ValueMappingFlattening.Catalog">  
    <ProductVariant ListPrice="99.99" ID="45-01">  
        <Feature Name="Material" Value="Leather"/>  
        <Feature Name="Color" Value="Black"/>  
    </ProductVariant>  
    <ProductVariant ListPrice="69.99" ID="45-02">  
        <Feature Name="Material" Value="Vinyl"/>  
        <Feature Name="Color" Value="Brown"/>  
    </ProductVariant>  
</ns0:Root>  
```  
  
 下图显示了执行此转换的映射。  
  
 ![演示如何使用循环 functoid 的映射。] (../core/media/loopingflattenfunctoid.gif "loopingflattenfunctoid")  
“循环”Functoid，平面架构映射  

## <a name="set-the-schema"></a>设置的架构  
 若要此类型映射正常工作，您必须执行以下操作：  
  
- 为连接到每个链接**名称**字段目标架构中，源架构链接属性设置为复制名称。 有关详细信息，请参阅[配置链接](../core/configuring-links.md)。 另请参阅**链接属性** [!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)]。
  
- 为连接到每个链接**值**字段目标架构中，源架构链接属性设置为复制值 （默认值）。  
  
- 链接连接**循环**functoid 到名为的记录**功能**在目标架构中，设置目标架构链接属性以匹配的链接上而。  
  
  若要反转此映射，将目录架构转换为平面架构，请参阅[值映射 （平展） Functoid](../core/value-mapping-flattening-functoid.md)。  
  
## <a name="see-also"></a>请参阅  
 [如何添加循环 Functoid 映射](../core/how-to-add-looping-functoids-to-a-map.md)   
 [循环 Functoid](../core/looping-functoid.md)   
 [“值映射（平展）”Functoid](../core/value-mapping-flattening-functoid.md)