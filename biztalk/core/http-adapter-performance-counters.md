---
title: HTTP 适配器性能计数器 |Microsoft 文档
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: d85473f1-1d67-4990-8d2f-fc7fe0e80108
caps.latest.revision: 10
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: ff9fcc2530484abd7c5bdbf1997e3d294afdb3dc
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/28/2017
ms.locfileid: "25973291"
---
# <a name="http-adapter-performance-counters"></a><span data-ttu-id="1d200-102">HTTP 适配器性能计数器</span><span class="sxs-lookup"><span data-stu-id="1d200-102">HTTP Adapter Performance Counters</span></span>
<span data-ttu-id="1d200-103">使用性能计数器可以监视服务在站点或系统上执行的工作的特定方面。</span><span class="sxs-lookup"><span data-stu-id="1d200-103">Performance counters allow you to monitor specific aspects of work performed on the site or system by service.</span></span> <span data-ttu-id="1d200-104">性能计数器能够帮助您标识和解决有关服务器性能的问题。</span><span class="sxs-lookup"><span data-stu-id="1d200-104">Performance counters can help you identify and troubleshoot server performance issues.</span></span>  
  
 <span data-ttu-id="1d200-105">以下性能计数器进行访问每个主机实例下**BizTalk:HTTP 接收适配器**和**BizTalk:HTTP 发送适配器**性能对象类别：</span><span class="sxs-lookup"><span data-stu-id="1d200-105">The following performance counters are accessible for each host instance under the **BizTalk:HTTP Receive Adapter** and the **BizTalk:HTTP Send Adapter** performance object categories:</span></span>  
  
