---
title: 消息框性能计数器 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 5eafbd7b-f5fc-4942-a975-18154e6a7ee2
caps.latest.revision: 19
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 43c0d914e9e45175672e3cf207ede11608e8438a
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65394580"
---
# <a name="message-box-performance-counters"></a><span data-ttu-id="c7c1f-102">Messagebox 性能计数器</span><span class="sxs-lookup"><span data-stu-id="c7c1f-102">Message Box Performance Counters</span></span>
<span data-ttu-id="c7c1f-103">性能计数器允许你监视的工作上的站点或系统服务执行的特定方面。</span><span class="sxs-lookup"><span data-stu-id="c7c1f-103">Performance counters allow you to monitor specific aspects of work performed on the site or system by service.</span></span> <span data-ttu-id="c7c1f-104">性能计数器可以帮助您确定和解决服务器性能问题。</span><span class="sxs-lookup"><span data-stu-id="c7c1f-104">Performance counters can help you identify and troubleshoot server performance issues.</span></span>  
  
 <span data-ttu-id="c7c1f-105">以下性能计数器都可以访问每个主机实例下**biztalk: Message Box: General Counters**并**biztalk: Message Box: Host Counters**性能对象类别:</span><span class="sxs-lookup"><span data-stu-id="c7c1f-105">The following performance counters are accessible for each host instance under the **BizTalk:Message Box:General Counters** and the **BizTalk:Message Box:Host Counters** performance object categories:</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="c7c1f-106">若要启用引用 SQL 代理作业的计数器，必须包括 SQLAgentUserRole 向服务帐户用于运行 BizTalk 主机/NT 服务的角色。</span><span class="sxs-lookup"><span data-stu-id="c7c1f-106">To enable counters that refer to the SQL Agent job, you must include the role SQLAgentUserRole to the service account used to run the BizTalk host/NT Service.</span></span> <span data-ttu-id="c7c1f-107">或者，可以授予权限使用其他角色或通过授予读取 MSDB 数据库的显式权限。</span><span class="sxs-lookup"><span data-stu-id="c7c1f-107">Alternatively, you can grant permission using other roles or by granting explicit permission to read the MSDB database.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="c7c1f-108">如果已向 BizTalk Server 组来添加一个新的 MessageBox，下面列出的计数器将不能为新的 MessageBox 之前已配置**缓存刷新**经过为 BizTalk Server 组的时间间隔 （默认值为 60秒为单位）。</span><span class="sxs-lookup"><span data-stu-id="c7c1f-108">If you have added a new MessageBox to your BizTalk Server group, the counters listed below will not be available for the new MessageBox until the configured **Cache Refresh** interval for the BizTalk Server group has elapsed (default of 60 seconds).</span></span>  
  
