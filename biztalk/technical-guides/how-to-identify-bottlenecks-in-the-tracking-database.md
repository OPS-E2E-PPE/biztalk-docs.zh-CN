---
title: 如何找出跟踪数据库的瓶颈 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 9b72e726-6225-47a0-8e1d-0f5a9cf745d3
caps.latest.revision: 4
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 2c82a0b106cbb8fee680582aad7d1aa5ce331f02
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65400418"
---
# <a name="how-to-identify-bottlenecks-in-the-tracking-database"></a><span data-ttu-id="cf37b-102">如何找出跟踪数据库的瓶颈</span><span class="sxs-lookup"><span data-stu-id="cf37b-102">How to Identify Bottlenecks in the Tracking Database</span></span>
<span data-ttu-id="cf37b-103">若要确定 BizTalk 跟踪 (BizTalkDTADb) 数据库的瓶颈，执行以下步骤：</span><span class="sxs-lookup"><span data-stu-id="cf37b-103">To identify bottlenecks in the BizTalk Tracking (BizTalkDTADb) database, perform the following steps:</span></span>  
  
1. <span data-ttu-id="cf37b-104">确保 SQL 代理服务正在运行。</span><span class="sxs-lookup"><span data-stu-id="cf37b-104">Ensure that the SQL-Agent Service is running.</span></span>  
  
2. <span data-ttu-id="cf37b-105">确保存档/清除作业正在运行并成功完成。</span><span class="sxs-lookup"><span data-stu-id="cf37b-105">Ensure that the Archive/Purge Job is running and completing successfully.</span></span>  
  
3. <span data-ttu-id="cf37b-106">确保 TrackedMessages_Copy_BizTalkMsgBoxDB 作业正在运行，成功完成。</span><span class="sxs-lookup"><span data-stu-id="cf37b-106">Ensure that the TrackedMessages_Copy_BizTalkMsgBoxDB Job is running and completing successfully.</span></span>  
  
4. <span data-ttu-id="cf37b-107">验证有足够的磁盘空间可用于 DTADb 存档和数据库增长。</span><span class="sxs-lookup"><span data-stu-id="cf37b-107">Verify that sufficient free disk space is available for the DTADb archives and database growth.</span></span>  
  
5. <span data-ttu-id="cf37b-108">使用专用的主机对其进行跟踪和度量值负载下的主机队列长度性能计数器。</span><span class="sxs-lookup"><span data-stu-id="cf37b-108">Use a dedicated host for tracking and measure the Host Queue Length performance counter when under load.</span></span>  
  
6. <span data-ttu-id="cf37b-109">随着时间的推移检查为增长趋势的后台处理表大小性能计数器。</span><span class="sxs-lookup"><span data-stu-id="cf37b-109">Check the Spool Table size performance counter for an increasing trend over time.</span></span>  
  
7. <span data-ttu-id="cf37b-110">检查长执行时间的存档/清除作业执行持续时间。</span><span class="sxs-lookup"><span data-stu-id="cf37b-110">Check the Archive/Purge job execution duration for long execution times.</span></span>  
  
8. <span data-ttu-id="cf37b-111">检查磁盘响应能力 （读/写性能计数器每秒磁盘） 上承载 BizTalk 跟踪数据库的磁盘。</span><span class="sxs-lookup"><span data-stu-id="cf37b-111">Check disk responsiveness (Disk Seconds per Read/Write performance counter) on the disk hosting the BizTalk Tracking database.</span></span>  
  
   <span data-ttu-id="cf37b-112">我们强烈建议优化 dtasp_BackupAndPurgeTrackingDatabase 或 dtasp_PurgeTrackingDatabase 调用 DTA 清除和存档作业的以下参数值：</span><span class="sxs-lookup"><span data-stu-id="cf37b-112">We strongly recommend tuning down the value of the following parameters of the dtasp_BackupAndPurgeTrackingDatabase or dtasp_PurgeTrackingDatabase invoked by the DTA Purge and Archive job:</span></span>  
  
