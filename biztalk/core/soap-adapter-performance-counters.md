---
title: "SOAP 适配器性能计数器 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 40b54d4e-0a2e-483f-982a-97ab9fb59202
caps.latest.revision: "10"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 870a3333ce638200c92125f08a4f048150584b51
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="soap-adapter-performance-counters"></a><span data-ttu-id="4d875-102">SOAP 适配器性能计数器</span><span class="sxs-lookup"><span data-stu-id="4d875-102">SOAP Adapter Performance Counters</span></span>
<span data-ttu-id="4d875-103">使用性能计数器可以监视服务在站点或系统上执行的工作的特定方面。</span><span class="sxs-lookup"><span data-stu-id="4d875-103">Performance counters allow you to monitor specific aspects of work performed on the site or system by service.</span></span> <span data-ttu-id="4d875-104">性能计数器能够帮助您标识和解决有关服务器性能的问题。</span><span class="sxs-lookup"><span data-stu-id="4d875-104">Performance counters can help you identify and troubleshoot server performance issues.</span></span>  
  
 <span data-ttu-id="4d875-105">以下性能计数器进行访问每个主机实例下**BizTalk:SOAP 接收适配器**和**BizTalk:SOAP 发送适配器**性能对象类别：</span><span class="sxs-lookup"><span data-stu-id="4d875-105">The following performance counters are accessible for each host instance under the **BizTalk:SOAP Receive Adapter** and the **BizTalk:SOAP Send Adapter** performance object categories:</span></span>  
  
|<span data-ttu-id="4d875-106">**类别**</span><span class="sxs-lookup"><span data-stu-id="4d875-106">**Category**</span></span>|<span data-ttu-id="4d875-107">**计数器**</span><span class="sxs-lookup"><span data-stu-id="4d875-107">**Counter**</span></span>|<span data-ttu-id="4d875-108">**Description**</span><span class="sxs-lookup"><span data-stu-id="4d875-108">**Description**</span></span>|  
|------------------|-----------------|---------------------|  
|<span data-ttu-id="4d875-109">BizTalk:SOAP Receive Adapter</span><span class="sxs-lookup"><span data-stu-id="4d875-109">BizTalk:SOAP Receive Adapter</span></span>|<span data-ttu-id="4d875-110">收到的消息</span><span class="sxs-lookup"><span data-stu-id="4d875-110">Messages received</span></span>|<span data-ttu-id="4d875-111">SOAP 接收适配器接收到的消息总数。</span><span class="sxs-lookup"><span data-stu-id="4d875-111">Total number of messages received by the SOAP receive adapter.</span></span> <span data-ttu-id="4d875-112">SOAP 接收适配器从 SOAP 客户端完整读取一个请求消息后，该计数器的值才会增加。</span><span class="sxs-lookup"><span data-stu-id="4d875-112">The counter is incremented after a request message is completely read by the adapter from the SOAP client.</span></span>|  
||<span data-ttu-id="4d875-113">每秒接收的消息数</span><span class="sxs-lookup"><span data-stu-id="4d875-113">Messages received/Sec</span></span>|<span data-ttu-id="4d875-114">SOAP 接收适配器每秒接收到的消息数。</span><span class="sxs-lookup"><span data-stu-id="4d875-114">Number of messages received by the SOAP receive adapter per second.</span></span> <span data-ttu-id="4d875-115">该计数器只计入 SOAP 接收适配器从 SOAP 客户端中完整读取的请求消息。</span><span class="sxs-lookup"><span data-stu-id="4d875-115">The counter applies only to request messages that have been completely read by the adapter from the SOAP client.</span></span>|  
|<span data-ttu-id="4d875-116">BizTalk:SOAP Send Adapter</span><span class="sxs-lookup"><span data-stu-id="4d875-116">BizTalk:SOAP Send Adapter</span></span>|<span data-ttu-id="4d875-117">发送的消息</span><span class="sxs-lookup"><span data-stu-id="4d875-117">Messages sent</span></span>|<span data-ttu-id="4d875-118">SOAP 发送适配器发送的消息总数。</span><span class="sxs-lookup"><span data-stu-id="4d875-118">Total number of messages sent by the SOAP send adapter.</span></span> <span data-ttu-id="4d875-119">此计数器只对已到达目标 URL 的消息时递增。</span><span class="sxs-lookup"><span data-stu-id="4d875-119">The counter is incremented only for messages that have reached the destination URL.</span></span>|  
||<span data-ttu-id="4d875-120">每秒发送的消息数</span><span class="sxs-lookup"><span data-stu-id="4d875-120">Messages sent/Sec</span></span>|<span data-ttu-id="4d875-121">SOAP 发送适配器每秒发送的消息数。</span><span class="sxs-lookup"><span data-stu-id="4d875-121">Number of messages sent by the SOAP send adapter per second.</span></span> <span data-ttu-id="4d875-122">该计数器只计入已到达目标 URL 的消息。</span><span class="sxs-lookup"><span data-stu-id="4d875-122">The counter applies only to messages that have reached the destination URL.</span></span>|  
  
