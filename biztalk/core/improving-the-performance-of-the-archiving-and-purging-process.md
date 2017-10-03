---
title: "提高性能的存档和清除进程 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- archiving [Tracking database], system performance
- DTA Purge and Archive job, performance
- purging, limitations
- performance, archiving
- performance, purging
- purging, system performance
ms.assetid: d65da58d-65e0-4f6c-8b15-5d4448049b42
caps.latest.revision: "10"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 3876021fec4d604960d672671cab8bf4be1dc0a5
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="improving-the-performance-of-the-archiving-and-purging-process"></a><span data-ttu-id="642f0-102">提高存档和清除进程的性能</span><span class="sxs-lookup"><span data-stu-id="642f0-102">Improving the Performance of the Archiving and Purging Process</span></span>
<span data-ttu-id="642f0-103">[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 数据库中存储的数据量有可能增长得非常迅速，这与 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 方案的设计方式、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 方案所处理的消息数量和消息大小以及跟踪的配置方式都有关。</span><span class="sxs-lookup"><span data-stu-id="642f0-103">The amount of data stored in the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] databases can grow very quickly depending on how you have designed your [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] scenario, depending on the number and size of messages processed by your [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] scenario, and depending on how you have configured tracking.</span></span> <span data-ttu-id="642f0-104">使数据库大小维持在合理的水平，可提高处理效率并使系统中的数据量在任何给定时间都保持正常。</span><span class="sxs-lookup"><span data-stu-id="642f0-104">By maintaining your database size at a healthy level, processing is more efficient and the amount of data in your system is normalized at any given time.</span></span> <span data-ttu-id="642f0-105">这样能够发挥出高效而稳定的性能。</span><span class="sxs-lookup"><span data-stu-id="642f0-105">This provides efficient and consistent performance.</span></span> <span data-ttu-id="642f0-106">此过程的自动化，可免去您手动维护数据库的工作。</span><span class="sxs-lookup"><span data-stu-id="642f0-106">By automating this process you free yourself of the burden of manually maintaining your databases.</span></span>  
  
## <a name="configuring-a-healthy-environment"></a><span data-ttu-id="642f0-107">配置运行状况良好的环境</span><span class="sxs-lookup"><span data-stu-id="642f0-107">Configuring a healthy environment</span></span>  
 <span data-ttu-id="642f0-108">维护运行状况良好的 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 环境的策略主要取决于您的特定方案和运行该方案的硬件。</span><span class="sxs-lookup"><span data-stu-id="642f0-108">Your strategy in maintaining a healthy [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] environment is heavily dependent on your particular scenario and the hardware it is running on.</span></span> <span data-ttu-id="642f0-109">关键是监视 BizTalk 跟踪 (BizTalkDTADb) 数据库的增长速率和大小。</span><span class="sxs-lookup"><span data-stu-id="642f0-109">The key things to monitor are the rate of growth and the size of your BizTalk Tracking (BizTalkDTADb) database.</span></span> <span data-ttu-id="642f0-110">跟踪数据库的一些表占据大量数据库空间，因此在运行时会影响性能。</span><span class="sxs-lookup"><span data-stu-id="642f0-110">A few tables of the tracking database account for bulk of the database size and hence the performance impact on runtime.</span></span>  
  
 <span data-ttu-id="642f0-111">配置同一个方案，却可以产生数量大不相同的跟踪数据，这取决于跟踪点的数量、用到的不同消息的数量、这些消息的大小以及所使用的消息正文跟踪的级别。</span><span class="sxs-lookup"><span data-stu-id="642f0-111">The same scenario can be configured to produce vastly different amount of tracking data based on how many tracking points are present, how many different messages are used, size of the messages and the level of message body tracking used.</span></span> <span data-ttu-id="642f0-112">下面是有关的一些重要因素：</span><span class="sxs-lookup"><span data-stu-id="642f0-112">Following are some important factors to monitor:</span></span>  
  
-   <span data-ttu-id="642f0-113">跟踪点（如管道、业务流程和端口）的数量</span><span class="sxs-lookup"><span data-stu-id="642f0-113">Number of tracking points - such as pipelines, orchestrations, and ports</span></span>  
  
-   <span data-ttu-id="642f0-114">跟踪的消息属性数</span><span class="sxs-lookup"><span data-stu-id="642f0-114">Number of message properties tracked</span></span>  
  
-   <span data-ttu-id="642f0-115">每个传入消息的消息数</span><span class="sxs-lookup"><span data-stu-id="642f0-115">Number of messages per incoming message</span></span>  
  
-   <span data-ttu-id="642f0-116">消息大小</span><span class="sxs-lookup"><span data-stu-id="642f0-116">Message size</span></span>  
  
-   <span data-ttu-id="642f0-117">通信速率（平均值和峰值）</span><span class="sxs-lookup"><span data-stu-id="642f0-117">Traffic rate (average and peak)</span></span>  
  
