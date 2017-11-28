---
title: "低延迟方案 Optimizations2 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 19cd78ce-ad7d-4e4b-8188-a63d707905d5
caps.latest.revision: "9"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 009b1298e90b586830f062c8e884b88995f9e33f
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="low-latency-scenario-optimizations"></a><span data-ttu-id="979c8-102">低延迟方案优化</span><span class="sxs-lookup"><span data-stu-id="979c8-102">Low-Latency Scenario Optimizations</span></span>
<span data-ttu-id="979c8-103">默认情况下，BizTalk Server 将优化吞吐量，而不是低延迟。</span><span class="sxs-lookup"><span data-stu-id="979c8-103">By default, BizTalk Server is optimized for throughput rather than low-latency.</span></span> <span data-ttu-id="979c8-104">下列优化可以应用于 BizTalk Server 中，在要求降低的延迟的情况中。</span><span class="sxs-lookup"><span data-stu-id="979c8-104">The following optimizations can be applied to BizTalk Server in scenarios where reduced latency is required.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="979c8-105">这些优化将提高延迟，但可能在执行此操作对整体吞吐量一些成本。</span><span class="sxs-lookup"><span data-stu-id="979c8-105">These optimizations will improve latency, but may do so at some cost to overall throughput.</span></span>  
  
