---
title: 常用事件筛选模式 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: fc80168b-25bd-4228-b84c-d38bf4e2fe4a
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 4d5e5b7ad34a8b87bebe88e21630b178fb7ee35c
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "37012974"
---
# <a name="common-event-filter-patterns"></a><span data-ttu-id="dc305-102">常用事件筛选模式</span><span class="sxs-lookup"><span data-stu-id="dc305-102">Common Event Filter Patterns</span></span>
<span data-ttu-id="dc305-103">使用用于 Windows Workflow Foundation (WF) 的 BAM 侦听器时，您可能会注意到，在侦听器配置文件中存在一组频繁使用的常用筛选模式。</span><span class="sxs-lookup"><span data-stu-id="dc305-103">As you work with the BAM Interceptor for Windows Workflow Foundation (WF), you will likely notice that there are a set of common filter patterns that you will use frequently in your interceptor configuration files.</span></span> <span data-ttu-id="dc305-104">虽然其中的某些筛选模式对于应用程序和环境而言是唯一的，但许多模式可跨环境和在不同的应用程序中使用。</span><span class="sxs-lookup"><span data-stu-id="dc305-104">While some of these filter patterns will be unique to your applications and environments, many patterns can be used across environments and in diverse applications.</span></span>  
  
 <span data-ttu-id="dc305-105">本主题收集了许多针对 WF 应用程序编写的侦听器配置文件所使用的常用筛选模式。</span><span class="sxs-lookup"><span data-stu-id="dc305-105">This topic collects many of the common filter patterns used by interceptor configuration files written for WF applications.</span></span> <span data-ttu-id="dc305-106">这些模式将按如下 Windows Workflow Foundation 跟踪事件进行分组：</span><span class="sxs-lookup"><span data-stu-id="dc305-106">Patterns are grouped by Windows Workflow Foundation tracking event:</span></span>  
  
- <span data-ttu-id="dc305-107">活动状态事件</span><span class="sxs-lookup"><span data-stu-id="dc305-107">Activity status events</span></span>  
  
- <span data-ttu-id="dc305-108">工作流状态事件</span><span class="sxs-lookup"><span data-stu-id="dc305-108">Workflow status events</span></span>  
  
- <span data-ttu-id="dc305-109">用户事件</span><span class="sxs-lookup"><span data-stu-id="dc305-109">User events</span></span>  
  
  <span data-ttu-id="dc305-110">可以将每种模式复制到侦听器配置文件中并进行修改使其适合您的应用程序。</span><span class="sxs-lookup"><span data-stu-id="dc305-110">Each pattern can be copied into your interceptor configuration file and modified to suit your application.</span></span>  
  
## <a name="activity-status-event-filter-patterns"></a><span data-ttu-id="dc305-111">活动状态事件筛选模式</span><span class="sxs-lookup"><span data-stu-id="dc305-111">Activity Status Event Filter Patterns</span></span>  
 <span data-ttu-id="dc305-112">活动是工作流的基本构造块。</span><span class="sxs-lookup"><span data-stu-id="dc305-112">Activities are the fundamental building blocks of workflows.</span></span> <span data-ttu-id="dc305-113">工作流是树结构中按层次结构组织的一组活动。</span><span class="sxs-lookup"><span data-stu-id="dc305-113">A workflow is a set of activities that are organized hierarchically in a tree structure.</span></span> <span data-ttu-id="dc305-114">一个活动代表工作流中的一个操作。</span><span class="sxs-lookup"><span data-stu-id="dc305-114">An activity represents an action in a workflow.</span></span> <span data-ttu-id="dc305-115">它可以是一个简单操作（如延迟），也可以是一个包含多个子活动的复合活动。</span><span class="sxs-lookup"><span data-stu-id="dc305-115">It can be a simple action such as a delay, or it can be a composite activity that consists of several child activities.</span></span>  
  
 <span data-ttu-id="dc305-116">本部分中的筛选器将使用以下一个或多个针对 WF 的 BAM 侦听器的自定义操作对活动进行筛选：</span><span class="sxs-lookup"><span data-stu-id="dc305-116">The filters in this section filter activities and use one or more of the following BAM Interceptor for WF custom operations:</span></span>  
  
-   <span data-ttu-id="dc305-117">GetActivityName</span><span class="sxs-lookup"><span data-stu-id="dc305-117">GetActivityName</span></span>  
  
-   <span data-ttu-id="dc305-118">GetActivityEvent</span><span class="sxs-lookup"><span data-stu-id="dc305-118">GetActivityEvent</span></span>  
  
-   <span data-ttu-id="dc305-119">GetActivityType</span><span class="sxs-lookup"><span data-stu-id="dc305-119">GetActivityType</span></span>  
  
-   <span data-ttu-id="dc305-120">GetActivityProperty</span><span class="sxs-lookup"><span data-stu-id="dc305-120">GetActivityProperty</span></span>  
  
-   <span data-ttu-id="dc305-121">GetWorkflowProperty</span><span class="sxs-lookup"><span data-stu-id="dc305-121">GetWorkflowProperty</span></span>  
  
