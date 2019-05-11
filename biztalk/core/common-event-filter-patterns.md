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
ms.openlocfilehash: 05a81dcac4e7bd43a0a60e042d285c56a9fcc35c
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65357133"
---
# <a name="common-event-filter-patterns"></a><span data-ttu-id="cef98-102">常用事件筛选模式</span><span class="sxs-lookup"><span data-stu-id="cef98-102">Common Event Filter Patterns</span></span>
<span data-ttu-id="cef98-103">使用 BAM 侦听器用于 Windows Workflow Foundation (WF) 工作时，你将很可能会有一组常用筛选模式，您将使用经常在侦听器配置文件中。</span><span class="sxs-lookup"><span data-stu-id="cef98-103">As you work with the BAM Interceptor for Windows Workflow Foundation (WF), you will likely notice that there are a set of common filter patterns that you will use frequently in your interceptor configuration files.</span></span> <span data-ttu-id="cef98-104">某些筛选模式将是唯一的应用程序和环境，而许多模式可用于跨环境和在不同的应用程序。</span><span class="sxs-lookup"><span data-stu-id="cef98-104">While some of these filter patterns will be unique to your applications and environments, many patterns can be used across environments and in diverse applications.</span></span>  
  
 <span data-ttu-id="cef98-105">本主题收集了许多针对 WF 应用程序编写的侦听器配置文件所使用的常用筛选模式。</span><span class="sxs-lookup"><span data-stu-id="cef98-105">This topic collects many of the common filter patterns used by interceptor configuration files written for WF applications.</span></span> <span data-ttu-id="cef98-106">Windows Workflow Foundation 跟踪事件进行分组模式：</span><span class="sxs-lookup"><span data-stu-id="cef98-106">Patterns are grouped by Windows Workflow Foundation tracking event:</span></span>  
  
- <span data-ttu-id="cef98-107">活动状态事件</span><span class="sxs-lookup"><span data-stu-id="cef98-107">Activity status events</span></span>  
  
- <span data-ttu-id="cef98-108">工作流状态事件</span><span class="sxs-lookup"><span data-stu-id="cef98-108">Workflow status events</span></span>  
  
- <span data-ttu-id="cef98-109">用户事件</span><span class="sxs-lookup"><span data-stu-id="cef98-109">User events</span></span>  
  
  <span data-ttu-id="cef98-110">每个模式可以复制到您的侦听器配置文件并修改使其适合你的应用程序。</span><span class="sxs-lookup"><span data-stu-id="cef98-110">Each pattern can be copied into your interceptor configuration file and modified to suit your application.</span></span>  
  
## <a name="activity-status-event-filter-patterns"></a><span data-ttu-id="cef98-111">活动状态事件筛选模式</span><span class="sxs-lookup"><span data-stu-id="cef98-111">Activity Status Event Filter Patterns</span></span>  
 <span data-ttu-id="cef98-112">活动是工作流的基本构建基块。</span><span class="sxs-lookup"><span data-stu-id="cef98-112">Activities are the fundamental building blocks of workflows.</span></span> <span data-ttu-id="cef98-113">工作流是一组在树结构中按层次结构组织的活动。</span><span class="sxs-lookup"><span data-stu-id="cef98-113">A workflow is a set of activities that are organized hierarchically in a tree structure.</span></span> <span data-ttu-id="cef98-114">活动表示在工作流中的操作。</span><span class="sxs-lookup"><span data-stu-id="cef98-114">An activity represents an action in a workflow.</span></span> <span data-ttu-id="cef98-115">它可以是一个简单的操作 （如延迟），也可以是包含多个子活动的复合活动。</span><span class="sxs-lookup"><span data-stu-id="cef98-115">It can be a simple action such as a delay, or it can be a composite activity that consists of several child activities.</span></span>  
  
 <span data-ttu-id="cef98-116">在本部分中的筛选器筛选活动和一个或多个以下的 BAM 侦听器的 WF 自定义操作的用法：</span><span class="sxs-lookup"><span data-stu-id="cef98-116">The filters in this section filter activities and use one or more of the following BAM Interceptor for WF custom operations:</span></span>  
  
