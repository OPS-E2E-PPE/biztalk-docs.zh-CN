---
title: 文件适配器性能计数器 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 343465b4-6b20-4a24-b4b1-138548c572cc
caps.latest.revision: 11
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 5920638764e274137ca7a2d94ab11248ae1b200f
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65345560"
---
# <a name="file-adapter-performance-counters"></a><span data-ttu-id="a4485-102">文件适配器性能计数器</span><span class="sxs-lookup"><span data-stu-id="a4485-102">File Adapter Performance Counters</span></span>
<span data-ttu-id="a4485-103">性能计数器允许你监视的工作上的站点或系统服务执行的特定方面。</span><span class="sxs-lookup"><span data-stu-id="a4485-103">Performance counters allow you to monitor specific aspects of work performed on the site or system by service.</span></span> <span data-ttu-id="a4485-104">性能计数器可以帮助您确定和解决服务器性能问题。</span><span class="sxs-lookup"><span data-stu-id="a4485-104">Performance counters can help you identify and troubleshoot server performance issues.</span></span>  
  
 <span data-ttu-id="a4485-105">以下性能计数器都可以访问每个主机实例下**biztalk: File Receive Adapter**并**biztalk: File Send Adapter**性能对象类别：</span><span class="sxs-lookup"><span data-stu-id="a4485-105">The following performance counters are accessible for each host instance under the **BizTalk:FILE Receive Adapter** and the **BizTalk:FILE Send Adapter** performance object categories:</span></span>  
  
