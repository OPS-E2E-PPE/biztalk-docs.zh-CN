---
title: 修复和重新提交一条消息 |Microsoft 文档
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: ccd720b4-44a2-4c44-bf6e-8cf5e9ded1aa
caps.latest.revision: 3
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: e524ffca1b79032dce55f74e195032d14ec1bf9e
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22295053"
---
# <a name="repairing-and-resubmitting-a-message"></a><span data-ttu-id="d3748-102">修复和重新提交一条消息</span><span class="sxs-lookup"><span data-stu-id="d3748-102">Repairing and Resubmitting a Message</span></span>
<span data-ttu-id="d3748-103">修复并重新提交失败的消息，请使用 ESB 管理门户的错误页。</span><span class="sxs-lookup"><span data-stu-id="d3748-103">To repair and resubmit a failed message, use the Faults page of the ESB Management Portal.</span></span>  
  
### <a name="to-repair-and-resubmit-a-message-for-processing"></a><span data-ttu-id="d3748-104">若要修复并重新提交邮件以进行处理</span><span class="sxs-lookup"><span data-stu-id="d3748-104">To repair and resubmit a message for processing</span></span>  
  
1.  <span data-ttu-id="d3748-105">在上找到所需的错误消息[门户错误页](../esb-toolkit/portal-faults-page.md)ESB 管理门户页。</span><span class="sxs-lookup"><span data-stu-id="d3748-105">Locate the desired fault message on the [Portal Faults Page](../esb-toolkit/portal-faults-page.md) page of the ESB Management Portal.</span></span> <span data-ttu-id="d3748-106">在错误页上使用的筛选功能搜索的特定消息。</span><span class="sxs-lookup"><span data-stu-id="d3748-106">Use the filtering capabilities on the Faults page to search for a specific message.</span></span> <span data-ttu-id="d3748-107">任何控件留空以检索所有消息。</span><span class="sxs-lookup"><span data-stu-id="d3748-107">Leave any of the controls empty to retrieve all messages.</span></span> <span data-ttu-id="d3748-108">请注意，筛选非常大的容错数据库上可能需要几秒钟才会显示相应的结果。</span><span class="sxs-lookup"><span data-stu-id="d3748-108">Note that filtering on a very large fault database may take several seconds to display the appropriate results.</span></span> <span data-ttu-id="d3748-109">图 1 说明错误页。</span><span class="sxs-lookup"><span data-stu-id="d3748-109">Figure 1 illustrates the Faults page.</span></span>  
  
     <span data-ttu-id="d3748-110">![FaultsPage](../esb-toolkit/media/faultspage.gif "FaultsPage")</span><span class="sxs-lookup"><span data-stu-id="d3748-110">![FaultsPage](../esb-toolkit/media/faultspage.gif "FaultsPage")</span></span>  
  
     <span data-ttu-id="d3748-111">**图 1**</span><span class="sxs-lookup"><span data-stu-id="d3748-111">**Figure 1**</span></span>  
  
     <span data-ttu-id="d3748-112">**ESB 管理门户的错误页上**</span><span class="sxs-lookup"><span data-stu-id="d3748-112">**The Faults page of the ESB Management Portal**</span></span>  
  
2.  <span data-ttu-id="d3748-113">若要打开的所需的错误消息的行中单击任一处[门户错误消息查看器](../esb-toolkit/portal-fault-message-viewer.md)页面[错误详细信息视图](../esb-toolkit/fault-details-view.md)。</span><span class="sxs-lookup"><span data-stu-id="d3748-113">Click anywhere in the row of the desired fault message to open the [Portal Fault Message Viewer](../esb-toolkit/portal-fault-message-viewer.md) page in [Fault Details View](../esb-toolkit/fault-details-view.md).</span></span>  
  
