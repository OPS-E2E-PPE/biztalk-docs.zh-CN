---
title: 移动数据库 |Microsoft 文档
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 6a0d09a1-90a5-4a5d-a783-b979724e101b
caps.latest.revision: 3
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: f5dd25f898890225300f8962e581a38912f36351
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22299029"
---
# <a name="moving-databases"></a><span data-ttu-id="82949-102">移动数据库</span><span class="sxs-lookup"><span data-stu-id="82949-102">Moving Databases</span></span>
<span data-ttu-id="82949-103">移动的建议的方法[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]（除外业务活动监视 (BAM) 数据库中） 的数据库是配置[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]部分中所述日志传送[灾难恢复](../technical-guides/disaster-recovery.md)。</span><span class="sxs-lookup"><span data-stu-id="82949-103">The recommended method for moving [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] databases (except for the Business Activity Monitoring (BAM) databases) is to configure [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] log shipping as described in the section [Disaster Recovery](../technical-guides/disaster-recovery.md).</span></span> <span data-ttu-id="82949-104">除了使用 BAM，所有的数据库[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]数据库可以通过使用备份**备份 BizTalk Server** [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)]代理作业。</span><span class="sxs-lookup"><span data-stu-id="82949-104">With the exception of the databases used by BAM, all of the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] databases can be backed up by using the **Backup BizTalk Server**[!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)] Agent job.</span></span> <span data-ttu-id="82949-105">有关此作业的详细信息，请参阅[如何安排备份 BizTalk Server 作业](http://go.microsoft.com/fwlink/?LinkId=154674)(http://go.microsoft.com/fwlink/?LinkId=154674) 中[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]帮助。</span><span class="sxs-lookup"><span data-stu-id="82949-105">For more information about this job, see [How to Schedule the Backup BizTalk Server Job](http://go.microsoft.com/fwlink/?LinkId=154674) (http://go.microsoft.com/fwlink/?LinkId=154674) in [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Help.</span></span>  
  
 <span data-ttu-id="82949-106">本部分介绍如何移动 BAM 相关数据库以及如何将移动剩余[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]不使用第一个配置数据库[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]日志传送。</span><span class="sxs-lookup"><span data-stu-id="82949-106">This section describes how to move the BAM-related databases and how to move the remaining [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] databases without first configuring [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] log shipping.</span></span> <span data-ttu-id="82949-107">升级时，此方法可能会有用[!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)]容纳的计算机[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]数据库或在其他方案中不与灾难恢复。</span><span class="sxs-lookup"><span data-stu-id="82949-107">This approach may be useful when upgrading the [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)] computers that house the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] databases or in other scenarios that are not related to disaster recovery.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="82949-108">本节内容</span><span class="sxs-lookup"><span data-stu-id="82949-108">In This Section</span></span>  
  
-   [<span data-ttu-id="82949-109">移动 BAM 数据库</span><span class="sxs-lookup"><span data-stu-id="82949-109">Moving BAM Databases</span></span>](../technical-guides/moving-bam-databases.md)  
  
-   [<span data-ttu-id="82949-110">移动非 BAM 数据库</span><span class="sxs-lookup"><span data-stu-id="82949-110">Moving Non-BAM Databases</span></span>](../technical-guides/moving-non-bam-databases.md)  
  
## <a name="see-also"></a><span data-ttu-id="82949-111">另请参阅</span><span class="sxs-lookup"><span data-stu-id="82949-111">See Also</span></span>  
 [<span data-ttu-id="82949-112">管理 BizTalk Server2</span><span class="sxs-lookup"><span data-stu-id="82949-112">Managing BizTalk Server2</span></span>](../technical-guides/managing-biztalk-server2.md)