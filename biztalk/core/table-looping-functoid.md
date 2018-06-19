---
title: 表循环 Functoid |Microsoft 文档
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- Table Looping functoids
- Table Looping functoids, about Table Looping functoids
ms.assetid: 6189a789-afe7-4e72-a778-2b0374db8f69
caps.latest.revision: 10
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 6c5e5f2967fb48bfe896c26246db1630266812f5
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22278237"
---
# <a name="table-looping-functoid"></a><span data-ttu-id="0eacc-102">“表循环”Functoid</span><span class="sxs-lookup"><span data-stu-id="0eacc-102">Table Looping Functoid</span></span>
<span data-ttu-id="0eacc-103">**表循环**functoid 使你能够创建要在创建输出实例消息中使用的输出值的表。</span><span class="sxs-lookup"><span data-stu-id="0eacc-103">The **Table Looping** functoid enables you to create a table of output values to use in creating the output instance message.</span></span> <span data-ttu-id="0eacc-104">该表中的数据可以由链接和常数组成。</span><span class="sxs-lookup"><span data-stu-id="0eacc-104">The data in the table can consist of links and constants.</span></span> <span data-ttu-id="0eacc-105">第一个输入的参数**表循环**functoid 配置作用域，或次数将循环记录。</span><span class="sxs-lookup"><span data-stu-id="0eacc-105">The first input parameter to the **Table Looping** functoid configures the scope, or how many times the records will loop.</span></span> <span data-ttu-id="0eacc-106">第二个输入参数**表循环**functoid 确定多少列是在表中，并且剩余输入定义为表的可能的单元格值顺序不分先后。</span><span class="sxs-lookup"><span data-stu-id="0eacc-106">The second input parameter for the **Table Looping** functoid determines how many columns are in the table, and the remaining inputs define possible cell values for the table, in no particular order.</span></span> <span data-ttu-id="0eacc-107">有关使用这些属性的详细信息，请参阅[Table-Driven 循环配置](../core/table-driven-looping-configuration.md)。</span><span class="sxs-lookup"><span data-stu-id="0eacc-107">For more information about working with these properties, see [Table-Driven Looping Configuration](../core/table-driven-looping-configuration.md).</span></span> <span data-ttu-id="0eacc-108">另请参阅[Table-Driven 循环示例](../core/table-driven-looping-example.md)。</span><span class="sxs-lookup"><span data-stu-id="0eacc-108">Also see [Table-Driven Looping Example](../core/table-driven-looping-example.md).</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="0eacc-109">**表循环**functoid 重复与它连接到的循环记录。</span><span class="sxs-lookup"><span data-stu-id="0eacc-109">The **Table Looping** functoid repeats with the looping record it is connected to.</span></span> <span data-ttu-id="0eacc-110">在每次迭代中，对于表循环网格中的每一行该 functoid 都将循环一次，从而生成多个输出循环。</span><span class="sxs-lookup"><span data-stu-id="0eacc-110">Within each iteration, it loops once per row in the table looping grid, producing multiple output loops.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0eacc-111">另请参阅</span><span class="sxs-lookup"><span data-stu-id="0eacc-111">See Also</span></span>  
 <span data-ttu-id="0eacc-112">[表提取程序 Functoid](../core/table-extractor-functoid.md) </span><span class="sxs-lookup"><span data-stu-id="0eacc-112">[Table Extractor Functoid](../core/table-extractor-functoid.md) </span></span>  
 <span data-ttu-id="0eacc-113">[如何添加表循环以及到地图表提取程序 Functoid](../core/how-to-add-table-looping-and-table-extractor-functoids-to-a-map.md) </span><span class="sxs-lookup"><span data-stu-id="0eacc-113">[How to Add Table Looping and Table Extractor Functoids to a Map](../core/how-to-add-table-looping-and-table-extractor-functoids-to-a-map.md) </span></span>  
 <span data-ttu-id="0eacc-114">[高级的 Functoid](../core/advanced-functoids.md) </span><span class="sxs-lookup"><span data-stu-id="0eacc-114">[Advanced Functoids](../core/advanced-functoids.md) </span></span>  
 <span data-ttu-id="0eacc-115">[索引 Functoid](../core/index-functoid.md) </span><span class="sxs-lookup"><span data-stu-id="0eacc-115">[Index Functoid](../core/index-functoid.md) </span></span>  
 <span data-ttu-id="0eacc-116">[迭代 Functoid](../core/iteration-functoid.md) </span><span class="sxs-lookup"><span data-stu-id="0eacc-116">[Iteration Functoid](../core/iteration-functoid.md) </span></span>  
 <span data-ttu-id="0eacc-117">[循环 Functoid](../core/looping-functoid.md) </span><span class="sxs-lookup"><span data-stu-id="0eacc-117">[Looping Functoid](../core/looping-functoid.md) </span></span>  
 [<span data-ttu-id="0eacc-118">记录计数 Functoid</span><span class="sxs-lookup"><span data-stu-id="0eacc-118">Record Count Functoid</span></span>](../core/record-count-functoid.md)