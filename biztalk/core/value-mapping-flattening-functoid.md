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
# <a name="value-mapping-flattening-functoid"></a><span data-ttu-id="eb306-102">“值映射(平展)”Functoid</span><span class="sxs-lookup"><span data-stu-id="eb306-102">Value Mapping (Flattening) Functoid</span></span>
<span data-ttu-id="eb306-103">**值映射 （平展）** functoid，可通过将多个记录转换为单个记录平展输入的实例消息的一部分。</span><span class="sxs-lookup"><span data-stu-id="eb306-103">The **Value Mapping (Flattening)** functoid enables you to flatten a portion of an input instance message by converting multiple records into a single record.</span></span> <span data-ttu-id="eb306-104">在转换 Microsoft Commerce Server 目录时通常执行此操作。</span><span class="sxs-lookup"><span data-stu-id="eb306-104">This is a common operation in converting Microsoft Commerce Server catalogs.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="eb306-105">**值映射 （平展）** 不应与组合 functoid**循环**functoid 或**表循环**functoid。</span><span class="sxs-lookup"><span data-stu-id="eb306-105">The **Value Mapping (Flattening)** functoid should not be combined with the **Looping** functoid or the **Table Looping** functoid.</span></span> <span data-ttu-id="eb306-106">如果它们结合使用，这会导致的编译的地图，假定循环依赖关系如下的目标节点没有源**循环**或**表循环**functoid。</span><span class="sxs-lookup"><span data-stu-id="eb306-106">If they are combined, it results in a compiled map that assumes there is no source looping dependency for the target nodes that are below the **Looping** or **Table Looping** functoid.</span></span>  
  
 <span data-ttu-id="eb306-107">下面的代码显示了部分目录，其中列出了改型产品，改型产品的每一个特征都记录在单独的记录中。</span><span class="sxs-lookup"><span data-stu-id="eb306-107">The following code shows a portion of a catalog listing product variants with each feature of the variant in a separate record.</span></span>  
  
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
  
 <span data-ttu-id="eb306-108">平展目录的此部分将转换**功能**记录合并到的属性**ProductVariant**记录。</span><span class="sxs-lookup"><span data-stu-id="eb306-108">Flattening this portion of the catalog would convert the **Feature** records into attributes of the **ProductVariant** record.</span></span>  
  
```  
<ns0:Root xmlns:ns0="http://ValueMappingFlat.ProductsOut">  
    <ProductVariant ListPrice="99.99" ID="45-01" Material="Leather" Color="Black" />  
    <ProductVariant ListPrice="69.99" ID="45-02" Material="Vinyl" Color="Brown" />  
</ns0:Root>  
```  
  
 <span data-ttu-id="eb306-109">下图显示的地图，执行此转换。</span><span class="sxs-lookup"><span data-stu-id="eb306-109">The following figure shows a map that performs this conversion.</span></span>  
  
 <span data-ttu-id="eb306-110">![映射源记录使用 functoid。] (../core/media/valuemappingflattenfunctoid.gif "valuemappingflattenfunctoid")</span><span class="sxs-lookup"><span data-stu-id="eb306-110">![Map source records using a functoid.](../core/media/valuemappingflattenfunctoid.gif "valuemappingflattenfunctoid")</span></span>  
<span data-ttu-id="eb306-111">“值映射(平展)”Functoid 映射</span><span class="sxs-lookup"><span data-stu-id="eb306-111">Value Mapping (Flattening) Functoid Map</span></span>  
  
 <span data-ttu-id="eb306-112">**值映射 （平展）** functoid 返回其第二个参数的值，如果其第一个参数为 true。</span><span class="sxs-lookup"><span data-stu-id="eb306-112">The **Value Mapping (Flattening)** functoid returns the value of its second parameter if its first parameter is true.</span></span> <span data-ttu-id="eb306-113">此映射中第一个**相等**functoid 测试以查看是否**名称**属性等于"材料"。</span><span class="sxs-lookup"><span data-stu-id="eb306-113">In this map, the first **Equal** functoid tests to see if the **Name** attribute is equal to "Material".</span></span> <span data-ttu-id="eb306-114">如果该属性值等于"材料"**相等**functoid 返回**True**。</span><span class="sxs-lookup"><span data-stu-id="eb306-114">If the attribute is equal to "Material", the **Equal** functoid returns **True**.</span></span> <span data-ttu-id="eb306-115">反过来，这会导致**值映射 （平展）** functoid 将的值分配**值**到输出的消息中的字段属性。</span><span class="sxs-lookup"><span data-stu-id="eb306-115">In turn, this causes the **Value Mapping (Flattening)** functoid to assign the value of the **Value** attribute to the field in the output message.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="eb306-116">另请参阅</span><span class="sxs-lookup"><span data-stu-id="eb306-116">See Also</span></span>  
 <span data-ttu-id="eb306-117">[如何添加值映射到图 （拼合） Functoid](../core/how-to-add-value-mapping-flattening-functoids-to-a-map.md) </span><span class="sxs-lookup"><span data-stu-id="eb306-117">[How to Add Value Mapping (Flattening) Functoids to a Map](../core/how-to-add-value-mapping-flattening-functoids-to-a-map.md) </span></span>  
 <span data-ttu-id="eb306-118">[平面架构到目录](../core/flat-schema-to-catalog.md) </span><span class="sxs-lookup"><span data-stu-id="eb306-118">[Flat Schema to Catalog](../core/flat-schema-to-catalog.md) </span></span>  
 [<span data-ttu-id="eb306-119">高级的 Functoid</span><span class="sxs-lookup"><span data-stu-id="eb306-119">Advanced Functoids</span></span>](../core/advanced-functoids.md)