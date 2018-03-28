---
title: 如何搜索挂起的服务实例 |Microsoft 文档
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- service instances, viewing
- service instances, Query tab [Administration Console]
- Query tab [Administration Console], service instances
- service instances, suspended
- Query tab [Administration Console], searching
- instances, suspended
- instances, services
ms.assetid: f91b1151-d879-4aa7-afc8-4cf13d928158
caps.latest.revision: ''
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 52c0d3ad192ad2cc8f4429f78cfa38ddc97ac837
ms.sourcegitcommit: 8418b1a8f38b7f56979cd6e203f0b591e2f40fe1
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/28/2018
---
# <a name="how-to-search-for-suspended-service-instances"></a><span data-ttu-id="cb222-102">如何搜索挂起的服务实例</span><span class="sxs-lookup"><span data-stu-id="cb222-102">How to Search for Suspended Service Instances</span></span>
<span data-ttu-id="cb222-103">你可以使用 **查询** BizTalk Server 管理控制台，以便搜索挂起的服务实例中的选项卡。</span><span class="sxs-lookup"><span data-stu-id="cb222-103">You can use the **Query** tab in the BizTalk Server Administration Console to search for suspended service instances.</span></span> <span data-ttu-id="cb222-104">您可以搜索消息的特定子集，以查找与服务名、类型、主机等相关联的特定消息。</span><span class="sxs-lookup"><span data-stu-id="cb222-104">You can search for a specific subset of messages to locate a specific message associated with a service name, type, host, etc.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="cb222-105">对于有关的挂起服务实例，已终止且带有未使用的消息实例显示为错误代码（“已终止且带有未使用的消息”）。</span><span class="sxs-lookup"><span data-stu-id="cb222-105">Terminated w/ unconsumed message instances are displayed as an error code (“Terminated with unconsumed messages”) for the pertinent suspended service instances.</span></span> <span data-ttu-id="cb222-106">这些实例是不可恢复的。</span><span class="sxs-lookup"><span data-stu-id="cb222-106">These instances are non-resumable.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="cb222-107">在按 URI 或错误适配器名称进行分组和筛选时，结果中将仅显示发送端口和接收端口。</span><span class="sxs-lookup"><span data-stu-id="cb222-107">When Grouping and Filtering by URI or error adapter name, only send and receive ports are displayed in the results.</span></span> <span data-ttu-id="cb222-108">对于所显示的结果中未包含的业务流程，将不能按 URI 进行分组和筛选。</span><span class="sxs-lookup"><span data-stu-id="cb222-108">Grouping and Filtering by URI is not possible for orchestrations, which are not included in the displayed results.</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="cb222-109">先决条件</span><span class="sxs-lookup"><span data-stu-id="cb222-109">Prerequisites</span></span>  
 <span data-ttu-id="cb222-110">若要执行此过程，则必须以 BizTalk Server Operators 组成员的身份登录。</span><span class="sxs-lookup"><span data-stu-id="cb222-110">To perform this procedure, you must be logged on as a member of the BizTalk Server Operators group.</span></span>  
  
### <a name="to-search-for-suspended-service-instances"></a><span data-ttu-id="cb222-111">搜索挂起的服务实例</span><span class="sxs-lookup"><span data-stu-id="cb222-111">To search for suspended service instances</span></span>  
  
1.  <span data-ttu-id="cb222-112">单击**启动**，单击**所有程序**，单击**Microsoft**[!INCLUDE[btsBizTalkServer2006r3ui](../includes/btsbiztalkserver2006r3ui-md.md)]，然后单击**BizTalk Server 管理**。</span><span class="sxs-lookup"><span data-stu-id="cb222-112">Click **Start**, click **All Programs**, click **Microsoft**[!INCLUDE[btsBizTalkServer2006r3ui](../includes/btsbiztalkserver2006r3ui-md.md)], and then click **BizTalk Server Administration**.</span></span>  
  
2.  <span data-ttu-id="cb222-113">在控制台树中，展开 **BizTalk Server 管理**, ，然后单击 BizTalk 组。</span><span class="sxs-lookup"><span data-stu-id="cb222-113">In the console tree, expand **BizTalk Server Administration**, and then click the BizTalk group.</span></span>  
  
3.  <span data-ttu-id="cb222-114">在详细信息窗格中，单击 **新查询** 选项卡。</span><span class="sxs-lookup"><span data-stu-id="cb222-114">In the details pane, click the **New Query** tab.</span></span>  
  
4.  <span data-ttu-id="cb222-115">在 **查询表达式** 组中，在 **值** 列中，选择 **挂起服务实例** 从下拉列表框。</span><span class="sxs-lookup"><span data-stu-id="cb222-115">In the **Query Expression** group, in the **Value** column, select **Suspended Service Instances** from the drop-down list box.</span></span>  
  
