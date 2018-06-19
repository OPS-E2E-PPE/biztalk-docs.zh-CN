---
title: 如何添加作用域 Shape1 |Microsoft 文档
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- Scope shapes, adding
- Scope shapes, Catch Exception blocks
- Catch Exception blocks, Scope shapes
- adding, Scope shapes
ms.assetid: dfe039d1-4c4a-4e21-ae03-7ca534aafec3
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 094f744f7d4d6d1c405ea50d222beb8c0a67920e
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22247181"
---
# <a name="how-to-add-a-scope-shape"></a><span data-ttu-id="4eb33-102">如何添加作用域形状</span><span class="sxs-lookup"><span data-stu-id="4eb33-102">How to Add a Scope Shape</span></span>
<span data-ttu-id="4eb33-103">请按照这些步骤添加作用域形状。</span><span class="sxs-lookup"><span data-stu-id="4eb33-103">Follow these steps to add a Scope shape.</span></span>  
  
### <a name="to-add-a-scope-shape"></a><span data-ttu-id="4eb33-104">若要添加作用域形状</span><span class="sxs-lookup"><span data-stu-id="4eb33-104">To add a Scope Shape</span></span>  
  
1.  <span data-ttu-id="4eb33-105">右键单击下箭头**ReceiveFromIn**端口，请指向**插入形状**，然后单击**作用域**。</span><span class="sxs-lookup"><span data-stu-id="4eb33-105">Right-click the arrow below the **ReceiveFromIn** port, point to **Insert Shape**, and then click **Scope**.</span></span>  
  
     ![](../core/media/siebeladapter-18-exceptionhandling-insertscope.gif "SiebelAdapter_18_ExceptionHandling_InsertScope")  
  
     <span data-ttu-id="4eb33-106">在作用域形状中，你将可能具有错误的操作。</span><span class="sxs-lookup"><span data-stu-id="4eb33-106">In the Scope shape, you set operations that might have a fault.</span></span>  
  
     <span data-ttu-id="4eb33-107">例如，添加发送、 接收和发送端口 SQLExecute 业务流程中。</span><span class="sxs-lookup"><span data-stu-id="4eb33-107">For example, add a send, a receive, and a send port in an SQLExecute orchestration.</span></span> <span data-ttu-id="4eb33-108">在此示例中，我们正在向 DB2 发送一条消息。</span><span class="sxs-lookup"><span data-stu-id="4eb33-108">In this example, we are sending a message to DB2.</span></span> <span data-ttu-id="4eb33-109">DB2 提供响应。</span><span class="sxs-lookup"><span data-stu-id="4eb33-109">DB2 gives a response.</span></span> <span data-ttu-id="4eb33-110">它运行业务流程的其余部分，并将返回到 OutFile 端口的信息。</span><span class="sxs-lookup"><span data-stu-id="4eb33-110">It runs the rest of the orchestration and returns information back to the OutFile port.</span></span>  
  
2.  <span data-ttu-id="4eb33-111">在作用域形状中，设置**事务**到**无**。</span><span class="sxs-lookup"><span data-stu-id="4eb33-111">In the Scope shape, set the **Transaction** to **None**.</span></span>  
  
3.  <span data-ttu-id="4eb33-112">在作用域形状中，右键单击并选择**新异常处理程序**。</span><span class="sxs-lookup"><span data-stu-id="4eb33-112">Right-click inside the Scope shape, and select **New Exception Handler**.</span></span>  
  
     ![](../core/media/siebeladapter-19-exceptionhandling-newexception.gif "SiebelAdapter_19_ExceptionHandling_NewException")  
  
     <span data-ttu-id="4eb33-113">这将创建“捕获异常”块。</span><span class="sxs-lookup"><span data-stu-id="4eb33-113">This creates the Catch Exception block.</span></span> <span data-ttu-id="4eb33-114">如果从后端，则会发生异常，它会捕获到捕获异常块内。</span><span class="sxs-lookup"><span data-stu-id="4eb33-114">If an exception occurs from the back-end, it is caught inside the Catch Exception block.</span></span>  
  
4.  <span data-ttu-id="4eb33-115">在“捕获异常”块中，必须添加逻辑。</span><span class="sxs-lookup"><span data-stu-id="4eb33-115">In the Catch Exception block, you must add the logic.</span></span>  
  
     <span data-ttu-id="4eb33-116">必须设置的最重要的逻辑是你期望出现的错误消息的类型。</span><span class="sxs-lookup"><span data-stu-id="4eb33-116">The most important logic you must set is the type of error message you are expecting.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4eb33-117">另请参阅</span><span class="sxs-lookup"><span data-stu-id="4eb33-117">See Also</span></span>  
 [<span data-ttu-id="4eb33-118">使用 BizTalk Server 异常处理</span><span class="sxs-lookup"><span data-stu-id="4eb33-118">Using BizTalk Server Exception Handling</span></span>](../core/using-biztalk-server-exception-handling2.md)