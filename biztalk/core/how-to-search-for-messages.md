---
title: 如何搜索消息 |Microsoft 文档
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- messages, viewing
- messages, searching
- Query tab [Administration Console], searching
- Query tab [Administration Console], messages
ms.assetid: c751d23f-913a-4325-81da-a36d61c07e8b
caps.latest.revision: 16
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: a5443cc021bd5f97621f44d295432c99834bdaed
ms.sourcegitcommit: 8418b1a8f38b7f56979cd6e203f0b591e2f40fe1
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/28/2018
ms.locfileid: "22255277"
---
# <a name="how-to-search-for-messages"></a><span data-ttu-id="77500-102">如何搜索消息</span><span class="sxs-lookup"><span data-stu-id="77500-102">How to Search for Messages</span></span>
<span data-ttu-id="77500-103">你可以使用 **查询** 在 BizTalk Server 管理控制台中搜索特定类的消息的选项卡。</span><span class="sxs-lookup"><span data-stu-id="77500-103">You can use the **Query** tab in the BizTalk Server Administration Console to search for a specific class of messages.</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="77500-104">先决条件</span><span class="sxs-lookup"><span data-stu-id="77500-104">Prerequisites</span></span>  
 <span data-ttu-id="77500-105">若要执行此过程，则必须以 BizTalk Server Operators 组成员的身份登录。</span><span class="sxs-lookup"><span data-stu-id="77500-105">To perform this procedure, you must be logged on as a member of the BizTalk Server Operators group.</span></span>  
  
### <a name="to-search-for-messages"></a><span data-ttu-id="77500-106">要搜索的消息</span><span class="sxs-lookup"><span data-stu-id="77500-106">To search for messages</span></span>  
  
1.  <span data-ttu-id="77500-107">单击 **启动**, ，单击 **所有程序**, ，单击 [!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)], ，然后单击 **BizTalk Server 管理**。</span><span class="sxs-lookup"><span data-stu-id="77500-107">Click **Start**, click **All Programs**, click [!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)], and then click **BizTalk Server Administration**.</span></span>  
  
2.  <span data-ttu-id="77500-108">在控制台树中，展开“[!INCLUDE[btsBizTalkServerAdminConsoleui](../includes/btsbiztalkserveradminconsoleui-md.md)]”，然后单击“BizTalk 组”。</span><span class="sxs-lookup"><span data-stu-id="77500-108">In the console tree, expand [!INCLUDE[btsBizTalkServerAdminConsoleui](../includes/btsbiztalkserveradminconsoleui-md.md)], and then click the BizTalk group.</span></span>  
  
3.  <span data-ttu-id="77500-109">在详细信息窗格中，单击 **新查询** 选项卡。</span><span class="sxs-lookup"><span data-stu-id="77500-109">In the details pane, click the **New Query** tab.</span></span>  
  
4.  <span data-ttu-id="77500-110">在 **查询表达式** 组中，在 **值** 列中，选择 **消息** 从下拉列表框。</span><span class="sxs-lookup"><span data-stu-id="77500-110">In the **Query Expression** group, in the **Value** column, select **Messages** from the drop-down list box.</span></span>  
  
