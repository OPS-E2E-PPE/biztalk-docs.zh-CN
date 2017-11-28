---
title: "表驱动的循环配置 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
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
caps.latest.revision: "8"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 2563c7f26d2beb0eba33173507989cc85aaabda1
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="table-driven-looping-configuration"></a><span data-ttu-id="9d85d-102">表驱动循环配置</span><span class="sxs-lookup"><span data-stu-id="9d85d-102">Table-Driven Looping Configuration</span></span>
<span data-ttu-id="9d85d-103">按照以下步骤配置映射中的表驱动循环：</span><span class="sxs-lookup"><span data-stu-id="9d85d-103">Follow these steps to configure table-driven looping in your map:</span></span>  
  
-   <span data-ttu-id="9d85d-104">**向图中添加表循环 functoid。**</span><span class="sxs-lookup"><span data-stu-id="9d85d-104">**Add a Table Looping functoid to the map.**</span></span> <span data-ttu-id="9d85d-105">你需要仅有一个**表循环**functoid 每个表驱动循环实例。</span><span class="sxs-lookup"><span data-stu-id="9d85d-105">You need only one **Table Looping** functoid per table-driven looping instance.</span></span> <span data-ttu-id="9d85d-106">例如，如果你使用表驱动循环派生帐单寄往和 ShipTo 信息，你需要仅一个**表循环**functoid 映射中的。</span><span class="sxs-lookup"><span data-stu-id="9d85d-106">For example, if you are using table-driven looping to derive BillTo and ShipTo information, you need only one **Table Looping** functoid in your map.</span></span> <span data-ttu-id="9d85d-107">但是，如果你使用表驱动循环派生帐单寄往和 ShipTo 信息以及 StoreName 和 StoreAddress 信息，你可能需要两个**表循环**functoid 映射中的。</span><span class="sxs-lookup"><span data-stu-id="9d85d-107">However, if you are using table-driven looping to derive BillTo and ShipTo information and StoreName and StoreAddress information, you might need two **Table Looping** functoids in your map.</span></span>  
  
-   <span data-ttu-id="9d85d-108">**将一个多个表提取程序 functoid 添加到显示的网格页。**</span><span class="sxs-lookup"><span data-stu-id="9d85d-108">**Add one more Table Extractor functoid to the displayed grid page.**</span></span> <span data-ttu-id="9d85d-109">添加任意多个**表提取程序**functoid 作为你需要为每个**表循环**functoid。</span><span class="sxs-lookup"><span data-stu-id="9d85d-109">Add as many **Table Extractor** functoids as you need for each **Table Looping** functoid.</span></span> <span data-ttu-id="9d85d-110">数**表提取程序**functoid 取决于目标架构中的字段数。</span><span class="sxs-lookup"><span data-stu-id="9d85d-110">The number of **Table Extractor** functoids depends on the number of fields in the destination schema.</span></span> <span data-ttu-id="9d85d-111">例如，如果你只有**AddressCode**在你源架构和 CompanyName、 地址、 市/县、 状态、 邮政编码和 AttentionName 目标架构中的，你需要添加六个**表提取程序**显示的网格逐页 functoid。</span><span class="sxs-lookup"><span data-stu-id="9d85d-111">For example, if you only have an **AddressCode** in your source schema and CompanyName, Address, City, State, PostalCode, and AttentionName in your destination schema, you need to add six **Table Extractor** functoids to the displayed grid page.</span></span>  
  
