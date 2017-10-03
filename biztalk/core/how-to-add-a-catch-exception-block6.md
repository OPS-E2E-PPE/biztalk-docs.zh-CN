---
title: "如何添加 Catch 异常 Block6 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- exception handling, Catch Exception block
- Catch Exception blocks
- exceptions, Catch Exception block
ms.assetid: 404312dd-773b-44fe-8b65-7de3d0af2f79
caps.latest.revision: "11"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: e4be60ddbe45ef4b4f293d7959dc774254e7cd3c
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="how-to-add-a-catch-exception-block"></a><span data-ttu-id="25a38-102">如何添加 Catch 异常块</span><span class="sxs-lookup"><span data-stu-id="25a38-102">How to Add a Catch Exception Block</span></span>
<span data-ttu-id="25a38-103">**捕获异常**块代表一个异常处理程序。</span><span class="sxs-lookup"><span data-stu-id="25a38-103">The **Catch Exception** block represents an exception handler.</span></span> <span data-ttu-id="25a38-104">**捕获异常**块附加到的末尾**作用域**中业务流程设计器形状。</span><span class="sxs-lookup"><span data-stu-id="25a38-104">**Catch Exception** blocks are attached to the end of a **Scope** shape in Orchestration Designer.</span></span> <span data-ttu-id="25a38-105">在 BizTalk Server 中，你可以将作为附加许多**捕获异常**阻止根据你的需要。</span><span class="sxs-lookup"><span data-stu-id="25a38-105">In BizTalk Server, you can attach as many **Catch Exception** blocks as you need.</span></span>  
  
 <span data-ttu-id="25a38-106">你可以设置异常处理程序来处理不同种类的异常。</span><span class="sxs-lookup"><span data-stu-id="25a38-106">You can set up exception handlers to handle different kinds of exceptions.</span></span> <span data-ttu-id="25a38-107">对每个异常处理程序，您应指定一个异常类型，该类型必须是错误消息或是从类 `System.Exception` 派生的对象。</span><span class="sxs-lookup"><span data-stu-id="25a38-107">On each exception handler, you specify an exception type, which must be either a fault message or an object derived from the class `System.Exception`.</span></span> <span data-ttu-id="25a38-108">如果不指定异常类型，异常块将会被视为一般异常处理程序，可以捕获不是从 `System.Exception` 派生的异常。</span><span class="sxs-lookup"><span data-stu-id="25a38-108">If you do not specify an exception type, the exception block is treated as a general exception handler, and can catch exceptions that do not derive from `System.Exception`.</span></span>  
  
 <span data-ttu-id="25a38-109">如果将引发异常，异常处理程序中的指定的类型相匹配，则调用该异常处理程序。</span><span class="sxs-lookup"><span data-stu-id="25a38-109">If an exception is thrown that matches the specified type in an exception handler, that exception handler is called.</span></span> <span data-ttu-id="25a38-110">如果某些其他异常被抛弃，它是由默认异常处理程序中进行处理。</span><span class="sxs-lookup"><span data-stu-id="25a38-110">If some other exception is thrown, it is handled by the default exception handler.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="25a38-111">若要添加**捕获异常**阻止**作用域**形状，**事务类型**属性**作用域**形状必须设置为无或长运行。</span><span class="sxs-lookup"><span data-stu-id="25a38-111">To add a **Catch Exception** block to a **Scope** shape, the **Transaction Type** property of the **Scope** shape must be set to None or Long Running.</span></span>  
  
## <a name="adding-and-populating-a-catch-exception-block"></a><span data-ttu-id="25a38-112">添加和填充 Catch 异常块</span><span class="sxs-lookup"><span data-stu-id="25a38-112">Adding and Populating a Catch Exception Block</span></span>  
  
#### <a name="to-add-and-populate-a-catch-exception-block"></a><span data-ttu-id="25a38-113">若要添加并填充 catch 异常块</span><span class="sxs-lookup"><span data-stu-id="25a38-113">To add and populate a catch exception block</span></span>  
  
1.  <span data-ttu-id="25a38-114">右键单击**作用域**你想要添加的形状**捕获异常**阻止，并依次**新异常处理程序**。</span><span class="sxs-lookup"><span data-stu-id="25a38-114">Right-click the **Scope** shape that you want to add a **Catch Exception** block to, and then click **New Exception Handler**.</span></span>  
  
     <span data-ttu-id="25a38-115">A**捕获异常**块添加到紧跟在关联的业务流程**作用域**形状。</span><span class="sxs-lookup"><span data-stu-id="25a38-115">A **Catch Exception** block is added to the orchestration immediately following the associated **Scope** shape.</span></span>  
  