5.  <span data-ttu-id="77500-111">在 **字段名称** 旁边星号的空下拉列表框中的列，(**\***)，选择一个或多个以下︰</span><span class="sxs-lookup"><span data-stu-id="77500-111">In the **Field Name** column, in the empty drop-down list box next to the asterisk (**\***), select one or more of the following:</span></span>  
  
    |<span data-ttu-id="77500-112">项</span><span class="sxs-lookup"><span data-stu-id="77500-112">Item</span></span>|<span data-ttu-id="77500-113">Description</span><span class="sxs-lookup"><span data-stu-id="77500-113">Description</span></span>|  
    |----------|-----------------|  
    |<span data-ttu-id="77500-114">**创建时间**</span><span class="sxs-lookup"><span data-stu-id="77500-114">**Creation Time**</span></span>|<span data-ttu-id="77500-115">找到指定日期之前或之后创建的消息。</span><span class="sxs-lookup"><span data-stu-id="77500-115">Find messages created before or after the specified date.</span></span>|  
    |<span data-ttu-id="77500-116">**错误适配器**</span><span class="sxs-lookup"><span data-stu-id="77500-116">**Error Adapter**</span></span>|<span data-ttu-id="77500-117">可以对其进行分组或筛选由适配器类型的消息︰ 文件、 FTP、 HTTP、 MQSeries、 MSMQ、 POP3、 SMTP、 SOAP、 或 Windows SharePoint Services。</span><span class="sxs-lookup"><span data-stu-id="77500-117">You can group or filter messages by adapter type: FILE, FTP, HTTP, MQSeries, MSMQ, POP3, SMTP, SOAP, or Windows SharePoint Services.</span></span>|  
    |<span data-ttu-id="77500-118">**错误代码**</span><span class="sxs-lookup"><span data-stu-id="77500-118">**Error Code**</span></span>|<span data-ttu-id="77500-119">可以对其进行分组或错误代码筛选消息。</span><span class="sxs-lookup"><span data-stu-id="77500-119">You can group or filter messages by error code.</span></span>|  
    |<span data-ttu-id="77500-120">**错误说明**</span><span class="sxs-lookup"><span data-stu-id="77500-120">**Error Description**</span></span>|<span data-ttu-id="77500-121">可以对其进行分组或筛选由错误说明的消息。</span><span class="sxs-lookup"><span data-stu-id="77500-121">You can group or filter messages by error description.</span></span>|  
    |<span data-ttu-id="77500-122">**主机名**</span><span class="sxs-lookup"><span data-stu-id="77500-122">**Host Name**</span></span>|<span data-ttu-id="77500-123">可以按主机名称对消息进行分组或筛选。</span><span class="sxs-lookup"><span data-stu-id="77500-123">You can group or filter messages by host name.</span></span>|  
    |<span data-ttu-id="77500-124">**实例状态**</span><span class="sxs-lookup"><span data-stu-id="77500-124">**Instance Status**</span></span>|<span data-ttu-id="77500-125">引用消息的服务实例的状态。</span><span class="sxs-lookup"><span data-stu-id="77500-125">The status of the service instance referencing the message.</span></span> <span data-ttu-id="77500-126">可以搜索下列所有类型的实例：所有正在运行的实例、所有挂起实例、活动实例、已冻结的实例、准备运行的实例、计划的实例、已挂起但不可恢复的实例或已挂起并可恢复的实例。</span><span class="sxs-lookup"><span data-stu-id="77500-126">You can search for all of the following types of instances: all running instances, all suspended instances, active instances, dehydrated instances, ready-to-run instances, scheduled instances, suspended but not resumable instances, or suspended and resumable instances.</span></span>|  
    |<span data-ttu-id="77500-127">**最大匹配数**</span><span class="sxs-lookup"><span data-stu-id="77500-127">**Maximum Matches**</span></span>|<span data-ttu-id="77500-128">要显示的匹配数。</span><span class="sxs-lookup"><span data-stu-id="77500-128">The number of matches to display.</span></span>|  
    |<span data-ttu-id="77500-129">**消息 ID**</span><span class="sxs-lookup"><span data-stu-id="77500-129">**Message ID**</span></span>|<span data-ttu-id="77500-130">可以按消息 ID 对消息进行分组或筛选。</span><span class="sxs-lookup"><span data-stu-id="77500-130">You can group or filter messages by message ID.</span></span>|  
    |<span data-ttu-id="77500-131">**消息状态**</span><span class="sxs-lookup"><span data-stu-id="77500-131">**Message Status**</span></span>|<span data-ttu-id="77500-132">可以搜索以下状态的消息：已使用、进程内、已挂起、已挂起但不可恢复、已挂起并可恢复、已排队、已排队但等待处理、已排队但计划以后送达、已排队但等待重试。</span><span class="sxs-lookup"><span data-stu-id="77500-132">You can search for messages with consumed, in process, suspended, suspended but not resumable, suspended and resumable, queued, queued but awaiting processing, queued but scheduled for later delivery, and queued but waiting to retry.</span></span>|  
    |<span data-ttu-id="77500-133">**消息类型**</span><span class="sxs-lookup"><span data-stu-id="77500-133">**Message Type**</span></span>|<span data-ttu-id="77500-134">可以按消息类型对消息进行分组或筛选。</span><span class="sxs-lookup"><span data-stu-id="77500-134">You can group or filter messages by message type.</span></span>|  
    |<span data-ttu-id="77500-135">**服务类**</span><span class="sxs-lookup"><span data-stu-id="77500-135">**Service Class**</span></span>|<span data-ttu-id="77500-136">可以搜索以下内容：独立适配器；消息传送；消息传送和独立适配器；MSMQT；业务流程；或路由故障报告。</span><span class="sxs-lookup"><span data-stu-id="77500-136">You can search for isolated adapters; messaging; messaging, and isolated adapters; MSMQT; Orchestration; or Routing Failure Report.</span></span>|  
    |<span data-ttu-id="77500-137">**服务实例 ID**</span><span class="sxs-lookup"><span data-stu-id="77500-137">**Service Instance ID**</span></span>|<span data-ttu-id="77500-138">可以按服务实例 ID 对消息进行分组或筛选。</span><span class="sxs-lookup"><span data-stu-id="77500-138">You can group or filter messages by service instance ID.</span></span>|  
    |<span data-ttu-id="77500-139">**服务名称**</span><span class="sxs-lookup"><span data-stu-id="77500-139">**Service Name**</span></span>|<span data-ttu-id="77500-140">可以按服务名对消息进行分组或筛选。</span><span class="sxs-lookup"><span data-stu-id="77500-140">You can group or filter messages by service name.</span></span>|  
    |<span data-ttu-id="77500-141">**服务类型 ID**</span><span class="sxs-lookup"><span data-stu-id="77500-141">**Service Type ID**</span></span>|<span data-ttu-id="77500-142">可以按服务类型 ID 对消息进行分组或筛选。</span><span class="sxs-lookup"><span data-stu-id="77500-142">You can group or filter messages by service type ID.</span></span>|  
    |<span data-ttu-id="77500-143">**URI**</span><span class="sxs-lookup"><span data-stu-id="77500-143">**URI**</span></span>|<span data-ttu-id="77500-144">可以按 URI 对消息进行分组或筛选。</span><span class="sxs-lookup"><span data-stu-id="77500-144">You can group or filter messages by URI.</span></span>|  
  
6.  <span data-ttu-id="77500-145">完成 **值** 列的适合于所选内容所做中 **字段名称** 列。</span><span class="sxs-lookup"><span data-stu-id="77500-145">Complete the **Value** column as appropriate for the selection you made in the **Field Name** column.</span></span>  
  
7.  <span data-ttu-id="77500-146">继续向视情况而定查询添加更多的行，通过完成 **字段名称**, ，**运算符**, ，和 **值** columns 和 then click **运行查询**。</span><span class="sxs-lookup"><span data-stu-id="77500-146">Continue adding additional lines to the query as appropriate, by completing the **Field Name**, **Operator**, and **Values** columns, and then click **Run Query**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="77500-147">另请参阅</span><span class="sxs-lookup"><span data-stu-id="77500-147">See Also</span></span>  
 [<span data-ttu-id="77500-148">使用管理控制台的“查询”选项卡</span><span class="sxs-lookup"><span data-stu-id="77500-148">Using the Administration Console Query Tab</span></span>](../core/using-the-administration-console-query-tab.md)