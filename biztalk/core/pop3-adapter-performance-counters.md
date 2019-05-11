---
title: POP3 适配器性能计数器 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: f799175e-e9e7-4937-93bd-aaec1c43b75a
caps.latest.revision: 10
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 87aaff170c75395b96b8d8d36d6efec6693e38ba
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65394918"
---
# <a name="pop3-adapter-performance-counters"></a><span data-ttu-id="8c6ea-102">POP3 适配器性能计数器</span><span class="sxs-lookup"><span data-stu-id="8c6ea-102">POP3 Adapter Performance Counters</span></span>
<span data-ttu-id="8c6ea-103">性能计数器允许你监视的工作上的站点或系统服务执行的特定方面。</span><span class="sxs-lookup"><span data-stu-id="8c6ea-103">Performance counters allow you to monitor specific aspects of work performed on the site or system by service.</span></span> <span data-ttu-id="8c6ea-104">性能计数器可以帮助您确定和解决服务器性能问题。</span><span class="sxs-lookup"><span data-stu-id="8c6ea-104">Performance counters can help you identify and troubleshoot server performance issues.</span></span>  
  
 <span data-ttu-id="8c6ea-105">以下性能计数器都可以访问每个主机实例下**BizTalk:POP3 Receive Adapter**性能对象类别：</span><span class="sxs-lookup"><span data-stu-id="8c6ea-105">The following performance counters are accessible for each host instance under the **BizTalk:POP3 Receive Adapter** performance object category:</span></span>  
  
|<span data-ttu-id="8c6ea-106">**类别**</span><span class="sxs-lookup"><span data-stu-id="8c6ea-106">**Category**</span></span>|<span data-ttu-id="8c6ea-107">**计数器**</span><span class="sxs-lookup"><span data-stu-id="8c6ea-107">**Counter**</span></span>|<span data-ttu-id="8c6ea-108">**说明**</span><span class="sxs-lookup"><span data-stu-id="8c6ea-108">**Description**</span></span>|  
|------------------|-----------------|---------------------|  
|<span data-ttu-id="8c6ea-109">BizTalk:POP3 Receive Adapter</span><span class="sxs-lookup"><span data-stu-id="8c6ea-109">BizTalk:POP3 Receive Adapter</span></span>|<span data-ttu-id="8c6ea-110">Active sessions</span><span class="sxs-lookup"><span data-stu-id="8c6ea-110">Active sessions</span></span>|<span data-ttu-id="8c6ea-111">同时管理 POP3 适配器的打开 POP3 连接的数目。</span><span class="sxs-lookup"><span data-stu-id="8c6ea-111">Number of open POP3 connections the POP3 adapter is managing at a time.</span></span>|  
||<span data-ttu-id="8c6ea-112">接收的字节数</span><span class="sxs-lookup"><span data-stu-id="8c6ea-112">Bytes received</span></span>|<span data-ttu-id="8c6ea-113">POP3 适配器从邮件服务器下载的字节的总数。</span><span class="sxs-lookup"><span data-stu-id="8c6ea-113">Total number of bytes downloaded by the POP3 adapter from a mail server.</span></span>|  
||<span data-ttu-id="8c6ea-114">接收的字节数/秒</span><span class="sxs-lookup"><span data-stu-id="8c6ea-114">Bytes receive/Sec</span></span>|<span data-ttu-id="8c6ea-115">POP3 适配器从邮件服务器每秒下载的字节数。</span><span class="sxs-lookup"><span data-stu-id="8c6ea-115">Number of bytes downloaded by the POP3 adapter from a mail server per second.</span></span>|  
||<span data-ttu-id="8c6ea-116">接收的消息</span><span class="sxs-lookup"><span data-stu-id="8c6ea-116">Messages received</span></span>|<span data-ttu-id="8c6ea-117">POP3 适配器从邮件服务器下载的电子邮件消息的总数。</span><span class="sxs-lookup"><span data-stu-id="8c6ea-117">Total number of email messages downloaded by the POP3 adapter from a mail server.</span></span>|  
||<span data-ttu-id="8c6ea-118">收到的消息数/秒</span><span class="sxs-lookup"><span data-stu-id="8c6ea-118">Messages received/Sec</span></span>|<span data-ttu-id="8c6ea-119">POP3 适配器每秒从邮件服务器下载的电子邮件消息数。</span><span class="sxs-lookup"><span data-stu-id="8c6ea-119">Number of email messages downloaded by the POP3 adapter from mail server per second.</span></span>|  
  
