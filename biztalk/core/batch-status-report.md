---
title: 批处理状态报告 |Microsoft 文档
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
ms.openlocfilehash: 7c033f58432c8ae5a2d87b87b56223b8f64a7201
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22231797"
---
# <a name="batch-status-report"></a><span data-ttu-id="d01f4-102">批处理状态报告</span><span class="sxs-lookup"><span data-stu-id="d01f4-102">Batch Status Report</span></span>
<span data-ttu-id="d01f4-103">此报告显示批处理业务流程实例的活动。</span><span class="sxs-lookup"><span data-stu-id="d01f4-103">This report shows the activity of instances of the batching orchestration.</span></span> <span data-ttu-id="d01f4-104">报告中的每行都指示出正在由一个批处理业务流程实例处理的批的状态。</span><span class="sxs-lookup"><span data-stu-id="d01f4-104">Each row in the report indicates the status of the batches being processed by a single instance of the batching orchestration.</span></span>  
  
 <span data-ttu-id="d01f4-105">保留批的状态不是在批处理状态报告中报告，而是在交换/确认状态报告中报告。</span><span class="sxs-lookup"><span data-stu-id="d01f4-105">The status of preserved batches is not reported in the Batch Status Report, but is reported in the Interchange/ACK Status report.</span></span>  
  
## <a name="fields-in-the-status-report"></a><span data-ttu-id="d01f4-106">状态报告中的字段</span><span class="sxs-lookup"><span data-stu-id="d01f4-106">Fields in the Status Report</span></span>  
 <span data-ttu-id="d01f4-107">批处理状态报告显示批处理交换的下列信息：</span><span class="sxs-lookup"><span data-stu-id="d01f4-107">The Batch Status Report displays the following information for batched interchanges:</span></span>  
  
-   <span data-ttu-id="d01f4-108">批状态</span><span class="sxs-lookup"><span data-stu-id="d01f4-108">Batch Status</span></span>  
  
-   <span data-ttu-id="d01f4-109">批名称</span><span class="sxs-lookup"><span data-stu-id="d01f4-109">Batch Name</span></span>  
  
-   <span data-ttu-id="d01f4-110">目标方名称</span><span class="sxs-lookup"><span data-stu-id="d01f4-110">Destination Party Name</span></span>  
  
-   <span data-ttu-id="d01f4-111">激活时间</span><span class="sxs-lookup"><span data-stu-id="d01f4-111">Activation Time</span></span>  
  
-   <span data-ttu-id="d01f4-112">批处理出现次数计数</span><span class="sxs-lookup"><span data-stu-id="d01f4-112">Batch Occurrence</span></span>  
  
-   <span data-ttu-id="d01f4-113">EDI 编码类型</span><span class="sxs-lookup"><span data-stu-id="d01f4-113">EDI Encoding Type</span></span>  
  
-   <span data-ttu-id="d01f4-114">批处理类型</span><span class="sxs-lookup"><span data-stu-id="d01f4-114">Batch Type</span></span>  
  
-   <span data-ttu-id="d01f4-115">批处理目标</span><span class="sxs-lookup"><span data-stu-id="d01f4-115">Batch Target</span></span>  
  
-   <span data-ttu-id="d01f4-116">批处理元素计数： 进行批处理的业务流程实例累积批处理元素数量</span><span class="sxs-lookup"><span data-stu-id="d01f4-116">Batch Element Count: how many batch elements have been accumulated by the batching orchestration instance</span></span>  
  
-   <span data-ttu-id="d01f4-117">被拒绝元素计数</span><span class="sxs-lookup"><span data-stu-id="d01f4-117">Rejected Elements Count</span></span>  
  
-   <span data-ttu-id="d01f4-118">最新的操作： 可以是批处理激活、 计划的版本、 计数基于版本、 手动重写版本、 批处理已终止/停止版本、 添加元素，或外部的版本</span><span class="sxs-lookup"><span data-stu-id="d01f4-118">Latest Action: Can be Batch Activated, Scheduled Release, Count Based Release, Manual Override Release, Batch Terminated/Stop Release, Element Added, or External Release</span></span>  
  
-   <span data-ttu-id="d01f4-119">交换控制编号</span><span class="sxs-lookup"><span data-stu-id="d01f4-119">Interchange Control Number</span></span>  
  
-   <span data-ttu-id="d01f4-120">交换日期时间</span><span class="sxs-lookup"><span data-stu-id="d01f4-120">Interchange Date Time</span></span>  
  
-   <span data-ttu-id="d01f4-121">批大小（以字符数表示）（默认情况下不显示）</span><span class="sxs-lookup"><span data-stu-id="d01f4-121">Batch Size (in characters) (not displayed by default)</span></span>  
  
