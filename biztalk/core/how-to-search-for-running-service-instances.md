---
title: 如何搜索正在运行的服务实例 |Microsoft Docs
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
- Query tab [Administration Console], searching
- service instances, searching
- service instances, running
ms.assetid: fc65bf33-c013-4e6a-b9fd-b4536811e7b4
caps.latest.revision: 16
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 4c61b94b440810fc948ae7e9e51c1897204d28c2
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "37023931"
---
# <a name="how-to-search-for-running-service-instances"></a><span data-ttu-id="5e4f2-102">如何搜索正在运行的服务实例</span><span class="sxs-lookup"><span data-stu-id="5e4f2-102">How to Search for Running Service Instances</span></span>
<span data-ttu-id="5e4f2-103">可以使用**查询**冻结在 BizTalk Server 管理控制台来搜索特定的选项卡，处于活动状态，在断点，计划，并在重试服务实例。</span><span class="sxs-lookup"><span data-stu-id="5e4f2-103">You can use the **Query** tab in the BizTalk Server Administration Console to search for a specific dehydrated, active, in breakpoint, scheduled, and retrying service instance.</span></span>  

## <a name="prerequisites"></a><span data-ttu-id="5e4f2-104">必要條件</span><span class="sxs-lookup"><span data-stu-id="5e4f2-104">Prerequisites</span></span>  
 <span data-ttu-id="5e4f2-105">若要执行此过程，则必须以 BizTalk Server Operators 组成员的身份登录。</span><span class="sxs-lookup"><span data-stu-id="5e4f2-105">To perform this procedure, you must be logged on as a member of the BizTalk Server Operators group.</span></span>  

### <a name="to-search-for-running-service-instances"></a><span data-ttu-id="5e4f2-106">搜索正在运行的服务实例</span><span class="sxs-lookup"><span data-stu-id="5e4f2-106">To search for running service instances</span></span>  

1. <span data-ttu-id="5e4f2-107">单击**启动**，单击**程序**，单击[!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)]，然后单击**BizTalk Server 管理**。</span><span class="sxs-lookup"><span data-stu-id="5e4f2-107">Click **Start**, click **Programs**, click [!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)], and then click **BizTalk Server Administration**.</span></span>  

2. <span data-ttu-id="5e4f2-108">在控制台树中，展开“[!INCLUDE[btsBizTalkServerAdminConsoleui](../includes/btsbiztalkserveradminconsoleui-md.md)]”，然后单击“BizTalk 组”。</span><span class="sxs-lookup"><span data-stu-id="5e4f2-108">In the console tree, expand [!INCLUDE[btsBizTalkServerAdminConsoleui](../includes/btsbiztalkserveradminconsoleui-md.md)], and then click the BizTalk group.</span></span>  

3. <span data-ttu-id="5e4f2-109">在详细信息窗格中，单击**新查询**选项卡。</span><span class="sxs-lookup"><span data-stu-id="5e4f2-109">In the details pane, click the **New Query** tab.</span></span>  

4. <span data-ttu-id="5e4f2-110">在中**查询表达式**组中，在**值**列中，选择**正在运行的服务实例**从下拉列表框。</span><span class="sxs-lookup"><span data-stu-id="5e4f2-110">In the **Query Expression** group, in the **Value** column, select **Running Service Instances** from the drop-down list box.</span></span>  

