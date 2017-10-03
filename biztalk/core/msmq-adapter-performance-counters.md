---
title: "MSMQ 适配器性能计数器 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: ab8b0342-c6c2-4113-ae54-359df28e5d30
caps.latest.revision: "10"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: f346feea5f3c651d466f40fc7c67507292f585a3
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="msmq-adapter-performance-counters"></a><span data-ttu-id="87791-102">MSMQ 适配器性能计数器</span><span class="sxs-lookup"><span data-stu-id="87791-102">MSMQ Adapter Performance Counters</span></span>
<span data-ttu-id="87791-103">使用性能计数器可以监视服务在站点或系统上执行的工作的特定方面。</span><span class="sxs-lookup"><span data-stu-id="87791-103">Performance counters allow you to monitor specific aspects of work performed on the site or system by service.</span></span> <span data-ttu-id="87791-104">性能计数器能够帮助您标识和解决有关服务器性能的问题。</span><span class="sxs-lookup"><span data-stu-id="87791-104">Performance counters can help you identify and troubleshoot server performance issues.</span></span>  
  
 <span data-ttu-id="87791-105">以下性能计数器进行访问每个主机实例下**BizTalk:MSMQ 接收适配器**和**BizTalk:MSMQ 发送适配器**性能对象类别：</span><span class="sxs-lookup"><span data-stu-id="87791-105">The following performance counters are accessible for each host instance under the **BizTalk:MSMQ Receive Adapter** and the **BizTalk:MSMQ Send Adapter** performance object categories:</span></span>  
  
|<span data-ttu-id="87791-106">**类别**</span><span class="sxs-lookup"><span data-stu-id="87791-106">**Category**</span></span>|<span data-ttu-id="87791-107">**计数器**</span><span class="sxs-lookup"><span data-stu-id="87791-107">**Counter**</span></span>|<span data-ttu-id="87791-108">**Description**</span><span class="sxs-lookup"><span data-stu-id="87791-108">**Description**</span></span>|  
|------------------|-----------------|---------------------|  
|<span data-ttu-id="87791-109">BizTalk:MSMQ Receive Adapter</span><span class="sxs-lookup"><span data-stu-id="87791-109">BizTalk:MSMQ Receive Adapter</span></span>|<span data-ttu-id="87791-110">Bytes received</span><span class="sxs-lookup"><span data-stu-id="87791-110">Bytes received</span></span>|<span data-ttu-id="87791-111">MSMQ 接收适配器接收到的字节总数。</span><span class="sxs-lookup"><span data-stu-id="87791-111">Total number of bytes received by the MSMQ receive adapter.</span></span> <span data-ttu-id="87791-112">MSMQ 接收适配器从源队列中完整读取一个消息后，该计数器的值才会增加。</span><span class="sxs-lookup"><span data-stu-id="87791-112">The counter is incremented after a message is completely read by the MSMQ receive adapter from the source queue.</span></span>|  
||<span data-ttu-id="87791-113">Bytes received/Sec</span><span class="sxs-lookup"><span data-stu-id="87791-113">Bytes received/Sec</span></span>|<span data-ttu-id="87791-114">MSMQ 接收适配器每秒接收到的字节数。</span><span class="sxs-lookup"><span data-stu-id="87791-114">Number of bytes received by the MSMQ receive adapter per second.</span></span> <span data-ttu-id="87791-115">该计数器只计入 MSMQ 接收适配器从源队列中完整读取的消息。</span><span class="sxs-lookup"><span data-stu-id="87791-115">The counter applies only to messages that have been completely read by the MSMQ receive adapter from the source queue.</span></span>|  
||<span data-ttu-id="87791-116">收到的消息</span><span class="sxs-lookup"><span data-stu-id="87791-116">Messages received</span></span>|<span data-ttu-id="87791-117">MSMQ 接收适配器接收到的消息总数。</span><span class="sxs-lookup"><span data-stu-id="87791-117">Total number of messages received by the MSMQ receive adapter.</span></span> <span data-ttu-id="87791-118">MSMQ 接收适配器从源队列中完整读取一个消息后，该计数器的值才会增加。</span><span class="sxs-lookup"><span data-stu-id="87791-118">The counter is incremented after a message is completely read by the MSMQ receive adapter from the source queue.</span></span>|  
||<span data-ttu-id="87791-119">每秒接收的消息数</span><span class="sxs-lookup"><span data-stu-id="87791-119">Messages received/Sec</span></span>|<span data-ttu-id="87791-120">MSMQ 接收适配器每秒接收到的消息数。</span><span class="sxs-lookup"><span data-stu-id="87791-120">Number of messages received by the MSMQ receive adapter per second.</span></span> <span data-ttu-id="87791-121">该计数器只计入 MSMQ 接收适配器从源队列中完整读取的消息。</span><span class="sxs-lookup"><span data-stu-id="87791-121">The counter applies only to messages that have been completely read by the MSMQ receive adapter from the source queue.</span></span>|  
|<span data-ttu-id="87791-122">BizTalk:MSMQ Send Adapter</span><span class="sxs-lookup"><span data-stu-id="87791-122">BizTalk:MSMQ Send Adapter</span></span>|<span data-ttu-id="87791-123">Bytes sent</span><span class="sxs-lookup"><span data-stu-id="87791-123">Bytes sent</span></span>|<span data-ttu-id="87791-124">MSMQ 发送适配器发送的字节总数。</span><span class="sxs-lookup"><span data-stu-id="87791-124">Total number of bytes sent by the MSMQ send adapter.</span></span> <span data-ttu-id="87791-125">该计数器只计入已到达目标队列的消息。</span><span class="sxs-lookup"><span data-stu-id="87791-125">The counter is incremented only for messages that have reached the destination queue.</span></span>|  
||<span data-ttu-id="87791-126">Bytes sent/Sec</span><span class="sxs-lookup"><span data-stu-id="87791-126">Bytes sent/Sec</span></span>|<span data-ttu-id="87791-127">MSMQ 发送适配器每秒发送的字节数。</span><span class="sxs-lookup"><span data-stu-id="87791-127">Number of bytes sent by the MSMQ send adapter per second.</span></span> <span data-ttu-id="87791-128">计数器仅适用于已到达目标队列的消息。</span><span class="sxs-lookup"><span data-stu-id="87791-128">The counter applies only to messages that have reached the destination queue.</span></span>|  
||<span data-ttu-id="87791-129">发送的消息</span><span class="sxs-lookup"><span data-stu-id="87791-129">Messages sent</span></span>|<span data-ttu-id="87791-130">MSMQ 发送适配器发送的消息总数。</span><span class="sxs-lookup"><span data-stu-id="87791-130">Total number of messages sent by the MSMQ send adapter.</span></span> <span data-ttu-id="87791-131">该计数器只计入已到达目标队列的消息。</span><span class="sxs-lookup"><span data-stu-id="87791-131">The counter is incremented only for messages that have reached the destination queue.</span></span>|  
||<span data-ttu-id="87791-132">每秒发送的消息数</span><span class="sxs-lookup"><span data-stu-id="87791-132">Messages sent/Sec</span></span>|<span data-ttu-id="87791-133">MSMQ 发送适配器每秒发送的消息数。</span><span class="sxs-lookup"><span data-stu-id="87791-133">Number of messages sent by the MSMQ send adapter per second.</span></span> <span data-ttu-id="87791-134">计数器仅适用于已到达目标队列的消息。</span><span class="sxs-lookup"><span data-stu-id="87791-134">The counter applies only to messages that have reached the destination queue.</span></span>|  
  
