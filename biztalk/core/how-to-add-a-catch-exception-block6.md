---
title: 如何添加捕获异常 Block6 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- exception handling, Catch Exception block
- Catch Exception blocks
- exceptions, Catch Exception block
ms.assetid: 404312dd-773b-44fe-8b65-7de3d0af2f79
caps.latest.revision: 11
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: a84b37953e05c83beff6853cd7143c7db2a36036
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65387375"
---
# <a name="how-to-add-a-catch-exception-block"></a><span data-ttu-id="5d4e7-102">如何添加捕获异常块</span><span class="sxs-lookup"><span data-stu-id="5d4e7-102">How to Add a Catch Exception Block</span></span>
<span data-ttu-id="5d4e7-103">**捕获异常**块代表异常处理程序。</span><span class="sxs-lookup"><span data-stu-id="5d4e7-103">The **Catch Exception** block represents an exception handler.</span></span> <span data-ttu-id="5d4e7-104">**捕获异常**块附加到的末尾**作用域**形状在业务流程设计器中的。</span><span class="sxs-lookup"><span data-stu-id="5d4e7-104">**Catch Exception** blocks are attached to the end of a **Scope** shape in Orchestration Designer.</span></span> <span data-ttu-id="5d4e7-105">在 BizTalk Server 中，你可以附加任意数量**捕获异常**块。</span><span class="sxs-lookup"><span data-stu-id="5d4e7-105">In BizTalk Server, you can attach as many **Catch Exception** blocks as you need.</span></span>  
  
 <span data-ttu-id="5d4e7-106">您可以将设置异常处理程序来处理不同类型的异常。</span><span class="sxs-lookup"><span data-stu-id="5d4e7-106">You can set up exception handlers to handle different kinds of exceptions.</span></span> <span data-ttu-id="5d4e7-107">在每个异常处理程序中，指定一个异常类型，该错误消息或是从类派生的对象必须是类型`System.Exception`。</span><span class="sxs-lookup"><span data-stu-id="5d4e7-107">On each exception handler, you specify an exception type, which must be either a fault message or an object derived from the class `System.Exception`.</span></span> <span data-ttu-id="5d4e7-108">如果不指定异常类型，异常块视为一般异常处理程序，并且可以捕获不是从派生的异常`System.Exception`。</span><span class="sxs-lookup"><span data-stu-id="5d4e7-108">If you do not specify an exception type, the exception block is treated as a general exception handler, and can catch exceptions that do not derive from `System.Exception`.</span></span>  
  
 <span data-ttu-id="5d4e7-109">如果引发异常，异常处理程序中的指定的类型相匹配，则调用该异常处理程序。</span><span class="sxs-lookup"><span data-stu-id="5d4e7-109">If an exception is thrown that matches the specified type in an exception handler, that exception handler is called.</span></span> <span data-ttu-id="5d4e7-110">如果引发了某些其他异常，则进行处理的默认异常处理程序。</span><span class="sxs-lookup"><span data-stu-id="5d4e7-110">If some other exception is thrown, it is handled by the default exception handler.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="5d4e7-111">若要添加**捕获异常**阻止**作用域**形状，**事务类型**属性的**范围**形状必须设置为无或长正在运行。</span><span class="sxs-lookup"><span data-stu-id="5d4e7-111">To add a **Catch Exception** block to a **Scope** shape, the **Transaction Type** property of the **Scope** shape must be set to None or Long Running.</span></span>  
  
## <a name="adding-and-populating-a-catch-exception-block"></a><span data-ttu-id="5d4e7-112">添加和填充捕获异常块</span><span class="sxs-lookup"><span data-stu-id="5d4e7-112">Adding and Populating a Catch Exception Block</span></span>  
  
#### <a name="to-add-and-populate-a-catch-exception-block"></a><span data-ttu-id="5d4e7-113">若要添加和填充捕获异常块</span><span class="sxs-lookup"><span data-stu-id="5d4e7-113">To add and populate a catch exception block</span></span>  
  
1.  <span data-ttu-id="5d4e7-114">右键单击**作用域**你想要添加的形状**捕获异常**块，然后单击**新建异常处理程序**。</span><span class="sxs-lookup"><span data-stu-id="5d4e7-114">Right-click the **Scope** shape that you want to add a **Catch Exception** block to, and then click **New Exception Handler**.</span></span>  
  
     <span data-ttu-id="5d4e7-115">一个**捕获异常**块添加到紧跟相关业务流程**作用域**形状。</span><span class="sxs-lookup"><span data-stu-id="5d4e7-115">A **Catch Exception** block is added to the orchestration immediately following the associated **Scope** shape.</span></span>  
  
