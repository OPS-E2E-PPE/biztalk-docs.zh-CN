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
# <a name="mass-copy-functoid"></a><span data-ttu-id="4b0a8-102">“批量复制”functoid</span><span class="sxs-lookup"><span data-stu-id="4b0a8-102">Mass Copy Functoid</span></span>
<span data-ttu-id="4b0a8-103">**大容量复制**functoid 使你使用包含的架构的映射**任何**和**anyAttribute**元素。</span><span class="sxs-lookup"><span data-stu-id="4b0a8-103">The **Mass Copy** functoid enables your maps to use schemas that include **any** and **anyAttribute** elements.</span></span> <span data-ttu-id="4b0a8-104">实际上，这些元素是 XML 架构定义语言为匹配未知结构或属性而提供的通配符。</span><span class="sxs-lookup"><span data-stu-id="4b0a8-104">These elements are, in essence, wildcards provided in the XML Schema definition language to match unknown structures or attributes.</span></span>  
  
 <span data-ttu-id="4b0a8-105">除了处理具有未知的结构、 数据**大容量复制**functoid，可简化架构开发： 仅将处理的架构部分需要在详细信息中指定。</span><span class="sxs-lookup"><span data-stu-id="4b0a8-105">In addition to handling data with unknown structure, the **Mass Copy** functoid enables you to simplify schema development: only the portions of a schema that will be processed need to be specified in detail.</span></span>  
  
 <span data-ttu-id="4b0a8-106">**大容量复制**functoid 对应于连接到源架构节点的输入的实例消息中复制元素**大容量复制**functoid。</span><span class="sxs-lookup"><span data-stu-id="4b0a8-106">The **Mass Copy** functoid copies the element in the input instance message corresponding to the source schema node connected to the **Mass Copy** functoid.</span></span> <span data-ttu-id="4b0a8-107">该 functoid 还可复制其任意或全部子结构，并在目标架构中所链接节点的输出实例消息中重新创建子结构。</span><span class="sxs-lookup"><span data-stu-id="4b0a8-107">The functoid also copies any and all of its substructure, and re-creates it in the output instance message at the linked node in the destination schema.</span></span> <span data-ttu-id="4b0a8-108">因此，你还可以使用**大容量复制**functoid 来复制任何具有相同的子结构的源和目标记录。</span><span class="sxs-lookup"><span data-stu-id="4b0a8-108">Thus, you can also use the **Mass Copy** functoid to copy any source and destination records having identical substructures.</span></span>  
  
 <span data-ttu-id="4b0a8-109">下图显示**大容量复制**functoid 映射中使用。</span><span class="sxs-lookup"><span data-stu-id="4b0a8-109">The following figure shows the **Mass Copy** functoid used in a map.</span></span>  
  
 <span data-ttu-id="4b0a8-110">![映射的大容量复制 functoid 用法](../core/media/masscopyfunctoid.gif "masscopyfunctoid")</span><span class="sxs-lookup"><span data-stu-id="4b0a8-110">![Map illustrating the use of the mass copy functoid](../core/media/masscopyfunctoid.gif "masscopyfunctoid")</span></span>  
<span data-ttu-id="4b0a8-111">“批量复制”Functoid 映射</span><span class="sxs-lookup"><span data-stu-id="4b0a8-111">Mass Copy Functoid Map</span></span>  
  
 <span data-ttu-id="4b0a8-112">请注意以下输入实例消息：</span><span class="sxs-lookup"><span data-stu-id="4b0a8-112">Consider the following input instance message.</span></span>  
  
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
  
 <span data-ttu-id="4b0a8-113">如果使用上面的映射处理此消息，则输出实例消息将与输入实例消息相同。</span><span class="sxs-lookup"><span data-stu-id="4b0a8-113">If the preceding map were used to process this message, the output instance message would be identical to the input instance message.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4b0a8-114">另请参阅</span><span class="sxs-lookup"><span data-stu-id="4b0a8-114">See Also</span></span>  
 <span data-ttu-id="4b0a8-115">[如何在向地图添加大容量复制 Functoid](../core/how-to-add-mass-copy-functoids-to-a-map.md) </span><span class="sxs-lookup"><span data-stu-id="4b0a8-115">[How to Add Mass Copy Functoids to a Map](../core/how-to-add-mass-copy-functoids-to-a-map.md) </span></span>  
 <span data-ttu-id="4b0a8-116">[高级的 Functoid](../core/advanced-functoids.md) </span><span class="sxs-lookup"><span data-stu-id="4b0a8-116">[Advanced Functoids](../core/advanced-functoids.md) </span></span>  
 <span data-ttu-id="4b0a8-117">[基本 Functoid](../core/basic-functoids.md) </span><span class="sxs-lookup"><span data-stu-id="4b0a8-117">[Basic Functoids](../core/basic-functoids.md) </span></span>  
 [<span data-ttu-id="4b0a8-118">链接到和从任何元素和 anyAttribute 节点</span><span class="sxs-lookup"><span data-stu-id="4b0a8-118">Links To and From the Any Element and anyAttribute Nodes</span></span>](../core/links-to-and-from-the-any-element-and-anyattribute-nodes.md)