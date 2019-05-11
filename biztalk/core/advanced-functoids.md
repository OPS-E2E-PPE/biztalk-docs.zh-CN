---
title: 高级 Functoid |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 82bf2547-5e44-45f8-b577-97e5760a0339
caps.latest.revision: 12
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: b0e906b7e1c4d7ca71f952441cd22542e9637399
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65360507"
---
# <a name="advanced-functoids"></a><span data-ttu-id="de80b-102">高级的 Functoid</span><span class="sxs-lookup"><span data-stu-id="de80b-102">Advanced Functoids</span></span>

## <a name="overview"></a><span data-ttu-id="de80b-103">概述</span><span class="sxs-lookup"><span data-stu-id="de80b-103">Overview</span></span>
<span data-ttu-id="de80b-104">高级的 functoid 根据用途分为五个组：</span><span class="sxs-lookup"><span data-stu-id="de80b-104">Advanced functoids fall into five groups, according to their use:</span></span>  
  
-   <span data-ttu-id="de80b-105">**管理循环记录。**</span><span class="sxs-lookup"><span data-stu-id="de80b-105">**Managing looping records.**</span></span> <span data-ttu-id="de80b-106">**索引**，**迭代**，**循环**， **Nil 值**，**记录计数**，**表提取程序**，并**表循环**functoid 使用在各种组合中输入的实例消息包含具有不可预测的部分数由循环重复元素，源架构中的记录。</span><span class="sxs-lookup"><span data-stu-id="de80b-106">The **Index**, **Iteration**, **Looping**, **Nil Value**, **Record Count**, **Table Extractor**, and **Table Looping** functoids are used in various combinations when the input instance message contains sections with an unpredictable number of repeating elements, as represented by looping records in the source schema.</span></span>  
  
-   <span data-ttu-id="de80b-107">**条件映射。**</span><span class="sxs-lookup"><span data-stu-id="de80b-107">**Conditional mapping.**</span></span> <span data-ttu-id="de80b-108">**值映射**并**值映射 （平展）** functoid 用于提供从输入的实例消息到输出实例消息的条件映射。</span><span class="sxs-lookup"><span data-stu-id="de80b-108">The **Value Mapping** and **Value Mapping (Flattening)** functoids are used to provide conditional mapping from an input instance message to an output instance message.</span></span> <span data-ttu-id="de80b-109">当其第一个输入的参数为 true 时，第二个输入的参数被放置到指定的元素或属性在输出实例消息中;否则，该元素或属性不被创建的输出实例消息中。</span><span class="sxs-lookup"><span data-stu-id="de80b-109">When their first input parameter is true, the second input parameter is put into the specified element or attribute in the output instance message; otherwise, that element or attribute is not created in the output instance message.</span></span>  
  
-   <span data-ttu-id="de80b-110">**任意脚本。**</span><span class="sxs-lookup"><span data-stu-id="de80b-110">**Arbitrary scripting.**</span></span> <span data-ttu-id="de80b-111">**脚本**functoid 用于运行任意脚本或编译代码时的输入的实例消息映射到输出实例消息。</span><span class="sxs-lookup"><span data-stu-id="de80b-111">The **Scripting** functoid is used to run arbitrary script or compiled code when an input instance message is being mapped to an output instance message.</span></span> <span data-ttu-id="de80b-112">可以创建此类脚本或已编译的代码，以便它接受来自已配置的常量值，从另一个 functoid 或它们的某种组合的输出的源实例消息中的输入的参数。</span><span class="sxs-lookup"><span data-stu-id="de80b-112">Such script or compiled code can be created so that it accepts input parameters from the source instance message, from configured constant values, from the output of another functoid, or some combination thereof.</span></span>  
  
-   <span data-ttu-id="de80b-113">**简单映射。**</span><span class="sxs-lookup"><span data-stu-id="de80b-113">**Simple mapping.**</span></span> <span data-ttu-id="de80b-114">**批量复制**functoid 可用于复制的整个元素，从输入的实例消息到输出实例消息到任意深度，包括及其子元素。</span><span class="sxs-lookup"><span data-stu-id="de80b-114">The **Mass Copy** functoid can be used to copy an entire element, including its subelements to an arbitrary depth, from an input instance message to an output instance message.</span></span>  
  
-   <span data-ttu-id="de80b-115">**故障排除**。</span><span class="sxs-lookup"><span data-stu-id="de80b-115">**Troubleshooting**.</span></span> <span data-ttu-id="de80b-116">**Assert** functoid 可用于测试有关元素值的假设。</span><span class="sxs-lookup"><span data-stu-id="de80b-116">The **Assert** functoid can be used to test your assumptions about element values.</span></span>  
  
## <a name="available-functoids"></a><span data-ttu-id="de80b-117">可用的 functoid</span><span class="sxs-lookup"><span data-stu-id="de80b-117">Available functoids</span></span>
  
 <span data-ttu-id="de80b-118">**高级**functoid 包括：</span><span class="sxs-lookup"><span data-stu-id="de80b-118">The **Advanced** functoids are:</span></span> 

