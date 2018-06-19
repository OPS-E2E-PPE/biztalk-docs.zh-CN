---
title: 使用 BizTalk Server 日志传送以实现灾难恢复 |Microsoft 文档
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 5d65015c-de53-4590-b644-5c2f66f763db
caps.latest.revision: 2
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 16f2cf9e1d8b717ff42536ef9c0dba79132b9663
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22302293"
---
# <a name="using-biztalk-server-log-shipping-for-disaster-recovery"></a><span data-ttu-id="75cce-102">使用 BizTalk Server 日志传送以实现灾难恢复</span><span class="sxs-lookup"><span data-stu-id="75cce-102">Using BizTalk Server Log Shipping for Disaster Recovery</span></span>
[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]<span data-ttu-id="75cce-103">实现数据库的备用容量通过数据库使用日志传送。</span><span class="sxs-lookup"><span data-stu-id="75cce-103"> implements database standby capabilities through the use of database log shipping.</span></span> [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]<span data-ttu-id="75cce-104">备份和还原的数据库和事务日志文件，允许备用服务器恢复数据库处理的事件中生产数据库服务器出现故障，可以自动执行日志传送。</span><span class="sxs-lookup"><span data-stu-id="75cce-104"> log shipping automates the backup and restore of database and transaction log files, allowing a standby server to resume database processing in the event that the production database server fails.</span></span>  
  
## <a name="how-log-shipping-works"></a><span data-ttu-id="75cce-105">如何日志传送工作原理</span><span class="sxs-lookup"><span data-stu-id="75cce-105">How Log Shipping Works</span></span>  
 <span data-ttu-id="75cce-106">[!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)]代理作业由[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]日志传送同步在生产中使用的源服务器和目标服务器作为备用每隔 15 分钟默认情况下使用 （每个备份 BizTalk Server 作业运行的时间） 之间的数据。</span><span class="sxs-lookup"><span data-stu-id="75cce-106">The [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)] Agent jobs used by [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] for log shipping synchronize data between the source server used in production and the destination server used as a standby every 15 minutes by default (every time that the Backup BizTalk Server job runs).</span></span>  
  
## <a name="using-log-shipping-for-disaster-recovery"></a><span data-ttu-id="75cce-107">使用日志传送以实现灾难恢复</span><span class="sxs-lookup"><span data-stu-id="75cce-107">Using Log Shipping for Disaster Recovery</span></span>  
 <span data-ttu-id="75cce-108">执行以下操作时使用[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]日志传送灾难恢复：</span><span class="sxs-lookup"><span data-stu-id="75cce-108">Do the following when using [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] log shipping for disaster recovery:</span></span>  
  
-   <span data-ttu-id="75cce-109">按照本主题中的步骤[清单： 增加可用性与灾难恢复](../technical-guides/checklist-increasing-availability-with-disaster-recovery.md)以提高可用性的生产型的[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]使用灾难恢复的环境。</span><span class="sxs-lookup"><span data-stu-id="75cce-109">Follow the steps in the topic [Checklist: Increasing Availability with Disaster Recovery](../technical-guides/checklist-increasing-availability-with-disaster-recovery.md) to increase availability of a production [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] environment using disaster recovery.</span></span>  
  
-   <span data-ttu-id="75cce-110">验证灾难恢复服务器具有处理生产负载的能力。</span><span class="sxs-lookup"><span data-stu-id="75cce-110">Verify that the disaster recovery servers have the capacity to handle production load.</span></span>  
  
     <span data-ttu-id="75cce-111">确保备用服务器具有相同或类似可用的资源 （CPU/内存/磁盘） 与生产服务器。</span><span class="sxs-lookup"><span data-stu-id="75cce-111">Ensure that the standby servers have the same or similar resources available (CPU/memory/disk) as the production servers.</span></span>  
  
-   <span data-ttu-id="75cce-112">确保你的灾难恢复日常活动期间细节很好地进行了说明。</span><span class="sxs-lookup"><span data-stu-id="75cce-112">Ensure that the specifics of your disaster recovery routine are well documented.</span></span>  
  
     <span data-ttu-id="75cce-113">记录你的灾难恢复准备和详细信息中的实现的每个步骤。</span><span class="sxs-lookup"><span data-stu-id="75cce-113">Document every step of your disaster recovery preparation and implementation in detail.</span></span> <span data-ttu-id="75cce-114">灾难很少反击方便时假定其第一天，方负责实现灾难恢复过程开始工作，以及将执行此操作在第一次。</span><span class="sxs-lookup"><span data-stu-id="75cce-114">Disaster seldom strikes when it is convenient so assume that the parties responsible for implementing the disaster recovery procedure are starting their first day of work and will be doing this for the first time.</span></span>  
  
-   <span data-ttu-id="75cce-115">作为正则的测试，实际故障转移到灾难恢复站点的一部分，尤其是当新的 BizTalk 应用程序都将置于生产。</span><span class="sxs-lookup"><span data-stu-id="75cce-115">As part of regular testing, practice failover to the disaster recovery site, especially as new BizTalk applications are put in production.</span></span>  
  
     <span data-ttu-id="75cce-116">执行故障转移测试作为常规的测试和维护，以确保顺利执行的一部分。</span><span class="sxs-lookup"><span data-stu-id="75cce-116">Perform failover testing as a part of regular testing and maintenance to ensure that it can be performed smoothly.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="75cce-117">另请参阅</span><span class="sxs-lookup"><span data-stu-id="75cce-117">See Also</span></span>  
 [<span data-ttu-id="75cce-118">灾难恢复</span><span class="sxs-lookup"><span data-stu-id="75cce-118">Disaster Recovery</span></span>](../technical-guides/disaster-recovery.md)