## <a name="to-access-performance-counters"></a><span data-ttu-id="4d875-123">访问性能计数器</span><span class="sxs-lookup"><span data-stu-id="4d875-123">To access performance counters</span></span>  
 <span data-ttu-id="4d875-124">依照下述步骤访问性能计数器。</span><span class="sxs-lookup"><span data-stu-id="4d875-124">Use the following steps to access the performance counters.</span></span>  
  
#### <a name="if-you-are-using-windows-server-2008"></a><span data-ttu-id="4d875-125">如果您使用的是 Windows Server 2008</span><span class="sxs-lookup"><span data-stu-id="4d875-125">If you are using Windows Server 2008</span></span>  
  
1.  <span data-ttu-id="4d875-126">单击**启动**，指向**管理工具**，然后单击**性能监视器**。</span><span class="sxs-lookup"><span data-stu-id="4d875-126">Click **Start**, point to **Administrative Tools**, and then click **Performance Monitor**.</span></span>  
  
2.  <span data-ttu-id="4d875-127">在**性能监视器**对话框框中，展开**监视工具**，选择**性能监视器**，然后单击**添加**。</span><span class="sxs-lookup"><span data-stu-id="4d875-127">In the **Performance Monitor** dialog box, expand **Monitoring Tools**, select **Performance Monitor**, and then click **Add**.</span></span>  
  
3.  <span data-ttu-id="4d875-128">在**添加计数器**对话框中，从**可用计数器**列表中，展开**BizTalk:SOAP**性能计数器对象，然后选择要监视的计数器</span><span class="sxs-lookup"><span data-stu-id="4d875-128">In the **Add Counters** dialog box, from the **Available Counters** list, expand the **BizTalk:SOAP** performance counter object and select the counters to be monitored</span></span>  
  
4.  <span data-ttu-id="4d875-129">在**实例的所选对象**列表中，选择要监视的所选计数器，然后单击的特定实例**添加**。</span><span class="sxs-lookup"><span data-stu-id="4d875-129">In the **Instances of Selected object** list, select the specific instances to be monitored for the selected counters and then click **Add**.</span></span> <span data-ttu-id="4d875-130">若要选择的所有可用的计数器实例，选择\<**所有实例**>。</span><span class="sxs-lookup"><span data-stu-id="4d875-130">To select all available counter instances, select \<**All instances**>.</span></span>  
  
5.  <span data-ttu-id="4d875-131">添加计数器后, 单击**确定**。</span><span class="sxs-lookup"><span data-stu-id="4d875-131">After adding the counters, click **OK**.</span></span>  
  
     <span data-ttu-id="4d875-132">所选的性能计数器显示在**性能监视器**屏幕。</span><span class="sxs-lookup"><span data-stu-id="4d875-132">The selected performance counters appear on the **Performance Monitor** screen.</span></span>