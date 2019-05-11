---
title: 日志传送 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- backing up, log shipping
- log shipping
ms.assetid: 25bc9724-1c99-43d0-8cd1-3ed8eaa60268
caps.latest.revision: 15
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 9fb0eb7d8c10d8e186f009cda82480490ef0df9e
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65380557"
---
# <a name="log-shipping"></a><span data-ttu-id="313f4-102">日志传送</span><span class="sxs-lookup"><span data-stu-id="313f4-102">Log Shipping</span></span>
<span data-ttu-id="313f4-103">日志传送具有备用服务器功能，有时称为热备份，它可以缩短出现系统故障时的停机时间。</span><span class="sxs-lookup"><span data-stu-id="313f4-103">Log shipping provides standby server capabilities, sometimes called a warm backup, which reduces downtime in the event of a system failure.</span></span>  
  
 <span data-ttu-id="313f4-104">由于分布式的数据库设计的[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]时生成，必须确保提供一致的备份，备份可以还原点。</span><span class="sxs-lookup"><span data-stu-id="313f4-104">Due to the distributed database design of [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)], when you produce backups you must be certain to provide a consistent point to which the backups can be restored.</span></span> <span data-ttu-id="313f4-105">事务可以跨多个数据库;如果一个数据库处于脱机状态，且必须还原，然后所有相关的数据库必须还原到单个点在时间，以确保系统处于一致状态。</span><span class="sxs-lookup"><span data-stu-id="313f4-105">Transactions can span multiple databases; if one database goes offline and must be restored, then all related databases must be restored to a single point in time to ensure that the system is in a consistent state.</span></span> <span data-ttu-id="313f4-106">并非所有数据库都参与分布式事务。</span><span class="sxs-lookup"><span data-stu-id="313f4-106">Not all databases participate in distributed transactions.</span></span> <span data-ttu-id="313f4-107">有关详细信息，请参阅[备份和还原 BizTalk Server 数据库](../core/backing-up-and-restoring-the-biztalk-server-databases.md)。</span><span class="sxs-lookup"><span data-stu-id="313f4-107">For more information, see [Backing Up and Restoring the BizTalk Server Databases](../core/backing-up-and-restoring-the-biztalk-server-databases.md).</span></span>  
  
 <span data-ttu-id="313f4-108">备份 BizTalk Server 作业使用 Microsoft SQL Server 日志标记提供生成数据库备份集的自动化的过程。</span><span class="sxs-lookup"><span data-stu-id="313f4-108">The Backup BizTalk Server job uses Microsoft SQL Server log marking to provide an automated process that produces database backup sets.</span></span> <span data-ttu-id="313f4-109">这些备份集包含在还原过程中使用的同步的点。</span><span class="sxs-lookup"><span data-stu-id="313f4-109">These backup sets include synchronized points that are used during the restoration process.</span></span> <span data-ttu-id="313f4-110">还原数据库备份 BizTalk Server 作业生成的一组的过程的一部分，为每个数据库的最后一个日志备份文件还原到特定的日志标记，使用第二个到最后一个标记。</span><span class="sxs-lookup"><span data-stu-id="313f4-110">As part of the process of restoring a set of databases produced by the Backup BizTalk Server job, the last log backup file for each database is restored to a specific log mark, using the second to last mark.</span></span> <span data-ttu-id="313f4-111">这使您可以将数据库还原到一致状态，并显著减少数据丢失量。</span><span class="sxs-lookup"><span data-stu-id="313f4-111">This enables you to restore your databases to a consistent state and significantly reduce the amount of data lost.</span></span> <span data-ttu-id="313f4-112">然后应使用的最后一个日志标记。</span><span class="sxs-lookup"><span data-stu-id="313f4-112">The log mark before the last one should be used.</span></span> <span data-ttu-id="313f4-113">SQL Server 包含日志传送功能，但应仅使用 BizTalk Server 日志传送功能时备份和还原 BizTalk Server 数据库。</span><span class="sxs-lookup"><span data-stu-id="313f4-113">Although SQL Server includes a log shipping feature, you should only use the BizTalk Server log shipping feature when backing up and restoring BizTalk Server databases.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="313f4-114">SQL Server 简单恢复模式不支持用于[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]数据库因为简单恢复模式不会备份事务日志，因此不维护活动记录的最新备份之后。</span><span class="sxs-lookup"><span data-stu-id="313f4-114">The SQL Server simple recovery model is not supported for use with [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] databases because the simple recovery model does not backup the transaction log and therefore does not maintain a record of activity since the most recent backup.</span></span>  <span data-ttu-id="313f4-115">SQL Server 配置为使用完整恢复模式来确保数据完整性[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]数据库备份集。</span><span class="sxs-lookup"><span data-stu-id="313f4-115">Configure SQL Server to use the full recovery model to ensure the integrity of data in [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] database backup sets.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="313f4-116">请参阅</span><span class="sxs-lookup"><span data-stu-id="313f4-116">See Also</span></span>  
 [<span data-ttu-id="313f4-117">有关备份和还原的高级信息</span><span class="sxs-lookup"><span data-stu-id="313f4-117">Advanced Information About Backup and Restore</span></span>](../core/advanced-information-about-backup-and-restore1.md)