5. <span data-ttu-id="5e4f2-111">在中**字段名**列，星号旁边的空下拉列表框中 (\* *\\* \* \*)，选择一个或多项操作：</span><span class="sxs-lookup"><span data-stu-id="5e4f2-111">In the **Field Name** column, in the empty drop-down list box next to the asterisk (\*\*\\*\*\*), select one or more of the following:</span></span>  


   |          <span data-ttu-id="5e4f2-112">项</span><span class="sxs-lookup"><span data-stu-id="5e4f2-112">Item</span></span>          |                                                             <span data-ttu-id="5e4f2-113">Description</span><span class="sxs-lookup"><span data-stu-id="5e4f2-113">Description</span></span>                                                             |
   |------------------------|-------------------------------------------------------------------------------------------------------------------------------------|
   |  <span data-ttu-id="5e4f2-114">**应用程序名称**</span><span class="sxs-lookup"><span data-stu-id="5e4f2-114">**Application Name**</span></span>  |                                                   <span data-ttu-id="5e4f2-115">BizTalk Server 应用程序。</span><span class="sxs-lookup"><span data-stu-id="5e4f2-115">The BizTalk Server application.</span></span>                                                   |
   |   <span data-ttu-id="5e4f2-116">**创建时间**</span><span class="sxs-lookup"><span data-stu-id="5e4f2-116">**Creation Time**</span></span>    |                             <span data-ttu-id="5e4f2-117">查找在指定日期之前或之后创建的正在运行的服务实例。</span><span class="sxs-lookup"><span data-stu-id="5e4f2-117">Find running service instances created before or after the specified date.</span></span>                              |
   |  <span data-ttu-id="5e4f2-118">**按结果进行分组**</span><span class="sxs-lookup"><span data-stu-id="5e4f2-118">**Group Results By**</span></span>  |  <span data-ttu-id="5e4f2-119">可以按应用程序、主机名称、挂起操作类型、服务类别、服务实例状态或服务名称对结果进行分组。</span><span class="sxs-lookup"><span data-stu-id="5e4f2-119">You can group results by application, host name, pending operation type, service class, service instance status, or service name.</span></span>  |
   |     <span data-ttu-id="5e4f2-120">**Host Name**</span><span class="sxs-lookup"><span data-stu-id="5e4f2-120">**Host Name**</span></span>      |                                                    <span data-ttu-id="5e4f2-121">BizTalk 主机的名称。</span><span class="sxs-lookup"><span data-stu-id="5e4f2-121">The name of the BizTalk Host.</span></span>                                                    |
   |  <span data-ttu-id="5e4f2-122">**实例状态**</span><span class="sxs-lookup"><span data-stu-id="5e4f2-122">**Instance Status**</span></span>   |             <span data-ttu-id="5e4f2-123">可以搜索活动实例、已冻结的实例、准备运行的实例以及计划的实例。</span><span class="sxs-lookup"><span data-stu-id="5e4f2-123">You can search for active instances, dehydrated instances, ready to run instances, and scheduled instances.</span></span>             |
   |  <span data-ttu-id="5e4f2-124">**最大匹配数**</span><span class="sxs-lookup"><span data-stu-id="5e4f2-124">**Maximum Matches**</span></span>   |                                                  <span data-ttu-id="5e4f2-125">要显示的匹配数。</span><span class="sxs-lookup"><span data-stu-id="5e4f2-125">The number of matches to display.</span></span>                                                  |
   | <span data-ttu-id="5e4f2-126">**挂起的操作**</span><span class="sxs-lookup"><span data-stu-id="5e4f2-126">**Pending Operations**</span></span> |                      <span data-ttu-id="5e4f2-127">可以搜索状态为即将挂起或终止的正在运行的服务实例</span><span class="sxs-lookup"><span data-stu-id="5e4f2-127">You can search for running service instances that are pending suspension or termination.</span></span>                       |
   |   <span data-ttu-id="5e4f2-128">**服务类**</span><span class="sxs-lookup"><span data-stu-id="5e4f2-128">**Service Class**</span></span>    | <span data-ttu-id="5e4f2-129">可以搜索以下内容：独立适配器；消息传送；消息传送和独立适配器；MSMQT；业务流程；或路由故障报告。</span><span class="sxs-lookup"><span data-stu-id="5e4f2-129">You can search for isolated adapters; messaging; messaging, and isolated adapters; MSMQT; Orchestration; or Routing Failure Report.</span></span> |
   |    <span data-ttu-id="5e4f2-130">**服务名称**</span><span class="sxs-lookup"><span data-stu-id="5e4f2-130">**Service Name**</span></span>    |                                 <span data-ttu-id="5e4f2-131">可以按服务名对正在运行的服务实例进行分组或筛选。</span><span class="sxs-lookup"><span data-stu-id="5e4f2-131">You can group or filter running service instances by service name.</span></span>                                  |
   |  <span data-ttu-id="5e4f2-132">**服务类型 ID**</span><span class="sxs-lookup"><span data-stu-id="5e4f2-132">**Service Type ID**</span></span>   |                                        <span data-ttu-id="5e4f2-133">可以按服务类型 ID 对消息进行分组或筛选。</span><span class="sxs-lookup"><span data-stu-id="5e4f2-133">You can group or filter messages by service type ID.</span></span>                                         |


6. <span data-ttu-id="5e4f2-134">完成**值**根据需要将所选内容中所做的列**字段名**列。</span><span class="sxs-lookup"><span data-stu-id="5e4f2-134">Complete the **Value** column as appropriate for the selection you made in the **Field Name** column.</span></span>  

7. <span data-ttu-id="5e4f2-135">继续将其他行添加到查询根据需要，通过完成**字段名**，**运算符**，并**值**列，并单击**运行查询**。</span><span class="sxs-lookup"><span data-stu-id="5e4f2-135">Continue adding additional lines to the query as appropriate, by completing the **Field Name**, **Operator**, and **Values** columns, and then click **Run Query**.</span></span>  

## <a name="see-also"></a><span data-ttu-id="5e4f2-136">请参阅</span><span class="sxs-lookup"><span data-stu-id="5e4f2-136">See Also</span></span>  
 [<span data-ttu-id="5e4f2-137">使用管理控制台的“查询”选项卡</span><span class="sxs-lookup"><span data-stu-id="5e4f2-137">Using the Administration Console Query Tab</span></span>](../core/using-the-administration-console-query-tab.md)