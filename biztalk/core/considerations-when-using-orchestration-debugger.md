---
title: 使用业务流程调试器时的注意事项 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- Orchestration Debugger, modified orchestrations
- Orchestration Debugger, planning
- atomic scopes
- planning, Orchestration Debugger
- Orchestration Debugger, atomic scopes
- Orchestration Debugger, simple types
- orchestrations, modifying
ms.assetid: 55bfef48-08bd-48bb-abd5-7264e683da46
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 8e3e244691d61ef27c55f606414dd08857d58f14
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "36998150"
---
# <a name="considerations-when-using-orchestration-debugger"></a><span data-ttu-id="7d093-102">使用业务流程调试器时的注意事项</span><span class="sxs-lookup"><span data-stu-id="7d093-102">Considerations when Using Orchestration Debugger</span></span>
<span data-ttu-id="7d093-103">以下是一些需要处理业务流程调试器时，请考虑事项。</span><span class="sxs-lookup"><span data-stu-id="7d093-103">Following are some things to consider when you work with the Orchestration Debugger.</span></span>  
  
## <a name="tracking-atomic-scopes"></a><span data-ttu-id="7d093-104">跟踪原子作用域</span><span class="sxs-lookup"><span data-stu-id="7d093-104">Tracking atomic scopes</span></span>  
 <span data-ttu-id="7d093-105">业务流程可以包含原子作用域，以包括对规则引擎的调用。</span><span class="sxs-lookup"><span data-stu-id="7d093-105">An orchestration can contain atomic scopes to include calls to the Rule Engine.</span></span> <span data-ttu-id="7d093-106">当附加到业务流程调试器中的某个实例时，业务流程实例中的任何原子作用域将导致跟踪的事件列表中出现间隔。</span><span class="sxs-lookup"><span data-stu-id="7d093-106">When you attach to an instance in the orchestration debugger, any atomic scopes in the orchestration instance will cause gaps to appear in the tracked events list.</span></span> <span data-ttu-id="7d093-107">以下两个原因发生这种情况：</span><span class="sxs-lookup"><span data-stu-id="7d093-107">This happens for two reasons:</span></span>  
  
- <span data-ttu-id="7d093-108">因为在作用域提交之前不会持久化原子事务中形状的事件</span><span class="sxs-lookup"><span data-stu-id="7d093-108">Because events for the shapes inside atomic transactions do not get persisted until the scope commits</span></span>  
  
- <span data-ttu-id="7d093-109">调试器重新加载到列表的末尾上的事件，以便在实时会话过程中的空白保持未填充。</span><span class="sxs-lookup"><span data-stu-id="7d093-109">The debugger reloads events onto the end of the list, so any gaps remain unfilled during the live session.</span></span>  
  
  <span data-ttu-id="7d093-110">如果刷新视图，则可以消除间隙。</span><span class="sxs-lookup"><span data-stu-id="7d093-110">You can eliminate the gaps if you refresh the view.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="7d093-111">不能在原子作用域内的形状上设置断点。</span><span class="sxs-lookup"><span data-stu-id="7d093-111">You cannot set a breakpoint on shapes inside an atomic scope.</span></span>  
  
## <a name="setting-breakpoints-in-the-exception-handler-scope"></a><span data-ttu-id="7d093-112">在异常处理程序作用域中设置断点</span><span class="sxs-lookup"><span data-stu-id="7d093-112">Setting breakpoints in the exception handler scope</span></span>  
 <span data-ttu-id="7d093-113">如果在设置了断点异常 catch 处理程序、 异常类型必须标记为可序列化，或业务流程调试器将在您设置的断点处停止。</span><span class="sxs-lookup"><span data-stu-id="7d093-113">If the breakpoint is set at the exception catch handler, the exception types must be marked as serializable, or the orchestration debugger will not stop at the breakpoints you set.</span></span> <span data-ttu-id="7d093-114">这是因为，业务流程调试器会暂留在所需断点，因此，在业务流程实例状态没有非可序列化对象，将引发一个持久性异常，并且在这种情况下，你将收到DebugBreakPointFailedException 异常。</span><span class="sxs-lookup"><span data-stu-id="7d093-114">This is because of that the orchestration debugger does persistence at the breakpoint, therefore, when there is a non-serializable object in the orchestration instance state, a persistence exception will be thrown, and in this case, you will also receive a DebugBreakPointFailedException exception.</span></span>  
  