|<span data-ttu-id="a4485-106">**类别**</span><span class="sxs-lookup"><span data-stu-id="a4485-106">**Category**</span></span>|<span data-ttu-id="a4485-107">**计数器**</span><span class="sxs-lookup"><span data-stu-id="a4485-107">**Counter**</span></span>|<span data-ttu-id="a4485-108">**说明**</span><span class="sxs-lookup"><span data-stu-id="a4485-108">**Description**</span></span>|  
|------------------|-----------------|---------------------|  
|<span data-ttu-id="a4485-109">Biztalk: File 接收适配器</span><span class="sxs-lookup"><span data-stu-id="a4485-109">BizTalk:FILE Receive Adapter</span></span>|<span data-ttu-id="a4485-110">接收的字节数</span><span class="sxs-lookup"><span data-stu-id="a4485-110">Bytes received</span></span>|<span data-ttu-id="a4485-111">接收适配器接收到该文件的字节总数。</span><span class="sxs-lookup"><span data-stu-id="a4485-111">Total number of bytes received by the file receive adapter.</span></span> <span data-ttu-id="a4485-112">在适配器从文件系统完全读取消息后，计数器将递增。</span><span class="sxs-lookup"><span data-stu-id="a4485-112">The counter is incremented after a message is completely read by the adapter from the file system.</span></span>|  
||<span data-ttu-id="a4485-113">接收的字节数/秒</span><span class="sxs-lookup"><span data-stu-id="a4485-113">Byte received/Sec</span></span>|<span data-ttu-id="a4485-114">由文件接收的字节数接收适配器每秒。</span><span class="sxs-lookup"><span data-stu-id="a4485-114">Number of bytes received by the file receive adapter per second.</span></span> <span data-ttu-id="a4485-115">计数器仅应用于已完全读取的文件适配器从文件系统的消息。</span><span class="sxs-lookup"><span data-stu-id="a4485-115">The counter applies only to messages that have been completely read by the file adapter from the file system.</span></span>|  
||<span data-ttu-id="a4485-116">删除重试次数</span><span class="sxs-lookup"><span data-stu-id="a4485-116">Delete retries</span></span>|<span data-ttu-id="a4485-117">尝试删除已读取的文件的 file 接收适配器的次数。</span><span class="sxs-lookup"><span data-stu-id="a4485-117">Number of times the file receive adapter attempts to delete a file that has been read.</span></span>|  
||<span data-ttu-id="a4485-118">锁定失败</span><span class="sxs-lookup"><span data-stu-id="a4485-118">Lock failures</span></span>|<span data-ttu-id="a4485-119">失败的次数文件接收适配器锁定文件。</span><span class="sxs-lookup"><span data-stu-id="a4485-119">Number of times the file receive adapter failed to lock the file.</span></span>|  
||<span data-ttu-id="a4485-120">每秒锁故障</span><span class="sxs-lookup"><span data-stu-id="a4485-120">Lock failures/sec</span></span>|<span data-ttu-id="a4485-121">无法锁定每秒的文件的 file 接收适配器的次数。</span><span class="sxs-lookup"><span data-stu-id="a4485-121">Number of times the file receive adapter failed to lock the file per second.</span></span>|  
||<span data-ttu-id="a4485-122">接收的消息</span><span class="sxs-lookup"><span data-stu-id="a4485-122">Messages received</span></span>|<span data-ttu-id="a4485-123">接收适配器接收到该文件的消息的总数。</span><span class="sxs-lookup"><span data-stu-id="a4485-123">Total number of messages received by the file receive adapter.</span></span> <span data-ttu-id="a4485-124">此计数器递增文件完全读取消息后接收适配器从文件系统。</span><span class="sxs-lookup"><span data-stu-id="a4485-124">The counter is incremented after a message is completely read by the file receive adapter from the file system.</span></span>|  
||<span data-ttu-id="a4485-125">收到的消息数/秒</span><span class="sxs-lookup"><span data-stu-id="a4485-125">Messages received/Sec</span></span>|<span data-ttu-id="a4485-126">适配器每秒接收的由文件接收的消息数。</span><span class="sxs-lookup"><span data-stu-id="a4485-126">Number of messages received by the file receive adapter per second.</span></span> <span data-ttu-id="a4485-127">计数器只计入由文件已完全读取的消息接收适配器从文件系统。</span><span class="sxs-lookup"><span data-stu-id="a4485-127">The counter applies only to messages that have been completely read by the file receive adapter from the file system.</span></span>|  
||<span data-ttu-id="a4485-128">生成批处理的时间</span><span class="sxs-lookup"><span data-stu-id="a4485-128">Time to build batch</span></span>|<span data-ttu-id="a4485-129">文件的平均占用时间接收适配器生成批。</span><span class="sxs-lookup"><span data-stu-id="a4485-129">Average time taken by file receive adapter to build a batch.</span></span>|  
|<span data-ttu-id="a4485-130">Biztalk: File 发送适配器</span><span class="sxs-lookup"><span data-stu-id="a4485-130">BizTalk:FILE Send Adapter</span></span>|<span data-ttu-id="a4485-131">发送的字节数</span><span class="sxs-lookup"><span data-stu-id="a4485-131">Bytes sent</span></span>|<span data-ttu-id="a4485-132">发送适配器发送文件的字节总数。</span><span class="sxs-lookup"><span data-stu-id="a4485-132">Total number of bytes sent by the file send adapter.</span></span> <span data-ttu-id="a4485-133">已完全写入文件系统的消息才是增加计数器的数值。</span><span class="sxs-lookup"><span data-stu-id="a4485-133">The counter is incremented only for messages that have been completely written to file system.</span></span>|  
||<span data-ttu-id="a4485-134">发送的字节数/秒</span><span class="sxs-lookup"><span data-stu-id="a4485-134">Bytes sent/Sec</span></span>|<span data-ttu-id="a4485-135">发送适配器每秒发送的文件的字节数。</span><span class="sxs-lookup"><span data-stu-id="a4485-135">Number of bytes sent by the file send adapter per second.</span></span> <span data-ttu-id="a4485-136">计数器仅应用于已完全写入文件系统的消息。</span><span class="sxs-lookup"><span data-stu-id="a4485-136">The counter applies only to messages that have been completely written to file system.</span></span>|  
||<span data-ttu-id="a4485-137">发送的消息</span><span class="sxs-lookup"><span data-stu-id="a4485-137">Messages sent</span></span>|<span data-ttu-id="a4485-138">发送适配器发送文件的消息的总数。</span><span class="sxs-lookup"><span data-stu-id="a4485-138">Total number of messages sent by the file send adapter.</span></span> <span data-ttu-id="a4485-139">已完全写入文件系统的消息才是增加计数器的数值。</span><span class="sxs-lookup"><span data-stu-id="a4485-139">The counter is incremented only for messages that have been completely written to file system.</span></span>|  
||<span data-ttu-id="a4485-140">发送的消息数/秒</span><span class="sxs-lookup"><span data-stu-id="a4485-140">Messages sent/Sec</span></span>|<span data-ttu-id="a4485-141">适配器每秒发送的文件发送的消息数。</span><span class="sxs-lookup"><span data-stu-id="a4485-141">Number of messages sent by the file send adapter per second.</span></span> <span data-ttu-id="a4485-142">计数器仅应用于已完全写入文件系统的消息。</span><span class="sxs-lookup"><span data-stu-id="a4485-142">The counter applies only to messages that have been completely written to file system.</span></span>|  
  
