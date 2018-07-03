---
title: 日期和时间 Functoid |Microsoft Docs
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
ms.openlocfilehash: 5224c409a6d705806cccc493009ce2c32062f0a1
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "37010662"
---
# <a name="date-and-time-functoids"></a><span data-ttu-id="60d89-102">“日期和时间”Functoid</span><span class="sxs-lookup"><span data-stu-id="60d89-102">Date and Time Functoids</span></span>

## <a name="overview"></a><span data-ttu-id="60d89-103">概述</span><span class="sxs-lookup"><span data-stu-id="60d89-103">Overview</span></span>
<span data-ttu-id="60d89-104">**日期 / 时间**functoid 可以分为两类。</span><span class="sxs-lookup"><span data-stu-id="60d89-104">**Date / Time** functoids can be divided into two categories.</span></span> <span data-ttu-id="60d89-105">第一类包含单个 functoid**添加天数**，用于将指定的天数添加到指定的日期和时间值。</span><span class="sxs-lookup"><span data-stu-id="60d89-105">The first category contains a single functoid, **Add Days**, which is used to add a specified number of days to a specified date and time value.</span></span> <span data-ttu-id="60d89-106">如果输出实例消息中的字段应包括对将来某个日期和时间的估计，这一类可能十分有用。</span><span class="sxs-lookup"><span data-stu-id="60d89-106">This can be useful when a field in the output instance message is supposed to include a date and time estimate in the future.</span></span> <span data-ttu-id="60d89-107">例如，**添加天数**functoid 可用于生成估计发货日期基于固定的增量了收到订单的日期。</span><span class="sxs-lookup"><span data-stu-id="60d89-107">For example, the **Add Days** functoid can be used to generate an estimated shipping date based a fixed delta from the date that an order was received.</span></span>  

 <span data-ttu-id="60d89-108">第二个类别包括所有中的剩余 functoid**日期和时间**类别。</span><span class="sxs-lookup"><span data-stu-id="60d89-108">The second category includes all of the remaining functoids in the **Date and Time** category.</span></span> <span data-ttu-id="60d89-109">这些 functoid 用于在运行时提供时间戳，以便输出实例消息中可以包括正在执行的消息转换的日期和时间。</span><span class="sxs-lookup"><span data-stu-id="60d89-109">They are used to provide a timestamp at run time, so that the date and time at which message transformation is being performed can be included in the output instance message.</span></span>  

 <span data-ttu-id="60d89-110">**添加天数**functoid 接受两个输入参数，而**日期**，**日期和时间**，以及**时间**functoid 具有任何输入参数。</span><span class="sxs-lookup"><span data-stu-id="60d89-110">The **Add Days** functoid accepts two input parameters, whereas the **Date**, **Date and Time**, and **Time** functoids have no input parameters.</span></span>  

## <a name="available-functoids"></a><span data-ttu-id="60d89-111">可用的 functoid</span><span class="sxs-lookup"><span data-stu-id="60d89-111">Available functoids</span></span>  
 <span data-ttu-id="60d89-112">**日期 / 时间**functoid 包括：</span><span class="sxs-lookup"><span data-stu-id="60d89-112">The **Date / Time** functoids are:</span></span> 

* <span data-ttu-id="60d89-113">添加天数</span><span class="sxs-lookup"><span data-stu-id="60d89-113">Add Days</span></span>
* <span data-ttu-id="60d89-114">date</span><span class="sxs-lookup"><span data-stu-id="60d89-114">Date</span></span>
* <span data-ttu-id="60d89-115">日期和时间</span><span class="sxs-lookup"><span data-stu-id="60d89-115">Date and Time</span></span>
* <span data-ttu-id="60d89-116">Time</span><span class="sxs-lookup"><span data-stu-id="60d89-116">Time</span></span>

<span data-ttu-id="60d89-117">提供了更多详细信息这些 functoid **Functoid 参考** [!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)]。</span><span class="sxs-lookup"><span data-stu-id="60d89-117">More details on these functoids are available **Functoid Reference** [!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)].</span></span>

## <a name="see-also"></a><span data-ttu-id="60d89-118">请参阅</span><span class="sxs-lookup"><span data-stu-id="60d89-118">See Also</span></span>  
- [<span data-ttu-id="60d89-119">如何向映射添加基本 Functoid</span><span class="sxs-lookup"><span data-stu-id="60d89-119">How to Add Basic Functoids to a Map</span></span>](../core/how-to-add-basic-functoids-to-a-map.md)   
- <span data-ttu-id="60d89-120">**日期和时间 Functoid 参考** [!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)]</span><span class="sxs-lookup"><span data-stu-id="60d89-120">**Date and Time Functoids Reference** [!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)]</span></span>