-   <span data-ttu-id="cef98-117">GetActivityName</span><span class="sxs-lookup"><span data-stu-id="cef98-117">GetActivityName</span></span>  
  
-   <span data-ttu-id="cef98-118">GetActivityEvent</span><span class="sxs-lookup"><span data-stu-id="cef98-118">GetActivityEvent</span></span>  
  
-   <span data-ttu-id="cef98-119">GetActivityType</span><span class="sxs-lookup"><span data-stu-id="cef98-119">GetActivityType</span></span>  
  
-   <span data-ttu-id="cef98-120">GetActivityProperty</span><span class="sxs-lookup"><span data-stu-id="cef98-120">GetActivityProperty</span></span>  
  
-   <span data-ttu-id="cef98-121">GetWorkflowProperty</span><span class="sxs-lookup"><span data-stu-id="cef98-121">GetWorkflowProperty</span></span>  
  
-   <span data-ttu-id="cef98-122">GetContextProperty</span><span class="sxs-lookup"><span data-stu-id="cef98-122">GetContextProperty</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="cef98-123">如果在筛选器中不使用 GetActivityEvent 操作，你的筛选器将查找仅限于已关闭的活动事件。</span><span class="sxs-lookup"><span data-stu-id="cef98-123">If you do not use the GetActivityEvent operation in your filter, your filter will look for Closed activity events only.</span></span>  
  
### <a name="filter-by-activity-name-closed-activity"></a><span data-ttu-id="cef98-124">按活动名 （已关闭的活动） 筛选</span><span class="sxs-lookup"><span data-stu-id="cef98-124">Filter by Activity Name (Closed Activity)</span></span>  
 <span data-ttu-id="cef98-125">经常需要按活动名筛选关闭的活动事件。</span><span class="sxs-lookup"><span data-stu-id="cef98-125">You will frequently need to filter for closed activity events by activity name.</span></span> <span data-ttu-id="cef98-126">当您需要捕获特定活动，如接收文件或向数据库写入数据的数据时，这很有用。</span><span class="sxs-lookup"><span data-stu-id="cef98-126">This is useful when you need to capture data from a specific activity such as receiving a file or writing data to a database.</span></span>  
  
 <span data-ttu-id="cef98-127">下面的筛选器已关闭的活动的片断将名为"MyActivity"。</span><span class="sxs-lookup"><span data-stu-id="cef98-127">The fragment below filters for a closed activity named "MyActivity".</span></span>  
  
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
  
### <a name="filter-by-activity-type-closed-activity-event"></a><span data-ttu-id="cef98-128">按活动类型 （已关闭的活动事件） 进行筛选</span><span class="sxs-lookup"><span data-stu-id="cef98-128">Filter by Activity Type (Closed Activity Event)</span></span>  
 <span data-ttu-id="cef98-129">将您想要筛选的活动类型而不是名称。</span><span class="sxs-lookup"><span data-stu-id="cef98-129">There will be times when you want to filter an activity by type rather than name.</span></span> <span data-ttu-id="cef98-130">例如，你可能想要将活动名称和所有活动的日期/时间戳保存在工作流中。</span><span class="sxs-lookup"><span data-stu-id="cef98-130">For example, you may want to save activity name and a date/time stamp for all activities in a workflow.</span></span> <span data-ttu-id="cef98-131">若要完成此操作，请使用`GetActivityType`操作。</span><span class="sxs-lookup"><span data-stu-id="cef98-131">To accomplish this, you use the `GetActivityType` operation.</span></span> <span data-ttu-id="cef98-132">`GetActivityType` 比较提供的类型与基类型和所有派生的类型来确定匹配。</span><span class="sxs-lookup"><span data-stu-id="cef98-132">`GetActivityType` compares a supplied type against the base type and all derived types to determine a match.</span></span> <span data-ttu-id="cef98-133">比较`System.Workflow.ComponentModel.Activity`将匹配，因为必须从其派生所有工作流活动。</span><span class="sxs-lookup"><span data-stu-id="cef98-133">Comparing against `System.Workflow.ComponentModel.Activity` will match since all workflow activities must derive from it.</span></span>  
  
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
  
