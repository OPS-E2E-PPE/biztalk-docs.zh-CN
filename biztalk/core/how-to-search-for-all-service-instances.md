---
title: 如何搜索所有服务实例 |Microsoft 文档
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- service instances, Query tab [Administration Console]
- Query tab [Administration Console], service instances
- Query tab [Administration Console], searching
- service instances, searching
- instances, services
ms.assetid: 48cb885c-aaf1-44e8-9810-2e70cf63db81
caps.latest.revision: 18
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: e96622fad23c28c0d4147f64a11cc540e88e7f97
ms.sourcegitcommit: 8418b1a8f38b7f56979cd6e203f0b591e2f40fe1
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/28/2018
ms.locfileid: "22255117"
---
# <a name="how-to-search-for-all-service-instances"></a><span data-ttu-id="100a0-102">如何搜索所有服务实例</span><span class="sxs-lookup"><span data-stu-id="100a0-102">How to Search for All Service Instances</span></span>
<span data-ttu-id="100a0-103">你可以使用 **查询** 在 BizTalk Server 管理控制台中以搜索所有服务实例的选项卡。</span><span class="sxs-lookup"><span data-stu-id="100a0-103">You can use the **Query** tab in the BizTalk Server Administration Console to search for all service instances.</span></span> <span data-ttu-id="100a0-104">如果存在任何正在运行的或挂起的实例，则无法取消登记特定的服务类型。</span><span class="sxs-lookup"><span data-stu-id="100a0-104">You cannot unenlist a specific service type if there are any running or suspended instances.</span></span> <span data-ttu-id="100a0-105">例如，在取消登记特定的服务类型之前，您可以搜索所有服务实例以确保没有正在运行的或挂起的实例。</span><span class="sxs-lookup"><span data-stu-id="100a0-105">For example, before you can unenlist a specific service type, you can search for all service instances to ensure that there are no running or suspended instances.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="100a0-106">在按 URI 进行分组和筛选时，结果中将仅显示发送和接收端口。</span><span class="sxs-lookup"><span data-stu-id="100a0-106">When Grouping and Filtering by URI, only send and receive ports are displayed in the results.</span></span> <span data-ttu-id="100a0-107">对于所显示的结果中未包含的业务流程，将不能按 URI 进行分组和筛选。</span><span class="sxs-lookup"><span data-stu-id="100a0-107">Grouping and Filtering by URI is not possible for orchestrations, which are not included in the displayed results.</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="100a0-108">先决条件</span><span class="sxs-lookup"><span data-stu-id="100a0-108">Prerequisites</span></span>  
 <span data-ttu-id="100a0-109">若要执行此过程，则必须以 BizTalk Server Operators 组成员的身份登录。</span><span class="sxs-lookup"><span data-stu-id="100a0-109">To perform this procedure, you must be logged on as a member of the BizTalk Server Operators group.</span></span>  
  
### <a name="to-search-for-all-service-instances"></a><span data-ttu-id="100a0-110">搜索所有服务实例</span><span class="sxs-lookup"><span data-stu-id="100a0-110">To search for all service instances</span></span>  
  
1.  <span data-ttu-id="100a0-111">单击 **启动**, ，单击 **所有程序**, ，单击 [!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)], ，然后单击 **BizTalk Server 管理**。</span><span class="sxs-lookup"><span data-stu-id="100a0-111">Click **Start**, click **All Programs**, click [!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)], and then click **BizTalk Server Administration**.</span></span>  
  
2.  <span data-ttu-id="100a0-112">在控制台树中，展开“[!INCLUDE[btsBizTalkServerAdminConsoleui](../includes/btsbiztalkserveradminconsoleui-md.md)]”，然后单击“BizTalk 组”。</span><span class="sxs-lookup"><span data-stu-id="100a0-112">In the console tree, expand [!INCLUDE[btsBizTalkServerAdminConsoleui](../includes/btsbiztalkserveradminconsoleui-md.md)], and then click the BizTalk group.</span></span>  
  
3.  <span data-ttu-id="100a0-113">在详细信息窗格中，单击 **新查询** 选项卡。</span><span class="sxs-lookup"><span data-stu-id="100a0-113">In the details pane, click the **New Query** tab.</span></span>  
  
4.  <span data-ttu-id="100a0-114">在 **查询表达式** 组中，在 **值** 列中，选择 **正在进行中的所有服务实例** 从下拉列表框。</span><span class="sxs-lookup"><span data-stu-id="100a0-114">In the **Query Expression** group, in the **Value** column, select **All In-Progress Service Instances** from the drop-down list box.</span></span>  
  
