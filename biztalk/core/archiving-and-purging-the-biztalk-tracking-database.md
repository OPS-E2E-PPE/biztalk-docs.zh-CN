---
title: 存档和清除跟踪数据库 |Microsoft 文档
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 7014cf31-86e8-4829-8055-056442329009
caps.latest.revision: 37
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 52e1f7b75f677bfd4818ddedcb74927633031a14
ms.sourcegitcommit: 32f380810b90b70e5df7be72a6a14988a747868e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/28/2018
ms.locfileid: "29710840"
---
# <a name="archive-and-purge-the-biztalkdtadb-database"></a><span data-ttu-id="6ac37-102">存档和清除 BizTalkDTADb 数据库</span><span class="sxs-lookup"><span data-stu-id="6ac37-102">Archive and Purge the BizTalkDTADb Database</span></span>

## <a name="overview"></a><span data-ttu-id="6ac37-103">概述</span><span class="sxs-lookup"><span data-stu-id="6ac37-103">Overview</span></span>
<span data-ttu-id="6ac37-104">随着 BizTalk Server 在系统中处理的数据的增加，BizTalk 跟踪 (BizTalkDTADb) 数据库的大小也会持续增长。</span><span class="sxs-lookup"><span data-stu-id="6ac37-104">As BizTalk Server processes more and more data on your system, the BizTalk Tracking (BizTalkDTADb) database continues to grow in size.</span></span> <span data-ttu-id="6ac37-105">不受控制的增长将会降低系统性能，并可能导致跟踪数据解码服务 (TDDS) 出错。</span><span class="sxs-lookup"><span data-stu-id="6ac37-105">Unchecked growth decreases system performance and may generate errors in the Tracking Data Decode Service (TDDS).</span></span> <span data-ttu-id="6ac37-106">除了一般的跟踪数据之外，跟踪的消息也会在 MessageBox 数据库中累积，导致磁盘性能下降。</span><span class="sxs-lookup"><span data-stu-id="6ac37-106">In addition to general tracking data, tracked messages can also accumulate in the MessageBox database, causing poor disk performance.</span></span>  
  
<span data-ttu-id="6ac37-107">BizTalk Server 会自动使用 DTA 清除和存档作业这两个进程。</span><span class="sxs-lookup"><span data-stu-id="6ac37-107">BizTalk Server automates both processes using the DTA Purge and Archive job.</span></span> <span data-ttu-id="6ac37-108">通过存档和清除 BizTalk 跟踪数据库中的数据，您可以保持一个运行状况良好的系统，并将跟踪数据进行存档以供将来使用。</span><span class="sxs-lookup"><span data-stu-id="6ac37-108">By archiving and purging data from the BizTalk Tracking database, you can maintain a healthy system, as well as keep your tracking data archived for future use.</span></span> <span data-ttu-id="6ac37-109">由于 BizTalk 跟踪数据库存档会随着时间的推移不断累积而占用磁盘空间，因此最好定期将 BizTalk 跟踪数据库存档移至辅助存储空间。</span><span class="sxs-lookup"><span data-stu-id="6ac37-109">Because BizTalk Tracking database archives accumulate over time and consume disk space, it is a good idea to move the BizTalk Tracking database archives to secondary storage on a regular basis.</span></span>  
  
 <span data-ttu-id="6ac37-110">在清除 BizTalk 跟踪数据库中的数据时，DTA 清除和存档作业将清除不同类型的跟踪信息，例如消息和服务实例信息、业务流程事件信息，以及规则引擎跟踪数据。</span><span class="sxs-lookup"><span data-stu-id="6ac37-110">When you purge data from the BizTalk Tracking database, the DTA Purge and Archive job purges different types of tracking information such as message and service instance information, orchestration event information, and rules engine tracking data.</span></span>  
  
 <span data-ttu-id="6ac37-111">跟踪数据记录的保留时间取决于将跟踪数据插入 BizTalk 跟踪数据库的时间。</span><span class="sxs-lookup"><span data-stu-id="6ac37-111">The age of a tracking data record is based on the time the tracking data was inserted into the BizTalk Tracking database.</span></span> <span data-ttu-id="6ac37-112">DTA 清除和存档作业使用时间戳来持续验证该记录是否早于数据生存时段。</span><span class="sxs-lookup"><span data-stu-id="6ac37-112">The DTA Purge and Archive job uses the time stamp to continuously verify whether the record is older than the live window of data.</span></span> <span data-ttu-id="6ac37-113">在每一个生存时段之后，将对 BizTalk 跟踪数据库进行存档，并创建一个新的存档文件。</span><span class="sxs-lookup"><span data-stu-id="6ac37-113">After every live window period, the BizTalk Tracking database is archived and a new archive file is created.</span></span> <span data-ttu-id="6ac37-114">在作业计划指定的每个 SQL Server 代理作业时间间隔之后，将清除在该生存时段之前完成的所有跟踪数据。</span><span class="sxs-lookup"><span data-stu-id="6ac37-114">At each SQL Server Agent job interval specified by the job schedule, all completed tracking data older than the live window period is purged.</span></span>  
  
 <span data-ttu-id="6ac37-115">BizTalk Server 使用了“软清除”和“硬清除”概念。</span><span class="sxs-lookup"><span data-stu-id="6ac37-115">BizTalk Server uses the concept of a soft purge and a hard purge.</span></span> <span data-ttu-id="6ac37-116">软清除用来清除已完成的实例，而硬清除仅用来清除未完成的实例。</span><span class="sxs-lookup"><span data-stu-id="6ac37-116">The soft purge is used to purge completed instances, while the hard purge is only used to purge incomplete instances.</span></span>  
  
