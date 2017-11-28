---
title: "存档和清除跟踪数据库 BizTalk |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- Tracking database, purging
- BizTalk Server, maintaining
- archiving [Tracking database]
- purging
- Tracking database, maintaining
- Tracking database, archiving
- maintaining, Tracking database
- maintaining, BizTalk Server
ms.assetid: 7014cf31-86e8-4829-8055-056442329009
caps.latest.revision: "37"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: e8fc75f5218ec7a189d28c7120cf23a3047c1752
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="archiving-and-purging-the-biztalk-tracking-database"></a><span data-ttu-id="c97db-102">存档和清除 BizTalk 跟踪数据库</span><span class="sxs-lookup"><span data-stu-id="c97db-102">Archiving and Purging the BizTalk Tracking Database</span></span>
<span data-ttu-id="c97db-103">随着 BizTalk Server 在系统中处理的数据的增加，BizTalk 跟踪 (BizTalkDTADb) 数据库的大小也会持续增长。</span><span class="sxs-lookup"><span data-stu-id="c97db-103">As BizTalk Server processes more and more data on your system, the BizTalk Tracking (BizTalkDTADb) database continues to grow in size.</span></span> <span data-ttu-id="c97db-104">不受控制的增长将会降低系统性能，并可能导致跟踪数据解码服务 (TDDS) 出错。</span><span class="sxs-lookup"><span data-stu-id="c97db-104">Unchecked growth decreases system performance and may generate errors in the Tracking Data Decode Service (TDDS).</span></span> <span data-ttu-id="c97db-105">除了一般的跟踪数据之外，跟踪的消息也会在 MessageBox 数据库中累积，导致磁盘性能下降。</span><span class="sxs-lookup"><span data-stu-id="c97db-105">In addition to general tracking data, tracked messages can also accumulate in the MessageBox database, causing poor disk performance.</span></span>  
  
 <span data-ttu-id="c97db-106">尽管早期版本的 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 附带了用于存档跟踪的消息和消除 BizTalk 跟踪数据库的示例脚本，不过 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 可使用 DTA 消除和存档作业来自动执行这两个过程。</span><span class="sxs-lookup"><span data-stu-id="c97db-106">While previous versions of [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] included sample scripts for archiving tracked messages and purging the BizTalk Tracking database, [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] automates both processes using the DTA Purge and Archive job.</span></span> <span data-ttu-id="c97db-107">通过存档和清除 BizTalk 跟踪数据库中的数据，您可以保持一个运行状况良好的系统，并将跟踪数据进行存档以供将来使用。</span><span class="sxs-lookup"><span data-stu-id="c97db-107">By archiving and purging data from the BizTalk Tracking database, you can maintain a healthy system, as well as keep your tracking data archived for future use.</span></span> <span data-ttu-id="c97db-108">由于 BizTalk 跟踪数据库存档会随着时间的推移不断累积而占用磁盘空间，因此最好定期将 BizTalk 跟踪数据库存档移至辅助存储空间。</span><span class="sxs-lookup"><span data-stu-id="c97db-108">Because BizTalk Tracking database archives accumulate over time and consume disk space, it is a good idea to move the BizTalk Tracking database archives to secondary storage on a regular basis.</span></span>  
  
 <span data-ttu-id="c97db-109">在清除 BizTalk 跟踪数据库中的数据时，DTA 清除和存档作业将清除不同类型的跟踪信息，例如消息和服务实例信息、业务流程事件信息，以及规则引擎跟踪数据。</span><span class="sxs-lookup"><span data-stu-id="c97db-109">When you purge data from the BizTalk Tracking database, the DTA Purge and Archive job purges different types of tracking information such as message and service instance information, orchestration event information, and rules engine tracking data.</span></span>  
  
 <span data-ttu-id="c97db-110">跟踪数据记录的保留时间取决于将跟踪数据插入 BizTalk 跟踪数据库的时间。</span><span class="sxs-lookup"><span data-stu-id="c97db-110">The age of a tracking data record is based on the time the tracking data was inserted into the BizTalk Tracking database.</span></span> <span data-ttu-id="c97db-111">DTA 清除和存档作业使用时间戳来持续验证该记录是否早于数据生存时段。</span><span class="sxs-lookup"><span data-stu-id="c97db-111">The DTA Purge and Archive job uses the time stamp to continuously verify whether the record is older than the live window of data.</span></span> <span data-ttu-id="c97db-112">在每一个生存时段之后，将对 BizTalk 跟踪数据库进行存档，并创建一个新的存档文件。</span><span class="sxs-lookup"><span data-stu-id="c97db-112">After every live window period, the BizTalk Tracking database is archived and a new archive file is created.</span></span> <span data-ttu-id="c97db-113">在作业计划指定的每个 SQL Server 代理作业时间间隔之后，将清除在该生存时段之前完成的所有跟踪数据。</span><span class="sxs-lookup"><span data-stu-id="c97db-113">At each SQL Server Agent job interval specified by the job schedule, all completed tracking data older than the live window period is purged.</span></span>  
  
 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]<span data-ttu-id="c97db-114"> 使用了“软清除”和“硬清除”概念。</span><span class="sxs-lookup"><span data-stu-id="c97db-114"> uses the concept of a soft purge and a hard purge.</span></span> <span data-ttu-id="c97db-115">软清除用来清除已完成的实例，而硬清除仅用来清除未完成的实例。</span><span class="sxs-lookup"><span data-stu-id="c97db-115">The soft purge is used to purge completed instances, while the hard purge is only used to purge incomplete instances.</span></span>  
  
 <span data-ttu-id="c97db-116">**软清除**</span><span class="sxs-lookup"><span data-stu-id="c97db-116">**Soft purge**</span></span>  
  
 <span data-ttu-id="c97db-117">在 DTA 存档和清除作业中，LiveHours 和 LiveDays 参数之和就是要在 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 环境中维护的数据生存时段。</span><span class="sxs-lookup"><span data-stu-id="c97db-117">In the DTA Archive and Purge job, the sum of the LiveHours and LiveDays parameters is the live window of data you want to maintain in your [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] environment.</span></span> <span data-ttu-id="c97db-118">将清除与在此数据生存时段之前完成的实例相关联的所有数据。</span><span class="sxs-lookup"><span data-stu-id="c97db-118">All data associated with a completed instance older than this live window of data is purged.</span></span> <span data-ttu-id="c97db-119">默认情况下，不启用 DTA 存档和清除作业。</span><span class="sxs-lookup"><span data-stu-id="c97db-119">By default, the DTA Archive and Purge job is not enabled.</span></span> <span data-ttu-id="c97db-120">您必须先进行配置，然后才能启用该作业。</span><span class="sxs-lookup"><span data-stu-id="c97db-120">You must first configure and then enable the job.</span></span>  
  
 <span data-ttu-id="c97db-121">例如，你可以配置运行每隔 20 分钟，DTA 清除和存档作业，并将设置 LiveHours = 1 且 LiveDays = 0。</span><span class="sxs-lookup"><span data-stu-id="c97db-121">For example, you can configure the DTA Purge and Archive job to run every 20 minutes, and set LiveHours=1 and LiveDays=0.</span></span> <span data-ttu-id="c97db-122">第一次此 SQL Server 代理作业运行 (T0)，通过创建存档花跟踪数据库的备份，并且一个条目保存在数据库中为此时间戳。</span><span class="sxs-lookup"><span data-stu-id="c97db-122">The first time this SQL Server Agent job runs (T0), it takes a backup of the tracking database by creating an archive and an entry is saved in the database with this timestamp.</span></span> <span data-ttu-id="c97db-123">为了清除跟踪数据，必须保证存档成功。</span><span class="sxs-lookup"><span data-stu-id="c97db-123">A successful archive is necessary in order to purge tracking data.</span></span> <span data-ttu-id="c97db-124">如果存档成功，则与 1 小时前完成的实例相关联的所有数据都将被清除。</span><span class="sxs-lookup"><span data-stu-id="c97db-124">If the archive was successful, then all the data associated with the instances that completed over an hour ago is purged.</span></span> <span data-ttu-id="c97db-125">每次运行该作业时，都将清除 1 小时之前完成的数据。</span><span class="sxs-lookup"><span data-stu-id="c97db-125">Each time the job runs, completed data over one hour old is purged.</span></span> <span data-ttu-id="c97db-126">在第 3 次运行时（1 小时后），将创建一个新的存档，它包含在前 1 小时内插入跟踪数据库的所有实例的数据。</span><span class="sxs-lookup"><span data-stu-id="c97db-126">On the 3rd run (after one hour), a new archive is created that contains the data for all instances that were inserted into the tracking database in the last one hour segment.</span></span>  
  
 <span data-ttu-id="c97db-127">为了与上面的示例相匹配，需要在 DTA 清除和存档作业中配置清除和存档的步骤，代码如下：</span><span class="sxs-lookup"><span data-stu-id="c97db-127">Here is how you would configure the Archive and Purge step in the DTA Purge and Archive job to match the example above:</span></span>  
  
