---
title: 处理阶段数 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- processing, stages
- process management solution tutorial, processing stages
ms.assetid: 74bd9f8c-99b4-4931-a096-6c54221ab2e5
caps.latest.revision: 9
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 3db73745d137486011c2b56031f64b41f59f8639
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65323531"
---
# <a name="number-of-processing-stages"></a><span data-ttu-id="07ea1-102">处理阶段的数目</span><span class="sxs-lookup"><span data-stu-id="07ea1-102">Number of Processing Stages</span></span>
<span data-ttu-id="07ea1-103">该解决方案，以便可以无需中断长时间运行的订单 （通过替换阶段） 修改该过程可分为若干阶段，将订单流程。</span><span class="sxs-lookup"><span data-stu-id="07ea1-103">The solution separates the order process into stages, so that it is possible to modify the process (by replacing stages) without disrupting long-running orders.</span></span> <span data-ttu-id="07ea1-104">有关如何在过程已分为若干阶段的详细信息，请参阅"划分业务流程"中[业务流程管理解决方案中的某些设计原则](../core/some-design-principles-in-the-business-process-management-solution.md)。</span><span class="sxs-lookup"><span data-stu-id="07ea1-104">For more information about how the process was divided into stages, see "Dividing Business Processes" in [Some Design Principles in the Business Process Management Solution](../core/some-design-principles-in-the-business-process-management-solution.md).</span></span>  
  
 <span data-ttu-id="07ea1-105">该解决方案的当前版本包含只有两个处理阶段。</span><span class="sxs-lookup"><span data-stu-id="07ea1-105">The current version of the solution contains only two processing stages.</span></span> <span data-ttu-id="07ea1-106">但是，它可以包含更多。</span><span class="sxs-lookup"><span data-stu-id="07ea1-106">It could, however, contain many more.</span></span> <span data-ttu-id="07ea1-107">多个阶段提供更多点可以版本进程并处理阶段的最新版本上继续工作。</span><span class="sxs-lookup"><span data-stu-id="07ea1-107">More stages provide more points where you can version the process and continue working on the latest version of a processing stage.</span></span> <span data-ttu-id="07ea1-108">但是，每个阶段都引起了额外的消息进行协调通过 MessageBox 数据库，这会增加处理时间的开销。</span><span class="sxs-lookup"><span data-stu-id="07ea1-108">However, each stage introduces the overhead of additional coordinating messages going through the MessageBox database, which increases processing time.</span></span> <span data-ttu-id="07ea1-109">必须监视解决方案的性能，以确定多个阶段数是否过多。</span><span class="sxs-lookup"><span data-stu-id="07ea1-109">You must monitor the solution's performance to determine if the number of multiple stages is excessive.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="07ea1-110">请参阅</span><span class="sxs-lookup"><span data-stu-id="07ea1-110">See Also</span></span>  
 <span data-ttu-id="07ea1-111">[业务流程管理解决方案的实施要点](../core/implementation-highlights-of-the-business-process-management-solution.md) </span><span class="sxs-lookup"><span data-stu-id="07ea1-111">[Implementation Highlights of the Business Process Management Solution](../core/implementation-highlights-of-the-business-process-management-solution.md) </span></span>  
 [<span data-ttu-id="07ea1-112">进程管理器逻辑</span><span class="sxs-lookup"><span data-stu-id="07ea1-112">Process Manager Logic</span></span>](../core/process-manager-logic.md)