-   <span data-ttu-id="dc305-122">GetContextProperty</span><span class="sxs-lookup"><span data-stu-id="dc305-122">GetContextProperty</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="dc305-123">如果在筛选器中不使用 GetActivityEvent 操作，则筛选器将仅查找“已关闭”的活动事件。</span><span class="sxs-lookup"><span data-stu-id="dc305-123">If you do not use the GetActivityEvent operation in your filter, your filter will look for Closed activity events only.</span></span>  
  
### <a name="filter-by-activity-name-closed-activity"></a><span data-ttu-id="dc305-124">按活动名筛选（关闭的活动）</span><span class="sxs-lookup"><span data-stu-id="dc305-124">Filter by Activity Name (Closed Activity)</span></span>  
 <span data-ttu-id="dc305-125">您将经常需要按活动名筛选关闭的活动事件。</span><span class="sxs-lookup"><span data-stu-id="dc305-125">You will frequently need to filter for closed activity events by activity name.</span></span> <span data-ttu-id="dc305-126">当您需要捕获特定活动（如接收文件或将数据写入数据库）中的数据时，此筛选器将非常有用。</span><span class="sxs-lookup"><span data-stu-id="dc305-126">This is useful when you need to capture data from a specific activity such as receiving a file or writing data to a database.</span></span>  
  
 <span data-ttu-id="dc305-127">下面的片断将筛选名为“MyActivity”的关闭活动。</span><span class="sxs-lookup"><span data-stu-id="dc305-127">The fragment below filters for a closed activity named "MyActivity".</span></span>  
  
```  
<ic:Filter>  
  <ic:Expression>  
    <wf:Operation Name="GetActivityName" />  
    <ic:Operation Name="Constant">  
      <ic:Argument>MyActivity</ic:Argument>  
    </ic:Operation>  
    <ic:Operation Name="Equals" />  
  </ic:Expression>  
</ic:Filter>  
```  
  
### <a name="filter-by-activity-type-closed-activity-event"></a><span data-ttu-id="dc305-128">按活动类型筛选（关闭的活动事件）</span><span class="sxs-lookup"><span data-stu-id="dc305-128">Filter by Activity Type (Closed Activity Event)</span></span>  
 <span data-ttu-id="dc305-129">有时，您可能希望按类型而不是按名称筛选活动。</span><span class="sxs-lookup"><span data-stu-id="dc305-129">There will be times when you want to filter an activity by type rather than name.</span></span> <span data-ttu-id="dc305-130">例如，您可能希望将所有活动的活动名和日期/时间戳都保存在工作流中。</span><span class="sxs-lookup"><span data-stu-id="dc305-130">For example, you may want to save activity name and a date/time stamp for all activities in a workflow.</span></span> <span data-ttu-id="dc305-131">若要完成此操作，请使用`GetActivityType`操作。</span><span class="sxs-lookup"><span data-stu-id="dc305-131">To accomplish this, you use the `GetActivityType` operation.</span></span> <span data-ttu-id="dc305-132">`GetActivityType` 比较提供的类型与基类型和所有派生的类型来确定匹配。</span><span class="sxs-lookup"><span data-stu-id="dc305-132">`GetActivityType` compares a supplied type against the base type and all derived types to determine a match.</span></span> <span data-ttu-id="dc305-133">比较`System.Workflow.ComponentModel.Activity`将匹配，因为必须从其派生所有工作流活动。</span><span class="sxs-lookup"><span data-stu-id="dc305-133">Comparing against `System.Workflow.ComponentModel.Activity` will match since all workflow activities must derive from it.</span></span>  
  
```  
<ic:Filter>  
  <ic:Expression>  
    <wf:Operation Name="GetActivityType" />  
    <ic:Operation Name="Constant">  
      <ic:Argument>System.Workflow.ComponentModel.Activity, System.Workflow.ComponentModel, Version=3.0.0.0, Culture=neutral, PublicKeyToken=31bf3856ad364e35, processorArchitecture=MSIL</ic:Argument>  
    </ic:Operation>  
    <ic:Operation Name="Equals" />  
  </ic:Expression>  
</ic:Filter>  
```  
  
### <a name="filter-by-activity-event-any-activity-type"></a><span data-ttu-id="dc305-134">按活动事件筛选（任意活动类型）</span><span class="sxs-lookup"><span data-stu-id="dc305-134">Filter by Activity Event (Any Activity Type)</span></span>  
 <span data-ttu-id="dc305-135">此筛选器使用 GetActivityEvent 操作查找关闭的活动。</span><span class="sxs-lookup"><span data-stu-id="dc305-135">This filter uses the GetActivityEvent operation to find closed activities.</span></span> <span data-ttu-id="dc305-136">捕获有关所有关闭事件的信息时，此筛选器将非常有用（与按名称或类型的特定事件相比较而言）。</span><span class="sxs-lookup"><span data-stu-id="dc305-136">It is useful for capturing information about all closed events (versus a specific event by name or type).</span></span>  
  
```  
<ic:Filter>  
  <ic:Expression>  
    <wf:Operation Name="GetActivityEvent" />  
    <ic:Operation Name="Constant">  
      <ic:Argument>Closed</ic:Argument>  
    </ic:Operation>  
    <ic:Operation Name="Equals" />  
  </ic:Expression>  
</ic:Filter>  
```  
  
