---
title: 如何添加 Catch 异常 Block5 |Microsoft 文档
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
ms.assetid: 4875060c-976c-40e7-830a-ffd1a47ba68a
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: f6c045677fb2d177377725a3f11e81a5c5c70f9e
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22246501"
---
# <a name="how-to-add-a-catch-exception-block"></a><span data-ttu-id="93d56-102">如何添加 Catch 异常块</span><span class="sxs-lookup"><span data-stu-id="93d56-102">How to Add a Catch Exception Block</span></span>
<span data-ttu-id="93d56-103">若要添加**捕获异常**阻止**作用域**形状，**事务类型**属性**作用域**形状必须设置为**无**或**长时间运行的**。</span><span class="sxs-lookup"><span data-stu-id="93d56-103">To add a **Catch Exception** block to a **Scope** shape, the **Transaction Type** property of the **Scope** shape must be set to **None** or **Long Running**.</span></span>  
  
### <a name="to-add-a-catch-exception-block"></a><span data-ttu-id="93d56-104">若要添加 catch 异常块</span><span class="sxs-lookup"><span data-stu-id="93d56-104">To add a catch exception block</span></span>  
  
1.  <span data-ttu-id="93d56-105">右键单击**作用域**形状，并依次**新异常处理程序**。</span><span class="sxs-lookup"><span data-stu-id="93d56-105">Right-click the **Scope** shape, and then click **New Exception Handler**.</span></span>  
  
     <span data-ttu-id="93d56-106">A**捕获异常**块添加到紧跟在关联的业务流程**作用域**形状。</span><span class="sxs-lookup"><span data-stu-id="93d56-106">A **Catch Exception** block is added to the orchestration immediately following the associated **Scope** shape.</span></span>  
  
2.  <span data-ttu-id="93d56-107">在**属性**窗口中，指定的属性。</span><span class="sxs-lookup"><span data-stu-id="93d56-107">In the **Properties** window, specify the properties.</span></span>  
  
     <span data-ttu-id="93d56-108">最重要的属性是**异常对象类型**; 这是它将捕获的消息的类型。</span><span class="sxs-lookup"><span data-stu-id="93d56-108">The most important property is the **Exception Object Type**; this is the type of message it will catch.</span></span>  
  
    |<span data-ttu-id="93d56-109">属性</span><span class="sxs-lookup"><span data-stu-id="93d56-109">Property</span></span>|<span data-ttu-id="93d56-110">Description</span><span class="sxs-lookup"><span data-stu-id="93d56-110">Description</span></span>|  
    |--------------|-----------------|  
    |<span data-ttu-id="93d56-111">**异常对象名称**</span><span class="sxs-lookup"><span data-stu-id="93d56-111">**Exception Object Name**</span></span>|<span data-ttu-id="93d56-112">为异常处理程序捕获的异常对象中指定一个名称。</span><span class="sxs-lookup"><span data-stu-id="93d56-112">Assigns a name to the exception object caught by the exception handler.</span></span>|  
    |<span data-ttu-id="93d56-113">**异常对象类型**</span><span class="sxs-lookup"><span data-stu-id="93d56-113">**Exception Object Type**</span></span>|<span data-ttu-id="93d56-114">确定此异常处理程序将要捕获的从 System.Exception 派生的对象类型。</span><span class="sxs-lookup"><span data-stu-id="93d56-114">Determines the object type (derived from System.Exception) that this exception handler will catch.</span></span>|  
  
3.  <span data-ttu-id="93d56-115">在**属性**窗口，请在**异常对象类型**列表中，选择**一般异常**。</span><span class="sxs-lookup"><span data-stu-id="93d56-115">In the **Properties** window, in the **Exception Object Type** list, select **General Exception**.</span></span>  
  
4.  <span data-ttu-id="93d56-116">内部**捕获异常**块中，添加形状来创建用于处理异常的进程。</span><span class="sxs-lookup"><span data-stu-id="93d56-116">Inside the **Catch Exception** block, add shapes to create the process for handling the exception.</span></span>  
  
    1.  <span data-ttu-id="93d56-117">右键单击以下**CatchException**和指向**插入形状**，然后选择**构造消息**。</span><span class="sxs-lookup"><span data-stu-id="93d56-117">Right-click below the **CatchException** and point to **Insert Shape**, and then select **Construct Message**.</span></span>  
  
    2.  <span data-ttu-id="93d56-118">在双击**MessageAssignment**以打开文本编辑器并输入消息赋值。</span><span class="sxs-lookup"><span data-stu-id="93d56-118">Double-click inside **MessageAssignment** to open the Text Editor and enter the Message assignment.</span></span>  
  
         <span data-ttu-id="93d56-119">例如，键入 `Message_3 = Test`。</span><span class="sxs-lookup"><span data-stu-id="93d56-119">For example, type `Message_3 = Test`.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="93d56-120">另请参阅</span><span class="sxs-lookup"><span data-stu-id="93d56-120">See Also</span></span>  
 <span data-ttu-id="93d56-121">[完成的异常消息](../core/completing-the-exception-message1.md) </span><span class="sxs-lookup"><span data-stu-id="93d56-121">[Completing the Exception Message](../core/completing-the-exception-message1.md) </span></span>  
 <span data-ttu-id="93d56-122">[如何添加作用域形状](../core/how-to-add-a-scope-shape5.md) </span><span class="sxs-lookup"><span data-stu-id="93d56-122">[How to Add a Scope Shape](../core/how-to-add-a-scope-shape5.md) </span></span>  
 [<span data-ttu-id="93d56-123">使用 BizTalk Server 异常处理</span><span class="sxs-lookup"><span data-stu-id="93d56-123">Using BizTalk Server Exception Handling</span></span>](../core/using-biztalk-server-exception-handling5.md)