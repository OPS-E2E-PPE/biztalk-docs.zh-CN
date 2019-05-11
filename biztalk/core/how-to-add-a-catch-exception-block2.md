---
title: 如何添加捕获异常块 2 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- Catch Exception blocks
- exceptions, Catch Exception blocks
ms.assetid: 7c8b6024-e8dc-4417-83f9-bf4032644b91
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: e16fb42f9b8814ab816f64f6cf2b3a8b482fbb58
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65387418"
---
# <a name="how-to-add-a-catch-exception-block"></a><span data-ttu-id="fa871-102">如何添加捕获异常块</span><span class="sxs-lookup"><span data-stu-id="fa871-102">How to Add a Catch Exception Block</span></span>
<span data-ttu-id="fa871-103">**捕获异常**块代表异常处理程序。</span><span class="sxs-lookup"><span data-stu-id="fa871-103">The **Catch Exception** block represents an exception handler.</span></span> <span data-ttu-id="fa871-104">**捕获异常**块附加到的末尾**作用域**形状在业务流程设计器中的。</span><span class="sxs-lookup"><span data-stu-id="fa871-104">**Catch Exception** blocks are attached to the end of a **Scope** shape in Orchestration Designer.</span></span> <span data-ttu-id="fa871-105">可以附加任意数量**捕获异常**块。</span><span class="sxs-lookup"><span data-stu-id="fa871-105">You can attach as many **Catch Exception** blocks as you need.</span></span>  
  
 <span data-ttu-id="fa871-106">您可以将设置异常处理程序来处理不同类型的异常。</span><span class="sxs-lookup"><span data-stu-id="fa871-106">You can set up exception handlers to handle different kinds of exceptions.</span></span> <span data-ttu-id="fa871-107">在每个异常处理程序中，指定异常类型。</span><span class="sxs-lookup"><span data-stu-id="fa871-107">On each exception handler, you specify an exception type.</span></span> <span data-ttu-id="fa871-108">这必须是异常或是从类派生的对象`System`。</span><span class="sxs-lookup"><span data-stu-id="fa871-108">This must be either an exception or an object derived from the class `System`.</span></span> <span data-ttu-id="fa871-109">如果异常引发的异常处理程序中的指定的类型相匹配，将调用该异常处理程序。</span><span class="sxs-lookup"><span data-stu-id="fa871-109">If an exception is thrown that matches the specified type in an exception handler, that exception handler will be called.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="fa871-110">若要将捕获异常块添加到作用域形状，作用域形状的事务类型属性必须设置为**无**或**长期**。</span><span class="sxs-lookup"><span data-stu-id="fa871-110">To add a Catch Exception block to a Scope shape, the Transaction Type property of the Scope shape must be set to **None** or **Long Running**.</span></span>  
  
### <a name="to-add-and-populate-a-catch-exception-block"></a><span data-ttu-id="fa871-111">若要添加和填充捕获异常块</span><span class="sxs-lookup"><span data-stu-id="fa871-111">To add and populate a Catch Exception block</span></span>  
  
1.  <span data-ttu-id="fa871-112">右键单击**作用域**你想要添加的形状**捕获异常**阻止，然后依次**新建异常处理程序**。</span><span class="sxs-lookup"><span data-stu-id="fa871-112">Right-click the **Scope** shape to which you want to add a **Catch Exception** block, and then click **New Exception Handler**.</span></span>  
  
     <span data-ttu-id="fa871-113">一个**捕获异常**块添加到紧跟相关业务流程**作用域**形状。</span><span class="sxs-lookup"><span data-stu-id="fa871-113">A **Catch Exception** block is added to the orchestration immediately following the associated **Scope** shape.</span></span>  
  
