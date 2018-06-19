---
title: 如何添加作用域形状 3 |Microsoft 文档
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
ms.openlocfilehash: 8231dfed1ea84ba5c11e0352f789b92cc38d0f83
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22248061"
---
# <a name="how-to-add-a-scope-shape"></a><span data-ttu-id="60105-102">如何添加作用域形状</span><span class="sxs-lookup"><span data-stu-id="60105-102">How to Add a Scope Shape</span></span>
<span data-ttu-id="60105-103">使用以下过程添加作用域形状。</span><span class="sxs-lookup"><span data-stu-id="60105-103">Use the following procedure to add a Scope shape.</span></span>  
  
### <a name="to-add-a-scope-shape"></a><span data-ttu-id="60105-104">若要添加作用域形状</span><span class="sxs-lookup"><span data-stu-id="60105-104">To add a Scope Shape</span></span>  
  
1.  <span data-ttu-id="60105-105">右键单击下箭头**接收**端口，请指向**插入形状**，然后选择**作用域**。</span><span class="sxs-lookup"><span data-stu-id="60105-105">Right-click the arrow below the **Receive** port, point to **Insert Shape**, and then select **Scope**.</span></span>  
  
     ![](../core/media/siebeladapter-18-exceptionhandling-insertscope.gif "SiebelAdapter_18_ExceptionHandling_InsertScope")  
  
     <span data-ttu-id="60105-106">在**作用域**形状，你将操作可能具有错误的设置。</span><span class="sxs-lookup"><span data-stu-id="60105-106">In the **Scope** shape, you set operations that might have a fault.</span></span>  
  
     <span data-ttu-id="60105-107">例如，添加发送、 接收和发送端口 SQLExecute 业务流程中。</span><span class="sxs-lookup"><span data-stu-id="60105-107">For example, add a send, a receive, and a send port in an SQLExecute orchestration.</span></span> <span data-ttu-id="60105-108">在此示例中，将向服务器发送消息。</span><span class="sxs-lookup"><span data-stu-id="60105-108">In this example, you send a message to SERVER.</span></span> <span data-ttu-id="60105-109">服务器发出响应，</span><span class="sxs-lookup"><span data-stu-id="60105-109">SERVER gives a response.</span></span> <span data-ttu-id="60105-110">它运行业务流程的其余部分，并将返回到 outFile 端口的信息。</span><span class="sxs-lookup"><span data-stu-id="60105-110">It runs the rest of the orchestration and returns information back to the outFile port.</span></span>  
  
2.  <span data-ttu-id="60105-111">在**作用域**形状，设置**事务**到**无**。</span><span class="sxs-lookup"><span data-stu-id="60105-111">In the **Scope** shape, set the **Transaction** to **None**.</span></span>  
  
3.  <span data-ttu-id="60105-112">右键单击内部**作用域**形状，然后选择**新异常处理程序**。</span><span class="sxs-lookup"><span data-stu-id="60105-112">Right-click inside the **Scope** shape, and select **New Exception Handler**.</span></span>  
  
     ![](../core/media/siebeladapter-19-exceptionhandling-newexception.gif "SiebelAdapter_19_ExceptionHandling_NewException")  
  
     <span data-ttu-id="60105-113">这将创建**捕获异常**块。</span><span class="sxs-lookup"><span data-stu-id="60105-113">This creates the **Catch Exception** block.</span></span> <span data-ttu-id="60105-114">如果从后端系统，则会发生异常，则将它捕获在**捕获异常**块。</span><span class="sxs-lookup"><span data-stu-id="60105-114">If an exception occurs from the back-end system, it is caught inside the **Catch Exception** block.</span></span>  
  
4.  <span data-ttu-id="60105-115">在**捕获异常**块中，你必须添加的逻辑。</span><span class="sxs-lookup"><span data-stu-id="60105-115">In the **Catch Exception** block, you must add the logic.</span></span>  
  
     <span data-ttu-id="60105-116">必须设置的最重要逻辑是你希望收到的错误消息的类型。</span><span class="sxs-lookup"><span data-stu-id="60105-116">The most important logic that you must set is the type of error message that you expect to receive.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="60105-117">另请参阅</span><span class="sxs-lookup"><span data-stu-id="60105-117">See Also</span></span>  
 [<span data-ttu-id="60105-118">使用 BizTalk Server 异常处理</span><span class="sxs-lookup"><span data-stu-id="60105-118">Using BizTalk Server Exception Handling</span></span>](../core/using-biztalk-server-exception-handling1.md)