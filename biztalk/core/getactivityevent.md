---
title: "GetActivityEvent |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 6fe824c9-4cea-44da-b830-5520d67988e0
caps.latest.revision: "10"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 9fb039c0e9946091214a52fbb605753a212c233c
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="getactivityevent"></a><span data-ttu-id="5ddad-102">GetActivityEvent</span><span class="sxs-lookup"><span data-stu-id="5ddad-102">GetActivityEvent</span></span>
<span data-ttu-id="5ddad-103">将当前活动事件的名称推送到堆栈上。</span><span class="sxs-lookup"><span data-stu-id="5ddad-103">Pushes the name of the current activity event onto the stack.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="5ddad-104">语法</span><span class="sxs-lookup"><span data-stu-id="5ddad-104">Syntax</span></span>  
  
```  
  
<wf:Operation Name="GetActivityEvent"/>  
```  
  
#### <a name="parameters"></a><span data-ttu-id="5ddad-105">Parameters</span><span class="sxs-lookup"><span data-stu-id="5ddad-105">Parameters</span></span>  
 <span data-ttu-id="5ddad-106">无。</span><span class="sxs-lookup"><span data-stu-id="5ddad-106">None.</span></span>  
  
## <a name="pushed-value"></a><span data-ttu-id="5ddad-107">推送的值</span><span class="sxs-lookup"><span data-stu-id="5ddad-107">Pushed Value</span></span>  
 <span data-ttu-id="5ddad-108">包含当前活动事件的字符串。</span><span class="sxs-lookup"><span data-stu-id="5ddad-108">String containing the current activity event.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="5ddad-109">注释</span><span class="sxs-lookup"><span data-stu-id="5ddad-109">Remarks</span></span>  
 <span data-ttu-id="5ddad-110">一个工作流活动在工作流的生存期中可以传递几种状态。</span><span class="sxs-lookup"><span data-stu-id="5ddad-110">A workflow activity can pass through several states during the lifetime of the workflow.</span></span> <span data-ttu-id="5ddad-111">Windows Workflow Foundation BAM 侦听器支持的定义的执行状态值大多数`System.Workflow.ComponentModel.ActivityExecutionStatus`枚举下, 表中所示。</span><span class="sxs-lookup"><span data-stu-id="5ddad-111">The Windows Workflow Foundation BAM interceptor supports most of the execution status values defined by the `System.Workflow.ComponentModel.ActivityExecutionStatus` enumeration, as shown in the following table.</span></span>  
  
|<span data-ttu-id="5ddad-112">执行状态</span><span class="sxs-lookup"><span data-stu-id="5ddad-112">Execution status</span></span>|<span data-ttu-id="5ddad-113">Description</span><span class="sxs-lookup"><span data-stu-id="5ddad-113">Description</span></span>|  
|----------------------|-----------------|  
|<span data-ttu-id="5ddad-114">Canceling</span><span class="sxs-lookup"><span data-stu-id="5ddad-114">Canceling</span></span>|<span data-ttu-id="5ddad-115">正在取消活动时，可表示的状态。</span><span class="sxs-lookup"><span data-stu-id="5ddad-115">Represents the status when an activity is in the process of being canceled.</span></span>|  
|<span data-ttu-id="5ddad-116">已关闭</span><span class="sxs-lookup"><span data-stu-id="5ddad-116">Closed</span></span>|<span data-ttu-id="5ddad-117">表示活动关闭时的状态。</span><span class="sxs-lookup"><span data-stu-id="5ddad-117">Represents the status when an activity is closed.</span></span>|  
|<span data-ttu-id="5ddad-118">Compensating</span><span class="sxs-lookup"><span data-stu-id="5ddad-118">Compensating</span></span>|<span data-ttu-id="5ddad-119">表示活动正在补偿时的状态。</span><span class="sxs-lookup"><span data-stu-id="5ddad-119">Represents the status when an activity is compensating.</span></span>|  
|<span data-ttu-id="5ddad-120">Executing</span><span class="sxs-lookup"><span data-stu-id="5ddad-120">Executing</span></span>|<span data-ttu-id="5ddad-121">表示活动正在执行时的状态。</span><span class="sxs-lookup"><span data-stu-id="5ddad-121">Represents the status when an activity is executing.</span></span>|  
|<span data-ttu-id="5ddad-122">Faulting</span><span class="sxs-lookup"><span data-stu-id="5ddad-122">Faulting</span></span>|<span data-ttu-id="5ddad-123">表示活动发生故障时的状态。</span><span class="sxs-lookup"><span data-stu-id="5ddad-123">Represents the status when an activity is faulting.</span></span>|  
  
> [!NOTE]
>  <span data-ttu-id="5ddad-124">你不能同时使用`GetActivityEvent`和`GetWorkflowEvent`相同 OnEvent 元素中。</span><span class="sxs-lookup"><span data-stu-id="5ddad-124">You cannot use both `GetActivityEvent` and `GetWorkflowEvent` in the same OnEvent element.</span></span>  
  
## <a name="example"></a><span data-ttu-id="5ddad-125">示例</span><span class="sxs-lookup"><span data-stu-id="5ddad-125">Example</span></span>  
 <span data-ttu-id="5ddad-126">下面的示例包含一个配置为在关闭的工作流中查找特定活动 (FoodAndDringPolicy) 的事件筛选器表达式。</span><span class="sxs-lookup"><span data-stu-id="5ddad-126">The following sample contains an event filter expression configured to find a specific activity—FoodAndDringPolicy—in a Closed workflow.</span></span> <span data-ttu-id="5ddad-127">这可通过使用的操作包括组合`GetActivityEvent`， `GetActivityName`，和逻辑运算。</span><span class="sxs-lookup"><span data-stu-id="5ddad-127">This is done by using a combination of operations including `GetActivityEvent`, `GetActivityName`, and logical operations.</span></span>  
  
```  
<ic:Filter>  
  <ic:Expression>  
    <wf:Operation Name="GetActivityName"/>  
    <ic:Operation Name="Constant">  
      <ic:Argument>FoodAndDrinksPolicy</ic:Argument>  
    </ic:Operation>  
    <ic:Operation Name="Equals"/>  
    <wf:Operation Name="GetActivityEvent"/>  
    <ic:Operation Name="Constant">  
      <ic:Argument>Closed</ic:Argument>  
    </ic:Operation>  
    <ic:Operation Name="Equals"/>  
    <ic:Operation Name="And"/>  
  </ic:Expression>  
</ic:Filter>  
```  
  
 <span data-ttu-id="5ddad-128">该筛选模式常用于 Windows Workflow Foundation 侦听器配置文件。</span><span class="sxs-lookup"><span data-stu-id="5ddad-128">This filter pattern is common with Windows Workflow Foundation interceptor configuration files.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="5ddad-129">参数不需要使用引号，除非您明确尝试匹配包含引号的字符串。</span><span class="sxs-lookup"><span data-stu-id="5ddad-129">Arguments do not require quotation marks unless you are explicitly trying to match a string that contains quotation marks.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5ddad-130">另请参阅</span><span class="sxs-lookup"><span data-stu-id="5ddad-130">See Also</span></span>  
 [<span data-ttu-id="5ddad-131">System.Workflow.ComponentModel.ActivityExecutionStatus 枚举</span><span class="sxs-lookup"><span data-stu-id="5ddad-131">System.Workflow.ComponentModel.ActivityExecutionStatus enumeration</span></span>](http://go.microsoft.com/fwlink/?LinkId=119570)