-   <span data-ttu-id="642f0-118">消息正文跟踪配置</span><span class="sxs-lookup"><span data-stu-id="642f0-118">Message body tracking configuration</span></span>  
  
 <span data-ttu-id="642f0-119">在涉及自动存档和清除数据时，请考虑需要保存在跟踪数据库中的实时数据量。</span><span class="sxs-lookup"><span data-stu-id="642f0-119">When considering automatic archiving and purging of data consider how much live data you need to keep in your tracking database.</span></span> <span data-ttu-id="642f0-120">您需要根据您的环境调整 DTA 清除和存档作业参数，以便在清除性能不会下降的前提下支持目标实时数据量。</span><span class="sxs-lookup"><span data-stu-id="642f0-120">You need to tune the DTA Purge and Archive job parameters as appropriate for your environment so that the targeted amount of live data can be supported by the purging performance without degradation.</span></span>  
  
 <span data-ttu-id="642f0-121">DTA 清除和存档作业可在给定时间间隔内清除特定数量的数据。</span><span class="sxs-lookup"><span data-stu-id="642f0-121">The DTA Purge and Archive job can purge a certain amount of data within a given time interval.</span></span> <span data-ttu-id="642f0-122">该作业的处理能力取决于运行的方案、当前数据库大小和硬件。</span><span class="sxs-lookup"><span data-stu-id="642f0-122">The capacity of the job depends on the scenarios running, the current database size, and the hardware.</span></span> <span data-ttu-id="642f0-123">为了获得稳定的环境，必须在传入跟踪数据的生成和清除之间取得平衡。</span><span class="sxs-lookup"><span data-stu-id="642f0-123">In order to have a stable environment, you must have a balance between the incoming tracking data generation and purging.</span></span> <span data-ttu-id="642f0-124">在测试环境中，可通过改变数据的生存时段和清除作业的频率来找到平衡。</span><span class="sxs-lookup"><span data-stu-id="642f0-124">In your test environment, you can find the balance by varying the live window of data and the frequency of the purging job.</span></span> <span data-ttu-id="642f0-125">在平衡状态下，系统将具有持续稳定的吞吐量。</span><span class="sxs-lookup"><span data-stu-id="642f0-125">In a balanced state, your system will deliver sustainable throughput.</span></span> <span data-ttu-id="642f0-126">您的目标是在 BizTalk 跟踪数据库表大小导致持续显著的性能问题之前，具有足够的缓冲区。</span><span class="sxs-lookup"><span data-stu-id="642f0-126">Your goal is to have enough of a buffer before the BizTalk Tracking database table size causes sustained, significant performance issues.</span></span>  
  
## <a name="performance-limitations"></a><span data-ttu-id="642f0-127">性能限制</span><span class="sxs-lookup"><span data-stu-id="642f0-127">Performance limitations</span></span>  
 <span data-ttu-id="642f0-128">清除时的性能对所有方案都是不可调整的。</span><span class="sxs-lookup"><span data-stu-id="642f0-128">Purging performance will not scale for all scenarios.</span></span> <span data-ttu-id="642f0-129">对于任何方案，跟踪数据量都可能不断增加。</span><span class="sxs-lookup"><span data-stu-id="642f0-129">For any scenario, it is possible to generate increasing amounts of tracking data.</span></span> <span data-ttu-id="642f0-130">当以持续较低速率清除跟踪数据时，跟踪数据库的大小就会增大，这会使清除性能进一步恶化。</span><span class="sxs-lookup"><span data-stu-id="642f0-130">When tracking data is purged at a consistently slower rate, there is a buildup of the tracking database size, which worsens the purging performance further.</span></span>  
  
 <span data-ttu-id="642f0-131">在负载不可承受的条件下，复制消息正文的速度也会降低，这可能在 MessageBox 数据库中形成积压。</span><span class="sxs-lookup"><span data-stu-id="642f0-131">Under unsustainable load conditions, the copying of message bodies may also become slower and there may become a backlog in the MessageBox database.</span></span> <span data-ttu-id="642f0-132">在极端条件下，日常消息正文复制和跟踪会产生消息正文不可用的存档，即使该消息包含相关的实例信息。</span><span class="sxs-lookup"><span data-stu-id="642f0-132">Under extreme conditions, the daily message body copying and tracking may lead to archives where the message body is not available even though it contains related instance information.</span></span> <span data-ttu-id="642f0-133">通常，高负载阶段和低负载阶段交替进行，使落后的作业在低负载阶段得以弥补。</span><span class="sxs-lookup"><span data-stu-id="642f0-133">Typically, periods of high loads alternate with periods of low load and enable the job to catch up during periods of low load.</span></span>  
  
 <span data-ttu-id="642f0-134">由于不断清除数据库并对存储的跟踪数据进行压缩，存档和清除 BizTalk 跟踪数据库能够大大降低发生负载不可承受情况的可能性。</span><span class="sxs-lookup"><span data-stu-id="642f0-134">Archiving and purging the BizTalk Tracking database should considerably reduce the possibility of unsustainable load conditions because of the continuous pruning of the database and the compaction of stored tracking data.</span></span> <span data-ttu-id="642f0-135">这些进程极大地减少了手动干预的需要。</span><span class="sxs-lookup"><span data-stu-id="642f0-135">These processes greatly reduce the need for manual intervention.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="642f0-136">另请参阅</span><span class="sxs-lookup"><span data-stu-id="642f0-136">See Also</span></span>  
 [<span data-ttu-id="642f0-137">存档和清除 BizTalk 跟踪数据库</span><span class="sxs-lookup"><span data-stu-id="642f0-137">Archiving and Purging the BizTalk Tracking Database</span></span>](../core/archiving-and-purging-the-biztalk-tracking-database.md)