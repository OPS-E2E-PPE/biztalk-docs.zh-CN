---
title: 位置记录注意事项 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 0f383d34-60a6-430f-ab0f-b1fc35cde568
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 96a03a10f14123f001ee100e65a3a423f362d94f
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65396217"
---
# <a name="positional-record-considerations"></a><span data-ttu-id="4f877-102">位置记录注意事项</span><span class="sxs-lookup"><span data-stu-id="4f877-102">Positional Record Considerations</span></span>
<span data-ttu-id="4f877-103">有一些注意事项，您应考虑使用时定位**记录**节点在架构中的。</span><span class="sxs-lookup"><span data-stu-id="4f877-103">There are a number of considerations that you should keep in mind when working with positional **Record** nodes within your schemas.</span></span> <span data-ttu-id="4f877-104">这包括有关标记处理、 位置记录嵌套、 位置数的方式，以及如何计算字段位置的注意事项。</span><span class="sxs-lookup"><span data-stu-id="4f877-104">This includes the considerations about tag handling, positional record nesting, how positions are counted, and how field positions are calculated.</span></span> <span data-ttu-id="4f877-105">本部分提供有关这些注意事项的信息。</span><span class="sxs-lookup"><span data-stu-id="4f877-105">This section provides information about these considerations.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="4f877-106">本节内容</span><span class="sxs-lookup"><span data-stu-id="4f877-106">In This Section</span></span>  
  
-   [<span data-ttu-id="4f877-107">位置记录中的标记处理</span><span class="sxs-lookup"><span data-stu-id="4f877-107">Tag Handling in Positional Records</span></span>](../core/tag-handling-in-positional-records.md)  
  
-   [<span data-ttu-id="4f877-108">嵌套位置记录</span><span class="sxs-lookup"><span data-stu-id="4f877-108">Nested Positional Records</span></span>](../core/nested-positional-records.md)  
  
-   [<span data-ttu-id="4f877-109">位置计数（单位为字节）</span><span class="sxs-lookup"><span data-stu-id="4f877-109">Position Counting in Bytes</span></span>](../core/position-counting-in-bytes.md)  
  
-   [<span data-ttu-id="4f877-110">字段位置计算</span><span class="sxs-lookup"><span data-stu-id="4f877-110">Field Position Calculation</span></span>](../core/field-position-calculation.md)