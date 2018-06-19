---
title: 高级 Functoid |Microsoft 文档
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
ms.openlocfilehash: 5002b639df79ece1019c2d013c128f615517ae5f
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22230389"
---
# <a name="advanced-functoids"></a><span data-ttu-id="c2cf2-102">高级的 Functoid</span><span class="sxs-lookup"><span data-stu-id="c2cf2-102">Advanced Functoids</span></span>

## <a name="overview"></a><span data-ttu-id="c2cf2-103">概述</span><span class="sxs-lookup"><span data-stu-id="c2cf2-103">Overview</span></span>
<span data-ttu-id="c2cf2-104">高级 functoid 根据用途可分为五组：</span><span class="sxs-lookup"><span data-stu-id="c2cf2-104">Advanced functoids fall into five groups, according to their use:</span></span>  
  
-   <span data-ttu-id="c2cf2-105">**管理循环记录。**</span><span class="sxs-lookup"><span data-stu-id="c2cf2-105">**Managing looping records.**</span></span> <span data-ttu-id="c2cf2-106">**索引**，**迭代**，**循环**， **Nil 值**，**记录计数**，**表提取程序**，和**表循环**时输入的实例消息包含与不可预测的各节 functoid 各种组合中使用的重复元素所表示的循环数源架构中的记录。</span><span class="sxs-lookup"><span data-stu-id="c2cf2-106">The **Index**, **Iteration**, **Looping**, **Nil Value**, **Record Count**, **Table Extractor**, and **Table Looping** functoids are used in various combinations when the input instance message contains sections with an unpredictable number of repeating elements, as represented by looping records in the source schema.</span></span>  
  
-   <span data-ttu-id="c2cf2-107">**条件映射。**</span><span class="sxs-lookup"><span data-stu-id="c2cf2-107">**Conditional mapping.**</span></span> <span data-ttu-id="c2cf2-108">**值映射**和**值映射 （平展）** functoid 用于提供从输入的实例消息到输出实例消息的条件映射。</span><span class="sxs-lookup"><span data-stu-id="c2cf2-108">The **Value Mapping** and **Value Mapping (Flattening)** functoids are used to provide conditional mapping from an input instance message to an output instance message.</span></span> <span data-ttu-id="c2cf2-109">如果它们的第一个输入参数为 True，则第二个输入参数将放入输出实例消息的指定元素或属性中；否则，将不会在输出实例消息中创建该元素或属性。</span><span class="sxs-lookup"><span data-stu-id="c2cf2-109">When their first input parameter is true, the second input parameter is put into the specified element or attribute in the output instance message; otherwise, that element or attribute is not created in the output instance message.</span></span>  
  
-   <span data-ttu-id="c2cf2-110">**任意脚本。**</span><span class="sxs-lookup"><span data-stu-id="c2cf2-110">**Arbitrary scripting.**</span></span> <span data-ttu-id="c2cf2-111">**脚本**functoid 用于运行任意脚本或已编译代码时输入的实例消息正在映射到输出实例消息。</span><span class="sxs-lookup"><span data-stu-id="c2cf2-111">The **Scripting** functoid is used to run arbitrary script or compiled code when an input instance message is being mapped to an output instance message.</span></span> <span data-ttu-id="c2cf2-112">此类脚本或编译代码可创建为从源实例消息、已配置的常数值、其他 functoid 的输出或它们的组合接受输入参数。</span><span class="sxs-lookup"><span data-stu-id="c2cf2-112">Such script or compiled code can be created so that it accepts input parameters from the source instance message, from configured constant values, from the output of another functoid, or some combination thereof.</span></span>  
  
-   <span data-ttu-id="c2cf2-113">**简单的映射。**</span><span class="sxs-lookup"><span data-stu-id="c2cf2-113">**Simple mapping.**</span></span> <span data-ttu-id="c2cf2-114">**大容量复制**functoid 可以用于复制的整个元素，包括从一个到输出实例消息的输入的实例消息及其子元素的任意深度。</span><span class="sxs-lookup"><span data-stu-id="c2cf2-114">The **Mass Copy** functoid can be used to copy an entire element, including its subelements to an arbitrary depth, from an input instance message to an output instance message.</span></span>  
  
-   <span data-ttu-id="c2cf2-115">**故障排除**。</span><span class="sxs-lookup"><span data-stu-id="c2cf2-115">**Troubleshooting**.</span></span> <span data-ttu-id="c2cf2-116">**断言**functoid 可以用于测试你的假设有关元素值。</span><span class="sxs-lookup"><span data-stu-id="c2cf2-116">The **Assert** functoid can be used to test your assumptions about element values.</span></span>  
  
## <a name="available-functoids"></a><span data-ttu-id="c2cf2-117">可用的 functoid</span><span class="sxs-lookup"><span data-stu-id="c2cf2-117">Available functoids</span></span>
  
 <span data-ttu-id="c2cf2-118">**高级**functoid 均：</span><span class="sxs-lookup"><span data-stu-id="c2cf2-118">The **Advanced** functoids are:</span></span> 