### <a name="filter-by-activity-name-and-type-closed-activity-event"></a><span data-ttu-id="dc305-137">按活动名和类型筛选（关闭的活动事件）</span><span class="sxs-lookup"><span data-stu-id="dc305-137">Filter by Activity Name and Type (Closed Activity Event)</span></span>  
 <span data-ttu-id="dc305-138">如果要指定想要查找的活动的精确类型（其中包括处理器结构），可以选择按活动名和活动类型筛选活动。</span><span class="sxs-lookup"><span data-stu-id="dc305-138">You may choose to filter activities by activity name and activity type if you want to specify the exact type of activity (including processor architecture) that you are interested in finding.</span></span> <span data-ttu-id="dc305-139">下面的示例将查找从 `System.Workflow.ComponentModel.Activity` 派生的“MyActivity”；可以将此活动更改为派生类型以进一步限制查找范围。</span><span class="sxs-lookup"><span data-stu-id="dc305-139">The sample below looks for "MyActivity" deriving from `System.Workflow.ComponentModel.Activity`; you can change this to a derived type to make it more restrictive.</span></span>  
  
```  
<ic:Filter>  
  <ic:Expression>  
    <wf:Operation Name="GetActivityName" />  
    <ic:Operation Name="Constant">  
      <ic:Argument>MyActivity</ic:Argument>  
    </ic:Operation>  
    <ic:Operation Name="Equals" />  
    <wf:Operation Name="GetActivityType" />  
    <ic:Operation Name="Constant">  
      <ic:Argument>System.Workflow.ComponentModel.Activity, System.Workflow.ComponentModel, Version=3.0.0.0, Culture=neutral, PublicKeyToken=31bf3856ad364e35, processorArchitecture=MSIL</ic:Argument>  
    </ic:Operation>  
    <ic:Operation Name="Equals" />  
<ic:Operation Name="And" />  
  </ic:Expression>  
</ic:Filter>  
```  
  
### <a name="filter-by-activity-name-and-event-any-activity-type"></a><span data-ttu-id="dc305-140">按活动名和事件筛选（任意活动类型）</span><span class="sxs-lookup"><span data-stu-id="dc305-140">Filter by Activity Name and Event (Any Activity Type)</span></span>  
 <span data-ttu-id="dc305-141">此表达式将基于活动名和活动事件进行筛选。</span><span class="sxs-lookup"><span data-stu-id="dc305-141">This expression filters based on activity name and activity event.</span></span> <span data-ttu-id="dc305-142">当您希望捕获有关特定活动和事件的信息时，或捕获多个活动事件中有关给定活动的数据时，此筛选器将非常有用。</span><span class="sxs-lookup"><span data-stu-id="dc305-142">This is useful when you want to capture information for a specific activity and event or when capturing data from more than one activity event for a given activity.</span></span> <span data-ttu-id="dc305-143">例如，您可能需要两个不同的 OnEvent 元素，一个用于“正在执行”时的 MyActivity，另一个用于“已关闭”时的 MyActivity，如下所示。</span><span class="sxs-lookup"><span data-stu-id="dc305-143">For example, you may want two different OnEvent elements, one for MyActivity when it is Executing and one for when it is Closed as shown below.</span></span>  
  
```  
<ic:Filter>  
  <ic:Expression>  
    <wf:Operation Name="GetActivityName" />  
    <ic:Operation Name="Constant">  
      <ic:Argument>MyActivity</ic:Argument>  
    </ic:Operation>  
    <ic:Operation Name="Equals" />  
    <wf:Operation Name="GetActivityEvent" />  
    <ic:Operation Name="Constant">  
      <ic:Argument>Closed</ic:Argument>  
    </ic:Operation>  
    <ic:Operation Name="Equals" />  
    <ic:Operation Name="And" />  
  </ic:Expression>  
</ic:Filter>  
```  
  
### <a name="filter-by-activity-type-and-event"></a><span data-ttu-id="dc305-144">按活动类型和事件筛选</span><span class="sxs-lookup"><span data-stu-id="dc305-144">Filter by Activity Type and Event</span></span>  
 <span data-ttu-id="dc305-145">当在单个活动事件期间捕获有关从特定类型派生的所有活动的信息时，此筛选器将非常有用。</span><span class="sxs-lookup"><span data-stu-id="dc305-145">This filter is useful for capturing information about all activities that derive from a specific type during a single activity event.</span></span> <span data-ttu-id="dc305-146">例如，当采购订单通过工作流时，您可能希望跟踪采购订单中的采购订单 ID 和日期/时间戳。</span><span class="sxs-lookup"><span data-stu-id="dc305-146">For example, you may be interested in tracking a purchase order ID and date/time stamp from a purchase order as it flows through a workflow.</span></span> <span data-ttu-id="dc305-147">若要完成此操作，请使用`GetActivityEvent`和`GetActivityType`操作。</span><span class="sxs-lookup"><span data-stu-id="dc305-147">To accomplish this, you use the `GetActivityEvent` and the `GetActivityType` operations.</span></span> <span data-ttu-id="dc305-148">`GetActivityType` 比较提供的类型与基类型和所有派生的类型来确定匹配。</span><span class="sxs-lookup"><span data-stu-id="dc305-148">`GetActivityType` compares a supplied type against the base type and all derived types to determine a match.</span></span> <span data-ttu-id="dc305-149">比较`System.Workflow.ComponentModel.Activity`将匹配，因为必须从其派生所有工作流活动。</span><span class="sxs-lookup"><span data-stu-id="dc305-149">Comparing against `System.Workflow.ComponentModel.Activity` will match since all workflow activities must derive from it.</span></span>  
  
