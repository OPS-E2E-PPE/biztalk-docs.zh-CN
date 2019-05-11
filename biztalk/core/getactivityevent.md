---
title: GetActivityEvent | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 6fe824c9-4cea-44da-b830-5520d67988e0
caps.latest.revision: 10
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 28c237cc32afb41d0fde2e702c9b0b42a2d14f41
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65345151"
---
# <a name="getactivityevent"></a><span data-ttu-id="cc16f-102">GetActivityEvent</span><span class="sxs-lookup"><span data-stu-id="cc16f-102">GetActivityEvent</span></span>
<span data-ttu-id="cc16f-103">将推送到堆栈上的当前活动事件的名称。</span><span class="sxs-lookup"><span data-stu-id="cc16f-103">Pushes the name of the current activity event onto the stack.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="cc16f-104">语法</span><span class="sxs-lookup"><span data-stu-id="cc16f-104">Syntax</span></span>  
  
```  
  
<wf:Operation Name="GetActivityEvent"/>  
```  
  
#### <a name="parameters"></a><span data-ttu-id="cc16f-105">Parameters</span><span class="sxs-lookup"><span data-stu-id="cc16f-105">Parameters</span></span>  
 <span data-ttu-id="cc16f-106">无。</span><span class="sxs-lookup"><span data-stu-id="cc16f-106">None.</span></span>  
  
## <a name="pushed-value"></a><span data-ttu-id="cc16f-107">推送的值</span><span class="sxs-lookup"><span data-stu-id="cc16f-107">Pushed Value</span></span>  
 <span data-ttu-id="cc16f-108">包含当前活动事件的字符串。</span><span class="sxs-lookup"><span data-stu-id="cc16f-108">String containing the current activity event.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="cc16f-109">备注</span><span class="sxs-lookup"><span data-stu-id="cc16f-109">Remarks</span></span>  
 <span data-ttu-id="cc16f-110">工作流活动在工作流的生存期内可以传递几种状态。</span><span class="sxs-lookup"><span data-stu-id="cc16f-110">A workflow activity can pass through several states during the lifetime of the workflow.</span></span> <span data-ttu-id="cc16f-111">Windows Workflow Foundation BAM 侦听器支持的执行状态值定义的大多数`System.Workflow.ComponentModel.ActivityExecutionStatus`枚举下, 表中所示。</span><span class="sxs-lookup"><span data-stu-id="cc16f-111">The Windows Workflow Foundation BAM interceptor supports most of the execution status values defined by the `System.Workflow.ComponentModel.ActivityExecutionStatus` enumeration, as shown in the following table.</span></span>  
  
|<span data-ttu-id="cc16f-112">执行状态</span><span class="sxs-lookup"><span data-stu-id="cc16f-112">Execution status</span></span>|<span data-ttu-id="cc16f-113">Description</span><span class="sxs-lookup"><span data-stu-id="cc16f-113">Description</span></span>|  
|----------------------|-----------------|  
|<span data-ttu-id="cc16f-114">正在取消</span><span class="sxs-lookup"><span data-stu-id="cc16f-114">Canceling</span></span>|<span data-ttu-id="cc16f-115">正在取消活动时表示的状态。</span><span class="sxs-lookup"><span data-stu-id="cc16f-115">Represents the status when an activity is in the process of being canceled.</span></span>|  
|<span data-ttu-id="cc16f-116">已关闭</span><span class="sxs-lookup"><span data-stu-id="cc16f-116">Closed</span></span>|<span data-ttu-id="cc16f-117">表示活动已关闭的状态。</span><span class="sxs-lookup"><span data-stu-id="cc16f-117">Represents the status when an activity is closed.</span></span>|  
|<span data-ttu-id="cc16f-118">补偿</span><span class="sxs-lookup"><span data-stu-id="cc16f-118">Compensating</span></span>|<span data-ttu-id="cc16f-119">表示正在补偿活动的状态。</span><span class="sxs-lookup"><span data-stu-id="cc16f-119">Represents the status when an activity is compensating.</span></span>|  
|<span data-ttu-id="cc16f-120">执行</span><span class="sxs-lookup"><span data-stu-id="cc16f-120">Executing</span></span>|<span data-ttu-id="cc16f-121">表示正在执行活动的状态。</span><span class="sxs-lookup"><span data-stu-id="cc16f-121">Represents the status when an activity is executing.</span></span>|  
|<span data-ttu-id="cc16f-122">出错</span><span class="sxs-lookup"><span data-stu-id="cc16f-122">Faulting</span></span>|<span data-ttu-id="cc16f-123">表示正在进行错误处理活动的状态。</span><span class="sxs-lookup"><span data-stu-id="cc16f-123">Represents the status when an activity is faulting.</span></span>|  
  
> [!NOTE]
>  <span data-ttu-id="cc16f-124">不能使用两者`GetActivityEvent`和`GetWorkflowEvent`同一个 OnEvent 元素中。</span><span class="sxs-lookup"><span data-stu-id="cc16f-124">You cannot use both `GetActivityEvent` and `GetWorkflowEvent` in the same OnEvent element.</span></span>  
  
## <a name="example"></a><span data-ttu-id="cc16f-125">示例</span><span class="sxs-lookup"><span data-stu-id="cc16f-125">Example</span></span>  
 <span data-ttu-id="cc16f-126">下面的示例包含配置为查找特定活动的事件筛选器表达式-FoodAndDringPolicy — 关闭的工作流中。</span><span class="sxs-lookup"><span data-stu-id="cc16f-126">The following sample contains an event filter expression configured to find a specific activity—FoodAndDringPolicy—in a Closed workflow.</span></span> <span data-ttu-id="cc16f-127">这是通过使用的操作，包括组合`GetActivityEvent`， `GetActivityName`，和逻辑运算。</span><span class="sxs-lookup"><span data-stu-id="cc16f-127">This is done by using a combination of operations including `GetActivityEvent`, `GetActivityName`, and logical operations.</span></span>  
  
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
  
 <span data-ttu-id="cc16f-128">此筛选器模式非常常见的 Windows Workflow Foundation 侦听器配置文件。</span><span class="sxs-lookup"><span data-stu-id="cc16f-128">This filter pattern is common with Windows Workflow Foundation interceptor configuration files.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="cc16f-129">参数不需要引号，除非您明确尝试匹配包含引号的字符串。</span><span class="sxs-lookup"><span data-stu-id="cc16f-129">Arguments do not require quotation marks unless you are explicitly trying to match a string that contains quotation marks.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="cc16f-130">请参阅</span><span class="sxs-lookup"><span data-stu-id="cc16f-130">See Also</span></span>  
 [<span data-ttu-id="cc16f-131">System.Workflow.ComponentModel.ActivityExecutionStatus 枚举</span><span class="sxs-lookup"><span data-stu-id="cc16f-131">System.Workflow.ComponentModel.ActivityExecutionStatus enumeration</span></span>](http://go.microsoft.com/fwlink/?LinkId=119570)