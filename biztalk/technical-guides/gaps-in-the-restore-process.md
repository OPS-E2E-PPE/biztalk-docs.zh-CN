---
title: 在还原过程中的缺口 |Microsoft 文档
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
ms.openlocfilehash: 2b7d3ccadd950f5a955430b982c1a6f79a262864
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22298093"
---
# <a name="gaps-in-the-restore-process"></a><span data-ttu-id="47c5d-102">在还原过程中的缺口</span><span class="sxs-lookup"><span data-stu-id="47c5d-102">Gaps in the Restore Process</span></span>
<span data-ttu-id="47c5d-103">时查看 Master.dbo.bts_LogShippingHistory 表中的记录，你可能会观察还原集方面的差距。</span><span class="sxs-lookup"><span data-stu-id="47c5d-103">When reviewing records in the Master.dbo.bts_LogShippingHistory table, you may observe gaps in restored sets.</span></span> <span data-ttu-id="47c5d-104">这可能由多种原因引起。</span><span class="sxs-lookup"><span data-stu-id="47c5d-104">This can occur for several reasons.</span></span> <span data-ttu-id="47c5d-105">但是，即使发生缺口，则可以还原的目标系统的稳定性。</span><span class="sxs-lookup"><span data-stu-id="47c5d-105">However, the stability of the destination system can be restored even when gaps have occurred.</span></span> <span data-ttu-id="47c5d-106">间隔必须跟设置为修复目标环境的完整备份还原。</span><span class="sxs-lookup"><span data-stu-id="47c5d-106">A gap must be followed by a restore of a full backup set to repair the destination environment.</span></span> <span data-ttu-id="47c5d-107">如果间隔后面不是完整备份集还原，目标环境不稳定且不能还原处于一致状态。</span><span class="sxs-lookup"><span data-stu-id="47c5d-107">If a gap is not followed by a full backup set restore, the destination environment is not stable and cannot be restored in a consistent state.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="47c5d-108">仅在重新创建数据库以及修复日志历史记录备份链中的问题时，才需要还原完整备份。</span><span class="sxs-lookup"><span data-stu-id="47c5d-108">Full backups are only restored to initially create the database and to repair problems in the log history backup chain.</span></span> <span data-ttu-id="47c5d-109">只要还原时，问题不会发生，将不还原完整备份集，因为它们在日志备份链未参与。</span><span class="sxs-lookup"><span data-stu-id="47c5d-109">As long as a problem does not occur with a restore, full backup sets are not restored, because they do not participate in the log backup chain.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="47c5d-110">另请参阅</span><span class="sxs-lookup"><span data-stu-id="47c5d-110">See Also</span></span>  
 [<span data-ttu-id="47c5d-111">故障排除日志传送</span><span class="sxs-lookup"><span data-stu-id="47c5d-111">Troubleshooting Log Shipping</span></span>](../technical-guides/troubleshooting-log-shipping.md)