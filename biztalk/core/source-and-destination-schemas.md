---
title: 源和目标架构 |Microsoft Docs
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
ms.openlocfilehash: 2f873c9dcd38c476ea47ea57e412aeec51e239b7
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65243270"
---
# <a name="source-and-destination-schemas"></a><span data-ttu-id="c860d-102">源和目标架构</span><span class="sxs-lookup"><span data-stu-id="c860d-102">Source and Destination Schemas</span></span>
<span data-ttu-id="c860d-103">每个 BizTalk 映射使用两个架构： 源架构和目标架构。</span><span class="sxs-lookup"><span data-stu-id="c860d-103">Each BizTalk map uses two schemas: a source schema and a destination schema.</span></span> <span data-ttu-id="c860d-104">源架构定义从中获取数据的实例消息的结构。</span><span class="sxs-lookup"><span data-stu-id="c860d-104">A source schema defines the structure of the instance messages from which you are taking data.</span></span> <span data-ttu-id="c860d-105">目标架构定义了映射生成的实例消息的结构。</span><span class="sxs-lookup"><span data-stu-id="c860d-105">The destination schema defines the structure of the instance messages the map produces.</span></span> <span data-ttu-id="c860d-106">例如，如果你想要映射的装运和帐单信息从采购订单到发票，需要定义采购订单的源架构和定义发票的架构的目标架构的架构。</span><span class="sxs-lookup"><span data-stu-id="c860d-106">For example, if you want to map the shipping and billing information from a purchase order to an invoice, you need a schema to define purchase orders for the source schema and a schema defining invoices for the destination schema.</span></span>  
  
 <span data-ttu-id="c860d-107">BizTalk 映射中使用的架构必须满足以下条件：</span><span class="sxs-lookup"><span data-stu-id="c860d-107">Schemas used in BizTalk maps must meet the following conditions:</span></span>  
  
- <span data-ttu-id="c860d-108">源和目标架构需要属于当前 BizTalk 项目中，或者必须在程序集中包括对架构的引用，以便可以在运行时访问这些架构。</span><span class="sxs-lookup"><span data-stu-id="c860d-108">The source and destination schemas need to be a part of your current BizTalk project, or you must include a reference to the schemas in the assembly so that the schemas can be accessed during run time.</span></span>  
  
- <span data-ttu-id="c860d-109">在 BizTalk 映射器中使用的架构必须基于 XML 架构定义 (XSD) 语言。</span><span class="sxs-lookup"><span data-stu-id="c860d-109">The schemas used in BizTalk Mapper must be based on the XML Schema definition (XSD) language.</span></span> <span data-ttu-id="c860d-110">BizTalk 编辑器提供了创建此类架构的简单方法。</span><span class="sxs-lookup"><span data-stu-id="c860d-110">BizTalk Editor provides an easy way to create such schemas.</span></span> <span data-ttu-id="c860d-111">有关使用 BizTalk 编辑器创建架构的详细信息，请参阅[使用 BizTalk 编辑器创建架构](../core/creating-schemas-using-biztalk-editor.md)。</span><span class="sxs-lookup"><span data-stu-id="c860d-111">For more information about creating schemas with BizTalk Editor, see [Creating Schemas Using BizTalk Editor](../core/creating-schemas-using-biztalk-editor.md).</span></span> <span data-ttu-id="c860d-112">另请参阅[创建架构](../core/creating-schemas.md)。</span><span class="sxs-lookup"><span data-stu-id="c860d-112">Also see [Creating Schemas](../core/creating-schemas.md).</span></span>  
  
  <span data-ttu-id="c860d-113">在 BizTalk 编辑器中，可以使用多个根节点创建架构。</span><span class="sxs-lookup"><span data-stu-id="c860d-113">In BizTalk Editor, you can create schemas with multiple root nodes.</span></span> <span data-ttu-id="c860d-114">但是，如果在 BizTalk 映射中的多个根节点使用一个架构，您必须选择哪个根节点 （和相应的子结构），在映射中使用。</span><span class="sxs-lookup"><span data-stu-id="c860d-114">However, if you use a schema with multiple root nodes in a BizTalk map, you must choose which root node (and corresponding substructure) to use in the map.</span></span> <span data-ttu-id="c860d-115">架构必须具有**根引用**属性确定哪个根是主要的。</span><span class="sxs-lookup"><span data-stu-id="c860d-115">Schemas have a **Root Reference** property identifying which root is primary.</span></span> <span data-ttu-id="c860d-116">如果架构具有多个根和**根引用**属性设置该架构是首次打开时作为源或目标架构，BizTalk 映射器将使用指定的根。</span><span class="sxs-lookup"><span data-stu-id="c860d-116">If a schema has multiple roots and the **Root Reference** property is set when the schema is first opened as the source or destination schema, BizTalk Mapper uses the specified root.</span></span> <span data-ttu-id="c860d-117">如果架构具有多个根和**根引用**属性未设置，则 BizTalk 映射器会提示你选择的根。</span><span class="sxs-lookup"><span data-stu-id="c860d-117">If a schema has multiple roots and the **Root Reference** property is not set, BizTalk Mapper prompts you to choose a root.</span></span>  
  
  <span data-ttu-id="c860d-118">如果您更改**根引用**属性已在映射中，BizTalk 映射器中使用的架构不会忽略该更改而继续使用最初指定的根。</span><span class="sxs-lookup"><span data-stu-id="c860d-118">If you change the **Root Reference** property of a schema already used in a map, BizTalk Mapper does not notice the change and continues to use the originally specified root.</span></span> <span data-ttu-id="c860d-119">如果你想要构建不同的映射使用同一架构的不同根，则最好不要设置**根引用**属性。</span><span class="sxs-lookup"><span data-stu-id="c860d-119">If you want to build different maps using different roots of the same schema, it is best not to set the **Root Reference** property.</span></span> <span data-ttu-id="c860d-120">这样一来，只要该架构用于新的映射，您必须显式选择根。</span><span class="sxs-lookup"><span data-stu-id="c860d-120">That way, whenever the schema is used for a new map, you must explicitly choose the root.</span></span>  
  
  <span data-ttu-id="c860d-121">如果它包含在映射中之后编辑架构，可能会破坏内映射的链接。</span><span class="sxs-lookup"><span data-stu-id="c860d-121">If you edit a schema after it is included in a map, the links within the map may break.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c860d-122">请参阅</span><span class="sxs-lookup"><span data-stu-id="c860d-122">See Also</span></span>  
 <span data-ttu-id="c860d-123">[映射](../core/maps.md) </span><span class="sxs-lookup"><span data-stu-id="c860d-123">[Maps](../core/maps.md) </span></span>  
 [<span data-ttu-id="c860d-124">使用 BizTalk 映射器创建映射</span><span class="sxs-lookup"><span data-stu-id="c860d-124">Creating Maps Using BizTalk Mapper</span></span>](../core/creating-maps-using-biztalk-mapper.md)