5.  <span data-ttu-id="100a0-115">在 **字段名称** 旁边星号的空下拉列表框中的列，(**\***)，选择一个或多个以下︰</span><span class="sxs-lookup"><span data-stu-id="100a0-115">In the **Field Name** column, in the empty drop-down list box next to the asterisk (**\***), select one or more of the following:</span></span>  
  
    |<span data-ttu-id="100a0-116">使用此选项</span><span class="sxs-lookup"><span data-stu-id="100a0-116">Use this</span></span>|<span data-ttu-id="100a0-117">执行的操作</span><span class="sxs-lookup"><span data-stu-id="100a0-117">To do this</span></span>|  
    |--------------|----------------|  
    |<span data-ttu-id="100a0-118">**应用程序名称**</span><span class="sxs-lookup"><span data-stu-id="100a0-118">**Application Name**</span></span>|<span data-ttu-id="100a0-119">BizTalk Server 应用程序。</span><span class="sxs-lookup"><span data-stu-id="100a0-119">The BizTalk Server application.</span></span>|  
    |<span data-ttu-id="100a0-120">**创建时间**</span><span class="sxs-lookup"><span data-stu-id="100a0-120">**Creation Time**</span></span>|<span data-ttu-id="100a0-121">查找在指定日期之前或之后创建的所有服务实例。</span><span class="sxs-lookup"><span data-stu-id="100a0-121">Find all service instances created before or after the specified date.</span></span>|  
    |<span data-ttu-id="100a0-122">**按结果进行分组**</span><span class="sxs-lookup"><span data-stu-id="100a0-122">**Group Results By**</span></span>|<span data-ttu-id="100a0-123">可以按应用程序、主机名称、服务类别、服务实例状态或服务名称对结果进行分组。</span><span class="sxs-lookup"><span data-stu-id="100a0-123">You can group results by application, host name, service class, service instance status, or service name.</span></span>|  
    |<span data-ttu-id="100a0-124">**主机名**</span><span class="sxs-lookup"><span data-stu-id="100a0-124">**Host Name**</span></span>|<span data-ttu-id="100a0-125">BizTalk 主机的名称。</span><span class="sxs-lookup"><span data-stu-id="100a0-125">The name of the BizTalk Host.</span></span>|  
    |<span data-ttu-id="100a0-126">**实例状态**</span><span class="sxs-lookup"><span data-stu-id="100a0-126">**Instance Status**</span></span>|<span data-ttu-id="100a0-127">可以搜索所有正在运行的实例、所有挂起的实例、活动实例、已冻结的实例、准备运行的实例、计划的实例、已挂起但不可恢复的实例或已挂起并可恢复的实例。</span><span class="sxs-lookup"><span data-stu-id="100a0-127">You can search for all running instances, all suspended instances, active instances, dehydrated instances, ready to run instances, scheduled instances, suspended but not resumable instances, or suspended and resumable instances.</span></span>|  
    |<span data-ttu-id="100a0-128">**最大匹配数**</span><span class="sxs-lookup"><span data-stu-id="100a0-128">**Maximum Matches**</span></span>|<span data-ttu-id="100a0-129">要显示的匹配数（必选）。</span><span class="sxs-lookup"><span data-stu-id="100a0-129">The number of matches to display (required).</span></span> <span data-ttu-id="100a0-130">通常设置为 50，这是默认值。</span><span class="sxs-lookup"><span data-stu-id="100a0-130">This is usually set to 50, the default.</span></span><br /><br /> <span data-ttu-id="100a0-131">如果选择了“结果分组依据”，则会显示组数，而不显示记录总数。</span><span class="sxs-lookup"><span data-stu-id="100a0-131">When you include Group Results By, this displays the number of groups, not the total number of records.</span></span>|  
    |<span data-ttu-id="100a0-132">**服务类**</span><span class="sxs-lookup"><span data-stu-id="100a0-132">**Service Class**</span></span>|<span data-ttu-id="100a0-133">可以搜索以下内容：独立适配器；消息传送；消息传送和独立适配器；MSMQT；业务流程；或路由故障报告。</span><span class="sxs-lookup"><span data-stu-id="100a0-133">You can search for isolated adapters; messaging; messaging, and isolated adapters; MSMQT; Orchestration; or Routing Failure Report.</span></span>|  
    |<span data-ttu-id="100a0-134">**服务实例 ID**</span><span class="sxs-lookup"><span data-stu-id="100a0-134">**Service Instance ID**</span></span>|<span data-ttu-id="100a0-135">可以按服务实例 ID 对服务实例进行分组或筛选。</span><span class="sxs-lookup"><span data-stu-id="100a0-135">You can group or filter service instances by service instance ID.</span></span>|  
    |<span data-ttu-id="100a0-136">**服务名称**</span><span class="sxs-lookup"><span data-stu-id="100a0-136">**Service Name**</span></span>|<span data-ttu-id="100a0-137">可以按服务名对服务实例进行分组或筛选。</span><span class="sxs-lookup"><span data-stu-id="100a0-137">You can group or filter service instances by service name.</span></span>|  
    |<span data-ttu-id="100a0-138">**服务类型 ID**</span><span class="sxs-lookup"><span data-stu-id="100a0-138">**Service Type ID**</span></span>|<span data-ttu-id="100a0-139">可以按服务类型 ID 对服务实例进行分组或筛选。</span><span class="sxs-lookup"><span data-stu-id="100a0-139">You can group or filter service instances by service type ID.</span></span>|  
  
6.  <span data-ttu-id="100a0-140">完成 **值** 列的适合于所选内容所做中 **字段名称** 列。</span><span class="sxs-lookup"><span data-stu-id="100a0-140">Complete the **Value** column as appropriate for the selection you made in the **Field Name** column.</span></span>  
  
7.  <span data-ttu-id="100a0-141">继续向视情况而定查询添加更多的行，通过完成 **字段名称**, ，**运算符**, ，和 **值** columns 和 then click **运行查询**。</span><span class="sxs-lookup"><span data-stu-id="100a0-141">Continue adding additional lines to the query as appropriate, by completing the **Field Name**, **Operator**, and **Values** columns, and then click **Run Query**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="100a0-142">另请参阅</span><span class="sxs-lookup"><span data-stu-id="100a0-142">See Also</span></span>  
 [<span data-ttu-id="100a0-143">使用管理控制台的“查询”选项卡</span><span class="sxs-lookup"><span data-stu-id="100a0-143">Using the Administration Console Query Tab</span></span>](../core/using-the-administration-console-query-tab.md)