```  
<ic:Filter>  
  <ic:Expression>  
    <wf:Operation Name="GetActivityEvent" />  
    <ic:Operation Name="Constant">  
      <ic:Argument>Closed</ic:Argument>  
    </ic:Operation>  
    <ic:Operation Name="Equals" />  
    <wf:Operation Name="GetActivityType" />  
    <ic:Operation Name="Constant">  
      <ic:Argument>System.Workflow.ComponentModel.Activity, System.Workflow.ComponentModel, Version=3.0.0.0, Culture=neutral, PublicKeyToken=31bf3856ad364e35, processorArchitecture=MSIL</ic:Argument>  
    </ic:Operation>  
    <ic:Operation Name="Equals" />  
    <ic:Operation Name="And" />  
  </ic:Expression>  
</ic:Filter>  
```  
  
### <a name="filter-by-activity-name-type-and-event"></a><span data-ttu-id="dc305-150">按活动名、类型和事件筛选</span><span class="sxs-lookup"><span data-stu-id="dc305-150">Filter by Activity Name, Type, and Event</span></span>  
 <span data-ttu-id="dc305-151">当您希望进一步限定想要跟踪的活动时，按名称、类型和事件筛选活动将非常有用。</span><span class="sxs-lookup"><span data-stu-id="dc305-151">Filtering an activity by name, type and event can be useful when you want to better qualify the activity you are interested in tracking.</span></span> <span data-ttu-id="dc305-152">例如，下面的筛选器将查找关闭的活动“MyActivity”，该活动将具有等效于 `System.Workflow.ComponentModel.Activity` 或从其派生的类型。</span><span class="sxs-lookup"><span data-stu-id="dc305-152">For example, the filter below looks for the closed activity "MyActivity" that has a type that is equal to or derives from `System.Workflow.ComponentModel.Activity`.</span></span>  
  
```  
<ic:Filter>  
  <ic:Expression>  
    <wf:Operation Name="GetActivityName" />  
    <ic:Operation Name="Constant">  
      <ic:Argument>MyActivity</ic:Argument>  
    </ic:Operation>  
    <ic:Operation Name="Equals" />  
    <wf:Operation Name="GetActivityEvent" />  
    <ic:Operation Name="Constant">  
      <ic:Argument>Closed</ic:Argument>  
    </ic:Operation>  
    <ic:Operation Name="Equals" />  
    <ic:Operation Name="And" />  
    <wf:Operation Name="GetActivityType" />  
    <ic:Operation Name="Constant">  
      <ic:Argument>System.Workflow.ComponentModel.Activity, System.Workflow.ComponentModel, Version=3.0.0.0, Culture=neutral, PublicKeyToken=31bf3856ad364e35, processorArchitecture=MSIL</ic:Argument>  
    </ic:Operation>  
    <ic:Operation Name="Equals" />  
    <ic:Operation Name="And" />  
  </ic:Expression>  
</ic:Filter>  
```  
  
## <a name="workflow-status-event-filter-patterns"></a><span data-ttu-id="dc305-153">工作流状态事件筛选模式</span><span class="sxs-lookup"><span data-stu-id="dc305-153">Workflow Status Event Filter Patterns</span></span>  
 <span data-ttu-id="dc305-154">本部分中的筛选器将使用以下一个或多个针对 WF 的 BAM 侦听器的自定义操作对工作流事件进行筛选：</span><span class="sxs-lookup"><span data-stu-id="dc305-154">The filters in this section filter workflow events and use one or more of the following BAM Interceptor for WF custom operations:</span></span>  
  
-   <span data-ttu-id="dc305-155">GetWorkflowEvent</span><span class="sxs-lookup"><span data-stu-id="dc305-155">GetWorkflowEvent</span></span>  
  
-   <span data-ttu-id="dc305-156">GetContextProperty</span><span class="sxs-lookup"><span data-stu-id="dc305-156">GetContextProperty</span></span>  
  
### <a name="filter-by-workflow-event"></a><span data-ttu-id="dc305-157">按工作流事件筛选</span><span class="sxs-lookup"><span data-stu-id="dc305-157">Filter by Workflow Event</span></span>  
 <span data-ttu-id="dc305-158">此表达式将按工作流事件进行筛选。</span><span class="sxs-lookup"><span data-stu-id="dc305-158">This expression filters by workflow event.</span></span>  
  
