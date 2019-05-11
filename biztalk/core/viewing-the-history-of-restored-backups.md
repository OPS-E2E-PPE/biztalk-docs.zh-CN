---
title: 查看历史记录的还原备份 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- restoring, history
- backing up, history
ms.assetid: 8852befa-b8e7-469d-b014-75c881907442
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 9f4685512b0dc841bd0cbbd7673ed1bf4d8b130a
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65320858"
---
# <a name="viewing-the-history-of-restored-backups"></a><span data-ttu-id="fad52-102">查看已还原备份的历史记录</span><span class="sxs-lookup"><span data-stu-id="fad52-102">Viewing the History of Restored Backups</span></span>
<span data-ttu-id="fad52-103">若要确定最近成功还原的备份集，请查看 Master.dbo.bts_LogShippingHistory 表的内容。</span><span class="sxs-lookup"><span data-stu-id="fad52-103">To determine the last successful backup set restored, review the contents of the Master.dbo.bts_LogShippingHistory table.</span></span> <span data-ttu-id="fad52-104">此表由获取备份历史记录作业来填充，由还原数据库作业来更新。</span><span class="sxs-lookup"><span data-stu-id="fad52-104">This table is populated by the Get Backup History job and updated by the Restore Databases job.</span></span> <span data-ttu-id="fad52-105">如果备份还原成功，则 Restored 列将设为 1，RestoredDateTime 将设为当前日期和时间。</span><span class="sxs-lookup"><span data-stu-id="fad52-105">When a backup is successfully restored, the Restored column is set to 1 and the RestoredDateTime is set to the current date and time.</span></span>  
  
 <span data-ttu-id="fad52-106">成功还原了所有要从特定备份集还原到服务器的数据库后，该备份集 ID 将被写入 Master.dbo.bts_LogShippingLastRestoreSet 表。</span><span class="sxs-lookup"><span data-stu-id="fad52-106">When all of the databases being restored to the server from a particular backup set have been successfully restored, that backup set ID is written to the Master.dbo.bts_LogShippingLastRestoreSet table.</span></span>  
  
## <a name="gaps-in-the-restore-process"></a><span data-ttu-id="fad52-107">还原过程中的间隔</span><span class="sxs-lookup"><span data-stu-id="fad52-107">Gaps in the restore process</span></span>  
 <span data-ttu-id="fad52-108">在 Master.dbo.bts_LogShippingHistory 表中查看记录时，可能会发现还原的备份集中存在间隔。</span><span class="sxs-lookup"><span data-stu-id="fad52-108">When reviewing records in the Master.dbo.bts_LogShippingHistory table, you may find gaps in the sets restored.</span></span> <span data-ttu-id="fad52-109">这可能由多种原因引起。</span><span class="sxs-lookup"><span data-stu-id="fad52-109">This can occur for several reasons.</span></span> <span data-ttu-id="fad52-110">但是，即使出现间隔，仍可恢复目标系统（即备份计算机）的稳定性。</span><span class="sxs-lookup"><span data-stu-id="fad52-110">However, you can still recover the stability of your destination system (which are your backup computers), even when gaps have occurred.</span></span> <span data-ttu-id="fad52-111">必须在出现间隔后进行完整备份集的还原以修复目标系统。</span><span class="sxs-lookup"><span data-stu-id="fad52-111">A gap must be followed by a restore of a full backup set to repair the destination system.</span></span> <span data-ttu-id="fad52-112">如果在出现间隔后不进行完整备份集的还原，则目标环境将是不稳定的。</span><span class="sxs-lookup"><span data-stu-id="fad52-112">If a gap is not followed by a full backup set restore, the destination environment is not stable.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="fad52-113">仅在重新创建数据库以及修复日志历史记录备份链中的问题时，才需要还原完整备份。</span><span class="sxs-lookup"><span data-stu-id="fad52-113">Full backups are only restored to initially create the database and to repair problems in the log history backup chain.</span></span> <span data-ttu-id="fad52-114">多数情况下，并不还原完整备份集，因为它们不是日志备份链的一部分。</span><span class="sxs-lookup"><span data-stu-id="fad52-114">In most cases full backup sets are not restored, as they are not part of the log backup chain.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="fad52-115">请参阅</span><span class="sxs-lookup"><span data-stu-id="fad52-115">See Also</span></span>  
 [<span data-ttu-id="fad52-116">有关备份和还原的高级信息</span><span class="sxs-lookup"><span data-stu-id="fad52-116">Advanced Information About Backup and Restore</span></span>](../core/advanced-information-about-backup-and-restore1.md)