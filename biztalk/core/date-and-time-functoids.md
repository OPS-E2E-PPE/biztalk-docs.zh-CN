---
title: 日期和时间 Functoid |Microsoft 文档
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 2e2d49f5-1aaf-4e4d-8da1-e8605304dccb
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 5ec31607ecefb417fef597b5ba700e6461c71a2f
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22238517"
---
# <a name="date-and-time-functoids"></a><span data-ttu-id="150b9-102">“日期和时间”Functoid</span><span class="sxs-lookup"><span data-stu-id="150b9-102">Date and Time Functoids</span></span>

## <a name="overview"></a><span data-ttu-id="150b9-103">概述</span><span class="sxs-lookup"><span data-stu-id="150b9-103">Overview</span></span>
<span data-ttu-id="150b9-104">**日期 / 时间**functoid 可以划分为两个类别。</span><span class="sxs-lookup"><span data-stu-id="150b9-104">**Date / Time** functoids can be divided into two categories.</span></span> <span data-ttu-id="150b9-105">第一个类别包含单个 functoid，**添加天**，它用于将指定的天数添加到指定的日期和时间值。</span><span class="sxs-lookup"><span data-stu-id="150b9-105">The first category contains a single functoid, **Add Days**, which is used to add a specified number of days to a specified date and time value.</span></span> <span data-ttu-id="150b9-106">如果输出实例消息中的字段应包括对将来某个日期和时间的估计，这一类可能十分有用。</span><span class="sxs-lookup"><span data-stu-id="150b9-106">This can be useful when a field in the output instance message is supposed to include a date and time estimate in the future.</span></span> <span data-ttu-id="150b9-107">例如，**添加天**functoid 可以用于生成估计传送日期基于固定的增量从了收到订单的日期。</span><span class="sxs-lookup"><span data-stu-id="150b9-107">For example, the **Add Days** functoid can be used to generate an estimated shipping date based a fixed delta from the date that an order was received.</span></span>  
  
 <span data-ttu-id="150b9-108">第二个类别包括所有在剩余 functoid**日期和时间**类别。</span><span class="sxs-lookup"><span data-stu-id="150b9-108">The second category includes all of the remaining functoids in the **Date and Time** category.</span></span> <span data-ttu-id="150b9-109">这些 functoid 用于在运行时提供时间戳，以便输出实例消息中可以包括正在执行的消息转换的日期和时间。</span><span class="sxs-lookup"><span data-stu-id="150b9-109">They are used to provide a timestamp at run time, so that the date and time at which message transformation is being performed can be included in the output instance message.</span></span>  
  
 <span data-ttu-id="150b9-110">**添加天**functoid 接受两个输入参数，而**日期**，**日期和时间**，和**时间**functoid 产生任何影响参数。</span><span class="sxs-lookup"><span data-stu-id="150b9-110">The **Add Days** functoid accepts two input parameters, whereas the **Date**, **Date and Time**, and **Time** functoids have no input parameters.</span></span>  

## <a name="available-functoids"></a><span data-ttu-id="150b9-111">可用的 functoid</span><span class="sxs-lookup"><span data-stu-id="150b9-111">Available functoids</span></span>  
 <span data-ttu-id="150b9-112">**日期 / 时间**functoid 均：</span><span class="sxs-lookup"><span data-stu-id="150b9-112">The **Date / Time** functoids are:</span></span> 

* <span data-ttu-id="150b9-113">添加天数</span><span class="sxs-lookup"><span data-stu-id="150b9-113">Add Days</span></span>
* <span data-ttu-id="150b9-114">日期</span><span class="sxs-lookup"><span data-stu-id="150b9-114">Date</span></span>
* <span data-ttu-id="150b9-115">日期和时间</span><span class="sxs-lookup"><span data-stu-id="150b9-115">Date and Time</span></span>
* <span data-ttu-id="150b9-116">Time</span><span class="sxs-lookup"><span data-stu-id="150b9-116">Time</span></span>

<span data-ttu-id="150b9-117">提供了更多详细信息上这些 functoid **Functoid 引用** [!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)]。</span><span class="sxs-lookup"><span data-stu-id="150b9-117">More details on these functoids are available **Functoid Reference** [!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)].</span></span>
  
## <a name="see-also"></a><span data-ttu-id="150b9-118">另请参阅</span><span class="sxs-lookup"><span data-stu-id="150b9-118">See Also</span></span>  
-  [<span data-ttu-id="150b9-119">如何在向地图添加基本 Functoid</span><span class="sxs-lookup"><span data-stu-id="150b9-119">How to Add Basic Functoids to a Map</span></span>](../core/how-to-add-basic-functoids-to-a-map.md)   
-  <span data-ttu-id="150b9-120">**日期和时间 Functoid 引用**[!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)]</span><span class="sxs-lookup"><span data-stu-id="150b9-120">**Date and Time Functoids Reference** [!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)]</span></span>