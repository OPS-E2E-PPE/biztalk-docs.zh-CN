---
title: 如何添加 Catch 异常 Block4 |Microsoft 文档
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- Catch Exception blocks, adding
- exception handling, Catch Exception blocks
ms.assetid: 632fa089-a1af-4126-b32b-68d4d8942387
caps.latest.revision: 12
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: b409f25fc32c609bb4c1a80c0582cdb1c363e965
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22246821"
---
# <a name="how-to-add-a-catch-exception-block"></a><span data-ttu-id="618fe-102">如何添加 Catch 异常块</span><span class="sxs-lookup"><span data-stu-id="618fe-102">How to Add a Catch Exception Block</span></span>
<span data-ttu-id="618fe-103">**捕获异常**块代表一个异常处理程序。</span><span class="sxs-lookup"><span data-stu-id="618fe-103">The **Catch Exception** block represents an exception handler.</span></span> <span data-ttu-id="618fe-104">**捕获异常**块附加到的末尾**作用域**中业务流程设计器形状。</span><span class="sxs-lookup"><span data-stu-id="618fe-104">**Catch Exception** blocks are attached to the end of a **Scope** shape in Orchestration Designer.</span></span> <span data-ttu-id="618fe-105">你可以将作为许多附加**捕获异常**阻止根据你的需要。</span><span class="sxs-lookup"><span data-stu-id="618fe-105">You can attach as many **Catch Exception** blocks as you need.</span></span>  
  
 <span data-ttu-id="618fe-106">你可以设置异常处理程序来处理不同种类的异常。</span><span class="sxs-lookup"><span data-stu-id="618fe-106">You can set up exception handlers to handle different kinds of exceptions.</span></span> <span data-ttu-id="618fe-107">对每个异常处理程序，您应指定一个异常类型，该类型必须是异常或是从类 System 派生的对象。</span><span class="sxs-lookup"><span data-stu-id="618fe-107">On each exception handler, you specify an exception type, which must be either an exception or an object derived from the class System.</span></span> <span data-ttu-id="618fe-108">如果将引发异常，异常处理程序中的指定的类型相匹配，则调用该异常处理程序。</span><span class="sxs-lookup"><span data-stu-id="618fe-108">If an exception is thrown that matches the specified type in an exception handler, that exception handler is called.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="618fe-109">若要添加**捕获异常**阻止**作用域**形状的事务类型属性**作用域**形状必须设置为**无**或**长时间运行的**。</span><span class="sxs-lookup"><span data-stu-id="618fe-109">To add a **Catch Exception** block to a **Scope** shape, the Transaction Type property of the **Scope** shape must be set to **None** or **Long Running**.</span></span>  
  
|<span data-ttu-id="618fe-110">添加和填充捕获异常块</span><span class="sxs-lookup"><span data-stu-id="618fe-110">Adding and populating a Catch Exception block</span></span>|  
|---------------------------------------------------|  
|<span data-ttu-id="618fe-111">1.右键单击**作用域**你想要添加的形状**捕获异常**块，并单击**新异常处理程序**。</span><span class="sxs-lookup"><span data-stu-id="618fe-111">1.  Right-click the **Scope** shape that you want to add a **Catch Exception** block to, and click **New Exception Handler**.</span></span><br />     <span data-ttu-id="618fe-112">A**捕获异常**块添加到紧跟在关联的业务流程**作用域**形状。</span><span class="sxs-lookup"><span data-stu-id="618fe-112">A **Catch Exception** block is added to the orchestration immediately following the associated **Scope** shape.</span></span><br /><span data-ttu-id="618fe-113">2.在**属性**窗口中，指定的属性。</span><span class="sxs-lookup"><span data-stu-id="618fe-113">2.  In the **Properties** window, specify the properties.</span></span> <span data-ttu-id="618fe-114">最重要的是**异常对象类型**; 这是它将捕获的消息的类型。</span><span class="sxs-lookup"><span data-stu-id="618fe-114">The most important is the **Exception Object Type**; this is the type of message it will catch.</span></span><br />     <span data-ttu-id="618fe-115">**异常对象名称**</span><span class="sxs-lookup"><span data-stu-id="618fe-115">**Exception Object Name**</span></span><br />     <span data-ttu-id="618fe-116">-将名称分配给异常处理程序捕获的异常对象。</span><span class="sxs-lookup"><span data-stu-id="618fe-116">- Assigns a name to the exception object caught by the exception handler.</span></span><br />     <span data-ttu-id="618fe-117">**异常对象类型**</span><span class="sxs-lookup"><span data-stu-id="618fe-117">**Exception Object Type**</span></span><br />     <span data-ttu-id="618fe-118">-确定 （从 System.Exception 派生） 的对象类型，将捕获此异常处理程序。</span><span class="sxs-lookup"><span data-stu-id="618fe-118">- Determines the object type (derived from System.Exception) that this exception handler will catch.</span></span><br /><span data-ttu-id="618fe-119">3.在**属性**窗口中，打开**异常对象类型**列表。</span><span class="sxs-lookup"><span data-stu-id="618fe-119">3.  In the **Properties** window, open the **Exception Object Type** list.</span></span> <span data-ttu-id="618fe-120">此列表包含**一般异常**。</span><span class="sxs-lookup"><span data-stu-id="618fe-120">This list contains the **General Exception**.</span></span><br /><span data-ttu-id="618fe-121">4.内部**捕获异常**块中，添加形状来创建用于处理异常的进程。</span><span class="sxs-lookup"><span data-stu-id="618fe-121">4.  Inside the **Catch Exception** block, add shapes to create the process for handling the exception.</span></span><br /><span data-ttu-id="618fe-122">5.右键单击以下**捕获异常**，指向**插入形状**，然后选择**构造消息**。</span><span class="sxs-lookup"><span data-stu-id="618fe-122">5.  Right-click below the **Catch Exception**, point to **Insert Shape**, and select **Construct Message**.</span></span><br /><span data-ttu-id="618fe-123">6.在双击**MessageAssignment**以激活文本编辑器中，并输入消息赋值。</span><span class="sxs-lookup"><span data-stu-id="618fe-123">6.  Double-click inside **MessageAssignment** to activate the Text Editor, and enter the Message assignment.</span></span><br />     <span data-ttu-id="618fe-124">例如，键入 Message_3 = Test。</span><span class="sxs-lookup"><span data-stu-id="618fe-124">For example, type in Message_3 = Test.</span></span><br />     ![](../core/media/siebeladapter-21-exceptionhandling-message3test.gif "SiebelAdapter_21_ExceptionHandling_Message3Test")|  
  
## <a name="see-also"></a><span data-ttu-id="618fe-125">另请参阅</span><span class="sxs-lookup"><span data-stu-id="618fe-125">See Also</span></span>  
 <span data-ttu-id="618fe-126">[完成的异常消息](../core/completing-the-exception-message2.md) </span><span class="sxs-lookup"><span data-stu-id="618fe-126">[Completing the Exception Message](../core/completing-the-exception-message2.md) </span></span>  
 <span data-ttu-id="618fe-127">[如何添加作用域形状](../core/how-to-add-a-scope-shape3.md) </span><span class="sxs-lookup"><span data-stu-id="618fe-127">[How to Add a Scope Shape](../core/how-to-add-a-scope-shape3.md) </span></span>  
 [<span data-ttu-id="618fe-128">使用 BizTalk Server 异常处理</span><span class="sxs-lookup"><span data-stu-id="618fe-128">Using BizTalk Server Exception Handling</span></span>](../core/using-biztalk-server-exception-handling1.md)