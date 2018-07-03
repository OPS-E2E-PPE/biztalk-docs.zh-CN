---
title: 优化业务活动监视 (BAM) 性能 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: c9ed29b2-0be6-4a37-be68-9476832fd49f
caps.latest.revision: 4
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: f28771f2611a8b5f7c2522b7cd45e875897645e9
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "36996198"
---
# <a name="optimizing-business-activity-monitoring-bam-performance"></a><span data-ttu-id="980d0-102">优化业务活动监视 (BAM) 性能</span><span class="sxs-lookup"><span data-stu-id="980d0-102">Optimizing Business Activity Monitoring (BAM) Performance</span></span>
<span data-ttu-id="980d0-103">本主题介绍了业务活动监视 (BAM) 的性能因素。</span><span class="sxs-lookup"><span data-stu-id="980d0-103">This topic describes Business Activity Monitoring (BAM) performance factors.</span></span>  
  
## <a name="bam-disk-usage-configuration"></a><span data-ttu-id="980d0-104">BAM 磁盘使用情况配置</span><span class="sxs-lookup"><span data-stu-id="980d0-104">BAM disk usage configuration</span></span>  
 <span data-ttu-id="980d0-105">如果在负载下的大量数据保存到 BAM 数据库的原因是 BizTalk 系统，BAM 会产生很大的开销。</span><span class="sxs-lookup"><span data-stu-id="980d0-105">BAM incurs significant overhead when a BizTalk system is under load because of the significant amount of data that is persisted to the BAM database.</span></span> <span data-ttu-id="980d0-106">因此，明智地使用 BAM 数据库的磁盘 I/O 技术是非常重要。</span><span class="sxs-lookup"><span data-stu-id="980d0-106">Therefore, judicious use of disk I/O techniques for the BAM database is critically important.</span></span>  
  
## <a name="bam-eventstream-apis"></a><span data-ttu-id="980d0-107">BAM EventStream Api</span><span class="sxs-lookup"><span data-stu-id="980d0-107">BAM EventStream APIs</span></span>  
 <span data-ttu-id="980d0-108">四种类型的 EventStreams 是可用于在 BizTalk BAM 方案中使用：</span><span class="sxs-lookup"><span data-stu-id="980d0-108">Four types of EventStreams are available for use in a BizTalk BAM scenario:</span></span>  
  
- <span data-ttu-id="980d0-109">DirectEventStream (DES)</span><span class="sxs-lookup"><span data-stu-id="980d0-109">DirectEventStream (DES)</span></span>  
  
- <span data-ttu-id="980d0-110">BufferedEventStream (BES)</span><span class="sxs-lookup"><span data-stu-id="980d0-110">BufferedEventStream (BES)</span></span>  
  
- <span data-ttu-id="980d0-111">OrchestrationEventStream (OES)</span><span class="sxs-lookup"><span data-stu-id="980d0-111">OrchestrationEventStream (OES)</span></span>  
  
- <span data-ttu-id="980d0-112">MessageEventStream (MES)</span><span class="sxs-lookup"><span data-stu-id="980d0-112">MessageEventStream (MES)</span></span>  
  
  <span data-ttu-id="980d0-113">应选择一种基于以下因素这些 Api:</span><span class="sxs-lookup"><span data-stu-id="980d0-113">You should choose one of these APIs based on the following factors:</span></span>  
  
- <span data-ttu-id="980d0-114">如果关心延迟问题，请选择 DES，可使数据同步地保留到 BAM 主导入数据库。</span><span class="sxs-lookup"><span data-stu-id="980d0-114">If your concern is latency, choose DES, where data is persisted synchronously to the BAM Primary Import database.</span></span>  
  
- <span data-ttu-id="980d0-115">如果您关注的问题的性能和事件插入的吞吐量，请选择异步 API （BES、 OES 或 MES）。</span><span class="sxs-lookup"><span data-stu-id="980d0-115">If your concern is performance and throughput of event insertion, choose an asynchronous API (BES, OES or MES).</span></span>  
  
