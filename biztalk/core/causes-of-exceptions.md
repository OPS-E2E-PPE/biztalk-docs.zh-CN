---
title: 异常的原因 |Microsoft 文档
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
ms.openlocfilehash: 9006234d71751078269e5a88559839fdadd91e91
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22232461"
---
# <a name="causes-of-exceptions"></a><span data-ttu-id="2ce40-102">引发异常的原因</span><span class="sxs-lookup"><span data-stu-id="2ce40-102">Causes of Exceptions</span></span>
<span data-ttu-id="2ce40-103">可以通过以下方式在业务流程中产生异常：</span><span class="sxs-lookup"><span data-stu-id="2ce40-103">Exceptions can be generated within an orchestration in the following ways:</span></span>  
  
-   <span data-ttu-id="2ce40-104">通过**引发的异常**形状，立即无条件地将引发异常。</span><span class="sxs-lookup"><span data-stu-id="2ce40-104">By a **Throw Exception** shape, which throws an exception immediately and unconditionally.</span></span> <span data-ttu-id="2ce40-105">控制权将传递从**引发的异常**形状上直接与相应的异常处理程序。</span><span class="sxs-lookup"><span data-stu-id="2ce40-105">Control passes from the **Throw Exception** shape directly to the appropriate exception handler.</span></span>  
  
-   <span data-ttu-id="2ce40-106">通过在长时间运行事务过期超时。</span><span class="sxs-lookup"><span data-stu-id="2ce40-106">By a time-out expiring in a long-running transaction.</span></span> <span data-ttu-id="2ce40-107">预定义的系统异常-**Microsoft.XLANG.BaseTypes.TimeOutException**— 在这种情况下引发。</span><span class="sxs-lookup"><span data-stu-id="2ce40-107">A predefined system exception—**Microsoft.XLANG.BaseTypes.TimeOutException**—is thrown in this case.</span></span>  
  
-   <span data-ttu-id="2ce40-108">通过某些其他事务失败。</span><span class="sxs-lookup"><span data-stu-id="2ce40-108">By some other transaction failure.</span></span> <span data-ttu-id="2ce40-109">运行时引擎将引发如 Microsoft.XLANG.BaseTypes.PersistenceException 这些故障的系统定义消息。</span><span class="sxs-lookup"><span data-stu-id="2ce40-109">The runtime engine throws a system-defined message such as Microsoft.XLANG.BaseTypes.PersistenceException for these failures.</span></span>  
  
-   <span data-ttu-id="2ce40-110">通过用户代码异常。</span><span class="sxs-lookup"><span data-stu-id="2ce40-110">By a user code exception.</span></span> <span data-ttu-id="2ce40-111">当业务流程中进行调用外部用户代码时，调用的公共语言运行时类可以引发异常。</span><span class="sxs-lookup"><span data-stu-id="2ce40-111">When calls to external user code are made within an orchestration, common language runtime classes that are called can throw exceptions.</span></span> <span data-ttu-id="2ce40-112">如果未在用户代码中处理这些异常，它们最终向上传播到在其中进行的用户代码调用该范围。</span><span class="sxs-lookup"><span data-stu-id="2ce40-112">If these exceptions are not handled in the user code, they eventually propagate up into the scope in which the call to the user code is made.</span></span>  
  
-   <span data-ttu-id="2ce40-113">由某些其他系统异常 （例如，持久性失败，例如类型加载程序异常的另一个.NET 或系统异常或将数据转换错误）。</span><span class="sxs-lookup"><span data-stu-id="2ce40-113">By some other system exception (for example, a persistence failure, another .NET or system exception such as type loader exception, or a data conversion error).</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="2ce40-114">当引发类型加载程序异常时，可能不会捕获异常中**捕获异常**块中，在相同**作用域**形状。</span><span class="sxs-lookup"><span data-stu-id="2ce40-114">When a type loader exception is thrown, the exception may not be caught in the **Catch Exception** block in the same **Scope** shape.</span></span> <span data-ttu-id="2ce40-115">这是由于异常是从类型加载程序，不是从 BizTalk 业务流程过程。</span><span class="sxs-lookup"><span data-stu-id="2ce40-115">This is because of that the exception is from the type loader, not from the BizTalk orchestration process.</span></span> <span data-ttu-id="2ce40-116">因此，它不遵循控制流的 BizTalk 规则。</span><span class="sxs-lookup"><span data-stu-id="2ce40-116">Therefore, it does not follow the BizTalk rules of control flow.</span></span>  
  
-   <span data-ttu-id="2ce40-117">通过中止执行周边范围中的一个同级分支。</span><span class="sxs-lookup"><span data-stu-id="2ce40-117">By a sibling branch in a surrounding scope halting execution.</span></span> <span data-ttu-id="2ce40-118">Microsoft.XLANG.BaseTypes.ForcedTerminationException 引发到每个分支，这种情况下，并且你可能想要将异常处理程序添加到每个。</span><span class="sxs-lookup"><span data-stu-id="2ce40-118">Microsoft.XLANG.BaseTypes.ForcedTerminationException is thrown to each branch in this case, and you might want to add an exception handler to each.</span></span> <span data-ttu-id="2ce40-119">此类异常处理程序无法重新引发的异常，也不应尝试引发任何其他类型的异常。</span><span class="sxs-lookup"><span data-stu-id="2ce40-119">Such an exception handler cannot re-throw its exception, nor should it attempt to throw any other type of exception.</span></span>  
  
-   <span data-ttu-id="2ce40-120">通过接收外部的消息，该值指示错误。</span><span class="sxs-lookup"><span data-stu-id="2ce40-120">By receipt of an external message that indicates a fault.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2ce40-121">另请参阅</span><span class="sxs-lookup"><span data-stu-id="2ce40-121">See Also</span></span>  
 <span data-ttu-id="2ce40-122">[错误消息](../core/fault-messages.md) </span><span class="sxs-lookup"><span data-stu-id="2ce40-122">[Fault Messages](../core/fault-messages.md) </span></span>  
 [<span data-ttu-id="2ce40-123">异常</span><span class="sxs-lookup"><span data-stu-id="2ce40-123">Exceptions</span></span>](../core/exceptions.md)