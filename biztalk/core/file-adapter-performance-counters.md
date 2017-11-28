---
title: "文件适配器性能计数器 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 343465b4-6b20-4a24-b4b1-138548c572cc
caps.latest.revision: "11"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 617c3fc2821c9b9aa1aba690d27a9b48dc1116c4
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="file-adapter-performance-counters"></a><span data-ttu-id="a9ab6-102">文件适配器性能计数器</span><span class="sxs-lookup"><span data-stu-id="a9ab6-102">File Adapter Performance Counters</span></span>
<span data-ttu-id="a9ab6-103">使用性能计数器可以监视服务在站点或系统上执行的工作的特定方面。</span><span class="sxs-lookup"><span data-stu-id="a9ab6-103">Performance counters allow you to monitor specific aspects of work performed on the site or system by service.</span></span> <span data-ttu-id="a9ab6-104">性能计数器能够帮助您标识和解决有关服务器性能的问题。</span><span class="sxs-lookup"><span data-stu-id="a9ab6-104">Performance counters can help you identify and troubleshoot server performance issues.</span></span>  
  
 <span data-ttu-id="a9ab6-105">以下性能计数器进行访问每个主机实例下**BizTalk:FILE 接收适配器**和**BizTalk:FILE 发送适配器**性能对象类别：</span><span class="sxs-lookup"><span data-stu-id="a9ab6-105">The following performance counters are accessible for each host instance under the **BizTalk:FILE Receive Adapter** and the **BizTalk:FILE Send Adapter** performance object categories:</span></span>  
  
