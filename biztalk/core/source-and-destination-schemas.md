---
title: 源和目标架构 |Microsoft 文档
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- destination schemas
- source schemas, maps
- XML schemas, defining
- destination schemas, about destination schemas
- schemas, destination
- destination schemas, maps
- maps, source schemas
- schemas, Root Reference property
- Root Reference property, modifying
- source schemas
- modifying, Root Reference property
- maps, Root Reference property
- source schemas, about source schemas
- schemas, maps
- maps, schema requirements
- schemas, requirements
- schemas, source schemas
- maps, destination schemas
- Root Reference property
ms.assetid: 8c805854-9fa1-4ce3-938d-a2e61ba17fa1
caps.latest.revision: 11
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: d82fb8445260b505fbd04b648c251b99fe896dcd
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22276925"
---
# <a name="source-and-destination-schemas"></a><span data-ttu-id="1edb8-102">源和目标架构</span><span class="sxs-lookup"><span data-stu-id="1edb8-102">Source and Destination Schemas</span></span>
<span data-ttu-id="1edb8-103">每个 BizTalk 映射都使用两个架构：一个源架构和一个目标架构。</span><span class="sxs-lookup"><span data-stu-id="1edb8-103">Each BizTalk map uses two schemas: a source schema and a destination schema.</span></span> <span data-ttu-id="1edb8-104">源架构定义了要从中获取数据的实例消息的结构。</span><span class="sxs-lookup"><span data-stu-id="1edb8-104">A source schema defines the structure of the instance messages from which you are taking data.</span></span> <span data-ttu-id="1edb8-105">目标架构则定义了映射生成的实例消息的结构。</span><span class="sxs-lookup"><span data-stu-id="1edb8-105">The destination schema defines the structure of the instance messages the map produces.</span></span> <span data-ttu-id="1edb8-106">例如，若要将采购订单的发货地址信息和帐单邮寄地址信息映射到发票，则需要一个定义采购订单的架构用作源架构，一个定义发票的架构用作目标架构。</span><span class="sxs-lookup"><span data-stu-id="1edb8-106">For example, if you want to map the shipping and billing information from a purchase order to an invoice, you need a schema to define purchase orders for the source schema and a schema defining invoices for the destination schema.</span></span>  
  
 <span data-ttu-id="1edb8-107">BizTalk 映射中使用的架构必须符合以下条件：</span><span class="sxs-lookup"><span data-stu-id="1edb8-107">Schemas used in BizTalk maps must meet the following conditions:</span></span>  
  
-   <span data-ttu-id="1edb8-108">源架构和目标架构必须是当前 BizTalk 项目的一部分，或者必须在程序集中包括指向这两个架构的引用以便在运行时访问它们。</span><span class="sxs-lookup"><span data-stu-id="1edb8-108">The source and destination schemas need to be a part of your current BizTalk project, or you must include a reference to the schemas in the assembly so that the schemas can be accessed during run time.</span></span>  
  