3.  <span data-ttu-id="d3748-114">滚动到底部的错误详细信息视图中的错误消息中包含的消息的列表。</span><span class="sxs-lookup"><span data-stu-id="d3748-114">Scroll to the bottom of the Fault Details view to the list of messages contained within the fault message.</span></span> <span data-ttu-id="d3748-115">图 2 演示了**消息**错误查看器页面的部分。</span><span class="sxs-lookup"><span data-stu-id="d3748-115">Figure 2 illustrates the **Messages** section of the Fault Viewer page.</span></span>  
  
     <span data-ttu-id="d3748-116">![消息部分](../esb-toolkit/media/ch8-messagessection.gif "Ch8 MessagesSection")</span><span class="sxs-lookup"><span data-stu-id="d3748-116">![Messages Section](../esb-toolkit/media/ch8-messagessection.gif "Ch8-MessagesSection")</span></span>  
  
     <span data-ttu-id="d3748-117">**图 2**</span><span class="sxs-lookup"><span data-stu-id="d3748-117">**Figure 2**</span></span>  
  
     <span data-ttu-id="d3748-118">**ESB 管理门户的错误查看器页上的消息部分**</span><span class="sxs-lookup"><span data-stu-id="d3748-118">**The Messages section of the Fault Viewer page of the ESB Management Portal**</span></span>  
  
4.  <span data-ttu-id="d3748-119">单击你想要重新提交消息的消息标识符。</span><span class="sxs-lookup"><span data-stu-id="d3748-119">Click the message identifier of the message you want to resubmit.</span></span> <span data-ttu-id="d3748-120">这将打开中的消息[消息详细信息视图](../esb-toolkit/message-details-view.md)，其中说明了单个消息和消息内容的详细信息，如图 3 中所示。</span><span class="sxs-lookup"><span data-stu-id="d3748-120">This opens the message in [Message Details View](../esb-toolkit/message-details-view.md), which shows details of the individual message and the message content, as illustrated in Figure 3.</span></span>  
  
     <span data-ttu-id="d3748-121">![消息查看器](../esb-toolkit/media/ch8-messageviewer.gif "Ch8 MessageViewer")</span><span class="sxs-lookup"><span data-stu-id="d3748-121">![Message Viewer](../esb-toolkit/media/ch8-messageviewer.gif "Ch8-MessageViewer")</span></span>  
  
     <span data-ttu-id="d3748-122">**图 3**</span><span class="sxs-lookup"><span data-stu-id="d3748-122">**Figure 3**</span></span>  
  
     <span data-ttu-id="d3748-123">**ESB 管理门户的消息查看器页上**</span><span class="sxs-lookup"><span data-stu-id="d3748-123">**The Message Viewer page of the ESB Management Portal**</span></span>  
  
5.  <span data-ttu-id="d3748-124">单击**编辑**下文本框中，其中包含要切换到编辑模式，然后编辑所需的消息内容的消息内容的链接。</span><span class="sxs-lookup"><span data-stu-id="d3748-124">Click the **Edit** link under the text box that contains the message content to switch to edit mode, and then edit the message contents as required.</span></span> <span data-ttu-id="d3748-125">例如，你可能需要更改消息中包含的服务方法调用的参数。</span><span class="sxs-lookup"><span data-stu-id="d3748-125">For example, you may need to change the parameters for service method invocations contained within the message.</span></span> <span data-ttu-id="d3748-126">请注意，你必须遵守 （如 XML 或平面文件格式） 的本机文档样式以防止被拒的消息时重新提交。</span><span class="sxs-lookup"><span data-stu-id="d3748-126">Note that you must adhere to the native document style (such as XML or flat file format) to prevent rejection of the message when resubmitted.</span></span> <span data-ttu-id="d3748-127">图 4 显示**消息详细信息**消息编辑器页部分。</span><span class="sxs-lookup"><span data-stu-id="d3748-127">Figure 4 illustrates the **Message Details** section of the Message Editor page.</span></span>  
  
     <span data-ttu-id="d3748-128">![消息详细信息](../esb-toolkit/media/ch8-messagedetails.gif "Ch8 MessageDetails")</span><span class="sxs-lookup"><span data-stu-id="d3748-128">![Message Details](../esb-toolkit/media/ch8-messagedetails.gif "Ch8-MessageDetails")</span></span>  
  
     <span data-ttu-id="d3748-129">**图 4**</span><span class="sxs-lookup"><span data-stu-id="d3748-129">**Figure 4**</span></span>  
  
     <span data-ttu-id="d3748-130">**ESB 管理门户的消息查看器页上的消息详细信息部分**</span><span class="sxs-lookup"><span data-stu-id="d3748-130">**The Message Details section of the Message Viewer page of the ESB Management Portal**</span></span>  
  
