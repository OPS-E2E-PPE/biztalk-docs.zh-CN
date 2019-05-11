---
title: 表提取程序 Functoid |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- Table Extractor functoids
- Table Extractor functoids, about Table Extractor functoids
ms.assetid: cb5f6f15-f4e1-46d3-846e-6e2664699b62
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 0aa7fa4226f0a79efcc6b8bd1b3bdc79f82430b1
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65291697"
---
# <a name="table-extractor-functoid"></a><span data-ttu-id="75636-102">表提取程序 Functoid</span><span class="sxs-lookup"><span data-stu-id="75636-102">Table Extractor Functoid</span></span>
<span data-ttu-id="75636-103">**表提取程序**functoid 确定将哪些数据从作为循环网格中的每一行提取**表循环**functoid 显示行。</span><span class="sxs-lookup"><span data-stu-id="75636-103">The **Table Extractor** functoid determines which data to extract from each row of the looping grid as the **Table Looping** functoid presents the rows.</span></span> <span data-ttu-id="75636-104">需要一个**表提取程序**functoid 输出的每个字段。</span><span class="sxs-lookup"><span data-stu-id="75636-104">You need one **Table Extractor** functoid for each output field.</span></span> <span data-ttu-id="75636-105">例如，假设输入的实例消息中采用单一格式，有一个地址，但在输出实例消息需要两种格式，并标记每一种格式中的地址。</span><span class="sxs-lookup"><span data-stu-id="75636-105">For example, suppose your input instance message had an address in a single format, but your output instance message needed the address in two formats with each format tagged.</span></span> <span data-ttu-id="75636-106">然后，将需要**表提取程序**functoid 为标记和每个元素的地址。</span><span class="sxs-lookup"><span data-stu-id="75636-106">Then you would need a **Table Extractor** functoid for the tag and for each element of the address.</span></span> <span data-ttu-id="75636-107">有关配置详细信息**表提取程序**functoid，请参阅[Table-Driven 循环配置](../core/table-driven-looping-configuration.md)。</span><span class="sxs-lookup"><span data-stu-id="75636-107">For more information about configuring the **Table Extractor** functoid, see [Table-Driven Looping Configuration](../core/table-driven-looping-configuration.md).</span></span> <span data-ttu-id="75636-108">另请参阅[Table-Driven 循环示例](../core/table-driven-looping-example.md)。</span><span class="sxs-lookup"><span data-stu-id="75636-108">Also see [Table-Driven Looping Example](../core/table-driven-looping-example.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="75636-109">请参阅</span><span class="sxs-lookup"><span data-stu-id="75636-109">See Also</span></span>  
 <span data-ttu-id="75636-110">[表循环 Functoid](../core/table-looping-functoid.md) </span><span class="sxs-lookup"><span data-stu-id="75636-110">[Table Looping Functoid](../core/table-looping-functoid.md) </span></span>  
 <span data-ttu-id="75636-111">[如何添加表循环和表提取程序 Functoid 映射](../core/how-to-add-table-looping-and-table-extractor-functoids-to-a-map.md) </span><span class="sxs-lookup"><span data-stu-id="75636-111">[How to Add Table Looping and Table Extractor Functoids to a Map](../core/how-to-add-table-looping-and-table-extractor-functoids-to-a-map.md) </span></span>  
 <span data-ttu-id="75636-112">[高级的 Functoid](../core/advanced-functoids.md) </span><span class="sxs-lookup"><span data-stu-id="75636-112">[Advanced Functoids](../core/advanced-functoids.md) </span></span>  
 <span data-ttu-id="75636-113">[索引 Functoid](../core/index-functoid.md) </span><span class="sxs-lookup"><span data-stu-id="75636-113">[Index Functoid](../core/index-functoid.md) </span></span>  
 <span data-ttu-id="75636-114">[迭代 Functoid](../core/iteration-functoid.md) </span><span class="sxs-lookup"><span data-stu-id="75636-114">[Iteration Functoid](../core/iteration-functoid.md) </span></span>  
 <span data-ttu-id="75636-115">[循环 Functoid](../core/looping-functoid.md) </span><span class="sxs-lookup"><span data-stu-id="75636-115">[Looping Functoid](../core/looping-functoid.md) </span></span>  
 [<span data-ttu-id="75636-116">记录计数 Functoid</span><span class="sxs-lookup"><span data-stu-id="75636-116">Record Count Functoid</span></span>](../core/record-count-functoid.md)