|<span data-ttu-id="a9ab6-106">**类别**</span><span class="sxs-lookup"><span data-stu-id="a9ab6-106">**Category**</span></span>|<span data-ttu-id="a9ab6-107">**计数器**</span><span class="sxs-lookup"><span data-stu-id="a9ab6-107">**Counter**</span></span>|<span data-ttu-id="a9ab6-108">**Description**</span><span class="sxs-lookup"><span data-stu-id="a9ab6-108">**Description**</span></span>|  
|------------------|-----------------|---------------------|  
|<span data-ttu-id="a9ab6-109">BizTalk:FILE Receive Adapter</span><span class="sxs-lookup"><span data-stu-id="a9ab6-109">BizTalk:FILE Receive Adapter</span></span>|<span data-ttu-id="a9ab6-110">Bytes received</span><span class="sxs-lookup"><span data-stu-id="a9ab6-110">Bytes received</span></span>|<span data-ttu-id="a9ab6-111">文件接收适配器接收到的字节总数。</span><span class="sxs-lookup"><span data-stu-id="a9ab6-111">Total number of bytes received by the file receive adapter.</span></span> <span data-ttu-id="a9ab6-112">从文件系统的适配器完全读取一条消息后，计数器即会递增。</span><span class="sxs-lookup"><span data-stu-id="a9ab6-112">The counter is incremented after a message is completely read by the adapter from the file system.</span></span>|  
||<span data-ttu-id="a9ab6-113">Byte received/Sec</span><span class="sxs-lookup"><span data-stu-id="a9ab6-113">Byte received/Sec</span></span>|<span data-ttu-id="a9ab6-114">文件接收适配器每秒接收到的字节数。</span><span class="sxs-lookup"><span data-stu-id="a9ab6-114">Number of bytes received by the file receive adapter per second.</span></span> <span data-ttu-id="a9ab6-115">该计数器仅计入文件适配器从文件系统中完整读取的消息。</span><span class="sxs-lookup"><span data-stu-id="a9ab6-115">The counter applies only to messages that have been completely read by the file adapter from the file system.</span></span>|  
||<span data-ttu-id="a9ab6-116">Delete retries</span><span class="sxs-lookup"><span data-stu-id="a9ab6-116">Delete retries</span></span>|<span data-ttu-id="a9ab6-117">文件接收适配器尝试删除已读取文件的次数。</span><span class="sxs-lookup"><span data-stu-id="a9ab6-117">Number of times the file receive adapter attempts to delete a file that has been read.</span></span>|  
||<span data-ttu-id="a9ab6-118">Lock failures</span><span class="sxs-lookup"><span data-stu-id="a9ab6-118">Lock failures</span></span>|<span data-ttu-id="a9ab6-119">文件接收适配器锁定文件失败的次数。</span><span class="sxs-lookup"><span data-stu-id="a9ab6-119">Number of times the file receive adapter failed to lock the file.</span></span>|  
||<span data-ttu-id="a9ab6-120">Lock failures/sec</span><span class="sxs-lookup"><span data-stu-id="a9ab6-120">Lock failures/sec</span></span>|<span data-ttu-id="a9ab6-121">文件接收适配器每秒锁定文件失败的次数。</span><span class="sxs-lookup"><span data-stu-id="a9ab6-121">Number of times the file receive adapter failed to lock the file per second.</span></span>|  
||<span data-ttu-id="a9ab6-122">收到的消息</span><span class="sxs-lookup"><span data-stu-id="a9ab6-122">Messages received</span></span>|<span data-ttu-id="a9ab6-123">文件接收适配器接收到的消息总数。</span><span class="sxs-lookup"><span data-stu-id="a9ab6-123">Total number of messages received by the file receive adapter.</span></span> <span data-ttu-id="a9ab6-124">文件接收适配器从文件系统中完整读取一个消息后，该计数器的值才会增加。</span><span class="sxs-lookup"><span data-stu-id="a9ab6-124">The counter is incremented after a message is completely read by the file receive adapter from the file system.</span></span>|  
||<span data-ttu-id="a9ab6-125">每秒接收的消息数</span><span class="sxs-lookup"><span data-stu-id="a9ab6-125">Messages received/Sec</span></span>|<span data-ttu-id="a9ab6-126">文件接收适配器每秒接收到的消息数。</span><span class="sxs-lookup"><span data-stu-id="a9ab6-126">Number of messages received by the file receive adapter per second.</span></span> <span data-ttu-id="a9ab6-127">该计数器只计入文件接收适配器从文件系统中完整读取的消息。</span><span class="sxs-lookup"><span data-stu-id="a9ab6-127">The counter applies only to messages that have been completely read by the file receive adapter from the file system.</span></span>|  
||<span data-ttu-id="a9ab6-128">生成批的时间</span><span class="sxs-lookup"><span data-stu-id="a9ab6-128">Time to build batch</span></span>|<span data-ttu-id="a9ab6-129">文件接收适配器生成批的平均占用时间。</span><span class="sxs-lookup"><span data-stu-id="a9ab6-129">Average time taken by file receive adapter to build a batch.</span></span>|  
|<span data-ttu-id="a9ab6-130">BizTalk:FILE Send Adapter</span><span class="sxs-lookup"><span data-stu-id="a9ab6-130">BizTalk:FILE Send Adapter</span></span>|<span data-ttu-id="a9ab6-131">Bytes sent</span><span class="sxs-lookup"><span data-stu-id="a9ab6-131">Bytes sent</span></span>|<span data-ttu-id="a9ab6-132">文件发送适配器发送的字节总数。</span><span class="sxs-lookup"><span data-stu-id="a9ab6-132">Total number of bytes sent by the file send adapter.</span></span> <span data-ttu-id="a9ab6-133">此计数器只对完全写入到文件系统的消息时递增。</span><span class="sxs-lookup"><span data-stu-id="a9ab6-133">The counter is incremented only for messages that have been completely written to file system.</span></span>|  
||<span data-ttu-id="a9ab6-134">Bytes sent/Sec</span><span class="sxs-lookup"><span data-stu-id="a9ab6-134">Bytes sent/Sec</span></span>|<span data-ttu-id="a9ab6-135">文件发送适配器每秒发送的字节数。</span><span class="sxs-lookup"><span data-stu-id="a9ab6-135">Number of bytes sent by the file send adapter per second.</span></span> <span data-ttu-id="a9ab6-136">该计数器只计入已完整写入文件系统的消息。</span><span class="sxs-lookup"><span data-stu-id="a9ab6-136">The counter applies only to messages that have been completely written to file system.</span></span>|  
||<span data-ttu-id="a9ab6-137">发送的消息</span><span class="sxs-lookup"><span data-stu-id="a9ab6-137">Messages sent</span></span>|<span data-ttu-id="a9ab6-138">文件发送适配器发送的消息总数。</span><span class="sxs-lookup"><span data-stu-id="a9ab6-138">Total number of messages sent by the file send adapter.</span></span> <span data-ttu-id="a9ab6-139">此计数器只对完全写入到文件系统的消息时递增。</span><span class="sxs-lookup"><span data-stu-id="a9ab6-139">The counter is incremented only for messages that have been completely written to file system.</span></span>|  
||<span data-ttu-id="a9ab6-140">每秒发送的消息数</span><span class="sxs-lookup"><span data-stu-id="a9ab6-140">Messages sent/Sec</span></span>|<span data-ttu-id="a9ab6-141">文件发送适配器每秒发送的消息数。</span><span class="sxs-lookup"><span data-stu-id="a9ab6-141">Number of messages sent by the file send adapter per second.</span></span> <span data-ttu-id="a9ab6-142">该计数器只计入已完整写入文件系统的消息。</span><span class="sxs-lookup"><span data-stu-id="a9ab6-142">The counter applies only to messages that have been completely written to file system.</span></span>|  
  
