---
title: "如何添加 Catch 异常 Block3 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- Scope shape [Orchestration Designer], Catch Exception block [Orchestration Designer]
- Catch Exception block [Orchestration Designer]
- Catch Exception block [Orchestration Designer], creating
- Catch Exception block [Orchestration Designer], exception handler
- Catch Exception block [Orchestration Designer], about Catch Exception blocks
- Orchestration Designer, errors
ms.assetid: 63ca4a60-b657-452a-86fd-78968ccf2933
caps.latest.revision: "8"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 1040a27a5e1273d2ad80a722deb421878de36c12
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="how-to-add-a-catch-exception-block"></a><span data-ttu-id="c5183-102">如何添加 Catch 异常块</span><span class="sxs-lookup"><span data-stu-id="c5183-102">How to Add a Catch Exception Block</span></span>
<span data-ttu-id="c5183-103">**捕获异常**块代表一个异常处理程序。</span><span class="sxs-lookup"><span data-stu-id="c5183-103">The **Catch Exception** block represents an exception handler.</span></span> <span data-ttu-id="c5183-104">**捕获异常**块附加到的末尾**作用域**中业务流程设计器形状。</span><span class="sxs-lookup"><span data-stu-id="c5183-104">**Catch Exception** blocks are attached to the end of a **Scope** shape in Orchestration Designer.</span></span> <span data-ttu-id="c5183-105">你可以将作为许多附加**捕获异常**阻止根据你的需要。</span><span class="sxs-lookup"><span data-stu-id="c5183-105">You can attach as many **Catch Exception** blocks as you need.</span></span>  
  
 <span data-ttu-id="c5183-106">你可以设置异常处理程序来处理不同种类的异常。</span><span class="sxs-lookup"><span data-stu-id="c5183-106">You can set up exception handlers to handle different kinds of exceptions.</span></span> <span data-ttu-id="c5183-107">在每个异常处理程序中，您可以指定异常类型，它必须是错误消息或派生自类的对象**System.Exception**。</span><span class="sxs-lookup"><span data-stu-id="c5183-107">On each exception handler, you specify an exception type, which must be either a fault message or an object derived from the class **System.Exception**.</span></span> <span data-ttu-id="c5183-108">如果不指定异常类型，该异常块将被视为常规异常处理程序，并且可以捕获是非派生自的异常**System.Exception**。</span><span class="sxs-lookup"><span data-stu-id="c5183-108">If you do not specify an exception type, the exception block will be treated as a general exception handler, and can catch exceptions that do not derive from **System.Exception**.</span></span>  
  
 <span data-ttu-id="c5183-109">如果出现了符合异常处理程序中的指定类型的异常，便会调用异常处理程序。</span><span class="sxs-lookup"><span data-stu-id="c5183-109">If an exception is thrown that matches the specified type in an exception handler, that exception handler will be called.</span></span> <span data-ttu-id="c5183-110">如果某些其他异常被抛弃，它将由默认异常处理程序处理。</span><span class="sxs-lookup"><span data-stu-id="c5183-110">If some other exception is thrown, it will be handled by the default exception handler.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="c5183-111">若要添加**捕获异常**阻止**作用域**形状，**事务类型**属性**作用域**形状必须设置为**无**或**长时间运行的**。</span><span class="sxs-lookup"><span data-stu-id="c5183-111">To add a **Catch Exception** block to a **Scope** shape, the **Transaction Type** property of the **Scope** shape must be set to **None** or **Long Running**.</span></span>  
  
### <a name="to-add-a-catch-exception-block"></a><span data-ttu-id="c5183-112">添加“捕获异常”块</span><span class="sxs-lookup"><span data-stu-id="c5183-112">To add a Catch Exception block</span></span>  
  
1.  <span data-ttu-id="c5183-113">右键单击**作用域**你想要添加的形状**捕获异常**块，并依次**新异常处理程序**。</span><span class="sxs-lookup"><span data-stu-id="c5183-113">Right-click the **Scope** shape to which you want to add a **Catch Exception** block, and then click **New Exception Handler**.</span></span>  
  
     <span data-ttu-id="c5183-114">A**捕获异常**块添加到紧跟在关联的业务流程**作用域**形状。</span><span class="sxs-lookup"><span data-stu-id="c5183-114">A **Catch Exception** block is added to the orchestration immediately following the associated **Scope** shape.</span></span>  
  
2.  <span data-ttu-id="c5183-115">在“属性”窗口中，指定以下属性：</span><span class="sxs-lookup"><span data-stu-id="c5183-115">In the Properties window, specify the following properties:</span></span>  
  
    |<span data-ttu-id="c5183-116">属性</span><span class="sxs-lookup"><span data-stu-id="c5183-116">Property</span></span>|<span data-ttu-id="c5183-117">Description</span><span class="sxs-lookup"><span data-stu-id="c5183-117">Description</span></span>|  
    |--------------|-----------------|  
    |<span data-ttu-id="c5183-118">异常对象名称</span><span class="sxs-lookup"><span data-stu-id="c5183-118">Exception Object Name</span></span>|<span data-ttu-id="c5183-119">为异常处理程序捕获的异常对象中指定一个名称。</span><span class="sxs-lookup"><span data-stu-id="c5183-119">Assigns a name to the exception object caught by the exception handler.</span></span>|  
    |<span data-ttu-id="c5183-120">异常对象类型</span><span class="sxs-lookup"><span data-stu-id="c5183-120">Exception Object Type</span></span>|<span data-ttu-id="c5183-121">确定此异常处理程序将要捕获的从 System.Exception 派生的对象类型。</span><span class="sxs-lookup"><span data-stu-id="c5183-121">Determines the object type (derived from System.Exception) that this exception handler will catch.</span></span>|  
  
3.  <span data-ttu-id="c5183-122">内部**捕获异常**块中，添加形状来创建用于处理异常的进程。</span><span class="sxs-lookup"><span data-stu-id="c5183-122">Inside the **Catch Exception** block, add shapes to create the process for handling the exception.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="c5183-123">如果指定一般异常**异常**对象类型，**捕获异常**块将截获任何异常，包括那些不派生自**System.Exception**.</span><span class="sxs-lookup"><span data-stu-id="c5183-123">If you specify General Exception as the **Exception** object type, the **Catch Exception** block will intercept any exception, including those that are not derived from **System.Exception**.</span></span> <span data-ttu-id="c5183-124">在这种情况下，您将没有异常对象的访问权限。</span><span class="sxs-lookup"><span data-stu-id="c5183-124">In such a case, you will not have access to an exception object.</span></span> <span data-ttu-id="c5183-125">在此块中，如果你使用**引发的异常**形状使用常规异常类型中，你将会有效地重新引发捕获的异常。</span><span class="sxs-lookup"><span data-stu-id="c5183-125">Within this block, if you use a **Throw Exception** shape with the General Exception type, you will be effectively rethrowing the caught exception.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c5183-126">另请参阅</span><span class="sxs-lookup"><span data-stu-id="c5183-126">See Also</span></span>  
 [<span data-ttu-id="c5183-127">异常</span><span class="sxs-lookup"><span data-stu-id="c5183-127">Exceptions</span></span>](../core/exceptions.md)