## <a name="view-related-interchanges-status-reports"></a><span data-ttu-id="d01f4-122">查看相关交换状态报告</span><span class="sxs-lookup"><span data-stu-id="d01f4-122">View Related Interchanges Status Reports</span></span>  
 <span data-ttu-id="d01f4-123">如果右键单击批处理状态报告中列出的交换或确认，则可以显示有关与批处理相关的交换的详细信息。</span><span class="sxs-lookup"><span data-stu-id="d01f4-123">If you right-click an interchange or acknowledgment listed in the Batch Status Report, you can display details about the interchanges related to the batch.</span></span>  
  
## <a name="fields-in-the-query-expression-for-the-status-report"></a><span data-ttu-id="d01f4-124">状态报告的查询表达式中的字段</span><span class="sxs-lookup"><span data-stu-id="d01f4-124">Fields in the Query Expression for the Status Report</span></span>  
 <span data-ttu-id="d01f4-125">您可更改用于确定显示的数据的查询表达式中的字段来自定义批处理状态报告。</span><span class="sxs-lookup"><span data-stu-id="d01f4-125">You can customize the Batch Status Report by changing the fields in the query expression that determines the data displayed.</span></span> <span data-ttu-id="d01f4-126">下列字段可用：</span><span class="sxs-lookup"><span data-stu-id="d01f4-126">The following fields are available:</span></span>  
  
