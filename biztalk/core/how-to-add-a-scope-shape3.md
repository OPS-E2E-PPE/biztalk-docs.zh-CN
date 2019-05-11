---
title: 如何添加作用域形状 3 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- Scope shapes, adding
ms.assetid: 8068ce97-4409-4c88-89e8-6505b56cefc5
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 85b022dc0335ccd3b247c5c2fcad0553fad2ede4
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65387343"
---
# <a name="how-to-add-a-scope-shape"></a><span data-ttu-id="75cf4-102">如何添加作用域形状</span><span class="sxs-lookup"><span data-stu-id="75cf4-102">How to Add a Scope Shape</span></span>
<span data-ttu-id="75cf4-103">使用以下过程添加作用域形状。</span><span class="sxs-lookup"><span data-stu-id="75cf4-103">Use the following procedure to add a Scope shape.</span></span>  
  
### <a name="to-add-a-scope-shape"></a><span data-ttu-id="75cf4-104">若要添加作用域形状</span><span class="sxs-lookup"><span data-stu-id="75cf4-104">To add a Scope Shape</span></span>  
  
1.  <span data-ttu-id="75cf4-105">右键单击下的箭头**接收**端口，指向**插入形状**，然后选择**范围**。</span><span class="sxs-lookup"><span data-stu-id="75cf4-105">Right-click the arrow below the **Receive** port, point to **Insert Shape**, and then select **Scope**.</span></span>  
  
     <span data-ttu-id="75cf4-106">![](../core/media/siebeladapter-18-exceptionhandling-insertscope.gif "SiebelAdapter_18_ExceptionHandling_InsertScope")</span><span class="sxs-lookup"><span data-stu-id="75cf4-106">![](../core/media/siebeladapter-18-exceptionhandling-insertscope.gif "SiebelAdapter_18_ExceptionHandling_InsertScope")</span></span>  
  
     <span data-ttu-id="75cf4-107">在中**作用域**形状，你将可能有错误的操作设置。</span><span class="sxs-lookup"><span data-stu-id="75cf4-107">In the **Scope** shape, you set operations that might have a fault.</span></span>  
  
     <span data-ttu-id="75cf4-108">例如，在 SQLExecute 业务流程中添加发送、 接收和发送端口。</span><span class="sxs-lookup"><span data-stu-id="75cf4-108">For example, add a send, a receive, and a send port in an SQLExecute orchestration.</span></span> <span data-ttu-id="75cf4-109">在此示例中，向服务器发送一条消息。</span><span class="sxs-lookup"><span data-stu-id="75cf4-109">In this example, you send a message to SERVER.</span></span> <span data-ttu-id="75cf4-110">服务器发出响应。</span><span class="sxs-lookup"><span data-stu-id="75cf4-110">SERVER gives a response.</span></span> <span data-ttu-id="75cf4-111">它运行业务流程的其余部分，并返回到 outFile 端口返回信息。</span><span class="sxs-lookup"><span data-stu-id="75cf4-111">It runs the rest of the orchestration and returns information back to the outFile port.</span></span>  
  
2.  <span data-ttu-id="75cf4-112">在中**作用域**形状中，设置**事务**到**None**。</span><span class="sxs-lookup"><span data-stu-id="75cf4-112">In the **Scope** shape, set the **Transaction** to **None**.</span></span>  
  
3.  <span data-ttu-id="75cf4-113">内右击**作用域**形状，然后选择**新建异常处理程序**。</span><span class="sxs-lookup"><span data-stu-id="75cf4-113">Right-click inside the **Scope** shape, and select **New Exception Handler**.</span></span>  
  
     <span data-ttu-id="75cf4-114">![](../core/media/siebeladapter-19-exceptionhandling-newexception.gif "SiebelAdapter_19_ExceptionHandling_NewException")</span><span class="sxs-lookup"><span data-stu-id="75cf4-114">![](../core/media/siebeladapter-19-exceptionhandling-newexception.gif "SiebelAdapter_19_ExceptionHandling_NewException")</span></span>  
  
     <span data-ttu-id="75cf4-115">这将创建**捕获异常**块。</span><span class="sxs-lookup"><span data-stu-id="75cf4-115">This creates the **Catch Exception** block.</span></span> <span data-ttu-id="75cf4-116">如果从后端系统会发生异常，则在捕获到**捕获异常**块。</span><span class="sxs-lookup"><span data-stu-id="75cf4-116">If an exception occurs from the back-end system, it is caught inside the **Catch Exception** block.</span></span>  
  
4.  <span data-ttu-id="75cf4-117">在中**捕获异常**块中，必须添加逻辑。</span><span class="sxs-lookup"><span data-stu-id="75cf4-117">In the **Catch Exception** block, you must add the logic.</span></span>  
  
     <span data-ttu-id="75cf4-118">必须设置的最重要逻辑是您希望收到的错误消息的类型。</span><span class="sxs-lookup"><span data-stu-id="75cf4-118">The most important logic that you must set is the type of error message that you expect to receive.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="75cf4-119">请参阅</span><span class="sxs-lookup"><span data-stu-id="75cf4-119">See Also</span></span>  
 [<span data-ttu-id="75cf4-120">使用 BizTalk Server 的异常处理</span><span class="sxs-lookup"><span data-stu-id="75cf4-120">Using BizTalk Server Exception Handling</span></span>](../core/using-biztalk-server-exception-handling1.md)