## <a name="to-access-performance-counters"></a><span data-ttu-id="a9ab6-143">访问性能计数器</span><span class="sxs-lookup"><span data-stu-id="a9ab6-143">To access performance counters</span></span>  
 <span data-ttu-id="a9ab6-144">依照下述步骤访问性能计数器。</span><span class="sxs-lookup"><span data-stu-id="a9ab6-144">Use the following steps to access the performance counters.</span></span>  
  
#### <a name="if-you-are-using-windows-2008"></a><span data-ttu-id="a9ab6-145">如果您使用的是 Windows 2008</span><span class="sxs-lookup"><span data-stu-id="a9ab6-145">If you are using Windows 2008</span></span>  
  
1.  <span data-ttu-id="a9ab6-146">单击**启动**，指向**管理工具**，然后单击**性能监视器**。</span><span class="sxs-lookup"><span data-stu-id="a9ab6-146">Click **Start**, point to **Administrative Tools**, and then click **Performance Monitor**.</span></span>  
  
2.  <span data-ttu-id="a9ab6-147">在**性能监视器**对话框框中，展开**监视工具**，选择**性能监视器**，然后单击**添加**。</span><span class="sxs-lookup"><span data-stu-id="a9ab6-147">In the **Performance Monitor** dialog box, expand **Monitoring Tools**, select **Performance Monitor**, and then click **Add**.</span></span>  
  
3.  <span data-ttu-id="a9ab6-148">在**添加计数器**对话框中，从**可用计数器**列表中，展开**BizTalk:FILE**性能计数器对象，然后选择要监视的计数器</span><span class="sxs-lookup"><span data-stu-id="a9ab6-148">In the **Add Counters** dialog box, from the **Available Counters** list, expand the **BizTalk:FILE** performance counter object and select the counters to be monitored</span></span>  
  
4.  <span data-ttu-id="a9ab6-149">在**实例的所选对象**列表中，选择要监视的所选计数器，然后单击的特定实例**添加**。</span><span class="sxs-lookup"><span data-stu-id="a9ab6-149">In the **Instances of Selected object** list, select the specific instances to be monitored for the selected counters and then click **Add**.</span></span>  <span data-ttu-id="a9ab6-150">若要选择的所有可用的计数器实例，选择\<**所有实例**>。</span><span class="sxs-lookup"><span data-stu-id="a9ab6-150">To select all available counter instances, select \<**All instances**>.</span></span>  
  
5.  <span data-ttu-id="a9ab6-151">添加计数器后, 单击**确定**。</span><span class="sxs-lookup"><span data-stu-id="a9ab6-151">After adding the counters, click **OK**.</span></span>  
  
     <span data-ttu-id="a9ab6-152">所选的性能计数器显示在**性能监视器**屏幕。</span><span class="sxs-lookup"><span data-stu-id="a9ab6-152">The selected performance counters appear on the **Performance Monitor** screen.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a9ab6-153">另请参阅</span><span class="sxs-lookup"><span data-stu-id="a9ab6-153">See Also</span></span>  
 [<span data-ttu-id="a9ab6-154">为持续性能规划</span><span class="sxs-lookup"><span data-stu-id="a9ab6-154">Planning for Sustained Performance</span></span>](../core/planning-for-sustained-performance.md)