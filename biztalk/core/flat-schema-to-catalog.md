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
# <a name="flat-schema-to-catalog"></a><span data-ttu-id="7a5cf-102">将平面架构转换为目录</span><span class="sxs-lookup"><span data-stu-id="7a5cf-102">Flat Schema to Catalog</span></span>

## <a name="overview"></a><span data-ttu-id="7a5cf-103">概述</span><span class="sxs-lookup"><span data-stu-id="7a5cf-103">Overview</span></span>
<span data-ttu-id="7a5cf-104">可以使用**循环**functoid 通过将单个记录映射到多个记录将平面架构转换为分层架构。</span><span class="sxs-lookup"><span data-stu-id="7a5cf-104">You can use the **Looping** functoid to convert a flat schema to an hierarchical schema by mapping a single record to multiple records.</span></span> <span data-ttu-id="7a5cf-105">将平面架构转换为 Microsoft Commerce Server 目录时通常会执行此操作。</span><span class="sxs-lookup"><span data-stu-id="7a5cf-105">This is a common operation in converting flat schemas to Microsoft Commerce Server catalogs.</span></span>  
  
 <span data-ttu-id="7a5cf-106">下面的代码显示了目录，其中列出产品变体，其作为其自己的记录每个变体的一部分。</span><span class="sxs-lookup"><span data-stu-id="7a5cf-106">The following code shows a portion of a catalog listing product variants with each variant as its own record.</span></span>  
  
```  
<ns0:Root xmlns:ns0="http://ValueMappingFlattening.FlatCatalog">  
    <ProductVariant ListPrice="99.99" ID="45-01" Material="Leather" Color="Black" />  
    <ProductVariant ListPrice="69.99" ID="45-02" Material="Vinyl" Color="Brown" />  
</ns0:Root>  
```  
  
 <span data-ttu-id="7a5cf-107">展开目录此部分将转换部分或全部**ProductVariant**为记录的属性。</span><span class="sxs-lookup"><span data-stu-id="7a5cf-107">Expanding this portion of the catalog would convert some or all of the **ProductVariant** attributes into records.</span></span>  
  
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
  
 <span data-ttu-id="7a5cf-108">下图显示了执行此转换的映射。</span><span class="sxs-lookup"><span data-stu-id="7a5cf-108">The following figure shows a map that performs this conversion.</span></span>  
  
 <span data-ttu-id="7a5cf-109">![演示如何使用循环 functoid 的映射。] (../core/media/loopingflattenfunctoid.gif "loopingflattenfunctoid")</span><span class="sxs-lookup"><span data-stu-id="7a5cf-109">![Map showing the use of the looping functoid.](../core/media/loopingflattenfunctoid.gif "loopingflattenfunctoid")</span></span>  
<span data-ttu-id="7a5cf-110">“循环”Functoid，平面架构映射</span><span class="sxs-lookup"><span data-stu-id="7a5cf-110">Looping Functoid, Flat Schema Map</span></span>  

## <a name="set-the-schema"></a><span data-ttu-id="7a5cf-111">设置的架构</span><span class="sxs-lookup"><span data-stu-id="7a5cf-111">Set the schema</span></span>  
 <span data-ttu-id="7a5cf-112">若要此类型映射正常工作，您必须执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="7a5cf-112">For this type of map to work correctly, you must do the following:</span></span>  
  
- <span data-ttu-id="7a5cf-113">为连接到每个链接**名称**字段目标架构中，源架构链接属性设置为复制名称。</span><span class="sxs-lookup"><span data-stu-id="7a5cf-113">For each link connecting to the **Name** field in the destination schema, set the source-schema link properties to copy the name.</span></span> <span data-ttu-id="7a5cf-114">有关详细信息，请参阅[配置链接](../core/configuring-links.md)。</span><span class="sxs-lookup"><span data-stu-id="7a5cf-114">For more information, see [Configuring Links](../core/configuring-links.md).</span></span> <span data-ttu-id="7a5cf-115">另请参阅**链接属性** [!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)]。</span><span class="sxs-lookup"><span data-stu-id="7a5cf-115">Also see **Link Properties** [!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)].</span></span>
  
- <span data-ttu-id="7a5cf-116">为连接到每个链接**值**字段目标架构中，源架构链接属性设置为复制值 （默认值）。</span><span class="sxs-lookup"><span data-stu-id="7a5cf-116">For each link connecting to the **Value** field in the destination schema, set the source-schema link properties to copy the value (the default).</span></span>  
  
- <span data-ttu-id="7a5cf-117">链接连接**循环**functoid 到名为的记录**功能**在目标架构中，设置目标架构链接属性以匹配的链接上而。</span><span class="sxs-lookup"><span data-stu-id="7a5cf-117">For the link connecting the **Looping** functoid to the record named **Feature** in the destination schema, set the destination-schema link properties to match links top-down.</span></span>  
  
  <span data-ttu-id="7a5cf-118">若要反转此映射，将目录架构转换为平面架构，请参阅[值映射 （平展） Functoid](../core/value-mapping-flattening-functoid.md)。</span><span class="sxs-lookup"><span data-stu-id="7a5cf-118">For the inverse of this mapping, converting a catalog schema to a flat schema, see [Value Mapping (Flattening) Functoid](../core/value-mapping-flattening-functoid.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7a5cf-119">请参阅</span><span class="sxs-lookup"><span data-stu-id="7a5cf-119">See Also</span></span>  
 <span data-ttu-id="7a5cf-120">[如何添加循环 Functoid 映射](../core/how-to-add-looping-functoids-to-a-map.md) </span><span class="sxs-lookup"><span data-stu-id="7a5cf-120">[How to Add Looping Functoids to a Map](../core/how-to-add-looping-functoids-to-a-map.md) </span></span>  
 <span data-ttu-id="7a5cf-121">[循环 Functoid](../core/looping-functoid.md) </span><span class="sxs-lookup"><span data-stu-id="7a5cf-121">[Looping Functoid](../core/looping-functoid.md) </span></span>  
 [<span data-ttu-id="7a5cf-122">“值映射（平展）”Functoid</span><span class="sxs-lookup"><span data-stu-id="7a5cf-122">Value Mapping (Flattening) Functoid</span></span>](../core/value-mapping-flattening-functoid.md)