```  
<ic:Filter>  
  <ic:Expression>  
    <wf:Operation Name="GetWorkflowEvent" />  
    <ic:Operation Name="Constant">  
      <ic:Argument>Created</ic:Argument>  
    </ic:Operation>  
    <ic:Operation Name="Equals" />  
  </ic:Expression>  
</ic:Filter>  
```  
  
## <a name="user-event-filter-patterns"></a><span data-ttu-id="dc305-159">用户事件筛选模式</span><span class="sxs-lookup"><span data-stu-id="dc305-159">User Event Filter Patterns</span></span>  
 <span data-ttu-id="dc305-160">如果您的应用程序使用 TrackData 方法跟踪自定义信息，则您可以使用以下一个或多个针对 WF 的 BAM 侦听器的自定义用户数据操作基于数据特性对信息进行筛选：</span><span class="sxs-lookup"><span data-stu-id="dc305-160">If your application tracks custom information using the TrackData method, you can filter based on the characteristics of the data using one or more of the following BAM Interceptor for WF custom user data operations:</span></span>  
  
- <span data-ttu-id="dc305-161">GetUserDataType</span><span class="sxs-lookup"><span data-stu-id="dc305-161">GetUserDataType</span></span>  
  
- <span data-ttu-id="dc305-162">GetUserKey</span><span class="sxs-lookup"><span data-stu-id="dc305-162">GetUserKey</span></span>  
  
- <span data-ttu-id="dc305-163">GetUserData</span><span class="sxs-lookup"><span data-stu-id="dc305-163">GetUserData</span></span>  
  
  <span data-ttu-id="dc305-164">该筛选器可以将上述操作与下列操作组合起来，以创建更为复杂的表达式：</span><span class="sxs-lookup"><span data-stu-id="dc305-164">The filter can combine these operations with the following to create a more complex expression:</span></span>  
  
- <span data-ttu-id="dc305-165">GetActivityName</span><span class="sxs-lookup"><span data-stu-id="dc305-165">GetActivityName</span></span>  
  
- <span data-ttu-id="dc305-166">GetActivityType</span><span class="sxs-lookup"><span data-stu-id="dc305-166">GetActivityType</span></span>  
  
- <span data-ttu-id="dc305-167">GetActivityProperty</span><span class="sxs-lookup"><span data-stu-id="dc305-167">GetActivityProperty</span></span>  
  
- <span data-ttu-id="dc305-168">GetWorkflowProperty</span><span class="sxs-lookup"><span data-stu-id="dc305-168">GetWorkflowProperty</span></span>  
  
- <span data-ttu-id="dc305-169">GetContextProperty</span><span class="sxs-lookup"><span data-stu-id="dc305-169">GetContextProperty</span></span>  
  
  <span data-ttu-id="dc305-170">如果筛选器不包括任何用户数据操作，则该筛选器不是用户事件筛选器，并且封闭的 OnEvent 将导致错误（如果用户操作出现在相应的更新表达式中）或将被标识为活动跟踪点而非用户跟踪点。</span><span class="sxs-lookup"><span data-stu-id="dc305-170">If your filter does not include at least one user data operation, your filter will not be a user event filter and the enclosing OnEvent will cause an error (if a user operation appears in a corresponding update expression) or will be identified as an activity track point and not a user track point.</span></span>  
  
### <a name="filter-by-activity-name-and-user-data-type"></a><span data-ttu-id="dc305-171">按活动名和用户数据类型筛选</span><span class="sxs-lookup"><span data-stu-id="dc305-171">Filter by Activity Name and User Data Type</span></span>  
 <span data-ttu-id="dc305-172">通常，您可以按活动名和用户数据类型标识事件。</span><span class="sxs-lookup"><span data-stu-id="dc305-172">Frequently you can identify an event by activity name and user data type.</span></span> <span data-ttu-id="dc305-173">下面的表达式将筛选名为“MyActivity”的活动和一个从 `System.Object` 派生的用户数据类型。</span><span class="sxs-lookup"><span data-stu-id="dc305-173">The following expression filters for an activity named "MyActivity" and a user data type that derives from `System.Object`.</span></span>  
  
```  
<ic:Filter>  
  <ic:Expression>  
    <wf:Operation Name="GetActivityName" />  
    <ic:Operation Name="Constant">  
      <ic:Argument>MyActivity</ic:Argument>  
    </ic:Operation>  
    <ic:Operation Name="Equals" />  
    <wf:Operation Name="GetUserDataType" />  
    <ic:Operation Name="Constant">  
      <ic:Argument>System.Object</ic:Argument>  
    </ic:Operation>  
    <ic:Operation Name="Equals" />  
    <ic:Operation Name="And" />  
  </ic:Expression>  
</ic:Filter>  
```  
  
### <a name="filter-by-activity-type-and-user-data-type"></a><span data-ttu-id="dc305-174">按活动类型和用户数据类型筛选</span><span class="sxs-lookup"><span data-stu-id="dc305-174">Filter by Activity Type and User Data Type</span></span>  
 <span data-ttu-id="dc305-175">可以基于活动类型和用户数据类型进行筛选。</span><span class="sxs-lookup"><span data-stu-id="dc305-175">You can filter based on activity type and user data type.</span></span> <span data-ttu-id="dc305-176">这将授予你筛选事件纬度根据类型从其派生因为两者`GetActivityType`和`GetUserDataType`与指定的类型及所有派生的类型的比较。</span><span class="sxs-lookup"><span data-stu-id="dc305-176">This grants you the latitude to filter events based on the type the derive from because both `GetActivityType` and `GetUserDataType` compare against the type specified and all derived types.</span></span>  
  
