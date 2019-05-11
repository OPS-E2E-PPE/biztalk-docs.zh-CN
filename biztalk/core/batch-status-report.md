---
title: 批处理状态报告 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 04dad016-e7bb-45cd-b36a-a9c83d073501
caps.latest.revision: 14
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 6a717d35073ead8a15aaec47cdcbe85e41988107
ms.sourcegitcommit: d27732e569b0897361dfaebca8352aa97bb7efe1
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/10/2019
ms.locfileid: "65529169"
---
# <a name="batch-status-report"></a><span data-ttu-id="14b79-102">批处理状态报告</span><span class="sxs-lookup"><span data-stu-id="14b79-102">Batch Status Report</span></span>
<span data-ttu-id="14b79-103">此报告显示批处理业务流程实例的活动。</span><span class="sxs-lookup"><span data-stu-id="14b79-103">This report shows the activity of instances of the batching orchestration.</span></span> <span data-ttu-id="14b79-104">在报表中的每一行指示批处理业务流程的单个实例正在处理的批的状态。</span><span class="sxs-lookup"><span data-stu-id="14b79-104">Each row in the report indicates the status of the batches being processed by a single instance of the batching orchestration.</span></span>  
  
 <span data-ttu-id="14b79-105">保留批的状态中批处理状态报告中，将不报告，但在交换 /ACK 状态报告中报告。</span><span class="sxs-lookup"><span data-stu-id="14b79-105">The status of preserved batches is not reported in the Batch Status Report, but is reported in the Interchange/ACK Status report.</span></span>  
  
## <a name="fields-in-the-status-report"></a><span data-ttu-id="14b79-106">在状态报告中的字段</span><span class="sxs-lookup"><span data-stu-id="14b79-106">Fields in the Status Report</span></span>  
 <span data-ttu-id="14b79-107">批处理状态报告显示批处理交换的以下信息：</span><span class="sxs-lookup"><span data-stu-id="14b79-107">The Batch Status Report displays the following information for batched interchanges:</span></span>  
  
-   <span data-ttu-id="14b79-108">批处理状态</span><span class="sxs-lookup"><span data-stu-id="14b79-108">Batch Status</span></span>  
  
-   <span data-ttu-id="14b79-109">批处理名称</span><span class="sxs-lookup"><span data-stu-id="14b79-109">Batch Name</span></span>  
  
-   <span data-ttu-id="14b79-110">目标参与方名称</span><span class="sxs-lookup"><span data-stu-id="14b79-110">Destination Party Name</span></span>  
  
-   <span data-ttu-id="14b79-111">激活时间</span><span class="sxs-lookup"><span data-stu-id="14b79-111">Activation Time</span></span>  
  
-   <span data-ttu-id="14b79-112">批处理出现次数计数</span><span class="sxs-lookup"><span data-stu-id="14b79-112">Batch Occurrence</span></span>  
  
-   <span data-ttu-id="14b79-113">EDI 编码类型</span><span class="sxs-lookup"><span data-stu-id="14b79-113">EDI Encoding Type</span></span>  
  
-   <span data-ttu-id="14b79-114">批处理类型</span><span class="sxs-lookup"><span data-stu-id="14b79-114">Batch Type</span></span>  
  
-   <span data-ttu-id="14b79-115">批处理目标</span><span class="sxs-lookup"><span data-stu-id="14b79-115">Batch Target</span></span>  
  
-   <span data-ttu-id="14b79-116">批处理元素计数： 批处理元素的数量已累计的批处理业务流程实例</span><span class="sxs-lookup"><span data-stu-id="14b79-116">Batch Element Count: how many batch elements have been accumulated by the batching orchestration instance</span></span>  
  
-   <span data-ttu-id="14b79-117">被拒绝的元素计数</span><span class="sxs-lookup"><span data-stu-id="14b79-117">Rejected Elements Count</span></span>  
  
-   <span data-ttu-id="14b79-118">最新的操作：可以是激活的批处理、 计划发布、 基于计数的发布、 手动覆盖发布、 批处理已终止/停止发布、 添加的元素或外部发布</span><span class="sxs-lookup"><span data-stu-id="14b79-118">Latest Action: Can be Batch Activated, Scheduled Release, Count Based Release, Manual Override Release, Batch Terminated/Stop Release, Element Added, or External Release</span></span>  
  
-   <span data-ttu-id="14b79-119">交换控制编号</span><span class="sxs-lookup"><span data-stu-id="14b79-119">Interchange Control Number</span></span>  
  
-   <span data-ttu-id="14b79-120">交换日期时间</span><span class="sxs-lookup"><span data-stu-id="14b79-120">Interchange Date Time</span></span>  
  