|<span data-ttu-id="c7c1f-109">Category</span><span class="sxs-lookup"><span data-stu-id="c7c1f-109">Category</span></span>|<span data-ttu-id="c7c1f-110">计数器</span><span class="sxs-lookup"><span data-stu-id="c7c1f-110">Counter</span></span>|<span data-ttu-id="c7c1f-111">Description</span><span class="sxs-lookup"><span data-stu-id="c7c1f-111">Description</span></span>|  
|--------------|-------------|-----------------|  
|<span data-ttu-id="c7c1f-112">常规计数器</span><span class="sxs-lookup"><span data-stu-id="c7c1f-112">General Counters</span></span>|<span data-ttu-id="c7c1f-113">实例总计数</span><span class="sxs-lookup"><span data-stu-id="c7c1f-113">Instances-Total Number</span></span>|<span data-ttu-id="c7c1f-114">跟踪的每个主机存在特定的消息框中的所有实例的总和。</span><span class="sxs-lookup"><span data-stu-id="c7c1f-114">Tracks the sum of all the instances of each host, which exist within a particular Message Box.</span></span>|  
|<span data-ttu-id="c7c1f-115">常规计数器</span><span class="sxs-lookup"><span data-stu-id="c7c1f-115">General Counters</span></span>|<span data-ttu-id="c7c1f-116">MsgBox 死进程清理 （清除作业）</span><span class="sxs-lookup"><span data-stu-id="c7c1f-116">MsgBox Dead Processes Cleanup (Purge Jobs)</span></span>|<span data-ttu-id="c7c1f-117">以秒为单位的 SQL 代理作业用于释放与死 BizTalk 进程关联的行的数据库的最近运行的时间。</span><span class="sxs-lookup"><span data-stu-id="c7c1f-117">Time in seconds for most recent run of SQL agent job which releases database rows associated with dead BizTalk processes.</span></span>|  
|<span data-ttu-id="c7c1f-118">常规计数器</span><span class="sxs-lookup"><span data-stu-id="c7c1f-118">General Counters</span></span>|<span data-ttu-id="c7c1f-119">MsgBox Msg 清理 （清除作业）</span><span class="sxs-lookup"><span data-stu-id="c7c1f-119">MsgBox Msg Cleanup (Purge Jobs)</span></span>|<span data-ttu-id="c7c1f-120">时间 （秒） 的最新运行 SQL 代理作业用于清除与删除的消息关联的 messagebox 表。</span><span class="sxs-lookup"><span data-stu-id="c7c1f-120">Time in seconds for most recent run of SQL agent job which cleans up message box tables associated with removed messages.</span></span>|  
|<span data-ttu-id="c7c1f-121">常规计数器</span><span class="sxs-lookup"><span data-stu-id="c7c1f-121">General Counters</span></span>|<span data-ttu-id="c7c1f-122">MsgBox 部件清理 （清除作业）</span><span class="sxs-lookup"><span data-stu-id="c7c1f-122">MsgBox Parts Cleanup (Purge Jobs)</span></span>|<span data-ttu-id="c7c1f-123">以秒为单位的最新运行 SQL 代理作业用于清除与关联的 messagebox 表已删除消息部分的时间。</span><span class="sxs-lookup"><span data-stu-id="c7c1f-123">Time in seconds for most recent run of SQL agent job which clean up message box tables associated with removed message parts.</span></span>|  
|<span data-ttu-id="c7c1f-124">常规计数器</span><span class="sxs-lookup"><span data-stu-id="c7c1f-124">General Counters</span></span>|<span data-ttu-id="c7c1f-125">MsgBox 清除订阅作业 （清除作业）</span><span class="sxs-lookup"><span data-stu-id="c7c1f-125">MsgBox Purge Subscriptions Job (Purge Jobs)</span></span>|<span data-ttu-id="c7c1f-126">以秒为单位的最新运行 SQL 代理作业用于清除不再使用的订阅的时间。</span><span class="sxs-lookup"><span data-stu-id="c7c1f-126">Time in seconds for most recent run of SQL agent job which purges subscriptions which are no longer in use.</span></span>|  
|<span data-ttu-id="c7c1f-127">常规计数器</span><span class="sxs-lookup"><span data-stu-id="c7c1f-127">General Counters</span></span>|<span data-ttu-id="c7c1f-128">后台处理大小</span><span class="sxs-lookup"><span data-stu-id="c7c1f-128">Spool Size</span></span>|<span data-ttu-id="c7c1f-129">在特定服务器上特定 messagebox 跟踪后台缓冲区的大小。</span><span class="sxs-lookup"><span data-stu-id="c7c1f-129">Tracks the size of the spool on a particular message box on a particular server.</span></span>|  
|<span data-ttu-id="c7c1f-130">常规计数器</span><span class="sxs-lookup"><span data-stu-id="c7c1f-130">General Counters</span></span>|<span data-ttu-id="c7c1f-131">跟踪的消息复制 （清除作业）</span><span class="sxs-lookup"><span data-stu-id="c7c1f-131">Tracked Msgs Copy (Purge Jobs)</span></span>|<span data-ttu-id="c7c1f-132">时间 （秒） 的最新运行 SQL 代理作业的复制所跟踪的消息正文跟踪的消息。</span><span class="sxs-lookup"><span data-stu-id="c7c1f-132">Time in seconds for most recent run of SQL agent job which copies tracked message bodies for tracked messages.</span></span>|  
|<span data-ttu-id="c7c1f-133">常规计数器</span><span class="sxs-lookup"><span data-stu-id="c7c1f-133">General Counters</span></span>|<span data-ttu-id="c7c1f-134">跟踪数据大小</span><span class="sxs-lookup"><span data-stu-id="c7c1f-134">Tracking data size</span></span>|<span data-ttu-id="c7c1f-135">在特定服务器上特定 messagebox 跟踪的跟踪数据大小的表。</span><span class="sxs-lookup"><span data-stu-id="c7c1f-135">Tracks the size of the tracking data table on a particular message box on a particular server.</span></span>|  
|<span data-ttu-id="c7c1f-136">常规计数器</span><span class="sxs-lookup"><span data-stu-id="c7c1f-136">General Counters</span></span>|<span data-ttu-id="c7c1f-137">跟踪后台处理清除 （清除作业）</span><span class="sxs-lookup"><span data-stu-id="c7c1f-137">Tracking Spool Cleanup (Purge Jobs)</span></span>|<span data-ttu-id="c7c1f-138">以秒为单位的最新的 SQL 代理作业用于清除非活动状态的运行时间跟踪后台处理表。</span><span class="sxs-lookup"><span data-stu-id="c7c1f-138">Time in seconds for the most recent run of the SQL agent job which purges the inactive tracking spool tables.</span></span>|  
|<span data-ttu-id="c7c1f-139">主机计数器</span><span class="sxs-lookup"><span data-stu-id="c7c1f-139">Host Counters</span></span>|<span data-ttu-id="c7c1f-140">主机队列-实例状态消息引用-长度</span><span class="sxs-lookup"><span data-stu-id="c7c1f-140">Host Queue - Instance State Msg Refs - Length</span></span>|<span data-ttu-id="c7c1f-141">跟踪此特定主机的实例状态队列中消息引用的数目。</span><span class="sxs-lookup"><span data-stu-id="c7c1f-141">Tracks the number of message references in the instance state queue for this particular host.</span></span>|  
|<span data-ttu-id="c7c1f-142">主机计数器</span><span class="sxs-lookup"><span data-stu-id="c7c1f-142">Host Counters</span></span>|<span data-ttu-id="c7c1f-143">主机队列-长度</span><span class="sxs-lookup"><span data-stu-id="c7c1f-143">Host Queue - Length</span></span>|<span data-ttu-id="c7c1f-144">跟踪特定主机队列中消息的总数。</span><span class="sxs-lookup"><span data-stu-id="c7c1f-144">Tracks the total number of messages in the particular host queue.</span></span>|  
|<span data-ttu-id="c7c1f-145">主机计数器</span><span class="sxs-lookup"><span data-stu-id="c7c1f-145">Host Counters</span></span>|<span data-ttu-id="c7c1f-146">主机队列-实例数</span><span class="sxs-lookup"><span data-stu-id="c7c1f-146">Host Queue - Number of Instances</span></span>|<span data-ttu-id="c7c1f-147">跟踪此特定主机的实例数。</span><span class="sxs-lookup"><span data-stu-id="c7c1f-147">Tracks the number of instances of this particular host.</span></span>|  
|<span data-ttu-id="c7c1f-148">主机计数器</span><span class="sxs-lookup"><span data-stu-id="c7c1f-148">Host Counters</span></span>|<span data-ttu-id="c7c1f-149">主机队列-挂起的消息的长度</span><span class="sxs-lookup"><span data-stu-id="c7c1f-149">Host Queue - Suspended Msgs - Length</span></span>|<span data-ttu-id="c7c1f-150">跟踪特定主机的挂起的消息总数。</span><span class="sxs-lookup"><span data-stu-id="c7c1f-150">Tracks the total number of suspended messages for the particular host.</span></span>|  
  
