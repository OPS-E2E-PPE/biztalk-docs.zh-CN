---
title: Windows SharePoint Services 适配器性能计数器 |Microsoft Docs
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
ms.openlocfilehash: 1346bc558bd9881d9eb925856f79277a831c2665
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65240362"
---
# <a name="windows-sharepoint-services-adapter-performance-counters"></a><span data-ttu-id="8513b-102">Windows SharePoint Services 适配器性能计数器</span><span class="sxs-lookup"><span data-stu-id="8513b-102">Windows SharePoint Services Adapter Performance Counters</span></span>
<span data-ttu-id="8513b-103">性能计数器允许你监视的工作上的站点或系统服务执行的特定方面。</span><span class="sxs-lookup"><span data-stu-id="8513b-103">Performance counters allow you to monitor specific aspects of work performed on the site or system by service.</span></span> <span data-ttu-id="8513b-104">性能计数器可以帮助您确定和解决服务器性能问题。</span><span class="sxs-lookup"><span data-stu-id="8513b-104">Performance counters can help you identify and troubleshoot server performance issues.</span></span>  
  
 <span data-ttu-id="8513b-105">以下性能计数器都可以访问每个主机实例下**biztalk: Windows Sharepoint Services 适配器**性能对象类别：</span><span class="sxs-lookup"><span data-stu-id="8513b-105">The following performance counters are accessible for each host instance under the **BizTalk:Windows Sharepoint Services Adapter** performance object category:</span></span>  
  
|<span data-ttu-id="8513b-106">**类别**</span><span class="sxs-lookup"><span data-stu-id="8513b-106">**Category**</span></span>|<span data-ttu-id="8513b-107">**计数器**</span><span class="sxs-lookup"><span data-stu-id="8513b-107">**Counter**</span></span>|<span data-ttu-id="8513b-108">**说明**</span><span class="sxs-lookup"><span data-stu-id="8513b-108">**Description**</span></span>|  
|------------------|-----------------|---------------------|  
|<span data-ttu-id="8513b-109">Biztalk: Windows Sharepoint Services 适配器</span><span class="sxs-lookup"><span data-stu-id="8513b-109">BizTalk:Windows Sharepoint Services Adapter</span></span>|<span data-ttu-id="8513b-110">%接收消息失败</span><span class="sxs-lookup"><span data-stu-id="8513b-110">% Receive Message Failures</span></span>|<span data-ttu-id="8513b-111">未处理的 BizTalk Server 由于接收错误的 Windows SharePoint Services 文件的百分比。</span><span class="sxs-lookup"><span data-stu-id="8513b-111">The percentage of Windows SharePoint Services files that have not been processed by BizTalk Server due to receive errors.</span></span>|  
||<span data-ttu-id="8513b-112">%发送消息失败</span><span class="sxs-lookup"><span data-stu-id="8513b-112">% Send Message Failures</span></span>|<span data-ttu-id="8513b-113">BizTalk Server 尝试发往 Windows SharePoint Services 的失败消息的百分比。</span><span class="sxs-lookup"><span data-stu-id="8513b-113">The percentage of failed messages BizTalk Server attempted to send to Windows SharePoint Services.</span></span>|  
||<span data-ttu-id="8513b-114">%Web 服务调用失败</span><span class="sxs-lookup"><span data-stu-id="8513b-114">% Web Service Call Failures</span></span>|<span data-ttu-id="8513b-115">Windows SharePoint Services 适配器 Web services 调用失败的百分比。</span><span class="sxs-lookup"><span data-stu-id="8513b-115">The percentage of Windows SharePoint Services adapter Web service calls that have failed.</span></span>|  
||<span data-ttu-id="8513b-116">Total receive 接收提交失败</span><span class="sxs-lookup"><span data-stu-id="8513b-116">Total Receive Commit Failures</span></span>|<span data-ttu-id="8513b-117">更新的 SharePoint 文档状态时出现的 Windows SharePoint Services 错误的总数。</span><span class="sxs-lookup"><span data-stu-id="8513b-117">The total number of Windows SharePoint Services errors that were raised when updating the status of the SharePoint documents.</span></span>|  
||<span data-ttu-id="8513b-118">Total receive 接收消息失败</span><span class="sxs-lookup"><span data-stu-id="8513b-118">Total Receive Message Failures</span></span>|<span data-ttu-id="8513b-119">收到尚未处理由 BizTalk Server 由于错误而导致的 Windows SharePoint Services 文件总数。</span><span class="sxs-lookup"><span data-stu-id="8513b-119">The total number of Windows SharePoint Services files received that have not been processed by BizTalk Server due to errors.</span></span>|  
||<span data-ttu-id="8513b-120">收到的消息总数</span><span class="sxs-lookup"><span data-stu-id="8513b-120">Total Received Messages</span></span>|<span data-ttu-id="8513b-121">接收的 Windows SharePoint Services 适配器，包括无法处理的文件的 Windows SharePoint Services 文件的总数。</span><span class="sxs-lookup"><span data-stu-id="8513b-121">The total number of Windows SharePoint Services files received by the Windows SharePoint Services adapter, including files that failed to process.</span></span>|  
||<span data-ttu-id="8513b-122">总发送消息失败</span><span class="sxs-lookup"><span data-stu-id="8513b-122">Total Send Message Failures</span></span>|<span data-ttu-id="8513b-123">BizTalk Server 尝试发往 Windows SharePoint Services 的失败消息的总数。</span><span class="sxs-lookup"><span data-stu-id="8513b-123">The total number of failed messages BizTalk Server attempted to send to Windows SharePoint Services.</span></span>|  
||<span data-ttu-id="8513b-124">发送的消息总计</span><span class="sxs-lookup"><span data-stu-id="8513b-124">Total Sent Messages</span></span>|<span data-ttu-id="8513b-125">BizTalk Server 发送到 Windows SharePoint Services，包括无法处理的文件的消息的总数。</span><span class="sxs-lookup"><span data-stu-id="8513b-125">The total number of messages BizTalk Server sent to Windows SharePoint Services, including files that failed to process.</span></span>|  
||<span data-ttu-id="8513b-126">全面的 Web 服务调用失败</span><span class="sxs-lookup"><span data-stu-id="8513b-126">Total Web Service Call Failures</span></span>|<span data-ttu-id="8513b-127">Windows SharePoint Services 适配器 Web services 调用失败的总数。</span><span class="sxs-lookup"><span data-stu-id="8513b-127">The total number of Windows SharePoint Services adapter Web service calls that have failed.</span></span>|  
||<span data-ttu-id="8513b-128">每秒的 web 服务调用</span><span class="sxs-lookup"><span data-stu-id="8513b-128">Web Service Calls per Second</span></span>|<span data-ttu-id="8513b-129">每秒调用 Windows SharePoint Services 适配器 Web 服务数。</span><span class="sxs-lookup"><span data-stu-id="8513b-129">The number of Windows SharePoint Services adapter Web service calls per second.</span></span>|  
  