|||||  
|-|-|-|-|  
|<span data-ttu-id="d01f4-127">查询表达式字段</span><span class="sxs-lookup"><span data-stu-id="d01f4-127">Query Expression Field</span></span>|<span data-ttu-id="d01f4-128">可能的运算符</span><span class="sxs-lookup"><span data-stu-id="d01f4-128">Potential Operators</span></span>|<span data-ttu-id="d01f4-129">可能的值</span><span class="sxs-lookup"><span data-stu-id="d01f4-129">Potential Values</span></span>|<span data-ttu-id="d01f4-130">默认情况下是否包括？</span><span class="sxs-lookup"><span data-stu-id="d01f4-130">Included By Default?</span></span>|  
|<span data-ttu-id="d01f4-131">搜索</span><span class="sxs-lookup"><span data-stu-id="d01f4-131">Search for</span></span>|<span data-ttu-id="d01f4-132">等于</span><span class="sxs-lookup"><span data-stu-id="d01f4-132">Equals</span></span>|<span data-ttu-id="d01f4-133">批状态</span><span class="sxs-lookup"><span data-stu-id="d01f4-133">Batch Status</span></span>|<span data-ttu-id="d01f4-134">是（必需）</span><span class="sxs-lookup"><span data-stu-id="d01f4-134">Yes (required)</span></span>|  
|<span data-ttu-id="d01f4-135">批状态</span><span class="sxs-lookup"><span data-stu-id="d01f4-135">Batch Status</span></span>|<span data-ttu-id="d01f4-136">等于</span><span class="sxs-lookup"><span data-stu-id="d01f4-136">Equals</span></span><br /><br /> <span data-ttu-id="d01f4-137">不等于</span><span class="sxs-lookup"><span data-stu-id="d01f4-137">Not Equals</span></span>|<span data-ttu-id="d01f4-138">定义： 配置的批处理实例但开始日期时间晚于当前日期时间。</span><span class="sxs-lookup"><span data-stu-id="d01f4-138">Defined: The batch instance is configured but the start date time is later than the current date time.</span></span><br /><br /> <span data-ttu-id="d01f4-139">活动 （默认值）： 批处理实例配置并且正在收集一批的事务集。</span><span class="sxs-lookup"><span data-stu-id="d01f4-139">Active (default): The batch instance is configured and is collecting transaction sets for a batch.</span></span> <span data-ttu-id="d01f4-140">起始日期时间早于当前日期时间。</span><span class="sxs-lookup"><span data-stu-id="d01f4-140">The start date time is earlier than the current date time.</span></span><br /><br /> <span data-ttu-id="d01f4-141">发布日期： 已满足释放条件，并已发送的批，或批处理业务流程已停止之前已处理的任何消息。</span><span class="sxs-lookup"><span data-stu-id="d01f4-141">Released: The release criteria has been met, and the batch has been sent, or that the batch orchestration was stopped before any messages were processed.</span></span><br /><br /> <span data-ttu-id="d01f4-142">完成： 释放条件已满足，但尚未发送批处理。</span><span class="sxs-lookup"><span data-stu-id="d01f4-142">Completed: The release criteria has been met, but the batch has not been sent.</span></span><br /><br /> <span data-ttu-id="d01f4-143">All： 显示任何处于上述状态之一的批处理实例。</span><span class="sxs-lookup"><span data-stu-id="d01f4-143">All: Display any batch instance that is in one of the above states.</span></span>|<span data-ttu-id="d01f4-144">是</span><span class="sxs-lookup"><span data-stu-id="d01f4-144">Yes</span></span>|  
|<span data-ttu-id="d01f4-145">最大匹配数</span><span class="sxs-lookup"><span data-stu-id="d01f4-145">Maximum Matches</span></span>|<span data-ttu-id="d01f4-146">等于</span><span class="sxs-lookup"><span data-stu-id="d01f4-146">Equals</span></span>|<span data-ttu-id="d01f4-147">整数（默认值为 50）</span><span class="sxs-lookup"><span data-stu-id="d01f4-147">Integer (default of 50)</span></span>|<span data-ttu-id="d01f4-148">是</span><span class="sxs-lookup"><span data-stu-id="d01f4-148">Yes</span></span>|  
|<span data-ttu-id="d01f4-149">激活日期时间</span><span class="sxs-lookup"><span data-stu-id="d01f4-149">Activation Date Time</span></span>|<span data-ttu-id="d01f4-150">小于或等于</span><span class="sxs-lookup"><span data-stu-id="d01f4-150">Less Than or Equals</span></span><br /><br /> <span data-ttu-id="d01f4-151">大于或等于</span><span class="sxs-lookup"><span data-stu-id="d01f4-151">Greater Than or Equals</span></span>|<span data-ttu-id="d01f4-152">日期时间</span><span class="sxs-lookup"><span data-stu-id="d01f4-152">Date Time</span></span><br /><br /> <span data-ttu-id="d01f4-153">今天</span><span class="sxs-lookup"><span data-stu-id="d01f4-153">Today</span></span><br /><br /> <span data-ttu-id="d01f4-154">今日 - 5</span><span class="sxs-lookup"><span data-stu-id="d01f4-154">Today - 5</span></span>|<span data-ttu-id="d01f4-155">是</span><span class="sxs-lookup"><span data-stu-id="d01f4-155">No</span></span><br /><br /> <span data-ttu-id="d01f4-156">注意：可在查询表达式中多次使用。</span><span class="sxs-lookup"><span data-stu-id="d01f4-156">Note: Can be included more than once in the query expression.</span></span>|  
|<span data-ttu-id="d01f4-157">批名称</span><span class="sxs-lookup"><span data-stu-id="d01f4-157">Batch Name</span></span>|<span data-ttu-id="d01f4-158">等于</span><span class="sxs-lookup"><span data-stu-id="d01f4-158">Equals</span></span>|<span data-ttu-id="d01f4-159">全部（默认值）</span><span class="sxs-lookup"><span data-stu-id="d01f4-159">All (Default)</span></span><br /><br /> <span data-ttu-id="d01f4-160">特定批处理名称</span><span class="sxs-lookup"><span data-stu-id="d01f4-160">Specific batch name</span></span>|<span data-ttu-id="d01f4-161">是</span><span class="sxs-lookup"><span data-stu-id="d01f4-161">No</span></span>|  
|<span data-ttu-id="d01f4-162">目标方</span><span class="sxs-lookup"><span data-stu-id="d01f4-162">Destination Party</span></span>|<span data-ttu-id="d01f4-163">等于</span><span class="sxs-lookup"><span data-stu-id="d01f4-163">Equals</span></span>|<span data-ttu-id="d01f4-164">所有 （默认值）</span><span class="sxs-lookup"><span data-stu-id="d01f4-164">All (default)</span></span><br /><br /> <span data-ttu-id="d01f4-165">特定参与方名称</span><span class="sxs-lookup"><span data-stu-id="d01f4-165">Specific party name</span></span>|<span data-ttu-id="d01f4-166">是</span><span class="sxs-lookup"><span data-stu-id="d01f4-166">No</span></span>|  
|<span data-ttu-id="d01f4-167">EDI 编码类型</span><span class="sxs-lookup"><span data-stu-id="d01f4-167">EDI encoding type</span></span>|<span data-ttu-id="d01f4-168">等于</span><span class="sxs-lookup"><span data-stu-id="d01f4-168">Equals</span></span>|<span data-ttu-id="d01f4-169">X12</span><span class="sxs-lookup"><span data-stu-id="d01f4-169">X12</span></span><br /><br /> <span data-ttu-id="d01f4-170">EDIFACT</span><span class="sxs-lookup"><span data-stu-id="d01f4-170">EDIFACT</span></span><br /><br /> <span data-ttu-id="d01f4-171">所有 （默认值）</span><span class="sxs-lookup"><span data-stu-id="d01f4-171">All (default)</span></span>|<span data-ttu-id="d01f4-172">是</span><span class="sxs-lookup"><span data-stu-id="d01f4-172">No</span></span>|  
  
