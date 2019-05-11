---
title: 部分备份集 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 7b9f15c0-4d31-4322-ac0a-8efdeed6f71e
caps.latest.revision: 2
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: baacc7a30a79084430ce570fc135b92e07586779
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65291332"
---
# <a name="partial-backup-sets"></a><span data-ttu-id="f0329-102">部分备份集</span><span class="sxs-lookup"><span data-stu-id="f0329-102">Partial Backup Sets</span></span>
<span data-ttu-id="f0329-103">在源系统上备份数据库，可能发生的问题导致部分备份集。</span><span class="sxs-lookup"><span data-stu-id="f0329-103">When backing up the databases on the source system, problems may occur that result in a partial backup set.</span></span> <span data-ttu-id="f0329-104">当发生这种情况时，Master.dbo.bts_LogShippingHistory 表将包含在 0 **SetComplete**列集中的所有记录。</span><span class="sxs-lookup"><span data-stu-id="f0329-104">When this occurs, the Master.dbo.bts_LogShippingHistory table will contain a 0 in the **SetComplete** column for all records in the set.</span></span>  
  
 <span data-ttu-id="f0329-105">无法还原这些设置。</span><span class="sxs-lookup"><span data-stu-id="f0329-105">These sets cannot be restored.</span></span> <span data-ttu-id="f0329-106">结果是日志备份集链已中断。</span><span class="sxs-lookup"><span data-stu-id="f0329-106">As a result the log backup set chain is broken.</span></span> <span data-ttu-id="f0329-107">必须忽略集，以及所有日志备份集后，到下一个完整备份集。</span><span class="sxs-lookup"><span data-stu-id="f0329-107">The set must be ignored, as well as all log backup sets after it, up to the next full backup set.</span></span> <span data-ttu-id="f0329-108">还原作业将自动寻找下一个有效的完整备份集。</span><span class="sxs-lookup"><span data-stu-id="f0329-108">The restore job will automatically look for the next valid full backup set.</span></span> <span data-ttu-id="f0329-109">如果没有找到一个，它将失败，并将还原的设置，以便修复目标环境。</span><span class="sxs-lookup"><span data-stu-id="f0329-109">If it does not find one, it fails and restores that set in order to repair the destination environment.</span></span>  
  
 <span data-ttu-id="f0329-110">在大多数情况下源系统将检测部分备份集已发生，并将自动生成如果它配置为执行此操作运行下一次完整备份集。</span><span class="sxs-lookup"><span data-stu-id="f0329-110">In most cases the source system will detect that a partial backup set has occurred and will automatically produce a full backup set the next time it runs if it is configured to do so.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="f0329-111">此问题的最常见原因是目标系统上的文件组没有足够的磁盘空间。</span><span class="sxs-lookup"><span data-stu-id="f0329-111">The most common cause of this problem is insufficient disk space for the file groups on the destination system.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f0329-112">请参阅</span><span class="sxs-lookup"><span data-stu-id="f0329-112">See Also</span></span>  
 [<span data-ttu-id="f0329-113">日志传送疑难解答</span><span class="sxs-lookup"><span data-stu-id="f0329-113">Troubleshooting Log Shipping</span></span>](../technical-guides/troubleshooting-log-shipping.md)