- <span data-ttu-id="980d0-116">如果你正在编写不具有的计算机运行的应用程序安装 BizTalk Server，请使用 DES 和 BES;可以在非 BizTalk 应用程序中使用这些 Api。</span><span class="sxs-lookup"><span data-stu-id="980d0-116">If you are writing an application that runs on a computer that does not have BizTalk Server installed, use DES and BES; these APIs can be used in non-BizTalk applications.</span></span>  
  
  > [!NOTE]  
  >  <span data-ttu-id="980d0-117">在有些情况下，您可能需要混合使用 EventStream 类型。</span><span class="sxs-lookup"><span data-stu-id="980d0-117">There are scenarios in which you may want to mix EventStream types.</span></span> <span data-ttu-id="980d0-118">例如，为管道处理，您可能想要捕获特定数据在 BAM 中的，而不考虑是否管道正在回滚其事务。</span><span class="sxs-lookup"><span data-stu-id="980d0-118">For example, for pipeline processing, you may want to capture the particular data in BAM regardless of whether the pipeline is rolling back its transaction.</span></span> <span data-ttu-id="980d0-119">具体而言，您可能希望捕获有关失败的消息数的数据或管道处理过程中出现多少次重试。</span><span class="sxs-lookup"><span data-stu-id="980d0-119">In particular, you may want capture data about how many messages failed or how many retries occurred during pipeline processing.</span></span> <span data-ttu-id="980d0-120">若要在这种情况下捕获数据，应使用 BES。</span><span class="sxs-lookup"><span data-stu-id="980d0-120">To capture the data in this situation you should use BES.</span></span>  
  
- <span data-ttu-id="980d0-121">如果您的应用程序运行在安装了 BizTalk Server 的计算机上，请使用 MES 和 OES。</span><span class="sxs-lookup"><span data-stu-id="980d0-121">If your application runs on a computer on which BizTalk Server is installed, use MES and OES.</span></span> <span data-ttu-id="980d0-122">（这些 API 只在 BizTalk 应用程序中可用。）</span><span class="sxs-lookup"><span data-stu-id="980d0-122">(These APIs are available only from BizTalk applications.)</span></span>  
  
  > [!NOTE]  
  >  <span data-ttu-id="980d0-123">OES 等效于 MES，但对 BizTalk 业务流程除外。</span><span class="sxs-lookup"><span data-stu-id="980d0-123">OES is the equivalent of MES but for BizTalk orchestrations.</span></span>  
  
- <span data-ttu-id="980d0-124">如果您希望 BAM 事件持久化与管道事务保持同步，则应使用消息传送事件 Stream (MES)。</span><span class="sxs-lookup"><span data-stu-id="980d0-124">If you want BAM event persistence to be in sync with pipeline transaction, you should use a Messaging Event Stream (MES).</span></span>  
  
  <span data-ttu-id="980d0-125">所有异步 EventStreams （BES、 MES 和 OES） 首次保存到 BizTalk MessageBox 数据库的数据。</span><span class="sxs-lookup"><span data-stu-id="980d0-125">All the asynchronous EventStreams (BES, MES, and OES) persist data first to the BizTalk MessageBox database.</span></span> <span data-ttu-id="980d0-126">跟踪数据解码服务 (TDDS) 会定期处理这些数据，并将其持久化到 BAM 主导入数据库。</span><span class="sxs-lookup"><span data-stu-id="980d0-126">Periodically the data is processed and persisted to the BAM Primary Import database by the Tracking Data Decode Service (TDDS).</span></span>  
  
  <span data-ttu-id="980d0-127">有关 BAM EventStream Api 的详细信息，请参阅[EventStream 类](http://go.microsoft.com/fwlink/?LinkId=158046)(http://go.microsoft.com/fwlink/?LinkId=158046) BizTalk Server 文档中。</span><span class="sxs-lookup"><span data-stu-id="980d0-127">For more information about the BAM EventStream APIs, see [EventStream Classes](http://go.microsoft.com/fwlink/?LinkId=158046) (http://go.microsoft.com/fwlink/?LinkId=158046) in the BizTalk Server documentation.</span></span>  
  
## <a name="bam-performance-counters"></a><span data-ttu-id="980d0-128">BAM 性能计数器</span><span class="sxs-lookup"><span data-stu-id="980d0-128">BAM performance counters</span></span>  
 <span data-ttu-id="980d0-129">有关 BAM 的性能计数器的详细列表，请参阅[BAM 性能计数器](http://go.microsoft.com/fwlink/?LinkId=158048)(http://go.microsoft.com/fwlink/?LinkId=158048) BizTalk Server 文档中。</span><span class="sxs-lookup"><span data-stu-id="980d0-129">For a detailed list of the performance counters for BAM, see [BAM Performance Counters](http://go.microsoft.com/fwlink/?LinkId=158048) (http://go.microsoft.com/fwlink/?LinkId=158048) in the BizTalk Server documentation.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="980d0-130">请参阅</span><span class="sxs-lookup"><span data-stu-id="980d0-130">See Also</span></span>  
 [<span data-ttu-id="980d0-131">优化 BizTalk Server 性能</span><span class="sxs-lookup"><span data-stu-id="980d0-131">Optimizing BizTalk Server Performance</span></span>](../technical-guides/optimizing-biztalk-server-performance.md)