```  
<ic:Filter>  
  <ic:Expression>  
    <wf:Operation Name="GetActivityType" />  
    <ic:Operation Name="Constant">  
      <ic:Argument>System.Workflow.ComponentModel.Activity, System.Workflow.ComponentModel, Version=3.0.0.0, Culture=neutral, PublicKeyToken=31bf3856ad364e35, processorArchitecture=MSIL</ic:Argument>  
    </ic:Operation>  
    <ic:Operation Name="Equals" />  
    <wf:Operation Name="GetUserDataType" />  
    <ic:Operation Name="Constant">  
      <ic:Argument>System.Object</ic:Argument>  
    </ic:Operation>  
    <ic:Operation Name="Equals" />  
    <ic:Operation Name="And" />  
  </ic:Expression>  
</ic:Filter>  
```  
  
### <a name="filter-by-activity-name-activity-type-and-user-data-type"></a><span data-ttu-id="dc305-177">按活动名、活动类型和用户数据类型筛选</span><span class="sxs-lookup"><span data-stu-id="dc305-177">Filter by Activity Name, Activity Type, and User Data Type</span></span>  
 <span data-ttu-id="dc305-178">此筛选器将通过包含活动名来进一步限制活动类型和用户数据类型筛选模式。</span><span class="sxs-lookup"><span data-stu-id="dc305-178">This filter further restricts the activity type and user data type filter pattern by including activity name.</span></span>  
  
```  
<ic:Filter>  
  <ic:Expression>  
    <wf:Operation Name="GetActivityType" />  
    <ic:Operation Name="Constant">  
      <ic:Argument>System.Workflow.ComponentModel.Activity, System.Workflow.ComponentModel, Version=3.0.0.0, Culture=neutral, PublicKeyToken=31bf3856ad364e35, processorArchitecture=MSIL</ic:Argument>  
    </ic:Operation>  
    <ic:Operation Name="Equals" />  
    <wf:Operation Name="GetActivityName" />  
    <ic:Operation Name="Constant">  
      <ic:Argument>MyActivity</ic:Argument>  
    </ic:Operation>  
    <ic:Operation Name="Equals" />  
    <ic:Operation Name="And" />  
    <wf:Operation Name="GetUserDataType" />  
    <ic:Operation Name="Constant">  
      <ic:Argument>System.Object</ic:Argument>  
    </ic:Operation>  
    <ic:Operation Name="Equals" />  
    <ic:Operation Name="And" />  
  </ic:Expression>  
</ic:Filter>  
```  
  
### <a name="filter-by-activity-name-and-user-key"></a><span data-ttu-id="dc305-179">按活动名和用户密钥筛选</span><span class="sxs-lookup"><span data-stu-id="dc305-179">Filter by Activity Name and User Key</span></span>  
 <span data-ttu-id="dc305-180">如果你的应用程序具有调用的活动`TrackData`与在运行时确定的密钥，你可能希望按活动名和用户密钥筛选。</span><span class="sxs-lookup"><span data-stu-id="dc305-180">If your application has an activity that calls `TrackData` with a key determined at run time, you may want to filter by activity name and user key.</span></span> <span data-ttu-id="dc305-181">这样，便可触发`OnEvent`基于特定密钥值。</span><span class="sxs-lookup"><span data-stu-id="dc305-181">This will enable you to trigger an `OnEvent` based on a specific key value.</span></span> <span data-ttu-id="dc305-182">例如，您的应用程序可能定义了多个密钥，并在活动内动态选择一个密钥。</span><span class="sxs-lookup"><span data-stu-id="dc305-182">For example, your application might define multiple keys and dynamically select one within an activity.</span></span>  
  
 <span data-ttu-id="dc305-183">下面的表达式将筛选包含名为“ItemKey”用户密钥的“MyActivity”。</span><span class="sxs-lookup"><span data-stu-id="dc305-183">The expression below filters for "MyActivity" containing a user key named "ItemKey".</span></span>  
  
```  
<ic:Filter>  
  <ic:Expression>  
    <wf:Operation Name="GetActivityName" />  
    <ic:Operation Name="Constant">  
      <ic:Argument>MyActivity</ic:Argument>  
    </ic:Operation>  
    <ic:Operation Name="Equals" />  
    <wf:Operation Name="GetUserKey" />  
    <ic:Operation Name="Constant">  
      <ic:Argument>ItemKey</ic:Argument>  
    </ic:Operation>  
    <ic:Operation Name="Equals" />  
    <ic:Operation Name="And" />  
  </ic:Expression>  
</ic:Filter>  
```  
  
