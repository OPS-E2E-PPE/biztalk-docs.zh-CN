---
title: GetWorkflowEvent | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 2534e0b8-26df-4554-b0df-742014deb64d
caps.latest.revision: 10
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 68cf89a168606ae64a83c67b29eb058770b67f44
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65387648"
---
# <a name="getworkflowevent"></a><span data-ttu-id="bb850-102">GetWorkflowEvent</span><span class="sxs-lookup"><span data-stu-id="bb850-102">GetWorkflowEvent</span></span>
<span data-ttu-id="bb850-103">将推送到堆栈上的当前工作流事件的名称。</span><span class="sxs-lookup"><span data-stu-id="bb850-103">Pushes the name of the current workflow event onto the stack.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="bb850-104">语法</span><span class="sxs-lookup"><span data-stu-id="bb850-104">Syntax</span></span>  
  
```  
  
<wf:Operation Name="GetWorkflowEvent" />  
```  
  
#### <a name="parameters"></a><span data-ttu-id="bb850-105">Parameters</span><span class="sxs-lookup"><span data-stu-id="bb850-105">Parameters</span></span>  
 <span data-ttu-id="bb850-106">无。</span><span class="sxs-lookup"><span data-stu-id="bb850-106">None.</span></span>  
  
## <a name="pushed-value"></a><span data-ttu-id="bb850-107">推送的值</span><span class="sxs-lookup"><span data-stu-id="bb850-107">Pushed Value</span></span>  
 <span data-ttu-id="bb850-108">包含当前的工作流事件的字符串。</span><span class="sxs-lookup"><span data-stu-id="bb850-108">String containing the current workflow event.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="bb850-109">备注</span><span class="sxs-lookup"><span data-stu-id="bb850-109">Remarks</span></span>  
 <span data-ttu-id="bb850-110">工作流实例在其执行过程期间可以传递几种状态。</span><span class="sxs-lookup"><span data-stu-id="bb850-110">A workflow instance can pass through several states during the course of its execution.</span></span> <span data-ttu-id="bb850-111">例如，工作流实例可能会进入空闲状态，或可能被挂起。</span><span class="sxs-lookup"><span data-stu-id="bb850-111">For example, a workflow instance may become idle, or it may be suspended.</span></span> <span data-ttu-id="bb850-112">每次工作流实例更改状态，它会发出到运行时跟踪基础结构的工作流状态事件。</span><span class="sxs-lookup"><span data-stu-id="bb850-112">Every time the workflow instance changes state, it emits a workflow status event to the runtime tracking infrastructure.</span></span> <span data-ttu-id="bb850-113">Windows Workflow Foundation BAM 侦听器支持由定义的事件的大多数`System.Workflow.Runtime.Tracking.TrackingWorkflowEvent`枚举下, 表中所示。</span><span class="sxs-lookup"><span data-stu-id="bb850-113">The Windows Workflow Foundation BAM interceptor supports most of the events defined by the `System.Workflow.Runtime.Tracking.TrackingWorkflowEvent` enumeration, as shown in the following table.</span></span>  
  
