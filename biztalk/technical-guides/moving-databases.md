---
title: 移动数据库 |Microsoft Docs
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
ms.openlocfilehash: 15562fc1fb642a4766190dabe912e81b38bb1ea8
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "36972414"
---
# <a name="moving-databases"></a><span data-ttu-id="674fe-102">移动数据库</span><span class="sxs-lookup"><span data-stu-id="674fe-102">Moving Databases</span></span>
<span data-ttu-id="674fe-103">移动的建议的方法[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]（除业务活动监视 (BAM) 数据库中） 的数据库是配置[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]部分中所述日志传送[灾难恢复](../technical-guides/disaster-recovery.md)。</span><span class="sxs-lookup"><span data-stu-id="674fe-103">The recommended method for moving [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] databases (except for the Business Activity Monitoring (BAM) databases) is to configure [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] log shipping as described in the section [Disaster Recovery](../technical-guides/disaster-recovery.md).</span></span> <span data-ttu-id="674fe-104">使用 BAM，所有的数据库除外[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]数据库可以通过使用备份**备份 BizTalk Server** [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)]代理作业。</span><span class="sxs-lookup"><span data-stu-id="674fe-104">With the exception of the databases used by BAM, all of the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] databases can be backed up by using the **Backup BizTalk Server**[!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)] Agent job.</span></span> <span data-ttu-id="674fe-105">有关此作业的详细信息，请参阅[如何安排备份 BizTalk Server 作业](http://go.microsoft.com/fwlink/?LinkId=154674)(<http://go.microsoft.com/fwlink/?LinkId=154674>) 中[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]帮助。</span><span class="sxs-lookup"><span data-stu-id="674fe-105">For more information about this job, see [How to Schedule the Backup BizTalk Server Job](http://go.microsoft.com/fwlink/?LinkId=154674) (<http://go.microsoft.com/fwlink/?LinkId=154674>) in [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Help.</span></span>  
  
 <span data-ttu-id="674fe-106">本部分介绍如何移动 BAM 相关数据库以及如何移动剩余[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]不使用第一个配置数据库[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]日志传送。</span><span class="sxs-lookup"><span data-stu-id="674fe-106">This section describes how to move the BAM-related databases and how to move the remaining [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] databases without first configuring [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] log shipping.</span></span> <span data-ttu-id="674fe-107">升级时，此方法可能会很有用[!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)]存放计算机[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]数据库或在其他方案中不与灾难恢复。</span><span class="sxs-lookup"><span data-stu-id="674fe-107">This approach may be useful when upgrading the [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)] computers that house the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] databases or in other scenarios that are not related to disaster recovery.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="674fe-108">本节内容</span><span class="sxs-lookup"><span data-stu-id="674fe-108">In This Section</span></span>  
  
-   [<span data-ttu-id="674fe-109">移动 BAM 数据库</span><span class="sxs-lookup"><span data-stu-id="674fe-109">Moving BAM Databases</span></span>](../technical-guides/moving-bam-databases.md)  
  
-   [<span data-ttu-id="674fe-110">移动非 BAM 数据库</span><span class="sxs-lookup"><span data-stu-id="674fe-110">Moving Non-BAM Databases</span></span>](../technical-guides/moving-non-bam-databases.md)  
  
## <a name="see-also"></a><span data-ttu-id="674fe-111">请参阅</span><span class="sxs-lookup"><span data-stu-id="674fe-111">See Also</span></span>  
 [<span data-ttu-id="674fe-112">管理 BizTalk Server2</span><span class="sxs-lookup"><span data-stu-id="674fe-112">Managing BizTalk Server2</span></span>](../technical-guides/managing-biztalk-server2.md)