## <a name="soft-purge"></a><span data-ttu-id="6ac37-117">软清除</span><span class="sxs-lookup"><span data-stu-id="6ac37-117">Soft purge</span></span>
  
 <span data-ttu-id="6ac37-118">在 DTA 存档和清除作业中，LiveHours 和 LiveDays 参数之和就是要在 BizTalk Server 环境中维护的数据生存时段。</span><span class="sxs-lookup"><span data-stu-id="6ac37-118">In the DTA Archive and Purge job, the sum of the LiveHours and LiveDays parameters is the live window of data you want to maintain in your BizTalk Server environment.</span></span> <span data-ttu-id="6ac37-119">将清除与在此数据生存时段之前完成的实例相关联的所有数据。</span><span class="sxs-lookup"><span data-stu-id="6ac37-119">All data associated with a completed instance older than this live window of data is purged.</span></span> <span data-ttu-id="6ac37-120">默认情况下，不启用 DTA 存档和清除作业。</span><span class="sxs-lookup"><span data-stu-id="6ac37-120">By default, the DTA Archive and Purge job is not enabled.</span></span> <span data-ttu-id="6ac37-121">您必须先进行配置，然后才能启用该作业。</span><span class="sxs-lookup"><span data-stu-id="6ac37-121">You must first configure and then enable the job.</span></span>  
  
 <span data-ttu-id="6ac37-122">例如，你可以配置运行每隔 20 分钟，DTA 清除和存档作业，并将设置 LiveHours = 1 且 LiveDays = 0。</span><span class="sxs-lookup"><span data-stu-id="6ac37-122">For example, you can configure the DTA Purge and Archive job to run every 20 minutes, and set LiveHours=1 and LiveDays=0.</span></span> <span data-ttu-id="6ac37-123">第一次此 SQL Server 代理作业运行 (T0)，通过创建存档花跟踪数据库的备份，并且一个条目保存在数据库中为此时间戳。</span><span class="sxs-lookup"><span data-stu-id="6ac37-123">The first time this SQL Server Agent job runs (T0), it takes a backup of the tracking database by creating an archive and an entry is saved in the database with this timestamp.</span></span> <span data-ttu-id="6ac37-124">为了清除跟踪数据，必须保证存档成功。</span><span class="sxs-lookup"><span data-stu-id="6ac37-124">A successful archive is necessary in order to purge tracking data.</span></span> <span data-ttu-id="6ac37-125">如果存档成功，则与 1 小时前完成的实例相关联的所有数据都将被清除。</span><span class="sxs-lookup"><span data-stu-id="6ac37-125">If the archive was successful, then all the data associated with the instances that completed over an hour ago is purged.</span></span> <span data-ttu-id="6ac37-126">每次运行该作业时，都将清除 1 小时之前完成的数据。</span><span class="sxs-lookup"><span data-stu-id="6ac37-126">Each time the job runs, completed data over one hour old is purged.</span></span> <span data-ttu-id="6ac37-127">在第 3 次运行时（1 小时后），将创建一个新的存档，它包含在前 1 小时内插入跟踪数据库的所有实例的数据。</span><span class="sxs-lookup"><span data-stu-id="6ac37-127">On the 3rd run (after one hour), a new archive is created that contains the data for all instances that were inserted into the tracking database in the last one hour segment.</span></span>  
  
 <span data-ttu-id="6ac37-128">下面是如何将配置存档和清除中 DTA 清除和存档作业，以匹配示例步骤：</span><span class="sxs-lookup"><span data-stu-id="6ac37-128">Here is how you would configure the Archive and Purge step in the DTA Purge and Archive job to match the example:</span></span>  
  
