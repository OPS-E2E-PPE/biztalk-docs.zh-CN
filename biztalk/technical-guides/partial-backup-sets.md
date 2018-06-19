---
title: 部分备份集 |Microsoft 文档
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
ms.openlocfilehash: f9740cb0f45d6bb46c13a95e50e4717ef142b164
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22298157"
---
# <a name="partial-backup-sets"></a><span data-ttu-id="82910-102">部分备份集</span><span class="sxs-lookup"><span data-stu-id="82910-102">Partial Backup Sets</span></span>
<span data-ttu-id="82910-103">在源系统上备份数据库，可能发生的问题导致部分的备份集。</span><span class="sxs-lookup"><span data-stu-id="82910-103">When backing up the databases on the source system, problems may occur that result in a partial backup set.</span></span> <span data-ttu-id="82910-104">当发生这种情况时，Master.dbo.bts_LogShippingHistory 表将包含在 0 **SetComplete**集中的所有记录的列。</span><span class="sxs-lookup"><span data-stu-id="82910-104">When this occurs, the Master.dbo.bts_LogShippingHistory table will contain a 0 in the **SetComplete** column for all records in the set.</span></span>  
  
 <span data-ttu-id="82910-105">无法还原这些设置。</span><span class="sxs-lookup"><span data-stu-id="82910-105">These sets cannot be restored.</span></span> <span data-ttu-id="82910-106">因此，日志备份集链已中断。</span><span class="sxs-lookup"><span data-stu-id="82910-106">As a result the log backup set chain is broken.</span></span> <span data-ttu-id="82910-107">设置必须忽略，作为以及所有日志备份集后，到下一步的完整备份集。</span><span class="sxs-lookup"><span data-stu-id="82910-107">The set must be ignored, as well as all log backup sets after it, up to the next full backup set.</span></span> <span data-ttu-id="82910-108">还原作业将自动查找下一个有效的完整备份集。</span><span class="sxs-lookup"><span data-stu-id="82910-108">The restore job will automatically look for the next valid full backup set.</span></span> <span data-ttu-id="82910-109">如果它未找到一个，它无法正常工作，并将还原的设置，以便修复目标环境。</span><span class="sxs-lookup"><span data-stu-id="82910-109">If it does not find one, it fails and restores that set in order to repair the destination environment.</span></span>  
  
 <span data-ttu-id="82910-110">在大多数情况下的源系统将检测部分的备份集发生，并将自动生成的下次运行如果它被配置为这样做完整备份集。</span><span class="sxs-lookup"><span data-stu-id="82910-110">In most cases the source system will detect that a partial backup set has occurred and will automatically produce a full backup set the next time it runs if it is configured to do so.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="82910-111">此问题的最常见原因是目标系统上的文件组的磁盘空间不足。</span><span class="sxs-lookup"><span data-stu-id="82910-111">The most common cause of this problem is insufficient disk space for the file groups on the destination system.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="82910-112">另请参阅</span><span class="sxs-lookup"><span data-stu-id="82910-112">See Also</span></span>  
 [<span data-ttu-id="82910-113">故障排除日志传送</span><span class="sxs-lookup"><span data-stu-id="82910-113">Troubleshooting Log Shipping</span></span>](../technical-guides/troubleshooting-log-shipping.md)