---
title: 表循环和表提取程序 Functoid |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 2907aada-f11a-485c-85c8-03092803ccf7
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: fe6660e5fbfb226ff49c394ee83d7205bd6e2dca
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65291642"
---
# <a name="table-looping-and-table-extractor-functoids"></a><span data-ttu-id="8d9d4-102">表循环和表提取程序 Functoid</span><span class="sxs-lookup"><span data-stu-id="8d9d4-102">Table Looping and Table Extractor Functoids</span></span>

## <a name="overview"></a><span data-ttu-id="8d9d4-103">概述</span><span class="sxs-lookup"><span data-stu-id="8d9d4-103">Overview</span></span>
<span data-ttu-id="8d9d4-104">在映射中，通常都会有一个结构中的输出实例消息的输入的实例消息中的每个结构。</span><span class="sxs-lookup"><span data-stu-id="8d9d4-104">In a map, you commonly have one structure in the output instance message for each structure in the input instance message.</span></span> <span data-ttu-id="8d9d4-105">但是，也会出现需要一个输入的实例结构生成多个输出实例结构的情况。</span><span class="sxs-lookup"><span data-stu-id="8d9d4-105">However, there are cases when you need an input instance structure to produce multiple output instance structures.</span></span> <span data-ttu-id="8d9d4-106">表驱动循环，可创建生成多个结构的映射。</span><span class="sxs-lookup"><span data-stu-id="8d9d4-106">Table-driven looping enables you to create maps generating such multiple structures.</span></span>  
  
 <span data-ttu-id="8d9d4-107">表驱动循环使用**表循环**functoid 和**表提取程序**functoid。</span><span class="sxs-lookup"><span data-stu-id="8d9d4-107">Table-driven looping uses the **Table Looping** functoid and the **Table Extractor** functoid.</span></span> <span data-ttu-id="8d9d4-108">**表循环**functoid 已配置的内部表。</span><span class="sxs-lookup"><span data-stu-id="8d9d4-108">The **Table Looping** functoid has an internal table you configure.</span></span> <span data-ttu-id="8d9d4-109">对于每个输入记录或字段中，**表循环**functoid 会输出表，一次一个的行。</span><span class="sxs-lookup"><span data-stu-id="8d9d4-109">For each input record or field, the **Table Looping** functoid outputs the rows of the table, one at a time.</span></span> <span data-ttu-id="8d9d4-110">例如，如果有十个记录中的输入的实例消息和内部表中的两个行**表循环**，则 functoid 会输出二十行，两个用于每条记录的总数。</span><span class="sxs-lookup"><span data-stu-id="8d9d4-110">For example, if there are ten records in the input instance message and two rows in the internal table of the **Table Looping**, the functoid outputs a total of twenty rows, two for each of the ten records.</span></span> <span data-ttu-id="8d9d4-111">**表提取程序**functoid 从行提取所需的项，并将其传递到输出实例消息。</span><span class="sxs-lookup"><span data-stu-id="8d9d4-111">The **Table Extractor** functoid extracts the desired item from a row and passes it on to the output instance message.</span></span>  
  
 <span data-ttu-id="8d9d4-112">有关更多详细信息，请参阅**表循环 Functoid 引用**并**表提取程序 Functoid 引用** [!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)]。</span><span class="sxs-lookup"><span data-stu-id="8d9d4-112">For more details, see the **Table Looping Functoid Reference** and **Table Extractor Functoid Reference** [!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)].</span></span>
  
## <a name="next-steps"></a><span data-ttu-id="8d9d4-113">后续步骤</span><span class="sxs-lookup"><span data-stu-id="8d9d4-113">Next steps</span></span>
  
-   [<span data-ttu-id="8d9d4-114">“表循环”Functoid</span><span class="sxs-lookup"><span data-stu-id="8d9d4-114">Table Looping Functoid</span></span>](../core/table-looping-functoid.md)  
  
-   [<span data-ttu-id="8d9d4-115">“表提取程序”functoid</span><span class="sxs-lookup"><span data-stu-id="8d9d4-115">Table Extractor Functoid</span></span>](../core/table-extractor-functoid.md)  
  
-   [<span data-ttu-id="8d9d4-116">表驱动循环配置</span><span class="sxs-lookup"><span data-stu-id="8d9d4-116">Table-Driven Looping Configuration</span></span>](../core/table-driven-looping-configuration.md)  
  
-   [<span data-ttu-id="8d9d4-117">表驱动循环示例</span><span class="sxs-lookup"><span data-stu-id="8d9d4-117">Table-Driven Looping Example</span></span>](../core/table-driven-looping-example.md)