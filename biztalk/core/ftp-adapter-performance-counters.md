---
title: "FTP 适配器性能计数器 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: ca5cbe67-9aa3-4194-816e-fab4eb551c07
caps.latest.revision: "12"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 5dad67f24f37f661e26f4cb56895c6bcad6b0782
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/28/2017
---
# <a name="ftp-adapter-performance-counters"></a><span data-ttu-id="844a6-102">FTP 适配器性能计数器</span><span class="sxs-lookup"><span data-stu-id="844a6-102">FTP Adapter Performance Counters</span></span>
<span data-ttu-id="844a6-103">使用性能计数器可以监视服务在站点或系统上执行的工作的特定方面。</span><span class="sxs-lookup"><span data-stu-id="844a6-103">Performance counters allow you to monitor specific aspects of work performed on the site or system by service.</span></span> <span data-ttu-id="844a6-104">性能计数器能够帮助您标识和解决有关服务器性能的问题。</span><span class="sxs-lookup"><span data-stu-id="844a6-104">Performance counters can help you identify and troubleshoot server performance issues.</span></span>  
  
 <span data-ttu-id="844a6-105">以下性能计数器进行访问每个主机实例下**BizTalk:FTP 接收适配器**和**BizTalk:FTP 发送适配器**性能对象类别：</span><span class="sxs-lookup"><span data-stu-id="844a6-105">The following performance counters are accessible for each host instance under the **BizTalk:FTP Receive Adapter** and the **BizTalk:FTP Send Adapter** performance object categories:</span></span>  
  
|<span data-ttu-id="844a6-106">**类别**</span><span class="sxs-lookup"><span data-stu-id="844a6-106">**Category**</span></span>|<span data-ttu-id="844a6-107">**计数器**</span><span class="sxs-lookup"><span data-stu-id="844a6-107">**Counter**</span></span>|<span data-ttu-id="844a6-108">**Description**</span><span class="sxs-lookup"><span data-stu-id="844a6-108">**Description**</span></span>|  
|------------------|-----------------|---------------------|  
|<span data-ttu-id="844a6-109">BizTalk:FTP Receive Adapter</span><span class="sxs-lookup"><span data-stu-id="844a6-109">BizTalk:FTP Receive Adapter</span></span>|<span data-ttu-id="844a6-110">Bytes received</span><span class="sxs-lookup"><span data-stu-id="844a6-110">Bytes received</span></span>|<span data-ttu-id="844a6-111">FTP 接收适配器接收到的字节总数。</span><span class="sxs-lookup"><span data-stu-id="844a6-111">Total number of bytes received by the FTP receive adapter.</span></span> <span data-ttu-id="844a6-112">FTP 接收适配器从 FTP 服务器中完整读取一个消息后，该计数器的值才会增加。</span><span class="sxs-lookup"><span data-stu-id="844a6-112">The counter is incremented after a message is completely read by the FTP receive adapter from the FTP server.</span></span>|  
||<span data-ttu-id="844a6-113">Bytes received/Sec</span><span class="sxs-lookup"><span data-stu-id="844a6-113">Bytes received/Sec</span></span>|<span data-ttu-id="844a6-114">FTP 接收适配器每秒接收到的字节数。</span><span class="sxs-lookup"><span data-stu-id="844a6-114">Number of bytes received by the FTP receive adapter per second.</span></span> <span data-ttu-id="844a6-115">该计数器只计入 FTP 接收适配器已从 FTP 服务器中完整读取的消息。</span><span class="sxs-lookup"><span data-stu-id="844a6-115">The counter applies only to messages that have been completely read by the FTP receive adapter from the FTP server.</span></span>|  
||<span data-ttu-id="844a6-116">收到的消息</span><span class="sxs-lookup"><span data-stu-id="844a6-116">Messages received</span></span>|<span data-ttu-id="844a6-117">FTP 接收适配器接收到的消息总数。</span><span class="sxs-lookup"><span data-stu-id="844a6-117">Total number of messages received by the FTP receive adapter.</span></span> <span data-ttu-id="844a6-118">FTP 接收适配器从 FTP 服务器中完整读取一个消息后，该计数器的值才会增加。</span><span class="sxs-lookup"><span data-stu-id="844a6-118">The counter is incremented after a message is completely read by the FTP receive adapter from the FTP server.</span></span>|  
||<span data-ttu-id="844a6-119">每秒接收的消息数</span><span class="sxs-lookup"><span data-stu-id="844a6-119">Messages received/Sec</span></span>|<span data-ttu-id="844a6-120">FTP 接收适配器每秒接收到的消息数。</span><span class="sxs-lookup"><span data-stu-id="844a6-120">Number of messages received by the FTP receive adapter per second.</span></span> <span data-ttu-id="844a6-121">该计数器只计入 FTP 接收适配器已从 FTP 服务器中完整读取的消息。</span><span class="sxs-lookup"><span data-stu-id="844a6-121">The counter applies only to messages that have been completely read by the FTP receive adapter from the FTP server.</span></span>|  
|<span data-ttu-id="844a6-122">BizTalk:FTP Send Adapter</span><span class="sxs-lookup"><span data-stu-id="844a6-122">BizTalk:FTP Send Adapter</span></span>|<span data-ttu-id="844a6-123">Bytes sent</span><span class="sxs-lookup"><span data-stu-id="844a6-123">Bytes sent</span></span>|<span data-ttu-id="844a6-124">FTP 发送适配器发送的字节总数。</span><span class="sxs-lookup"><span data-stu-id="844a6-124">Total number of bytes sent by the FTP send adapter.</span></span> <span data-ttu-id="844a6-125">此计数器只对已写入到目标 FTP 服务器的消息时递增。</span><span class="sxs-lookup"><span data-stu-id="844a6-125">The counter is incremented only for messages that have been written to the destination FTP server.</span></span>|  
||<span data-ttu-id="844a6-126">Bytes sent/Sec</span><span class="sxs-lookup"><span data-stu-id="844a6-126">Bytes sent/Sec</span></span>|<span data-ttu-id="844a6-127">FTP 发送适配器每秒发送的字节数。</span><span class="sxs-lookup"><span data-stu-id="844a6-127">Number of bytes sent by the FTP send adapter per second.</span></span> <span data-ttu-id="844a6-128">计数器仅适用于已写入到目标 FTP 服务器的消息。</span><span class="sxs-lookup"><span data-stu-id="844a6-128">The counter applies only to messages that have been written to the destination FTP server.</span></span>|  
||<span data-ttu-id="844a6-129">发送的消息</span><span class="sxs-lookup"><span data-stu-id="844a6-129">Messages sent</span></span>|<span data-ttu-id="844a6-130">FTP 发送适配器已发送的消息总数。</span><span class="sxs-lookup"><span data-stu-id="844a6-130">Total number of messages sent by the FTP send adapter.</span></span> <span data-ttu-id="844a6-131">此计数器只对已写入到目标 FTP 服务器的消息时递增。</span><span class="sxs-lookup"><span data-stu-id="844a6-131">The counter is incremented only for messages that have been written to the destination FTP server.</span></span>|  
||<span data-ttu-id="844a6-132">每秒发送的消息数</span><span class="sxs-lookup"><span data-stu-id="844a6-132">Messages sent/Sec</span></span>|<span data-ttu-id="844a6-133">FTP 发送适配器每秒发送的消息数。</span><span class="sxs-lookup"><span data-stu-id="844a6-133">Number of messages sent by the FTP send adapter per second.</span></span> <span data-ttu-id="844a6-134">该计数器只计入已写入目标 FTP 服务器的消息。</span><span class="sxs-lookup"><span data-stu-id="844a6-134">The counter applies only to messages that have been written to destination FTP server.</span></span>|  
  
