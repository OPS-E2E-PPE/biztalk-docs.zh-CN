---
title: "备份和还原的 BizTalk Server 数据库 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- backing up, BizTalk Server
- backing up, transaction logs
- maintaining, restoring
- restoring, BizTalk Server
- maintaining, backing up
- transaction logs
ms.assetid: 7c08ce19-614c-4728-8dde-c40d4052339e
caps.latest.revision: "23"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 44bbb9316f1d036551acba5441424bcce65c2549
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="backing-up-and-restoring-the-biztalk-server-databases"></a><span data-ttu-id="1c0a0-102">备份和还原的 BizTalk Server 数据库</span><span class="sxs-lookup"><span data-stu-id="1c0a0-102">Backing Up and Restoring the BizTalk Server Databases</span></span>
<span data-ttu-id="1c0a0-103">本部分提供有关如何备份和还原 BizTalk Server 数据库的信息。</span><span class="sxs-lookup"><span data-stu-id="1c0a0-103">This section provides information about how to back up and restore the BizTalk Server databases.</span></span> <span data-ttu-id="1c0a0-104">请按照本部分中的过程进行操作，以确保在发生硬件故障时能够还原出一致的 BizTalk Server 环境。</span><span class="sxs-lookup"><span data-stu-id="1c0a0-104">You should follow the procedures in this section to ensure your ability to restore a consistent BizTalk Server environment in the event of a hardware failure.</span></span> <span data-ttu-id="1c0a0-105">由于 BizTalk Server 在各数据库中执行分布式事务，所以应先备份所有数据库，然后再还原所有数据库，这是很关键的。</span><span class="sxs-lookup"><span data-stu-id="1c0a0-105">BizTalk Server performs distributed transactions across databases, so it is critical that you back up and then restore all databases.</span></span>  
  
 <span data-ttu-id="1c0a0-106">BizTalk Server 要求执行自定义备份过程，该过程使用完整数据库备份、日志备份以及事务性日志标记。</span><span class="sxs-lookup"><span data-stu-id="1c0a0-106">BizTalk Server requires a customized backup process that uses full database backups and log backups in conjunction with transactional log marking.</span></span> <span data-ttu-id="1c0a0-107">有关此过程的信息，请参阅[标记的事务、 完整备份和日志备份](../core/marked-transactions-full-backups-and-log-backups.md)。</span><span class="sxs-lookup"><span data-stu-id="1c0a0-107">For information about this process, see [Marked Transactions, Full Backups, and Log Backups](../core/marked-transactions-full-backups-and-log-backups.md).</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="1c0a0-108">本节内容</span><span class="sxs-lookup"><span data-stu-id="1c0a0-108">In This Section</span></span>  
  
-   [<span data-ttu-id="1c0a0-109">清单： 备份和还原 BizTalk Server 数据库</span><span class="sxs-lookup"><span data-stu-id="1c0a0-109">Checklist: Back Up and Restore BizTalk Server Databases</span></span>](../core/checklist-back-up-and-restore-biztalk-server-databases.md)  
  
-   [<span data-ttu-id="1c0a0-110">备份和还原数据库的最佳实践</span><span class="sxs-lookup"><span data-stu-id="1c0a0-110">Best Practices for Backing Up and Restoring Databases</span></span>](../core/best-practices-for-backing-up-and-restoring-databases.md)  
  
-   [<span data-ttu-id="1c0a0-111">备份和还原 BizTalk Server 数据库</span><span class="sxs-lookup"><span data-stu-id="1c0a0-111">Backing Up and Restoring BizTalk Server Databases</span></span>](../core/backing-up-and-restoring-biztalk-server-databases.md)  
  
-   [<span data-ttu-id="1c0a0-112">备份和还原 BAM</span><span class="sxs-lookup"><span data-stu-id="1c0a0-112">Backing Up and Restoring BAM</span></span>](../core/backing-up-and-restoring-bam.md)  
  
-   [<span data-ttu-id="1c0a0-113">解决数据丢失</span><span class="sxs-lookup"><span data-stu-id="1c0a0-113">Resolving Data Loss</span></span>](../core/resolving-data-loss.md)  
  
-   [<span data-ttu-id="1c0a0-114">有关备份和还原的高级的信息</span><span class="sxs-lookup"><span data-stu-id="1c0a0-114">Advanced Information About Backup and Restore</span></span>](../core/advanced-information-about-backup-and-restore1.md)