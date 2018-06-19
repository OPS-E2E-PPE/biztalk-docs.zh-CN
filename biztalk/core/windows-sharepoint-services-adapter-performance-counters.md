---
title: Windows SharePoint Services 适配器性能计数器 |Microsoft 文档
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 41583fde-530a-4070-9647-f1ab6273aadf
caps.latest.revision: 9
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 1af70299f5e308d1fc40fa6206f0ebfabff22a06
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/28/2017
ms.locfileid: "25973283"
---
# <a name="windows-sharepoint-services-adapter-performance-counters"></a><span data-ttu-id="1405a-102">Windows SharePoint Services 适配器性能计数器</span><span class="sxs-lookup"><span data-stu-id="1405a-102">Windows SharePoint Services Adapter Performance Counters</span></span>
<span data-ttu-id="1405a-103">使用性能计数器可以监视服务在站点或系统上执行的工作的特定方面。</span><span class="sxs-lookup"><span data-stu-id="1405a-103">Performance counters allow you to monitor specific aspects of work performed on the site or system by service.</span></span> <span data-ttu-id="1405a-104">性能计数器能够帮助您标识和解决有关服务器性能的问题。</span><span class="sxs-lookup"><span data-stu-id="1405a-104">Performance counters can help you identify and troubleshoot server performance issues.</span></span>  
  
 <span data-ttu-id="1405a-105">以下性能计数器进行访问每个主机实例下**biztalk: Windows Sharepoint Services Adapter**性能对象类别：</span><span class="sxs-lookup"><span data-stu-id="1405a-105">The following performance counters are accessible for each host instance under the **BizTalk:Windows Sharepoint Services Adapter** performance object category:</span></span>  
  
|<span data-ttu-id="1405a-106">**类别**</span><span class="sxs-lookup"><span data-stu-id="1405a-106">**Category**</span></span>|<span data-ttu-id="1405a-107">**计数器**</span><span class="sxs-lookup"><span data-stu-id="1405a-107">**Counter**</span></span>|<span data-ttu-id="1405a-108">**Description**</span><span class="sxs-lookup"><span data-stu-id="1405a-108">**Description**</span></span>|  
|------------------|-----------------|---------------------|  
|<span data-ttu-id="1405a-109">BizTalk:Windows SharePoint Services Adapter</span><span class="sxs-lookup"><span data-stu-id="1405a-109">BizTalk:Windows Sharepoint Services Adapter</span></span>|<span data-ttu-id="1405a-110">% Receive Message Failures</span><span class="sxs-lookup"><span data-stu-id="1405a-110">% Receive Message Failures</span></span>|<span data-ttu-id="1405a-111">由于接收错误而未经 BizTalk Server 处理的 Windows SharePoint Services 文件的百分比。</span><span class="sxs-lookup"><span data-stu-id="1405a-111">The percentage of Windows SharePoint Services files that have not been processed by BizTalk Server due to receive errors.</span></span>|  
||<span data-ttu-id="1405a-112">% Send Message Failures</span><span class="sxs-lookup"><span data-stu-id="1405a-112">% Send Message Failures</span></span>|<span data-ttu-id="1405a-113">BizTalk Server 尝试发往 Windows SharePoint Services 的失败消息的百分比。</span><span class="sxs-lookup"><span data-stu-id="1405a-113">The percentage of failed messages BizTalk Server attempted to send to Windows SharePoint Services.</span></span>|  
||<span data-ttu-id="1405a-114">% Web Service Call Failures</span><span class="sxs-lookup"><span data-stu-id="1405a-114">% Web Service Call Failures</span></span>|<span data-ttu-id="1405a-115">Windows SharePoint Services 适配器 Web Services 调用失败的百分比。</span><span class="sxs-lookup"><span data-stu-id="1405a-115">The percentage of Windows SharePoint Services adapter Web service calls that have failed.</span></span>|  
||<span data-ttu-id="1405a-116">Total Receive Commit Failures</span><span class="sxs-lookup"><span data-stu-id="1405a-116">Total Receive Commit Failures</span></span>|<span data-ttu-id="1405a-117">更新 SharePoint 文档状态时引发的 Windows SharePoint Services 错误的总数。</span><span class="sxs-lookup"><span data-stu-id="1405a-117">The total number of Windows SharePoint Services errors that were raised when updating the status of the SharePoint documents.</span></span>|  
||<span data-ttu-id="1405a-118">Total Receive Message Failures</span><span class="sxs-lookup"><span data-stu-id="1405a-118">Total Receive Message Failures</span></span>|<span data-ttu-id="1405a-119">由于错误而未经 BizTalk Server 处理的已接收 Windows SharePoint Services 文件的总数。</span><span class="sxs-lookup"><span data-stu-id="1405a-119">The total number of Windows SharePoint Services files received that have not been processed by BizTalk Server due to errors.</span></span>|  
||<span data-ttu-id="1405a-120">Total Received Messages</span><span class="sxs-lookup"><span data-stu-id="1405a-120">Total Received Messages</span></span>|<span data-ttu-id="1405a-121">Windows SharePoint Services 适配器接收的 Windows SharePoint Services 文件的总数，其中包括无法处理的文件。</span><span class="sxs-lookup"><span data-stu-id="1405a-121">The total number of Windows SharePoint Services files received by the Windows SharePoint Services adapter, including files that failed to process.</span></span>|  
||<span data-ttu-id="1405a-122">Total Send Message Failures</span><span class="sxs-lookup"><span data-stu-id="1405a-122">Total Send Message Failures</span></span>|<span data-ttu-id="1405a-123">BizTalk Server 尝试发往 Windows SharePoint Services 的失败消息的总数。</span><span class="sxs-lookup"><span data-stu-id="1405a-123">The total number of failed messages BizTalk Server attempted to send to Windows SharePoint Services.</span></span>|  
||<span data-ttu-id="1405a-124">Total Sent Messages</span><span class="sxs-lookup"><span data-stu-id="1405a-124">Total Sent Messages</span></span>|<span data-ttu-id="1405a-125">BizTalk Server 发往 Windows SharePoint Services 的消息总数，其中包括无法处理的文件。</span><span class="sxs-lookup"><span data-stu-id="1405a-125">The total number of messages BizTalk Server sent to Windows SharePoint Services, including files that failed to process.</span></span>|  
||<span data-ttu-id="1405a-126">Total Web Service Call Failures</span><span class="sxs-lookup"><span data-stu-id="1405a-126">Total Web Service Call Failures</span></span>|<span data-ttu-id="1405a-127">Windows SharePoint Services 适配器 Web Services 调用失败的总数。</span><span class="sxs-lookup"><span data-stu-id="1405a-127">The total number of Windows SharePoint Services adapter Web service calls that have failed.</span></span>|  
||<span data-ttu-id="1405a-128">Web Service Calls per Second</span><span class="sxs-lookup"><span data-stu-id="1405a-128">Web Service Calls per Second</span></span>|<span data-ttu-id="1405a-129">Windows SharePoint Services 适配器 Web Services 的每秒调用数。</span><span class="sxs-lookup"><span data-stu-id="1405a-129">The number of Windows SharePoint Services adapter Web service calls per second.</span></span>|  
  