6.  <span data-ttu-id="d3748-131">编辑消息之后, 在消息文本框下的下拉列表中选择重新提交位置。</span><span class="sxs-lookup"><span data-stu-id="d3748-131">After editing the message, select a resubmission location in the drop-down list under the message text box.</span></span> <span data-ttu-id="d3748-132">此列表显示动态检索的可用终结点列表。</span><span class="sxs-lookup"><span data-stu-id="d3748-132">This list shows the dynamically retrieved list of available endpoints.</span></span> <span data-ttu-id="d3748-133">你必须选择一个终结点配置为重新提交终结点。</span><span class="sxs-lookup"><span data-stu-id="d3748-133">You must select an endpoint configured as a resubmission endpoint.</span></span> <span data-ttu-id="d3748-134">以下终结点是适用于重新提交：</span><span class="sxs-lookup"><span data-stu-id="d3748-134">The following endpoints are suitable for resubmission:</span></span>  
  
    -   <span data-ttu-id="d3748-135">**WCF 入口**。</span><span class="sxs-lookup"><span data-stu-id="d3748-135">**WCF On-Ramp**.</span></span> <span data-ttu-id="d3748-136">此终结点是在提升 ESB 路线服务 WCF，仅适用于 XML 文件。</span><span class="sxs-lookup"><span data-stu-id="d3748-136">This endpoint is the ESB Itinerary Services WCF on-ramp and is available only for XML files.</span></span> <span data-ttu-id="d3748-137">门户网站的 Web.config 文件定义此入口的 URL。</span><span class="sxs-lookup"><span data-stu-id="d3748-137">The portal Web.config file defines the URL for this on-ramp.</span></span>  
  
    -   <span data-ttu-id="d3748-138">**SOAP 入口**。</span><span class="sxs-lookup"><span data-stu-id="d3748-138">**SOAP On-Ramp**.</span></span> <span data-ttu-id="d3748-139">此终结点是在提升 ESB 路线服务 ASMX，仅适用于 XML 文件。</span><span class="sxs-lookup"><span data-stu-id="d3748-139">This endpoint is the ESB Itinerary Services ASMX on-ramp and is available only for XML files.</span></span> <span data-ttu-id="d3748-140">门户网站的 Web.config 文件定义此入口的 URL。</span><span class="sxs-lookup"><span data-stu-id="d3748-140">The portal Web.config file defines the URL for this on-ramp.</span></span>  
  
    -   <span data-ttu-id="d3748-141">**任何接收位置使用 BizTalk HTTP 适配器**。</span><span class="sxs-lookup"><span data-stu-id="d3748-141">**Any receive location using the BizTalk HTTP adapter**.</span></span> <span data-ttu-id="d3748-142">此选项仅供 XML 文件和平面文件。</span><span class="sxs-lookup"><span data-stu-id="d3748-142">This option is available for XML files and flat files.</span></span>  
  
7.  <span data-ttu-id="d3748-143">单击**重新提交**链接以重新提交消息。</span><span class="sxs-lookup"><span data-stu-id="d3748-143">Click the **Resubmit** link to resubmit the message.</span></span> <span data-ttu-id="d3748-144">一个消息，表明**重新提交状态**出现在消息内容文本框的下面。</span><span class="sxs-lookup"><span data-stu-id="d3748-144">A message indicating the **Resubmission Status** appears under the message content text box.</span></span>  
  
8.  <span data-ttu-id="d3748-145">如果需要，请打开[审核日志页](../esb-toolkit/audit-log-page.md)从**管理员**选项卡，确认消息重新提交，如图 5 中所示。</span><span class="sxs-lookup"><span data-stu-id="d3748-145">If required, open the [Audit Log Page](../esb-toolkit/audit-log-page.md) from the **Admin** tab to confirm message resubmission, as illustrated in Figure 5.</span></span>  
  
     <span data-ttu-id="d3748-146">![已页面小视图](../esb-toolkit/media/ch8-auditlogpagesmallview.gif "Ch8 AuditLogPageSmallView")</span><span class="sxs-lookup"><span data-stu-id="d3748-146">![AuditLog Page Small View](../esb-toolkit/media/ch8-auditlogpagesmallview.gif "Ch8-AuditLogPageSmallView")</span></span>  
  
     <span data-ttu-id="d3748-147">**图 5**</span><span class="sxs-lookup"><span data-stu-id="d3748-147">**Figure 5**</span></span>  
  
     <span data-ttu-id="d3748-148">**ESB 管理门户的审核日志页上**</span><span class="sxs-lookup"><span data-stu-id="d3748-148">**The Audit Log page of the ESB Management Portal**</span></span>