|<span data-ttu-id="1d200-106">**类别**</span><span class="sxs-lookup"><span data-stu-id="1d200-106">**Category**</span></span>|<span data-ttu-id="1d200-107">**计数器**</span><span class="sxs-lookup"><span data-stu-id="1d200-107">**Counter**</span></span>|<span data-ttu-id="1d200-108">**Description**</span><span class="sxs-lookup"><span data-stu-id="1d200-108">**Description**</span></span>|  
|------------------|-----------------|---------------------|  
|<span data-ttu-id="1d200-109">BizTalk:HTTP Receive Adapter</span><span class="sxs-lookup"><span data-stu-id="1d200-109">BizTalk:HTTP Receive Adapter</span></span>|<span data-ttu-id="1d200-110">内存队列大小</span><span class="sxs-lookup"><span data-stu-id="1d200-110">Memory queue size</span></span>|<span data-ttu-id="1d200-111">HTTP 接收适配器的内部内存队列中的传入消息数。</span><span class="sxs-lookup"><span data-stu-id="1d200-111">Number of incoming messages in the HTTP receive adapter's internal memory queue.</span></span>|  
||<span data-ttu-id="1d200-112">接收到的消息</span><span class="sxs-lookup"><span data-stu-id="1d200-112">Message received</span></span>|<span data-ttu-id="1d200-113">HTTP 接收适配器收到的 HTTP 请求的总数。</span><span class="sxs-lookup"><span data-stu-id="1d200-113">Total number of HTTP requests received by the HTTP receive adapter.</span></span> <span data-ttu-id="1d200-114">HTTP 接收适配器从 HTTP 客户端完整读取一个请求消息后，该计数器的值才会增加。</span><span class="sxs-lookup"><span data-stu-id="1d200-114">The counter is incremented after a request message is completely read by the HTTP receive adapter from the HTTP client.</span></span>|  
||<span data-ttu-id="1d200-115">每秒接收的消息数</span><span class="sxs-lookup"><span data-stu-id="1d200-115">Messages received/Sec</span></span>|<span data-ttu-id="1d200-116">HTTP 接收适配器每秒收到的 HTTP 请求数。</span><span class="sxs-lookup"><span data-stu-id="1d200-116">Number of HTTP requests received by the HTTP receive adapter per second.</span></span> <span data-ttu-id="1d200-117">该计数器只计入 HTTP 接收适配器已从 HTTP 客户端完整读取的请求消息。</span><span class="sxs-lookup"><span data-stu-id="1d200-117">The counter applies only to request messages that have been completely read by the HTTP receive adapter from the HTTP client.</span></span>|  
||<span data-ttu-id="1d200-118">发送的消息</span><span class="sxs-lookup"><span data-stu-id="1d200-118">Messages sent</span></span>|<span data-ttu-id="1d200-119">HTTP 接收适配器发送的 HTTP 响应的总数。</span><span class="sxs-lookup"><span data-stu-id="1d200-119">Total number of HTTP responses sent by the HTTP receive adapter.</span></span> <span data-ttu-id="1d200-120">此计数器递增只对已成功地发送到 HTTP 客户端的响应消息中。</span><span class="sxs-lookup"><span data-stu-id="1d200-120">The counter is incremented only for response messages that have been successfully sent to HTTP clients.</span></span>|  
||<span data-ttu-id="1d200-121">每秒发送的消息数</span><span class="sxs-lookup"><span data-stu-id="1d200-121">Messages sent/Sec</span></span>|<span data-ttu-id="1d200-122">HTTP 接收适配器每秒发送的 HTTP 响应数。</span><span class="sxs-lookup"><span data-stu-id="1d200-122">Number of HTTP responses sent by the HTTP receive adapter per second.</span></span> <span data-ttu-id="1d200-123">该计数器只计入已成功发送到 HTTP 客户端的响应消息。</span><span class="sxs-lookup"><span data-stu-id="1d200-123">The counter applies only to response messages that have been successfully sent to HTTP clients.</span></span>|  
||<span data-ttu-id="1d200-124">将消息添加到批中的时间</span><span class="sxs-lookup"><span data-stu-id="1d200-124">Time to add message to batch</span></span>|<span data-ttu-id="1d200-125">从 IIS 将消息发送到 HTTP 接收适配器，到将消息添加到批次，这之间的平均时间。</span><span class="sxs-lookup"><span data-stu-id="1d200-125">Average time between when a message is given to the HTTP receive adapter by IIS and when the message is added to a batch.</span></span>|  
||<span data-ttu-id="1d200-126">生成批的时间</span><span class="sxs-lookup"><span data-stu-id="1d200-126">Time to build batch</span></span>|<span data-ttu-id="1d200-127">HTTP 接收适配器生成批消息所花费的平均时间。</span><span class="sxs-lookup"><span data-stu-id="1d200-127">Average time taken by the HTTP receive adapter to build a message batch.</span></span>|  
|<span data-ttu-id="1d200-128">BizTalk:HTTP Send Adapter</span><span class="sxs-lookup"><span data-stu-id="1d200-128">BizTalk:HTTP Send Adapter</span></span>|<span data-ttu-id="1d200-129">内存队列大小</span><span class="sxs-lookup"><span data-stu-id="1d200-129">Memory queue size</span></span>|<span data-ttu-id="1d200-130">HTTP 发送适配器的内部内存队列中的传出消息数。</span><span class="sxs-lookup"><span data-stu-id="1d200-130">Number of outgoing messages in the HTTP send adapter's internal memory queue.</span></span>|  
||<span data-ttu-id="1d200-131">收到的消息</span><span class="sxs-lookup"><span data-stu-id="1d200-131">Messages received</span></span>|<span data-ttu-id="1d200-132">HTTP 发送适配器收到的 HTTP 响应消息总数。</span><span class="sxs-lookup"><span data-stu-id="1d200-132">Total number of HTTP response messages received by the HTTP send adapter.</span></span> <span data-ttu-id="1d200-133">HTTP 发送适配器从 HTTP 服务器完整读取一个响应消息后，该计数器的值才会增加。</span><span class="sxs-lookup"><span data-stu-id="1d200-133">The counter is incremented after a response message is completely read by the HTTP send adapter from HTTP servers.</span></span>|  
||<span data-ttu-id="1d200-134">每秒接收消息</span><span class="sxs-lookup"><span data-stu-id="1d200-134">Message received/Sec</span></span>|<span data-ttu-id="1d200-135">HTTP 发送适配器每秒收到的 HTTP 响应数。</span><span class="sxs-lookup"><span data-stu-id="1d200-135">Number of HTTP responses received by the HTTP send adapter per second.</span></span> <span data-ttu-id="1d200-136">该计数器只计入 HTTP 发送适配器已从 HTTP 服务器完整读取的响应消息。</span><span class="sxs-lookup"><span data-stu-id="1d200-136">The counter applies only to response messages that have been completely read by the HTTP send adapter from HTTP servers.</span></span>|  
||<span data-ttu-id="1d200-137">发送的消息</span><span class="sxs-lookup"><span data-stu-id="1d200-137">Messages sent</span></span>|<span data-ttu-id="1d200-138">HTTP 发送适配器发送的 HTTP 请求的总数。</span><span class="sxs-lookup"><span data-stu-id="1d200-138">Total number of HTTP requests sent by the HTTP send adapter.</span></span> <span data-ttu-id="1d200-139">此计数器只对已到达目标 URL 的请求消息时递增。</span><span class="sxs-lookup"><span data-stu-id="1d200-139">The counter is incremented only for request messages that have reached the destination URL.</span></span>|  
||<span data-ttu-id="1d200-140">每秒发送的消息数</span><span class="sxs-lookup"><span data-stu-id="1d200-140">Messages sent/Sec</span></span>|<span data-ttu-id="1d200-141">HTTP 发送适配器每秒发送的 HTTP 请求数。</span><span class="sxs-lookup"><span data-stu-id="1d200-141">Number of HTTP requests sent by the HTTP send adapter per second.</span></span> <span data-ttu-id="1d200-142">该计数器只计入已到达目标 URL 的请求消息。</span><span class="sxs-lookup"><span data-stu-id="1d200-142">The counter applies only to request messages that have reached the destination URL.</span></span>|  
  