2.  <span data-ttu-id="5d4e7-116">在中**属性**窗口中，指定的属性。</span><span class="sxs-lookup"><span data-stu-id="5d4e7-116">In the **Properties** window, specify the properties.</span></span> <span data-ttu-id="5d4e7-117">最重要属性是**异常对象类型**因为这是将捕获的消息类型。</span><span class="sxs-lookup"><span data-stu-id="5d4e7-117">The most important property is the **Exception Object Type** because this is the type of message it will catch.</span></span>  
  
    |<span data-ttu-id="5d4e7-118">属性</span><span class="sxs-lookup"><span data-stu-id="5d4e7-118">Property</span></span>|<span data-ttu-id="5d4e7-119">Description</span><span class="sxs-lookup"><span data-stu-id="5d4e7-119">Description</span></span>|  
    |--------------|-----------------|  
    |<span data-ttu-id="5d4e7-120">异常对象名称</span><span class="sxs-lookup"><span data-stu-id="5d4e7-120">Exception Object Name</span></span>|<span data-ttu-id="5d4e7-121">为指定的异常处理程序捕获的异常对象名称。</span><span class="sxs-lookup"><span data-stu-id="5d4e7-121">Assigns a name to the exception object caught by the exception handler.</span></span>|  
    |<span data-ttu-id="5d4e7-122">异常对象类型</span><span class="sxs-lookup"><span data-stu-id="5d4e7-122">Exception Object Type</span></span>|<span data-ttu-id="5d4e7-123">确定对象类型 （从 System.Exception 派生的），将会捕获此异常处理程序。</span><span class="sxs-lookup"><span data-stu-id="5d4e7-123">Determines the object type (derived from System.Exception) that this exception handler will catch.</span></span>|  
  
3.  <span data-ttu-id="5d4e7-124">在中**属性**窗口中，单击**异常对象类型**列表。</span><span class="sxs-lookup"><span data-stu-id="5d4e7-124">In the **Properties** window, click the **Exception Object Type** list.</span></span> <span data-ttu-id="5d4e7-125">此列表包含常规适配器引发的异常。</span><span class="sxs-lookup"><span data-stu-id="5d4e7-125">This list contains the general exception that is thrown by the adapter.</span></span>  
  
     <span data-ttu-id="5d4e7-126">名称显示为错误设置中的端口到后端系统，例如，ps。SQLExecute.Fault。</span><span class="sxs-lookup"><span data-stu-id="5d4e7-126">The name appears as the fault you set in the port to the back-end system, for example, PS.SQLExecute.Fault.</span></span>  
  
4.  <span data-ttu-id="5d4e7-127">为添加名称**异常对象名称**，例如，测试。</span><span class="sxs-lookup"><span data-stu-id="5d4e7-127">Add a name for the **Exception Object Name**, for example, Test.</span></span>  
  
     <span data-ttu-id="5d4e7-128">内部**捕获异常**块中，添加形状以创建处理异常进程。</span><span class="sxs-lookup"><span data-stu-id="5d4e7-128">Inside the **Catch Exception** block, add shapes to create the process for handling the exception.</span></span>  
  
    1.  <span data-ttu-id="5d4e7-129">下单击鼠标右键**捕获异常**，依次指向**插入形状**，然后选择**构造消息**。</span><span class="sxs-lookup"><span data-stu-id="5d4e7-129">Right-click below the **Catch Exception**, point to **Insert Shape**, and select **Construct Message**.</span></span>  
  
         <span data-ttu-id="5d4e7-130">![](../core/media/siebeladapter-20-exceptionhandling-constructmessage.gif "SiebelAdapter_20_ExceptionHandling_ConstructMessage")</span><span class="sxs-lookup"><span data-stu-id="5d4e7-130">![](../core/media/siebeladapter-20-exceptionhandling-constructmessage.gif "SiebelAdapter_20_ExceptionHandling_ConstructMessage")</span></span>  
  
    2.  <span data-ttu-id="5d4e7-131">双击**MessageAssignment**以打开文本编辑器并输入消息赋值。</span><span class="sxs-lookup"><span data-stu-id="5d4e7-131">Double-click inside **MessageAssignment** to open the Text Editor and enter the Message assignment.</span></span>  
  
         <span data-ttu-id="5d4e7-132">输入中设置的名称**异常对象名称**从**捕获异常**，并为该错误创建的新消息。</span><span class="sxs-lookup"><span data-stu-id="5d4e7-132">Enter the name that you set in the **Exception Object Name** from the **Catch Exception**, and the new message you created for the fault.</span></span>  
  
         <span data-ttu-id="5d4e7-133">例如，键入 `Message_3 = Test`。</span><span class="sxs-lookup"><span data-stu-id="5d4e7-133">For example, type `Message_3 = Test`.</span></span>  
  
         <span data-ttu-id="5d4e7-134">![](../core/media/siebeladapter-21-exceptionhandling-message3test.gif "SiebelAdapter_21_ExceptionHandling_Message3Test")</span><span class="sxs-lookup"><span data-stu-id="5d4e7-134">![](../core/media/siebeladapter-21-exceptionhandling-message3test.gif "SiebelAdapter_21_ExceptionHandling_Message3Test")</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5d4e7-135">请参阅</span><span class="sxs-lookup"><span data-stu-id="5d4e7-135">See Also</span></span>  
 <span data-ttu-id="5d4e7-136">[如何添加作用域形状](../core/how-to-add-a-scope-shape1.md) </span><span class="sxs-lookup"><span data-stu-id="5d4e7-136">[How to Add a Scope Shape](../core/how-to-add-a-scope-shape1.md) </span></span>  
 <span data-ttu-id="5d4e7-137">[完成异常消息](../core/completing-the-exception-message3.md) </span><span class="sxs-lookup"><span data-stu-id="5d4e7-137">[Completing the Exception Message](../core/completing-the-exception-message3.md) </span></span>  
 [<span data-ttu-id="5d4e7-138">使用 BizTalk Server 的异常处理</span><span class="sxs-lookup"><span data-stu-id="5d4e7-138">Using BizTalk Server Exception Handling</span></span>](../core/using-biztalk-server-exception-handling2.md)