## <a name="to-access-performance-counters"></a><span data-ttu-id="c7c1f-151">若要访问性能计数器</span><span class="sxs-lookup"><span data-stu-id="c7c1f-151">To access performance counters</span></span>  
 <span data-ttu-id="c7c1f-152">使用以下步骤访问性能计数器。</span><span class="sxs-lookup"><span data-stu-id="c7c1f-152">Use the following steps to access the performance counters.</span></span>  
  
#### <a name="if-you-are-using-windows-2008"></a><span data-ttu-id="c7c1f-153">如果您使用的 Windows 2008</span><span class="sxs-lookup"><span data-stu-id="c7c1f-153">If you are using Windows 2008</span></span>  
  
1.  <span data-ttu-id="c7c1f-154">单击**启动**，依次指向**管理工具**，然后单击**性能监视器**。</span><span class="sxs-lookup"><span data-stu-id="c7c1f-154">Click **Start**, point to **Administrative Tools**, and then click **Performance Monitor**.</span></span>  
  
2.  <span data-ttu-id="c7c1f-155">在中**性能监视器**对话框框中，展开**监视工具**，选择**性能监视器**，然后单击**添加**。</span><span class="sxs-lookup"><span data-stu-id="c7c1f-155">In the **Performance Monitor** dialog box, expand **Monitoring Tools**, select **Performance Monitor**, and then click **Add**.</span></span>  
  