## <a name="to-access-performance-counters"></a><span data-ttu-id="1405a-130">访问性能计数器</span><span class="sxs-lookup"><span data-stu-id="1405a-130">To access performance counters</span></span>  
 <span data-ttu-id="1405a-131">依照下述步骤访问性能计数器。</span><span class="sxs-lookup"><span data-stu-id="1405a-131">Use the following steps to access the performance counters.</span></span>  
  
#### <a name="if-you-are-using-windows-2008"></a><span data-ttu-id="1405a-132">如果您使用的是 Windows 2008</span><span class="sxs-lookup"><span data-stu-id="1405a-132">If you are using Windows 2008</span></span>  
  
1.  <span data-ttu-id="1405a-133">单击**启动**，指向**管理工具**，然后单击**性能监视器**。</span><span class="sxs-lookup"><span data-stu-id="1405a-133">Click **Start**, point to **Administrative Tools**, and then click **Performance Monitor**.</span></span>  
  
2.  <span data-ttu-id="1405a-134">在**性能监视器**对话框框中，展开**监视工具**，选择**性能监视器**，然后单击**添加**。</span><span class="sxs-lookup"><span data-stu-id="1405a-134">In the **Performance Monitor** dialog box, expand **Monitoring Tools**, select **Performance Monitor**, and then click **Add**.</span></span>  
  
3.  <span data-ttu-id="1405a-135">在**添加计数器**对话框中，从**可用计数器**列表中，展开**biztalk: Windows Sharepoint Services Adapter**性能计数器对象，并选择要监视的计数器</span><span class="sxs-lookup"><span data-stu-id="1405a-135">In the **Add Counters** dialog box, from the **Available Counters** list, expand the **BizTalk:Windows Sharepoint Services Adapter** performance counter object and select the counters to be monitored</span></span>  
  
4.  <span data-ttu-id="1405a-136">在**实例的所选对象**列表中，选择要监视的所选计数器，然后单击的特定实例**添加**。</span><span class="sxs-lookup"><span data-stu-id="1405a-136">In the **Instances of Selected object** list, select the specific instances to be monitored for the selected counters and then click **Add**.</span></span>  <span data-ttu-id="1405a-137">若要选择的所有可用的计数器实例，选择\<**所有实例**\>。</span><span class="sxs-lookup"><span data-stu-id="1405a-137">To select all available counter instances, select \<**All instances**\>.</span></span>  
  
5.  <span data-ttu-id="1405a-138">添加计数器后, 单击**确定**。</span><span class="sxs-lookup"><span data-stu-id="1405a-138">After adding the counters, click **OK**.</span></span>  
  
     <span data-ttu-id="1405a-139">所选的性能计数器显示在**性能监视器**屏幕。</span><span class="sxs-lookup"><span data-stu-id="1405a-139">The selected performance counters appear on the **Performance Monitor** screen.</span></span>