```  
exec dtasp_BackupAndPurgeTrackingDatabase  
1, --@nLiveHours 1,   
0, --@nLiveDays   
1, --@nHardDeleteDays   
‘\\server\backup’, --@nvcFolder   
null, --@nvcValidatingServer   
0 --@fForceBackup Soft purge process  
```  
  
 <span data-ttu-id="c97db-128">最后一次备份的时间戳存储在 BizTalk 跟踪数据库中，以确保只清除上一存档中已有的数据。</span><span class="sxs-lookup"><span data-stu-id="c97db-128">The time stamp of the last backup is stored in the BizTalk Tracking database and ensures that data is only purged if it is in the previous archive.</span></span> <span data-ttu-id="c97db-129">为了增加可靠性，存档按大约 10 分钟的间隔依次重叠。</span><span class="sxs-lookup"><span data-stu-id="c97db-129">For additional reliability, archives are overlapped by approximately 10 minutes.</span></span> <span data-ttu-id="c97db-130">下图显示了基于上述示例的软清除过程。</span><span class="sxs-lookup"><span data-stu-id="c97db-130">The following figure, based on the example above, shows the soft purge process.</span></span> <span data-ttu-id="c97db-131">请注意，存档和清除任务无需同时进行。</span><span class="sxs-lookup"><span data-stu-id="c97db-131">Note that the archiving and purging tasks do not necessarily happen at the same time.</span></span>  
  
 <span data-ttu-id="c97db-132">**软清除过程**</span><span class="sxs-lookup"><span data-stu-id="c97db-132">**Soft purge process**</span></span>  
  
 <span data-ttu-id="c97db-133">![软清除进程](../core/media/archivingandpurging.gif "archivingandpurging")</span><span class="sxs-lookup"><span data-stu-id="c97db-133">![Soft purge process](../core/media/archivingandpurging.gif "archivingandpurging")</span></span>  
  
 <span data-ttu-id="c97db-134">**硬清除**</span><span class="sxs-lookup"><span data-stu-id="c97db-134">**Hard purge**</span></span>  
  
 <span data-ttu-id="c97db-135">由于软清除只清除与已完成的实例相关联的数据，因此，如果存在许多无限期运行的循环实例，则跟踪数据库将会增长，并且这些实例将永远无法清除。</span><span class="sxs-lookup"><span data-stu-id="c97db-135">Because the soft purge only purges data associated with completed instances, if you have many looping instances that run indefinitely, then your tracking database would grow and these instances would never be purged.</span></span> <span data-ttu-id="c97db-136">使用硬清除日期可以清除指定时间间隔之前的所有信息，只有指示服务存在的信息除外。</span><span class="sxs-lookup"><span data-stu-id="c97db-136">The hard purge date allows all information older than the specified interval to be purged except for information indicating a service's existence.</span></span> <span data-ttu-id="c97db-137">设置硬清除使用 **@nHardDeleteDays** 中 DTA 存档和清除作业步骤中的参数存档和清除。</span><span class="sxs-lookup"><span data-stu-id="c97db-137">You set the hard purge using the **@nHardDeleteDays** parameter in the Archive and Purge step in the DTA Archive and Purge job.</span></span> <span data-ttu-id="c97db-138">硬清除设置应始终大于软清除设置。</span><span class="sxs-lookup"><span data-stu-id="c97db-138">The hard purge setting should always be greater than your soft purge setting.</span></span> <span data-ttu-id="c97db-139">换而言之，  **@nHardDeleteDays** 应大于的总和 **@nLiveHours** 和 **@nLiveDays** 。</span><span class="sxs-lookup"><span data-stu-id="c97db-139">In other words, **@nHardDeleteDays** should be greater than the sum of **@nLiveHours** and **@nLiveDays**.</span></span>  
  
 <span data-ttu-id="c97db-140">存档和清除所包括的功能如下表所述：</span><span class="sxs-lookup"><span data-stu-id="c97db-140">Archiving and purging includes the features described in the following table:</span></span>  
  
