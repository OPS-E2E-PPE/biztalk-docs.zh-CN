---
title: EventStream 类 |Microsoft 文档
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: a3e7a6b3-69cc-4312-9074-acccd1175d37
caps.latest.revision: 11
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 89eafdced54927007bcc8dfc02e4834641e2ae2f
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22245821"
---
# <a name="eventstream-classes"></a><span data-ttu-id="512d3-102">EventStream 类</span><span class="sxs-lookup"><span data-stu-id="512d3-102">EventStream Classes</span></span>
<span data-ttu-id="512d3-103">用于 BAM 的 EventStream API 驻留在 Microsoft.BizTalk.BAM.EventObservation 命名空间中。</span><span class="sxs-lookup"><span data-stu-id="512d3-103">The EventStream APIs for BAM reside in the Microsoft.BizTalk.BAM.EventObservation namespace.</span></span> <span data-ttu-id="512d3-104">要针对该 API 进行编码，必须在用于开发的计算机上安装以下 DLL：</span><span class="sxs-lookup"><span data-stu-id="512d3-104">To code against the APIs, you must install the following DLLs on your development computer:</span></span>  
  
-   <span data-ttu-id="512d3-105">Microsoft.BizTalk.BAM.EventObservation.dll</span><span class="sxs-lookup"><span data-stu-id="512d3-105">Microsoft.BizTalk.BAM.EventObservation.dll</span></span>  
  
-   <span data-ttu-id="512d3-106">Microsoft.Biztalk.BAM.Xlangs.dll： 此 DLL 是必需的业务流程事件流进行编码。</span><span class="sxs-lookup"><span data-stu-id="512d3-106">Microsoft.Biztalk.BAM.Xlangs.dll: This DLL is required when coding for Orchestration event streams.</span></span>  
  
-   <span data-ttu-id="512d3-107">Microsoft.BizTalk.Pipeline.dll： 在编码的管道上下文用于消息传递事件流时需要此 DLL。</span><span class="sxs-lookup"><span data-stu-id="512d3-107">Microsoft.BizTalk.Pipeline.dll: This DLL required when using coding pipeline contexts for Messaging event streams.</span></span>  
  
 <span data-ttu-id="512d3-108">将该 DLL 添加到您的项目引用，并使用下面的 using 语句在编码中包括命名空间：</span><span class="sxs-lookup"><span data-stu-id="512d3-108">Add the DLL to your project reference and include the namespace in your code with the following using statement:</span></span>  
  
```  
using Microsoft.BizTalk.Bam.EventObservation;  
```  
  
 <span data-ttu-id="512d3-109">**类**</span><span class="sxs-lookup"><span data-stu-id="512d3-109">**Classes**</span></span>  
  
|<span data-ttu-id="512d3-110">Name</span><span class="sxs-lookup"><span data-stu-id="512d3-110">Name</span></span>|<span data-ttu-id="512d3-111">Description</span><span class="sxs-lookup"><span data-stu-id="512d3-111">Description</span></span>|  
|----------|-----------------|  
|<span data-ttu-id="512d3-112">DirectEventStream (DES)</span><span class="sxs-lookup"><span data-stu-id="512d3-112">DirectEventStream (DES)</span></span>|<span data-ttu-id="512d3-113">同步，无延迟</span><span class="sxs-lookup"><span data-stu-id="512d3-113">Synchronous, no latency</span></span>|  
|<span data-ttu-id="512d3-114">BufferedEventStream (BES)</span><span class="sxs-lookup"><span data-stu-id="512d3-114">BufferedEventStream (BES)</span></span>|<span data-ttu-id="512d3-115">异步，高吞吐量，有一定的延迟</span><span class="sxs-lookup"><span data-stu-id="512d3-115">Asynchronous, high throughput, some latency</span></span>|  
|<span data-ttu-id="512d3-116">OrchestrationEventStream (OES)</span><span class="sxs-lookup"><span data-stu-id="512d3-116">OrchestrationEventStream (OES)</span></span>|<span data-ttu-id="512d3-117">异步，参与 BizTalk 业务流程事务</span><span class="sxs-lookup"><span data-stu-id="512d3-117">Asynchronous, participates in BizTalk orchestration transactions</span></span>|  
|<span data-ttu-id="512d3-118">IPipelineContext 接口</span><span class="sxs-lookup"><span data-stu-id="512d3-118">IPipelineContext Interface</span></span>|<span data-ttu-id="512d3-119">异步，参与 BizTalk Server 管道事务。</span><span class="sxs-lookup"><span data-stu-id="512d3-119">Asynchronous, participates in BizTalk Server pipeline transactions.</span></span> <span data-ttu-id="512d3-120">用于创建消息传送事件流 (MES)。</span><span class="sxs-lookup"><span data-stu-id="512d3-120">Used to create Messaging Event Streams (MES).</span></span>|  
  
 <span data-ttu-id="512d3-121">您应该基于以下因素选择 API：</span><span class="sxs-lookup"><span data-stu-id="512d3-121">You should choose an API based on the following factors:</span></span>  
  
