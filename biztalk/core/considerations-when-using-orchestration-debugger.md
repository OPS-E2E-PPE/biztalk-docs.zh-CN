---
title: 使用业务流程调试器时的注意事项 |Microsoft 文档
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
ms.openlocfilehash: 2815da55bc74d822cb5fe2540347855db75b3a8b
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22237965"
---
# <a name="considerations-when-using-orchestration-debugger"></a><span data-ttu-id="7566a-102">使用业务流程调试器时的注意事项</span><span class="sxs-lookup"><span data-stu-id="7566a-102">Considerations when Using Orchestration Debugger</span></span>
<span data-ttu-id="7566a-103">以下是要考虑业务流程调试器中处理时的一些事项。</span><span class="sxs-lookup"><span data-stu-id="7566a-103">Following are some things to consider when you work with the Orchestration Debugger.</span></span>  
  
## <a name="tracking-atomic-scopes"></a><span data-ttu-id="7566a-104">跟踪原子作用域</span><span class="sxs-lookup"><span data-stu-id="7566a-104">Tracking atomic scopes</span></span>  
 <span data-ttu-id="7566a-105">业务流程可以包含原子作用域，以包括对规则引擎调用。</span><span class="sxs-lookup"><span data-stu-id="7566a-105">An orchestration can contain atomic scopes to include calls to the Rule Engine.</span></span> <span data-ttu-id="7566a-106">当附加到业务流程调试器中的某个实例时，业务流程实例中的所有原子作用域将导致显示在跟踪的事件列表的差距。</span><span class="sxs-lookup"><span data-stu-id="7566a-106">When you attach to an instance in the orchestration debugger, any atomic scopes in the orchestration instance will cause gaps to appear in the tracked events list.</span></span> <span data-ttu-id="7566a-107">有两个原因发生这种情况：</span><span class="sxs-lookup"><span data-stu-id="7566a-107">This happens for two reasons:</span></span>  
  
-   <span data-ttu-id="7566a-108">因为范围提交后，才执行不保存在原子事务内部形状的事件</span><span class="sxs-lookup"><span data-stu-id="7566a-108">Because events for the shapes inside atomic transactions do not get persisted until the scope commits</span></span>  
  
-   <span data-ttu-id="7566a-109">调试器将重新加载到列表中，末尾的事件，因此任何缺口实时会话期间保持未填充。</span><span class="sxs-lookup"><span data-stu-id="7566a-109">The debugger reloads events onto the end of the list, so any gaps remain unfilled during the live session.</span></span>  
  
 <span data-ttu-id="7566a-110">如果您刷新视图，则可以消除缺口。</span><span class="sxs-lookup"><span data-stu-id="7566a-110">You can eliminate the gaps if you refresh the view.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="7566a-111">不能在原子作用域内的形状上设置断点。</span><span class="sxs-lookup"><span data-stu-id="7566a-111">You cannot set a breakpoint on shapes inside an atomic scope.</span></span>  
  
## <a name="setting-breakpoints-in-the-exception-handler-scope"></a><span data-ttu-id="7566a-112">异常处理程序作用域中设置断点</span><span class="sxs-lookup"><span data-stu-id="7566a-112">Setting breakpoints in the exception handler scope</span></span>  
 <span data-ttu-id="7566a-113">如果在设置断点异常 catch 处理程序、 异常类型必须标记为可序列化，或业务流程调试器不会在你设置的断点处停止。</span><span class="sxs-lookup"><span data-stu-id="7566a-113">If the breakpoint is set at the exception catch handler, the exception types must be marked as serializable, or the orchestration debugger will not stop at the breakpoints you set.</span></span> <span data-ttu-id="7566a-114">这是由于，业务流程调试器时，会暂留在所需断点，因此，不可序列化对象中存在的业务流程实例状态，将引发一个持久性异常，并且在这种情况下，您也会收到DebugBreakPointFailedException 异常。</span><span class="sxs-lookup"><span data-stu-id="7566a-114">This is because of that the orchestration debugger does persistence at the breakpoint, therefore, when there is a non-serializable object in the orchestration instance state, a persistence exception will be thrown, and in this case, you will also receive a DebugBreakPointFailedException exception.</span></span>  
  