|<span data-ttu-id="c97db-141">功能</span><span class="sxs-lookup"><span data-stu-id="c97db-141">Feature</span></span>|<span data-ttu-id="c97db-142">Description</span><span class="sxs-lookup"><span data-stu-id="c97db-142">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="c97db-143">硬清除</span><span class="sxs-lookup"><span data-stu-id="c97db-143">Hard purge</span></span>|<span data-ttu-id="c97db-144">使用该功能，可以配置一个时间间隔来清除指定日期之前的示例信息。</span><span class="sxs-lookup"><span data-stu-id="c97db-144">Enables you to configure a time interval to purge information for incomplete instances older than a specified date.</span></span>|  
|<span data-ttu-id="c97db-145">将跟踪的消息复制到跟踪数据库</span><span class="sxs-lookup"><span data-stu-id="c97db-145">Copying tracked messages to tracking database</span></span>|<span data-ttu-id="c97db-146">使用“CopyTrackedMessageToDTA”选项，可以直接将跟踪的消息从 MessageBox 服务器复制到 BizTalk 跟踪数据库中。</span><span class="sxs-lookup"><span data-stu-id="c97db-146">Using the CopyTrackedMessageToDTA option, you can directly copy tracked messages from the MessageBox servers to your BizTalk Tracking database.</span></span> <span data-ttu-id="c97db-147">使用 DTA 清除和存档作业清除数据时，要求进行此操作。</span><span class="sxs-lookup"><span data-stu-id="c97db-147">This is required in order to purge data using the DTA Purge and Archive job.</span></span>|  
|<span data-ttu-id="c97db-148">存档验证</span><span class="sxs-lookup"><span data-stu-id="c97db-148">Archive validation</span></span>|<span data-ttu-id="c97db-149">使用该功能，可以选择设置一个辅助数据库服务器，以便在创建存档时对其进行验证。</span><span class="sxs-lookup"><span data-stu-id="c97db-149">Enables you to optionally set up a secondary database server to validate the archives as they are created.</span></span>|  
|<span data-ttu-id="c97db-150">多个 BizTalk 跟踪数据库版本的跟踪支持</span><span class="sxs-lookup"><span data-stu-id="c97db-150">Tracking support for multiple BizTalk Tracking database versions</span></span>|<span data-ttu-id="c97db-151">这使您能够将跟踪支持与 [!INCLUDE[btsBizTalkServer2004](../includes/btsbiztalkserver2004-md.md)] 和 [!INCLUDE[btsBizTalkServer2006](../includes/btsbiztalkserver2006-md.md)] 数据库存档一起使用。</span><span class="sxs-lookup"><span data-stu-id="c97db-151">Enables you to use tracking support with [!INCLUDE[btsBizTalkServer2004](../includes/btsbiztalkserver2004-md.md)] and [!INCLUDE[btsBizTalkServer2006](../includes/btsbiztalkserver2006-md.md)] database archives.</span></span>|  
|<span data-ttu-id="c97db-152">减少跟踪数据</span><span class="sxs-lookup"><span data-stu-id="c97db-152">Reduction of tracking data</span></span>|<span data-ttu-id="c97db-153">在不减少生成的任何跟踪信息的情况下，显著减少存储的跟踪数据的数量。</span><span class="sxs-lookup"><span data-stu-id="c97db-153">Substantially reduces the amount of tracking data stored without reducing any tracking information generated.</span></span> <span data-ttu-id="c97db-154">这样可以降低跟踪数据库的增长速度。</span><span class="sxs-lookup"><span data-stu-id="c97db-154">This results in slower growth of the tracking database.</span></span>|  
|<span data-ttu-id="c97db-155">更快的跟踪操作，对数据库架构进行了显著优化</span><span class="sxs-lookup"><span data-stu-id="c97db-155">Faster tracking operations, significant optimization in database schemas</span></span>|<span data-ttu-id="c97db-156">使您可以使用跟踪任务在大型数据库中查找消息和服务实例；已对此功能进行了显著优化。</span><span class="sxs-lookup"><span data-stu-id="c97db-156">Enables you to use tracking tasks for finding messages and service instances on large databases; this feature has been significantly optimized.</span></span>|  
  