### <a name="filter-by-activity-event-any-activity-type"></a><span data-ttu-id="cef98-134">按活动事件 （任意活动类型） 进行筛选</span><span class="sxs-lookup"><span data-stu-id="cef98-134">Filter by Activity Event (Any Activity Type)</span></span>  
 <span data-ttu-id="cef98-135">此筛选器使用 GetActivityEvent 操作查找关闭的活动。</span><span class="sxs-lookup"><span data-stu-id="cef98-135">This filter uses the GetActivityEvent operation to find closed activities.</span></span> <span data-ttu-id="cef98-136">它可用于捕获 （而不是按名称或类型的特定事件） 的所有已关闭事件的相关信息。</span><span class="sxs-lookup"><span data-stu-id="cef98-136">It is useful for capturing information about all closed events (versus a specific event by name or type).</span></span>  
  
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
  
### <a name="filter-by-activity-name-and-type-closed-activity-event"></a><span data-ttu-id="cef98-137">按活动名筛选，并键入 （已关闭的活动事件）</span><span class="sxs-lookup"><span data-stu-id="cef98-137">Filter by Activity Name and Type (Closed Activity Event)</span></span>  
 <span data-ttu-id="cef98-138">您可以选择要筛选活动按活动名和活动类型，如果你想要指定您是想要查找的活动 （包括处理器体系结构） 的确切类型。</span><span class="sxs-lookup"><span data-stu-id="cef98-138">You may choose to filter activities by activity name and activity type if you want to specify the exact type of activity (including processor architecture) that you are interested in finding.</span></span> <span data-ttu-id="cef98-139">下面的示例将查找"MyActivity"派生自`System.Workflow.ComponentModel.Activity`; 你可以更改为派生类型以使其更具限制性。</span><span class="sxs-lookup"><span data-stu-id="cef98-139">The sample below looks for "MyActivity" deriving from `System.Workflow.ComponentModel.Activity`; you can change this to a derived type to make it more restrictive.</span></span>  
  
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
  
### <a name="filter-by-activity-name-and-event-any-activity-type"></a><span data-ttu-id="cef98-140">按活动名和事件 （任意活动类型） 筛选</span><span class="sxs-lookup"><span data-stu-id="cef98-140">Filter by Activity Name and Event (Any Activity Type)</span></span>  
 <span data-ttu-id="cef98-141">此表达式筛选器基于活动名和活动事件。</span><span class="sxs-lookup"><span data-stu-id="cef98-141">This expression filters based on activity name and activity event.</span></span> <span data-ttu-id="cef98-142">如果想要捕获特定活动和事件的信息或捕获多个给定活动的活动事件中的数据时，这非常有用。</span><span class="sxs-lookup"><span data-stu-id="cef98-142">This is useful when you want to capture information for a specific activity and event or when capturing data from more than one activity event for a given activity.</span></span> <span data-ttu-id="cef98-143">例如，你可能想两个不同的 OnEvent 元素，一个用于 MyActivity 时正在执行另一个用于时关闭，如下所示。</span><span class="sxs-lookup"><span data-stu-id="cef98-143">For example, you may want two different OnEvent elements, one for MyActivity when it is Executing and one for when it is Closed as shown below.</span></span>  
  
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
  
