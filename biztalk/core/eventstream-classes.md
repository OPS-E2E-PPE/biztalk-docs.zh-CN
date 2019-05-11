---
title: EventStream 类 |Microsoft Docs
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
ms.openlocfilehash: ba599c008c571af520dbc9b7919157371e32750f
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65388319"
---
# <a name="eventstream-classes"></a><span data-ttu-id="f49b5-102">EventStream 类</span><span class="sxs-lookup"><span data-stu-id="f49b5-102">EventStream Classes</span></span>
<span data-ttu-id="f49b5-103">用于 BAM 的 EventStream Api 驻留在 Microsoft.BizTalk.BAM.EventObservation 命名空间。</span><span class="sxs-lookup"><span data-stu-id="f49b5-103">The EventStream APIs for BAM reside in the Microsoft.BizTalk.BAM.EventObservation namespace.</span></span> <span data-ttu-id="f49b5-104">若要针对 Api 进行编码，必须在开发计算机上安装以下 Dll:</span><span class="sxs-lookup"><span data-stu-id="f49b5-104">To code against the APIs, you must install the following DLLs on your development computer:</span></span>  
  
- <span data-ttu-id="f49b5-105">Microsoft.BizTalk.BAM.EventObservation.dll</span><span class="sxs-lookup"><span data-stu-id="f49b5-105">Microsoft.BizTalk.BAM.EventObservation.dll</span></span>  
  
- <span data-ttu-id="f49b5-106">Microsoft.Biztalk.BAM.Xlangs.dll:业务流程事件流编码时需要此 DLL。</span><span class="sxs-lookup"><span data-stu-id="f49b5-106">Microsoft.Biztalk.BAM.Xlangs.dll: This DLL is required when coding for Orchestration event streams.</span></span>  
  
- <span data-ttu-id="f49b5-107">Microsoft.BizTalk.Pipeline.dll:将编码管道上下文用于消息传送事件流时需要此 DLL。</span><span class="sxs-lookup"><span data-stu-id="f49b5-107">Microsoft.BizTalk.Pipeline.dll: This DLL required when using coding pipeline contexts for Messaging event streams.</span></span>  
  
  <span data-ttu-id="f49b5-108">将 DLL 添加到项目引用和命名空间在代码中包含以下 using 语句：</span><span class="sxs-lookup"><span data-stu-id="f49b5-108">Add the DLL to your project reference and include the namespace in your code with the following using statement:</span></span>  
  
```  
using Microsoft.BizTalk.Bam.EventObservation;  
```  
  
 <span data-ttu-id="f49b5-109">**类**</span><span class="sxs-lookup"><span data-stu-id="f49b5-109">**Classes**</span></span>  
  
|<span data-ttu-id="f49b5-110">“属性”</span><span class="sxs-lookup"><span data-stu-id="f49b5-110">Name</span></span>|<span data-ttu-id="f49b5-111">Description</span><span class="sxs-lookup"><span data-stu-id="f49b5-111">Description</span></span>|  
|----------|-----------------|  
|<span data-ttu-id="f49b5-112">DirectEventStream (DES)</span><span class="sxs-lookup"><span data-stu-id="f49b5-112">DirectEventStream (DES)</span></span>|<span data-ttu-id="f49b5-113">同步，无延迟</span><span class="sxs-lookup"><span data-stu-id="f49b5-113">Synchronous, no latency</span></span>|  
|<span data-ttu-id="f49b5-114">BufferedEventStream (BES)</span><span class="sxs-lookup"><span data-stu-id="f49b5-114">BufferedEventStream (BES)</span></span>|<span data-ttu-id="f49b5-115">异步、 高吞吐量，一定程度的延迟</span><span class="sxs-lookup"><span data-stu-id="f49b5-115">Asynchronous, high throughput, some latency</span></span>|  
|<span data-ttu-id="f49b5-116">OrchestrationEventStream (OES)</span><span class="sxs-lookup"><span data-stu-id="f49b5-116">OrchestrationEventStream (OES)</span></span>|<span data-ttu-id="f49b5-117">异步，参与 BizTalk 业务流程事务</span><span class="sxs-lookup"><span data-stu-id="f49b5-117">Asynchronous, participates in BizTalk orchestration transactions</span></span>|  
|<span data-ttu-id="f49b5-118">IPipelineContext 接口</span><span class="sxs-lookup"><span data-stu-id="f49b5-118">IPipelineContext Interface</span></span>|<span data-ttu-id="f49b5-119">异步，参与 BizTalk Server 管道事务。</span><span class="sxs-lookup"><span data-stu-id="f49b5-119">Asynchronous, participates in BizTalk Server pipeline transactions.</span></span> <span data-ttu-id="f49b5-120">用于创建消息传送事件流 (MES)。</span><span class="sxs-lookup"><span data-stu-id="f49b5-120">Used to create Messaging Event Streams (MES).</span></span>|  
  
 <span data-ttu-id="f49b5-121">应选择 API 基于以下因素：</span><span class="sxs-lookup"><span data-stu-id="f49b5-121">You should choose an API based on the following factors:</span></span>  
  