### <a name="filter-by-activity-type-and-user-key"></a><span data-ttu-id="dc305-184">按活动类型和用户密钥筛选</span><span class="sxs-lookup"><span data-stu-id="dc305-184">Filter by Activity Type and User Key</span></span>  
 <span data-ttu-id="dc305-185">如果您的应用程序包含多个使用运行时确定的密钥调用 `TrackData` 的活动，您可能希望按活动名和用户密钥进行筛选。</span><span class="sxs-lookup"><span data-stu-id="dc305-185">If your application contain multiple activities that call `TrackData` with a key determined at run time, you may want to filter by activity name and user key.</span></span> <span data-ttu-id="dc305-186">这样，便可触发`OnEvent`基于特定密钥值。</span><span class="sxs-lookup"><span data-stu-id="dc305-186">This will enable you to trigger an `OnEvent` based on a specific key value.</span></span> <span data-ttu-id="dc305-187">例如，您的应用程序可能定义了多个密钥，并在活动内动态选择一个密钥。</span><span class="sxs-lookup"><span data-stu-id="dc305-187">For example, your application might define multiple keys and dynamically select one within an activity.</span></span>  
  
 <span data-ttu-id="dc305-188">下面的表达式将筛选从包含名为“ItemKey”用户密钥的 `System.Workflow.ComponentModel.Activity` 派生的任意活动。</span><span class="sxs-lookup"><span data-stu-id="dc305-188">The expression below filters for any activity deriving from `System.Workflow.ComponentModel.Activity` containing a user key named "ItemKey".</span></span>  
  
```  
<ic:Filter>  
  <ic:Expression>  
    <wf:Operation Name="GetActivityType" />  
    <ic:Operation Name="Constant">  
      <ic:Argument>System.Workflow.ComponentModel.Activity, System.Workflow.ComponentModel, Version=3.0.0.0, Culture=neutral, PublicKeyToken=31bf3856ad364e35, processorArchitecture=MSIL</ic:Argument>  
    </ic:Operation>  
    <ic:Operation Name="Equals" />  
    <wf:Operation Name="GetUserKey" />  
    <ic:Operation Name="Constant">  
      <ic:Argument>ItemKey</ic:Argument>  
    </ic:Operation>  
    <ic:Operation Name="Equals" />  
    <ic:Operation Name="And" />  
  </ic:Expression>  
</ic:Filter>  
```  
  
### <a name="filter-by-activity-name-activity-type-and-user-key"></a><span data-ttu-id="dc305-189">按活动名、活动类型和用户密钥筛选</span><span class="sxs-lookup"><span data-stu-id="dc305-189">Filter by Activity Name, Activity Type, and User Key</span></span>  
 <span data-ttu-id="dc305-190">此筛选模式将通过在筛选器中包含活动名来进一步限制活动类型和用户密钥筛选模式。</span><span class="sxs-lookup"><span data-stu-id="dc305-190">This filter pattern further refines the activity type and user key filter pattern by including the activity name in the filter.</span></span>  
  
```  
<ic:Filter>  
  <ic:Expression>  
    <wf:Operation Name="GetActivityType" />  
    <ic:Operation Name="Constant">  
      <ic:Argument>System.Workflow.ComponentModel.Activity, System.Workflow.ComponentModel, Version=3.0.0.0, Culture=neutral, PublicKeyToken=31bf3856ad364e35, processorArchitecture=MSIL</ic:Argument>  
    </ic:Operation>  
    <ic:Operation Name="Equals" />  
    <wf:Operation Name="GetActivityName" />  
    <ic:Operation Name="Constant">  
      <ic:Argument>MyActivity</ic:Argument>  
    </ic:Operation>  
    <ic:Operation Name="Equals" />  
    <ic:Operation Name="And" />  
    <wf:Operation Name="GetUserKey" />  
    <ic:Operation Name="Constant">  
      <ic:Argument>key</ic:Argument>  
    </ic:Operation>  
    <ic:Operation Name="Equals" />  
    <ic:Operation Name="And" />  
  </ic:Expression>  
</ic:Filter>  
```  
  
### <a name="filter-by-activity-name-user-data-type-and-user-key"></a><span data-ttu-id="dc305-191">按活动名、用户数据类型和用户密钥筛选</span><span class="sxs-lookup"><span data-stu-id="dc305-191">Filter by Activity Name, User Data Type, and User Key</span></span>  
 <span data-ttu-id="dc305-192">当您希望将筛选器限制为筛选包含特定用户密钥并从特定数据类型派生的指定活动时，此筛选器将非常有用。</span><span class="sxs-lookup"><span data-stu-id="dc305-192">This filter is useful when you want to restrict your filter to a named activity with a specific user key and deriving from a specific data type.</span></span> <span data-ttu-id="dc305-193">例如，您的活动可能使用密钥“Item”和字符串或整数（取决于项类型）的数据值来调用 TrackData。</span><span class="sxs-lookup"><span data-stu-id="dc305-193">For example, your activity may call TrackData using the key "Item" and a data value of string or integer depending upon the item type.</span></span>  
  
