---
title: HTTP 适配器性能计数器 |Microsoft Docs
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
ms.openlocfilehash: bd3fa6a9dbb49edd5bbeee20230d1ccef2ac6baa
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65382845"
---
# <a name="http-adapter-performance-counters"></a><span data-ttu-id="36c69-102">HTTP 适配器性能计数器</span><span class="sxs-lookup"><span data-stu-id="36c69-102">HTTP Adapter Performance Counters</span></span>
<span data-ttu-id="36c69-103">性能计数器允许你监视的工作上的站点或系统服务执行的特定方面。</span><span class="sxs-lookup"><span data-stu-id="36c69-103">Performance counters allow you to monitor specific aspects of work performed on the site or system by service.</span></span> <span data-ttu-id="36c69-104">性能计数器可以帮助您确定和解决服务器性能问题。</span><span class="sxs-lookup"><span data-stu-id="36c69-104">Performance counters can help you identify and troubleshoot server performance issues.</span></span>  
  
 <span data-ttu-id="36c69-105">以下性能计数器都可以访问每个主机实例下**biztalk: Http Receive Adapter**并**biztalk: Http Send Adapter**性能对象类别：</span><span class="sxs-lookup"><span data-stu-id="36c69-105">The following performance counters are accessible for each host instance under the **BizTalk:HTTP Receive Adapter** and the **BizTalk:HTTP Send Adapter** performance object categories:</span></span>  
  
