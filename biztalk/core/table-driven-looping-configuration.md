---
title: 表驱动循环配置 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- Table Looping functoids
- Table Extractor functoids, configuring
- Table Extractor functoids
- Table Extractor functoids, adding to grid
- Table Looping functoids, about Table Looping functoids
- Table Looping functoids, configuring
- Table Extractor functoids, about Table Extractor functoids
- Table Looping functoids, adding to map
ms.assetid: ecc24d9b-ebc0-4559-9746-58e3b00c02ab
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: ecb4efd2e067cf34113c6bb811207c21f8fd35c6
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65291707"
---
# <a name="table-driven-looping-configuration"></a><span data-ttu-id="38331-102">表驱动循环配置</span><span class="sxs-lookup"><span data-stu-id="38331-102">Table-Driven Looping Configuration</span></span>
<span data-ttu-id="38331-103">请执行以下步骤来配置表驱动循环在地图中：</span><span class="sxs-lookup"><span data-stu-id="38331-103">Follow these steps to configure table-driven looping in your map:</span></span>  
  
- <span data-ttu-id="38331-104">**向映射添加表循环 functoid。**</span><span class="sxs-lookup"><span data-stu-id="38331-104">**Add a Table Looping functoid to the map.**</span></span> <span data-ttu-id="38331-105">只需要一**表循环**functoid 每个表驱动循环实例。</span><span class="sxs-lookup"><span data-stu-id="38331-105">You need only one **Table Looping** functoid per table-driven looping instance.</span></span> <span data-ttu-id="38331-106">例如，如果你使用表驱动循环派生 BillTo 和 ShipTo 信息，则需要只有一个**表循环**functoid 在映射中的。</span><span class="sxs-lookup"><span data-stu-id="38331-106">For example, if you are using table-driven looping to derive BillTo and ShipTo information, you need only one **Table Looping** functoid in your map.</span></span> <span data-ttu-id="38331-107">但是，如果你使用表驱动循环派生 BillTo 和 ShipTo 信息以及 StoreName 和 StoreAddress 信息，则可能需要两个**表循环**functoid 在映射中的。</span><span class="sxs-lookup"><span data-stu-id="38331-107">However, if you are using table-driven looping to derive BillTo and ShipTo information and StoreName and StoreAddress information, you might need two **Table Looping** functoids in your map.</span></span>  
  
- <span data-ttu-id="38331-108">**将多个表提取程序 functoid 添加到显示的网格页。**</span><span class="sxs-lookup"><span data-stu-id="38331-108">**Add one more Table Extractor functoid to the displayed grid page.**</span></span> <span data-ttu-id="38331-109">添加任意数量**表提取程序**functoid 作为您需要为每个**表循环**functoid。</span><span class="sxs-lookup"><span data-stu-id="38331-109">Add as many **Table Extractor** functoids as you need for each **Table Looping** functoid.</span></span> <span data-ttu-id="38331-110">数**表提取程序**functoid 依赖于目标架构中的字段数。</span><span class="sxs-lookup"><span data-stu-id="38331-110">The number of **Table Extractor** functoids depends on the number of fields in the destination schema.</span></span> <span data-ttu-id="38331-111">例如，如果您只需**AddressCode**在你源架构和 CompanyName、 地址、 城市、 州、 邮政编码和 AttentionName 目标架构中的，您需要添加六个**表提取程序**向显示的网格页的 functoid。</span><span class="sxs-lookup"><span data-stu-id="38331-111">For example, if you only have an **AddressCode** in your source schema and CompanyName, Address, City, State, PostalCode, and AttentionName in your destination schema, you need to add six **Table Extractor** functoids to the displayed grid page.</span></span>  
  