-   <span data-ttu-id="14b79-121">（默认情况下不显示） 的批大小 （以字符为单位）</span><span class="sxs-lookup"><span data-stu-id="14b79-121">Batch Size (in characters) (not displayed by default)</span></span>  
  
## <a name="view-related-interchanges-status-reports"></a><span data-ttu-id="14b79-122">查看相关的交换状态报告</span><span class="sxs-lookup"><span data-stu-id="14b79-122">View Related Interchanges Status Reports</span></span>  
 <span data-ttu-id="14b79-123">如果您右键单击的交换或确认批处理状态报告中列出，可以显示有关与批处理相关的交换的详细信息。</span><span class="sxs-lookup"><span data-stu-id="14b79-123">If you right-click an interchange or acknowledgment listed in the Batch Status Report, you can display details about the interchanges related to the batch.</span></span>  
  
## <a name="fields-in-the-query-expression-for-the-status-report"></a><span data-ttu-id="14b79-124">在状态报告的查询表达式中的字段</span><span class="sxs-lookup"><span data-stu-id="14b79-124">Fields in the Query Expression for the Status Report</span></span>  
 <span data-ttu-id="14b79-125">您可以更改用于确定所显示数据的查询表达式中的字段来自定义批处理状态报告。</span><span class="sxs-lookup"><span data-stu-id="14b79-125">You can customize the Batch Status Report by changing the fields in the query expression that determines the data displayed.</span></span> <span data-ttu-id="14b79-126">可以使用下列域：</span><span class="sxs-lookup"><span data-stu-id="14b79-126">The following fields are available:</span></span>  
  
