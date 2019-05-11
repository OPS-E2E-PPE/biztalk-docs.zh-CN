---
title: MSMQ 适配器性能计数器 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: ab8b0342-c6c2-4113-ae54-359df28e5d30
caps.latest.revision: 10
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 11214cd0698ac2d158523524f3e9cfdc59946cf5
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65263661"
---
# <a name="msmq-adapter-performance-counters"></a><span data-ttu-id="545c1-102">MSMQ 适配器性能计数器</span><span class="sxs-lookup"><span data-stu-id="545c1-102">MSMQ Adapter Performance Counters</span></span>
<span data-ttu-id="545c1-103">性能计数器允许你监视的工作上的站点或系统服务执行的特定方面。</span><span class="sxs-lookup"><span data-stu-id="545c1-103">Performance counters allow you to monitor specific aspects of work performed on the site or system by service.</span></span> <span data-ttu-id="545c1-104">性能计数器可以帮助您确定和解决服务器性能问题。</span><span class="sxs-lookup"><span data-stu-id="545c1-104">Performance counters can help you identify and troubleshoot server performance issues.</span></span>  
  
 <span data-ttu-id="545c1-105">以下性能计数器都可以访问每个主机实例下**biztalk: Msmq Receive Adapter**并**biztalk: Msmq Send Adapter**性能对象类别：</span><span class="sxs-lookup"><span data-stu-id="545c1-105">The following performance counters are accessible for each host instance under the **BizTalk:MSMQ Receive Adapter** and the **BizTalk:MSMQ Send Adapter** performance object categories:</span></span>  
  
|<span data-ttu-id="545c1-106">**类别**</span><span class="sxs-lookup"><span data-stu-id="545c1-106">**Category**</span></span>|<span data-ttu-id="545c1-107">**计数器**</span><span class="sxs-lookup"><span data-stu-id="545c1-107">**Counter**</span></span>|<span data-ttu-id="545c1-108">**说明**</span><span class="sxs-lookup"><span data-stu-id="545c1-108">**Description**</span></span>|  
|------------------|-----------------|---------------------|  
|<span data-ttu-id="545c1-109">Biztalk: Msmq 接收适配器</span><span class="sxs-lookup"><span data-stu-id="545c1-109">BizTalk:MSMQ Receive Adapter</span></span>|<span data-ttu-id="545c1-110">接收的字节数</span><span class="sxs-lookup"><span data-stu-id="545c1-110">Bytes received</span></span>|<span data-ttu-id="545c1-111">接收适配器的 msmq 接收的字节总数。</span><span class="sxs-lookup"><span data-stu-id="545c1-111">Total number of bytes received by the MSMQ receive adapter.</span></span> <span data-ttu-id="545c1-112">此计数器递增后一条消息完全读取的 MSMQ 接收适配器从源队列。</span><span class="sxs-lookup"><span data-stu-id="545c1-112">The counter is incremented after a message is completely read by the MSMQ receive adapter from the source queue.</span></span>|  
||<span data-ttu-id="545c1-113">接收的字节数/秒</span><span class="sxs-lookup"><span data-stu-id="545c1-113">Bytes received/Sec</span></span>|<span data-ttu-id="545c1-114">Msmq 接收的字节数接收适配器每秒。</span><span class="sxs-lookup"><span data-stu-id="545c1-114">Number of bytes received by the MSMQ receive adapter per second.</span></span> <span data-ttu-id="545c1-115">计数器只计入消息已完全读取的 MSMQ 接收适配器从源队列。</span><span class="sxs-lookup"><span data-stu-id="545c1-115">The counter applies only to messages that have been completely read by the MSMQ receive adapter from the source queue.</span></span>|  
||<span data-ttu-id="545c1-116">接收的消息</span><span class="sxs-lookup"><span data-stu-id="545c1-116">Messages received</span></span>|<span data-ttu-id="545c1-117">接收适配器接收到 MSMQ 的消息的总数。</span><span class="sxs-lookup"><span data-stu-id="545c1-117">Total number of messages received by the MSMQ receive adapter.</span></span> <span data-ttu-id="545c1-118">此计数器递增后一条消息完全读取的 MSMQ 接收适配器从源队列。</span><span class="sxs-lookup"><span data-stu-id="545c1-118">The counter is incremented after a message is completely read by the MSMQ receive adapter from the source queue.</span></span>|  
||<span data-ttu-id="545c1-119">收到的消息数/秒</span><span class="sxs-lookup"><span data-stu-id="545c1-119">Messages received/Sec</span></span>|<span data-ttu-id="545c1-120">适配器每秒接收的 msmq 接收的消息数。</span><span class="sxs-lookup"><span data-stu-id="545c1-120">Number of messages received by the MSMQ receive adapter per second.</span></span> <span data-ttu-id="545c1-121">计数器只计入消息已完全读取的 MSMQ 接收适配器从源队列。</span><span class="sxs-lookup"><span data-stu-id="545c1-121">The counter applies only to messages that have been completely read by the MSMQ receive adapter from the source queue.</span></span>|  
|<span data-ttu-id="545c1-122">Biztalk: Msmq 发送适配器</span><span class="sxs-lookup"><span data-stu-id="545c1-122">BizTalk:MSMQ Send Adapter</span></span>|<span data-ttu-id="545c1-123">发送的字节数</span><span class="sxs-lookup"><span data-stu-id="545c1-123">Bytes sent</span></span>|<span data-ttu-id="545c1-124">发送适配器通过 MSMQ 发送的字节总数。</span><span class="sxs-lookup"><span data-stu-id="545c1-124">Total number of bytes sent by the MSMQ send adapter.</span></span> <span data-ttu-id="545c1-125">仅对已到达目标队列的消息是增加计数器的数值。</span><span class="sxs-lookup"><span data-stu-id="545c1-125">The counter is incremented only for messages that have reached the destination queue.</span></span>|  
||<span data-ttu-id="545c1-126">发送的字节数/秒</span><span class="sxs-lookup"><span data-stu-id="545c1-126">Bytes sent/Sec</span></span>|<span data-ttu-id="545c1-127">适配器每秒发送的 msmq 发送的字节数。</span><span class="sxs-lookup"><span data-stu-id="545c1-127">Number of bytes sent by the MSMQ send adapter per second.</span></span> <span data-ttu-id="545c1-128">计数器仅应用于已到达目标队列的消息。</span><span class="sxs-lookup"><span data-stu-id="545c1-128">The counter applies only to messages that have reached the destination queue.</span></span>|  
||<span data-ttu-id="545c1-129">发送的消息</span><span class="sxs-lookup"><span data-stu-id="545c1-129">Messages sent</span></span>|<span data-ttu-id="545c1-130">发送适配器发送的 MSMQ 消息的总数。</span><span class="sxs-lookup"><span data-stu-id="545c1-130">Total number of messages sent by the MSMQ send adapter.</span></span> <span data-ttu-id="545c1-131">仅对已到达目标队列的消息是增加计数器的数值。</span><span class="sxs-lookup"><span data-stu-id="545c1-131">The counter is incremented only for messages that have reached the destination queue.</span></span>|  
||<span data-ttu-id="545c1-132">发送的消息数/秒</span><span class="sxs-lookup"><span data-stu-id="545c1-132">Messages sent/Sec</span></span>|<span data-ttu-id="545c1-133">适配器每秒发送的 msmq 发送的消息数。</span><span class="sxs-lookup"><span data-stu-id="545c1-133">Number of messages sent by the MSMQ send adapter per second.</span></span> <span data-ttu-id="545c1-134">计数器仅应用于已到达目标队列的消息。</span><span class="sxs-lookup"><span data-stu-id="545c1-134">The counter applies only to messages that have reached the destination queue.</span></span>|  
  