5.  <span data-ttu-id="cb222-116">在 **字段名称** 旁边星号的空下拉列表框中的列，(**\***)，选择一个或多个以下︰</span><span class="sxs-lookup"><span data-stu-id="cb222-116">In the **Field Name** column, in the empty drop-down list box next to the asterisk (**\***), select one or more of the following:</span></span>  
  
    |<span data-ttu-id="cb222-117">项</span><span class="sxs-lookup"><span data-stu-id="cb222-117">Item</span></span>|<span data-ttu-id="cb222-118">Description</span><span class="sxs-lookup"><span data-stu-id="cb222-118">Description</span></span>|  
    |----------|-----------------|  
    |<span data-ttu-id="cb222-119">**应用程序名称**</span><span class="sxs-lookup"><span data-stu-id="cb222-119">**Application Name**</span></span>|<span data-ttu-id="cb222-120">BizTalk Server 应用程序的名称。</span><span class="sxs-lookup"><span data-stu-id="cb222-120">The name of the BizTalk Server application.</span></span>|  
    |<span data-ttu-id="cb222-121">**创建时间**</span><span class="sxs-lookup"><span data-stu-id="cb222-121">**Creation Time**</span></span>|<span data-ttu-id="cb222-122">查找在指定日期之前或之后创建的挂起的服务实例。</span><span class="sxs-lookup"><span data-stu-id="cb222-122">Find suspended service instances created before or after the specified date.</span></span>|  
    |<span data-ttu-id="cb222-123">**错误适配器**</span><span class="sxs-lookup"><span data-stu-id="cb222-123">**Error Adapter**</span></span>|<span data-ttu-id="cb222-124">可以按适配器类型对挂起的服务实例进行分组或筛选。</span><span class="sxs-lookup"><span data-stu-id="cb222-124">You can group or filter suspended service instances by adapter type.</span></span> <span data-ttu-id="cb222-125">例如︰ 文件、 FTP、 HTTP、 MQSeries、 MSMQ、 POP3、 SMTP、 SOAP、 或 Windows SharePoint Services。</span><span class="sxs-lookup"><span data-stu-id="cb222-125">For example: FILE, FTP, HTTP, MQSeries, MSMQ, POP3, SMTP, SOAP,  or Windows SharePoint Services.</span></span> <span data-ttu-id="cb222-126">**注意︰**  在查询结果中，适配器仅时，填充字段 BizTalk Server 运行时使用安装该指定的适配器时遇到错误。</span><span class="sxs-lookup"><span data-stu-id="cb222-126">**Note:**  In the query results, the adapter field is only populated when the BizTalk Server runtime runs into an error while using the specified adater.</span></span> <span data-ttu-id="cb222-127">如果运行时未找到适配器错误，则在查询结果中“适配器错误”字段为空。</span><span class="sxs-lookup"><span data-stu-id="cb222-127">If the runtime does not find an error with the adapter, in the query results, the Error Adapter field is empty.</span></span>|  
    |<span data-ttu-id="cb222-128">**错误代码**</span><span class="sxs-lookup"><span data-stu-id="cb222-128">**Error Code**</span></span>|<span data-ttu-id="cb222-129">可以按照错误代码对挂起的服务实例进行分组或筛选，以显示具有该错误代码的所有已挂起的服务实例。</span><span class="sxs-lookup"><span data-stu-id="cb222-129">You can group or filter suspended service instances by error code to show all that service instances have been suspended with that error code.</span></span>|  
    |<span data-ttu-id="cb222-130">**错误说明**</span><span class="sxs-lookup"><span data-stu-id="cb222-130">**Error Description**</span></span>|<span data-ttu-id="cb222-131">可以对具有指定错误说明的挂起的服务实例进行分组或筛选。</span><span class="sxs-lookup"><span data-stu-id="cb222-131">You can group or filter suspended service instances with the specified error description.</span></span>|  
    |<span data-ttu-id="cb222-132">**按结果进行分组**</span><span class="sxs-lookup"><span data-stu-id="cb222-132">**Group Results By**</span></span>|<span data-ttu-id="cb222-133">可以按照适配器、应用程序、错误代码、错误说明、主机名称、服务级别、服务实例状态、服务名或 URI 对结果进行分组或筛选。</span><span class="sxs-lookup"><span data-stu-id="cb222-133">You can group or filter results by adapter, application, error code, error description, host name, service class, service instance status, service name, or URI.</span></span>|  
    |<span data-ttu-id="cb222-134">**主机名**</span><span class="sxs-lookup"><span data-stu-id="cb222-134">**Host Name**</span></span>|<span data-ttu-id="cb222-135">按主机名称对挂起的服务实例进行分组或筛选。</span><span class="sxs-lookup"><span data-stu-id="cb222-135">Group or filter suspended service instances by host name.</span></span>|  
    |<span data-ttu-id="cb222-136">**实例状态**</span><span class="sxs-lookup"><span data-stu-id="cb222-136">**Instance Status**</span></span>|<span data-ttu-id="cb222-137">您可以搜索已挂起但不可恢复的实例，也可以搜索已挂起并可恢复的实例。</span><span class="sxs-lookup"><span data-stu-id="cb222-137">You can search for suspended but not resumable instances, or suspended and resumable instances.</span></span>|  
    |<span data-ttu-id="cb222-138">**最大匹配数**</span><span class="sxs-lookup"><span data-stu-id="cb222-138">**Maximum Matches**</span></span>|<span data-ttu-id="cb222-139">要显示的匹配数。</span><span class="sxs-lookup"><span data-stu-id="cb222-139">The number of matches to display.</span></span>|  
    |<span data-ttu-id="cb222-140">**服务类**</span><span class="sxs-lookup"><span data-stu-id="cb222-140">**Service Class**</span></span>|<span data-ttu-id="cb222-141">可以搜索以下内容：独立适配器；消息传送；消息传送和独立适配器；MSMQT；业务流程；或路由故障报告。</span><span class="sxs-lookup"><span data-stu-id="cb222-141">You can search for isolated adapters; messaging; messaging, and isolated adapters; MSMQT; Orchestration; or Routing Failure Report.</span></span>|  
    |<span data-ttu-id="cb222-142">**服务名称**</span><span class="sxs-lookup"><span data-stu-id="cb222-142">**Service Name**</span></span>|<span data-ttu-id="cb222-143">可以按服务名对挂起的服务实例进行分组或筛选。</span><span class="sxs-lookup"><span data-stu-id="cb222-143">You can group or filter suspended service instances by service name.</span></span>|  
    |<span data-ttu-id="cb222-144">**服务类型 ID**</span><span class="sxs-lookup"><span data-stu-id="cb222-144">**Service Type ID**</span></span>|<span data-ttu-id="cb222-145">可以按服务类型 ID 对挂起的服务实例进行分组或筛选。</span><span class="sxs-lookup"><span data-stu-id="cb222-145">You can group or filter suspended service instances by service type ID.</span></span>|  
    |<span data-ttu-id="cb222-146">**挂起时间**</span><span class="sxs-lookup"><span data-stu-id="cb222-146">**Suspension Time**</span></span>|<span data-ttu-id="cb222-147">可以对在指定日期之前或之后挂起的服务实例进行分组或筛选。</span><span class="sxs-lookup"><span data-stu-id="cb222-147">You can group or filter suspended service instances suspended before or after the specified date.</span></span>|  
    |<span data-ttu-id="cb222-148">**URI**</span><span class="sxs-lookup"><span data-stu-id="cb222-148">**URI**</span></span>|<span data-ttu-id="cb222-149">可以按 URI 对挂起的服务实例进行分组或筛选。</span><span class="sxs-lookup"><span data-stu-id="cb222-149">You can group or filter suspended service instances by URI.</span></span> <span data-ttu-id="cb222-150">**注意︰**  在查询结果中，URI 仅在填充 BizTalk Server 运行时将发送到指定的 URI 时遇到错误。</span><span class="sxs-lookup"><span data-stu-id="cb222-150">**Note:**  In the query results, the URI is only populated when the BizTalk Server runtime runs into an error while sending to the specified URI.</span></span> <span data-ttu-id="cb222-151">如果运行时在发送至 URI 时未找到错误，则在查询结果中，URI 字段为空或显示“URI 不可用”。</span><span class="sxs-lookup"><span data-stu-id="cb222-151">If the runtime does not find an error when sending to the URI, in the query results, the URI field is empty or shows "URI unavailable."</span></span>|  
  
6.  <span data-ttu-id="cb222-152">完成 **值** 列的适合于所选内容所做中 **字段名称** 列。</span><span class="sxs-lookup"><span data-stu-id="cb222-152">Complete the **Value** column as appropriate for the selection you made in the **Field Name** column.</span></span>  
  
7.  <span data-ttu-id="cb222-153">继续向视情况而定查询添加更多的行，通过完成 **字段名称**, ，**运算符**, ，和 **值** columns 和 then click **运行查询**。</span><span class="sxs-lookup"><span data-stu-id="cb222-153">Continue adding additional lines to the query as appropriate, by completing the **Field Name**, **Operator**, and **Values** columns, and then click **Run Query**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="cb222-154">另请参阅</span><span class="sxs-lookup"><span data-stu-id="cb222-154">See Also</span></span>  
 [<span data-ttu-id="cb222-155">使用管理控制台的“查询”选项卡</span><span class="sxs-lookup"><span data-stu-id="cb222-155">Using the Administration Console Query Tab</span></span>](../core/using-the-administration-console-query-tab.md)