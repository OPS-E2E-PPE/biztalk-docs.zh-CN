---
title: 如何添加捕获异常块 1 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- exceptions, adding Catch Exception block
- Catch Exception blocks, adding
- exception handling, Catch Exception blocks
ms.assetid: 8e4b264b-b3b0-4d83-81df-a14dc2ddeea2
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 34e5ebf17db715175a532f0ec0863a506b9e3557
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65344011"
---
# <a name="how-to-add-a-catch-exception-block"></a><span data-ttu-id="0e424-102">如何添加捕获异常块</span><span class="sxs-lookup"><span data-stu-id="0e424-102">How to Add a Catch Exception Block</span></span>
<span data-ttu-id="0e424-103">**捕获异常**块代表异常处理程序。</span><span class="sxs-lookup"><span data-stu-id="0e424-103">The **Catch Exception** block represents an exception handler.</span></span> <span data-ttu-id="0e424-104">**捕获异常**块附加到的末尾**作用域**形状在业务流程设计器中的。</span><span class="sxs-lookup"><span data-stu-id="0e424-104">**Catch Exception** blocks are attached to the end of a **Scope** shape in Orchestration Designer.</span></span> <span data-ttu-id="0e424-105">可以附加任意数量**捕获异常**块。</span><span class="sxs-lookup"><span data-stu-id="0e424-105">You can attach as many **Catch Exception** blocks as you need.</span></span>  
  
 <span data-ttu-id="0e424-106">您可以将设置异常处理程序来处理不同类型的异常。</span><span class="sxs-lookup"><span data-stu-id="0e424-106">You can set up exception handlers to handle different kinds of exceptions.</span></span> <span data-ttu-id="0e424-107">在每个异常处理程序中，指定一个异常类型，它是异常或是从类派生的对象必须是`System`。</span><span class="sxs-lookup"><span data-stu-id="0e424-107">On each exception handler, you specify an exception type, which must be either an exception or an object derived from the class `System`.</span></span> <span data-ttu-id="0e424-108">如果异常引发的异常处理程序中的指定的类型相匹配，将调用该异常处理程序。</span><span class="sxs-lookup"><span data-stu-id="0e424-108">If an exception is thrown that matches the specified type in an exception handler, that exception handler will be called.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="0e424-109">若要添加**捕获异常**阻止**作用域**形状的事务类型属性**作用域**形状必须设置为**无**或**长时间运行的**。</span><span class="sxs-lookup"><span data-stu-id="0e424-109">To add a **Catch Exception** block to a **Scope** shape, the Transaction Type property of the **Scope** shape must be set to **None** or **Long Running**.</span></span>  
  
### <a name="to-add-and-populate-a-catch-exception-block"></a><span data-ttu-id="0e424-110">若要添加和填充捕获异常块</span><span class="sxs-lookup"><span data-stu-id="0e424-110">To add and populate a Catch Exception block</span></span>  
  
1.  <span data-ttu-id="0e424-111">右键单击**作用域**你想要添加的形状**捕获异常**阻止，然后依次**新建异常处理程序**。</span><span class="sxs-lookup"><span data-stu-id="0e424-111">Right-click the **Scope** shape to which you want to add a **Catch Exception** block, and then click **New Exception Handler**.</span></span>  
  
     <span data-ttu-id="0e424-112">一个**捕获异常**块添加到紧跟相关业务流程**作用域**形状。</span><span class="sxs-lookup"><span data-stu-id="0e424-112">A **Catch Exception** block is added to the orchestration immediately following the associated **Scope** shape.</span></span>  
  
2.  <span data-ttu-id="0e424-113">在中**属性**窗口中，指定的属性。</span><span class="sxs-lookup"><span data-stu-id="0e424-113">In the **Properties** window, specify the properties.</span></span>  
  
     <span data-ttu-id="0e424-114">最重要属性是异常对象类型;这是消息的将捕获类型。</span><span class="sxs-lookup"><span data-stu-id="0e424-114">The most important property is the Exception Object Type; this is the type of message it will catch.</span></span>  
  
    |<span data-ttu-id="0e424-115">属性</span><span class="sxs-lookup"><span data-stu-id="0e424-115">Property</span></span>|<span data-ttu-id="0e424-116">Description</span><span class="sxs-lookup"><span data-stu-id="0e424-116">Description</span></span>|  
    |--------------|-----------------|  
    |<span data-ttu-id="0e424-117">异常对象名称</span><span class="sxs-lookup"><span data-stu-id="0e424-117">Exception Object Name</span></span>|<span data-ttu-id="0e424-118">为指定的异常处理程序捕获的异常对象名称。</span><span class="sxs-lookup"><span data-stu-id="0e424-118">Assigns a name to the exception object caught by the exception handler.</span></span>|  
    |<span data-ttu-id="0e424-119">异常对象类型</span><span class="sxs-lookup"><span data-stu-id="0e424-119">Exception Object Type</span></span>|<span data-ttu-id="0e424-120">确定对象类型 （从 System.Exception 派生的），将会捕获此异常处理程序。</span><span class="sxs-lookup"><span data-stu-id="0e424-120">Determines the object type (derived from System.Exception) that this exception handler will catch.</span></span>|  
  
3.  <span data-ttu-id="0e424-121">在中**属性**窗口，请在**异常对象类型**列表中，选择**一般异常**。</span><span class="sxs-lookup"><span data-stu-id="0e424-121">In the **Properties** window, in the **Exception Object Type** list, select the **General Exception**.</span></span>  
  
4.  <span data-ttu-id="0e424-122">内部**捕获异常**块中，添加形状以创建处理异常进程。</span><span class="sxs-lookup"><span data-stu-id="0e424-122">Inside the **Catch Exception** block, add shapes to create the process for handling the exception.</span></span>  
  
5.  <span data-ttu-id="0e424-123">下单击鼠标右键**捕获异常**块中，依次指向**插入形状**，然后选择**构造消息**。</span><span class="sxs-lookup"><span data-stu-id="0e424-123">Right-click below the **Catch Exception** block, point to **Insert Shape**, and then select **Construct Message**.</span></span>  
  
6.  <span data-ttu-id="0e424-124">双击**MessageAssignment**以激活文本编辑器并输入消息赋值。</span><span class="sxs-lookup"><span data-stu-id="0e424-124">Double-click inside **MessageAssignment** to activate the Text Editor and enter the Message assignment.</span></span>  
  
     <span data-ttu-id="0e424-125">例如，键入 `Message_3 = Test`。</span><span class="sxs-lookup"><span data-stu-id="0e424-125">For example, type `Message_3 = Test`.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0e424-126">请参阅</span><span class="sxs-lookup"><span data-stu-id="0e424-126">See Also</span></span>  
 <span data-ttu-id="0e424-127">[完成异常消息](../core/completing-the-exception-message5.md) </span><span class="sxs-lookup"><span data-stu-id="0e424-127">[Completing the Exception Message](../core/completing-the-exception-message5.md) </span></span>  
 <span data-ttu-id="0e424-128">[如何添加作用域形状](../core/how-to-add-a-scope-shape2.md) </span><span class="sxs-lookup"><span data-stu-id="0e424-128">[How to Add a Scope Shape](../core/how-to-add-a-scope-shape2.md) </span></span>  
 [<span data-ttu-id="0e424-129">使用 BizTalk Server 的异常处理</span><span class="sxs-lookup"><span data-stu-id="0e424-129">Using BizTalk Server Exception Handling</span></span>](../core/using-biztalk-server-exception-handling3.md)