### <a name="filter-by-activity-type-and-event"></a><span data-ttu-id="cef98-144">按活动类型和事件筛选</span><span class="sxs-lookup"><span data-stu-id="cef98-144">Filter by Activity Type and Event</span></span>  
 <span data-ttu-id="cef98-145">此筛选器可用于捕获有关单个活动事件期间从特定类型派生的所有活动的信息。</span><span class="sxs-lookup"><span data-stu-id="cef98-145">This filter is useful for capturing information about all activities that derive from a specific type during a single activity event.</span></span> <span data-ttu-id="cef98-146">例如，您可以根据兴趣参阅跟踪采购订单 ID 和日期/时间戳从采购订单通过工作流中流动。</span><span class="sxs-lookup"><span data-stu-id="cef98-146">For example, you may be interested in tracking a purchase order ID and date/time stamp from a purchase order as it flows through a workflow.</span></span> <span data-ttu-id="cef98-147">若要完成此操作，请使用`GetActivityEvent`和`GetActivityType`操作。</span><span class="sxs-lookup"><span data-stu-id="cef98-147">To accomplish this, you use the `GetActivityEvent` and the `GetActivityType` operations.</span></span> <span data-ttu-id="cef98-148">`GetActivityType` 比较提供的类型与基类型和所有派生的类型来确定匹配。</span><span class="sxs-lookup"><span data-stu-id="cef98-148">`GetActivityType` compares a supplied type against the base type and all derived types to determine a match.</span></span> <span data-ttu-id="cef98-149">比较`System.Workflow.ComponentModel.Activity`将匹配，因为必须从其派生所有工作流活动。</span><span class="sxs-lookup"><span data-stu-id="cef98-149">Comparing against `System.Workflow.ComponentModel.Activity` will match since all workflow activities must derive from it.</span></span>  
  
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
  
### <a name="filter-by-activity-name-type-and-event"></a><span data-ttu-id="cef98-150">按活动名、 类型和事件筛选</span><span class="sxs-lookup"><span data-stu-id="cef98-150">Filter by Activity Name, Type, and Event</span></span>  
 <span data-ttu-id="cef98-151">按名称筛选活动，类型和事件可在你想要更好地限定您感兴趣跟踪的活动。</span><span class="sxs-lookup"><span data-stu-id="cef98-151">Filtering an activity by name, type and event can be useful when you want to better qualify the activity you are interested in tracking.</span></span> <span data-ttu-id="cef98-152">例如，下面的筛选器查找已关闭的活动具有等于或派生的类型的"MyActivity" `System.Workflow.ComponentModel.Activity`。</span><span class="sxs-lookup"><span data-stu-id="cef98-152">For example, the filter below looks for the closed activity "MyActivity" that has a type that is equal to or derives from `System.Workflow.ComponentModel.Activity`.</span></span>  
  
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
  
## <a name="workflow-status-event-filter-patterns"></a><span data-ttu-id="cef98-153">工作流状态事件筛选模式</span><span class="sxs-lookup"><span data-stu-id="cef98-153">Workflow Status Event Filter Patterns</span></span>  
 <span data-ttu-id="cef98-154">在本部分中的筛选器筛选工作流事件并使用一个或多个以下的 BAM 侦听器的 WF 自定义操作：</span><span class="sxs-lookup"><span data-stu-id="cef98-154">The filters in this section filter workflow events and use one or more of the following BAM Interceptor for WF custom operations:</span></span>  
  
-   <span data-ttu-id="cef98-155">GetWorkflowEvent</span><span class="sxs-lookup"><span data-stu-id="cef98-155">GetWorkflowEvent</span></span>  
  
-   <span data-ttu-id="cef98-156">GetContextProperty</span><span class="sxs-lookup"><span data-stu-id="cef98-156">GetContextProperty</span></span>  
  
### <a name="filter-by-workflow-event"></a><span data-ttu-id="cef98-157">按工作流事件筛选</span><span class="sxs-lookup"><span data-stu-id="cef98-157">Filter by Workflow Event</span></span>  
 <span data-ttu-id="cef98-158">此表达式将筛选由工作流事件。</span><span class="sxs-lookup"><span data-stu-id="cef98-158">This expression filters by workflow event.</span></span>  
  
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
  
