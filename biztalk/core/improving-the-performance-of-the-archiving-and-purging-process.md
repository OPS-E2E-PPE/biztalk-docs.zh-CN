---
title: 提高性能的存档和清除进程 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- archiving [Tracking database], system performance
- DTA Purge and Archive job, performance
- purging, limitations
- performance, archiving
- performance, purging
- purging, system performance
ms.assetid: d65da58d-65e0-4f6c-8b15-5d4448049b42
caps.latest.revision: 10
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: e6d7cb6adf314bd5575d354c52c2682138bad784
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65382200"
---
# <a name="improving-the-performance-of-the-archiving-and-purging-process"></a><span data-ttu-id="148af-102">提高存档和清除进程的性能</span><span class="sxs-lookup"><span data-stu-id="148af-102">Improving the Performance of the Archiving and Purging Process</span></span>
<span data-ttu-id="148af-103">存储中的数据量[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]数据库可根据设计方式非常快速地增长你[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]方案中，根据的数量和处理的消息的大小在[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]方案中，并取决于如何具有配置跟踪。</span><span class="sxs-lookup"><span data-stu-id="148af-103">The amount of data stored in the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] databases can grow very quickly depending on how you have designed your [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] scenario, depending on the number and size of messages processed by your [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] scenario, and depending on how you have configured tracking.</span></span> <span data-ttu-id="148af-104">通过维护你的数据库大小正常级别，处理效率更高，并且在任何给定时间规范化你的系统中的数据量。</span><span class="sxs-lookup"><span data-stu-id="148af-104">By maintaining your database size at a healthy level, processing is more efficient and the amount of data in your system is normalized at any given time.</span></span> <span data-ttu-id="148af-105">这提供了高效的一致性能。</span><span class="sxs-lookup"><span data-stu-id="148af-105">This provides efficient and consistent performance.</span></span> <span data-ttu-id="148af-106">通过自动执行此过程，解放自我您手动维护数据库的负担。</span><span class="sxs-lookup"><span data-stu-id="148af-106">By automating this process you free yourself of the burden of manually maintaining your databases.</span></span>  
  
## <a name="configuring-a-healthy-environment"></a><span data-ttu-id="148af-107">配置正常运行的环境</span><span class="sxs-lookup"><span data-stu-id="148af-107">Configuring a healthy environment</span></span>  
 <span data-ttu-id="148af-108">策略维护正常[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]环境是很大程度上取决于特定方案和硬件运行。</span><span class="sxs-lookup"><span data-stu-id="148af-108">Your strategy in maintaining a healthy [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] environment is heavily dependent on your particular scenario and the hardware it is running on.</span></span> <span data-ttu-id="148af-109">若要监视的重要事项是 BizTalk 跟踪 (BizTalkDTADb) 数据库的大小和增长的速率。</span><span class="sxs-lookup"><span data-stu-id="148af-109">The key things to monitor are the rate of growth and the size of your BizTalk Tracking (BizTalkDTADb) database.</span></span> <span data-ttu-id="148af-110">跟踪数据库的一些表占据大量数据库大小，因此将运行时对性能的影响。</span><span class="sxs-lookup"><span data-stu-id="148af-110">A few tables of the tracking database account for bulk of the database size and hence the performance impact on runtime.</span></span>  
  
 <span data-ttu-id="148af-111">相同的方案可以配置为生成都得到了显著不同数量的跟踪数据基于跟踪点的数量都存在，如何使用许多不同的消息，使用的消息大小和消息正文跟踪的级别。</span><span class="sxs-lookup"><span data-stu-id="148af-111">The same scenario can be configured to produce vastly different amount of tracking data based on how many tracking points are present, how many different messages are used, size of the messages and the level of message body tracking used.</span></span> <span data-ttu-id="148af-112">以下是一些重要因素：</span><span class="sxs-lookup"><span data-stu-id="148af-112">Following are some important factors to monitor:</span></span>  
  
- <span data-ttu-id="148af-113">跟踪点-例如管道、 业务流程和端口号</span><span class="sxs-lookup"><span data-stu-id="148af-113">Number of tracking points - such as pipelines, orchestrations, and ports</span></span>  
  
- <span data-ttu-id="148af-114">跟踪消息属性的数目</span><span class="sxs-lookup"><span data-stu-id="148af-114">Number of message properties tracked</span></span>  
  
- <span data-ttu-id="148af-115">每个传入消息的消息数</span><span class="sxs-lookup"><span data-stu-id="148af-115">Number of messages per incoming message</span></span>  
  
- <span data-ttu-id="148af-116">消息大小</span><span class="sxs-lookup"><span data-stu-id="148af-116">Message size</span></span>  
  
- <span data-ttu-id="148af-117">通信速率 （平均值和峰值）</span><span class="sxs-lookup"><span data-stu-id="148af-117">Traffic rate (average and peak)</span></span>  
  
