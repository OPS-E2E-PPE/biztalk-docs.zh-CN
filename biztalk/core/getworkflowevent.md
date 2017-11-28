---
title: "GetWorkflowEvent |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 2534e0b8-26df-4554-b0df-742014deb64d
caps.latest.revision: "10"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: f8dc753bd45452af6ab586a11f216bc65f9539fb
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="getworkflowevent"></a><span data-ttu-id="c77d1-102">GetWorkflowEvent</span><span class="sxs-lookup"><span data-stu-id="c77d1-102">GetWorkflowEvent</span></span>
<span data-ttu-id="c77d1-103">将当前工作流事件的名称推送到堆栈上。</span><span class="sxs-lookup"><span data-stu-id="c77d1-103">Pushes the name of the current workflow event onto the stack.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c77d1-104">语法</span><span class="sxs-lookup"><span data-stu-id="c77d1-104">Syntax</span></span>  
  
```  
  
<wf:Operation Name="GetWorkflowEvent" />  
```  
  
#### <a name="parameters"></a><span data-ttu-id="c77d1-105">Parameters</span><span class="sxs-lookup"><span data-stu-id="c77d1-105">Parameters</span></span>  
 <span data-ttu-id="c77d1-106">无。</span><span class="sxs-lookup"><span data-stu-id="c77d1-106">None.</span></span>  
  
## <a name="pushed-value"></a><span data-ttu-id="c77d1-107">推送的值</span><span class="sxs-lookup"><span data-stu-id="c77d1-107">Pushed Value</span></span>  
 <span data-ttu-id="c77d1-108">包含当前工作流事件的字符串。</span><span class="sxs-lookup"><span data-stu-id="c77d1-108">String containing the current workflow event.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="c77d1-109">注释</span><span class="sxs-lookup"><span data-stu-id="c77d1-109">Remarks</span></span>  
 <span data-ttu-id="c77d1-110">一个工作流实例在执行的过程中可以传递几个状态。</span><span class="sxs-lookup"><span data-stu-id="c77d1-110">A workflow instance can pass through several states during the course of its execution.</span></span> <span data-ttu-id="c77d1-111">例如，工作流实例可能变为空闲状态，也可能处于挂起状态。</span><span class="sxs-lookup"><span data-stu-id="c77d1-111">For example, a workflow instance may become idle, or it may be suspended.</span></span> <span data-ttu-id="c77d1-112">工作流实例每次更改状态时，会向运行时跟踪基础结构发出一个工作流状态事件。</span><span class="sxs-lookup"><span data-stu-id="c77d1-112">Every time the workflow instance changes state, it emits a workflow status event to the runtime tracking infrastructure.</span></span> <span data-ttu-id="c77d1-113">Windows Workflow Foundation BAM 侦听器支持由定义的事件的大多数`System.Workflow.Runtime.Tracking.TrackingWorkflowEvent`枚举下, 表中所示。</span><span class="sxs-lookup"><span data-stu-id="c77d1-113">The Windows Workflow Foundation BAM interceptor supports most of the events defined by the `System.Workflow.Runtime.Tracking.TrackingWorkflowEvent` enumeration, as shown in the following table.</span></span>  
  
