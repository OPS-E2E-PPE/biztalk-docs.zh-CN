---
title: "如何确定跟踪数据库中的瓶颈 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 9b72e726-6225-47a0-8e1d-0f5a9cf745d3
caps.latest.revision: "4"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 16cd05b6c399d250d8a411f41f56406f19afc9e0
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="how-to-identify-bottlenecks-in-the-tracking-database"></a><span data-ttu-id="8c32e-102">如何确定跟踪数据库中的瓶颈</span><span class="sxs-lookup"><span data-stu-id="8c32e-102">How to Identify Bottlenecks in the Tracking Database</span></span>
<span data-ttu-id="8c32e-103">若要确定 BizTalk 跟踪 (BizTalkDTADb) 数据库中的瓶颈，执行以下步骤：</span><span class="sxs-lookup"><span data-stu-id="8c32e-103">To identify bottlenecks in the BizTalk Tracking (BizTalkDTADb) database, perform the following steps:</span></span>  
  
1.  <span data-ttu-id="8c32e-104">确保 SQL 代理服务正在运行。</span><span class="sxs-lookup"><span data-stu-id="8c32e-104">Ensure that the SQL-Agent Service is running.</span></span>  
  
2.  <span data-ttu-id="8c32e-105">确保存档/清除作业正在运行并成功完成。</span><span class="sxs-lookup"><span data-stu-id="8c32e-105">Ensure that the Archive/Purge Job is running and completing successfully.</span></span>  
  
3.  <span data-ttu-id="8c32e-106">确保 TrackedMessages_Copy_BizTalkMsgBoxDB 作业是运行且已成功完成。</span><span class="sxs-lookup"><span data-stu-id="8c32e-106">Ensure that the TrackedMessages_Copy_BizTalkMsgBoxDB Job is running and completing successfully.</span></span>  
  
4.  <span data-ttu-id="8c32e-107">验证有足够的磁盘空间可用于 DTADb 存档和数据库增长。</span><span class="sxs-lookup"><span data-stu-id="8c32e-107">Verify that sufficient free disk space is available for the DTADb archives and database growth.</span></span>  
  
5.  <span data-ttu-id="8c32e-108">使用专用的主机，对其进行跟踪和度量值负载下的主机 Queue Length 性能计数器。</span><span class="sxs-lookup"><span data-stu-id="8c32e-108">Use a dedicated host for tracking and measure the Host Queue Length performance counter when under load.</span></span>  
  
6.  <span data-ttu-id="8c32e-109">随着时间的推移检查上升趋势的假脱机表大小性能计数器。</span><span class="sxs-lookup"><span data-stu-id="8c32e-109">Check the Spool Table size performance counter for an increasing trend over time.</span></span>  
  
7.  <span data-ttu-id="8c32e-110">检查长执行时间的存档/清除作业执行持续时间。</span><span class="sxs-lookup"><span data-stu-id="8c32e-110">Check the Archive/Purge job execution duration for long execution times.</span></span>  
  
8.  <span data-ttu-id="8c32e-111">检查磁盘响应能力 （读/写性能计数器每次磁盘） 上承载 BizTalk 跟踪数据库的磁盘。</span><span class="sxs-lookup"><span data-stu-id="8c32e-111">Check disk responsiveness (Disk Seconds per Read/Write performance counter) on the disk hosting the BizTalk Tracking database.</span></span>  
  
 <span data-ttu-id="8c32e-112">我们强烈建议优化下 dtasp_BackupAndPurgeTrackingDatabase 或 dtasp_PurgeTrackingDatabase 调用由 DTA 清除和存档作业的以下参数的值：</span><span class="sxs-lookup"><span data-stu-id="8c32e-112">We strongly recommend tuning down the value of the following parameters of the dtasp_BackupAndPurgeTrackingDatabase or dtasp_PurgeTrackingDatabase invoked by the DTA Purge and Archive job:</span></span>  
  