## <a name="increase-the-biztalk-server-host-internal-message-queue-size"></a><span data-ttu-id="979c8-106">增加的 BizTalk Server 主机内部消息队列大小</span><span class="sxs-lookup"><span data-stu-id="979c8-106">Increase the BizTalk Server host internal message queue size</span></span>  
 <span data-ttu-id="979c8-107">每个 BizTalk 主机有其自己的内部内存中队列。</span><span class="sxs-lookup"><span data-stu-id="979c8-107">Each BizTalk host has its own internal in-memory queue.</span></span> <span data-ttu-id="979c8-108">增加此队列从 100 到 10000，以提高性能的低延迟方案的默认值的大小。</span><span class="sxs-lookup"><span data-stu-id="979c8-108">Increase the size of this queue from the default value of 100 to 10000 to improve performance for a low-latency scenario.</span></span> <span data-ttu-id="979c8-109">有关修改的内部消息队列大小的值的详细信息，请参阅[如何修改资源基于限制设置](http://go.microsoft.com/fwlink/?LinkID=208366)(http://go.microsoft.com/fwlink/?LinkID=208366) BizTalk Server 文档中。</span><span class="sxs-lookup"><span data-stu-id="979c8-109">For more information about modifying the value of the internal message queue size, see [How to Modify Resource Based Throttling Settings](http://go.microsoft.com/fwlink/?LinkID=208366) (http://go.microsoft.com/fwlink/?LinkID=208366) in the BizTalk Server documentation.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="979c8-110">增加内部消息队列大小值将增加的主机实例使用的内存。</span><span class="sxs-lookup"><span data-stu-id="979c8-110">Increasing the internal message queue size value will increase the memory used by the host instance.</span></span>  
  
## <a name="increase-the-biztalk-server-host-in-process-messages"></a><span data-ttu-id="979c8-111">增加 BizTalk Server 主机进程内消息</span><span class="sxs-lookup"><span data-stu-id="979c8-111">Increase the BizTalk Server host in-process messages</span></span>  
 <span data-ttu-id="979c8-112">增加从默认值为 1000年到 10000 的进程内消息，以提高性能。</span><span class="sxs-lookup"><span data-stu-id="979c8-112">Increase the in-process messages from the default value of 1000 to 10,000 to improve performance.</span></span> <span data-ttu-id="979c8-113">有关修改在处理消息的值的详细信息，请参阅[如何修改默认的主机限制设置](http://go.microsoft.com/fwlink/?LinkID=208366)(http://go.microsoft.com/fwlink/?LinkID=208366) BizTalk Server 文档中。</span><span class="sxs-lookup"><span data-stu-id="979c8-113">For more information about modifying the value of the in-process messages, see [How to Modify the Default Host Throttling Settings](http://go.microsoft.com/fwlink/?LinkID=208366) (http://go.microsoft.com/fwlink/?LinkID=208366) in the BizTalk Server documentation.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="979c8-114">增加内部消息队列大小值将增加的主机实例使用的内存。</span><span class="sxs-lookup"><span data-stu-id="979c8-114">Increasing the internal message queue size value will increase the memory used by the host instance.</span></span>  
  
## <a name="optimize-orchestrations-for-low-latency"></a><span data-ttu-id="979c8-115">优化低延迟的业务的流程</span><span class="sxs-lookup"><span data-stu-id="979c8-115">Optimize orchestrations for low latency</span></span>  
 <span data-ttu-id="979c8-116">请遵循中的"有关优化为低延迟方案的业务流程的建议"部分建议[优化业务流程性能](../technical-guides/optimizing-orchestration-performance.md)。</span><span class="sxs-lookup"><span data-stu-id="979c8-116">Follow the recommendations in the “Recommendations for optimizing orchestrations for low latency scenarios” section of [Optimizing Orchestration Performance](../technical-guides/optimizing-orchestration-performance.md).</span></span>  
  
## <a name="configure-polling-intervals"></a><span data-ttu-id="979c8-117">配置轮询间隔</span><span class="sxs-lookup"><span data-stu-id="979c8-117">Configure polling intervals</span></span>  
 <span data-ttu-id="979c8-118">设置仪表板用于跨 BizTalk 组中配置的给定主机的轮询间隔。</span><span class="sxs-lookup"><span data-stu-id="979c8-118">Use the Settings Dashboard to configure the polling intervals of a given host, across the BizTalk Group.</span></span> <span data-ttu-id="979c8-119">若要更改轮询间隔：</span><span class="sxs-lookup"><span data-stu-id="979c8-119">To change Polling Intervals:</span></span>  
  
1.  <span data-ttu-id="979c8-120">在**BizTalk Server 管理控制台**，展开**BizTalk Server 管理**，右键单击**BizTalk 组**，然后单击**设置**.</span><span class="sxs-lookup"><span data-stu-id="979c8-120">In the **BizTalk Server Administration Console**, expand **BizTalk Server Administration**, right-click **BizTalk Group**, and then click **Settings**.</span></span>  
  
2.  <span data-ttu-id="979c8-121">在**BizTalk 设置仪表板**对话框中，在**主机**页，请在**常规**选项卡上，在**轮询间隔**，你会发现**消息**和**Orchestration**值。</span><span class="sxs-lookup"><span data-stu-id="979c8-121">In the **BizTalk Settings Dashboard** dialog box, on the **Hosts** page, on the **General** tab, under **Polling Intervals**, you will find the **Messaging** and **Orchestration** values.</span></span> <span data-ttu-id="979c8-122">默认情况下，这两个值设置为 500 毫秒。</span><span class="sxs-lookup"><span data-stu-id="979c8-122">By default, both these values are set to 500 milliseconds.</span></span>  
  
 <span data-ttu-id="979c8-123">下表列出了我们用于测试 BizTalk 进程内 64 位主机 （RxHost、 TxHost 和 PxHost） 上的轮询值。</span><span class="sxs-lookup"><span data-stu-id="979c8-123">The following table lists the polling values that we used for testing on the BizTalk in-process 64-bit Hosts (RxHost, TxHost and PxHost).</span></span> <span data-ttu-id="979c8-124">若要禁用轮询，可以将轮询间隔设置为一个非常大数字视为表中列出。</span><span class="sxs-lookup"><span data-stu-id="979c8-124">To disable polling, you can set the polling interval to a very big number as listed in the table.</span></span>  
  
|<span data-ttu-id="979c8-125">服务器主机</span><span class="sxs-lookup"><span data-stu-id="979c8-125">Server Hosts</span></span>|<span data-ttu-id="979c8-126">消息传送</span><span class="sxs-lookup"><span data-stu-id="979c8-126">Messaging</span></span>|<span data-ttu-id="979c8-127">业务流程</span><span class="sxs-lookup"><span data-stu-id="979c8-127">Orchestration</span></span>|  
|------------------|---------------|-------------------|  
|<span data-ttu-id="979c8-128">**RxHost**</span><span class="sxs-lookup"><span data-stu-id="979c8-128">**RxHost**</span></span><br /><br /> <span data-ttu-id="979c8-129">因为我们仅发布到 BizTalk 消息框通过单向传入消息接收位置、 RxHost 上不需要轮询 （接收主机）。</span><span class="sxs-lookup"><span data-stu-id="979c8-129">Because we are only publishing incoming messages to the BizTalk message box through a one-way receive location, polling is not required on the RxHost (receive host).</span></span>|<span data-ttu-id="979c8-130">200000</span><span class="sxs-lookup"><span data-stu-id="979c8-130">200000</span></span>|<span data-ttu-id="979c8-131">200000</span><span class="sxs-lookup"><span data-stu-id="979c8-131">200000</span></span>|  
|<span data-ttu-id="979c8-132">**TxHost**</span><span class="sxs-lookup"><span data-stu-id="979c8-132">**TxHost**</span></span><br /><br /> <span data-ttu-id="979c8-133">因为我们仅收到了消息传送实例从 BizTalk 消息框中，业务流程轮询 TxHost （发送主机） 上不需要。</span><span class="sxs-lookup"><span data-stu-id="979c8-133">Because we are only receiving messaging instances from the BizTalk message box, orchestration polling is not required on the TxHost (send host).</span></span>|<span data-ttu-id="979c8-134">50</span><span class="sxs-lookup"><span data-stu-id="979c8-134">50</span></span>|<span data-ttu-id="979c8-135">200000</span><span class="sxs-lookup"><span data-stu-id="979c8-135">200000</span></span>|  
|<span data-ttu-id="979c8-136">**PxHost**</span><span class="sxs-lookup"><span data-stu-id="979c8-136">**PxHost**</span></span><br /><br /> <span data-ttu-id="979c8-137">因为我们仅收到了业务流程实例从 BizTalk 消息框中，消息传送轮询上不需要 PxHost （处理主机）。</span><span class="sxs-lookup"><span data-stu-id="979c8-137">Because we are only receiving orchestration instances from the BizTalk message box, messaging polling is not required on the PxHost (Processing host).</span></span>|<span data-ttu-id="979c8-138">200000</span><span class="sxs-lookup"><span data-stu-id="979c8-138">200000</span></span>|<span data-ttu-id="979c8-139">50</span><span class="sxs-lookup"><span data-stu-id="979c8-139">50</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="979c8-140">另请参阅</span><span class="sxs-lookup"><span data-stu-id="979c8-140">See Also</span></span>  
 [<span data-ttu-id="979c8-141">优化 BizTalk Server 性能</span><span class="sxs-lookup"><span data-stu-id="979c8-141">Optimizing BizTalk Server Performance</span></span>](../technical-guides/optimizing-biztalk-server-performance.md)