|<span data-ttu-id="36c69-106">**类别**</span><span class="sxs-lookup"><span data-stu-id="36c69-106">**Category**</span></span>|<span data-ttu-id="36c69-107">**计数器**</span><span class="sxs-lookup"><span data-stu-id="36c69-107">**Counter**</span></span>|<span data-ttu-id="36c69-108">**说明**</span><span class="sxs-lookup"><span data-stu-id="36c69-108">**Description**</span></span>|  
|------------------|-----------------|---------------------|  
|<span data-ttu-id="36c69-109">Biztalk: Http 接收适配器</span><span class="sxs-lookup"><span data-stu-id="36c69-109">BizTalk:HTTP Receive Adapter</span></span>|<span data-ttu-id="36c69-110">内存队列大小</span><span class="sxs-lookup"><span data-stu-id="36c69-110">Memory queue size</span></span>|<span data-ttu-id="36c69-111">传入消息在 HTTP 接收适配器的内部内存队列。</span><span class="sxs-lookup"><span data-stu-id="36c69-111">Number of incoming messages in the HTTP receive adapter's internal memory queue.</span></span>|  
||<span data-ttu-id="36c69-112">接收消息</span><span class="sxs-lookup"><span data-stu-id="36c69-112">Message received</span></span>|<span data-ttu-id="36c69-113">接收适配器收到的 HTTP 的 HTTP 请求的总数。</span><span class="sxs-lookup"><span data-stu-id="36c69-113">Total number of HTTP requests received by the HTTP receive adapter.</span></span> <span data-ttu-id="36c69-114">此计数器递增后请求消息完全读取的 HTTP 接收适配器从 HTTP 客户端。</span><span class="sxs-lookup"><span data-stu-id="36c69-114">The counter is incremented after a request message is completely read by the HTTP receive adapter from the HTTP client.</span></span>|  
||<span data-ttu-id="36c69-115">收到的消息数/秒</span><span class="sxs-lookup"><span data-stu-id="36c69-115">Messages received/Sec</span></span>|<span data-ttu-id="36c69-116">适配器每秒接收的 http 接收到 HTTP 请求数。</span><span class="sxs-lookup"><span data-stu-id="36c69-116">Number of HTTP requests received by the HTTP receive adapter per second.</span></span> <span data-ttu-id="36c69-117">该计数器仅适用于请求消息已完全读取的 HTTP 接收适配器从 HTTP 客户端。</span><span class="sxs-lookup"><span data-stu-id="36c69-117">The counter applies only to request messages that have been completely read by the HTTP receive adapter from the HTTP client.</span></span>|  
||<span data-ttu-id="36c69-118">发送的消息</span><span class="sxs-lookup"><span data-stu-id="36c69-118">Messages sent</span></span>|<span data-ttu-id="36c69-119">接收适配器通过 HTTP 发送的 HTTP 响应的总数。</span><span class="sxs-lookup"><span data-stu-id="36c69-119">Total number of HTTP responses sent by the HTTP receive adapter.</span></span> <span data-ttu-id="36c69-120">仅对已成功发送到 HTTP 客户端的响应消息是增加计数器的数值。</span><span class="sxs-lookup"><span data-stu-id="36c69-120">The counter is incremented only for response messages that have been successfully sent to HTTP clients.</span></span>|  
||<span data-ttu-id="36c69-121">发送的消息数/秒</span><span class="sxs-lookup"><span data-stu-id="36c69-121">Messages sent/Sec</span></span>|<span data-ttu-id="36c69-122">适配器每秒接收的 http 发送的 HTTP 响应数。</span><span class="sxs-lookup"><span data-stu-id="36c69-122">Number of HTTP responses sent by the HTTP receive adapter per second.</span></span> <span data-ttu-id="36c69-123">计数器仅应用于已成功发送到 HTTP 客户端的响应消息。</span><span class="sxs-lookup"><span data-stu-id="36c69-123">The counter applies only to response messages that have been successfully sent to HTTP clients.</span></span>|  
||<span data-ttu-id="36c69-124">若要将消息添加到批的时间</span><span class="sxs-lookup"><span data-stu-id="36c69-124">Time to add message to batch</span></span>|<span data-ttu-id="36c69-125">当消息发送到 HTTP 之间的平均时间接收适配器的 IIS 和时将消息添加到批处理。</span><span class="sxs-lookup"><span data-stu-id="36c69-125">Average time between when a message is given to the HTTP receive adapter by IIS and when the message is added to a batch.</span></span>|  
||<span data-ttu-id="36c69-126">生成批处理的时间</span><span class="sxs-lookup"><span data-stu-id="36c69-126">Time to build batch</span></span>|<span data-ttu-id="36c69-127">HTTP 的平均占用时间接收适配器生成批消息。</span><span class="sxs-lookup"><span data-stu-id="36c69-127">Average time taken by the HTTP receive adapter to build a message batch.</span></span>|  
|<span data-ttu-id="36c69-128">Biztalk: Http 发送适配器</span><span class="sxs-lookup"><span data-stu-id="36c69-128">BizTalk:HTTP Send Adapter</span></span>|<span data-ttu-id="36c69-129">内存队列大小</span><span class="sxs-lookup"><span data-stu-id="36c69-129">Memory queue size</span></span>|<span data-ttu-id="36c69-130">发送适配器的内部内存队列在 HTTP 的传出消息数。</span><span class="sxs-lookup"><span data-stu-id="36c69-130">Number of outgoing messages in the HTTP send adapter's internal memory queue.</span></span>|  
||<span data-ttu-id="36c69-131">接收的消息</span><span class="sxs-lookup"><span data-stu-id="36c69-131">Messages received</span></span>|<span data-ttu-id="36c69-132">发送适配器通过 HTTP 接收 HTTP 响应消息的总数。</span><span class="sxs-lookup"><span data-stu-id="36c69-132">Total number of HTTP response messages received by the HTTP send adapter.</span></span> <span data-ttu-id="36c69-133">HTTP 发送适配器从 HTTP 服务器完整读取的响应消息后，计数器将递增。</span><span class="sxs-lookup"><span data-stu-id="36c69-133">The counter is incremented after a response message is completely read by the HTTP send adapter from HTTP servers.</span></span>|  
||<span data-ttu-id="36c69-134">收到的消息数/秒</span><span class="sxs-lookup"><span data-stu-id="36c69-134">Message received/Sec</span></span>|<span data-ttu-id="36c69-135">适配器每秒发送的 http 接收到的 HTTP 响应数。</span><span class="sxs-lookup"><span data-stu-id="36c69-135">Number of HTTP responses received by the HTTP send adapter per second.</span></span> <span data-ttu-id="36c69-136">计数器仅应用于已完全读取的 HTTP 发送适配器从 HTTP 服务器的响应消息。</span><span class="sxs-lookup"><span data-stu-id="36c69-136">The counter applies only to response messages that have been completely read by the HTTP send adapter from HTTP servers.</span></span>|  
||<span data-ttu-id="36c69-137">发送的消息</span><span class="sxs-lookup"><span data-stu-id="36c69-137">Messages sent</span></span>|<span data-ttu-id="36c69-138">发送适配器通过 HTTP 发送的 HTTP 请求的总数。</span><span class="sxs-lookup"><span data-stu-id="36c69-138">Total number of HTTP requests sent by the HTTP send adapter.</span></span> <span data-ttu-id="36c69-139">仅对已到达目标 URL 的请求消息是增加计数器的数值。</span><span class="sxs-lookup"><span data-stu-id="36c69-139">The counter is incremented only for request messages that have reached the destination URL.</span></span>|  
||<span data-ttu-id="36c69-140">发送的消息数/秒</span><span class="sxs-lookup"><span data-stu-id="36c69-140">Messages sent/Sec</span></span>|<span data-ttu-id="36c69-141">适配器每秒发送的 http 发送的 HTTP 请求数。</span><span class="sxs-lookup"><span data-stu-id="36c69-141">Number of HTTP requests sent by the HTTP send adapter per second.</span></span> <span data-ttu-id="36c69-142">计数器仅应用于已到达目标 URL 的请求消息。</span><span class="sxs-lookup"><span data-stu-id="36c69-142">The counter applies only to request messages that have reached the destination URL.</span></span>|  
  