```  
exec dtasp_BackupAndPurgeTrackingDatabase  
1, --@nLiveHours 1,   
0, --@nLiveDays   
1, --@nHardDeleteDays   
‘\\server\backup’, --@nvcFolder   
null, --@nvcValidatingServer   
0 --@fForceBackup Soft purge process  
```  
  
 <span data-ttu-id="6ac37-129">最后一次备份的时间戳存储在 BizTalk 跟踪数据库中，以确保只清除上一存档中已有的数据。</span><span class="sxs-lookup"><span data-stu-id="6ac37-129">The time stamp of the last backup is stored in the BizTalk Tracking database and ensures that data is only purged if it is in the previous archive.</span></span> <span data-ttu-id="6ac37-130">为了增加可靠性，存档按大约 10 分钟的间隔依次重叠。</span><span class="sxs-lookup"><span data-stu-id="6ac37-130">For additional reliability, archives are overlapped by approximately 10 minutes.</span></span> <span data-ttu-id="6ac37-131">下图显示了基于上述示例的软清除过程。</span><span class="sxs-lookup"><span data-stu-id="6ac37-131">The following figure, based on the example above, shows the soft purge process.</span></span> <span data-ttu-id="6ac37-132">请注意，存档和清除任务无需同时进行。</span><span class="sxs-lookup"><span data-stu-id="6ac37-132">Note that the archiving and purging tasks do not necessarily happen at the same time.</span></span>  
  
 <span data-ttu-id="6ac37-133">**软清除过程**</span><span class="sxs-lookup"><span data-stu-id="6ac37-133">**Soft purge process**</span></span>  
  
 <span data-ttu-id="6ac37-134">![软清除进程](../core/media/archivingandpurging.gif "archivingandpurging")</span><span class="sxs-lookup"><span data-stu-id="6ac37-134">![Soft purge process](../core/media/archivingandpurging.gif "archivingandpurging")</span></span>  
  
## <a name="hard-purge"></a><span data-ttu-id="6ac37-135">硬清除</span><span class="sxs-lookup"><span data-stu-id="6ac37-135">Hard purge</span></span>
  
 <span data-ttu-id="6ac37-136">由于软清除只清除与已完成的实例相关联的数据，因此，如果存在许多无限期运行的循环实例，则跟踪数据库将会增长，并且这些实例将永远无法清除。</span><span class="sxs-lookup"><span data-stu-id="6ac37-136">Because the soft purge only purges data associated with completed instances, if you have many looping instances that run indefinitely, then your tracking database would grow and these instances would never be purged.</span></span> <span data-ttu-id="6ac37-137">使用硬清除日期可以清除指定时间间隔之前的所有信息，只有指示服务存在的信息除外。</span><span class="sxs-lookup"><span data-stu-id="6ac37-137">The hard purge date allows all information older than the specified interval to be purged except for information indicating a service's existence.</span></span> <span data-ttu-id="6ac37-138">设置硬清除使用 **@nHardDeleteDays** 中 DTA 存档和清除作业步骤中的参数存档和清除。</span><span class="sxs-lookup"><span data-stu-id="6ac37-138">You set the hard purge using the **@nHardDeleteDays** parameter in the Archive and Purge step in the DTA Archive and Purge job.</span></span> <span data-ttu-id="6ac37-139">硬清除设置应始终大于软清除设置。</span><span class="sxs-lookup"><span data-stu-id="6ac37-139">The hard purge setting should always be greater than your soft purge setting.</span></span> <span data-ttu-id="6ac37-140">换而言之， **@nHardDeleteDays** 应大于的总和 **@nLiveHours** 和 **@nLiveDays**。</span><span class="sxs-lookup"><span data-stu-id="6ac37-140">In other words, **@nHardDeleteDays** should be greater than the sum of **@nLiveHours** and **@nLiveDays**.</span></span>  
  
 <span data-ttu-id="6ac37-141">存档和清除所包括的功能如下表所述：</span><span class="sxs-lookup"><span data-stu-id="6ac37-141">Archiving and purging includes the features described in the following table:</span></span>  
  