## <a name="to-access-performance-counters"></a><span data-ttu-id="a4485-143">若要访问性能计数器</span><span class="sxs-lookup"><span data-stu-id="a4485-143">To access performance counters</span></span>  
 <span data-ttu-id="a4485-144">使用以下步骤访问性能计数器。</span><span class="sxs-lookup"><span data-stu-id="a4485-144">Use the following steps to access the performance counters.</span></span>  
  
#### <a name="if-you-are-using-windows-2008"></a><span data-ttu-id="a4485-145">如果您使用的 Windows 2008</span><span class="sxs-lookup"><span data-stu-id="a4485-145">If you are using Windows 2008</span></span>  
  
1.  <span data-ttu-id="a4485-146">单击**启动**，依次指向**管理工具**，然后单击**性能监视器**。</span><span class="sxs-lookup"><span data-stu-id="a4485-146">Click **Start**, point to **Administrative Tools**, and then click **Performance Monitor**.</span></span>  
  
2.  <span data-ttu-id="a4485-147">在中**性能监视器**对话框框中，展开**监视工具**，选择**性能监视器**，然后单击**添加**。</span><span class="sxs-lookup"><span data-stu-id="a4485-147">In the **Performance Monitor** dialog box, expand **Monitoring Tools**, select **Performance Monitor**, and then click **Add**.</span></span>  
  
3.  <span data-ttu-id="a4485-148">在中**添加计数器**对话框中，从**可用的计数器**列表中，展开**biztalk: File**性能计数器对象，然后选择要监视的计数器</span><span class="sxs-lookup"><span data-stu-id="a4485-148">In the **Add Counters** dialog box, from the **Available Counters** list, expand the **BizTalk:FILE** performance counter object and select the counters to be monitored</span></span>  
  
4.  <span data-ttu-id="a4485-149">在中**选定对象的实例**列表中，选择要监视的所选的计数器，然后单击的特定实例**添加**。</span><span class="sxs-lookup"><span data-stu-id="a4485-149">In the **Instances of Selected object** list, select the specific instances to be monitored for the selected counters and then click **Add**.</span></span>  <span data-ttu-id="a4485-150">若要选择的所有可用的计数器实例，请选择\<**所有实例**\>。</span><span class="sxs-lookup"><span data-stu-id="a4485-150">To select all available counter instances, select \<**All instances**\>.</span></span>  
  
5.  <span data-ttu-id="a4485-151">添加计数器之后, 单击**确定**。</span><span class="sxs-lookup"><span data-stu-id="a4485-151">After adding the counters, click **OK**.</span></span>  
  
     <span data-ttu-id="a4485-152">所选的性能计数器随即显示在**性能监视器**屏幕。</span><span class="sxs-lookup"><span data-stu-id="a4485-152">The selected performance counters appear on the **Performance Monitor** screen.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a4485-153">请参阅</span><span class="sxs-lookup"><span data-stu-id="a4485-153">See Also</span></span>  
 [<span data-ttu-id="a4485-154">规划可持续性能</span><span class="sxs-lookup"><span data-stu-id="a4485-154">Planning for Sustained Performance</span></span>](../core/planning-for-sustained-performance.md)