## <a name="to-access-performance-counters"></a><span data-ttu-id="36c69-143">若要访问性能计数器</span><span class="sxs-lookup"><span data-stu-id="36c69-143">To access performance counters</span></span>  
 <span data-ttu-id="36c69-144">使用以下步骤访问性能计数器。</span><span class="sxs-lookup"><span data-stu-id="36c69-144">Use the following steps to access the performance counters.</span></span>  
  
#### <a name="if-you-are-using-windows-2008"></a><span data-ttu-id="36c69-145">如果您使用的 Windows 2008</span><span class="sxs-lookup"><span data-stu-id="36c69-145">If you are using Windows 2008</span></span>  
  
1.  <span data-ttu-id="36c69-146">单击**启动**，依次指向**管理工具**，然后单击**性能监视器**。</span><span class="sxs-lookup"><span data-stu-id="36c69-146">Click **Start**, point to **Administrative Tools**, and then click **Performance Monitor**.</span></span>  
  
2.  <span data-ttu-id="36c69-147">在中**性能监视器**对话框框中，展开**监视工具**，选择**性能监视器**，然后单击**添加**。</span><span class="sxs-lookup"><span data-stu-id="36c69-147">In the **Performance Monitor** dialog box, expand **Monitoring Tools**, select **Performance Monitor**, and then click **Add**.</span></span>  
  
3.  <span data-ttu-id="36c69-148">在中**添加计数器**对话框中，从**可用的计数器**列表中，展开**biztalk: Http**性能计数器对象，然后选择要监视的计数器</span><span class="sxs-lookup"><span data-stu-id="36c69-148">In the **Add Counters** dialog box, from the **Available Counters** list, expand the **BizTalk:HTTP** performance counter object and select the counters to be monitored</span></span>  
  
4.  <span data-ttu-id="36c69-149">在中**选定对象的实例**列表中，选择要监视的所选的计数器，然后单击的特定实例**添加**。</span><span class="sxs-lookup"><span data-stu-id="36c69-149">In the **Instances of Selected object** list, select the specific instances to be monitored for the selected counters and then click **Add**.</span></span>  <span data-ttu-id="36c69-150">若要选择的所有可用的计数器实例，请选择\<**所有实例**\>。</span><span class="sxs-lookup"><span data-stu-id="36c69-150">To select all available counter instances, select \<**All instances**\>.</span></span>  
  
5.  <span data-ttu-id="36c69-151">添加计数器之后, 单击**确定**。</span><span class="sxs-lookup"><span data-stu-id="36c69-151">After adding the counters, click **OK**.</span></span>  
  
     <span data-ttu-id="36c69-152">所选的性能计数器随即显示在**性能监视器**屏幕。</span><span class="sxs-lookup"><span data-stu-id="36c69-152">The selected performance counters appear on the **Performance Monitor** screen.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="36c69-153">请参阅</span><span class="sxs-lookup"><span data-stu-id="36c69-153">See Also</span></span>  
 <span data-ttu-id="36c69-154">[监视 BizTalk Server](../core/monitoring-biztalk-server.md) </span><span class="sxs-lookup"><span data-stu-id="36c69-154">[Monitoring BizTalk Server](../core/monitoring-biztalk-server.md) </span></span>  
 <span data-ttu-id="36c69-155">[HTTP 适配器配置和优化参数](../core/http-adapter-configuration-and-tuning-parameters.md) </span><span class="sxs-lookup"><span data-stu-id="36c69-155">[HTTP Adapter Configuration and Tuning Parameters](../core/http-adapter-configuration-and-tuning-parameters.md) </span></span>  
 [<span data-ttu-id="36c69-156">在群集主机内运行适配器处理程序的注意事项</span><span class="sxs-lookup"><span data-stu-id="36c69-156">Considerations for Running Adapter Handlers within a Clustered Host</span></span>](../core/considerations-for-running-adapter-handlers-within-a-clustered-host1.md)