|<span data-ttu-id="6ac37-142">功能</span><span class="sxs-lookup"><span data-stu-id="6ac37-142">Feature</span></span>|<span data-ttu-id="6ac37-143">Description</span><span class="sxs-lookup"><span data-stu-id="6ac37-143">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="6ac37-144">硬清除</span><span class="sxs-lookup"><span data-stu-id="6ac37-144">Hard purge</span></span>|<span data-ttu-id="6ac37-145">使用该功能，可以配置一个时间间隔来清除指定日期之前的示例信息。</span><span class="sxs-lookup"><span data-stu-id="6ac37-145">Enables you to configure a time interval to purge information for incomplete instances older than a specified date.</span></span>|  
|<span data-ttu-id="6ac37-146">将跟踪的消息复制到跟踪数据库</span><span class="sxs-lookup"><span data-stu-id="6ac37-146">Copying tracked messages to tracking database</span></span>|<span data-ttu-id="6ac37-147">使用“CopyTrackedMessageToDTA”选项，可以直接将跟踪的消息从 MessageBox 服务器复制到 BizTalk 跟踪数据库中。</span><span class="sxs-lookup"><span data-stu-id="6ac37-147">Using the CopyTrackedMessageToDTA option, you can directly copy tracked messages from the MessageBox servers to your BizTalk Tracking database.</span></span> <span data-ttu-id="6ac37-148">使用 DTA 清除和存档作业清除数据时，要求进行此操作。</span><span class="sxs-lookup"><span data-stu-id="6ac37-148">This is required in order to purge data using the DTA Purge and Archive job.</span></span>|  
|<span data-ttu-id="6ac37-149">存档验证</span><span class="sxs-lookup"><span data-stu-id="6ac37-149">Archive validation</span></span>|<span data-ttu-id="6ac37-150">使用该功能，可以选择设置一个辅助数据库服务器，以便在创建存档时对其进行验证。</span><span class="sxs-lookup"><span data-stu-id="6ac37-150">Enables you to optionally set up a secondary database server to validate the archives as they are created.</span></span>|  
|<span data-ttu-id="6ac37-151">多个 BizTalk 跟踪数据库版本的跟踪支持</span><span class="sxs-lookup"><span data-stu-id="6ac37-151">Tracking support for multiple BizTalk Tracking database versions</span></span>|<span data-ttu-id="6ac37-152">你可以使用跟踪与 BizTalk Server 支持的实现数据库存档。</span><span class="sxs-lookup"><span data-stu-id="6ac37-152">Enables you to use tracking support with BizTalk Server database archives.</span></span>|  
|<span data-ttu-id="6ac37-153">减少跟踪数据</span><span class="sxs-lookup"><span data-stu-id="6ac37-153">Reduction of tracking data</span></span>|<span data-ttu-id="6ac37-154">在不减少生成的任何跟踪信息的情况下，显著减少存储的跟踪数据的数量。</span><span class="sxs-lookup"><span data-stu-id="6ac37-154">Substantially reduces the amount of tracking data stored without reducing any tracking information generated.</span></span> <span data-ttu-id="6ac37-155">这样可以降低跟踪数据库的增长速度。</span><span class="sxs-lookup"><span data-stu-id="6ac37-155">This results in slower growth of the tracking database.</span></span>|  
|<span data-ttu-id="6ac37-156">更快的跟踪操作，对数据库架构进行了显著优化</span><span class="sxs-lookup"><span data-stu-id="6ac37-156">Faster tracking operations, significant optimization in database schemas</span></span>|<span data-ttu-id="6ac37-157">使您可以使用跟踪任务在大型数据库中查找消息和服务实例；已对此功能进行了显著优化。</span><span class="sxs-lookup"><span data-stu-id="6ac37-157">Enables you to use tracking tasks for finding messages and service instances on large databases; this feature has been significantly optimized.</span></span>|  
  
