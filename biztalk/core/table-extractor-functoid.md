---
title: "表提取程序 Functoid |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- Table Extractor functoids
- Table Extractor functoids, about Table Extractor functoids
ms.assetid: cb5f6f15-f4e1-46d3-846e-6e2664699b62
caps.latest.revision: "7"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 837762dcf1bd0814494f05712eb7d616cdfa7180
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="table-extractor-functoid"></a><span data-ttu-id="7fa28-102">“表提取程序”Functoid</span><span class="sxs-lookup"><span data-stu-id="7fa28-102">Table Extractor Functoid</span></span>
<span data-ttu-id="7fa28-103">**表提取程序**functoid 确定要从每个循环网格行中提取的数据**表循环**functoid 显示行。</span><span class="sxs-lookup"><span data-stu-id="7fa28-103">The **Table Extractor** functoid determines which data to extract from each row of the looping grid as the **Table Looping** functoid presents the rows.</span></span> <span data-ttu-id="7fa28-104">你需要一个**表提取程序**functoid 为每个输出字段。</span><span class="sxs-lookup"><span data-stu-id="7fa28-104">You need one **Table Extractor** functoid for each output field.</span></span> <span data-ttu-id="7fa28-105">例如，假设您的输入实例消息中的地址采用单一格式，而输出实例消息需要为该地址采用两种格式，并标记出每一种格式。</span><span class="sxs-lookup"><span data-stu-id="7fa28-105">For example, suppose your input instance message had an address in a single format, but your output instance message needed the address in two formats with each format tagged.</span></span> <span data-ttu-id="7fa28-106">然后，你将需要**表提取程序**functoid 的标记和地址的每个元素。</span><span class="sxs-lookup"><span data-stu-id="7fa28-106">Then you would need a **Table Extractor** functoid for the tag and for each element of the address.</span></span> <span data-ttu-id="7fa28-107">有关配置的详细信息**表提取程序**functoid，请参阅[Table-Driven 循环配置](../core/table-driven-looping-configuration.md)。</span><span class="sxs-lookup"><span data-stu-id="7fa28-107">For more information about configuring the **Table Extractor** functoid, see [Table-Driven Looping Configuration](../core/table-driven-looping-configuration.md).</span></span> <span data-ttu-id="7fa28-108">另请参阅[Table-Driven 循环示例](../core/table-driven-looping-example.md)。</span><span class="sxs-lookup"><span data-stu-id="7fa28-108">Also see [Table-Driven Looping Example](../core/table-driven-looping-example.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7fa28-109">另请参阅</span><span class="sxs-lookup"><span data-stu-id="7fa28-109">See Also</span></span>  
 <span data-ttu-id="7fa28-110">[表循环 Functoid](../core/table-looping-functoid.md) </span><span class="sxs-lookup"><span data-stu-id="7fa28-110">[Table Looping Functoid](../core/table-looping-functoid.md) </span></span>  
 <span data-ttu-id="7fa28-111">[如何添加表循环以及到地图表提取程序 Functoid](../core/how-to-add-table-looping-and-table-extractor-functoids-to-a-map.md) </span><span class="sxs-lookup"><span data-stu-id="7fa28-111">[How to Add Table Looping and Table Extractor Functoids to a Map](../core/how-to-add-table-looping-and-table-extractor-functoids-to-a-map.md) </span></span>  
 <span data-ttu-id="7fa28-112">[高级的 Functoid](../core/advanced-functoids.md) </span><span class="sxs-lookup"><span data-stu-id="7fa28-112">[Advanced Functoids](../core/advanced-functoids.md) </span></span>  
 <span data-ttu-id="7fa28-113">[索引 Functoid](../core/index-functoid.md) </span><span class="sxs-lookup"><span data-stu-id="7fa28-113">[Index Functoid](../core/index-functoid.md) </span></span>  
 <span data-ttu-id="7fa28-114">[迭代 Functoid](../core/iteration-functoid.md) </span><span class="sxs-lookup"><span data-stu-id="7fa28-114">[Iteration Functoid](../core/iteration-functoid.md) </span></span>  
 <span data-ttu-id="7fa28-115">[循环 Functoid](../core/looping-functoid.md) </span><span class="sxs-lookup"><span data-stu-id="7fa28-115">[Looping Functoid](../core/looping-functoid.md) </span></span>  
 [<span data-ttu-id="7fa28-116">记录计数 Functoid</span><span class="sxs-lookup"><span data-stu-id="7fa28-116">Record Count Functoid</span></span>](../core/record-count-functoid.md)