-   <span data-ttu-id="9d85d-112">**使用适当的输入配置表循环 functoid。**</span><span class="sxs-lookup"><span data-stu-id="9d85d-112">**Configure the Table Looping functoid with the appropriate inputs.**</span></span> <span data-ttu-id="9d85d-113">首先，链接**表循环**functoid 到输入的实例记录或元素。</span><span class="sxs-lookup"><span data-stu-id="9d85d-113">First, link the **Table Looping** functoid to the input instance record or element.</span></span> <span data-ttu-id="9d85d-114">同时，还要将其链接到输出实例消息中的结构。</span><span class="sxs-lookup"><span data-stu-id="9d85d-114">Also link it to the structure in the output instance message.</span></span> <span data-ttu-id="9d85d-115">接下来，通过配置输入**配置\<Functoid > Functoid**对话框。</span><span class="sxs-lookup"><span data-stu-id="9d85d-115">Next, configure the inputs by using the **Configure \<Functoid> Functoid** dialog box.</span></span> <span data-ttu-id="9d85d-116">有关如何配置此属性的详细信息，请参阅[编辑 Functoid 属性和输入参数](../core/editing-functoid-properties-and-input-parameters.md)。</span><span class="sxs-lookup"><span data-stu-id="9d85d-116">For more information about how to configure this property, see [Editing Functoid Properties and Input Parameters](../core/editing-functoid-properties-and-input-parameters.md) .</span></span> <span data-ttu-id="9d85d-117">你输入的输入列表必须是全面且完整，因为这是将用于配置的数据**表 Functoid 网格**属性。</span><span class="sxs-lookup"><span data-stu-id="9d85d-117">The list of inputs you enter must be comprehensive and complete because this is the data that you will use to configure the **Table Functoid Grid** property.</span></span> <span data-ttu-id="9d85d-118">输入参数必须按以下方式定义：</span><span class="sxs-lookup"><span data-stu-id="9d85d-118">The inputs must be defined as follows:</span></span>  
  
    -   <span data-ttu-id="9d85d-119">**第一个输入。**</span><span class="sxs-lookup"><span data-stu-id="9d85d-119">**First input.**</span></span> <span data-ttu-id="9d85d-120">第一个输入参数是指向输入实例消息记录或字段的链接。</span><span class="sxs-lookup"><span data-stu-id="9d85d-120">The first input parameter is the link to the input instance message record or field.</span></span> <span data-ttu-id="9d85d-121">**表循环**functoid 循环一次的记录或字段的每个实例。</span><span class="sxs-lookup"><span data-stu-id="9d85d-121">The **Table Looping** functoid loops once for each instance of the record or field.</span></span>  
  
        > [!NOTE]
        >  <span data-ttu-id="9d85d-122">此参数为必填输入参数。</span><span class="sxs-lookup"><span data-stu-id="9d85d-122">This is a required input.</span></span>  
  
    -   <span data-ttu-id="9d85d-123">**第二个输入。**</span><span class="sxs-lookup"><span data-stu-id="9d85d-123">**Second input.**</span></span> <span data-ttu-id="9d85d-124">第二个输入参数定义循环网格中的列数。</span><span class="sxs-lookup"><span data-stu-id="9d85d-124">The second input parameter defines the number of columns in the looping grid.</span></span> <span data-ttu-id="9d85d-125">该网格最多可包含 228 列。</span><span class="sxs-lookup"><span data-stu-id="9d85d-125">The grid may contain up to 228 columns.</span></span>  
  
        > [!NOTE]
        >  <span data-ttu-id="9d85d-126">此参数为必填输入参数。</span><span class="sxs-lookup"><span data-stu-id="9d85d-126">This is a required input.</span></span>  
  
    -   <span data-ttu-id="9d85d-127">**剩余的输入。**</span><span class="sxs-lookup"><span data-stu-id="9d85d-127">**Remaining inputs.**</span></span> <span data-ttu-id="9d85d-128">剩余输入**表循环**functoid 包含的所有可能的值，可能会出现在列表**表 Functoid 网格**。</span><span class="sxs-lookup"><span data-stu-id="9d85d-128">The remaining inputs for the **Table Looping** functoid consist of a list of all of the possible values that may appear in the **Table Functoid Grid**.</span></span>  
  
        > [!NOTE]
        >  <span data-ttu-id="9d85d-129">标记链接非常有用。</span><span class="sxs-lookup"><span data-stu-id="9d85d-129">Labeling links is very helpful.</span></span> <span data-ttu-id="9d85d-130">没有标签，链接将显示在**表 Functoid 网格**完全指定路径。</span><span class="sxs-lookup"><span data-stu-id="9d85d-130">Without labels, links appear in the **Table Functoid Grid** as fully specified paths.</span></span>  
  
         <span data-ttu-id="9d85d-131">有关分步说明有关如何配置输入**表循环**functoid，请参阅[如何添加表循环和一个映射到表提取程序 Functoid](../core/how-to-add-table-looping-and-table-extractor-functoids-to-a-map.md)。</span><span class="sxs-lookup"><span data-stu-id="9d85d-131">For step-by-step instructions about how to configure inputs for the **Table Looping** functoid, see [How to Add Table Looping and Table Extractor Functoids to a Map](../core/how-to-add-table-looping-and-table-extractor-functoids-to-a-map.md).</span></span> <span data-ttu-id="9d85d-132">具体地讲，就是步骤 3 到步骤 8。</span><span class="sxs-lookup"><span data-stu-id="9d85d-132">In particular, see steps 3 through 8.</span></span>  
  
-   <span data-ttu-id="9d85d-133">**配置表循环 functoid 表 Functoid 网格属性。**</span><span class="sxs-lookup"><span data-stu-id="9d85d-133">**Configure the Table Functoid Grid property of the Table Looping functoid.**</span></span> <span data-ttu-id="9d85d-134">使用**表 Functoid 网格**以打开**配置表循环 Functoid**对话框中，在其中配置循环的网格中的单元格。</span><span class="sxs-lookup"><span data-stu-id="9d85d-134">Use the **Table Functoid Grid** property to open the **Configure Table Looping Functoid** dialog box in which you configure the cells in the looping grid.</span></span>  
  
     <span data-ttu-id="9d85d-135">有关如何配置循环网格的分步说明，请参阅[如何添加表循环和一个映射到表提取程序 Functoid](../core/how-to-add-table-looping-and-table-extractor-functoids-to-a-map.md)。</span><span class="sxs-lookup"><span data-stu-id="9d85d-135">For step-by-step instructions about how to configure the looping grid, see [How to Add Table Looping and Table Extractor Functoids to a Map](../core/how-to-add-table-looping-and-table-extractor-functoids-to-a-map.md).</span></span> <span data-ttu-id="9d85d-136">具体地讲，就是步骤 9 到步骤 10。</span><span class="sxs-lookup"><span data-stu-id="9d85d-136">In particular, see steps 9 and 10.</span></span>  
  
