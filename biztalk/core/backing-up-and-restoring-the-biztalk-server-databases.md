---
title: 备份和还原 BizTalk Server 数据库 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- backing up, BizTalk Server
- backing up, transaction logs
- maintaining, restoring
- restoring, BizTalk Server
- maintaining, backing up
- transaction logs
ms.assetid: 7c08ce19-614c-4728-8dde-c40d4052339e
caps.latest.revision: 23
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: a6fbf2bfec008d48623aa5238d1208d55460f0cc
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65358672"
---
# <a name="backing-up-and-restoring-the-biztalk-server-databases"></a><span data-ttu-id="a0e1e-102">备份和还原 BizTalk Server 数据库</span><span class="sxs-lookup"><span data-stu-id="a0e1e-102">Backing Up and Restoring the BizTalk Server Databases</span></span>
<span data-ttu-id="a0e1e-103">本部分提供有关如何备份和还原 BizTalk Server 数据库的信息。</span><span class="sxs-lookup"><span data-stu-id="a0e1e-103">This section provides information about how to back up and restore the BizTalk Server databases.</span></span> <span data-ttu-id="a0e1e-104">应遵循此部分以确保能够还原出现硬件故障一致的 BizTalk Server 环境中的过程。</span><span class="sxs-lookup"><span data-stu-id="a0e1e-104">You should follow the procedures in this section to ensure your ability to restore a consistent BizTalk Server environment in the event of a hardware failure.</span></span> <span data-ttu-id="a0e1e-105">BizTalk Server 在数据库之间执行分布式的事务，因此很关键备份，然后还原所有数据库。</span><span class="sxs-lookup"><span data-stu-id="a0e1e-105">BizTalk Server performs distributed transactions across databases, so it is critical that you back up and then restore all databases.</span></span>  
  
 <span data-ttu-id="a0e1e-106">BizTalk Server 需要使用完整数据库备份和日志备份一起使用以及事务性日志标记的自定义备份进程。</span><span class="sxs-lookup"><span data-stu-id="a0e1e-106">BizTalk Server requires a customized backup process that uses full database backups and log backups in conjunction with transactional log marking.</span></span> <span data-ttu-id="a0e1e-107">有关此过程的信息，请参阅[标记的事务、 完整备份和日志备份](../core/marked-transactions-full-backups-and-log-backups.md)。</span><span class="sxs-lookup"><span data-stu-id="a0e1e-107">For information about this process, see [Marked Transactions, Full Backups, and Log Backups](../core/marked-transactions-full-backups-and-log-backups.md).</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="a0e1e-108">本节内容</span><span class="sxs-lookup"><span data-stu-id="a0e1e-108">In This Section</span></span>  
  
-   [<span data-ttu-id="a0e1e-109">清单：备份和还原 BizTalk Server 数据库</span><span class="sxs-lookup"><span data-stu-id="a0e1e-109">Checklist: Back Up and Restore BizTalk Server Databases</span></span>](../core/checklist-back-up-and-restore-biztalk-server-databases.md)  
  
-   [<span data-ttu-id="a0e1e-110">备份和还原数据库的最佳做法</span><span class="sxs-lookup"><span data-stu-id="a0e1e-110">Best Practices for Backing Up and Restoring Databases</span></span>](../core/best-practices-for-backing-up-and-restoring-databases.md)  
  
-   [<span data-ttu-id="a0e1e-111">备份和还原 BizTalk Server 数据库</span><span class="sxs-lookup"><span data-stu-id="a0e1e-111">Backing Up and Restoring BizTalk Server Databases</span></span>](../core/backing-up-and-restoring-biztalk-server-databases.md)  
  
-   [<span data-ttu-id="a0e1e-112">备份和还原 BAM</span><span class="sxs-lookup"><span data-stu-id="a0e1e-112">Backing Up and Restoring BAM</span></span>](../core/backing-up-and-restoring-bam.md)  
  
-   [<span data-ttu-id="a0e1e-113">解决数据丢失问题</span><span class="sxs-lookup"><span data-stu-id="a0e1e-113">Resolving Data Loss</span></span>](../core/resolving-data-loss.md)  
  
-   [<span data-ttu-id="a0e1e-114">有关备份和还原的高级信息</span><span class="sxs-lookup"><span data-stu-id="a0e1e-114">Advanced Information About Backup and Restore</span></span>](../core/advanced-information-about-backup-and-restore1.md)