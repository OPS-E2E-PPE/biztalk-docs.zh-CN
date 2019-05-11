---
title: 如何配置引发异常形状 |Microsoft Docs
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
ms.openlocfilehash: ee24b5a6fab36e7a865f26a04e8c040141835735
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65385939"
---
# <a name="how-to-configure-the-throw-exception-shape"></a><span data-ttu-id="cbf0e-102">如何配置引发异常形状</span><span class="sxs-lookup"><span data-stu-id="cbf0e-102">How to Configure the Throw Exception Shape</span></span>
<span data-ttu-id="cbf0e-103">您可以显式引发异常在业务流程中使用**引发异常**形状。</span><span class="sxs-lookup"><span data-stu-id="cbf0e-103">You can explicitly throw exceptions in an orchestration by using the **Throw Exception** shape.</span></span> <span data-ttu-id="cbf0e-104">时引发异常，运行时引擎将搜索的最接近的异常处理程序可以处理所引发异常的类型。</span><span class="sxs-lookup"><span data-stu-id="cbf0e-104">When the throw is performed, the runtime engine will search for the nearest exception handler that can handle the type of exception being thrown.</span></span>  
  
 <span data-ttu-id="cbf0e-105">首先，当前业务流程中搜索所封闭范围，并以找到相应的处理程序已引发的异常的类型被视为作用域的相关联的异常处理程序。</span><span class="sxs-lookup"><span data-stu-id="cbf0e-105">First, the current orchestration is searched for an enclosing scope, and the associated exception handlers of the scope are considered in order to locate the appropriate handler for the type of exception that has been thrown.</span></span>  
  
 <span data-ttu-id="cbf0e-106">如果不找到任何适当的异常处理程序，则对当前业务流程的调用点的作用域搜索调用当前业务流程的业务流程。</span><span class="sxs-lookup"><span data-stu-id="cbf0e-106">If no appropriate exception handler is found, the orchestration that called the current orchestration is searched for a scope that encloses the point of the call to the current orchestration.</span></span> <span data-ttu-id="cbf0e-107">此搜索继续，直到找到异常处理程序可以处理当前异常。</span><span class="sxs-lookup"><span data-stu-id="cbf0e-107">This search continues until an exception handler is found that can handle the current exception.</span></span>  
  
 <span data-ttu-id="cbf0e-108">是的与相同的类的异常类或基类所引发的异常的运行时类型的异常的完全匹配项。</span><span class="sxs-lookup"><span data-stu-id="cbf0e-108">An exact match for the exception is an exception class that is of the same class as, or a base class of, the run-time type of the exception being thrown.</span></span>  
  
 <span data-ttu-id="cbf0e-109">找到匹配的异常处理程序后，控制被转到异常处理程序的第一个语句。</span><span class="sxs-lookup"><span data-stu-id="cbf0e-109">After a matching exception handler is found, control is transferred to the first statement of the exception handler.</span></span>  
  
 <span data-ttu-id="cbf0e-110">如果搜索匹配的异常处理程序失败，业务流程将停止。</span><span class="sxs-lookup"><span data-stu-id="cbf0e-110">If the search for matching exception handlers fails, the orchestration halts.</span></span> <span data-ttu-id="cbf0e-111">事务可以帮助您这种情况影响降至最低。</span><span class="sxs-lookup"><span data-stu-id="cbf0e-111">Transactions can help you minimize the impact of such an occurrence.</span></span>  
  
## <a name="procedure"></a><span data-ttu-id="cbf0e-112">过程</span><span class="sxs-lookup"><span data-stu-id="cbf0e-112">Procedure</span></span>  
  
#### <a name="to-configure-a-throw-exception-shape"></a><span data-ttu-id="cbf0e-113">若要配置引发异常形状</span><span class="sxs-lookup"><span data-stu-id="cbf0e-113">To configure a Throw Exception shape</span></span>  
  
-   <span data-ttu-id="cbf0e-114">在属性窗口中，选择要从引发的可用对象类型**异常对象**下拉列表。</span><span class="sxs-lookup"><span data-stu-id="cbf0e-114">In the Properties window, select an available object type to throw from the **Exception Object** drop-down list.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="cbf0e-115">选择中的常规异常**引发异常**形状仅当**引发异常**形状在异常处理程序内，并且你想要重新引发当前异常处理程序中捕获到异常。</span><span class="sxs-lookup"><span data-stu-id="cbf0e-115">Select General Exception in the **Throw Exception** shape only if the **Throw Exception** shape is within an exception handler and you want to rethrow the exception caught in the current exception handler.</span></span> <span data-ttu-id="cbf0e-116">你将在编译期间收到错误，如果使用的一般异常**引发异常**在任何其他上下文中的形状。</span><span class="sxs-lookup"><span data-stu-id="cbf0e-116">You will receive an error during the compile if you use General Exception for a **Throw Exception** shape in any other context.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="cbf0e-117">请参阅</span><span class="sxs-lookup"><span data-stu-id="cbf0e-117">See Also</span></span>  
 [<span data-ttu-id="cbf0e-118">异常</span><span class="sxs-lookup"><span data-stu-id="cbf0e-118">Exceptions</span></span>](../core/exceptions.md)