-   <span data-ttu-id="9d85d-137">**配置表提取程序 functoid。**</span><span class="sxs-lookup"><span data-stu-id="9d85d-137">**Configure the Table Extractor functoids.**</span></span> <span data-ttu-id="9d85d-138">使用**输入参数**属性配置**表提取程序**functoid 输入，如下所示：</span><span class="sxs-lookup"><span data-stu-id="9d85d-138">Use the **Input Parameters** property to configure the **Table Extractor** functoid inputs as follows:</span></span>  
  
    -   <span data-ttu-id="9d85d-139">**第一个输入。**</span><span class="sxs-lookup"><span data-stu-id="9d85d-139">**First input.**</span></span> <span data-ttu-id="9d85d-140">第一个输入的参数**表提取程序**functoid 是**表循环**functoid。</span><span class="sxs-lookup"><span data-stu-id="9d85d-140">The first input parameter to a **Table Extractor** functoid is the **Table Looping** functoid.</span></span>  
  
    -   <span data-ttu-id="9d85d-141">**第二个输入。**</span><span class="sxs-lookup"><span data-stu-id="9d85d-141">**Second input.**</span></span> <span data-ttu-id="9d85d-142">第二个输入参数指定要从行中的哪一列提取数据。</span><span class="sxs-lookup"><span data-stu-id="9d85d-142">The second input parameter specifies the column in the row from which to extract data.</span></span>  
  
     <span data-ttu-id="9d85d-143">有关分步说明有关如何配置**表提取程序**与关联的 functoid**表循环**functoid，请参阅[如何添加表循环和表提取程序向地图 Functoid](../core/how-to-add-table-looping-and-table-extractor-functoids-to-a-map.md)。</span><span class="sxs-lookup"><span data-stu-id="9d85d-143">For step-by-step instructions about how to configure the **Table Extractor** functoids associated with a **Table Looping** functoid, see [How to Add Table Looping and Table Extractor Functoids to a Map](../core/how-to-add-table-looping-and-table-extractor-functoids-to-a-map.md).</span></span> <span data-ttu-id="9d85d-144">具体而言，请参阅步骤 11 到 16。</span><span class="sxs-lookup"><span data-stu-id="9d85d-144">In particular, see steps 11 through 16.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9d85d-145">另请参阅</span><span class="sxs-lookup"><span data-stu-id="9d85d-145">See Also</span></span>  
 <span data-ttu-id="9d85d-146">[表循环 Functoid](../core/table-looping-functoid.md) </span><span class="sxs-lookup"><span data-stu-id="9d85d-146">[Table Looping Functoid](../core/table-looping-functoid.md) </span></span>  
 <span data-ttu-id="9d85d-147">[表提取程序 Functoid](../core/table-extractor-functoid.md) </span><span class="sxs-lookup"><span data-stu-id="9d85d-147">[Table Extractor Functoid](../core/table-extractor-functoid.md) </span></span>  
 <span data-ttu-id="9d85d-148">[表驱动循环示例](../core/table-driven-looping-example.md) </span><span class="sxs-lookup"><span data-stu-id="9d85d-148">[Table-Driven Looping Example](../core/table-driven-looping-example.md) </span></span>  
 <span data-ttu-id="9d85d-149">[如何添加表循环以及到地图表提取程序 Functoid](../core/how-to-add-table-looping-and-table-extractor-functoids-to-a-map.md) </span><span class="sxs-lookup"><span data-stu-id="9d85d-149">[How to Add Table Looping and Table Extractor Functoids to a Map](../core/how-to-add-table-looping-and-table-extractor-functoids-to-a-map.md) </span></span>  
 <span data-ttu-id="9d85d-150">[高级的 Functoid](../core/advanced-functoids.md) </span><span class="sxs-lookup"><span data-stu-id="9d85d-150">[Advanced Functoids](../core/advanced-functoids.md) </span></span>  
 <span data-ttu-id="9d85d-151">[索引 Functoid](../core/index-functoid.md) </span><span class="sxs-lookup"><span data-stu-id="9d85d-151">[Index Functoid](../core/index-functoid.md) </span></span>  
 <span data-ttu-id="9d85d-152">[迭代 Functoid](../core/iteration-functoid.md) </span><span class="sxs-lookup"><span data-stu-id="9d85d-152">[Iteration Functoid](../core/iteration-functoid.md) </span></span>  
 <span data-ttu-id="9d85d-153">[循环 Functoid](../core/looping-functoid.md) </span><span class="sxs-lookup"><span data-stu-id="9d85d-153">[Looping Functoid](../core/looping-functoid.md) </span></span>  
 [<span data-ttu-id="9d85d-154">记录计数 Functoid</span><span class="sxs-lookup"><span data-stu-id="9d85d-154">Record Count Functoid</span></span>](../core/record-count-functoid.md)