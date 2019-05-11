---
title: 如何添加捕获异常 Block3 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- Scope shape [Orchestration Designer], Catch Exception block [Orchestration Designer]
- Catch Exception block [Orchestration Designer]
- Catch Exception block [Orchestration Designer], creating
- Catch Exception block [Orchestration Designer], exception handler
- Catch Exception block [Orchestration Designer], about Catch Exception blocks
- Orchestration Designer, errors
ms.assetid: 63ca4a60-b657-452a-86fd-78968ccf2933
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 35746e0bc8e9bbadb8deffb5287943a95fd77e77
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65343948"
---
# <a name="how-to-add-a-catch-exception-block"></a><span data-ttu-id="eb1ce-102">如何添加捕获异常块</span><span class="sxs-lookup"><span data-stu-id="eb1ce-102">How to Add a Catch Exception Block</span></span>
<span data-ttu-id="eb1ce-103">**捕获异常**块代表异常处理程序。</span><span class="sxs-lookup"><span data-stu-id="eb1ce-103">The **Catch Exception** block represents an exception handler.</span></span> <span data-ttu-id="eb1ce-104">**捕获异常**块附加到的末尾**作用域**形状在业务流程设计器中的。</span><span class="sxs-lookup"><span data-stu-id="eb1ce-104">**Catch Exception** blocks are attached to the end of a **Scope** shape in Orchestration Designer.</span></span> <span data-ttu-id="eb1ce-105">可以附加任意数量**捕获异常**块。</span><span class="sxs-lookup"><span data-stu-id="eb1ce-105">You can attach as many **Catch Exception** blocks as you need.</span></span>  
  
 <span data-ttu-id="eb1ce-106">您可以将设置异常处理程序来处理不同类型的异常。</span><span class="sxs-lookup"><span data-stu-id="eb1ce-106">You can set up exception handlers to handle different kinds of exceptions.</span></span> <span data-ttu-id="eb1ce-107">在每个异常处理程序中，指定一个异常类型，该错误消息或是从类派生的对象必须是类型**System.Exception**。</span><span class="sxs-lookup"><span data-stu-id="eb1ce-107">On each exception handler, you specify an exception type, which must be either a fault message or an object derived from the class **System.Exception**.</span></span> <span data-ttu-id="eb1ce-108">如果不指定异常类型，异常块将被视为一般异常处理程序，并且可以捕获不是从派生的异常**System.Exception**。</span><span class="sxs-lookup"><span data-stu-id="eb1ce-108">If you do not specify an exception type, the exception block will be treated as a general exception handler, and can catch exceptions that do not derive from **System.Exception**.</span></span>  
  
 <span data-ttu-id="eb1ce-109">如果异常引发的异常处理程序中的指定的类型相匹配，将调用该异常处理程序。</span><span class="sxs-lookup"><span data-stu-id="eb1ce-109">If an exception is thrown that matches the specified type in an exception handler, that exception handler will be called.</span></span> <span data-ttu-id="eb1ce-110">如果引发了某些其他异常，它将由默认异常处理程序处理。</span><span class="sxs-lookup"><span data-stu-id="eb1ce-110">If some other exception is thrown, it will be handled by the default exception handler.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="eb1ce-111">若要添加**捕获异常**阻止**作用域**形状，**事务类型**属性的**范围**形状必须设置为**None**或**长时间运行的**。</span><span class="sxs-lookup"><span data-stu-id="eb1ce-111">To add a **Catch Exception** block to a **Scope** shape, the **Transaction Type** property of the **Scope** shape must be set to **None** or **Long Running**.</span></span>  
  
### <a name="to-add-a-catch-exception-block"></a><span data-ttu-id="eb1ce-112">若要添加捕获异常块</span><span class="sxs-lookup"><span data-stu-id="eb1ce-112">To add a Catch Exception block</span></span>  
  
1.  <span data-ttu-id="eb1ce-113">右键单击**作用域**你想要添加的形状**捕获异常**阻止，然后依次**新建异常处理程序**。</span><span class="sxs-lookup"><span data-stu-id="eb1ce-113">Right-click the **Scope** shape to which you want to add a **Catch Exception** block, and then click **New Exception Handler**.</span></span>  
  
     <span data-ttu-id="eb1ce-114">一个**捕获异常**块添加到紧跟相关业务流程**作用域**形状。</span><span class="sxs-lookup"><span data-stu-id="eb1ce-114">A **Catch Exception** block is added to the orchestration immediately following the associated **Scope** shape.</span></span>  
  
2.  <span data-ttu-id="eb1ce-115">在属性窗口中，指定以下属性：</span><span class="sxs-lookup"><span data-stu-id="eb1ce-115">In the Properties window, specify the following properties:</span></span>  
  
    |<span data-ttu-id="eb1ce-116">属性</span><span class="sxs-lookup"><span data-stu-id="eb1ce-116">Property</span></span>|<span data-ttu-id="eb1ce-117">Description</span><span class="sxs-lookup"><span data-stu-id="eb1ce-117">Description</span></span>|  
    |--------------|-----------------|  
    |<span data-ttu-id="eb1ce-118">异常对象名称</span><span class="sxs-lookup"><span data-stu-id="eb1ce-118">Exception Object Name</span></span>|<span data-ttu-id="eb1ce-119">为指定的异常处理程序捕获的异常对象名称。</span><span class="sxs-lookup"><span data-stu-id="eb1ce-119">Assigns a name to the exception object caught by the exception handler.</span></span>|  
    |<span data-ttu-id="eb1ce-120">异常对象类型</span><span class="sxs-lookup"><span data-stu-id="eb1ce-120">Exception Object Type</span></span>|<span data-ttu-id="eb1ce-121">确定对象类型 （从 System.Exception 派生的），将会捕获此异常处理程序。</span><span class="sxs-lookup"><span data-stu-id="eb1ce-121">Determines the object type (derived from System.Exception) that this exception handler will catch.</span></span>|  
  
3.  <span data-ttu-id="eb1ce-122">内部**捕获异常**块中，添加形状以创建处理异常进程。</span><span class="sxs-lookup"><span data-stu-id="eb1ce-122">Inside the **Catch Exception** block, add shapes to create the process for handling the exception.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="eb1ce-123">如果指定为常规异常**异常**对象类型，**捕获异常**块将会截获所有异常，包括那些不派生自**System.Exception**.</span><span class="sxs-lookup"><span data-stu-id="eb1ce-123">If you specify General Exception as the **Exception** object type, the **Catch Exception** block will intercept any exception, including those that are not derived from **System.Exception**.</span></span> <span data-ttu-id="eb1ce-124">在这种情况下，您将没有异常对象的访问权限。</span><span class="sxs-lookup"><span data-stu-id="eb1ce-124">In such a case, you will not have access to an exception object.</span></span> <span data-ttu-id="eb1ce-125">在此块中，如果您使用**引发异常**形状与常规异常类型，您将会重新引发已捕获的异常。</span><span class="sxs-lookup"><span data-stu-id="eb1ce-125">Within this block, if you use a **Throw Exception** shape with the General Exception type, you will be effectively rethrowing the caught exception.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="eb1ce-126">请参阅</span><span class="sxs-lookup"><span data-stu-id="eb1ce-126">See Also</span></span>  
 [<span data-ttu-id="eb1ce-127">异常</span><span class="sxs-lookup"><span data-stu-id="eb1ce-127">Exceptions</span></span>](../core/exceptions.md)