## <a name="user-event-filter-patterns"></a><span data-ttu-id="cef98-159">用户事件筛选模式</span><span class="sxs-lookup"><span data-stu-id="cef98-159">User Event Filter Patterns</span></span>  
 <span data-ttu-id="cef98-160">如果你的应用程序跟踪使用 TrackData 方法的自定义信息，您可以筛选使用一个或多个以下的 BAM 侦听器的 WF 自定义用户数据操作的数据的特征：</span><span class="sxs-lookup"><span data-stu-id="cef98-160">If your application tracks custom information using the TrackData method, you can filter based on the characteristics of the data using one or more of the following BAM Interceptor for WF custom user data operations:</span></span>  
  
- <span data-ttu-id="cef98-161">GetUserDataType</span><span class="sxs-lookup"><span data-stu-id="cef98-161">GetUserDataType</span></span>  
  
- <span data-ttu-id="cef98-162">GetUserKey</span><span class="sxs-lookup"><span data-stu-id="cef98-162">GetUserKey</span></span>  
  
- <span data-ttu-id="cef98-163">GetUserData</span><span class="sxs-lookup"><span data-stu-id="cef98-163">GetUserData</span></span>  
  
  <span data-ttu-id="cef98-164">筛选器可以组合这些操作与以下内容，以创建更复杂的表达式：</span><span class="sxs-lookup"><span data-stu-id="cef98-164">The filter can combine these operations with the following to create a more complex expression:</span></span>  
  
- <span data-ttu-id="cef98-165">GetActivityName</span><span class="sxs-lookup"><span data-stu-id="cef98-165">GetActivityName</span></span>  
  
- <span data-ttu-id="cef98-166">GetActivityType</span><span class="sxs-lookup"><span data-stu-id="cef98-166">GetActivityType</span></span>  
  
- <span data-ttu-id="cef98-167">GetActivityProperty</span><span class="sxs-lookup"><span data-stu-id="cef98-167">GetActivityProperty</span></span>  
  
- <span data-ttu-id="cef98-168">GetWorkflowProperty</span><span class="sxs-lookup"><span data-stu-id="cef98-168">GetWorkflowProperty</span></span>  
  
- <span data-ttu-id="cef98-169">GetContextProperty</span><span class="sxs-lookup"><span data-stu-id="cef98-169">GetContextProperty</span></span>  
  
  <span data-ttu-id="cef98-170">如果你的筛选器不包括至少一个用户数据操作，你的筛选器不会用户事件筛选器并且封闭的 OnEvent 将导致错误 （如果用户操作出现在相应的更新表达式中） 或将被标识为活动跟踪点而不是用户跟踪点。</span><span class="sxs-lookup"><span data-stu-id="cef98-170">If your filter does not include at least one user data operation, your filter will not be a user event filter and the enclosing OnEvent will cause an error (if a user operation appears in a corresponding update expression) or will be identified as an activity track point and not a user track point.</span></span>  
  
### <a name="filter-by-activity-name-and-user-data-type"></a><span data-ttu-id="cef98-171">按活动名和用户数据类型筛选</span><span class="sxs-lookup"><span data-stu-id="cef98-171">Filter by Activity Name and User Data Type</span></span>  
 <span data-ttu-id="cef98-172">经常可以确定按活动名和用户数据类型的事件。</span><span class="sxs-lookup"><span data-stu-id="cef98-172">Frequently you can identify an event by activity name and user data type.</span></span> <span data-ttu-id="cef98-173">以下表达式筛选器的名为"MyActivity"和用户数据类型派生的活动`System.Object`。</span><span class="sxs-lookup"><span data-stu-id="cef98-173">The following expression filters for an activity named "MyActivity" and a user data type that derives from `System.Object`.</span></span>  
  
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
  