* <span data-ttu-id="de80b-119">添加 Functoid</span><span class="sxs-lookup"><span data-stu-id="de80b-119">Assert Functoid</span></span>
* <span data-ttu-id="de80b-120">索引 Functoid</span><span class="sxs-lookup"><span data-stu-id="de80b-120">Index Functoid</span></span> 
* <span data-ttu-id="de80b-121">迭代 Functoid</span><span class="sxs-lookup"><span data-stu-id="de80b-121">Iteration Functoid</span></span> 
* <span data-ttu-id="de80b-122">循环 Functoid</span><span class="sxs-lookup"><span data-stu-id="de80b-122">Looping Functoid</span></span> 
* <span data-ttu-id="de80b-123">批量复制 Functoid</span><span class="sxs-lookup"><span data-stu-id="de80b-123">Mass Copy Functoid</span></span> 
* <span data-ttu-id="de80b-124">零值 Functoid</span><span class="sxs-lookup"><span data-stu-id="de80b-124">Nil Value Functoid</span></span>
* <span data-ttu-id="de80b-125">“记录计数”Functoid</span><span class="sxs-lookup"><span data-stu-id="de80b-125">Record Count Functoid</span></span> 
* <span data-ttu-id="de80b-126">脚本 Functoid</span><span class="sxs-lookup"><span data-stu-id="de80b-126">Scripting Functoid</span></span> 
* <span data-ttu-id="de80b-127">表循环和表提取程序 Functoid</span><span class="sxs-lookup"><span data-stu-id="de80b-127">Table Looping and Table Extractor Functoids</span></span>
* <span data-ttu-id="de80b-128">值映射 Functoid</span><span class="sxs-lookup"><span data-stu-id="de80b-128">Value Mapping Functoid</span></span>
* <span data-ttu-id="de80b-129">“值映射(平展)”Functoid</span><span class="sxs-lookup"><span data-stu-id="de80b-129">Value Mapping (Flattening) Functoid</span></span>

<span data-ttu-id="de80b-130">这些 functoid 的详细信息位于**Functoid 参考** [!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)]。</span><span class="sxs-lookup"><span data-stu-id="de80b-130">More details on these functoids are in the **Functoid Reference** [!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)].</span></span>
  
## <a name="next-steps"></a><span data-ttu-id="de80b-131">后续步骤</span><span class="sxs-lookup"><span data-stu-id="de80b-131">Next steps</span></span>
  
-   [<span data-ttu-id="de80b-132">“添加”Functoid</span><span class="sxs-lookup"><span data-stu-id="de80b-132">Assert Functoid</span></span>](../core/assert-functoid.md)  
  
-   [<span data-ttu-id="de80b-133">“索引”Functoid</span><span class="sxs-lookup"><span data-stu-id="de80b-133">Index Functoid</span></span>](../core/index-functoid.md)  
  
-   [<span data-ttu-id="de80b-134">“迭代”Functoid</span><span class="sxs-lookup"><span data-stu-id="de80b-134">Iteration Functoid</span></span>](../core/iteration-functoid.md)  
  
-   [<span data-ttu-id="de80b-135">循环 Functoid</span><span class="sxs-lookup"><span data-stu-id="de80b-135">Looping Functoid</span></span>](../core/looping-functoid.md)  
  
-   [<span data-ttu-id="de80b-136">“批量复制”Functoid</span><span class="sxs-lookup"><span data-stu-id="de80b-136">Mass Copy Functoid</span></span>](../core/mass-copy-functoid.md)  
  
-   [<span data-ttu-id="de80b-137">“零值”Functoid</span><span class="sxs-lookup"><span data-stu-id="de80b-137">Nil Value Functoid</span></span>](../core/nil-value-functoid.md)  
  
-   [<span data-ttu-id="de80b-138">“记录计数”Functoid</span><span class="sxs-lookup"><span data-stu-id="de80b-138">Record Count Functoid</span></span>](../core/record-count-functoid.md)  
  
-   [<span data-ttu-id="de80b-139">“表循环”和“表提取程序”Functoid</span><span class="sxs-lookup"><span data-stu-id="de80b-139">Table Looping and Table Extractor Functoids</span></span>](../core/table-looping-and-table-extractor-functoids.md)  
  
-   [<span data-ttu-id="de80b-140">“值映射”Functoid</span><span class="sxs-lookup"><span data-stu-id="de80b-140">Value Mapping Functoid</span></span>](../core/value-mapping-functoid.md)  
  
-   [<span data-ttu-id="de80b-141">“值映射（平展）”Functoid</span><span class="sxs-lookup"><span data-stu-id="de80b-141">Value Mapping (Flattening) Functoid</span></span>](../core/value-mapping-flattening-functoid.md)  
  
-   [<span data-ttu-id="de80b-142">“脚本编写”Functoid</span><span class="sxs-lookup"><span data-stu-id="de80b-142">Scripting Functoid</span></span>](../core/scripting-functoid.md)