> [!NOTE]
>  <span data-ttu-id="c97db-157">如果存在通过清除 BizTalk 跟踪数据库暂时得以解决的性能问题，并且希望对 BizTalk 进行控制以便不再收集跟踪信息，则可能要考虑禁用全局跟踪功能。</span><span class="sxs-lookup"><span data-stu-id="c97db-157">If you are having performance issues that are momentarily addressed by purging the BizTalk tracking database, and you want to configure BizTalk to no longer collect tracking information, you may want to consider turning off global tracking.</span></span> <span data-ttu-id="c97db-158">有关禁用全局跟踪功能的信息，请参阅“如何禁用全局跟踪”。</span><span class="sxs-lookup"><span data-stu-id="c97db-158">For information about turning off global tracking, see How to Turn Off Global Tracking.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="c97db-159">本节内容</span><span class="sxs-lookup"><span data-stu-id="c97db-159">In This Section</span></span>  
  
-   [<span data-ttu-id="c97db-160">清单： 存档和清除 BizTalk 跟踪数据库</span><span class="sxs-lookup"><span data-stu-id="c97db-160">Checklist: Archiving and Purging the BizTalk Tracking Database</span></span>](../core/checklist-archiving-and-purging-the-biztalk-tracking-database.md)  
  
-   [<span data-ttu-id="c97db-161">如何配置用于存档和清除数据从跟踪数据库 BizTalk BTS_BACKUP_USERS 角色</span><span class="sxs-lookup"><span data-stu-id="c97db-161">How to Configure the BTS_BACKUP_USERS Role for Archiving and Purging Data from the BizTalk Tracking Database</span></span>](../core/configure-bts_backup_users-role-to-archive-and-purge-from-tracking-database.md)  
  