### <a name="filter-by-activity-type-and-user-data-type"></a><span data-ttu-id="cef98-174">按活动类型和用户数据类型进行筛选</span><span class="sxs-lookup"><span data-stu-id="cef98-174">Filter by Activity Type and User Data Type</span></span>  
 <span data-ttu-id="cef98-175">您可以筛选基于活动类型和用户数据类型。</span><span class="sxs-lookup"><span data-stu-id="cef98-175">You can filter based on activity type and user data type.</span></span> <span data-ttu-id="cef98-176">这将授予你筛选事件纬度根据类型从其派生因为两者`GetActivityType`和`GetUserDataType`与指定的类型及所有派生的类型的比较。</span><span class="sxs-lookup"><span data-stu-id="cef98-176">This grants you the latitude to filter events based on the type the derive from because both `GetActivityType` and `GetUserDataType` compare against the type specified and all derived types.</span></span>  
  
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
  
### <a name="filter-by-activity-name-activity-type-and-user-data-type"></a><span data-ttu-id="cef98-177">按活动名、 活动类型和用户数据类型筛选</span><span class="sxs-lookup"><span data-stu-id="cef98-177">Filter by Activity Name, Activity Type, and User Data Type</span></span>  
 <span data-ttu-id="cef98-178">此筛选器进一步通过包含活动名来限制活动类型和用户数据类型筛选器模式。</span><span class="sxs-lookup"><span data-stu-id="cef98-178">This filter further restricts the activity type and user data type filter pattern by including activity name.</span></span>  
  
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
  
### <a name="filter-by-activity-name-and-user-key"></a><span data-ttu-id="cef98-179">按活动名和用户密钥筛选</span><span class="sxs-lookup"><span data-stu-id="cef98-179">Filter by Activity Name and User Key</span></span>  
 <span data-ttu-id="cef98-180">如果你的应用程序具有调用的活动`TrackData`与在运行时确定的密钥，你可能希望按活动名和用户密钥筛选。</span><span class="sxs-lookup"><span data-stu-id="cef98-180">If your application has an activity that calls `TrackData` with a key determined at run time, you may want to filter by activity name and user key.</span></span> <span data-ttu-id="cef98-181">这样，便可触发`OnEvent`基于特定密钥值。</span><span class="sxs-lookup"><span data-stu-id="cef98-181">This will enable you to trigger an `OnEvent` based on a specific key value.</span></span> <span data-ttu-id="cef98-182">例如，你的应用程序可能会定义多个键，并动态选择一个活动中。</span><span class="sxs-lookup"><span data-stu-id="cef98-182">For example, your application might define multiple keys and dynamically select one within an activity.</span></span>  
  
 <span data-ttu-id="cef98-183">下面的筛选器的表达式将为"MyActivity"包含用户键名为"ItemKey"。</span><span class="sxs-lookup"><span data-stu-id="cef98-183">The expression below filters for "MyActivity" containing a user key named "ItemKey".</span></span>  
  
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
  
### <a name="filter-by-activity-type-and-user-key"></a><span data-ttu-id="cef98-184">按活动类型和用户密钥筛选</span><span class="sxs-lookup"><span data-stu-id="cef98-184">Filter by Activity Type and User Key</span></span>  
 <span data-ttu-id="cef98-185">如果你的应用程序包含多个活动可调用`TrackData`与在运行时确定的密钥，你可能希望按活动名和用户密钥筛选。</span><span class="sxs-lookup"><span data-stu-id="cef98-185">If your application contain multiple activities that call `TrackData` with a key determined at run time, you may want to filter by activity name and user key.</span></span> <span data-ttu-id="cef98-186">这样，便可触发`OnEvent`基于特定密钥值。</span><span class="sxs-lookup"><span data-stu-id="cef98-186">This will enable you to trigger an `OnEvent` based on a specific key value.</span></span> <span data-ttu-id="cef98-187">例如，你的应用程序可能会定义多个键，并动态选择一个活动中。</span><span class="sxs-lookup"><span data-stu-id="cef98-187">For example, your application might define multiple keys and dynamically select one within an activity.</span></span>  
  
 <span data-ttu-id="cef98-188">下面从派生的任意活动的筛选器的表达式将`System.Workflow.ComponentModel.Activity`包含用户键名为"ItemKey"。</span><span class="sxs-lookup"><span data-stu-id="cef98-188">The expression below filters for any activity deriving from `System.Workflow.ComponentModel.Activity` containing a user key named "ItemKey".</span></span>  
  
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
  