## <a name="to-access-performance-counters"></a><span data-ttu-id="8513b-130">若要访问性能计数器</span><span class="sxs-lookup"><span data-stu-id="8513b-130">To access performance counters</span></span>  
 <span data-ttu-id="8513b-131">使用以下步骤访问性能计数器。</span><span class="sxs-lookup"><span data-stu-id="8513b-131">Use the following steps to access the performance counters.</span></span>  
  
#### <a name="if-you-are-using-windows-2008"></a><span data-ttu-id="8513b-132">如果您使用的 Windows 2008</span><span class="sxs-lookup"><span data-stu-id="8513b-132">If you are using Windows 2008</span></span>  
  
1.  <span data-ttu-id="8513b-133">单击**启动**，依次指向**管理工具**，然后单击**性能监视器**。</span><span class="sxs-lookup"><span data-stu-id="8513b-133">Click **Start**, point to **Administrative Tools**, and then click **Performance Monitor**.</span></span>  
  
2.  <span data-ttu-id="8513b-134">在中**性能监视器**对话框框中，展开**监视工具**，选择**性能监视器**，然后单击**添加**。</span><span class="sxs-lookup"><span data-stu-id="8513b-134">In the **Performance Monitor** dialog box, expand **Monitoring Tools**, select **Performance Monitor**, and then click **Add**.</span></span>  
  
3.  <span data-ttu-id="8513b-135">在中**添加计数器**对话框中，从**可用的计数器**列表中，展开**biztalk: Windows Sharepoint Services 适配器**性能计数器对象，并选择要监视的计数器</span><span class="sxs-lookup"><span data-stu-id="8513b-135">In the **Add Counters** dialog box, from the **Available Counters** list, expand the **BizTalk:Windows Sharepoint Services Adapter** performance counter object and select the counters to be monitored</span></span>  
  
4.  <span data-ttu-id="8513b-136">在中**选定对象的实例**列表中，选择要监视的所选的计数器，然后单击的特定实例**添加**。</span><span class="sxs-lookup"><span data-stu-id="8513b-136">In the **Instances of Selected object** list, select the specific instances to be monitored for the selected counters and then click **Add**.</span></span>  <span data-ttu-id="8513b-137">若要选择的所有可用的计数器实例，请选择\<**所有实例**\>。</span><span class="sxs-lookup"><span data-stu-id="8513b-137">To select all available counter instances, select \<**All instances**\>.</span></span>  
  
5.  <span data-ttu-id="8513b-138">添加计数器之后, 单击**确定**。</span><span class="sxs-lookup"><span data-stu-id="8513b-138">After adding the counters, click **OK**.</span></span>  
  
     <span data-ttu-id="8513b-139">所选的性能计数器随即显示在**性能监视器**屏幕。</span><span class="sxs-lookup"><span data-stu-id="8513b-139">The selected performance counters appear on the **Performance Monitor** screen.</span></span>