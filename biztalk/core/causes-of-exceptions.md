---
title: 引发异常的原因 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- orchestrations, errors
- errors, orchestrations
- errors, causes
ms.assetid: b0422382-d034-4c58-87c6-fc269dbbfe43
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 71c6bf04421ca538400545239711637990e3adf5
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65357597"
---
# <a name="causes-of-exceptions"></a><span data-ttu-id="cbde4-102">引发异常的原因</span><span class="sxs-lookup"><span data-stu-id="cbde4-102">Causes of Exceptions</span></span>
<span data-ttu-id="cbde4-103">可以通过以下方式在业务流程中生成异常：</span><span class="sxs-lookup"><span data-stu-id="cbde4-103">Exceptions can be generated within an orchestration in the following ways:</span></span>  
  
-   <span data-ttu-id="cbde4-104">通过**引发异常**形状，它立即无条件地将引发异常。</span><span class="sxs-lookup"><span data-stu-id="cbde4-104">By a **Throw Exception** shape, which throws an exception immediately and unconditionally.</span></span> <span data-ttu-id="cbde4-105">控制权将传递从**引发异常**形状直接向相应的异常处理程序。</span><span class="sxs-lookup"><span data-stu-id="cbde4-105">Control passes from the **Throw Exception** shape directly to the appropriate exception handler.</span></span>  
  
-   <span data-ttu-id="cbde4-106">通过在一个长时间运行的事务过期超时。</span><span class="sxs-lookup"><span data-stu-id="cbde4-106">By a time-out expiring in a long-running transaction.</span></span> <span data-ttu-id="cbde4-107">预定义的系统异常 —**Microsoft.XLANG.BaseTypes.TimeOutException**— 在这种情况下引发。</span><span class="sxs-lookup"><span data-stu-id="cbde4-107">A predefined system exception—**Microsoft.XLANG.BaseTypes.TimeOutException**—is thrown in this case.</span></span>  
  
-   <span data-ttu-id="cbde4-108">由某些其他事务失败。</span><span class="sxs-lookup"><span data-stu-id="cbde4-108">By some other transaction failure.</span></span> <span data-ttu-id="cbde4-109">运行时引擎会引发如 Microsoft.XLANG.BaseTypes.PersistenceException 这些故障的系统定义消息。</span><span class="sxs-lookup"><span data-stu-id="cbde4-109">The runtime engine throws a system-defined message such as Microsoft.XLANG.BaseTypes.PersistenceException for these failures.</span></span>  
  
-   <span data-ttu-id="cbde4-110">通过用户代码异常。</span><span class="sxs-lookup"><span data-stu-id="cbde4-110">By a user code exception.</span></span> <span data-ttu-id="cbde4-111">当业务流程中进行时对外部用户代码的调用时，调用的公共语言运行时类可能会引发异常。</span><span class="sxs-lookup"><span data-stu-id="cbde4-111">When calls to external user code are made within an orchestration, common language runtime classes that are called can throw exceptions.</span></span> <span data-ttu-id="cbde4-112">如果未在用户代码中处理这些异常，它们最终向上传播到在其中进行调用用户代码的作用域。</span><span class="sxs-lookup"><span data-stu-id="cbde4-112">If these exceptions are not handled in the user code, they eventually propagate up into the scope in which the call to the user code is made.</span></span>  
  
-   <span data-ttu-id="cbde4-113">由某些其他系统异常 （例如，持久化错误，例如类型加载程序异常的另一个.NET 或系统异常或数据转换错误）。</span><span class="sxs-lookup"><span data-stu-id="cbde4-113">By some other system exception (for example, a persistence failure, another .NET or system exception such as type loader exception, or a data conversion error).</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="cbde4-114">当引发类型加载程序异常时，可能不会捕获异常在**捕获异常**在同一个阻止**作用域**形状。</span><span class="sxs-lookup"><span data-stu-id="cbde4-114">When a type loader exception is thrown, the exception may not be caught in the **Catch Exception** block in the same **Scope** shape.</span></span> <span data-ttu-id="cbde4-115">这是由于的例外是从类型加载程序，不能从 BizTalk 业务流程进程。</span><span class="sxs-lookup"><span data-stu-id="cbde4-115">This is because of that the exception is from the type loader, not from the BizTalk orchestration process.</span></span> <span data-ttu-id="cbde4-116">因此，它不遵循控制流的 BizTalk 规则。</span><span class="sxs-lookup"><span data-stu-id="cbde4-116">Therefore, it does not follow the BizTalk rules of control flow.</span></span>  
  
-   <span data-ttu-id="cbde4-117">通过停止执行周围的作用域中的同级分支。</span><span class="sxs-lookup"><span data-stu-id="cbde4-117">By a sibling branch in a surrounding scope halting execution.</span></span> <span data-ttu-id="cbde4-118">Microsoft.XLANG.BaseTypes.ForcedTerminationException 引发向每个分支，在这种情况下，并且你可能想要添加到每个异常处理程序。</span><span class="sxs-lookup"><span data-stu-id="cbde4-118">Microsoft.XLANG.BaseTypes.ForcedTerminationException is thrown to each branch in this case, and you might want to add an exception handler to each.</span></span> <span data-ttu-id="cbde4-119">此类异常处理程序不能重新引发的异常，也不应尝试会引发任何其他类型的异常。</span><span class="sxs-lookup"><span data-stu-id="cbde4-119">Such an exception handler cannot re-throw its exception, nor should it attempt to throw any other type of exception.</span></span>  
  
-   <span data-ttu-id="cbde4-120">由一个外部的消息，指示错误的回执。</span><span class="sxs-lookup"><span data-stu-id="cbde4-120">By receipt of an external message that indicates a fault.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="cbde4-121">请参阅</span><span class="sxs-lookup"><span data-stu-id="cbde4-121">See Also</span></span>  
 <span data-ttu-id="cbde4-122">[错误消息](../core/fault-messages.md) </span><span class="sxs-lookup"><span data-stu-id="cbde4-122">[Fault Messages](../core/fault-messages.md) </span></span>  
 [<span data-ttu-id="cbde4-123">异常</span><span class="sxs-lookup"><span data-stu-id="cbde4-123">Exceptions</span></span>](../core/exceptions.md)