- <span data-ttu-id="148af-118">消息正文跟踪配置</span><span class="sxs-lookup"><span data-stu-id="148af-118">Message body tracking configuration</span></span>  
  
  <span data-ttu-id="148af-119">自动存档和清除数据，请考虑需要保留在跟踪数据库中的实时数据量。</span><span class="sxs-lookup"><span data-stu-id="148af-119">When considering automatic archiving and purging of data consider how much live data you need to keep in your tracking database.</span></span> <span data-ttu-id="148af-120">您需要调整 DTA 清除和存档作业参数，以根据你的环境，以便清除而不会降低性能可以支持目标实时数据量。</span><span class="sxs-lookup"><span data-stu-id="148af-120">You need to tune the DTA Purge and Archive job parameters as appropriate for your environment so that the targeted amount of live data can be supported by the purging performance without degradation.</span></span>  
  
  <span data-ttu-id="148af-121">DTA 清除和存档作业可以在给定的时间间隔内清除一定数量的数据。</span><span class="sxs-lookup"><span data-stu-id="148af-121">The DTA Purge and Archive job can purge a certain amount of data within a given time interval.</span></span> <span data-ttu-id="148af-122">作业的容量取决于运行的方案、 当前数据库大小和硬件。</span><span class="sxs-lookup"><span data-stu-id="148af-122">The capacity of the job depends on the scenarios running, the current database size, and the hardware.</span></span> <span data-ttu-id="148af-123">为了获得稳定的环境，必须具有传入的跟踪数据的生成和清除之间的平衡。</span><span class="sxs-lookup"><span data-stu-id="148af-123">In order to have a stable environment, you must have a balance between the incoming tracking data generation and purging.</span></span> <span data-ttu-id="148af-124">在测试环境中，可以通过不同的数据生存时段和清除作业的频率来找到平衡。</span><span class="sxs-lookup"><span data-stu-id="148af-124">In your test environment, you can find the balance by varying the live window of data and the frequency of the purging job.</span></span> <span data-ttu-id="148af-125">在平衡状态下，系统将提供可承受吞吐量。</span><span class="sxs-lookup"><span data-stu-id="148af-125">In a balanced state, your system will deliver sustainable throughput.</span></span> <span data-ttu-id="148af-126">你的目标是缓冲区的具有足够，然后 BizTalk 跟踪数据库表大小导致持续显著的性能问题。</span><span class="sxs-lookup"><span data-stu-id="148af-126">Your goal is to have enough of a buffer before the BizTalk Tracking database table size causes sustained, significant performance issues.</span></span>  
  
## <a name="performance-limitations"></a><span data-ttu-id="148af-127">性能限制</span><span class="sxs-lookup"><span data-stu-id="148af-127">Performance limitations</span></span>  
 <span data-ttu-id="148af-128">所有情况下将不能清除时的性能。</span><span class="sxs-lookup"><span data-stu-id="148af-128">Purging performance will not scale for all scenarios.</span></span> <span data-ttu-id="148af-129">对于任何方案，就可以生成数量不断增长的跟踪数据。</span><span class="sxs-lookup"><span data-stu-id="148af-129">For any scenario, it is possible to generate increasing amounts of tracking data.</span></span> <span data-ttu-id="148af-130">当以持续较低速率清除跟踪数据时，会跟踪的数据库大小，清除性能进一步恶化。</span><span class="sxs-lookup"><span data-stu-id="148af-130">When tracking data is purged at a consistently slower rate, there is a buildup of the tracking database size, which worsens the purging performance further.</span></span>  
  
 <span data-ttu-id="148af-131">在负载不可承受情况下复制消息正文可能也会降低，并且那里可能会积压在 MessageBox 数据库中。</span><span class="sxs-lookup"><span data-stu-id="148af-131">Under unsustainable load conditions, the copying of message bodies may also become slower and there may become a backlog in the MessageBox database.</span></span> <span data-ttu-id="148af-132">在极端条件下每日消息正文复制和跟踪可能会导致存档消息正文并不可用的即使它包含相关的实例信息。</span><span class="sxs-lookup"><span data-stu-id="148af-132">Under extreme conditions, the daily message body copying and tracking may lead to archives where the message body is not available even though it contains related instance information.</span></span> <span data-ttu-id="148af-133">通常情况下，高负载的时间段与低负载的高峰期的备用和启用作业，以便在低负载时段保持同步。</span><span class="sxs-lookup"><span data-stu-id="148af-133">Typically, periods of high loads alternate with periods of low load and enable the job to catch up during periods of low load.</span></span>  
  
 <span data-ttu-id="148af-134">存档和清除 BizTalk 跟踪数据库能够大大降低负载不可承受情况可能会由于数据库的连续修剪和存储的跟踪数据压缩。</span><span class="sxs-lookup"><span data-stu-id="148af-134">Archiving and purging the BizTalk Tracking database should considerably reduce the possibility of unsustainable load conditions because of the continuous pruning of the database and the compaction of stored tracking data.</span></span> <span data-ttu-id="148af-135">这些进程极大地减少需手动干预。</span><span class="sxs-lookup"><span data-stu-id="148af-135">These processes greatly reduce the need for manual intervention.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="148af-136">请参阅</span><span class="sxs-lookup"><span data-stu-id="148af-136">See Also</span></span>  
 [<span data-ttu-id="148af-137">存档和清除 BizTalk 跟踪数据库</span><span class="sxs-lookup"><span data-stu-id="148af-137">Archiving and Purging the BizTalk Tracking Database</span></span>](../core/archiving-and-purging-the-biztalk-tracking-database.md)