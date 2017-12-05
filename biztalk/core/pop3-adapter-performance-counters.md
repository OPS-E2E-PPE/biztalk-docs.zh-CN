---
title: "POP3 适配器性能计数器 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: f799175e-e9e7-4937-93bd-aaec1c43b75a
caps.latest.revision: "10"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 4c53bd0a487924a50155f388b6a657541ebe8fd3
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/28/2017
---
# <a name="pop3-adapter-performance-counters"></a><span data-ttu-id="0079d-102">POP3 适配器性能计数器</span><span class="sxs-lookup"><span data-stu-id="0079d-102">POP3 Adapter Performance Counters</span></span>
<span data-ttu-id="0079d-103">使用性能计数器可以监视服务在站点或系统上执行的工作的特定方面。</span><span class="sxs-lookup"><span data-stu-id="0079d-103">Performance counters allow you to monitor specific aspects of work performed on the site or system by service.</span></span> <span data-ttu-id="0079d-104">性能计数器能够帮助您标识和解决有关服务器性能的问题。</span><span class="sxs-lookup"><span data-stu-id="0079d-104">Performance counters can help you identify and troubleshoot server performance issues.</span></span>  
  
 <span data-ttu-id="0079d-105">以下性能计数器进行访问每个主机实例下**BizTalk:POP3 接收适配器**性能对象类别：</span><span class="sxs-lookup"><span data-stu-id="0079d-105">The following performance counters are accessible for each host instance under the **BizTalk:POP3 Receive Adapter** performance object category:</span></span>  
  
|<span data-ttu-id="0079d-106">**类别**</span><span class="sxs-lookup"><span data-stu-id="0079d-106">**Category**</span></span>|<span data-ttu-id="0079d-107">**计数器**</span><span class="sxs-lookup"><span data-stu-id="0079d-107">**Counter**</span></span>|<span data-ttu-id="0079d-108">**Description**</span><span class="sxs-lookup"><span data-stu-id="0079d-108">**Description**</span></span>|  
|------------------|-----------------|---------------------|  
|<span data-ttu-id="0079d-109">BizTalk:POP3 Receive Adapter</span><span class="sxs-lookup"><span data-stu-id="0079d-109">BizTalk:POP3 Receive Adapter</span></span>|<span data-ttu-id="0079d-110">Active sessions</span><span class="sxs-lookup"><span data-stu-id="0079d-110">Active sessions</span></span>|<span data-ttu-id="0079d-111">POP3 适配器同时管理的 POP3 打开连接的数量。</span><span class="sxs-lookup"><span data-stu-id="0079d-111">Number of open POP3 connections the POP3 adapter is managing at a time.</span></span>|  
||<span data-ttu-id="0079d-112">Bytes received</span><span class="sxs-lookup"><span data-stu-id="0079d-112">Bytes received</span></span>|<span data-ttu-id="0079d-113">POP3 适配器从邮件服务器下载的总字节数。</span><span class="sxs-lookup"><span data-stu-id="0079d-113">Total number of bytes downloaded by the POP3 adapter from a mail server.</span></span>|  
||<span data-ttu-id="0079d-114">Bytes receive/Sec</span><span class="sxs-lookup"><span data-stu-id="0079d-114">Bytes receive/Sec</span></span>|<span data-ttu-id="0079d-115">POP3 适配器每秒从邮件服务器下载的字节数。</span><span class="sxs-lookup"><span data-stu-id="0079d-115">Number of bytes downloaded by the POP3 adapter from a mail server per second.</span></span>|  
||<span data-ttu-id="0079d-116">收到的消息</span><span class="sxs-lookup"><span data-stu-id="0079d-116">Messages received</span></span>|<span data-ttu-id="0079d-117">POP3 适配器从邮件服务器下载的电子邮件总数。</span><span class="sxs-lookup"><span data-stu-id="0079d-117">Total number of email messages downloaded by the POP3 adapter from a mail server.</span></span>|  
||<span data-ttu-id="0079d-118">每秒接收的消息数</span><span class="sxs-lookup"><span data-stu-id="0079d-118">Messages received/Sec</span></span>|<span data-ttu-id="0079d-119">POP3 适配器每秒从邮件服务器下载的电子邮件数。</span><span class="sxs-lookup"><span data-stu-id="0079d-119">Number of email messages downloaded by the POP3 adapter from mail server per second.</span></span>|  
  