## <a name="to-access-performance-counters"></a><span data-ttu-id="545c1-135">若要访问性能计数器</span><span class="sxs-lookup"><span data-stu-id="545c1-135">To access performance counters</span></span>  
 <span data-ttu-id="545c1-136">使用以下步骤访问性能计数器。</span><span class="sxs-lookup"><span data-stu-id="545c1-136">Use the following steps to access the performance counters.</span></span>  
  
#### <a name="if-you-are-using-windows-2008"></a><span data-ttu-id="545c1-137">如果您使用的 Windows 2008</span><span class="sxs-lookup"><span data-stu-id="545c1-137">If you are using Windows 2008</span></span>  
  
1.  <span data-ttu-id="545c1-138">单击**启动**，依次指向**管理工具**，然后单击**性能监视器**。</span><span class="sxs-lookup"><span data-stu-id="545c1-138">Click **Start**, point to **Administrative Tools**, and then click **Performance Monitor**.</span></span>  
  
2.  <span data-ttu-id="545c1-139">在中**性能监视器**对话框框中，展开**监视工具**，选择**性能监视器**，然后单击**添加**。</span><span class="sxs-lookup"><span data-stu-id="545c1-139">In the **Performance Monitor** dialog box, expand **Monitoring Tools**, select **Performance Monitor**, and then click **Add**.</span></span>  
  
3.  <span data-ttu-id="545c1-140">在中**添加计数器**对话框中，从**可用的计数器**列表中，展开**biztalk: Msmq**性能计数器对象，然后选择要监视的计数器</span><span class="sxs-lookup"><span data-stu-id="545c1-140">In the **Add Counters** dialog box, from the **Available Counters** list, expand the **BizTalk:MSMQ** performance counter object and select the counters to be monitored</span></span>  
  
4.  <span data-ttu-id="545c1-141">在中**选定对象的实例**列表中，选择要监视的所选的计数器，然后单击的特定实例**添加**。</span><span class="sxs-lookup"><span data-stu-id="545c1-141">In the **Instances of Selected object** list, select the specific instances to be monitored for the selected counters and then click **Add**.</span></span>  <span data-ttu-id="545c1-142">若要选择的所有可用的计数器实例，请选择\<**所有实例**\>。</span><span class="sxs-lookup"><span data-stu-id="545c1-142">To select all available counter instances, select \<**All instances**\>.</span></span>  
  
5.  <span data-ttu-id="545c1-143">添加计数器之后, 单击**确定**。</span><span class="sxs-lookup"><span data-stu-id="545c1-143">After adding the counters, click **OK**.</span></span>  
  
     <span data-ttu-id="545c1-144">所选的性能计数器随即显示在**性能监视器**屏幕。</span><span class="sxs-lookup"><span data-stu-id="545c1-144">The selected performance counters appear on the **Performance Monitor** screen.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="545c1-145">请参阅</span><span class="sxs-lookup"><span data-stu-id="545c1-145">See Also</span></span>  
 <span data-ttu-id="545c1-146">[将 LoadGen 2007 与 MSMQ 使用](../core/using-loadgen-2007-with-msmq.md) </span><span class="sxs-lookup"><span data-stu-id="545c1-146">[Using LoadGen 2007 with MSMQ](../core/using-loadgen-2007-with-msmq.md) </span></span>  
 [<span data-ttu-id="545c1-147">优化 MSMQ 适配器的性能</span><span class="sxs-lookup"><span data-stu-id="545c1-147">Optimizing Performance of the MSMQ Adapter</span></span>](../core/optimizing-performance-of-the-msmq-adapter.md)