> [!NOTE]
>  <span data-ttu-id="6ac37-158">如果存在通过清除 BizTalk 跟踪数据库暂时得以解决的性能问题，并且希望对 BizTalk 进行控制以便不再收集跟踪信息，则可能要考虑禁用全局跟踪功能。</span><span class="sxs-lookup"><span data-stu-id="6ac37-158">If you are having performance issues that are momentarily addressed by purging the BizTalk tracking database, and you want to configure BizTalk to no longer collect tracking information, you may want to consider turning off global tracking.</span></span> <span data-ttu-id="6ac37-159">请参阅[关闭全局跟踪](../core/how-to-turn-off-global-tracking.md)。</span><span class="sxs-lookup"><span data-stu-id="6ac37-159">See [Turn Off Global Tracking](../core/how-to-turn-off-global-tracking.md).</span></span>  
  
## <a name="next-steps"></a><span data-ttu-id="6ac37-160">后续步骤</span><span class="sxs-lookup"><span data-stu-id="6ac37-160">Next steps</span></span>
  
-   [<span data-ttu-id="6ac37-161">清单：存档和清除 BizTalk 跟踪数据库</span><span class="sxs-lookup"><span data-stu-id="6ac37-161">Checklist: Archiving and Purging the BizTalk Tracking Database</span></span>](../core/checklist-archiving-and-purging-the-biztalk-tracking-database.md)  
  
-   [<span data-ttu-id="6ac37-162">配置 BTS_BACKUP_USERS 角色以存档和清除 BizTalk 跟踪数据库中的数据</span><span class="sxs-lookup"><span data-stu-id="6ac37-162">Configure the BTS_BACKUP_USERS Role for Archiving and Purging Data from the BizTalk Tracking Database</span></span>](../core/configure-bts_backup_users-role-to-archive-and-purge-from-tracking-database.md)  
  
-   [<span data-ttu-id="6ac37-163">配置 DTA 清除和存档作业</span><span class="sxs-lookup"><span data-stu-id="6ac37-163">Configure the DTA Purge and Archive Job</span></span>](../core/how-to-configure-the-dta-purge-and-archive-job.md)  
  
-   [<span data-ttu-id="6ac37-164">从 BizTalk 跟踪数据库中清除数据</span><span class="sxs-lookup"><span data-stu-id="6ac37-164">Purge Data from the BizTalk Tracking Database</span></span>](../core/how-to-purge-data-from-the-biztalk-tracking-database.md)  
  
-   [<span data-ttu-id="6ac37-165">从 BizTalk 跟踪数据库中手动清除数据</span><span class="sxs-lookup"><span data-stu-id="6ac37-165">Manually Purge Data from the BizTalk Tracking Database</span></span>](../core/how-to-manually-purge-data-from-the-biztalk-tracking-database.md)  
  
-   [<span data-ttu-id="6ac37-166">启用自动存档验证</span><span class="sxs-lookup"><span data-stu-id="6ac37-166">Enable Automatic Archive Validation</span></span>](../core/how-to-enable-automatic-archive-validation.md)  
  
-   [<span data-ttu-id="6ac37-167">将跟踪的消息复制到 BizTalk 跟踪数据库</span><span class="sxs-lookup"><span data-stu-id="6ac37-167">Copy Tracked Messages into the BizTalk Tracking Database</span></span>](../core/how-to-copy-tracked-messages-into-the-biztalk-tracking-database.md)  
  
-   [<span data-ttu-id="6ac37-168">提高存档和清除进程的性能</span><span class="sxs-lookup"><span data-stu-id="6ac37-168">Improving the Performance of the Archiving and Purging Process</span></span>](../core/improving-the-performance-of-the-archiving-and-purging-process.md)  
  
-   [<span data-ttu-id="6ac37-169">禁用全局跟踪</span><span class="sxs-lookup"><span data-stu-id="6ac37-169">Turn Off Global Tracking</span></span>](../core/how-to-turn-off-global-tracking.md)