---
title: "处理阶段数 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- processing, stages
- process management solution tutorial, processing stages
ms.assetid: 74bd9f8c-99b4-4931-a096-6c54221ab2e5
caps.latest.revision: "9"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 1f61c5c348e54ea096c921cb6fc63f0db339dbf4
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="number-of-processing-stages"></a><span data-ttu-id="ea46d-102">处理阶段数</span><span class="sxs-lookup"><span data-stu-id="ea46d-102">Number of Processing Stages</span></span>
<span data-ttu-id="ea46d-103">该解决方案可将订单流程分为若干阶段，以便可以通过替换阶段来修改该流程，而无需中断长时间运行的订单。</span><span class="sxs-lookup"><span data-stu-id="ea46d-103">The solution separates the order process into stages, so that it is possible to modify the process (by replacing stages) without disrupting long-running orders.</span></span> <span data-ttu-id="ea46d-104">有关如何在过程已划分为阶段的详细信息，请参阅"除以业务流程"[业务流程管理解决方案中的某些设计原则](../core/some-design-principles-in-the-business-process-management-solution.md)。</span><span class="sxs-lookup"><span data-stu-id="ea46d-104">For more information about how the process was divided into stages, see "Dividing Business Processes" in [Some Design Principles in the Business Process Management Solution](../core/some-design-principles-in-the-business-process-management-solution.md).</span></span>  
  
 <span data-ttu-id="ea46d-105">该解决方案的当前版本仅包含两个处理阶段。</span><span class="sxs-lookup"><span data-stu-id="ea46d-105">The current version of the solution contains only two processing stages.</span></span> <span data-ttu-id="ea46d-106">不过，它可以包含更多阶段。</span><span class="sxs-lookup"><span data-stu-id="ea46d-106">It could, however, contain many more.</span></span> <span data-ttu-id="ea46d-107">包含的阶段越多，则可以在其中确定流程的版本并继续在最新版本的处理阶段中工作的点就越多。</span><span class="sxs-lookup"><span data-stu-id="ea46d-107">More stages provide more points where you can version the process and continue working on the latest version of a processing stage.</span></span> <span data-ttu-id="ea46d-108">但是，每个阶段都引起了对通过 MessageBox 数据库的消息进行协调的额外开销，这会增加处理时间。</span><span class="sxs-lookup"><span data-stu-id="ea46d-108">However, each stage introduces the overhead of additional coordinating messages going through the MessageBox database, which increases processing time.</span></span> <span data-ttu-id="ea46d-109">您必须监视该解决方案的性能，以便确定阶段数是否过多。</span><span class="sxs-lookup"><span data-stu-id="ea46d-109">You must monitor the solution's performance to determine if the number of multiple stages is excessive.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ea46d-110">另请参阅</span><span class="sxs-lookup"><span data-stu-id="ea46d-110">See Also</span></span>  
 <span data-ttu-id="ea46d-111">[实现突出显示的业务流程管理解决方案](../core/implementation-highlights-of-the-business-process-management-solution.md) </span><span class="sxs-lookup"><span data-stu-id="ea46d-111">[Implementation Highlights of the Business Process Management Solution](../core/implementation-highlights-of-the-business-process-management-solution.md) </span></span>  
 [<span data-ttu-id="ea46d-112">过程管理器逻辑</span><span class="sxs-lookup"><span data-stu-id="ea46d-112">Process Manager Logic</span></span>](../core/process-manager-logic.md)