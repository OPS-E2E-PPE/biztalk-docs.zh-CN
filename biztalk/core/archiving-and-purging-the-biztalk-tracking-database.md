---
title: 存档和清除跟踪数据库 |Microsoft Docs
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
ms.openlocfilehash: 99d1d1e65ff943c2a677abc5e71fea4248955f73
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65358972"
---
# <a name="archive-and-purge-the-biztalkdtadb-database"></a><span data-ttu-id="4f45a-102">存档和清除 BizTalkDTADb 数据库</span><span class="sxs-lookup"><span data-stu-id="4f45a-102">Archive and Purge the BizTalkDTADb Database</span></span>

## <a name="overview"></a><span data-ttu-id="4f45a-103">概述</span><span class="sxs-lookup"><span data-stu-id="4f45a-103">Overview</span></span>
<span data-ttu-id="4f45a-104">当 BizTalk Server 处理越来越多的数据，你的系统上，BizTalk 跟踪 (BizTalkDTADb) 数据库将不断增长的大小。</span><span class="sxs-lookup"><span data-stu-id="4f45a-104">As BizTalk Server processes more and more data on your system, the BizTalk Tracking (BizTalkDTADb) database continues to grow in size.</span></span> <span data-ttu-id="4f45a-105">受控制的增长会降低系统性能，并且可能会生成错误中跟踪数据解码服务 (TDDS)。</span><span class="sxs-lookup"><span data-stu-id="4f45a-105">Unchecked growth decreases system performance and may generate errors in the Tracking Data Decode Service (TDDS).</span></span> <span data-ttu-id="4f45a-106">除了常规的跟踪数据，系统可能还会跟踪的消息累积在 MessageBox 数据库中，从而导致磁盘性能下降。</span><span class="sxs-lookup"><span data-stu-id="4f45a-106">In addition to general tracking data, tracked messages can also accumulate in the MessageBox database, causing poor disk performance.</span></span>  
  
<span data-ttu-id="4f45a-107">BizTalk Server 会自动将这两个进程使用 DTA 清除和存档作业。</span><span class="sxs-lookup"><span data-stu-id="4f45a-107">BizTalk Server automates both processes using the DTA Purge and Archive job.</span></span> <span data-ttu-id="4f45a-108">通过存档和清除 BizTalk 跟踪数据库中的数据，你可以保持系统正常运行，以及将存档以供将来使用的跟踪数据。</span><span class="sxs-lookup"><span data-stu-id="4f45a-108">By archiving and purging data from the BizTalk Tracking database, you can maintain a healthy system, as well as keep your tracking data archived for future use.</span></span> <span data-ttu-id="4f45a-109">BizTalk 跟踪数据库存档累积一段时间，占用磁盘空间，因为它是移动到辅助存储定期存档 BizTalk 跟踪数据库的一个好办法。</span><span class="sxs-lookup"><span data-stu-id="4f45a-109">Because BizTalk Tracking database archives accumulate over time and consume disk space, it is a good idea to move the BizTalk Tracking database archives to secondary storage on a regular basis.</span></span>  
  
 <span data-ttu-id="4f45a-110">当 BizTalk 跟踪数据库中清除数据时，DTA 清除和存档作业清除不同类型的跟踪信息，例如消息和服务实例信息、 业务流程事件信息和规则引擎跟踪数据。</span><span class="sxs-lookup"><span data-stu-id="4f45a-110">When you purge data from the BizTalk Tracking database, the DTA Purge and Archive job purges different types of tracking information such as message and service instance information, orchestration event information, and rules engine tracking data.</span></span>  
  
 <span data-ttu-id="4f45a-111">跟踪数据插入到 BizTalk 跟踪数据库的跟踪数据记录基于时间的期限。</span><span class="sxs-lookup"><span data-stu-id="4f45a-111">The age of a tracking data record is based on the time the tracking data was inserted into the BizTalk Tracking database.</span></span> <span data-ttu-id="4f45a-112">DTA 清除和存档作业使用时间戳来持续验证记录是否早于数据生存时段。</span><span class="sxs-lookup"><span data-stu-id="4f45a-112">The DTA Purge and Archive job uses the time stamp to continuously verify whether the record is older than the live window of data.</span></span> <span data-ttu-id="4f45a-113">每一个生存时段之后存档 BizTalk 跟踪数据库并创建一个新的存档文件。</span><span class="sxs-lookup"><span data-stu-id="4f45a-113">After every live window period, the BizTalk Tracking database is archived and a new archive file is created.</span></span> <span data-ttu-id="4f45a-114">指定作业计划的每个 SQL Server 代理作业时间间隔，在完成所有较旧的跟踪数据不是该生存时段都将被清除。</span><span class="sxs-lookup"><span data-stu-id="4f45a-114">At each SQL Server Agent job interval specified by the job schedule, all completed tracking data older than the live window period is purged.</span></span>  
  
 <span data-ttu-id="4f45a-115">BizTalk Server 使用软清除和硬清除的概念。</span><span class="sxs-lookup"><span data-stu-id="4f45a-115">BizTalk Server uses the concept of a soft purge and a hard purge.</span></span> <span data-ttu-id="4f45a-116">软清除用来清除已完成的实例，而硬清除仅用来清除未完成的实例。</span><span class="sxs-lookup"><span data-stu-id="4f45a-116">The soft purge is used to purge completed instances, while the hard purge is only used to purge incomplete instances.</span></span>  
  