## <a name="tracking-a-modified-orchestration"></a><span data-ttu-id="7d093-115">跟踪已修改的业务流程</span><span class="sxs-lookup"><span data-stu-id="7d093-115">Tracking a modified orchestration</span></span>  
 <span data-ttu-id="7d093-116">如果您跟踪在不更改版本号的情况下修改业务流程，必须重新启动该业务流程登记到的所有主机实例。</span><span class="sxs-lookup"><span data-stu-id="7d093-116">If you track an orchestration modified without changing the version number, you must restart all the host instances to which the orchestration is enlisted.</span></span> <span data-ttu-id="7d093-117">这可确保任何形状更改新部署版本中正确显示，在逐步执行业务流程调试器。</span><span class="sxs-lookup"><span data-stu-id="7d093-117">This insures that any shape change in the newly deployed version displays correctly, as you step through the Orchestration Debugger.</span></span>  
  
## <a name="tracking-simple-types"></a><span data-ttu-id="7d093-118">跟踪的简单类型</span><span class="sxs-lookup"><span data-stu-id="7d093-118">Tracking simple types</span></span>  
 <span data-ttu-id="7d093-119">业务流程调试器仅支持简单类型。</span><span class="sxs-lookup"><span data-stu-id="7d093-119">The Orchestration Debugger only supports simple types.</span></span> <span data-ttu-id="7d093-120">例如，如果跟踪包含.NET 对象的多部分消息可以查看所有消息部分，但.NET 对象属性的属性。</span><span class="sxs-lookup"><span data-stu-id="7d093-120">For example, if you track a multipart message that contains a .NET object you can view the properties of all message parts, with the exception of the .NET object properties.</span></span>  
  
 <span data-ttu-id="7d093-121">当业务流程将开始出现在断点处的状态和业务流程调试器时，可以执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="7d093-121">When an orchestration appears in the In Breakpoint state and the Orchestration Debugger starts, you can perform the following actions:</span></span>  
  
-   <span data-ttu-id="7d093-122">使用**附加**服务选项。</span><span class="sxs-lookup"><span data-stu-id="7d093-122">Use the **Attach** service option.</span></span>  
  
-   <span data-ttu-id="7d093-123">查看已完成的步骤。</span><span class="sxs-lookup"><span data-stu-id="7d093-123">Review the steps that have already completed.</span></span>  
  
-   <span data-ttu-id="7d093-124">查看变量和消息的状态。</span><span class="sxs-lookup"><span data-stu-id="7d093-124">View the state of variables and messages.</span></span>  
  
-   <span data-ttu-id="7d093-125">设置其他断点。</span><span class="sxs-lookup"><span data-stu-id="7d093-125">Set additional breakpoints.</span></span>  
  
-   <span data-ttu-id="7d093-126">选择**继续服务**选项。</span><span class="sxs-lookup"><span data-stu-id="7d093-126">Select the **Continue Service** option.</span></span>  
  
-   <span data-ttu-id="7d093-127">重复所需的任何步骤。</span><span class="sxs-lookup"><span data-stu-id="7d093-127">Repeat any steps as required.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7d093-128">请参阅</span><span class="sxs-lookup"><span data-stu-id="7d093-128">See Also</span></span>  
 <span data-ttu-id="7d093-129">[业务流程调试器中的交互模式](../core/interactive-mode-in-orchestration-debugger.md) </span><span class="sxs-lookup"><span data-stu-id="7d093-129">[Interactive Mode in Orchestration Debugger](../core/interactive-mode-in-orchestration-debugger.md) </span></span>  
 [<span data-ttu-id="7d093-130">调试业务流程</span><span class="sxs-lookup"><span data-stu-id="7d093-130">Debugging an Orchestration</span></span>](../core/debugging-an-orchestration.md)