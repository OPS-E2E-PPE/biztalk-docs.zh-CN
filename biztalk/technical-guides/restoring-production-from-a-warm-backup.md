---
title: 从暖备份中还原生产 |Microsoft 文档
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 2bda14b8-b3cc-4a5e-a353-fca5885fd594
caps.latest.revision: 2
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 8e590b4eccb6ee946a915ff1f3a0265bbfe977e7
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22302085"
---
# <a name="restoring-production-from-a-warm-backup"></a><span data-ttu-id="28440-102">从暖备份中还原生产</span><span class="sxs-lookup"><span data-stu-id="28440-102">Restoring Production from a Warm Backup</span></span>
<span data-ttu-id="28440-103">如果源系统开始变得不可靠，则可以从目标到源中还原数据库。</span><span class="sxs-lookup"><span data-stu-id="28440-103">If the source system becomes unreliable, it is possible to restore the databases from the destination to the source.</span></span> <span data-ttu-id="28440-104">执行以下过程将从目标的数据库还原到源。</span><span class="sxs-lookup"><span data-stu-id="28440-104">Perform the following procedure to restore databases from the destination to the source.</span></span>  
  
### <a name="to-restore-the-databases-from-the-destination-to-the-source-follow-these-steps"></a><span data-ttu-id="28440-105">若要还原到源从目标数据库，请按照下列步骤</span><span class="sxs-lookup"><span data-stu-id="28440-105">To restore the databases from the destination to the source follow these steps</span></span>  
  
1.  <span data-ttu-id="28440-106">禁用源 （生产） 上的所有备份作业[!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)]实例。</span><span class="sxs-lookup"><span data-stu-id="28440-106">Disable all backup jobs on the source (production) [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)] instance(s).</span></span>  
  
2.  <span data-ttu-id="28440-107">等待所有还原作业来在目标灾难恢复 (DR) 上完成[!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)]实例。</span><span class="sxs-lookup"><span data-stu-id="28440-107">Wait for all restore jobs to complete on the destination disaster recovery (DR) [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)] instance(s).</span></span>  
  
3.  <span data-ttu-id="28440-108">禁用目标 (DR) 上的所有还原作业[!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)]实例。</span><span class="sxs-lookup"><span data-stu-id="28440-108">Disable all restore jobs on the destination (DR) [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)] instance(s).</span></span>  
  
4.  <span data-ttu-id="28440-109">还原与 STOPATMARK 目标 (DR) 上的所有数据库[!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)]实例。</span><span class="sxs-lookup"><span data-stu-id="28440-109">Restore all databases with STOPATMARK on the destination (DR) [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)] instance(s).</span></span>  
  
5.  <span data-ttu-id="28440-110">停止所有[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]所有 BizTalk 服务器上的服务。</span><span class="sxs-lookup"><span data-stu-id="28440-110">Stop all [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] services on all BizTalk servers.</span></span>  
  
6.  <span data-ttu-id="28440-111">删除所有[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]-相关数据库上的源 （生产）[!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)]实例。</span><span class="sxs-lookup"><span data-stu-id="28440-111">Drop all [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]-related databases on the source (production) [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)] instance(s).</span></span>  
  
7.  <span data-ttu-id="28440-112">备份 （完整） 的所有数据库上的目标 (DR)[!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)]实例。</span><span class="sxs-lookup"><span data-stu-id="28440-112">Back up (full) all databases on the destination (DR) [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)] instance(s).</span></span>  
  
8.  <span data-ttu-id="28440-113">还原 （完整） 所有[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]数据库备份在步骤 7 中的源 （生产） 到[!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)]实例。</span><span class="sxs-lookup"><span data-stu-id="28440-113">Restore (full) all [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] databases backed up in step 7 to the source (production) [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)] instance(s).</span></span>  
  
9. <span data-ttu-id="28440-114">重新启动所有 BizTalk 服务器包括主密钥服务器。</span><span class="sxs-lookup"><span data-stu-id="28440-114">Restart all BizTalk servers including the master secret server.</span></span>  
  
10. <span data-ttu-id="28440-115">删除所有[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]-相关目标 (DR) 上的数据库[!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)]实例。</span><span class="sxs-lookup"><span data-stu-id="28440-115">Drop all [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]-related databases on the destination (DR) [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)] instance(s).</span></span>  
  
11. <span data-ttu-id="28440-116">启用源上的备份作业[!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)]实例。</span><span class="sxs-lookup"><span data-stu-id="28440-116">Enable backup jobs on the source [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)] instance(s).</span></span>  
  
12. <span data-ttu-id="28440-117">启用目标 (DR) 上的还原作业[!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)]实例。</span><span class="sxs-lookup"><span data-stu-id="28440-117">Enable restore jobs on the destination (DR) [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)] instance(s).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="28440-118">另请参阅</span><span class="sxs-lookup"><span data-stu-id="28440-118">See Also</span></span>  
 [<span data-ttu-id="28440-119">有关备份和 Restore2 的高级的信息</span><span class="sxs-lookup"><span data-stu-id="28440-119">Advanced Information About Backup and Restore2</span></span>](../technical-guides/advanced-information-about-backup-and-restore2.md)