|<span data-ttu-id="bb850-114">活动事件</span><span class="sxs-lookup"><span data-stu-id="bb850-114">Activity event</span></span>|<span data-ttu-id="bb850-115">Description</span><span class="sxs-lookup"><span data-stu-id="bb850-115">Description</span></span>|  
|--------------------|-----------------|  
|<span data-ttu-id="bb850-116">已更改</span><span class="sxs-lookup"><span data-stu-id="bb850-116">Changed</span></span>|<span data-ttu-id="bb850-117">工作流实例上发生了工作流更改。</span><span class="sxs-lookup"><span data-stu-id="bb850-117">A workflow change has occurred on the workflow instance.</span></span>|  
|<span data-ttu-id="bb850-118">已完成</span><span class="sxs-lookup"><span data-stu-id="bb850-118">Completed</span></span>|<span data-ttu-id="bb850-119">工作流实例已完成。</span><span class="sxs-lookup"><span data-stu-id="bb850-119">The workflow instance has completed.</span></span>|  
|<span data-ttu-id="bb850-120">创建时间</span><span class="sxs-lookup"><span data-stu-id="bb850-120">Created</span></span>|<span data-ttu-id="bb850-121">已创建工作流实例。</span><span class="sxs-lookup"><span data-stu-id="bb850-121">The workflow instance has been created.</span></span>|  
|<span data-ttu-id="bb850-122">异常</span><span class="sxs-lookup"><span data-stu-id="bb850-122">Exception</span></span>|<span data-ttu-id="bb850-123">发生未经处理的异常。</span><span class="sxs-lookup"><span data-stu-id="bb850-123">An unhandled exception has occurred.</span></span>|  
|<span data-ttu-id="bb850-124">Idle</span><span class="sxs-lookup"><span data-stu-id="bb850-124">Idle</span></span>|<span data-ttu-id="bb850-125">工作流实例处于空闲状态。</span><span class="sxs-lookup"><span data-stu-id="bb850-125">The workflow instance is idle.</span></span>|  
|<span data-ttu-id="bb850-126">加载</span><span class="sxs-lookup"><span data-stu-id="bb850-126">Loaded</span></span>|<span data-ttu-id="bb850-127">工作流实例加载到内存。</span><span class="sxs-lookup"><span data-stu-id="bb850-127">The workflow instance has been loaded into memory.</span></span>|  
|<span data-ttu-id="bb850-128">保留</span><span class="sxs-lookup"><span data-stu-id="bb850-128">Persisted</span></span>|<span data-ttu-id="bb850-129">已保留工作流实例。</span><span class="sxs-lookup"><span data-stu-id="bb850-129">The workflow instance has been persisted.</span></span>|  
|<span data-ttu-id="bb850-130">恢复</span><span class="sxs-lookup"><span data-stu-id="bb850-130">Resumed</span></span>|<span data-ttu-id="bb850-131">先前挂起的工作流实例已继续运行。</span><span class="sxs-lookup"><span data-stu-id="bb850-131">A previously suspended workflow instance has resumed running.</span></span>|  
|<span data-ttu-id="bb850-132">Started</span><span class="sxs-lookup"><span data-stu-id="bb850-132">Started</span></span>|<span data-ttu-id="bb850-133">已启动工作流实例。</span><span class="sxs-lookup"><span data-stu-id="bb850-133">The workflow instance has been started.</span></span>|  
|<span data-ttu-id="bb850-134">挂起</span><span class="sxs-lookup"><span data-stu-id="bb850-134">Suspended</span></span>|<span data-ttu-id="bb850-135">工作流实例已挂起。</span><span class="sxs-lookup"><span data-stu-id="bb850-135">The workflow instance has been suspended.</span></span>|  
|<span data-ttu-id="bb850-136">终止</span><span class="sxs-lookup"><span data-stu-id="bb850-136">Terminated</span></span>|<span data-ttu-id="bb850-137">工作流实例已终止。</span><span class="sxs-lookup"><span data-stu-id="bb850-137">The workflow instance has been terminated.</span></span>|  
|<span data-ttu-id="bb850-138">卸载</span><span class="sxs-lookup"><span data-stu-id="bb850-138">Unloaded</span></span>|<span data-ttu-id="bb850-139">已从内存中卸载工作流实例。</span><span class="sxs-lookup"><span data-stu-id="bb850-139">The workflow instance has been unloaded from memory.</span></span>|  
  
> [!NOTE]
>  <span data-ttu-id="bb850-140">不能使用两者`GetWorkflowEvent`和`GetActivityEvent`同一个 OnEvent 元素中。</span><span class="sxs-lookup"><span data-stu-id="bb850-140">You cannot use both `GetWorkflowEvent` and `GetActivityEvent` in the same OnEvent element.</span></span>  
  
## <a name="example"></a><span data-ttu-id="bb850-141">示例</span><span class="sxs-lookup"><span data-stu-id="bb850-141">Example</span></span>  
 <span data-ttu-id="bb850-142">下面的示例包含配置为查找特定活动的筛选器-"FoodAndDrinksPolicy"，在工作流中。</span><span class="sxs-lookup"><span data-stu-id="bb850-142">The following sample contains a filter that is configured to find a specific activity—"FoodAndDrinksPolicy"—in a workflow.</span></span> <span data-ttu-id="bb850-143">在示例中，配置筛选器来查找关闭的工作流中名为"FoodAndDrinksPolicy"的活动。</span><span class="sxs-lookup"><span data-stu-id="bb850-143">In the sample, a filter is configured to find the activity named "FoodAndDrinksPolicy" in a closed workflow.</span></span> <span data-ttu-id="bb850-144">这是通过比较返回的值`GetWorkflowEvent`常量"Created"。</span><span class="sxs-lookup"><span data-stu-id="bb850-144">This is done by comparing the value returned by `GetWorkflowEvent` to the constant "Created".</span></span>  
  
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
  
 <span data-ttu-id="bb850-145">此操作可用于跟踪工作流的生存期和检测异常或其他问题与工作流。</span><span class="sxs-lookup"><span data-stu-id="bb850-145">This operation is useful for tracking the lifetime of a workflow and for detecting exceptions or other problems with the workflow.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="bb850-146">请参阅</span><span class="sxs-lookup"><span data-stu-id="bb850-146">See Also</span></span>  
 [<span data-ttu-id="bb850-147">System.Workflow.Runtime.Tracking.TrackingWorkflowEvent 枚举</span><span class="sxs-lookup"><span data-stu-id="bb850-147">System.Workflow.Runtime.Tracking.TrackingWorkflowEvent enumeration</span></span>](http://go.microsoft.com/fwlink/?LinkId=119568)