## <a name="to-access-performance-counters"></a><span data-ttu-id="1d200-143">访问性能计数器</span><span class="sxs-lookup"><span data-stu-id="1d200-143">To access performance counters</span></span>  
 <span data-ttu-id="1d200-144">依照下述步骤访问性能计数器。</span><span class="sxs-lookup"><span data-stu-id="1d200-144">Use the following steps to access the performance counters.</span></span>  
  
#### <a name="if-you-are-using-windows-2008"></a><span data-ttu-id="1d200-145">如果您使用的是 Windows 2008</span><span class="sxs-lookup"><span data-stu-id="1d200-145">If you are using Windows 2008</span></span>  
  
1.  <span data-ttu-id="1d200-146">单击**启动**，指向**管理工具**，然后单击**性能监视器**。</span><span class="sxs-lookup"><span data-stu-id="1d200-146">Click **Start**, point to **Administrative Tools**, and then click **Performance Monitor**.</span></span>  
  
2.  <span data-ttu-id="1d200-147">在**性能监视器**对话框框中，展开**监视工具**，选择**性能监视器**，然后单击**添加**。</span><span class="sxs-lookup"><span data-stu-id="1d200-147">In the **Performance Monitor** dialog box, expand **Monitoring Tools**, select **Performance Monitor**, and then click **Add**.</span></span>  
  
3.  <span data-ttu-id="1d200-148">在**添加计数器**对话框中，从**可用计数器**列表中，展开**BizTalk:HTTP**性能计数器对象，然后选择要监视的计数器</span><span class="sxs-lookup"><span data-stu-id="1d200-148">In the **Add Counters** dialog box, from the **Available Counters** list, expand the **BizTalk:HTTP** performance counter object and select the counters to be monitored</span></span>  
  
4.  <span data-ttu-id="1d200-149">在**实例的所选对象**列表中，选择要监视的所选计数器，然后单击的特定实例**添加**。</span><span class="sxs-lookup"><span data-stu-id="1d200-149">In the **Instances of Selected object** list, select the specific instances to be monitored for the selected counters and then click **Add**.</span></span>  <span data-ttu-id="1d200-150">若要选择的所有可用的计数器实例，选择\<**所有实例**\>。</span><span class="sxs-lookup"><span data-stu-id="1d200-150">To select all available counter instances, select \<**All instances**\>.</span></span>  
  
5.  <span data-ttu-id="1d200-151">添加计数器后, 单击**确定**。</span><span class="sxs-lookup"><span data-stu-id="1d200-151">After adding the counters, click **OK**.</span></span>  
  
     <span data-ttu-id="1d200-152">所选的性能计数器显示在**性能监视器**屏幕。</span><span class="sxs-lookup"><span data-stu-id="1d200-152">The selected performance counters appear on the **Performance Monitor** screen.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1d200-153">另请参阅</span><span class="sxs-lookup"><span data-stu-id="1d200-153">See Also</span></span>  
 <span data-ttu-id="1d200-154">[监视 BizTalk Server](../core/monitoring-biztalk-server.md) </span><span class="sxs-lookup"><span data-stu-id="1d200-154">[Monitoring BizTalk Server](../core/monitoring-biztalk-server.md) </span></span>  
 <span data-ttu-id="1d200-155">[HTTP 适配器配置和优化参数](../core/http-adapter-configuration-and-tuning-parameters.md) </span><span class="sxs-lookup"><span data-stu-id="1d200-155">[HTTP Adapter Configuration and Tuning Parameters](../core/http-adapter-configuration-and-tuning-parameters.md) </span></span>  
 [<span data-ttu-id="1d200-156">在群集主机内运行适配器处理程序的注意事项</span><span class="sxs-lookup"><span data-stu-id="1d200-156">Considerations for Running Adapter Handlers within a Clustered Host</span></span>](../core/considerations-for-running-adapter-handlers-within-a-clustered-host1.md)