## <a name="tracking-a-modified-orchestration"></a><span data-ttu-id="7566a-115">跟踪修改后的业务流程</span><span class="sxs-lookup"><span data-stu-id="7566a-115">Tracking a modified orchestration</span></span>  
 <span data-ttu-id="7566a-116">如果跟踪未更改版本号的情况下修改一个业务流程，您必须重新启动业务流程登记到的所有主机实例。</span><span class="sxs-lookup"><span data-stu-id="7566a-116">If you track an orchestration modified without changing the version number, you must restart all the host instances to which the orchestration is enlisted.</span></span> <span data-ttu-id="7566a-117">这将确保任何形状更改新部署的版本中正确显示，逐步执行业务流程调试器。</span><span class="sxs-lookup"><span data-stu-id="7566a-117">This insures that any shape change in the newly deployed version displays correctly, as you step through the Orchestration Debugger.</span></span>  
  
## <a name="tracking-simple-types"></a><span data-ttu-id="7566a-118">跟踪简单类型</span><span class="sxs-lookup"><span data-stu-id="7566a-118">Tracking simple types</span></span>  
 <span data-ttu-id="7566a-119">业务流程调试器仅支持简单类型。</span><span class="sxs-lookup"><span data-stu-id="7566a-119">The Orchestration Debugger only supports simple types.</span></span> <span data-ttu-id="7566a-120">例如，如果跟踪包含.NET 对象的多部分消息可以查看所有消息部分，除了.NET 对象属性的属性。</span><span class="sxs-lookup"><span data-stu-id="7566a-120">For example, if you track a multipart message that contains a .NET object you can view the properties of all message parts, with the exception of the .NET object properties.</span></span>  
  
 <span data-ttu-id="7566a-121">当业务流程出现在断点处状态和业务流程调试器启动时，你可以执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="7566a-121">When an orchestration appears in the In Breakpoint state and the Orchestration Debugger starts, you can perform the following actions:</span></span>  
  
-   <span data-ttu-id="7566a-122">使用**附加**服务选项。</span><span class="sxs-lookup"><span data-stu-id="7566a-122">Use the **Attach** service option.</span></span>  
  
-   <span data-ttu-id="7566a-123">查看已完成的步骤。</span><span class="sxs-lookup"><span data-stu-id="7566a-123">Review the steps that have already completed.</span></span>  
  
-   <span data-ttu-id="7566a-124">查看变量和消息的状态。</span><span class="sxs-lookup"><span data-stu-id="7566a-124">View the state of variables and messages.</span></span>  
  
-   <span data-ttu-id="7566a-125">设置其他断点。</span><span class="sxs-lookup"><span data-stu-id="7566a-125">Set additional breakpoints.</span></span>  
  
-   <span data-ttu-id="7566a-126">选择**继续服务**选项。</span><span class="sxs-lookup"><span data-stu-id="7566a-126">Select the **Continue Service** option.</span></span>  
  
-   <span data-ttu-id="7566a-127">重复根据需要的任何步骤。</span><span class="sxs-lookup"><span data-stu-id="7566a-127">Repeat any steps as required.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7566a-128">另请参阅</span><span class="sxs-lookup"><span data-stu-id="7566a-128">See Also</span></span>  
 <span data-ttu-id="7566a-129">[在调试器中业务流程交互模式](../core/interactive-mode-in-orchestration-debugger.md) </span><span class="sxs-lookup"><span data-stu-id="7566a-129">[Interactive Mode in Orchestration Debugger](../core/interactive-mode-in-orchestration-debugger.md) </span></span>  
 [<span data-ttu-id="7566a-130">调试业务流程</span><span class="sxs-lookup"><span data-stu-id="7566a-130">Debugging an Orchestration</span></span>](../core/debugging-an-orchestration.md)