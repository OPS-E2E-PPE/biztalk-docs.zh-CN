---
title: "如何控制结果列表的大小 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- results list [Orchestration Debugger], deleting columns
- results list [Orchestration Debugger], limiting list size
- Orchestration Debugger, results list
- results list [Orchestration Designer]
- results list [Orchestration Debugger], adding columns
ms.assetid: 4d41003f-5ea9-4599-8ec0-737c342ffdbd
caps.latest.revision: "16"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 80787e4c7dbac57aca9c787943846e924a1a7870
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="how-to-control-the-size-of-the-results-list"></a><span data-ttu-id="e57d0-102">如何控制“结果”列表的大小</span><span class="sxs-lookup"><span data-stu-id="e57d0-102">How to Control the Size of the Results List</span></span>
<span data-ttu-id="e57d0-103">上**组中心数据库**页[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理控制台，查询结果窗格中包含太多列的需要进行滚动才能查看它们的信息。</span><span class="sxs-lookup"><span data-stu-id="e57d0-103">On the **Group Hub** page of the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Administration console, the Query results pane contains so many columns of information that you need to scroll to view them.</span></span> <span data-ttu-id="e57d0-104">您可以添加或删除窗格中的列，以便只显示所需的信息。</span><span class="sxs-lookup"><span data-stu-id="e57d0-104">You can add or remove columns in the pane to display only the information that you need.</span></span> <span data-ttu-id="e57d0-105">要添加或删除列，请右键单击该查询结果窗格中，然后单击的任何部分**添加/删除列**上下文菜单上。</span><span class="sxs-lookup"><span data-stu-id="e57d0-105">To add or remove columns, right-click any part of the Query results pane and click **Add/Remove Columns** on the context menu.</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="e57d0-106">先决条件</span><span class="sxs-lookup"><span data-stu-id="e57d0-106">Prerequisites</span></span>  
 <span data-ttu-id="e57d0-107">必须以 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Administrators 组成员的身份登录，才能执行此过程。</span><span class="sxs-lookup"><span data-stu-id="e57d0-107">You must be logged on as a member of the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Administrators group to perform this procedure.</span></span>  
  
### <a name="to-add-or-remove-columns-in-the-results-list"></a><span data-ttu-id="e57d0-108">添加或删除结果列表中的列</span><span class="sxs-lookup"><span data-stu-id="e57d0-108">To add or remove columns in the results list</span></span>  
  
1.  <span data-ttu-id="e57d0-109">右键单击中的任意单元**查询结果**列表，，然后单击**添加/删除列**上下文菜单上。</span><span class="sxs-lookup"><span data-stu-id="e57d0-109">Right-click any cell in the **Query results** list, and then click **Add/Remove Columns** on the context menu.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="e57d0-110">已在结果列表中存在的项目显示在右侧**显示的列**。</span><span class="sxs-lookup"><span data-stu-id="e57d0-110">Items that are already present in the results list appear on the right side under **Displayed Columns**.</span></span> <span data-ttu-id="e57d0-111">在结果列表中不存在的项都显示在下的左边缘**可用列**。</span><span class="sxs-lookup"><span data-stu-id="e57d0-111">Items that are not present in the results list appear on the left side under **Available Columns**.</span></span>  
  
2.  <span data-ttu-id="e57d0-112">若要添加某一列，选择某一项从**可用列**单击**添加**将该列移到的列表**显示的列**。</span><span class="sxs-lookup"><span data-stu-id="e57d0-112">To add a column, select one of the items from **Available Columns** and click **Add** to move that column to the list of **Displayed Columns**.</span></span>  
  
3.  <span data-ttu-id="e57d0-113">若要删除某一列，选择某一项从**显示的列**单击**删除**将该列移到的列表**可用列**。</span><span class="sxs-lookup"><span data-stu-id="e57d0-113">To remove a column, select one of the items from **Displayed Columns** and click **Remove** to move that column to the list of **Available Columns**.</span></span>  
  
 <span data-ttu-id="e57d0-114">您可以使用创建或运行查询时提供的筛选器来控制查询返回的结果数。</span><span class="sxs-lookup"><span data-stu-id="e57d0-114">You can control the number of results that the query returns by using the filters that are provided when you create or run a query.</span></span>  
  
## <a name="columns-in-the-query-results-list"></a><span data-ttu-id="e57d0-115">“查询结果”列表中的列</span><span class="sxs-lookup"><span data-stu-id="e57d0-115">Columns in the Query Results List</span></span>  
 <span data-ttu-id="e57d0-116">查询结果显示在发起该查询的视图底部的“查询结果”窗格中。</span><span class="sxs-lookup"><span data-stu-id="e57d0-116">The query results are displayed in the Query results pane at the bottom of the view that originated the query.</span></span> <span data-ttu-id="e57d0-117">无法直接访问结果列表。</span><span class="sxs-lookup"><span data-stu-id="e57d0-117">You cannot directly access the results list.</span></span> <span data-ttu-id="e57d0-118">上下文菜单显示可以对当前活动视图中选定的记录执行的所有操作。</span><span class="sxs-lookup"><span data-stu-id="e57d0-118">The context menu shows all of the actions you can perform on the selected record within the currently active view.</span></span> <span data-ttu-id="e57d0-119">例如，如果记录包含服务实例 ID，则显示与服务有关的操作。</span><span class="sxs-lookup"><span data-stu-id="e57d0-119">For example, if the record contains a Service Instance ID, then service-related actions appear.</span></span> <span data-ttu-id="e57d0-120">如果记录包含消息 ID，则显示与消息有关的操作。</span><span class="sxs-lookup"><span data-stu-id="e57d0-120">If there is a Message ID, then message-related actions appear.</span></span>  
  
 <span data-ttu-id="e57d0-121">由于您可能不需要此完整列表中包含的所有信息，因此可以只选择要查看的列，或者替换所删除的列。</span><span class="sxs-lookup"><span data-stu-id="e57d0-121">Because you might not need all the information contained in this complete list, you can select only those columns you want to view, or you can replace columns that you removed.</span></span> <span data-ttu-id="e57d0-122">在按时间对结果列表进行排序时，实例可排序到毫秒，即使列表中未显示毫秒也是如此。</span><span class="sxs-lookup"><span data-stu-id="e57d0-122">When you sort the results list by time, the instances sort up to milliseconds, even if no milliseconds appear on the list.</span></span> <span data-ttu-id="e57d0-123">如果重新使用保存的查询时，则每次运行查询时，结果中只显示选择的列。</span><span class="sxs-lookup"><span data-stu-id="e57d0-123">When you reuse a saved query the results show only the columns selected each time the query is run.</span></span>  
  
 <span data-ttu-id="e57d0-124">下表显示了结果列表中显示的完整项目列表。</span><span class="sxs-lookup"><span data-stu-id="e57d0-124">The following table shows a complete list of the items that appear in the results list.</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="e57d0-125">**服务或消息字段**</span><span class="sxs-lookup"><span data-stu-id="e57d0-125">**Service or Message field**</span></span>|<span data-ttu-id="e57d0-126">**Description**</span><span class="sxs-lookup"><span data-stu-id="e57d0-126">**Description**</span></span>|  
|<span data-ttu-id="e57d0-127">服务名称</span><span class="sxs-lookup"><span data-stu-id="e57d0-127">Service Name</span></span>|<span data-ttu-id="e57d0-128">服务实例的名称。</span><span class="sxs-lookup"><span data-stu-id="e57d0-128">Name of the service instance.</span></span>|  
|<span data-ttu-id="e57d0-129">事件类型</span><span class="sxs-lookup"><span data-stu-id="e57d0-129">Event Type</span></span>|<span data-ttu-id="e57d0-130">服务类型，例如消息传送（报告为管道）、业务流程或传输适配器。</span><span class="sxs-lookup"><span data-stu-id="e57d0-130">Type of service (for example, messaging (reported as Pipeline), orchestration, transport adapter).</span></span>|  
|<span data-ttu-id="e57d0-131">错误说明</span><span class="sxs-lookup"><span data-stu-id="e57d0-131">Error Description</span></span>|<span data-ttu-id="e57d0-132">出现错误时有关错误的说明。</span><span class="sxs-lookup"><span data-stu-id="e57d0-132">Description of the error if one occurred.</span></span>|  
|<span data-ttu-id="e57d0-133">State</span><span class="sxs-lookup"><span data-stu-id="e57d0-133">State</span></span>|<span data-ttu-id="e57d0-134">运行查询时的操作状态。</span><span class="sxs-lookup"><span data-stu-id="e57d0-134">State of the operation when the query was run.</span></span>|  
|<span data-ttu-id="e57d0-135">错误代码</span><span class="sxs-lookup"><span data-stu-id="e57d0-135">Error Code</span></span>|<span data-ttu-id="e57d0-136">出现错误时的错误代码。</span><span class="sxs-lookup"><span data-stu-id="e57d0-136">Code of the error if one occurred.</span></span>|  
|<span data-ttu-id="e57d0-137">解密证书</span><span class="sxs-lookup"><span data-stu-id="e57d0-137">Decryption Certificate</span></span>|<span data-ttu-id="e57d0-138">显示与消息或服务相关的证书信息。</span><span class="sxs-lookup"><span data-stu-id="e57d0-138">Shows the certificate information relating to the message or service.</span></span>|  
|<span data-ttu-id="e57d0-139">Duration</span><span class="sxs-lookup"><span data-stu-id="e57d0-139">Duration</span></span>|<span data-ttu-id="e57d0-140">操作完成所用的时间。</span><span class="sxs-lookup"><span data-stu-id="e57d0-140">Time for the operation to complete.</span></span>|  
|<span data-ttu-id="e57d0-141">端口名称</span><span class="sxs-lookup"><span data-stu-id="e57d0-141">Port Name</span></span>|<span data-ttu-id="e57d0-142">实例流中涉及的端口。</span><span class="sxs-lookup"><span data-stu-id="e57d0-142">Port involved in the flow of the instance.</span></span>|  
|<span data-ttu-id="e57d0-143">签名</span><span class="sxs-lookup"><span data-stu-id="e57d0-143">Signature</span></span>|<span data-ttu-id="e57d0-144">消息的数字签名信息。</span><span class="sxs-lookup"><span data-stu-id="e57d0-144">Digital signature information of the message.</span></span>|  
|<span data-ttu-id="e57d0-145">Size</span><span class="sxs-lookup"><span data-stu-id="e57d0-145">Size</span></span>|<span data-ttu-id="e57d0-146">消息大小（以字节为单位）。</span><span class="sxs-lookup"><span data-stu-id="e57d0-146">Size of the message in bytes.</span></span>|  
|<span data-ttu-id="e57d0-147">Start Time</span><span class="sxs-lookup"><span data-stu-id="e57d0-147">Start Time</span></span>|<span data-ttu-id="e57d0-148">时间操作已开始。</span><span class="sxs-lookup"><span data-stu-id="e57d0-148">Time the operation started.</span></span>|  
|<span data-ttu-id="e57d0-149">结束时间</span><span class="sxs-lookup"><span data-stu-id="e57d0-149">End Time</span></span>|<span data-ttu-id="e57d0-150">操作结束时间。</span><span class="sxs-lookup"><span data-stu-id="e57d0-150">Time the operation ended.</span></span>|  
|<span data-ttu-id="e57d0-151">部分计数</span><span class="sxs-lookup"><span data-stu-id="e57d0-151">Part Count</span></span>|<span data-ttu-id="e57d0-152">消息中的部分数。</span><span class="sxs-lookup"><span data-stu-id="e57d0-152">Number of parts in the message.</span></span>|  
|<span data-ttu-id="e57d0-153">聚会</span><span class="sxs-lookup"><span data-stu-id="e57d0-153">Party</span></span>|<span data-ttu-id="e57d0-154">启动操作的参与方的标识符。</span><span class="sxs-lookup"><span data-stu-id="e57d0-154">Identifier of the party starting the operation.</span></span>|  
|<span data-ttu-id="e57d0-155">URI</span><span class="sxs-lookup"><span data-stu-id="e57d0-155">URI</span></span>|<span data-ttu-id="e57d0-156">发起方的 URI。</span><span class="sxs-lookup"><span data-stu-id="e57d0-156">URI of the initiating party.</span></span>|  
|<span data-ttu-id="e57d0-157">TimeStamp</span><span class="sxs-lookup"><span data-stu-id="e57d0-157">TimeStamp</span></span>|<span data-ttu-id="e57d0-158">时间操作已开始。</span><span class="sxs-lookup"><span data-stu-id="e57d0-158">Time the operation started.</span></span>|  
|<span data-ttu-id="e57d0-159">主机</span><span class="sxs-lookup"><span data-stu-id="e57d0-159">Host</span></span>|<span data-ttu-id="e57d0-160">运行服务实例的 BizTalk 主机的名称。</span><span class="sxs-lookup"><span data-stu-id="e57d0-160">Name of the BizTalk Host running the service instance.</span></span>|  
|<span data-ttu-id="e57d0-161">程序集名称</span><span class="sxs-lookup"><span data-stu-id="e57d0-161">Assembly Name</span></span>|<span data-ttu-id="e57d0-162">实现服务实例的 .NET 程序集的名称。</span><span class="sxs-lookup"><span data-stu-id="e57d0-162">Name of the .NET assembly that implements the service instance.</span></span>|  
|<span data-ttu-id="e57d0-163">程序集版本</span><span class="sxs-lookup"><span data-stu-id="e57d0-163">Assembly Version</span></span>|<span data-ttu-id="e57d0-164">相关程序集的版本号。</span><span class="sxs-lookup"><span data-stu-id="e57d0-164">Version number of the related assembly.</span></span>|  
|<span data-ttu-id="e57d0-165">部署时</span><span class="sxs-lookup"><span data-stu-id="e57d0-165">Deployment Time</span></span>|<span data-ttu-id="e57d0-166">将服务实例程序集部署到 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 的时间。</span><span class="sxs-lookup"><span data-stu-id="e57d0-166">Time that the service instance assembly deployed into [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)].</span></span>|  
|<span data-ttu-id="e57d0-167">活动 ID</span><span class="sxs-lookup"><span data-stu-id="e57d0-167">Activity ID</span></span>|<span data-ttu-id="e57d0-168">标识唯一的服务实例活动（例如，管道/业务流程发送/接收的消息具有相同的 ID）。</span><span class="sxs-lookup"><span data-stu-id="e57d0-168">Identifies unique service instance activity (for example, messages sent/received by the pipeline/orchestration have the same ID).</span></span>|  
|<span data-ttu-id="e57d0-169">服务实例 ID</span><span class="sxs-lookup"><span data-stu-id="e57d0-169">Service Instance ID</span></span>|<span data-ttu-id="e57d0-170">标识正在运行的服务实例的全局唯一标识符 (GUID)。</span><span class="sxs-lookup"><span data-stu-id="e57d0-170">Globally unique identifier (GUID) that identifies a run of a service instance.</span></span>|  
|<span data-ttu-id="e57d0-171">消息实例 ID</span><span class="sxs-lookup"><span data-stu-id="e57d0-171">Message Instance ID</span></span>|<span data-ttu-id="e57d0-172">标识消息实例的全局唯一标识符 (GUID)。</span><span class="sxs-lookup"><span data-stu-id="e57d0-172">Globally unique identifier (GUID) that identifies a message instance.</span></span>|  
|<span data-ttu-id="e57d0-173">服务 ID</span><span class="sxs-lookup"><span data-stu-id="e57d0-173">Service ID</span></span>|<span data-ttu-id="e57d0-174">标识服务的全局唯一标识符 (GUID)。</span><span class="sxs-lookup"><span data-stu-id="e57d0-174">Globally unique identifier (GUID) that identifies a service.</span></span>|  
|<span data-ttu-id="e57d0-175">服务类别</span><span class="sxs-lookup"><span data-stu-id="e57d0-175">Service Class</span></span>|<span data-ttu-id="e57d0-176">类类型（管道或业务流程）。</span><span class="sxs-lookup"><span data-stu-id="e57d0-176">Type of class (pipeline or orchestration).</span></span>|  
|<span data-ttu-id="e57d0-177">服务类别 ID</span><span class="sxs-lookup"><span data-stu-id="e57d0-177">Service Class ID</span></span>|<span data-ttu-id="e57d0-178">用于标识服务（例如业务流程）的与服务无关的 GUID。</span><span class="sxs-lookup"><span data-stu-id="e57d0-178">A service-independent GUID that identifies a service (for example, orchestration).</span></span>|  
|<span data-ttu-id="e57d0-179">图标</span><span class="sxs-lookup"><span data-stu-id="e57d0-179">Icon</span></span>|<span data-ttu-id="e57d0-180">结果行的图标。</span><span class="sxs-lookup"><span data-stu-id="e57d0-180">Icon of the result row.</span></span>|  
|<span data-ttu-id="e57d0-181">适配器</span><span class="sxs-lookup"><span data-stu-id="e57d0-181">Adapter</span></span>|<span data-ttu-id="e57d0-182">操作中使用的适配器。</span><span class="sxs-lookup"><span data-stu-id="e57d0-182">Adapter used in the operation.</span></span>|