-   <span data-ttu-id="512d3-122">如果关心延迟问题，请选择 DES，可使数据同步地保留到 BAM 主导入数据库。</span><span class="sxs-lookup"><span data-stu-id="512d3-122">If your concern is latency, choose DES, where data is persisted synchronously to the BAM Primary Import database.</span></span> <span data-ttu-id="512d3-123">除 DES 之外，所有其他 EventStream 类是异步的，并具有一些滞后时间。</span><span class="sxs-lookup"><span data-stu-id="512d3-123">Except for DES, all other EventStream classes are asynchronous and have some latency.</span></span> <span data-ttu-id="512d3-124">数据首先将暂留到 MessageBox，随后由 TDDS 处理，从而可以将数据移动到 BAMPrimaryImport 数据库中。</span><span class="sxs-lookup"><span data-stu-id="512d3-124">The data is first persisted to MessageBox and subsequently processed by TDDS which moves data into the BAMPrimaryImport database.</span></span>  
  
-   <span data-ttu-id="512d3-125">如果关心事件插入的性能和吞吐量，请选择异步 API。</span><span class="sxs-lookup"><span data-stu-id="512d3-125">If your concern is performance and throughput of event insertion, choose an asynchronous API.</span></span>  
  
-   <span data-ttu-id="512d3-126">如果您要编写的应用程序运行在没有安装 BizTalk Server 的计算机上，请使用 DES 和 BES。</span><span class="sxs-lookup"><span data-stu-id="512d3-126">If you are writing an application that runs on a computer that does not have BizTalk Server installed, use DES and BES.</span></span> <span data-ttu-id="512d3-127">（也就是说，这些 API 可以在非 BizTalk 应用程序中使用。）</span><span class="sxs-lookup"><span data-stu-id="512d3-127">(In other words, these APIs can be used in non-BizTalk applications.)</span></span>  
  
-   <span data-ttu-id="512d3-128">如果您的应用程序运行在安装了 BizTalk Server 的计算机上，请使用 MES 和 OES。</span><span class="sxs-lookup"><span data-stu-id="512d3-128">If your application runs on a computer on which BizTalk Server is installed, use MES and OES.</span></span> <span data-ttu-id="512d3-129">（这些 API 只在 BizTalk 应用程序中可用。）</span><span class="sxs-lookup"><span data-stu-id="512d3-129">(These APIs are available only from BizTalk applications.)</span></span>  
  
    -   <span data-ttu-id="512d3-130">如果您希望 BAM 事件持久化与管道事务保持同步，应使用消息传送事件流。</span><span class="sxs-lookup"><span data-stu-id="512d3-130">If you want BAM event persistence to be in sync with pipeline transaction, you should use a Messaging Event Stream.</span></span>  
  
    -   <span data-ttu-id="512d3-131">OES 等效于 MES，但对 BizTalk 业务流程除外。</span><span class="sxs-lookup"><span data-stu-id="512d3-131">OES is the equivalent of MES but for BizTalk orchestrations.</span></span>  
  
 <span data-ttu-id="512d3-132">在有些情况下，您可能需要混合使用 EventStream 类型。</span><span class="sxs-lookup"><span data-stu-id="512d3-132">There are scenarios in which you may want to mix EventStream types.</span></span> <span data-ttu-id="512d3-133">例如，在管道处理中，可能需要在 BAM 中捕获特定数据，而不考虑管道是否回滚其事务。</span><span class="sxs-lookup"><span data-stu-id="512d3-133">For example, in a pipeline processing, you may want to capture the particular data in BAM regardless of whether the pipeline is rolling back its transaction.</span></span> <span data-ttu-id="512d3-134">特别是，您可能需要捕获有关管道处理期间多少消息失败或有多少重试的数据。</span><span class="sxs-lookup"><span data-stu-id="512d3-134">In particular, you may want capture data about how many messages failed or how many retries there were during pipeline processing.</span></span> <span data-ttu-id="512d3-135">若要在这种情况下捕获数据，应使用 BES。</span><span class="sxs-lookup"><span data-stu-id="512d3-135">To capture the data in this situation you should use BES.</span></span>  
  
 <span data-ttu-id="512d3-136">所有异步 EventStreams（BES、MES 和 OES）都首先在 BizTalk MessageBox 数据库中保留数据。</span><span class="sxs-lookup"><span data-stu-id="512d3-136">All the asynchronous EventStreams (BES, MES, and OES) persist data first in the BizTalk MessageBox database.</span></span> <span data-ttu-id="512d3-137">跟踪数据解码服务 (TDDS) 会定期处理这些数据，并将其持久化到 BAM 主导入数据库。</span><span class="sxs-lookup"><span data-stu-id="512d3-137">Periodically the data is processed and persisted to the BAM Primary Import database by the Tracking Data Decode Service (TDDS).</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="512d3-138">若要确保 EventStream 调用不会在 BizTalk 应用程序中产生瓶颈，建议您使用异步 API。</span><span class="sxs-lookup"><span data-stu-id="512d3-138">To ensure that EventStream calls do not create a bottleneck from a BizTalk application, we recommend that you use asynchronous APIs.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="512d3-139">本节内容</span><span class="sxs-lookup"><span data-stu-id="512d3-139">In This Section</span></span>  
  
-   [<span data-ttu-id="512d3-140">OrchestrationEventStream</span><span class="sxs-lookup"><span data-stu-id="512d3-140">OrchestrationEventStream</span></span>](../core/orchestrationeventstream.md)  
  
-   [<span data-ttu-id="512d3-141">消息传递的事件流</span><span class="sxs-lookup"><span data-stu-id="512d3-141">Messaging Event Streams</span></span>](../core/messaging-event-streams.md)