## <a name="to-access-performance-counters"></a><span data-ttu-id="8c6ea-120">若要访问性能计数器</span><span class="sxs-lookup"><span data-stu-id="8c6ea-120">To access performance counters</span></span>  
 <span data-ttu-id="8c6ea-121">请执行以下步骤访问 POP3 适配器的性能计数器：</span><span class="sxs-lookup"><span data-stu-id="8c6ea-121">Follow these steps to access performance counters for the POP3 adapter:</span></span>  
  
#### <a name="if-you-are-using-windows-2008"></a><span data-ttu-id="8c6ea-122">如果您使用的 Windows 2008</span><span class="sxs-lookup"><span data-stu-id="8c6ea-122">If you are using Windows 2008</span></span>  
  
1.  <span data-ttu-id="8c6ea-123">单击**启动**，依次指向**管理工具**，然后单击**性能监视器**。</span><span class="sxs-lookup"><span data-stu-id="8c6ea-123">Click **Start**, point to **Administrative Tools**, and then click **Performance Monitor**.</span></span>  
  
2.  <span data-ttu-id="8c6ea-124">在中**性能监视器**对话框框中，展开**监视工具**，选择**性能监视器**，然后单击**添加**。</span><span class="sxs-lookup"><span data-stu-id="8c6ea-124">In the **Performance Monitor** dialog box, expand **Monitoring Tools**, select **Performance Monitor**, and then click **Add**.</span></span>  
  
3.  <span data-ttu-id="8c6ea-125">在中**添加计数器**对话框中，从**可用的计数器**列表中，展开**BizTalk:POP3 Receive Adapter**性能计数器对象，然后选择要进行的计数器监视</span><span class="sxs-lookup"><span data-stu-id="8c6ea-125">In the **Add Counters** dialog box, from the **Available Counters** list, expand the **BizTalk:POP3 Receive Adapter** performance counter object and select the counters to be monitored</span></span>  
  
4.  <span data-ttu-id="8c6ea-126">在中**选定对象的实例**列表中，选择要监视的所选的计数器，然后单击的特定实例**添加**。</span><span class="sxs-lookup"><span data-stu-id="8c6ea-126">In the **Instances of Selected object** list, select the specific instances to be monitored for the selected counters and then click **Add**.</span></span>  <span data-ttu-id="8c6ea-127">若要选择的所有可用的计数器实例，请选择\<**所有实例**\>。</span><span class="sxs-lookup"><span data-stu-id="8c6ea-127">To select all available counter instances, select \<**All instances**\>.</span></span>  
  
5.  <span data-ttu-id="8c6ea-128">添加计数器之后, 单击**确定**。</span><span class="sxs-lookup"><span data-stu-id="8c6ea-128">After adding the counters, click **OK**.</span></span>  
  
     <span data-ttu-id="8c6ea-129">所选的性能计数器随即显示在**性能监视器**屏幕。</span><span class="sxs-lookup"><span data-stu-id="8c6ea-129">The selected performance counters appear on the **Performance Monitor** screen.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8c6ea-130">请参阅</span><span class="sxs-lookup"><span data-stu-id="8c6ea-130">See Also</span></span>  
 [<span data-ttu-id="8c6ea-131">监视 BizTalk Server</span><span class="sxs-lookup"><span data-stu-id="8c6ea-131">Monitoring BizTalk Server</span></span>](../core/monitoring-biztalk-server.md)  
 <span data-ttu-id="8c6ea-132">[使用 POP3 适配器处理多部分消息](../core/processing-multi-part-messages-with-the-pop3-adapter.md) </span><span class="sxs-lookup"><span data-stu-id="8c6ea-132">[Processing Multi Part Messages with the POP3 Adapter](../core/processing-multi-part-messages-with-the-pop3-adapter.md) </span></span>  
 [<span data-ttu-id="8c6ea-133">在群集主机内运行适配器处理程序的注意事项</span><span class="sxs-lookup"><span data-stu-id="8c6ea-133">Considerations for Running Adapter Handlers within a Clustered Host</span></span>](../core/considerations-for-running-adapter-handlers-within-a-clustered-host1.md)