### <a name="filter-by-activity-name-activity-type-and-user-key"></a><span data-ttu-id="cef98-189">按活动名、 活动类型和用户密钥筛选</span><span class="sxs-lookup"><span data-stu-id="cef98-189">Filter by Activity Name, Activity Type, and User Key</span></span>  
 <span data-ttu-id="cef98-190">此筛选器模式进一步改进活动类型和用户密钥筛选模式通过将活动名称包含在筛选器中。</span><span class="sxs-lookup"><span data-stu-id="cef98-190">This filter pattern further refines the activity type and user key filter pattern by including the activity name in the filter.</span></span>  
  
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
  
### <a name="filter-by-activity-name-user-data-type-and-user-key"></a><span data-ttu-id="cef98-191">按活动名、 用户数据类型和用户密钥筛选</span><span class="sxs-lookup"><span data-stu-id="cef98-191">Filter by Activity Name, User Data Type, and User Key</span></span>  
 <span data-ttu-id="cef98-192">此筛选器是你想要使用特定用户密钥的指定活动限制你的筛选器时很有用并从特定的数据类型派生。</span><span class="sxs-lookup"><span data-stu-id="cef98-192">This filter is useful when you want to restrict your filter to a named activity with a specific user key and deriving from a specific data type.</span></span> <span data-ttu-id="cef98-193">例如，您的活动可以调用 TrackData 使用密钥"Item"和字符串或整数取决于项类型的数据值。</span><span class="sxs-lookup"><span data-stu-id="cef98-193">For example, your activity may call TrackData using the key "Item" and a data value of string or integer depending upon the item type.</span></span>  
  
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
  
### <a name="filter-by-activity-type-user-data-type-and-user-key"></a><span data-ttu-id="cef98-194">按活动类型、 用户数据类型和用户密钥筛选</span><span class="sxs-lookup"><span data-stu-id="cef98-194">Filter by Activity Type, User Data Type, and User Key</span></span>  
 <span data-ttu-id="cef98-195">此筛选器会非常有用，当你想要将活动类型筛选器限制包含特定用户密钥并从特定的数据类型派生。</span><span class="sxs-lookup"><span data-stu-id="cef98-195">This filter is useful when you want to restrict your filter to an activity type with a specific user key and deriving from a specific data type.</span></span> <span data-ttu-id="cef98-196">它可以是限制性更强或较弱限制性比使用活动名、 用户数据类型和用户密钥基于所使用的类型。</span><span class="sxs-lookup"><span data-stu-id="cef98-196">It can be more restrictive or less restrictive than using activity name, user data type, and user key based on the type used.</span></span> <span data-ttu-id="cef98-197">如果指定的派生程度最高的类型，则可能是限制性更强;如果指定根基本类型，则可能是限制性较弱。</span><span class="sxs-lookup"><span data-stu-id="cef98-197">If you specify the most-derived type, it could be more restrictive; if you specify the root base type, it could be less restrictive.</span></span>  
  
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
  
### <a name="filter-by-activity-name-activity-type-user-data-type-and-user-key"></a><span data-ttu-id="cef98-198">按活动名、 活动类型、 用户数据类型和用户密钥筛选</span><span class="sxs-lookup"><span data-stu-id="cef98-198">Filter by Activity Name, Activity Type, User Data Type, and User Key</span></span>  
 <span data-ttu-id="cef98-199">此筛选器进一步限制活动类型、 用户数据类型和用户密钥模式通过添加活动名。</span><span class="sxs-lookup"><span data-stu-id="cef98-199">This filter further restricts the activity type, user data type, and user key pattern by the addition of activity name.</span></span>  
  
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