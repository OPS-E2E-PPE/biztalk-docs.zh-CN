---
title: 如何配置抛出异常形状 |Microsoft 文档
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- Throw Exception shape [Orchestration Designer]
- orchestrations, errors
- Orchestration Designer, errors
ms.assetid: d3190f1b-db5e-4988-bff6-f7a276760ece
caps.latest.revision: 11
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 07d156572484ba4fbe71533252ce4fe956136699
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22248077"
---
# <a name="how-to-configure-the-throw-exception-shape"></a><span data-ttu-id="79227-102">如何配置引发异常形状</span><span class="sxs-lookup"><span data-stu-id="79227-102">How to Configure the Throw Exception Shape</span></span>
<span data-ttu-id="79227-103">您可以显式抛异常业务流程中使用**引发的异常**形状。</span><span class="sxs-lookup"><span data-stu-id="79227-103">You can explicitly throw exceptions in an orchestration by using the **Throw Exception** shape.</span></span> <span data-ttu-id="79227-104">在引发异常时，运行时引擎将搜索最近的能处理所引发的异常类型的异常处理程序。</span><span class="sxs-lookup"><span data-stu-id="79227-104">When the throw is performed, the runtime engine will search for the nearest exception handler that can handle the type of exception being thrown.</span></span>  
  
 <span data-ttu-id="79227-105">首先，在当前业务流程中搜索封闭作用域，然后按顺序考虑该作用域的相关异常处理程序，以查找与所引发的异常类型相应的处理程序。</span><span class="sxs-lookup"><span data-stu-id="79227-105">First, the current orchestration is searched for an enclosing scope, and the associated exception handlers of the scope are considered in order to locate the appropriate handler for the type of exception that has been thrown.</span></span>  
  
 <span data-ttu-id="79227-106">如果找不到适当的异常处理程序，将在调用当前业务流程的业务流程中搜索调用当前业务流程的调用点所在的作用域。</span><span class="sxs-lookup"><span data-stu-id="79227-106">If no appropriate exception handler is found, the orchestration that called the current orchestration is searched for a scope that encloses the point of the call to the current orchestration.</span></span> <span data-ttu-id="79227-107">这种搜索会持续到找到能处理当前异常的异常处理程序为止。</span><span class="sxs-lookup"><span data-stu-id="79227-107">This search continues until an exception handler is found that can handle the current exception.</span></span>  
  
 <span data-ttu-id="79227-108">完全匹配异常的异常类是所引发异常的运行时类型的类或者基类。</span><span class="sxs-lookup"><span data-stu-id="79227-108">An exact match for the exception is an exception class that is of the same class as, or a base class of, the run-time type of the exception being thrown.</span></span>  
  
 <span data-ttu-id="79227-109">在找到匹配的异常处理程序后，控制将被转到异常处理程序的第一个语句。</span><span class="sxs-lookup"><span data-stu-id="79227-109">After a matching exception handler is found, control is transferred to the first statement of the exception handler.</span></span>  
  
 <span data-ttu-id="79227-110">如果搜索匹配的异常处理程序失败，则业务流程将停止。</span><span class="sxs-lookup"><span data-stu-id="79227-110">If the search for matching exception handlers fails, the orchestration halts.</span></span> <span data-ttu-id="79227-111">事务有助于将发生这种情况的影响降至最低。</span><span class="sxs-lookup"><span data-stu-id="79227-111">Transactions can help you minimize the impact of such an occurrence.</span></span>  
  
## <a name="procedure"></a><span data-ttu-id="79227-112">过程</span><span class="sxs-lookup"><span data-stu-id="79227-112">Procedure</span></span>  
  
#### <a name="to-configure-a-throw-exception-shape"></a><span data-ttu-id="79227-113">配置引发异常形状</span><span class="sxs-lookup"><span data-stu-id="79227-113">To configure a Throw Exception shape</span></span>  
  
-   <span data-ttu-id="79227-114">在属性窗口中，选择要从引发的可用对象类型**异常对象**下拉列表。</span><span class="sxs-lookup"><span data-stu-id="79227-114">In the Properties window, select an available object type to throw from the **Exception Object** drop-down list.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="79227-115">选择中出现一般异常**引发的异常**形状才**引发的异常**形状在异常处理程序内，并且你想要重新引发当前异常处理程序中捕获的异常。</span><span class="sxs-lookup"><span data-stu-id="79227-115">Select General Exception in the **Throw Exception** shape only if the **Throw Exception** shape is within an exception handler and you want to rethrow the exception caught in the current exception handler.</span></span> <span data-ttu-id="79227-116">你将在编译期间收到错误，如果使用常规异常**引发的异常**在任何其他上下文中的形状。</span><span class="sxs-lookup"><span data-stu-id="79227-116">You will receive an error during the compile if you use General Exception for a **Throw Exception** shape in any other context.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="79227-117">另请参阅</span><span class="sxs-lookup"><span data-stu-id="79227-117">See Also</span></span>  
 [<span data-ttu-id="79227-118">异常</span><span class="sxs-lookup"><span data-stu-id="79227-118">Exceptions</span></span>](../core/exceptions.md)