## <a name="to-access-performance-counters"></a><span data-ttu-id="87791-135">访问性能计数器</span><span class="sxs-lookup"><span data-stu-id="87791-135">To access performance counters</span></span>  
 <span data-ttu-id="87791-136">依照下述步骤访问性能计数器。</span><span class="sxs-lookup"><span data-stu-id="87791-136">Use the following steps to access the performance counters.</span></span>  
  
#### <a name="if-you-are-using-windows-2008"></a><span data-ttu-id="87791-137">如果您使用的是 Windows 2008</span><span class="sxs-lookup"><span data-stu-id="87791-137">If you are using Windows 2008</span></span>  
  
1.  <span data-ttu-id="87791-138">单击**启动**，指向**管理工具**，然后单击**性能监视器**。</span><span class="sxs-lookup"><span data-stu-id="87791-138">Click **Start**, point to **Administrative Tools**, and then click **Performance Monitor**.</span></span>  
  
2.  <span data-ttu-id="87791-139">在**性能监视器**对话框框中，展开**监视工具**，选择**性能监视器**，然后单击**添加**。</span><span class="sxs-lookup"><span data-stu-id="87791-139">In the **Performance Monitor** dialog box, expand **Monitoring Tools**, select **Performance Monitor**, and then click **Add**.</span></span>  
  
3.  <span data-ttu-id="87791-140">在**添加计数器**对话框中，从**可用计数器**列表中，展开**BizTalk:MSMQ**性能计数器对象，然后选择要监视的计数器</span><span class="sxs-lookup"><span data-stu-id="87791-140">In the **Add Counters** dialog box, from the **Available Counters** list, expand the **BizTalk:MSMQ** performance counter object and select the counters to be monitored</span></span>  
  
4.  <span data-ttu-id="87791-141">在**实例的所选对象**列表中，选择要监视的所选计数器，然后单击的特定实例**添加**。</span><span class="sxs-lookup"><span data-stu-id="87791-141">In the **Instances of Selected object** list, select the specific instances to be monitored for the selected counters and then click **Add**.</span></span>  <span data-ttu-id="87791-142">若要选择的所有可用的计数器实例，选择\<**所有实例**>。</span><span class="sxs-lookup"><span data-stu-id="87791-142">To select all available counter instances, select \<**All instances**>.</span></span>  
  
5.  <span data-ttu-id="87791-143">添加计数器后, 单击**确定**。</span><span class="sxs-lookup"><span data-stu-id="87791-143">After adding the counters, click **OK**.</span></span>  
  
     <span data-ttu-id="87791-144">所选的性能计数器显示在**性能监视器**屏幕。</span><span class="sxs-lookup"><span data-stu-id="87791-144">The selected performance counters appear on the **Performance Monitor** screen.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="87791-145">另请参阅</span><span class="sxs-lookup"><span data-stu-id="87791-145">See Also</span></span>  
 <span data-ttu-id="87791-146">[使用 MSMQ LoadGen 2007](../core/using-loadgen-2007-with-msmq.md) </span><span class="sxs-lookup"><span data-stu-id="87791-146">[Using LoadGen 2007 with MSMQ](../core/using-loadgen-2007-with-msmq.md) </span></span>  
 [<span data-ttu-id="87791-147">优化性能的 MSMQ 适配器</span><span class="sxs-lookup"><span data-stu-id="87791-147">Optimizing Performance of the MSMQ Adapter</span></span>](../core/optimizing-performance-of-the-msmq-adapter.md)