-   [<span data-ttu-id="c97db-162">如何配置 DTA 清除和存档作业</span><span class="sxs-lookup"><span data-stu-id="c97db-162">How to Configure the DTA Purge and Archive Job</span></span>](../core/how-to-configure-the-dta-purge-and-archive-job.md)  
  
-   [<span data-ttu-id="c97db-163">如何从 BizTalk 跟踪数据库清除数据</span><span class="sxs-lookup"><span data-stu-id="c97db-163">How to Purge Data from the BizTalk Tracking Database</span></span>](../core/how-to-purge-data-from-the-biztalk-tracking-database.md)  
  
-   [<span data-ttu-id="c97db-164">如何从 BizTalk 跟踪数据库手动清除数据</span><span class="sxs-lookup"><span data-stu-id="c97db-164">How to Manually Purge Data from the BizTalk Tracking Database</span></span>](../core/how-to-manually-purge-data-from-the-biztalk-tracking-database.md)  
  
-   [<span data-ttu-id="c97db-165">如何启用自动存档验证</span><span class="sxs-lookup"><span data-stu-id="c97db-165">How to Enable Automatic Archive Validation</span></span>](../core/how-to-enable-automatic-archive-validation.md)  
  
-   [<span data-ttu-id="c97db-166">如何将跟踪的消息复制到跟踪数据库 BizTalk</span><span class="sxs-lookup"><span data-stu-id="c97db-166">How to Copy Tracked Messages into the BizTalk Tracking Database</span></span>](../core/how-to-copy-tracked-messages-into-the-biztalk-tracking-database.md)  
  
-   [<span data-ttu-id="c97db-167">提高了存档和清除过程的性能</span><span class="sxs-lookup"><span data-stu-id="c97db-167">Improving the Performance of the Archiving and Purging Process</span></span>](../core/improving-the-performance-of-the-archiving-and-purging-process.md)  
  
-   [<span data-ttu-id="c97db-168">如何关闭全局跟踪</span><span class="sxs-lookup"><span data-stu-id="c97db-168">How to Turn Off Global Tracking</span></span>](../core/how-to-turn-off-global-tracking.md)