* <span data-ttu-id="c2cf2-119">“添加”Functoid</span><span class="sxs-lookup"><span data-stu-id="c2cf2-119">Assert Functoid</span></span>
* <span data-ttu-id="c2cf2-120">“索引”Functoid</span><span class="sxs-lookup"><span data-stu-id="c2cf2-120">Index Functoid</span></span> 
* <span data-ttu-id="c2cf2-121">迭代 Functoid</span><span class="sxs-lookup"><span data-stu-id="c2cf2-121">Iteration Functoid</span></span> 
* <span data-ttu-id="c2cf2-122">“循环”Functoid</span><span class="sxs-lookup"><span data-stu-id="c2cf2-122">Looping Functoid</span></span> 
* <span data-ttu-id="c2cf2-123">“批量复制”functoid</span><span class="sxs-lookup"><span data-stu-id="c2cf2-123">Mass Copy Functoid</span></span> 
* <span data-ttu-id="c2cf2-124">“零值”Functoid</span><span class="sxs-lookup"><span data-stu-id="c2cf2-124">Nil Value Functoid</span></span>
* <span data-ttu-id="c2cf2-125">“记录计数”Functoid</span><span class="sxs-lookup"><span data-stu-id="c2cf2-125">Record Count Functoid</span></span> 
* <span data-ttu-id="c2cf2-126">“脚本”Functoid</span><span class="sxs-lookup"><span data-stu-id="c2cf2-126">Scripting Functoid</span></span> 
* <span data-ttu-id="c2cf2-127">表循环和表提取程序 Functoid</span><span class="sxs-lookup"><span data-stu-id="c2cf2-127">Table Looping and Table Extractor Functoids</span></span>
* <span data-ttu-id="c2cf2-128">“值映射”Functoid</span><span class="sxs-lookup"><span data-stu-id="c2cf2-128">Value Mapping Functoid</span></span>
* <span data-ttu-id="c2cf2-129">“值映射(平展)”Functoid</span><span class="sxs-lookup"><span data-stu-id="c2cf2-129">Value Mapping (Flattening) Functoid</span></span>

<span data-ttu-id="c2cf2-130">这些 functoid 更多详细信息位于**Functoid 引用** [!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)]。</span><span class="sxs-lookup"><span data-stu-id="c2cf2-130">More details on these functoids are in the **Functoid Reference** [!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)].</span></span>
  
## <a name="next-steps"></a><span data-ttu-id="c2cf2-131">后续步骤</span><span class="sxs-lookup"><span data-stu-id="c2cf2-131">Next steps</span></span>
  
-   [<span data-ttu-id="c2cf2-132">断言 Functoid</span><span class="sxs-lookup"><span data-stu-id="c2cf2-132">Assert Functoid</span></span>](../core/assert-functoid.md)  
  
-   [<span data-ttu-id="c2cf2-133">索引 Functoid</span><span class="sxs-lookup"><span data-stu-id="c2cf2-133">Index Functoid</span></span>](../core/index-functoid.md)  
  
-   [<span data-ttu-id="c2cf2-134">迭代 Functoid</span><span class="sxs-lookup"><span data-stu-id="c2cf2-134">Iteration Functoid</span></span>](../core/iteration-functoid.md)  
  
-   [<span data-ttu-id="c2cf2-135">循环 Functoid</span><span class="sxs-lookup"><span data-stu-id="c2cf2-135">Looping Functoid</span></span>](../core/looping-functoid.md)  
  
-   [<span data-ttu-id="c2cf2-136">大容量复制 Functoid</span><span class="sxs-lookup"><span data-stu-id="c2cf2-136">Mass Copy Functoid</span></span>](../core/mass-copy-functoid.md)  
  
-   [<span data-ttu-id="c2cf2-137">Nil 值 Functoid</span><span class="sxs-lookup"><span data-stu-id="c2cf2-137">Nil Value Functoid</span></span>](../core/nil-value-functoid.md)  
  
-   [<span data-ttu-id="c2cf2-138">记录计数 Functoid</span><span class="sxs-lookup"><span data-stu-id="c2cf2-138">Record Count Functoid</span></span>](../core/record-count-functoid.md)  
  
-   [<span data-ttu-id="c2cf2-139">表循环和表提取程序 Functoid</span><span class="sxs-lookup"><span data-stu-id="c2cf2-139">Table Looping and Table Extractor Functoids</span></span>](../core/table-looping-and-table-extractor-functoids.md)  
  
-   [<span data-ttu-id="c2cf2-140">值映射 Functoid</span><span class="sxs-lookup"><span data-stu-id="c2cf2-140">Value Mapping Functoid</span></span>](../core/value-mapping-functoid.md)  
  
-   [<span data-ttu-id="c2cf2-141">映射 （拼合） Functoid 的值</span><span class="sxs-lookup"><span data-stu-id="c2cf2-141">Value Mapping (Flattening) Functoid</span></span>](../core/value-mapping-flattening-functoid.md)  
  
-   [<span data-ttu-id="c2cf2-142">脚本 Functoid</span><span class="sxs-lookup"><span data-stu-id="c2cf2-142">Scripting Functoid</span></span>](../core/scripting-functoid.md)