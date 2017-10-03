---
title: "日志传送 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- backing up, log shipping
- log shipping
ms.assetid: 25bc9724-1c99-43d0-8cd1-3ed8eaa60268
caps.latest.revision: "15"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 5bd90e23fc99988bb134a77befe3195ca507037d
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="log-shipping"></a><span data-ttu-id="dab1a-102">日志传送</span><span class="sxs-lookup"><span data-stu-id="dab1a-102">Log Shipping</span></span>
<span data-ttu-id="dab1a-103">日志传送具有备用服务器功能，有时称为热备份，它可以缩短出现系统失败时的停机时间。</span><span class="sxs-lookup"><span data-stu-id="dab1a-103">Log shipping provides standby server capabilities, sometimes called a warm backup, which reduces downtime in the event of a system failure.</span></span>  
  
 <span data-ttu-id="dab1a-104">由于的分布式的数据库设计[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]，当你生成必须确保提供一个一致的备份到备份可以还原点。</span><span class="sxs-lookup"><span data-stu-id="dab1a-104">Due to the distributed database design of [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)], when you produce backups you must be certain to provide a consistent point to which the backups can be restored.</span></span> <span data-ttu-id="dab1a-105">事务可跨越多个数据库，如果一个数据库脱机并且必须还原，则其他相关数据库也必须及时还原到同一时间点，以确保系统处于一致的状态。</span><span class="sxs-lookup"><span data-stu-id="dab1a-105">Transactions can span multiple databases; if one database goes offline and must be restored, then all related databases must be restored to a single point in time to ensure that the system is in a consistent state.</span></span> <span data-ttu-id="dab1a-106">分布式事务并不涉及所有数据库。</span><span class="sxs-lookup"><span data-stu-id="dab1a-106">Not all databases participate in distributed transactions.</span></span> <span data-ttu-id="dab1a-107">有关详细信息，请参阅[备份和还原 BizTalk Server 数据库](../core/backing-up-and-restoring-the-biztalk-server-databases.md)。</span><span class="sxs-lookup"><span data-stu-id="dab1a-107">For more information, see [Backing Up and Restoring the BizTalk Server Databases](../core/backing-up-and-restoring-the-biztalk-server-databases.md).</span></span>  
  
 <span data-ttu-id="dab1a-108">备份 BizTalk Server 作业使用 Microsoft SQL Server 日志标记自动生成数据库备份集。</span><span class="sxs-lookup"><span data-stu-id="dab1a-108">The Backup BizTalk Server job uses Microsoft SQL Server log marking to provide an automated process that produces database backup sets.</span></span> <span data-ttu-id="dab1a-109">这些备份集包含还原过程中将使用的同步点。</span><span class="sxs-lookup"><span data-stu-id="dab1a-109">These backup sets include synchronized points that are used during the restoration process.</span></span> <span data-ttu-id="dab1a-110">在还原由备份 BizTalk Server 作业生成的数据库集的过程中，利用倒数第二个标记，将每个数据库的最近的日志备份文件还原到某个特定的日志标记。</span><span class="sxs-lookup"><span data-stu-id="dab1a-110">As part of the process of restoring a set of databases produced by the Backup BizTalk Server job, the last log backup file for each database is restored to a specific log mark, using the second to last mark.</span></span> <span data-ttu-id="dab1a-111">这使您可将数据库还原到一致的状态，并有效地减少数据丢失量。</span><span class="sxs-lookup"><span data-stu-id="dab1a-111">This enables you to restore your databases to a consistent state and significantly reduce the amount of data lost.</span></span> <span data-ttu-id="dab1a-112">建议使用倒数第二个日志标记。</span><span class="sxs-lookup"><span data-stu-id="dab1a-112">The log mark before the last one should be used.</span></span> <span data-ttu-id="dab1a-113">尽管 SQL Server 也具有日志传送功能，但是在备份和还原 BizTalk Server 数据库时，仅应使用 BizTalk Server 的日志传送功能。</span><span class="sxs-lookup"><span data-stu-id="dab1a-113">Although SQL Server includes a log shipping feature, you should only use the BizTalk Server log shipping feature when backing up and restoring BizTalk Server databases.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="dab1a-114">由于简单恢复模式不会备份事务集，从而不会维护自最近备份以来的活动记录，因此，不支持将 SQL Server 简单恢复模式与 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 数据库一起使用。</span><span class="sxs-lookup"><span data-stu-id="dab1a-114">The SQL Server simple recovery model is not supported for use with [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] databases because the simple recovery model does not backup the transaction log and therefore does not maintain a record of activity since the most recent backup.</span></span>  <span data-ttu-id="dab1a-115">SQL Server 配置为使用完整恢复模型来确保中数据的完整性[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]数据库备份集。</span><span class="sxs-lookup"><span data-stu-id="dab1a-115">Configure SQL Server to use the full recovery model to ensure the integrity of data in [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] database backup sets.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="dab1a-116">另请参阅</span><span class="sxs-lookup"><span data-stu-id="dab1a-116">See Also</span></span>  
 [<span data-ttu-id="dab1a-117">有关备份和还原的高级的信息</span><span class="sxs-lookup"><span data-stu-id="dab1a-117">Advanced Information About Backup and Restore</span></span>](../core/advanced-information-about-backup-and-restore1.md)