- <span data-ttu-id="f49b5-122">如果您关注的问题的延迟，请选择的 DES，其中数据以同步方式保存到 BAM 主导入数据库。</span><span class="sxs-lookup"><span data-stu-id="f49b5-122">If your concern is latency, choose DES, where data is persisted synchronously to the BAM Primary Import database.</span></span> <span data-ttu-id="f49b5-123">除 DES 之外，所有其他 EventStream 类是异步的具有一些滞后时间。</span><span class="sxs-lookup"><span data-stu-id="f49b5-123">Except for DES, all other EventStream classes are asynchronous and have some latency.</span></span> <span data-ttu-id="f49b5-124">数据首先将暂留到 MessageBox，并随后由 TDDS 将数据移到 BAMPrimaryImport 数据库的处理。</span><span class="sxs-lookup"><span data-stu-id="f49b5-124">The data is first persisted to MessageBox and subsequently processed by TDDS which moves data into the BAMPrimaryImport database.</span></span>  
  
- <span data-ttu-id="f49b5-125">如果您关注的问题的性能和事件插入的吞吐量，请选择异步 API。</span><span class="sxs-lookup"><span data-stu-id="f49b5-125">If your concern is performance and throughput of event insertion, choose an asynchronous API.</span></span>  
  
- <span data-ttu-id="f49b5-126">如果你正在编写不具有的计算机运行的应用程序安装 BizTalk Server，请使用 DES 和 BES。</span><span class="sxs-lookup"><span data-stu-id="f49b5-126">If you are writing an application that runs on a computer that does not have BizTalk Server installed, use DES and BES.</span></span> <span data-ttu-id="f49b5-127">（换句话说，这些 Api 可在非 BizTalk 应用程序。）</span><span class="sxs-lookup"><span data-stu-id="f49b5-127">(In other words, these APIs can be used in non-BizTalk applications.)</span></span>  
  
- <span data-ttu-id="f49b5-128">如果你的应用程序在其安装 BizTalk Server 的计算机上运行，使用 MES 和 OES。</span><span class="sxs-lookup"><span data-stu-id="f49b5-128">If your application runs on a computer on which BizTalk Server is installed, use MES and OES.</span></span> <span data-ttu-id="f49b5-129">（这些都提供 Api 只能从 BizTalk 应用程序。）</span><span class="sxs-lookup"><span data-stu-id="f49b5-129">(These APIs are available only from BizTalk applications.)</span></span>  
  
  -   <span data-ttu-id="f49b5-130">如果您希望 BAM 事件持久化与管道事务保持同步，则应使用消息传送事件 Stream。</span><span class="sxs-lookup"><span data-stu-id="f49b5-130">If you want BAM event persistence to be in sync with pipeline transaction, you should use a Messaging Event Stream.</span></span>  
  
  -   <span data-ttu-id="f49b5-131">OES 等效于 MES，但对 BizTalk 业务流程。</span><span class="sxs-lookup"><span data-stu-id="f49b5-131">OES is the equivalent of MES but for BizTalk orchestrations.</span></span>  
  
  <span data-ttu-id="f49b5-132">有在其中你可能想要混合使用 EventStream 类型的方案。</span><span class="sxs-lookup"><span data-stu-id="f49b5-132">There are scenarios in which you may want to mix EventStream types.</span></span> <span data-ttu-id="f49b5-133">例如，在管道处理中，你可能想要捕获特定数据在 BAM 中的，而不考虑是否管道正在回滚其事务。</span><span class="sxs-lookup"><span data-stu-id="f49b5-133">For example, in a pipeline processing, you may want to capture the particular data in BAM regardless of whether the pipeline is rolling back its transaction.</span></span> <span data-ttu-id="f49b5-134">具体而言，您可能希望捕获有关失败的消息数的数据或在管道处理过程中已有多少重试。</span><span class="sxs-lookup"><span data-stu-id="f49b5-134">In particular, you may want capture data about how many messages failed or how many retries there were during pipeline processing.</span></span> <span data-ttu-id="f49b5-135">若要捕获的数据在此情况下应使用 BES。</span><span class="sxs-lookup"><span data-stu-id="f49b5-135">To capture the data in this situation you should use BES.</span></span>  
  
  <span data-ttu-id="f49b5-136">所有异步 EventStreams （BES、 MES 和 OES） 首先在 BizTalk MessageBox 数据库中保留数据。</span><span class="sxs-lookup"><span data-stu-id="f49b5-136">All the asynchronous EventStreams (BES, MES, and OES) persist data first in the BizTalk MessageBox database.</span></span> <span data-ttu-id="f49b5-137">跟踪数据解码服务 (TDDS) 会定期处理这些数据，并将其持久化到 BAM 主导入数据库。</span><span class="sxs-lookup"><span data-stu-id="f49b5-137">Periodically the data is processed and persisted to the BAM Primary Import database by the Tracking Data Decode Service (TDDS).</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="f49b5-138">若要确保 EventStream 调用不执行操作的 BizTalk 应用程序中产生瓶颈，我们建议使用异步 Api。</span><span class="sxs-lookup"><span data-stu-id="f49b5-138">To ensure that EventStream calls do not create a bottleneck from a BizTalk application, we recommend that you use asynchronous APIs.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="f49b5-139">本节内容</span><span class="sxs-lookup"><span data-stu-id="f49b5-139">In This Section</span></span>  
  
-   [<span data-ttu-id="f49b5-140">OrchestrationEventStream</span><span class="sxs-lookup"><span data-stu-id="f49b5-140">OrchestrationEventStream</span></span>](../core/orchestrationeventstream.md)  
  
-   [<span data-ttu-id="f49b5-141">消息传送事件流</span><span class="sxs-lookup"><span data-stu-id="f49b5-141">Messaging Event Streams</span></span>](../core/messaging-event-streams.md)