2.  <span data-ttu-id="25a38-116">在**属性**窗口中，指定的属性。</span><span class="sxs-lookup"><span data-stu-id="25a38-116">In the **Properties** window, specify the properties.</span></span> <span data-ttu-id="25a38-117">最重要的属性是**异常对象类型**因为这是它将捕获的消息的类型。</span><span class="sxs-lookup"><span data-stu-id="25a38-117">The most important property is the **Exception Object Type** because this is the type of message it will catch.</span></span>  
  
    |<span data-ttu-id="25a38-118">属性</span><span class="sxs-lookup"><span data-stu-id="25a38-118">Property</span></span>|<span data-ttu-id="25a38-119">Description</span><span class="sxs-lookup"><span data-stu-id="25a38-119">Description</span></span>|  
    |--------------|-----------------|  
    |<span data-ttu-id="25a38-120">异常对象名称</span><span class="sxs-lookup"><span data-stu-id="25a38-120">Exception Object Name</span></span>|<span data-ttu-id="25a38-121">为异常处理程序捕获的异常对象中指定一个名称。</span><span class="sxs-lookup"><span data-stu-id="25a38-121">Assigns a name to the exception object caught by the exception handler.</span></span>|  
    |<span data-ttu-id="25a38-122">异常对象类型</span><span class="sxs-lookup"><span data-stu-id="25a38-122">Exception Object Type</span></span>|<span data-ttu-id="25a38-123">确定此异常处理程序将要捕获的从 System.Exception 派生的对象类型。</span><span class="sxs-lookup"><span data-stu-id="25a38-123">Determines the object type (derived from System.Exception) that this exception handler will catch.</span></span>|  
  
3.  <span data-ttu-id="25a38-124">在**属性**窗口中，单击**异常对象类型**列表。</span><span class="sxs-lookup"><span data-stu-id="25a38-124">In the **Properties** window, click the **Exception Object Type** list.</span></span> <span data-ttu-id="25a38-125">此列表包含适配器引发一般异常。</span><span class="sxs-lookup"><span data-stu-id="25a38-125">This list contains the general exception that is thrown by the adapter.</span></span>  
  
     <span data-ttu-id="25a38-126">该名称显示为在到后端系统，例如，ps。 端口中设置的错误SQLExecute.Fault。</span><span class="sxs-lookup"><span data-stu-id="25a38-126">The name appears as the fault you set in the port to the back-end system, for example, PS.SQLExecute.Fault.</span></span>  
  
4.  <span data-ttu-id="25a38-127">为添加名称**异常对象名称**，例如，测试。</span><span class="sxs-lookup"><span data-stu-id="25a38-127">Add a name for the **Exception Object Name**, for example, Test.</span></span>  
  
     <span data-ttu-id="25a38-128">内部**捕获异常**块中，添加形状来创建用于处理异常的进程。</span><span class="sxs-lookup"><span data-stu-id="25a38-128">Inside the **Catch Exception** block, add shapes to create the process for handling the exception.</span></span>  
  
    1.  <span data-ttu-id="25a38-129">右键单击以下**捕获异常**，指向**插入形状**，然后选择**构造消息**。</span><span class="sxs-lookup"><span data-stu-id="25a38-129">Right-click below the **Catch Exception**, point to **Insert Shape**, and select **Construct Message**.</span></span>  
  
         ![](../core/media/siebeladapter-20-exceptionhandling-constructmessage.gif "SiebelAdapter_20_ExceptionHandling_ConstructMessage")  
  
    2.  <span data-ttu-id="25a38-130">在双击**MessageAssignment**以打开文本编辑器并输入消息赋值。</span><span class="sxs-lookup"><span data-stu-id="25a38-130">Double-click inside **MessageAssignment** to open the Text Editor and enter the Message assignment.</span></span>  
  
         <span data-ttu-id="25a38-131">输入你在中设置的名称**异常对象名称**从**捕获异常**，和新创建的错误消息。</span><span class="sxs-lookup"><span data-stu-id="25a38-131">Enter the name that you set in the **Exception Object Name** from the **Catch Exception**, and the new message you created for the fault.</span></span>  
  
         <span data-ttu-id="25a38-132">例如，键入 `Message_3 = Test`。</span><span class="sxs-lookup"><span data-stu-id="25a38-132">For example, type `Message_3 = Test`.</span></span>  
  
         ![](../core/media/siebeladapter-21-exceptionhandling-message3test.gif "SiebelAdapter_21_ExceptionHandling_Message3Test")  
  
## <a name="see-also"></a><span data-ttu-id="25a38-133">另请参阅</span><span class="sxs-lookup"><span data-stu-id="25a38-133">See Also</span></span>  
 <span data-ttu-id="25a38-134">[如何添加作用域形状](../core/how-to-add-a-scope-shape1.md) </span><span class="sxs-lookup"><span data-stu-id="25a38-134">[How to Add a Scope Shape](../core/how-to-add-a-scope-shape1.md) </span></span>  
 <span data-ttu-id="25a38-135">[完成的异常消息](../core/completing-the-exception-message3.md) </span><span class="sxs-lookup"><span data-stu-id="25a38-135">[Completing the Exception Message](../core/completing-the-exception-message3.md) </span></span>  
 [<span data-ttu-id="25a38-136">使用 BizTalk Server 异常处理</span><span class="sxs-lookup"><span data-stu-id="25a38-136">Using BizTalk Server Exception Handling</span></span>](../core/using-biztalk-server-exception-handling2.md)