## <a name="to-access-performance-counters"></a><span data-ttu-id="0079d-120">访问性能计数器</span><span class="sxs-lookup"><span data-stu-id="0079d-120">To access performance counters</span></span>  
 <span data-ttu-id="0079d-121">依照下述步骤访问 POP3 适配器的性能计数器：</span><span class="sxs-lookup"><span data-stu-id="0079d-121">Follow these steps to access performance counters for the POP3 adapter:</span></span>  
  
#### <a name="if-you-are-using-windows-2008"></a><span data-ttu-id="0079d-122">如果您使用的是 Windows 2008</span><span class="sxs-lookup"><span data-stu-id="0079d-122">If you are using Windows 2008</span></span>  
  
1.  <span data-ttu-id="0079d-123">单击**启动**，指向**管理工具**，然后单击**性能监视器**。</span><span class="sxs-lookup"><span data-stu-id="0079d-123">Click **Start**, point to **Administrative Tools**, and then click **Performance Monitor**.</span></span>  
  
2.  <span data-ttu-id="0079d-124">在**性能监视器**对话框框中，展开**监视工具**，选择**性能监视器**，然后单击**添加**。</span><span class="sxs-lookup"><span data-stu-id="0079d-124">In the **Performance Monitor** dialog box, expand **Monitoring Tools**, select **Performance Monitor**, and then click **Add**.</span></span>  
  
3.  <span data-ttu-id="0079d-125">在**添加计数器**对话框中，从**可用计数器**列表中，展开**BizTalk:POP3 接收适配器**性能计数器对象，然后选择要将的计数器监视</span><span class="sxs-lookup"><span data-stu-id="0079d-125">In the **Add Counters** dialog box, from the **Available Counters** list, expand the **BizTalk:POP3 Receive Adapter** performance counter object and select the counters to be monitored</span></span>  
  
4.  <span data-ttu-id="0079d-126">在**实例的所选对象**列表中，选择要监视的所选计数器，然后单击的特定实例**添加**。</span><span class="sxs-lookup"><span data-stu-id="0079d-126">In the **Instances of Selected object** list, select the specific instances to be monitored for the selected counters and then click **Add**.</span></span>  <span data-ttu-id="0079d-127">若要选择的所有可用的计数器实例，选择\<**所有实例**\>。</span><span class="sxs-lookup"><span data-stu-id="0079d-127">To select all available counter instances, select \<**All instances**\>.</span></span>  
  
5.  <span data-ttu-id="0079d-128">添加计数器后, 单击**确定**。</span><span class="sxs-lookup"><span data-stu-id="0079d-128">After adding the counters, click **OK**.</span></span>  
  
     <span data-ttu-id="0079d-129">所选的性能计数器显示在**性能监视器**屏幕。</span><span class="sxs-lookup"><span data-stu-id="0079d-129">The selected performance counters appear on the **Performance Monitor** screen.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0079d-130">另请参阅</span><span class="sxs-lookup"><span data-stu-id="0079d-130">See Also</span></span>  
 [<span data-ttu-id="0079d-131">监视 BizTalk Server</span><span class="sxs-lookup"><span data-stu-id="0079d-131">Monitoring BizTalk Server</span></span>](../core/monitoring-biztalk-server.md)  
 <span data-ttu-id="0079d-132">[处理与 POP3 适配器的多部分消息](../core/processing-multi-part-messages-with-the-pop3-adapter.md) </span><span class="sxs-lookup"><span data-stu-id="0079d-132">[Processing Multi Part Messages with the POP3 Adapter](../core/processing-multi-part-messages-with-the-pop3-adapter.md) </span></span>  
 [<span data-ttu-id="0079d-133">在群集主机内运行适配器处理程序的注意事项</span><span class="sxs-lookup"><span data-stu-id="0079d-133">Considerations for Running Adapter Handlers within a Clustered Host</span></span>](../core/considerations-for-running-adapter-handlers-within-a-clustered-host1.md)