-   <span data-ttu-id="8c32e-113">@nLiveHourstinyint-任何完成实例早于 （实时小时数） + （实时天） 将被删除以及所有关联的数据。</span><span class="sxs-lookup"><span data-stu-id="8c32e-113">@nLiveHours tinyint — Any completed instance older than the (live hours) + (live days) will be deleted along with all associated data.</span></span> <span data-ttu-id="8c32e-114">默认值为 0 小时。</span><span class="sxs-lookup"><span data-stu-id="8c32e-114">Default is 0 hours.</span></span>  
  
-   <span data-ttu-id="8c32e-115">@nLiveDaystinyint-任何完成实例早于 （实时小时数） + （实时天） 将被删除以及所有关联的数据。</span><span class="sxs-lookup"><span data-stu-id="8c32e-115">@nLiveDays tinyint — Any completed instance older than the (live hours) + (live days) will be deleted along with all associated data.</span></span> <span data-ttu-id="8c32e-116">默认间隔为 1 天。</span><span class="sxs-lookup"><span data-stu-id="8c32e-116">Default interval is 1 day.</span></span>  
  
-   <span data-ttu-id="8c32e-117">@nHardDeleteDaystinyint-所有数据 （即使不完整） 较旧，这将被删除。</span><span class="sxs-lookup"><span data-stu-id="8c32e-117">@nHardDeleteDays tinyint — All data (even if incomplete) older than this will be deleted.</span></span> <span data-ttu-id="8c32e-118">为 HardDeleteDays 指定的时间间隔应大于数据生存时段。</span><span class="sxs-lookup"><span data-stu-id="8c32e-118">The time interval specified for HardDeleteDays should be greater than the live window of data.</span></span> <span data-ttu-id="8c32e-119">数据生存时段是维护 BizTalk 跟踪 (BizTalkDTADb) 数据库中的跟踪数据所需的时间间隔。</span><span class="sxs-lookup"><span data-stu-id="8c32e-119">The live window of data is the interval of time for which you want to maintain tracking data in the BizTalk Tracking (BizTalkDTADb) database.</span></span> <span data-ttu-id="8c32e-120">早于此间隔的所有内容都应在下一次存档时进行存档，然后清除。</span><span class="sxs-lookup"><span data-stu-id="8c32e-120">Anything older than this interval is eligible to be archived at the next archive and then purged.</span></span> <span data-ttu-id="8c32e-121">默认值为 30 天。</span><span class="sxs-lookup"><span data-stu-id="8c32e-121">Default is 30 days.</span></span>  
  
 <span data-ttu-id="8c32e-122">应根据数据保留策略，在生产环境中，设置这些参数，而在性能实验室测试的建议你使用的值，如下所示：</span><span class="sxs-lookup"><span data-stu-id="8c32e-122">These parameters should be set in accordance with data retention policies in a production environment, whereas in a performance lab tests we recommend that you use values as follows:</span></span>  
  
 <span data-ttu-id="8c32e-123">声明@dtLastBackup设置的日期时间@dtLastBackup= GetUTCDate()</span><span class="sxs-lookup"><span data-stu-id="8c32e-123">declare @dtLastBackup datetime set @dtLastBackup = GetUTCDate()</span></span>  
 <span data-ttu-id="8c32e-124">exec dtasp_PurgeTrackingDatabase 1，0，1，@dtLastBackup</span><span class="sxs-lookup"><span data-stu-id="8c32e-124">exec dtasp_PurgeTrackingDatabase 1, 0, 1, @dtLastBackup</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8c32e-125">另请参阅</span><span class="sxs-lookup"><span data-stu-id="8c32e-125">See Also</span></span>  
 [<span data-ttu-id="8c32e-126">数据库层中的瓶颈</span><span class="sxs-lookup"><span data-stu-id="8c32e-126">Bottlenecks in the Database Tier</span></span>](../technical-guides/bottlenecks-in-the-database-tier.md)