|<span data-ttu-id="c77d1-114">活动事件</span><span class="sxs-lookup"><span data-stu-id="c77d1-114">Activity event</span></span>|<span data-ttu-id="c77d1-115">Description</span><span class="sxs-lookup"><span data-stu-id="c77d1-115">Description</span></span>|  
|--------------------|-----------------|  
|<span data-ttu-id="c77d1-116">已更改</span><span class="sxs-lookup"><span data-stu-id="c77d1-116">Changed</span></span>|<span data-ttu-id="c77d1-117">工作流更改已经在工作流实例上发生。</span><span class="sxs-lookup"><span data-stu-id="c77d1-117">A workflow change has occurred on the workflow instance.</span></span>|  
|<span data-ttu-id="c77d1-118">已完成</span><span class="sxs-lookup"><span data-stu-id="c77d1-118">Completed</span></span>|<span data-ttu-id="c77d1-119">工作流实例已完成。</span><span class="sxs-lookup"><span data-stu-id="c77d1-119">The workflow instance has completed.</span></span>|  
|<span data-ttu-id="c77d1-120">创建时间</span><span class="sxs-lookup"><span data-stu-id="c77d1-120">Created</span></span>|<span data-ttu-id="c77d1-121">工作流实例已创建。</span><span class="sxs-lookup"><span data-stu-id="c77d1-121">The workflow instance has been created.</span></span>|  
|<span data-ttu-id="c77d1-122">异常</span><span class="sxs-lookup"><span data-stu-id="c77d1-122">Exception</span></span>|<span data-ttu-id="c77d1-123">已出现未处理的异常。</span><span class="sxs-lookup"><span data-stu-id="c77d1-123">An unhandled exception has occurred.</span></span>|  
|<span data-ttu-id="c77d1-124">Idle</span><span class="sxs-lookup"><span data-stu-id="c77d1-124">Idle</span></span>|<span data-ttu-id="c77d1-125">工作流实例处于空闲状态。</span><span class="sxs-lookup"><span data-stu-id="c77d1-125">The workflow instance is idle.</span></span>|  
|<span data-ttu-id="c77d1-126">Loaded</span><span class="sxs-lookup"><span data-stu-id="c77d1-126">Loaded</span></span>|<span data-ttu-id="c77d1-127">工作流实例已加载到内存中。</span><span class="sxs-lookup"><span data-stu-id="c77d1-127">The workflow instance has been loaded into memory.</span></span>|  
|<span data-ttu-id="c77d1-128">Persisted</span><span class="sxs-lookup"><span data-stu-id="c77d1-128">Persisted</span></span>|<span data-ttu-id="c77d1-129">工作流实例已持久化。</span><span class="sxs-lookup"><span data-stu-id="c77d1-129">The workflow instance has been persisted.</span></span>|  
|<span data-ttu-id="c77d1-130">Resumed</span><span class="sxs-lookup"><span data-stu-id="c77d1-130">Resumed</span></span>|<span data-ttu-id="c77d1-131">以前挂起的工作流实例已恢复运行。</span><span class="sxs-lookup"><span data-stu-id="c77d1-131">A previously suspended workflow instance has resumed running.</span></span>|  
|<span data-ttu-id="c77d1-132">Started</span><span class="sxs-lookup"><span data-stu-id="c77d1-132">Started</span></span>|<span data-ttu-id="c77d1-133">工作流实例已启动。</span><span class="sxs-lookup"><span data-stu-id="c77d1-133">The workflow instance has been started.</span></span>|  
|<span data-ttu-id="c77d1-134">已挂起</span><span class="sxs-lookup"><span data-stu-id="c77d1-134">Suspended</span></span>|<span data-ttu-id="c77d1-135">工作流实例已挂起。</span><span class="sxs-lookup"><span data-stu-id="c77d1-135">The workflow instance has been suspended.</span></span>|  
|<span data-ttu-id="c77d1-136">Terminated</span><span class="sxs-lookup"><span data-stu-id="c77d1-136">Terminated</span></span>|<span data-ttu-id="c77d1-137">工作流实例已终止。</span><span class="sxs-lookup"><span data-stu-id="c77d1-137">The workflow instance has been terminated.</span></span>|  
|<span data-ttu-id="c77d1-138">Unloaded</span><span class="sxs-lookup"><span data-stu-id="c77d1-138">Unloaded</span></span>|<span data-ttu-id="c77d1-139">工作流实例已从内存中卸载。</span><span class="sxs-lookup"><span data-stu-id="c77d1-139">The workflow instance has been unloaded from memory.</span></span>|  
  
> [!NOTE]
>  <span data-ttu-id="c77d1-140">你不能同时使用`GetWorkflowEvent`和`GetActivityEvent`相同 OnEvent 元素中。</span><span class="sxs-lookup"><span data-stu-id="c77d1-140">You cannot use both `GetWorkflowEvent` and `GetActivityEvent` in the same OnEvent element.</span></span>  
  
## <a name="example"></a><span data-ttu-id="c77d1-141">示例</span><span class="sxs-lookup"><span data-stu-id="c77d1-141">Example</span></span>  
 <span data-ttu-id="c77d1-142">下面的示例包含一个配置为在工作流中查找特定活动（“FoodAndDrinksPolicy”）的筛选器。</span><span class="sxs-lookup"><span data-stu-id="c77d1-142">The following sample contains a filter that is configured to find a specific activity—"FoodAndDrinksPolicy"—in a workflow.</span></span> <span data-ttu-id="c77d1-143">在该示例中，一个筛选器配置为在关闭的工作流中查找名称为“FoodAndDrinksPolicy”的活动。</span><span class="sxs-lookup"><span data-stu-id="c77d1-143">In the sample, a filter is configured to find the activity named "FoodAndDrinksPolicy" in a closed workflow.</span></span> <span data-ttu-id="c77d1-144">这是通过将 `GetWorkflowEvent` 返回的值与常量“Created”相比较来完成的。</span><span class="sxs-lookup"><span data-stu-id="c77d1-144">This is done by comparing the value returned by `GetWorkflowEvent` to the constant "Created".</span></span>  
  
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
  
 <span data-ttu-id="c77d1-145">对于跟踪工作流的生存期和检测工作流的异常或其他问题，此操作非常有用。</span><span class="sxs-lookup"><span data-stu-id="c77d1-145">This operation is useful for tracking the lifetime of a workflow and for detecting exceptions or other problems with the workflow.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c77d1-146">另请参阅</span><span class="sxs-lookup"><span data-stu-id="c77d1-146">See Also</span></span>  
 [<span data-ttu-id="c77d1-147">System.Workflow.Runtime.Tracking.TrackingWorkflowEvent 枚举</span><span class="sxs-lookup"><span data-stu-id="c77d1-147">System.Workflow.Runtime.Tracking.TrackingWorkflowEvent enumeration</span></span>](http://go.microsoft.com/fwlink/?LinkId=119568)