2.  <span data-ttu-id="fa871-114">在中**属性**窗口中，指定的属性。</span><span class="sxs-lookup"><span data-stu-id="fa871-114">In the **Properties** window, specify the properties.</span></span>  
  
     <span data-ttu-id="fa871-115">最重要属性是**异常对象类型**; 这是将捕获的消息类型。</span><span class="sxs-lookup"><span data-stu-id="fa871-115">The most important property is the **Exception Object Type**; this is the type of message it will catch.</span></span>  
  
3.  <span data-ttu-id="fa871-116">在中**属性**windows，请在**异常对象类型**列表中，选择**一般异常**。</span><span class="sxs-lookup"><span data-stu-id="fa871-116">In the **Properties** windows, in the **Exception Object Type** list, select  **General Exception**.</span></span>  
  
    |<span data-ttu-id="fa871-117">属性</span><span class="sxs-lookup"><span data-stu-id="fa871-117">Property</span></span>|<span data-ttu-id="fa871-118">Description</span><span class="sxs-lookup"><span data-stu-id="fa871-118">Description</span></span>|  
    |--------------|-----------------|  
    |<span data-ttu-id="fa871-119">**异常对象名称**</span><span class="sxs-lookup"><span data-stu-id="fa871-119">**Exception Object Name**</span></span>|<span data-ttu-id="fa871-120">为指定的异常处理程序捕获的异常对象名称。</span><span class="sxs-lookup"><span data-stu-id="fa871-120">Assigns a name to the exception object caught by the exception handler.</span></span>|  
    |<span data-ttu-id="fa871-121">**异常对象类型**</span><span class="sxs-lookup"><span data-stu-id="fa871-121">**Exception Object Type**</span></span>|<span data-ttu-id="fa871-122">确定对象类型 （从 System.Exception 派生的），将会捕获此异常处理程序。</span><span class="sxs-lookup"><span data-stu-id="fa871-122">Determines the object type (derived from System.Exception) that this exception handler will catch.</span></span>|  
  
4.  <span data-ttu-id="fa871-123">在捕获异常块中，添加形状以创建处理异常进程。</span><span class="sxs-lookup"><span data-stu-id="fa871-123">Inside the Catch Exception block, add shapes to create the process for handling the exception.</span></span>  
  
    1.  <span data-ttu-id="fa871-124">下单击鼠标右键**CatchException** ，然后指向**插入形状**，然后选择**构造消息**。</span><span class="sxs-lookup"><span data-stu-id="fa871-124">Right-click below the **CatchException** and point to **Insert Shape**, and then select **Construct Message**.</span></span>  
  
    2.  <span data-ttu-id="fa871-125">双击**MessageAssignment**以打开文本编辑器并输入消息赋值。</span><span class="sxs-lookup"><span data-stu-id="fa871-125">Double-click inside **MessageAssignment** to open the Text Editor and enter the Message assignment.</span></span>  
  
         <span data-ttu-id="fa871-126">例如，键入 `Message_3 = Test`。</span><span class="sxs-lookup"><span data-stu-id="fa871-126">For example, type `Message_3 = Test`.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="fa871-127">请参阅</span><span class="sxs-lookup"><span data-stu-id="fa871-127">See Also</span></span>  
 <span data-ttu-id="fa871-128">[完成异常消息](../core/completing-the-exception-message4.md) </span><span class="sxs-lookup"><span data-stu-id="fa871-128">[Completing the Exception Message](../core/completing-the-exception-message4.md) </span></span>  
 <span data-ttu-id="fa871-129">[如何添加作用域形状](../core/how-to-add-a-scope-shape4.md) </span><span class="sxs-lookup"><span data-stu-id="fa871-129">[How to Add a Scope Shape](../core/how-to-add-a-scope-shape4.md) </span></span>  
 [<span data-ttu-id="fa871-130">使用 BizTalk Server 的异常处理</span><span class="sxs-lookup"><span data-stu-id="fa871-130">Using BizTalk Server Exception Handling</span></span>](../core/using-biztalk-server-exception-handling4.md)