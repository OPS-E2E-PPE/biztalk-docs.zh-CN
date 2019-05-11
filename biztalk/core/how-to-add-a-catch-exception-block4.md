---
title: 如何添加捕获异常 Block4 |Microsoft Docs
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
ms.openlocfilehash: 9cf27fd031f5887eed499eb1b10418fa911a127c
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65387370"
---
# <a name="how-to-add-a-catch-exception-block"></a><span data-ttu-id="27189-102">如何添加捕获异常块</span><span class="sxs-lookup"><span data-stu-id="27189-102">How to Add a Catch Exception Block</span></span>
<span data-ttu-id="27189-103">**捕获异常**块代表异常处理程序。</span><span class="sxs-lookup"><span data-stu-id="27189-103">The **Catch Exception** block represents an exception handler.</span></span> <span data-ttu-id="27189-104">**捕获异常**块附加到的末尾**作用域**形状在业务流程设计器中的。</span><span class="sxs-lookup"><span data-stu-id="27189-104">**Catch Exception** blocks are attached to the end of a **Scope** shape in Orchestration Designer.</span></span> <span data-ttu-id="27189-105">可以附加任意数量**捕获异常**块。</span><span class="sxs-lookup"><span data-stu-id="27189-105">You can attach as many **Catch Exception** blocks as you need.</span></span>  
  
 <span data-ttu-id="27189-106">您可以将设置异常处理程序来处理不同类型的异常。</span><span class="sxs-lookup"><span data-stu-id="27189-106">You can set up exception handlers to handle different kinds of exceptions.</span></span> <span data-ttu-id="27189-107">在每个异常处理程序中，指定一个异常类型，它必须是异常或是从类 System 派生的对象。</span><span class="sxs-lookup"><span data-stu-id="27189-107">On each exception handler, you specify an exception type, which must be either an exception or an object derived from the class System.</span></span> <span data-ttu-id="27189-108">如果引发异常，异常处理程序中的指定的类型相匹配，则调用该异常处理程序。</span><span class="sxs-lookup"><span data-stu-id="27189-108">If an exception is thrown that matches the specified type in an exception handler, that exception handler is called.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="27189-109">若要添加**捕获异常**阻止**作用域**形状的事务类型属性**作用域**形状必须设置为**无**或**长时间运行的**。</span><span class="sxs-lookup"><span data-stu-id="27189-109">To add a **Catch Exception** block to a **Scope** shape, the Transaction Type property of the **Scope** shape must be set to **None** or **Long Running**.</span></span>  
  
|<span data-ttu-id="27189-110">添加和填充捕获异常块</span><span class="sxs-lookup"><span data-stu-id="27189-110">Adding and populating a Catch Exception block</span></span>|  
|---------------------------------------------------|  
|<span data-ttu-id="27189-111">1.右键单击**作用域**你想要添加的形状**捕获异常**阻止对，然后单击**新建异常处理程序**。</span><span class="sxs-lookup"><span data-stu-id="27189-111">1.  Right-click the **Scope** shape that you want to add a **Catch Exception** block to, and click **New Exception Handler**.</span></span><br />     <span data-ttu-id="27189-112">一个**捕获异常**块添加到紧跟相关业务流程**作用域**形状。</span><span class="sxs-lookup"><span data-stu-id="27189-112">A **Catch Exception** block is added to the orchestration immediately following the associated **Scope** shape.</span></span><br /><span data-ttu-id="27189-113">2.在中**属性**窗口中，指定的属性。</span><span class="sxs-lookup"><span data-stu-id="27189-113">2.  In the **Properties** window, specify the properties.</span></span> <span data-ttu-id="27189-114">最重要的是**异常对象类型**; 这是将捕获的消息类型。</span><span class="sxs-lookup"><span data-stu-id="27189-114">The most important is the **Exception Object Type**; this is the type of message it will catch.</span></span><br />     <span data-ttu-id="27189-115">**异常对象名称**</span><span class="sxs-lookup"><span data-stu-id="27189-115">**Exception Object Name**</span></span><br />     <span data-ttu-id="27189-116">-为指定的异常处理程序捕获的异常对象名称。</span><span class="sxs-lookup"><span data-stu-id="27189-116">- Assigns a name to the exception object caught by the exception handler.</span></span><br />     <span data-ttu-id="27189-117">**异常对象类型**</span><span class="sxs-lookup"><span data-stu-id="27189-117">**Exception Object Type**</span></span><br />     <span data-ttu-id="27189-118">-确定 （从 System.Exception 派生） 的对象类型，将会捕获此异常处理程序。</span><span class="sxs-lookup"><span data-stu-id="27189-118">- Determines the object type (derived from System.Exception) that this exception handler will catch.</span></span><br /><span data-ttu-id="27189-119">3.在中**属性**窗口中，打开**异常对象类型**列表。</span><span class="sxs-lookup"><span data-stu-id="27189-119">3.  In the **Properties** window, open the **Exception Object Type** list.</span></span> <span data-ttu-id="27189-120">此列表包含**一般异常**。</span><span class="sxs-lookup"><span data-stu-id="27189-120">This list contains the **General Exception**.</span></span><br /><span data-ttu-id="27189-121">4.内部**捕获异常**块中，添加形状以创建处理异常进程。</span><span class="sxs-lookup"><span data-stu-id="27189-121">4.  Inside the **Catch Exception** block, add shapes to create the process for handling the exception.</span></span><br /><span data-ttu-id="27189-122">5.下单击鼠标右键**捕获异常**，依次指向**插入形状**，然后选择**构造消息**。</span><span class="sxs-lookup"><span data-stu-id="27189-122">5.  Right-click below the **Catch Exception**, point to **Insert Shape**, and select **Construct Message**.</span></span><br /><span data-ttu-id="27189-123">6.双击**MessageAssignment**以激活文本编辑器中，并输入消息赋值。</span><span class="sxs-lookup"><span data-stu-id="27189-123">6.  Double-click inside **MessageAssignment** to activate the Text Editor, and enter the Message assignment.</span></span><br />     <span data-ttu-id="27189-124">例如，键入 Message_3 = Test。</span><span class="sxs-lookup"><span data-stu-id="27189-124">For example, type in Message_3 = Test.</span></span><br />     <span data-ttu-id="27189-125">![](../core/media/siebeladapter-21-exceptionhandling-message3test.gif "SiebelAdapter_21_ExceptionHandling_Message3Test")</span><span class="sxs-lookup"><span data-stu-id="27189-125">![](../core/media/siebeladapter-21-exceptionhandling-message3test.gif "SiebelAdapter_21_ExceptionHandling_Message3Test")</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="27189-126">请参阅</span><span class="sxs-lookup"><span data-stu-id="27189-126">See Also</span></span>  
 <span data-ttu-id="27189-127">[完成异常消息](../core/completing-the-exception-message2.md) </span><span class="sxs-lookup"><span data-stu-id="27189-127">[Completing the Exception Message](../core/completing-the-exception-message2.md) </span></span>  
 <span data-ttu-id="27189-128">[如何添加作用域形状](../core/how-to-add-a-scope-shape3.md) </span><span class="sxs-lookup"><span data-stu-id="27189-128">[How to Add a Scope Shape](../core/how-to-add-a-scope-shape3.md) </span></span>  
 [<span data-ttu-id="27189-129">使用 BizTalk Server 的异常处理</span><span class="sxs-lookup"><span data-stu-id="27189-129">Using BizTalk Server Exception Handling</span></span>](../core/using-biztalk-server-exception-handling1.md)