3.  <span data-ttu-id="c7c1f-156">在中**添加计数器**对话框中，从**可用的计数器**列表中选择**biztalk: Message Box: General Counters**或**biztalk: Message 框： 主机计数器**。</span><span class="sxs-lookup"><span data-stu-id="c7c1f-156">In the **Add Counters** dialog box, from the **Available Counters** list, select either **BizTalk:Message Box:General Counters** or  **BizTalk:Message box:Host Counters**.</span></span> <span data-ttu-id="c7c1f-157">展开所选的性能计数器对象，然后选择要监视的计数器</span><span class="sxs-lookup"><span data-stu-id="c7c1f-157">Expand the selected performance counter object and select the counters to be monitored</span></span>  
  
4.  <span data-ttu-id="c7c1f-158">在中**选定对象的实例**列表中，选择要监视的所选的计数器，然后单击的特定实例**添加**。</span><span class="sxs-lookup"><span data-stu-id="c7c1f-158">In the **Instances of Selected object** list, select the specific instances to be monitored for the selected counters and then click **Add**.</span></span>  <span data-ttu-id="c7c1f-159">若要选择的所有可用的计数器实例，请选择\<**所有实例**\>。</span><span class="sxs-lookup"><span data-stu-id="c7c1f-159">To select all available counter instances, select \<**All instances**\>.</span></span>  
  
5.  <span data-ttu-id="c7c1f-160">添加计数器之后, 单击**确定**。</span><span class="sxs-lookup"><span data-stu-id="c7c1f-160">After adding the counters, click **OK**.</span></span>  
  
     <span data-ttu-id="c7c1f-161">所选的性能计数器随即显示在**性能监视器**屏幕。</span><span class="sxs-lookup"><span data-stu-id="c7c1f-161">The selected performance counters appear on the **Performance Monitor** screen.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c7c1f-162">请参阅</span><span class="sxs-lookup"><span data-stu-id="c7c1f-162">See Also</span></span>  
 <span data-ttu-id="c7c1f-163">[性能提示和技巧](../core/performance-tips-and-tricks.md) </span><span class="sxs-lookup"><span data-stu-id="c7c1f-163">[Performance Tips and Tricks](../core/performance-tips-and-tricks.md) </span></span>  
 <span data-ttu-id="c7c1f-164">[测量最大可承受引擎吞吐量](../core/measuring-maximum-sustainable-engine-throughput.md) </span><span class="sxs-lookup"><span data-stu-id="c7c1f-164">[Measuring Maximum Sustainable Engine Throughput](../core/measuring-maximum-sustainable-engine-throughput.md) </span></span>  
 <span data-ttu-id="c7c1f-165">[测量最大可承受跟踪吞吐量](../core/measuring-maximum-sustainable-tracking-throughput.md) </span><span class="sxs-lookup"><span data-stu-id="c7c1f-165">[Measuring Maximum Sustainable Tracking Throughput](../core/measuring-maximum-sustainable-tracking-throughput.md) </span></span>  
 [<span data-ttu-id="c7c1f-166">通过主机阻止优化资源使用情况</span><span class="sxs-lookup"><span data-stu-id="c7c1f-166">Optimizing Resource Usage Through Host Throttling</span></span>](../core/optimizing-resource-usage-through-host-throttling.md)