- <span data-ttu-id="38331-112">**将表循环 functoid 配置相应的输入。**</span><span class="sxs-lookup"><span data-stu-id="38331-112">**Configure the Table Looping functoid with the appropriate inputs.**</span></span> <span data-ttu-id="38331-113">首先，链接**表循环**functoid 到输入的实例记录或元素。</span><span class="sxs-lookup"><span data-stu-id="38331-113">First, link the **Table Looping** functoid to the input instance record or element.</span></span> <span data-ttu-id="38331-114">此外将其链接到输出实例消息中的结构。</span><span class="sxs-lookup"><span data-stu-id="38331-114">Also link it to the structure in the output instance message.</span></span> <span data-ttu-id="38331-115">接下来，通过配置输入**配置\<Functoid\> Functoid**对话框。</span><span class="sxs-lookup"><span data-stu-id="38331-115">Next, configure the inputs by using the **Configure \<Functoid\> Functoid** dialog box.</span></span> <span data-ttu-id="38331-116">有关如何配置此属性的详细信息，请参阅[编辑 Functoid 属性和输入参数](../core/editing-functoid-properties-and-input-parameters.md)。</span><span class="sxs-lookup"><span data-stu-id="38331-116">For more information about how to configure this property, see [Editing Functoid Properties and Input Parameters](../core/editing-functoid-properties-and-input-parameters.md) .</span></span> <span data-ttu-id="38331-117">输入的输入列表必须是全面而完整，因为这是将用于配置的数据**表 Functoid 网格**属性。</span><span class="sxs-lookup"><span data-stu-id="38331-117">The list of inputs you enter must be comprehensive and complete because this is the data that you will use to configure the **Table Functoid Grid** property.</span></span> <span data-ttu-id="38331-118">必须按如下所示定义输入：</span><span class="sxs-lookup"><span data-stu-id="38331-118">The inputs must be defined as follows:</span></span>  
  
  -   <span data-ttu-id="38331-119">**第一个输入。**</span><span class="sxs-lookup"><span data-stu-id="38331-119">**First input.**</span></span> <span data-ttu-id="38331-120">第一个输入的参数是指向输入的实例消息记录或字段的链接。</span><span class="sxs-lookup"><span data-stu-id="38331-120">The first input parameter is the link to the input instance message record or field.</span></span> <span data-ttu-id="38331-121">**表循环**functoid 为每个记录或字段实例循环一次。</span><span class="sxs-lookup"><span data-stu-id="38331-121">The **Table Looping** functoid loops once for each instance of the record or field.</span></span>  
  
      > [!NOTE]
      >  <span data-ttu-id="38331-122">这是所需的输入。</span><span class="sxs-lookup"><span data-stu-id="38331-122">This is a required input.</span></span>  
  
  -   <span data-ttu-id="38331-123">**第二个输入。**</span><span class="sxs-lookup"><span data-stu-id="38331-123">**Second input.**</span></span> <span data-ttu-id="38331-124">第二个输入的参数定义循环网格中的列数。</span><span class="sxs-lookup"><span data-stu-id="38331-124">The second input parameter defines the number of columns in the looping grid.</span></span> <span data-ttu-id="38331-125">网格可能包含最多 228 列。</span><span class="sxs-lookup"><span data-stu-id="38331-125">The grid may contain up to 228 columns.</span></span>  
  
      > [!NOTE]
      >  <span data-ttu-id="38331-126">这是所需的输入。</span><span class="sxs-lookup"><span data-stu-id="38331-126">This is a required input.</span></span>  
  
  -   <span data-ttu-id="38331-127">**剩余输入参数。**</span><span class="sxs-lookup"><span data-stu-id="38331-127">**Remaining inputs.**</span></span> <span data-ttu-id="38331-128">剩余的输入**表循环**functoid 包含所有中可能出现的可能值的列表**表 Functoid 网格**。</span><span class="sxs-lookup"><span data-stu-id="38331-128">The remaining inputs for the **Table Looping** functoid consist of a list of all of the possible values that may appear in the **Table Functoid Grid**.</span></span>  
  
      > [!NOTE]
      >  <span data-ttu-id="38331-129">标记链接是非常有帮助。</span><span class="sxs-lookup"><span data-stu-id="38331-129">Labeling links is very helpful.</span></span> <span data-ttu-id="38331-130">如果没有标记，链接将显示在**表 Functoid 网格**为完全指定路径。</span><span class="sxs-lookup"><span data-stu-id="38331-130">Without labels, links appear in the **Table Functoid Grid** as fully specified paths.</span></span>  
  
       <span data-ttu-id="38331-131">有关如何配置的输入的分步说明**表循环**functoid，请参阅[如何添加表循环和向映射表提取程序 Functoid](../core/how-to-add-table-looping-and-table-extractor-functoids-to-a-map.md)。</span><span class="sxs-lookup"><span data-stu-id="38331-131">For step-by-step instructions about how to configure inputs for the **Table Looping** functoid, see [How to Add Table Looping and Table Extractor Functoids to a Map](../core/how-to-add-table-looping-and-table-extractor-functoids-to-a-map.md).</span></span> <span data-ttu-id="38331-132">具体而言，请参阅步骤 3 至 8。</span><span class="sxs-lookup"><span data-stu-id="38331-132">In particular, see steps 3 through 8.</span></span>  
  
- <span data-ttu-id="38331-133">**配置表循环 functoid 的表 Functoid 网格属性。**</span><span class="sxs-lookup"><span data-stu-id="38331-133">**Configure the Table Functoid Grid property of the Table Looping functoid.**</span></span> <span data-ttu-id="38331-134">使用**表 Functoid 网格**以打开**配置表循环 Functoid**对话框配置循环网格中的单元格。</span><span class="sxs-lookup"><span data-stu-id="38331-134">Use the **Table Functoid Grid** property to open the **Configure Table Looping Functoid** dialog box in which you configure the cells in the looping grid.</span></span>  
  
   <span data-ttu-id="38331-135">有关如何配置循环网格的分步说明，请参阅[如何添加表循环和向映射表提取程序 Functoid](../core/how-to-add-table-looping-and-table-extractor-functoids-to-a-map.md)。</span><span class="sxs-lookup"><span data-stu-id="38331-135">For step-by-step instructions about how to configure the looping grid, see [How to Add Table Looping and Table Extractor Functoids to a Map](../core/how-to-add-table-looping-and-table-extractor-functoids-to-a-map.md).</span></span> <span data-ttu-id="38331-136">具体而言，请参阅步骤 9 和 10。</span><span class="sxs-lookup"><span data-stu-id="38331-136">In particular, see steps 9 and 10.</span></span>  
  
