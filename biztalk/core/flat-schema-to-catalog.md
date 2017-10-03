---
title: "平面到目录的架构 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: a0e37afa-2329-4691-9fa1-82b8c7bcd59a
caps.latest.revision: "8"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 0f3a45ad66ca10ab829a4cc7279891487124c3cc
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="flat-schema-to-catalog"></a>将平面架构转换为目录

## <a name="overview"></a>概述
你可以使用**循环**functoid 来映射到多个记录的单个记录转换为分层的架构的平面架构。 将平面架构转换为 Microsoft Commerce Server 目录时通常会执行此操作。  
  
 下面的代码演示列出产品变体，其每个变体作为其自己的记录目录的一部分。  
  
```  
<ns0:Root xmlns:ns0="http://ValueMappingFlattening.FlatCatalog">  
    <ProductVariant ListPrice="99.99" ID="45-01" Material="Leather" Color="Black" />  
    <ProductVariant ListPrice="69.99" ID="45-02" Material="Vinyl" Color="Brown" />  
</ns0:Root>  
```  
  
 展开该目录的此部分将转换部分或全部**ProductVariant**到记录的属性。  
  
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
  
 下图显示的地图，执行此转换。  
  
 ![显示使用情况的循环 functoid 的映射。] (../core/media/loopingflattenfunctoid.gif "loopingflattenfunctoid")  
“循环”Functoid，平面架构映射  

## <a name="set-the-schema"></a>设置架构  
 若要此类型映射正常工作，您必须执行以下操作：  
  
-   为连接到每个链接**名称**目标架构中字段中，设置链接属性以将该名称复制的源架构。 有关详细信息，请参阅[配置链接](../core/configuring-links.md)。 另请参阅**链接属性** [!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)]。
  
-   为连接到每个链接**值**目标架构中字段中，设置要复制的值 （默认值） 的链接属性的源架构。  
  
-   用于链接连接**循环**到名为记录 functoid**功能**目标架构中设置的目标架构链接属性以匹配链接的上下。  
  
 有关此映射的反向，将目录架构转换为平面架构，请参阅[值映射 （平展） Functoid](../core/value-mapping-flattening-functoid.md)。  
  
## <a name="see-also"></a>另请参阅  
 [如何添加循环到图 Functoid](../core/how-to-add-looping-functoids-to-a-map.md)   
 [循环 Functoid](../core/looping-functoid.md)   
 [映射 （拼合） Functoid 的值](../core/value-mapping-flattening-functoid.md)