```  
<ic:Filter>  
  <ic:Expression>  
    <wf:Operation Name="GetActivityName" />  
    <ic:Operation Name="Constant">  
      <ic:Argument>MyActivity</ic:Argument>  
    </ic:Operation>  
    <ic:Operation Name="Equals" />  
    <wf:Operation Name="GetUserDataType" />  
    <ic:Operation Name="Constant">  
      <ic:Argument>System.Object</ic:Argument>  
    </ic:Operation>  
    <ic:Operation Name="Equals" />  
    <ic:Operation Name="And" />  
    <wf:Operation Name="GetUserKey" />  
    <ic:Operation Name="Constant">  
      <ic:Argument>key</ic:Argument>  
    </ic:Operation>  
    <ic:Operation Name="Equals" />  
    <ic:Operation Name="And" />  
  </ic:Expression>  
</ic:Filter>  
```  
  
### <a name="filter-by-activity-type-user-data-type-and-user-key"></a><span data-ttu-id="dc305-194">按活动类型、用户数据类型和用户密钥筛选</span><span class="sxs-lookup"><span data-stu-id="dc305-194">Filter by Activity Type, User Data Type, and User Key</span></span>  
 <span data-ttu-id="dc305-195">当您希望将筛选器限制为筛选包含特定用户密钥并从特定数据类型派生的活动类型时，此筛选器将非常有用。</span><span class="sxs-lookup"><span data-stu-id="dc305-195">This filter is useful when you want to restrict your filter to an activity type with a specific user key and deriving from a specific data type.</span></span> <span data-ttu-id="dc305-196">相对于使用活动名、用户数据类型和用户密钥的筛选器，此筛选器可以具有较强或较弱限制性（取决于所使用的类型）。</span><span class="sxs-lookup"><span data-stu-id="dc305-196">It can be more restrictive or less restrictive than using activity name, user data type, and user key based on the type used.</span></span> <span data-ttu-id="dc305-197">如果您指定派生程度最高的类型，则此筛选器可以具有较强限制性；如果您指定根基本类型，则此筛选器可以具有较弱限制性。</span><span class="sxs-lookup"><span data-stu-id="dc305-197">If you specify the most-derived type, it could be more restrictive; if you specify the root base type, it could be less restrictive.</span></span>  
  
```  
<ic:Filter>  
  <ic:Expression>  
    <wf:Operation Name="GetActivityType" />  
    <ic:Operation Name="Constant">  
      <ic:Argument>System.Workflow.ComponentModel.Activity, System.Workflow.ComponentModel, Version=3.0.0.0, Culture=neutral, PublicKeyToken=31bf3856ad364e35, processorArchitecture=MSIL</ic:Argument>  
    </ic:Operation>  
    <ic:Operation Name="Equals" />  
    <wf:Operation Name="GetUserDataType" />  
    <ic:Operation Name="Constant">  
      <ic:Argument>System.Object</ic:Argument>  
    </ic:Operation>  
    <ic:Operation Name="Equals" />  
    <ic:Operation Name="And" />  
    <wf:Operation Name="GetUserKey" />  
    <ic:Operation Name="Constant">  
      <ic:Argument>key</ic:Argument>  
    </ic:Operation>  
    <ic:Operation Name="Equals" />  
    <ic:Operation Name="And" />  
  </ic:Expression>  
</ic:Filter>  
```  
  
### <a name="filter-by-activity-name-activity-type-user-data-type-and-user-key"></a><span data-ttu-id="dc305-198">按活动名、活动类型、用户数据类型和用户密钥筛选</span><span class="sxs-lookup"><span data-stu-id="dc305-198">Filter by Activity Name, Activity Type, User Data Type, and User Key</span></span>  
 <span data-ttu-id="dc305-199">此筛选器将通过添加活动名来进一步限制活动类型、用户数据类型和用户密钥筛选模式。</span><span class="sxs-lookup"><span data-stu-id="dc305-199">This filter further restricts the activity type, user data type, and user key pattern by the addition of activity name.</span></span>  
  
```  
<ic:Filter>  
  <ic:Expression>  
    <wf:Operation Name="GetActivityType" />  
    <ic:Operation Name="Constant">  
      <ic:Argument>System.Workflow.ComponentModel.Activity, System.Workflow.ComponentModel, Version=3.0.0.0, Culture=neutral, PublicKeyToken=31bf3856ad364e35, processorArchitecture=MSIL</ic:Argument>  
    </ic:Operation>  
    <ic:Operation Name="Equals" />  
    <wf:Operation Name="GetActivityName" />  
    <ic:Operation Name="Constant">  
      <ic:Argument>MyActivity</ic:Argument>  
    </ic:Operation>  
    <ic:Operation Name="Equals" />  
    <ic:Operation Name="And" />  
    <wf:Operation Name="GetUserDataType" />  
    <ic:Operation Name="Constant">  
      <ic:Argument>System.Object</ic:Argument>  
    </ic:Operation>  
    <ic:Operation Name="Equals" />  
    <ic:Operation Name="And" />  
    <wf:Operation Name="GetUserKey" />  
    <ic:Operation Name="Constant">  
      <ic:Argument>key</ic:Argument>  
    </ic:Operation>  
    <ic:Operation Name="Equals" />  
    <ic:Operation Name="And" />  
  </ic:Expression>  
</ic:Filter>   
```