- <span data-ttu-id="cf37b-113">@nLiveHours tinyint — 任何已完成实例早于 （生存小时数） + （生存天数） 也会删除所有关联的数据。</span><span class="sxs-lookup"><span data-stu-id="cf37b-113">@nLiveHours tinyint — Any completed instance older than the (live hours) + (live days) will be deleted along with all associated data.</span></span> <span data-ttu-id="cf37b-114">默认值为 0 小时。</span><span class="sxs-lookup"><span data-stu-id="cf37b-114">Default is 0 hours.</span></span>  
  
- <span data-ttu-id="cf37b-115">@nLiveDays tinyint — 任何已完成实例早于 （生存小时数） + （生存天数） 也会删除所有关联的数据。</span><span class="sxs-lookup"><span data-stu-id="cf37b-115">@nLiveDays tinyint — Any completed instance older than the (live hours) + (live days) will be deleted along with all associated data.</span></span> <span data-ttu-id="cf37b-116">默认间隔为 1 天。</span><span class="sxs-lookup"><span data-stu-id="cf37b-116">Default interval is 1 day.</span></span>  
  
- <span data-ttu-id="cf37b-117">@nHardDeleteDays tinyint — 所有数据 （即使数据不完整） 早于此将被删除。</span><span class="sxs-lookup"><span data-stu-id="cf37b-117">@nHardDeleteDays tinyint — All data (even if incomplete) older than this will be deleted.</span></span> <span data-ttu-id="cf37b-118">为 HardDeleteDays 指定的时间间隔应大于数据生存时段。</span><span class="sxs-lookup"><span data-stu-id="cf37b-118">The time interval specified for HardDeleteDays should be greater than the live window of data.</span></span> <span data-ttu-id="cf37b-119">数据生存时段是时间的你想要将 BizTalk 跟踪 (BizTalkDTADb) 数据库中保留跟踪数据间隔。</span><span class="sxs-lookup"><span data-stu-id="cf37b-119">The live window of data is the interval of time for which you want to maintain tracking data in the BizTalk Tracking (BizTalkDTADb) database.</span></span> <span data-ttu-id="cf37b-120">早于此时间间隔内有资格将在下一次存档，然后清除。</span><span class="sxs-lookup"><span data-stu-id="cf37b-120">Anything older than this interval is eligible to be archived at the next archive and then purged.</span></span> <span data-ttu-id="cf37b-121">默认值为 30 天。</span><span class="sxs-lookup"><span data-stu-id="cf37b-121">Default is 30 days.</span></span>  
  
  <span data-ttu-id="cf37b-122">应根据数据保留策略在生产环境中，设置这些参数，而在性能实验室测试中，建议你使用的值，如下所示：</span><span class="sxs-lookup"><span data-stu-id="cf37b-122">These parameters should be set in accordance with data retention policies in a production environment, whereas in a performance lab tests we recommend that you use values as follows:</span></span>  
  
  <span data-ttu-id="cf37b-123">声明@dtLastBackup设置的日期时间@dtLastBackup= getutcdate （）</span><span class="sxs-lookup"><span data-stu-id="cf37b-123">declare @dtLastBackup datetime set @dtLastBackup = GetUTCDate()</span></span>  
  <span data-ttu-id="cf37b-124">exec dtasp_PurgeTrackingDatabase 1, 0, 1, @dtLastBackup</span><span class="sxs-lookup"><span data-stu-id="cf37b-124">exec dtasp_PurgeTrackingDatabase 1, 0, 1, @dtLastBackup</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="cf37b-125">请参阅</span><span class="sxs-lookup"><span data-stu-id="cf37b-125">See Also</span></span>  
 [<span data-ttu-id="cf37b-126">数据库层的瓶颈</span><span class="sxs-lookup"><span data-stu-id="cf37b-126">Bottlenecks in the Database Tier</span></span>](../technical-guides/bottlenecks-in-the-database-tier.md)