|||||  
|-|-|-|-|  
|<span data-ttu-id="14b79-127">查询表达式字段</span><span class="sxs-lookup"><span data-stu-id="14b79-127">Query Expression Field</span></span>|<span data-ttu-id="14b79-128">可能的运算符</span><span class="sxs-lookup"><span data-stu-id="14b79-128">Potential Operators</span></span>|<span data-ttu-id="14b79-129">可能的值</span><span class="sxs-lookup"><span data-stu-id="14b79-129">Potential Values</span></span>|<span data-ttu-id="14b79-130">默认情况下包含？</span><span class="sxs-lookup"><span data-stu-id="14b79-130">Included By Default?</span></span>|  
|<span data-ttu-id="14b79-131">搜索</span><span class="sxs-lookup"><span data-stu-id="14b79-131">Search for</span></span>|<span data-ttu-id="14b79-132">等于</span><span class="sxs-lookup"><span data-stu-id="14b79-132">Equals</span></span>|<span data-ttu-id="14b79-133">批处理状态</span><span class="sxs-lookup"><span data-stu-id="14b79-133">Batch Status</span></span>|<span data-ttu-id="14b79-134">是（必需）</span><span class="sxs-lookup"><span data-stu-id="14b79-134">Yes (required)</span></span>|  
|<span data-ttu-id="14b79-135">批处理状态</span><span class="sxs-lookup"><span data-stu-id="14b79-135">Batch Status</span></span>|<span data-ttu-id="14b79-136">等于</span><span class="sxs-lookup"><span data-stu-id="14b79-136">Equals</span></span><br /><br /> <span data-ttu-id="14b79-137">不等于</span><span class="sxs-lookup"><span data-stu-id="14b79-137">Not Equals</span></span>|<span data-ttu-id="14b79-138">定义：配置了批实例但开始日期时间晚于当前日期时间。</span><span class="sxs-lookup"><span data-stu-id="14b79-138">Defined: The batch instance is configured but the start date time is later than the current date time.</span></span><br /><br /> <span data-ttu-id="14b79-139">处于活动状态 （默认值）：批处理实例已配置且正在收集用于批处理的事务集。</span><span class="sxs-lookup"><span data-stu-id="14b79-139">Active (default): The batch instance is configured and is collecting transaction sets for a batch.</span></span> <span data-ttu-id="14b79-140">开始日期时间是早于当前日期时间。</span><span class="sxs-lookup"><span data-stu-id="14b79-140">The start date time is earlier than the current date time.</span></span><br /><br /> <span data-ttu-id="14b79-141">发布日期：已满足发布条件，并已发送批，或处理任何消息前，停止批处理业务流程。</span><span class="sxs-lookup"><span data-stu-id="14b79-141">Released: The release criteria has been met, and the batch has been sent, or that the batch orchestration was stopped before any messages were processed.</span></span><br /><br /> <span data-ttu-id="14b79-142">已完成：发布条件已满足，但尚未发送批。</span><span class="sxs-lookup"><span data-stu-id="14b79-142">Completed: The release criteria has been met, but the batch has not been sent.</span></span><br /><br /> <span data-ttu-id="14b79-143">所有：显示处于上述状态之一的任何批处理实例。</span><span class="sxs-lookup"><span data-stu-id="14b79-143">All: Display any batch instance that is in one of the above states.</span></span>|<span data-ttu-id="14b79-144">是</span><span class="sxs-lookup"><span data-stu-id="14b79-144">Yes</span></span>|  
|<span data-ttu-id="14b79-145">最大匹配数</span><span class="sxs-lookup"><span data-stu-id="14b79-145">Maximum Matches</span></span>|<span data-ttu-id="14b79-146">等于</span><span class="sxs-lookup"><span data-stu-id="14b79-146">Equals</span></span>|<span data-ttu-id="14b79-147">整数 （默认值为 50）</span><span class="sxs-lookup"><span data-stu-id="14b79-147">Integer (default of 50)</span></span>|<span data-ttu-id="14b79-148">是</span><span class="sxs-lookup"><span data-stu-id="14b79-148">Yes</span></span>|  
|<span data-ttu-id="14b79-149">激活日期时间</span><span class="sxs-lookup"><span data-stu-id="14b79-149">Activation Date Time</span></span>|<span data-ttu-id="14b79-150">小于或等于</span><span class="sxs-lookup"><span data-stu-id="14b79-150">Less Than or Equals</span></span><br /><br /> <span data-ttu-id="14b79-151">大于或等于</span><span class="sxs-lookup"><span data-stu-id="14b79-151">Greater Than or Equals</span></span>|<span data-ttu-id="14b79-152">日期时间</span><span class="sxs-lookup"><span data-stu-id="14b79-152">Date Time</span></span><br /><br /> <span data-ttu-id="14b79-153">今天</span><span class="sxs-lookup"><span data-stu-id="14b79-153">Today</span></span><br /><br /> <span data-ttu-id="14b79-154">Today-5</span><span class="sxs-lookup"><span data-stu-id="14b79-154">Today - 5</span></span>|<span data-ttu-id="14b79-155">否</span><span class="sxs-lookup"><span data-stu-id="14b79-155">No</span></span><br /><br /> <span data-ttu-id="14b79-156">注意：可以包含多个查询表达式中。</span><span class="sxs-lookup"><span data-stu-id="14b79-156">Note: Can be included more than once in the query expression.</span></span>|  
|<span data-ttu-id="14b79-157">批处理名称</span><span class="sxs-lookup"><span data-stu-id="14b79-157">Batch Name</span></span>|<span data-ttu-id="14b79-158">等于</span><span class="sxs-lookup"><span data-stu-id="14b79-158">Equals</span></span>|<span data-ttu-id="14b79-159">所有 （默认值）</span><span class="sxs-lookup"><span data-stu-id="14b79-159">All (Default)</span></span><br /><br /> <span data-ttu-id="14b79-160">特定批处理名称</span><span class="sxs-lookup"><span data-stu-id="14b79-160">Specific batch name</span></span>|<span data-ttu-id="14b79-161">否</span><span class="sxs-lookup"><span data-stu-id="14b79-161">No</span></span>|  
|<span data-ttu-id="14b79-162">目标参与方</span><span class="sxs-lookup"><span data-stu-id="14b79-162">Destination Party</span></span>|<span data-ttu-id="14b79-163">等于</span><span class="sxs-lookup"><span data-stu-id="14b79-163">Equals</span></span>|<span data-ttu-id="14b79-164">所有 （默认值）</span><span class="sxs-lookup"><span data-stu-id="14b79-164">All (default)</span></span><br /><br /> <span data-ttu-id="14b79-165">特定参与方名称</span><span class="sxs-lookup"><span data-stu-id="14b79-165">Specific party name</span></span>|<span data-ttu-id="14b79-166">否</span><span class="sxs-lookup"><span data-stu-id="14b79-166">No</span></span>|  
|<span data-ttu-id="14b79-167">EDI 编码类型</span><span class="sxs-lookup"><span data-stu-id="14b79-167">EDI encoding type</span></span>|<span data-ttu-id="14b79-168">等于</span><span class="sxs-lookup"><span data-stu-id="14b79-168">Equals</span></span>|<span data-ttu-id="14b79-169">X12</span><span class="sxs-lookup"><span data-stu-id="14b79-169">X12</span></span><br /><br /> <span data-ttu-id="14b79-170">EDIFACT</span><span class="sxs-lookup"><span data-stu-id="14b79-170">EDIFACT</span></span><br /><br /> <span data-ttu-id="14b79-171">所有 （默认值）</span><span class="sxs-lookup"><span data-stu-id="14b79-171">All (default)</span></span>|<span data-ttu-id="14b79-172">否</span><span class="sxs-lookup"><span data-stu-id="14b79-172">No</span></span>|  
  