-   <span data-ttu-id="1edb8-109">BizTalk 映射器中使用的架构必须基于 XML 架构定义 (XSD) 语言。</span><span class="sxs-lookup"><span data-stu-id="1edb8-109">The schemas used in BizTalk Mapper must be based on the XML Schema definition (XSD) language.</span></span> <span data-ttu-id="1edb8-110">使用 BizTalk 编辑器可以便捷地创建此类架构。</span><span class="sxs-lookup"><span data-stu-id="1edb8-110">BizTalk Editor provides an easy way to create such schemas.</span></span> <span data-ttu-id="1edb8-111">有关创建使用 BizTalk 编辑器的架构的详细信息，请参阅[使用 BizTalk 编辑器创建架构](../core/creating-schemas-using-biztalk-editor.md)。</span><span class="sxs-lookup"><span data-stu-id="1edb8-111">For more information about creating schemas with BizTalk Editor, see [Creating Schemas Using BizTalk Editor](../core/creating-schemas-using-biztalk-editor.md).</span></span> <span data-ttu-id="1edb8-112">另请参阅[创建架构](../core/creating-schemas.md)。</span><span class="sxs-lookup"><span data-stu-id="1edb8-112">Also see [Creating Schemas](../core/creating-schemas.md).</span></span>  
  
 <span data-ttu-id="1edb8-113">在 BizTalk 编辑器中，可以创建带多个根节点的架构。</span><span class="sxs-lookup"><span data-stu-id="1edb8-113">In BizTalk Editor, you can create schemas with multiple root nodes.</span></span> <span data-ttu-id="1edb8-114">但是，如果在 BizTalk 映射中使用带有多个根节点的架构，则必须选择要在映射中使用的根节点（以及相应的子结构）。</span><span class="sxs-lookup"><span data-stu-id="1edb8-114">However, if you use a schema with multiple root nodes in a BizTalk map, you must choose which root node (and corresponding substructure) to use in the map.</span></span> <span data-ttu-id="1edb8-115">架构具有**根引用**属性标识的根是主。</span><span class="sxs-lookup"><span data-stu-id="1edb8-115">Schemas have a **Root Reference** property identifying which root is primary.</span></span> <span data-ttu-id="1edb8-116">如果某个架构具有多个根和**根引用**属性设置的架构是首次打开时作为源或目标架构、 BizTalk 映射程序使用指定的根。</span><span class="sxs-lookup"><span data-stu-id="1edb8-116">If a schema has multiple roots and the **Root Reference** property is set when the schema is first opened as the source or destination schema, BizTalk Mapper uses the specified root.</span></span> <span data-ttu-id="1edb8-117">如果某个架构具有多个根和**根引用**未设置属性，BizTalk 映射程序将提示你选择的根。</span><span class="sxs-lookup"><span data-stu-id="1edb8-117">If a schema has multiple roots and the **Root Reference** property is not set, BizTalk Mapper prompts you to choose a root.</span></span>  
  
 <span data-ttu-id="1edb8-118">如果你更改**根引用**属性已在地图中，BizTalk 映射程序中使用的架构不到更改，并继续使用最初指定的根。</span><span class="sxs-lookup"><span data-stu-id="1edb8-118">If you change the **Root Reference** property of a schema already used in a map, BizTalk Mapper does not notice the change and continues to use the originally specified root.</span></span> <span data-ttu-id="1edb8-119">如果你想要生成不同的映射使用不同的相同的架构的根，则最好不要设置**根引用**属性。</span><span class="sxs-lookup"><span data-stu-id="1edb8-119">If you want to build different maps using different roots of the same schema, it is best not to set the **Root Reference** property.</span></span> <span data-ttu-id="1edb8-120">这样，在架构用于新的映射时，您就必须明确地选择根。</span><span class="sxs-lookup"><span data-stu-id="1edb8-120">That way, whenever the schema is used for a new map, you must explicitly choose the root.</span></span>  
  
 <span data-ttu-id="1edb8-121">如果在映射包含架构之后再编辑该架构，则映射中的链接可能会断开。</span><span class="sxs-lookup"><span data-stu-id="1edb8-121">If you edit a schema after it is included in a map, the links within the map may break.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1edb8-122">另请参阅</span><span class="sxs-lookup"><span data-stu-id="1edb8-122">See Also</span></span>  
 <span data-ttu-id="1edb8-123">[地图](../core/maps.md) </span><span class="sxs-lookup"><span data-stu-id="1edb8-123">[Maps](../core/maps.md) </span></span>  
 [<span data-ttu-id="1edb8-124">创建使用 BizTalk 映射程序图</span><span class="sxs-lookup"><span data-stu-id="1edb8-124">Creating Maps Using BizTalk Mapper</span></span>](../core/creating-maps-using-biztalk-mapper.md)