- <span data-ttu-id="38331-137">**配置表提取程序 functoid。**</span><span class="sxs-lookup"><span data-stu-id="38331-137">**Configure the Table Extractor functoids.**</span></span> <span data-ttu-id="38331-138">使用**输入参数**属性可配置**表提取程序**functoid 的输入，如下所示：</span><span class="sxs-lookup"><span data-stu-id="38331-138">Use the **Input Parameters** property to configure the **Table Extractor** functoid inputs as follows:</span></span>  
  
  - <span data-ttu-id="38331-139">**第一个输入。**</span><span class="sxs-lookup"><span data-stu-id="38331-139">**First input.**</span></span> <span data-ttu-id="38331-140">第一个输入的参数**表提取程序**functoid**表循环**functoid。</span><span class="sxs-lookup"><span data-stu-id="38331-140">The first input parameter to a **Table Extractor** functoid is the **Table Looping** functoid.</span></span>  
  
  - <span data-ttu-id="38331-141">**第二个输入。**</span><span class="sxs-lookup"><span data-stu-id="38331-141">**Second input.**</span></span> <span data-ttu-id="38331-142">第二个输入的参数指定要从中提取数据行中的列。</span><span class="sxs-lookup"><span data-stu-id="38331-142">The second input parameter specifies the column in the row from which to extract data.</span></span>  
  
    <span data-ttu-id="38331-143">有关如何配置的分步说明**表提取程序**与关联的 functoid**表循环**functoid，请参阅[如何添加表循环和表提取程序向映射 Functoid](../core/how-to-add-table-looping-and-table-extractor-functoids-to-a-map.md)。</span><span class="sxs-lookup"><span data-stu-id="38331-143">For step-by-step instructions about how to configure the **Table Extractor** functoids associated with a **Table Looping** functoid, see [How to Add Table Looping and Table Extractor Functoids to a Map](../core/how-to-add-table-looping-and-table-extractor-functoids-to-a-map.md).</span></span> <span data-ttu-id="38331-144">具体而言，请参阅步骤 11 到 16。</span><span class="sxs-lookup"><span data-stu-id="38331-144">In particular, see steps 11 through 16.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="38331-145">请参阅</span><span class="sxs-lookup"><span data-stu-id="38331-145">See Also</span></span>  
 <span data-ttu-id="38331-146">[表循环 Functoid](../core/table-looping-functoid.md) </span><span class="sxs-lookup"><span data-stu-id="38331-146">[Table Looping Functoid](../core/table-looping-functoid.md) </span></span>  
 <span data-ttu-id="38331-147">[表提取程序 Functoid](../core/table-extractor-functoid.md) </span><span class="sxs-lookup"><span data-stu-id="38331-147">[Table Extractor Functoid](../core/table-extractor-functoid.md) </span></span>  
 <span data-ttu-id="38331-148">[表驱动循环示例](../core/table-driven-looping-example.md) </span><span class="sxs-lookup"><span data-stu-id="38331-148">[Table-Driven Looping Example](../core/table-driven-looping-example.md) </span></span>  
 <span data-ttu-id="38331-149">[如何添加表循环和表提取程序 Functoid 映射](../core/how-to-add-table-looping-and-table-extractor-functoids-to-a-map.md) </span><span class="sxs-lookup"><span data-stu-id="38331-149">[How to Add Table Looping and Table Extractor Functoids to a Map](../core/how-to-add-table-looping-and-table-extractor-functoids-to-a-map.md) </span></span>  
 <span data-ttu-id="38331-150">[高级的 Functoid](../core/advanced-functoids.md) </span><span class="sxs-lookup"><span data-stu-id="38331-150">[Advanced Functoids](../core/advanced-functoids.md) </span></span>  
 <span data-ttu-id="38331-151">[索引 Functoid](../core/index-functoid.md) </span><span class="sxs-lookup"><span data-stu-id="38331-151">[Index Functoid](../core/index-functoid.md) </span></span>  
 <span data-ttu-id="38331-152">[迭代 Functoid](../core/iteration-functoid.md) </span><span class="sxs-lookup"><span data-stu-id="38331-152">[Iteration Functoid](../core/iteration-functoid.md) </span></span>  
 <span data-ttu-id="38331-153">[循环 Functoid](../core/looping-functoid.md) </span><span class="sxs-lookup"><span data-stu-id="38331-153">[Looping Functoid](../core/looping-functoid.md) </span></span>  
 [<span data-ttu-id="38331-154">记录计数 Functoid</span><span class="sxs-lookup"><span data-stu-id="38331-154">Record Count Functoid</span></span>](../core/record-count-functoid.md)