## <a name="to-access-performance-counters"></a><span data-ttu-id="844a6-135">访问性能计数器</span><span class="sxs-lookup"><span data-stu-id="844a6-135">To access performance counters</span></span>  
 <span data-ttu-id="844a6-136">依照下述步骤访问性能计数器。</span><span class="sxs-lookup"><span data-stu-id="844a6-136">Use the following steps to access the performance counters.</span></span>  
  
#### <a name="if-you-are-using-windows-2008"></a><span data-ttu-id="844a6-137">如果您使用的是 Windows 2008</span><span class="sxs-lookup"><span data-stu-id="844a6-137">If you are using Windows 2008</span></span>  
  
1.  <span data-ttu-id="844a6-138">单击**启动**，指向**管理工具**，然后单击**性能监视器**。</span><span class="sxs-lookup"><span data-stu-id="844a6-138">Click **Start**, point to **Administrative Tools**, and then click **Performance Monitor**.</span></span>  
  
2.  <span data-ttu-id="844a6-139">在**性能监视器**对话框框中，展开**监视工具**，选择**性能监视器**，然后单击**添加**。</span><span class="sxs-lookup"><span data-stu-id="844a6-139">In the **Performance Monitor** dialog box, expand **Monitoring Tools**, select **Performance Monitor**, and then click **Add**.</span></span>  
  
3.  <span data-ttu-id="844a6-140">在**添加计数器**对话框中，从**可用计数器**列表中，展开**BizTalk:FTP**性能计数器对象，然后选择要监视的计数器</span><span class="sxs-lookup"><span data-stu-id="844a6-140">In the **Add Counters** dialog box, from the **Available Counters** list, expand the **BizTalk:FTP** performance counter object and select the counters to be monitored</span></span>  
  
4.  <span data-ttu-id="844a6-141">在**实例的所选对象**列表中，选择要监视的所选计数器，然后单击的特定实例**添加**。</span><span class="sxs-lookup"><span data-stu-id="844a6-141">In the **Instances of Selected object** list, select the specific instances to be monitored for the selected counters and then click **Add**.</span></span>  <span data-ttu-id="844a6-142">若要选择的所有可用的计数器实例，选择\<**所有实例**\>。</span><span class="sxs-lookup"><span data-stu-id="844a6-142">To select all available counter instances, select \<**All instances**\>.</span></span>  
  
5.  <span data-ttu-id="844a6-143">添加计数器后, 单击**确定**。</span><span class="sxs-lookup"><span data-stu-id="844a6-143">After adding the counters, click **OK**.</span></span>  
  
     <span data-ttu-id="844a6-144">所选的性能计数器显示在**性能监视器**屏幕。</span><span class="sxs-lookup"><span data-stu-id="844a6-144">The selected performance counters appear on the **Performance Monitor** screen.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="844a6-145">另请参阅</span><span class="sxs-lookup"><span data-stu-id="844a6-145">See Also</span></span>  
 <span data-ttu-id="844a6-146">[监视 BizTalk Server](../core/monitoring-biztalk-server.md) [运行在群集主机内的适配器处理程序的注意事项](../core/considerations-for-running-adapter-handlers-within-a-clustered-host1.md)</span><span class="sxs-lookup"><span data-stu-id="844a6-146">[Monitoring BizTalk Server](../core/monitoring-biztalk-server.md) [Considerations for Running Adapter Handlers within a Clustered Host](../core/considerations-for-running-adapter-handlers-within-a-clustered-host1.md)</span></span>