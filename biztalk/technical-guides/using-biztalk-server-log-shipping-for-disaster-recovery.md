---
title: 使用 BizTalk Server 日志传送灾难恢复 |Microsoft Docs
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
ms.openlocfilehash: 9dc2ab707bb4620fdb4b45db2750514758f21300
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65400360"
---
# <a name="using-biztalk-server-log-shipping-for-disaster-recovery"></a><span data-ttu-id="329b1-102">使用 BizTalk Server 日志传送灾难恢复</span><span class="sxs-lookup"><span data-stu-id="329b1-102">Using BizTalk Server Log Shipping for Disaster Recovery</span></span>
[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] <span data-ttu-id="329b1-103">实现数据库的备用容量通过数据库使用日志传送。</span><span class="sxs-lookup"><span data-stu-id="329b1-103">implements database standby capabilities through the use of database log shipping.</span></span> [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] <span data-ttu-id="329b1-104">备份和还原的数据库和事务日志文件，从而允许在备用服务器恢复数据库处理在的生产数据库服务器出现故障，可自动执行日志传送。</span><span class="sxs-lookup"><span data-stu-id="329b1-104">log shipping automates the backup and restore of database and transaction log files, allowing a standby server to resume database processing in the event that the production database server fails.</span></span>  
  
## <a name="how-log-shipping-works"></a><span data-ttu-id="329b1-105">如何日志传送的工作原理</span><span class="sxs-lookup"><span data-stu-id="329b1-105">How Log Shipping Works</span></span>  
 <span data-ttu-id="329b1-106">[!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)]使用的代理作业[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]日志传送同步在生产环境中使用的源服务器和目标服务器作为备用每隔 15 分钟默认情况下使用 （每个备份 BizTalk Server 作业运行的时间） 之间的数据。</span><span class="sxs-lookup"><span data-stu-id="329b1-106">The [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)] Agent jobs used by [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] for log shipping synchronize data between the source server used in production and the destination server used as a standby every 15 minutes by default (every time that the Backup BizTalk Server job runs).</span></span>  
  
## <a name="using-log-shipping-for-disaster-recovery"></a><span data-ttu-id="329b1-107">使用日志传送灾难恢复</span><span class="sxs-lookup"><span data-stu-id="329b1-107">Using Log Shipping for Disaster Recovery</span></span>  
 <span data-ttu-id="329b1-108">执行以下操作时使用[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]日志传送灾难恢复：</span><span class="sxs-lookup"><span data-stu-id="329b1-108">Do the following when using [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] log shipping for disaster recovery:</span></span>  
  
- <span data-ttu-id="329b1-109">按照本主题中的步骤[核对清单：提供高可用性灾难恢复](../technical-guides/checklist-increasing-availability-with-disaster-recovery.md)以提高可用性的生产型的[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]使用灾难恢复环境。</span><span class="sxs-lookup"><span data-stu-id="329b1-109">Follow the steps in the topic [Checklist: Increasing Availability with Disaster Recovery](../technical-guides/checklist-increasing-availability-with-disaster-recovery.md) to increase availability of a production [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] environment using disaster recovery.</span></span>  
  
- <span data-ttu-id="329b1-110">验证的灾难恢复服务器都具有容量来处理生产负载。</span><span class="sxs-lookup"><span data-stu-id="329b1-110">Verify that the disaster recovery servers have the capacity to handle production load.</span></span>  
  
   <span data-ttu-id="329b1-111">确保备用服务器具有相同或相似可用的资源 （CPU/内存/磁盘） 作为生产服务器。</span><span class="sxs-lookup"><span data-stu-id="329b1-111">Ensure that the standby servers have the same or similar resources available (CPU/memory/disk) as the production servers.</span></span>  
  
- <span data-ttu-id="329b1-112">请确保也记录在灾难恢复例程的详细信息。</span><span class="sxs-lookup"><span data-stu-id="329b1-112">Ensure that the specifics of your disaster recovery routine are well documented.</span></span>  
  
   <span data-ttu-id="329b1-113">记录你的灾难恢复准备和实现详细信息中的每个步骤。</span><span class="sxs-lookup"><span data-stu-id="329b1-113">Document every step of your disaster recovery preparation and implementation in detail.</span></span> <span data-ttu-id="329b1-114">灾难很少反击方便的时候假定方负责实现灾难恢复过程开始其第一天的工作，将会执行此操作的第一次。</span><span class="sxs-lookup"><span data-stu-id="329b1-114">Disaster seldom strikes when it is convenient so assume that the parties responsible for implementing the disaster recovery procedure are starting their first day of work and will be doing this for the first time.</span></span>  
  
- <span data-ttu-id="329b1-115">作为常规的测试，实际故障转移到灾难恢复站点的一部分，尤其是当新的 BizTalk 应用程序放在生产环境中。</span><span class="sxs-lookup"><span data-stu-id="329b1-115">As part of regular testing, practice failover to the disaster recovery site, especially as new BizTalk applications are put in production.</span></span>  
  
   <span data-ttu-id="329b1-116">执行故障转移测试作为常规测试和维护，以确保顺利地执行的一部分。</span><span class="sxs-lookup"><span data-stu-id="329b1-116">Perform failover testing as a part of regular testing and maintenance to ensure that it can be performed smoothly.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="329b1-117">请参阅</span><span class="sxs-lookup"><span data-stu-id="329b1-117">See Also</span></span>  
 [<span data-ttu-id="329b1-118">灾难恢复</span><span class="sxs-lookup"><span data-stu-id="329b1-118">Disaster Recovery</span></span>](../technical-guides/disaster-recovery.md)