## <a name="soft-purge"></a><span data-ttu-id="4f45a-117">软清除</span><span class="sxs-lookup"><span data-stu-id="4f45a-117">Soft purge</span></span>
  
 <span data-ttu-id="4f45a-118">在 DTA 存档和清除作业中，LiveHours 和 LiveDays 参数之和是想要维护 BizTalk Server 环境中的数据生存时段。</span><span class="sxs-lookup"><span data-stu-id="4f45a-118">In the DTA Archive and Purge job, the sum of the LiveHours and LiveDays parameters is the live window of data you want to maintain in your BizTalk Server environment.</span></span> <span data-ttu-id="4f45a-119">清除与数据的保留时间超过此生存时段的已完成实例相关联的所有数据。</span><span class="sxs-lookup"><span data-stu-id="4f45a-119">All data associated with a completed instance older than this live window of data is purged.</span></span> <span data-ttu-id="4f45a-120">默认情况下不启用 DTA 存档和清除作业。</span><span class="sxs-lookup"><span data-stu-id="4f45a-120">By default, the DTA Archive and Purge job is not enabled.</span></span> <span data-ttu-id="4f45a-121">您必须首先配置，然后启用该作业。</span><span class="sxs-lookup"><span data-stu-id="4f45a-121">You must first configure and then enable the job.</span></span>  
  
 <span data-ttu-id="4f45a-122">例如，可配置 DTA 清除和存档作业来运行每隔 20 分钟，并设置： LiveHours = 1 和 LiveDays = 0。</span><span class="sxs-lookup"><span data-stu-id="4f45a-122">For example, you can configure the DTA Purge and Archive job to run every 20 minutes, and set LiveHours=1 and LiveDays=0.</span></span> <span data-ttu-id="4f45a-123">第一次此 SQL Server 代理作业运行时 (T0)，它将通过创建存档跟踪数据库的备份和具有此时间戳在数据库中保存一个条目。</span><span class="sxs-lookup"><span data-stu-id="4f45a-123">The first time this SQL Server Agent job runs (T0), it takes a backup of the tracking database by creating an archive and an entry is saved in the database with this timestamp.</span></span> <span data-ttu-id="4f45a-124">存档成功才可清除跟踪数据。</span><span class="sxs-lookup"><span data-stu-id="4f45a-124">A successful archive is necessary in order to purge tracking data.</span></span> <span data-ttu-id="4f45a-125">如果存档成功，然后清除与在前一小时内完成的实例相关联的所有数据。</span><span class="sxs-lookup"><span data-stu-id="4f45a-125">If the archive was successful, then all the data associated with the instances that completed over an hour ago is purged.</span></span> <span data-ttu-id="4f45a-126">每次运行作业时，将清除 1 小时之前已完成的数据。</span><span class="sxs-lookup"><span data-stu-id="4f45a-126">Each time the job runs, completed data over one hour old is purged.</span></span> <span data-ttu-id="4f45a-127">(1 小时后） 第三个运行时，被创建新的存档，其中包含已插入到跟踪数据库中的最后一小时段的所有实例的数据。</span><span class="sxs-lookup"><span data-stu-id="4f45a-127">On the 3rd run (after one hour), a new archive is created that contains the data for all instances that were inserted into the tracking database in the last one hour segment.</span></span>  
  
 <span data-ttu-id="4f45a-128">下面是如何将配置存档和清除与示例匹配 DTA 清除和存档作业中步骤：</span><span class="sxs-lookup"><span data-stu-id="4f45a-128">Here is how you would configure the Archive and Purge step in the DTA Purge and Archive job to match the example:</span></span>  
  
```  
exec dtasp_BackupAndPurgeTrackingDatabase  
1, --@nLiveHours 1,   
0, --@nLiveDays   
1, --@nHardDeleteDays   
‘\\server\backup’, --@nvcFolder   
null, --@nvcValidatingServer   
0 --@fForceBackup Soft purge process  
```  
  
 <span data-ttu-id="4f45a-129">上次备份的时间戳存储在 BizTalk 跟踪数据库中，并确保在上一存档中是否只清除数据。</span><span class="sxs-lookup"><span data-stu-id="4f45a-129">The time stamp of the last backup is stored in the BizTalk Tracking database and ensures that data is only purged if it is in the previous archive.</span></span> <span data-ttu-id="4f45a-130">为了增加可靠性，存档按大约 10 分钟重叠。</span><span class="sxs-lookup"><span data-stu-id="4f45a-130">For additional reliability, archives are overlapped by approximately 10 minutes.</span></span> <span data-ttu-id="4f45a-131">下图中，基于上述示例中，显示了软清除过程。</span><span class="sxs-lookup"><span data-stu-id="4f45a-131">The following figure, based on the example above, shows the soft purge process.</span></span> <span data-ttu-id="4f45a-132">请注意，存档和清除任务确实不一定会出现在同一时间。</span><span class="sxs-lookup"><span data-stu-id="4f45a-132">Note that the archiving and purging tasks do not necessarily happen at the same time.</span></span>  
  
 <span data-ttu-id="4f45a-133">**软清除过程**</span><span class="sxs-lookup"><span data-stu-id="4f45a-133">**Soft purge process**</span></span>  
  
 <span data-ttu-id="4f45a-134">![软清除过程](../core/media/archivingandpurging.gif "archivingandpurging")</span><span class="sxs-lookup"><span data-stu-id="4f45a-134">![Soft purge process](../core/media/archivingandpurging.gif "archivingandpurging")</span></span>  
  
## <a name="hard-purge"></a><span data-ttu-id="4f45a-135">硬清除</span><span class="sxs-lookup"><span data-stu-id="4f45a-135">Hard purge</span></span>
  
 <span data-ttu-id="4f45a-136">由于软清除只清除与已完成的实例，如果您具有无限期运行的多个循环实例，然后跟踪数据库会增长，并且这些实例将永远无法清除关联的数据。</span><span class="sxs-lookup"><span data-stu-id="4f45a-136">Because the soft purge only purges data associated with completed instances, if you have many looping instances that run indefinitely, then your tracking database would grow and these instances would never be purged.</span></span> <span data-ttu-id="4f45a-137">硬清除日期可以早于指定的间隔清除除外，该值指示服务存在的信息的所有信息。</span><span class="sxs-lookup"><span data-stu-id="4f45a-137">The hard purge date allows all information older than the specified interval to be purged except for information indicating a service's existence.</span></span> <span data-ttu-id="4f45a-138">设置硬清除使用<strong>@nHardDeleteDays</strong>中存档和清除参数在 DTA 存档和清除作业步骤。</span><span class="sxs-lookup"><span data-stu-id="4f45a-138">You set the hard purge using the <strong>@nHardDeleteDays</strong> parameter in the Archive and Purge step in the DTA Archive and Purge job.</span></span> <span data-ttu-id="4f45a-139">硬清除设置应始终大于软清除设置。</span><span class="sxs-lookup"><span data-stu-id="4f45a-139">The hard purge setting should always be greater than your soft purge setting.</span></span> <span data-ttu-id="4f45a-140">换而言之， <strong>@nHardDeleteDays</strong>应大于的总和<strong>@nLiveHours</strong>并<strong>@nLiveDays</strong>。</span><span class="sxs-lookup"><span data-stu-id="4f45a-140">In other words, <strong>@nHardDeleteDays</strong> should be greater than the sum of <strong>@nLiveHours</strong> and <strong>@nLiveDays</strong>.</span></span>  
  
 <span data-ttu-id="4f45a-141">存档和清除包括下表中所述的功能：</span><span class="sxs-lookup"><span data-stu-id="4f45a-141">Archiving and purging includes the features described in the following table:</span></span>  
  
|<span data-ttu-id="4f45a-142">功能</span><span class="sxs-lookup"><span data-stu-id="4f45a-142">Feature</span></span>|<span data-ttu-id="4f45a-143">Description</span><span class="sxs-lookup"><span data-stu-id="4f45a-143">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="4f45a-144">硬清除</span><span class="sxs-lookup"><span data-stu-id="4f45a-144">Hard purge</span></span>|<span data-ttu-id="4f45a-145">可以配置一个时间间隔来清除早于指定日期的不完整实例的信息。</span><span class="sxs-lookup"><span data-stu-id="4f45a-145">Enables you to configure a time interval to purge information for incomplete instances older than a specified date.</span></span>|  
|<span data-ttu-id="4f45a-146">将跟踪的消息复制到跟踪数据库</span><span class="sxs-lookup"><span data-stu-id="4f45a-146">Copying tracked messages to tracking database</span></span>|<span data-ttu-id="4f45a-147">使用 copytrackedmessagetodta 选项，则可直接复制跟踪的消息从 MessageBox 服务器到 BizTalk 跟踪数据库。</span><span class="sxs-lookup"><span data-stu-id="4f45a-147">Using the CopyTrackedMessageToDTA option, you can directly copy tracked messages from the MessageBox servers to your BizTalk Tracking database.</span></span> <span data-ttu-id="4f45a-148">这是为了清除数据使用 DTA 清除和存档作业所必需的。</span><span class="sxs-lookup"><span data-stu-id="4f45a-148">This is required in order to purge data using the DTA Purge and Archive job.</span></span>|  
|<span data-ttu-id="4f45a-149">存档验证</span><span class="sxs-lookup"><span data-stu-id="4f45a-149">Archive validation</span></span>|<span data-ttu-id="4f45a-150">可以选择性地设置辅助数据库服务器来验证存档，因为它们创建。</span><span class="sxs-lookup"><span data-stu-id="4f45a-150">Enables you to optionally set up a secondary database server to validate the archives as they are created.</span></span>|  
|<span data-ttu-id="4f45a-151">跟踪对多个 BizTalk 跟踪数据库版本的支持</span><span class="sxs-lookup"><span data-stu-id="4f45a-151">Tracking support for multiple BizTalk Tracking database versions</span></span>|<span data-ttu-id="4f45a-152">使您可以使用跟踪支持与 BizTalk Server 数据库存档。</span><span class="sxs-lookup"><span data-stu-id="4f45a-152">Enables you to use tracking support with BizTalk Server database archives.</span></span>|  
|<span data-ttu-id="4f45a-153">减少跟踪数据</span><span class="sxs-lookup"><span data-stu-id="4f45a-153">Reduction of tracking data</span></span>|<span data-ttu-id="4f45a-154">极大地减少了跟踪数据存储而不会降低生成任何跟踪信息的量。</span><span class="sxs-lookup"><span data-stu-id="4f45a-154">Substantially reduces the amount of tracking data stored without reducing any tracking information generated.</span></span> <span data-ttu-id="4f45a-155">这会导致在跟踪数据库的速度较慢增长。</span><span class="sxs-lookup"><span data-stu-id="4f45a-155">This results in slower growth of the tracking database.</span></span>|  
|<span data-ttu-id="4f45a-156">更快的跟踪操作，在数据库架构进行了显著优化</span><span class="sxs-lookup"><span data-stu-id="4f45a-156">Faster tracking operations, significant optimization in database schemas</span></span>|<span data-ttu-id="4f45a-157">使你可以使用跟踪任务在大型数据库; 查找消息和服务实例此功能已显著优化。</span><span class="sxs-lookup"><span data-stu-id="4f45a-157">Enables you to use tracking tasks for finding messages and service instances on large databases; this feature has been significantly optimized.</span></span>|  
  
> [!NOTE]
>  <span data-ttu-id="4f45a-158">如果您遇到暂时解决通过清除 BizTalk 跟踪数据库的性能问题，并且你想要配置 BizTalk，不再收集跟踪信息，你可能想要考虑禁用全局跟踪。</span><span class="sxs-lookup"><span data-stu-id="4f45a-158">If you are having performance issues that are momentarily addressed by purging the BizTalk tracking database, and you want to configure BizTalk to no longer collect tracking information, you may want to consider turning off global tracking.</span></span> <span data-ttu-id="4f45a-159">请参阅[禁用全局跟踪](../core/how-to-turn-off-global-tracking.md)。</span><span class="sxs-lookup"><span data-stu-id="4f45a-159">See [Turn Off Global Tracking](../core/how-to-turn-off-global-tracking.md).</span></span>  
  
## <a name="next-steps"></a><span data-ttu-id="4f45a-160">后续步骤</span><span class="sxs-lookup"><span data-stu-id="4f45a-160">Next steps</span></span>
  
-   [<span data-ttu-id="4f45a-161">清单：存档和清除 BizTalk 跟踪数据库</span><span class="sxs-lookup"><span data-stu-id="4f45a-161">Checklist: Archiving and Purging the BizTalk Tracking Database</span></span>](../core/checklist-archiving-and-purging-the-biztalk-tracking-database.md)  
  
-   [<span data-ttu-id="4f45a-162">配置 BTS_BACKUP_USERS 角色以存档和清除 BizTalk 跟踪数据库中的数据</span><span class="sxs-lookup"><span data-stu-id="4f45a-162">Configure the BTS_BACKUP_USERS Role for Archiving and Purging Data from the BizTalk Tracking Database</span></span>](../core/configure-bts_backup_users-role-to-archive-and-purge-from-tracking-database.md)  
  
-   [<span data-ttu-id="4f45a-163">配置 DTA 清除和存档作业</span><span class="sxs-lookup"><span data-stu-id="4f45a-163">Configure the DTA Purge and Archive Job</span></span>](../core/how-to-configure-the-dta-purge-and-archive-job.md)  
  
-   [<span data-ttu-id="4f45a-164">从 BizTalk 跟踪数据库中清除数据</span><span class="sxs-lookup"><span data-stu-id="4f45a-164">Purge Data from the BizTalk Tracking Database</span></span>](../core/how-to-purge-data-from-the-biztalk-tracking-database.md)  
  
-   [<span data-ttu-id="4f45a-165">从 BizTalk 跟踪数据库中手动清除数据</span><span class="sxs-lookup"><span data-stu-id="4f45a-165">Manually Purge Data from the BizTalk Tracking Database</span></span>](../core/how-to-manually-purge-data-from-the-biztalk-tracking-database.md)  
  
-   [<span data-ttu-id="4f45a-166">启用自动存档验证</span><span class="sxs-lookup"><span data-stu-id="4f45a-166">Enable Automatic Archive Validation</span></span>](../core/how-to-enable-automatic-archive-validation.md)  
  
-   [<span data-ttu-id="4f45a-167">将跟踪的消息复制到 BizTalk 跟踪数据库</span><span class="sxs-lookup"><span data-stu-id="4f45a-167">Copy Tracked Messages into the BizTalk Tracking Database</span></span>](../core/how-to-copy-tracked-messages-into-the-biztalk-tracking-database.md)  
  
-   [<span data-ttu-id="4f45a-168">提高存档和清除进程的性能</span><span class="sxs-lookup"><span data-stu-id="4f45a-168">Improving the Performance of the Archiving and Purging Process</span></span>](../core/improving-the-performance-of-the-archiving-and-purging-process.md)  
  
-   [<span data-ttu-id="4f45a-169">禁用全局跟踪</span><span class="sxs-lookup"><span data-stu-id="4f45a-169">Turn Off Global Tracking</span></span>](../core/how-to-turn-off-global-tracking.md)