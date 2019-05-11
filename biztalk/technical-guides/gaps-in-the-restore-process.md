---
title: 还原过程中的间隔 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 616c4f36-8ed6-4b99-b97a-5635627dfc17
caps.latest.revision: 2
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 06de30faec798fe57f30299051dc7f97db285bcf
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65279058"
---
# <a name="gaps-in-the-restore-process"></a><span data-ttu-id="8b189-102">还原过程中的间隔</span><span class="sxs-lookup"><span data-stu-id="8b189-102">Gaps in the Restore Process</span></span>
<span data-ttu-id="8b189-103">当查看 Master.dbo.bts_LogShippingHistory 表中的记录，可能会观察到已还原的组中的缺口。</span><span class="sxs-lookup"><span data-stu-id="8b189-103">When reviewing records in the Master.dbo.bts_LogShippingHistory table, you may observe gaps in restored sets.</span></span> <span data-ttu-id="8b189-104">这可能由多种原因引起。</span><span class="sxs-lookup"><span data-stu-id="8b189-104">This can occur for several reasons.</span></span> <span data-ttu-id="8b189-105">但是，即使发生缺口，则可以还原目标系统的稳定性。</span><span class="sxs-lookup"><span data-stu-id="8b189-105">However, the stability of the destination system can be restored even when gaps have occurred.</span></span> <span data-ttu-id="8b189-106">间隔必须后跟完整备份集以修复目标环境的还原。</span><span class="sxs-lookup"><span data-stu-id="8b189-106">A gap must be followed by a restore of a full backup set to repair the destination environment.</span></span> <span data-ttu-id="8b189-107">如果间隔后面不是完整备份集还原，目标环境不稳定，不能还原处于一致状态。</span><span class="sxs-lookup"><span data-stu-id="8b189-107">If a gap is not followed by a full backup set restore, the destination environment is not stable and cannot be restored in a consistent state.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="8b189-108">仅在重新创建数据库以及修复日志历史记录备份链中的问题时，才需要还原完整备份。</span><span class="sxs-lookup"><span data-stu-id="8b189-108">Full backups are only restored to initially create the database and to repair problems in the log history backup chain.</span></span> <span data-ttu-id="8b189-109">只要在还原时不会发生问题，完整备份集不会还原，因为它们不参与日志备份链。</span><span class="sxs-lookup"><span data-stu-id="8b189-109">As long as a problem does not occur with a restore, full backup sets are not restored, because they do not participate in the log backup chain.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8b189-110">请参阅</span><span class="sxs-lookup"><span data-stu-id="8b189-110">See Also</span></span>  
 [<span data-ttu-id="8b189-111">日志传送疑难解答</span><span class="sxs-lookup"><span data-stu-id="8b189-111">Troubleshooting Log Shipping</span></span>](../technical-guides/troubleshooting-log-shipping.md)