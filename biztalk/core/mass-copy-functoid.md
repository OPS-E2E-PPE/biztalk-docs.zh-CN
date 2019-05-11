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
# <a name="mass-copy-functoid"></a><span data-ttu-id="44d14-102">批量复制 Functoid</span><span class="sxs-lookup"><span data-stu-id="44d14-102">Mass Copy Functoid</span></span>
<span data-ttu-id="44d14-103">**批量复制**functoid，映射可使用包含的架构**任何**并**anyAttribute**元素。</span><span class="sxs-lookup"><span data-stu-id="44d14-103">The **Mass Copy** functoid enables your maps to use schemas that include **any** and **anyAttribute** elements.</span></span> <span data-ttu-id="44d14-104">从本质上讲，这些元素是 XML 架构定义语言为匹配未知的结构或属性中提供的通配符。</span><span class="sxs-lookup"><span data-stu-id="44d14-104">These elements are, in essence, wildcards provided in the XML Schema definition language to match unknown structures or attributes.</span></span>  
  
 <span data-ttu-id="44d14-105">除了处理未知结构的数据**批量复制**functoid，您可以简化架构开发： 需详细指定仅将处理的架构部分。</span><span class="sxs-lookup"><span data-stu-id="44d14-105">In addition to handling data with unknown structure, the **Mass Copy** functoid enables you to simplify schema development: only the portions of a schema that will be processed need to be specified in detail.</span></span>  
  
 <span data-ttu-id="44d14-106">**批量复制**functoid 复制到连接到源架构节点相对应的输入的实例消息中的元素**批量复制**functoid。</span><span class="sxs-lookup"><span data-stu-id="44d14-106">The **Mass Copy** functoid copies the element in the input instance message corresponding to the source schema node connected to the **Mass Copy** functoid.</span></span> <span data-ttu-id="44d14-107">该 functoid 还将复制其子结构的所有和目标架构中所链接节点的输出实例消息中重新创建。</span><span class="sxs-lookup"><span data-stu-id="44d14-107">The functoid also copies any and all of its substructure, and re-creates it in the output instance message at the linked node in the destination schema.</span></span> <span data-ttu-id="44d14-108">因此，您还可以使用**批量复制**functoid 复制任何具有相同子结构的源和目标记录。</span><span class="sxs-lookup"><span data-stu-id="44d14-108">Thus, you can also use the **Mass Copy** functoid to copy any source and destination records having identical substructures.</span></span>  
  
 <span data-ttu-id="44d14-109">下图显示**批量复制**映射中使用的 functoid。</span><span class="sxs-lookup"><span data-stu-id="44d14-109">The following figure shows the **Mass Copy** functoid used in a map.</span></span>  
  
 <span data-ttu-id="44d14-110">![说明如何使用批量复制 functoid](../core/media/masscopyfunctoid.gif "masscopyfunctoid")</span><span class="sxs-lookup"><span data-stu-id="44d14-110">![Map illustrating the use of the mass copy functoid](../core/media/masscopyfunctoid.gif "masscopyfunctoid")</span></span>  
<span data-ttu-id="44d14-111">批量复制 Functoid 映射</span><span class="sxs-lookup"><span data-stu-id="44d14-111">Mass Copy Functoid Map</span></span>  
  
 <span data-ttu-id="44d14-112">请考虑以下输入的实例消息。</span><span class="sxs-lookup"><span data-stu-id="44d14-112">Consider the following input instance message.</span></span>  
  
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
  
 <span data-ttu-id="44d14-113">如果使用上面的映射来处理此消息，输出实例消息将具有与输入的实例消息相同。</span><span class="sxs-lookup"><span data-stu-id="44d14-113">If the preceding map were used to process this message, the output instance message would be identical to the input instance message.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="44d14-114">请参阅</span><span class="sxs-lookup"><span data-stu-id="44d14-114">See Also</span></span>  
 <span data-ttu-id="44d14-115">[如何向映射添加批量复制 Functoid](../core/how-to-add-mass-copy-functoids-to-a-map.md) </span><span class="sxs-lookup"><span data-stu-id="44d14-115">[How to Add Mass Copy Functoids to a Map](../core/how-to-add-mass-copy-functoids-to-a-map.md) </span></span>  
 <span data-ttu-id="44d14-116">[高级的 Functoid](../core/advanced-functoids.md) </span><span class="sxs-lookup"><span data-stu-id="44d14-116">[Advanced Functoids](../core/advanced-functoids.md) </span></span>  
 <span data-ttu-id="44d14-117">[基本 Functoid](../core/basic-functoids.md) </span><span class="sxs-lookup"><span data-stu-id="44d14-117">[Basic Functoids](../core/basic-functoids.md) </span></span>  
 [<span data-ttu-id="44d14-118">与“任何元素”和“任何属性”节点相关的链接</span><span class="sxs-lookup"><span data-stu-id="44d14-118">Links To and From the Any Element and anyAttribute Nodes</span></span>](../core/links-to-and-from-the-any-element-and-anyattribute-nodes.md)